# DepFSNotifyChildren

- ea: `0x18001127c`
- end: `0x1800114ef`
- name: `DepFSNotifyChildren`
- size: `627`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a120`
- `0x18000cb40`
- `0x1800110c0`

## callees

- `0x1800010b8`
- `0x1800010fc`
- `0x18000f73c`
- `0x18001127c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x180011401`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180011401`
- `ntoskrnl!KeWaitForSingleObject` at `0x180011441`
- `ntoskrnl!KeWaitForSingleObject` at `0x180011441`
- `ntoskrnl!KeInitializeEvent` at `0x18001133f`
- `ntoskrnl!KeInitializeEvent` at `0x18001133f`
- `ntoskrnl!IofCallDriver` at `0x180011417`
- `ntoskrnl!IofCallDriver` at `0x180011417`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800113f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800113f5`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180011389`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180011389`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180011465`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180011465`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180011450`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180011450`

## pseudocode

```c
__int64 __fastcall DepFSNotifyChildren(__int64 a1)
{
  unsigned int v1; // r15d
  __int64 *v2; // rsi
  __int64 *v3; // rdi
  unsigned __int64 v4; // r14
  char *v5; // rbx
  __int64 v6; // rcx
  IRP *v7; // r12
  NTSTATUS Status; // edi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-19h] BYREF
  __int128 InputBuffer; // [rsp+60h] [rbp-9h] BYREF
  __int64 v12; // [rsp+70h] [rbp+7h]
  struct _KEVENT Event; // [rsp+78h] [rbp+Fh] BYREF

  v1 = 0;
  v2 = (__int64 *)(a1 + 8);
  if ( !a1 )
    v2 = &qword_1800051B0;
  v3 = (__int64 *)*v2;
  if ( (__int64 *)*v2 != v2 )
  {
    v4 = (-(__int64)(a1 != 0) & 0xFFFFFFFFFFFFFFE0uLL) + 40;
    do
    {
      v5 = (char *)v3 - v4;
      if ( *(__int64 **)((char *)v3 - v4 + 40) == (__int64 *)((char *)v3 - v4 + 40) || (*((_DWORD *)v5 + 23) & 3) != 0 )
      {
        v3 = (__int64 *)*v3;
      }
      else
      {
        v6 = qword_1800051B0;
        v12 = 0;
        InputBuffer = 0;
        IoStatusBlock = 0;
        memset(&Event, 0, sizeof(Event));
        *(_QWORD *)&InputBuffer = *((_QWORD *)v5 + 13);
        *((_QWORD *)&InputBuffer + 1) = *((_QWORD *)v5 + 15);
        LODWORD(v12) = 1;
        while ( (__int64 *)v6 != &qword_1800051B0 )
        {
          if ( *(_QWORD *)(v6 + 88) == *((_QWORD *)v5 + 16) )
            *(_DWORD *)(v6 + 52) |= 0x20u;
          v6 = *(_QWORD *)v6;
        }
        KeInitializeEvent(&Event, NotificationEvent, 0);
        v7 = IoBuildDeviceIoControlRequest(
               0x2D9194u,
               *((PDEVICE_OBJECT *)v5 + 16),
               &InputBuffer,
               0x18u,
               0,
               0,
               0,
               &Event,
               &IoStatusBlock);
        if ( v7 )
        {
          *((_DWORD *)v5 + 23) |= 1u;
          ++*((_DWORD *)v5 + 14);
          ExReleaseResourceLite(&Resource);
          KeLeaveCriticalRegion();
          Status = IofCallDriver(*((PDEVICE_OBJECT *)v5 + 16), v7);
          if ( Status == 259 )
          {
            KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
            Status = IoStatusBlock.Status;
          }
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite(&Resource, 1u);
          if ( Status < 0 )
          {
            v1 = Status;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                WPP_f74f0f1428a330a1ddba74e336bf7301_Traceguids,
                v5,
                Status);
            }
          }
          DereferenceDependencyContext(v5, 1, 0);
          v3 = (__int64 *)*v2;
        }
        else
        {
          v3 = (__int64 *)*v3;
          v1 = -1073741670;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_q(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0x13u,
              (__int64)WPP_f74f0f1428a330a1ddba74e336bf7301_Traceguids,
              v5);
          }
          *((_DWORD *)v5 + 23) |= 2u;
        }
      }
    }
    while ( v3 != v2 );
  }
  return v1;
}

