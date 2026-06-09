# DepFSAutochkWaitWorker

- ea: `0x180008010`
- end: `0x180008446`
- name: `DepFSAutochkWaitWorker`
- size: `1078`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001020`
- `0x180001064`
- `0x1800010b8`
- `0x1800011a4`
- `0x180008010`
- `0x18000a32c`
- `0x18000eac0`
- `0x18000f73c`
- `0x18000f91c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800082b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008419`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800082b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008419`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800082f9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800082f9`
- `ntoskrnl!KeInitializeEvent` at `0x1800081fb`
- `ntoskrnl!KeInitializeEvent` at `0x1800081fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800083ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800083ed`
- `ntoskrnl!IofCallDriver` at `0x1800082cf`
- `ntoskrnl!IofCallDriver` at `0x1800082cf`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x18000806e`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x18000806e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800082ab`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000840d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800082ab`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000840d`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180008245`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180008245`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800080ab`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008179`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008386`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800080ab`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008179`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008386`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008096`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008164`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008371`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008096`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008164`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008371`
- `ntoskrnl!KeDelayExecutionThread` at `0x180008062`
- `ntoskrnl!KeDelayExecutionThread` at `0x180008062`

## pseudocode

```c
void __fastcall DepFSAutochkWaitWorker(PVOID StartContext)
{
  char v1; // bl
  __int64 v2; // rdx
  int v3; // eax
  _DWORD *v4; // rcx
  unsigned int v5; // r14d
  _DWORD *v6; // rdi
  __int64 v7; // rdi
  int v8; // edx
  int v9; // eax
  IRP *v10; // rsi
  NTSTATUS Status; // esi
  unsigned int i; // edi
  _DWORD *v13; // rsi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+7h] BYREF
  __int128 InputBuffer; // [rsp+60h] [rbp+17h] BYREF
  __int64 v16; // [rsp+70h] [rbp+27h]
  struct _KEVENT Event; // [rsp+78h] [rbp+2Fh] BYREF
  PVOID P; // [rsp+B8h] [rbp+6Fh] BYREF
  union _LARGE_INTEGER Interval; // [rsp+C0h] [rbp+77h] BYREF

  P = 0;
  v1 = 0;
  v16 = 0;
  IoStatusBlock = 0;
  memset(&Event, 0, sizeof(Event));
  InputBuffer = 0;
  while ( !FsRtlAreVolumeStartupApplicationsComplete() )
  {
    Interval.QuadPart = -10000000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  if ( !byte_180005194 && !byte_180005196 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    v1 = 1;
    if ( !byte_180005194 && !byte_180005196 && dword_1800051C4 != 4 )
    {
      v3 = DepFSGenerateDependencyList(0, 0, 0, &P, 1, 0x8000);
      if ( v3 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          23,
          WPP_a4016d7e857d3af68560d770380f4c36_Traceguids,
          (unsigned int)v3);
      }
      v4 = P;
      if ( P )
      {
        v5 = 0;
        if ( *((_DWORD *)P + 1) )
        {
          do
          {
            v6 = &v4[4 * v5];
            if ( !v1 )
            {
              v1 = 1;
              KeEnterCriticalRegion();
              ExAcquireResourceExclusiveLite(&Resource, 1u);
              v4 = P;
            }
            if ( (v6[2] & 2) != 0 )
            {
              v7 = *((_QWORD *)v6 + 2);
              if ( *(_QWORD *)(v7 + 40) != v7 + 40 )
              {
                v8 = *(_DWORD *)(v7 + 60);
                if ( (v8 & 4) == 0 )
                {
                  v9 = *(_DWORD *)(v7 + 92);
                  if ( (v9 & 0x403) == 0 )
                  {
                    if ( (v8 & 2) != 0 )
                    {
                      *(_DWORD *)(v7 + 92) = v9 | 0x200;
                      LODWORD(v16) = 2;
                    }
                    else
                    {
                      *(_DWORD *)(v7 + 92) = v9 | 0x600;
                      LODWORD(v16) = 18;
                    }
                    *(_QWORD *)&InputBuffer = *(_QWORD *)(v7 + 104);
                    *((_QWORD *)&InputBuffer + 1) = *(_QWORD *)(v7 + 120);
                    KeInitializeEvent(&Event, NotificationEvent, 0);
                    v10 = IoBuildDeviceIoControlRequest(
                            0x2D9198u,
                            *(PDEVICE_OBJECT *)(v7 + 128),
                            &InputBuffer,
                            0x18u,
                            0,
                            0,
                            0,
                            &Event,
                            &IoStatusBlock);
                    if ( v10 )
                    {
                      ExReleaseResourceLite(&Resource);
                      KeLeaveCriticalRegion();
                      v1 = 0;
                      Status = IofCallDriver(*(PDEVICE_OBJECT *)(v7 + 128), v10);
                      if ( Status == 259 )
                      {
                        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
                        Status = IoStatusBlock.Status;
                      }
                      if ( Status < 0 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                        {
                          WPP_SF_Dq(
                            WPP_GLOBAL_Control->AttachedDevice,
                            25,
                            WPP_a4016d7e857d3af68560d770380f4c36_Traceguids,
                            (unsigned int)Status,
                            v7);
                        }
                        if ( (*(_DWORD *)(v7 + 60) & 0x10) != 0 && (v16 & 0x10) != 0 )
                          DepFSBugCheckNotEnoughSpace(Status);
                      }
                    }
                    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      WPP_SF_q(
                        WPP_GLOBAL_Control->AttachedDevice,
                        24,
                        WPP_a4016d7e857d3af68560d770380f4c36_Traceguids,
                        v7);
                    }
                    v4 = P;
                  }
                }
              }
            }
            ++v5;
          }
          while ( v5 < v4[1] );
          if ( !v1 )
          {
            v1 = 1;
            KeEnterCriticalRegion();
            ExAcquireResourceExclusiveLite(&Resource, 1u);
            v4 = P;
          }
        }
        for ( i = 0; i < v4[1]; ++i )
        {
          v13 = &v4[4 * i];
          if ( (v13[2] & 1) != 0 && *((_QWORD *)v13 + 2) )
          {
            DereferenceVolumeContext(*((_QWORD *)v13 + 2));
            v4 = P;
          }
          if ( (v13[2] & 2) != 0 && *((_QWORD *)v13 + 2) )
          {
            DereferenceDependencyContext(*((PVOID *)v13 + 2));
            v4 = P;
          }
        }
        ExFreePoolWithTag(v4, 0x6C447044u);
      }
    }
  }
  LOBYTE(v2) = v1;
  FsDepRegisterUnregisterForBugchecks(0, v2);
  if ( v1 )
  {
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x180008010  mov     [rsp-8+arg_0], rbx
0x180008015  mov     [rsp-8+arg_18], rsi
0x18000801a  push    rbp
0x18000801b  push    rdi
0x18000801c  push    r14
0x18000801e  lea     rbp, [rsp-47h]
0x180008023  sub     rsp, 90h
0x18000802a  xorps   xmm0, xmm0
0x18000802d  mov     [rbp+57h+P], 0
0x180008035  xor     bl, bl
0x180008037  xorps   xmm1, xmm1
0x18000803a  xor     eax, eax
0x18000803c  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x180008040  mov     [rbp+57h+var_30], rax
0x180008044  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180008048  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x18000804c  movups  [rbp+57h+InputBuffer], xmm0
0x180008050  jmp     short loc_18000806E
0x180008052  lea     r8, [rbp+57h+Interval]; Interval
0x180008056  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFF676980h
0x18000805e  xor     edx, edx; Alertable
0x180008060  xor     ecx, ecx; WaitMode
0x180008062  call    cs:__imp_KeDelayExecutionThread
0x180008069  nop     dword ptr [rax+rax+00h]
0x18000806e  call    cs:__imp_FsRtlAreVolumeStartupApplicationsComplete
0x180008075  nop     dword ptr [rax+rax+00h]
0x18000807a  test    al, al
0x18000807c  jz      short loc_180008052
0x18000807e  cmp     cs:byte_180005194, bl
0x180008084  jnz     loc_1800083F9
0x18000808a  cmp     cs:byte_180005196, bl
0x180008090  jnz     loc_1800083F9
0x180008096  call    cs:__imp_KeEnterCriticalRegion
0x18000809d  nop     dword ptr [rax+rax+00h]
0x1800080a2  mov     dl, 1; Wait
0x1800080a4  lea     rcx, Resource; Resource
0x1800080ab  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800080b2  nop     dword ptr [rax+rax+00h]
0x1800080b7  cmp     cs:byte_180005194, 0
0x1800080be  mov     bl, 1
0x1800080c0  jnz     loc_1800083F9
0x1800080c6  cmp     cs:byte_180005196, 0
0x1800080cd  jnz     loc_1800083F9
0x1800080d3  cmp     cs:dword_1800051C4, 4
0x1800080da  jz      loc_1800083F9
0x1800080e0  mov     [rsp+0A0h+OutputBufferLength], 8000h
0x1800080e8  lea     r9, [rbp+57h+P]
0x1800080ec  xor     r8d, r8d
0x1800080ef  mov     byte ptr [rsp+0A0h+OutputBuffer], bl
0x1800080f3  xor     edx, edx
0x1800080f5  xor     ecx, ecx
0x1800080f7  call    DepFSGenerateDependencyList
0x1800080fc  lea     rcx, WPP_GLOBAL_Control
0x180008103  test    eax, eax
0x180008105  jns     short loc_18000813A
0x180008107  mov     r10, cs:WPP_GLOBAL_Control
0x18000810e  cmp     r10, rcx
0x180008111  jz      short loc_18000813A
0x180008113  mov     ecx, [r10+2Ch]
0x180008117  test    bl, cl
0x180008119  jz      short loc_18000813A
0x18000811b  cmp     byte ptr [r10+29h], 2
0x180008120  jb      short loc_18000813A
0x180008122  mov     rcx, [r10+18h]
0x180008126  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x18000812d  mov     edx, 17h
0x180008132  mov     r9d, eax
0x180008135  call    WPP_SF_D
0x18000813a  mov     rcx, [rbp+57h+P]
0x18000813e  test    rcx, rcx
0x180008141  jz      loc_1800083F9
0x180008147  xor     r14d, r14d
0x18000814a  cmp     [rcx+4], r14d
0x18000814e  jbe     loc_180008396
0x180008154  mov     edi, r14d
0x180008157  shl     rdi, 4
0x18000815b  add     rdi, rcx
0x18000815e  test    bl, bl
0x180008160  jnz     short loc_180008189
0x180008162  mov     bl, 1
0x180008164  call    cs:__imp_KeEnterCriticalRegion
0x18000816b  nop     dword ptr [rax+rax+00h]
0x180008170  mov     dl, bl; Wait
0x180008172  lea     rcx, Resource; Resource
0x180008179  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180008180  nop     dword ptr [rax+rax+00h]
0x180008185  mov     rcx, [rbp+57h+P]
0x180008189  test    byte ptr [rdi+8], 2
0x18000818d  jz      loc_18000835E
0x180008193  mov     rdi, [rdi+10h]
0x180008197  lea     rax, [rdi+28h]
0x18000819b  cmp     [rax], rax
0x18000819e  jz      loc_18000835E
0x1800081a4  mov     edx, [rdi+3Ch]
0x1800081a7  test    dl, 4
0x1800081aa  jnz     loc_18000835E
0x1800081b0  mov     eax, [rdi+5Ch]
0x1800081b3  test    eax, 403h
0x1800081b8  jnz     loc_18000835E
0x1800081be  test    dl, 2
0x1800081c1  jz      short loc_1800081D3
0x1800081c3  bts     eax, 9
0x1800081c7  mov     [rdi+5Ch], eax
0x1800081ca  mov     dword ptr [rbp+57h+var_30], 2
0x1800081d1  jmp     short loc_1800081E2
0x1800081d3  or      eax, 600h
0x1800081d8  mov     [rdi+5Ch], eax
0x1800081db  mov     dword ptr [rbp+57h+var_30], 12h
0x1800081e2  mov     rax, [rdi+68h]
0x1800081e6  lea     rcx, [rbp+57h+Event]; Event
0x1800081ea  mov     qword ptr [rbp+57h+InputBuffer], rax
0x1800081ee  xor     r8d, r8d; State
0x1800081f1  mov     rax, [rdi+78h]
0x1800081f5  xor     edx, edx; Type
0x1800081f7  mov     qword ptr [rbp+57h+InputBuffer+8], rax
0x1800081fb  call    cs:__imp_KeInitializeEvent
0x180008202  nop     dword ptr [rax+rax+00h]
0x180008207  mov     rdx, [rdi+80h]; DeviceObject
0x18000820e  lea     rax, [rbp+57h+var_50]
0x180008212  mov     [rsp+0A0h+IoStatusBlock], rax; IoStatusBlock
0x180008217  lea     r8, [rbp+57h+InputBuffer]; InputBuffer
0x18000821b  lea     rax, [rbp+57h+Event]
0x18000821f  mov     r9d, 18h; InputBufferLength
0x180008225  mov     [rsp+0A0h+var_68], rax; Event
0x18000822a  mov     ecx, 2D9198h; IoControlCode
0x18000822f  mov     [rsp+0A0h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x180008234  mov     [rsp+0A0h+OutputBufferLength], 0; OutputBufferLength
0x18000823c  mov     [rsp+0A0h+OutputBuffer], 0; OutputBuffer
0x180008245  call    cs:__imp_IoBuildDeviceIoControlRequest
0x18000824c  nop     dword ptr [rax+rax+00h]
0x180008251  mov     rsi, rax
0x180008254  test    rax, rax
0x180008257  jnz     short loc_1800082A0
0x180008259  mov     rcx, cs:WPP_GLOBAL_Control
0x180008260  lea     rax, WPP_GLOBAL_Control
0x180008267  cmp     rcx, rax
0x18000826a  jz      loc_18000835A
0x180008270  mov     eax, [rcx+2Ch]
0x180008273  test    al, 1
0x180008275  jz      loc_18000835A
0x18000827b  cmp     byte ptr [rcx+29h], 2
0x18000827f  jb      loc_18000835A
0x180008285  mov     rcx, [rcx+18h]
0x180008289  lea     edx, [rsi+18h]
0x18000828c  mov     r9, rdi
0x18000828f  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x180008296  call    WPP_SF_q
0x18000829b  jmp     loc_18000835A
0x1800082a0  test    bl, bl
0x1800082a2  jz      short loc_1800082C5
0x1800082a4  lea     rcx, Resource; Resource
0x1800082ab  call    cs:__imp_ExReleaseResourceLite
0x1800082b2  nop     dword ptr [rax+rax+00h]
0x1800082b7  call    cs:__imp_KeLeaveCriticalRegion
0x1800082be  nop     dword ptr [rax+rax+00h]
0x1800082c3  xor     bl, bl
0x1800082c5  mov     rcx, [rdi+80h]; DeviceObject
0x1800082cc  mov     rdx, rsi; Irp
0x1800082cf  call    cs:__imp_IofCallDriver
0x1800082d6  nop     dword ptr [rax+rax+00h]
0x1800082db  mov     esi, eax
0x1800082dd  cmp     eax, 103h
0x1800082e2  jnz     short loc_180008308
0x1800082e4  xor     r9d, r9d; Alertable
0x1800082e7  mov     [rsp+0A0h+OutputBuffer], 0; Timeout
0x1800082f0  xor     r8d, r8d; WaitMode
0x1800082f3  lea     rcx, [rbp+57h+Event]; Object
0x1800082f7  xor     edx, edx; WaitReason
0x1800082f9  call    cs:__imp_KeWaitForSingleObject
0x180008300  nop     dword ptr [rax+rax+00h]
0x180008305  mov     esi, dword ptr [rbp+57h+var_50]
0x180008308  test    esi, esi
0x18000830a  jns     short loc_18000835A
0x18000830c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008313  lea     rax, WPP_GLOBAL_Control
0x18000831a  cmp     rcx, rax
0x18000831d  jz      short loc_180008349
0x18000831f  mov     eax, [rcx+2Ch]
0x180008322  test    al, 1
0x180008324  jz      short loc_180008349
0x180008326  cmp     byte ptr [rcx+29h], 2
0x18000832a  jb      short loc_180008349
0x18000832c  mov     rcx, [rcx+18h]
0x180008330  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x180008337  mov     edx, 19h
0x18000833c  mov     [rsp+0A0h+OutputBuffer], rdi
0x180008341  mov     r9d, esi
0x180008344  call    WPP_SF_Dq
0x180008349  mov     eax, [rdi+3Ch]
0x18000834c  test    al, 10h
0x18000834e  jz      short loc_18000835A
0x180008350  test    byte ptr [rbp+57h+var_30], 10h
0x180008354  jnz     loc_18000843E
0x18000835a  mov     rcx, [rbp+57h+P]
0x18000835e  inc     r14d
0x180008361  cmp     r14d, [rcx+4]
0x180008365  jb      loc_180008154
0x18000836b  test    bl, bl
0x18000836d  jnz     short loc_180008396
0x18000836f  mov     bl, 1
0x180008371  call    cs:__imp_KeEnterCriticalRegion
0x180008378  nop     dword ptr [rax+rax+00h]
0x18000837d  mov     dl, bl; Wait
0x18000837f  lea     rcx, Resource; Resource
0x180008386  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000838d  nop     dword ptr [rax+rax+00h]
0x180008392  mov     rcx, [rbp+57h+P]
0x180008396  xor     edi, edi
0x180008398  cmp     [rcx+4], edi
0x18000839b  jbe     short loc_1800083E8
0x18000839d  mov     esi, edi
0x18000839f  shl     rsi, 4
0x1800083a3  add     rsi, rcx
0x1800083a6  test    byte ptr [rsi+8], 1
0x1800083aa  jz      short loc_1800083C1
0x1800083ac  mov     rax, [rsi+10h]
0x1800083b0  test    rax, rax
0x1800083b3  jz      short loc_1800083C1
0x1800083b5  mov     rcx, rax
0x1800083b8  call    DereferenceVolumeContext
0x1800083bd  mov     rcx, [rbp+57h+P]
0x1800083c1  test    byte ptr [rsi+8], 2
0x1800083c5  jz      short loc_1800083E1
0x1800083c7  mov     rax, [rsi+10h]
0x1800083cb  test    rax, rax
0x1800083ce  jz      short loc_1800083E1
0x1800083d0  xor     r8d, r8d
0x1800083d3  mov     dl, bl
0x1800083d5  mov     rcx, rax; P
0x1800083d8  call    DereferenceDependencyContext
0x1800083dd  mov     rcx, [rbp+57h+P]; P
0x1800083e1  inc     edi
0x1800083e3  cmp     edi, [rcx+4]
0x1800083e6  jb      short loc_18000839D
0x1800083e8  mov     edx, 6C447044h; Tag
0x1800083ed  call    cs:__imp_ExFreePoolWithTag
0x1800083f4  nop     dword ptr [rax+rax+00h]
0x1800083f9  mov     dl, bl
0x1800083fb  xor     ecx, ecx
0x1800083fd  call    FsDepRegisterUnregisterForBugchecks
0x180008402  test    bl, bl
0x180008404  jz      short loc_180008425
0x180008406  lea     rcx, Resource; Resource
0x18000840d  call    cs:__imp_ExReleaseResourceLite
0x180008414  nop     dword ptr [rax+rax+00h]
0x180008419  call    cs:__imp_KeLeaveCriticalRegion
0x180008420  nop     dword ptr [rax+rax+00h]
0x180008425  lea     r11, [rsp+0A0h+var_10]
0x18000842d  mov     rbx, [r11+20h]
0x180008431  mov     rsi, [r11+38h]
0x180008435  mov     rsp, r11
0x180008438  pop     r14
0x18000843a  pop     rdi
0x18000843b  pop     rbp
0x18000843c  retn
0x18000843e  mov     ecx, esi
0x180008440  call    DepFSBugCheckNotEnoughSpace
```