```

## disassembly

```asm
0x18001127c  push    rbp
0x18001127e  push    rbx
0x18001127f  push    rsi
0x180011280  push    rdi
0x180011281  push    r12
0x180011283  push    r14
0x180011285  push    r15
0x180011287  lea     rbp, [rsp-27h]
0x18001128c  sub     rsp, 90h
0x180011293  xor     r15d, r15d
0x180011296  lea     rdx, qword_1800051B0
0x18001129d  lea     rsi, [rcx+8]
0x1800112a1  test    rcx, rcx
0x1800112a4  jnz     short loc_1800112A9
0x1800112a6  mov     rsi, rdx
0x1800112a9  mov     rdi, [rsi]
0x1800112ac  cmp     rdi, rsi
0x1800112af  jz      loc_1800114D9
0x1800112b5  neg     rcx
0x1800112b8  sbb     r14, r14
0x1800112bb  and     r14, 0FFFFFFFFFFFFFFE0h
0x1800112bf  add     r14, 28h ; '('
0x1800112c3  mov     rbx, rdi
0x1800112c6  sub     rbx, r14
0x1800112c9  lea     rax, [rbx+28h]
0x1800112cd  cmp     [rax], rax
0x1800112d0  jz      loc_1800114CD
0x1800112d6  mov     eax, [rbx+5Ch]
0x1800112d9  test    al, 3
0x1800112db  jnz     loc_1800114CD
0x1800112e1  mov     rcx, cs:qword_1800051B0
0x1800112e8  xor     eax, eax
0x1800112ea  mov     [rbp+57h+var_50], rax
0x1800112ee  xorps   xmm0, xmm0
0x1800112f1  movups  [rbp+57h+InputBuffer], xmm0
0x1800112f5  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x1800112f9  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x1800112fd  xorps   xmm1, xmm1
0x180011300  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x180011304  mov     rax, [rbx+68h]
0x180011308  mov     qword ptr [rbp+57h+InputBuffer], rax
0x18001130c  mov     rax, [rbx+78h]
0x180011310  mov     qword ptr [rbp+57h+InputBuffer+8], rax
0x180011314  mov     dword ptr [rbp+57h+var_50], 1
0x18001131b  jmp     short loc_180011331
0x18001131d  mov     rax, [rbx+80h]
0x180011324  cmp     [rcx+58h], rax
0x180011328  jnz     short loc_18001132E
0x18001132a  or      dword ptr [rcx+34h], 20h
0x18001132e  mov     rcx, [rcx]
0x180011331  cmp     rcx, rdx
0x180011334  jnz     short loc_18001131D
0x180011336  xor     r8d, r8d; State
0x180011339  lea     rcx, [rbp+57h+Event]; Event
0x18001133d  xor     edx, edx; Type
0x18001133f  call    cs:__imp_KeInitializeEvent
0x180011346  nop     dword ptr [rax+rax+00h]
0x18001134b  mov     rdx, [rbx+80h]; DeviceObject
0x180011352  lea     rax, [rbp+57h+var_70]
0x180011356  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x18001135b  lea     r8, [rbp+57h+InputBuffer]; InputBuffer
0x18001135f  lea     rax, [rbp+57h+Event]
0x180011363  mov     r9d, 18h; InputBufferLength
0x180011369  mov     [rsp+0C0h+var_88], rax; Event
0x18001136e  mov     ecx, 2D9194h; IoControlCode
0x180011373  mov     [rsp+0C0h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x180011378  mov     [rsp+0C0h+OutputBufferLength], 0; OutputBufferLength
0x180011380  mov     [rsp+0C0h+OutputBuffer], 0; OutputBuffer
0x180011389  call    cs:__imp_IoBuildDeviceIoControlRequest
0x180011390  nop     dword ptr [rax+rax+00h]
0x180011395  mov     r12, rax
0x180011398  test    rax, rax
0x18001139b  jnz     short loc_1800113E7
0x18001139d  mov     rdi, [rdi]
0x1800113a0  mov     r15d, 0C000009Ah
0x1800113a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113ad  lea     rax, WPP_GLOBAL_Control
0x1800113b4  cmp     rcx, rax
0x1800113b7  jz      short loc_1800113DE
0x1800113b9  mov     eax, [rcx+2Ch]
0x1800113bc  test    al, 1
0x1800113be  jz      short loc_1800113DE
0x1800113c0  cmp     byte ptr [rcx+29h], 2
0x1800113c4  jb      short loc_1800113DE
0x1800113c6  mov     rcx, [rcx+18h]
0x1800113ca  lea     edx, [r12+13h]
0x1800113cf  mov     r9, rbx
0x1800113d2  lea     r8, WPP_f74f0f1428a330a1ddba74e336bf7301_Traceguids
0x1800113d9  call    WPP_SF_q
0x1800113de  or      dword ptr [rbx+5Ch], 2
0x1800113e2  jmp     loc_1800114C4
0x1800113e7  or      dword ptr [rbx+5Ch], 1
0x1800113eb  lea     rcx, Resource; Resource
0x1800113f2  inc     dword ptr [rbx+38h]
0x1800113f5  call    cs:__imp_ExReleaseResourceLite
0x1800113fc  nop     dword ptr [rax+rax+00h]
0x180011401  call    cs:__imp_KeLeaveCriticalRegion
0x180011408  nop     dword ptr [rax+rax+00h]
0x18001140d  mov     rcx, [rbx+80h]; DeviceObject
0x180011414  mov     rdx, r12; Irp
0x180011417  call    cs:__imp_IofCallDriver
0x18001141e  nop     dword ptr [rax+rax+00h]
0x180011423  mov     edi, eax
0x180011425  cmp     eax, 103h
0x18001142a  jnz     short loc_180011450
0x18001142c  xor     r9d, r9d; Alertable
0x18001142f  mov     [rsp+0C0h+OutputBuffer], 0; Timeout
0x180011438  xor     r8d, r8d; WaitMode
0x18001143b  lea     rcx, [rbp+57h+Event]; Object
0x18001143f  xor     edx, edx; WaitReason
0x180011441  call    cs:__imp_KeWaitForSingleObject
0x180011448  nop     dword ptr [rax+rax+00h]
0x18001144d  mov     edi, dword ptr [rbp+57h+var_70]
0x180011450  call    cs:__imp_KeEnterCriticalRegion
0x180011457  nop     dword ptr [rax+rax+00h]
0x18001145c  mov     dl, 1; Wait
0x18001145e  lea     rcx, Resource; Resource
0x180011465  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18001146c  nop     dword ptr [rax+rax+00h]
0x180011471  test    edi, edi
0x180011473  jns     short loc_1800114B4
0x180011475  mov     r15d, edi
0x180011478  mov     rcx, cs:WPP_GLOBAL_Control
0x18001147f  lea     rax, WPP_GLOBAL_Control
0x180011486  cmp     rcx, rax
0x180011489  jz      short loc_1800114B4
0x18001148b  mov     eax, [rcx+2Ch]
0x18001148e  test    al, 1
0x180011490  jz      short loc_1800114B4
0x180011492  cmp     byte ptr [rcx+29h], 2
0x180011496  jb      short loc_1800114B4
0x180011498  mov     rcx, [rcx+18h]
0x18001149c  lea     r8, WPP_f74f0f1428a330a1ddba74e336bf7301_Traceguids
0x1800114a3  mov     edx, 14h
0x1800114a8  mov     dword ptr [rsp+0C0h+OutputBuffer], edi
0x1800114ac  mov     r9, rbx
0x1800114af  call    WPP_SF_qD
0x1800114b4  xor     r8d, r8d
0x1800114b7  mov     dl, 1
0x1800114b9  mov     rcx, rbx; P
0x1800114bc  call    DereferenceDependencyContext
0x1800114c1  mov     rdi, [rsi]
0x1800114c4  lea     rdx, qword_1800051B0
0x1800114cb  jmp     short loc_1800114D0
0x1800114cd  mov     rdi, [rdi]
0x1800114d0  cmp     rdi, rsi
0x1800114d3  jnz     loc_1800112C3
0x1800114d9  mov     eax, r15d
0x1800114dc  add     rsp, 90h
0x1800114e3  pop     r15
0x1800114e5  pop     r14
0x1800114e7  pop     r12
0x1800114e9  pop     rdi
0x1800114ea  pop     rsi
0x1800114eb  pop     rbx
0x1800114ec  pop     rbp
0x1800114ed  retn
```
