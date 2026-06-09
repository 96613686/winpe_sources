# ScoThread_StartThread(_SCO_THREAD *)

- ea: `0x140143c30`
- end: `0x140143e8b`
- name: `?ScoThread_StartThread@@YAJPEAU_SCO_THREAD@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(struct _SCO_THREAD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1401439b0`

## callees

- `0x140005608`
- `0x140005b4c`
- `0x140005c04`
- `0x140143c30`
- `0x140143e94`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x140143cfd`
- `ntoskrnl!PsCreateSystemThread` at `0x140143cfd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140143d7b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140143d7b`
- `ntoskrnl!ZwClose` at `0x140143d95`
- `ntoskrnl!ZwClose` at `0x140143d95`
- `ntoskrnl!KeClearEvent` at `0x140143cbd`
- `ntoskrnl!KeClearEvent` at `0x140143cbd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140143db2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140143db2`

## pseudocode

```c
__int64 __fastcall ScoThread_StartThread(struct _SCO_THREAD *a1)
{
  char v2; // bl
  char v3; // dl
  __int16 DeviceType; // ax
  __int64 i; // rdi
  int v6; // edx
  NTSTATUS v7; // edi
  int v8; // r8d
  int v9; // edx
  int v10; // r8d
  void *v11; // rcx
  __int16 v12; // ax
  void *ThreadHandle; // [rsp+70h] [rbp+8h] BYREF
  PVOID Object; // [rsp+78h] [rbp+10h] BYREF

  ThreadHandle = 0;
  v2 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (v3 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v3 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v3 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      DeviceType != 0,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      4,
      14,
      (__int64)WPP_156ad3417adc34dfbe002b9340b9b992_Traceguids,
      a1);
  for ( i = 0; i != 3; ++i )
    KeClearEvent((PRKEVENT)((char *)a1->ThreadEvents + 16 * i + 8 * i));
  a1->ThreadInitialized = 0;
  a1->ThreadSelfPointer = 0;
  v7 = PsCreateSystemThread(&ThreadHandle, 0, 0, 0, 0, (PKSTART_ROUTINE)ScoThread_ThreadFunction, a1);
  if ( v7 >= 0 )
  {
    Object = 0;
    ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
    v11 = ThreadHandle;
    a1->ThreadSelfPointer = (_ETHREAD *)Object;
    ZwClose(v11);
    KeWaitForSingleObject(&a1->SynchThreadEvent, Executive, 0, 0, 0);
    if ( a1->ThreadInitialized )
    {
      v7 = 0;
    }
    else
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v9) = 0;
      LOBYTE(v10) = 1;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        4,
        16,
        (__int64)WPP_156ad3417adc34dfbe002b9340b9b992_Traceguids);
      ScoThread_StopThread(a1);
      v7 = -1073741670;
    }
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v6) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v6) = 0;
    LOBYTE(v8) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v8,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      15,
      (__int64)WPP_156ad3417adc34dfbe002b9340b9b992_Traceguids);
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v2 = 0;
  v12 = WPP_GLOBAL_Control->DeviceType;
  if ( v2 || v12 )
  {
    LOBYTE(v9) = v2;
    LOBYTE(v10) = v12 != 0;
    WPP_RECORDER_AND_TRACE_SF_qL(
      WPP_GLOBAL_Control->AttachedDevice,
      v9,
      v10,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      4,
      17,
      (__int64)WPP_156ad3417adc34dfbe002b9340b9b992_Traceguids,
      (char)a1,
      v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140143c30  mov     [rsp+arg_10], rbx
0x140143c35  mov     [rsp+arg_18], rbp
0x140143c3a  push    rsi
0x140143c3b  push    rdi
0x140143c3c  push    r12
0x140143c3e  sub     rsp, 50h
0x140143c42  xor     ebp, ebp
0x140143c44  mov     rsi, rcx
0x140143c47  mov     [rsp+68h+ThreadHandle], rbp
0x140143c4c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140143c53  lea     ebx, [rbp+1]
0x140143c56  mov     eax, [rcx+2Ch]
0x140143c59  test    al, 8
0x140143c5b  jz      short loc_140143C65
0x140143c5d  cmp     byte ptr [rcx+29h], 5
0x140143c61  mov     dl, bl
0x140143c63  jnb     short loc_140143C68
0x140143c65  mov     dl, bpl
0x140143c68  movzx   eax, word ptr [rcx+48h]
0x140143c6c  lea     r12, WPP_156ad3417adc34dfbe002b9340b9b992_Traceguids
0x140143c73  test    ax, ax
0x140143c76  setnz   r8b
0x140143c7a  test    dl, dl
0x140143c7c  jnz     short loc_140143C83
0x140143c7e  test    ax, ax
0x140143c81  jz      short loc_140143CAE
0x140143c83  mov     r9, [rcx+40h]
0x140143c87  mov     rcx, [rcx+18h]
0x140143c8b  mov     [rsp+68h+var_28], rsi
0x140143c90  mov     [rsp+68h+var_30], r12
0x140143c95  mov     word ptr [rsp+68h+StartContext], 0Eh
0x140143c9c  mov     dword ptr [rsp+68h+StartRoutine], 4
0x140143ca4  mov     byte ptr [rsp+68h+ClientId], 5
0x140143ca9  call    WPP_RECORDER_AND_TRACE_SF_q
0x140143cae  mov     rdi, rbp
0x140143cb1  lea     rax, [rdi+5]
0x140143cb5  lea     rax, [rdi+rax*2]
0x140143cb9  lea     rcx, [rsi+rax*8]; Event
0x140143cbd  call    cs:__imp_KeClearEvent
0x140143cc4  nop     dword ptr [rax+rax+00h]
0x140143cc9  add     rdi, rbx
0x140143ccc  cmp     rdi, 3
0x140143cd0  jnz     short loc_140143CB1
0x140143cd2  lea     rax, ?ScoThread_ThreadFunction@@YAXPEAX@Z; ScoThread_ThreadFunction(void *)
0x140143cd9  mov     [rsp+68h+StartContext], rsi; StartContext
0x140143cde  mov     [rsp+68h+StartRoutine], rax; StartRoutine
0x140143ce3  lea     rcx, [rsp+68h+ThreadHandle]; ThreadHandle
0x140143ce8  xor     r9d, r9d; ProcessHandle
0x140143ceb  mov     [rsp+68h+ClientId], rbp; ClientId
0x140143cf0  xor     r8d, r8d; ObjectAttributes
0x140143cf3  mov     [rsi+30h], bpl
0x140143cf7  xor     edx, edx; DesiredAccess
0x140143cf9  mov     [rsi+28h], rbp
0x140143cfd  call    cs:__imp_PsCreateSystemThread
0x140143d04  nop     dword ptr [rax+rax+00h]
0x140143d09  mov     edi, eax
0x140143d0b  test    eax, eax
0x140143d0d  jns     short loc_140143D57
0x140143d0f  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140143d16  mov     ecx, [rax+2Ch]
0x140143d19  test    cl, 8
0x140143d1c  jz      short loc_140143D26
0x140143d1e  cmp     byte ptr [rax+29h], 2
0x140143d22  mov     dl, bl
0x140143d24  jnb     short loc_140143D29
0x140143d26  mov     dl, bpl
0x140143d29  mov     r9, [rax+40h]
0x140143d2d  mov     r8b, bl
0x140143d30  mov     rcx, [rax+18h]
0x140143d34  mov     [rsp+68h+var_30], r12
0x140143d39  mov     word ptr [rsp+68h+StartContext], 0Fh
0x140143d40  mov     dword ptr [rsp+68h+StartRoutine], 4
0x140143d48  mov     byte ptr [rsp+68h+ClientId], 2
0x140143d4d  call    WPP_RECORDER_AND_TRACE_SF_
0x140143d52  jmp     loc_140143E17
0x140143d57  mov     rcx, [rsp+68h+ThreadHandle]; Handle
0x140143d5c  lea     rax, [rsp+68h+Object]
0x140143d61  mov     [rsp+68h+StartRoutine], rbp; HandleInformation
0x140143d66  xor     r9d, r9d; AccessMode
0x140143d69  xor     r8d, r8d; ObjectType
0x140143d6c  mov     [rsp+68h+ClientId], rax; Object
0x140143d71  mov     edx, 1FFFFFh; DesiredAccess
0x140143d76  mov     [rsp+68h+Object], rbp
0x140143d7b  call    cs:__imp_ObReferenceObjectByHandle
0x140143d82  nop     dword ptr [rax+rax+00h]
0x140143d87  mov     rax, [rsp+68h+Object]
0x140143d8c  mov     rcx, [rsp+68h+ThreadHandle]; Handle
0x140143d91  mov     [rsi+28h], rax
0x140143d95  call    cs:__imp_ZwClose
0x140143d9c  nop     dword ptr [rax+rax+00h]
0x140143da1  lea     rcx, [rsi+38h]; Object
0x140143da5  mov     [rsp+68h+ClientId], rbp; Timeout
0x140143daa  xor     r9d, r9d; Alertable
0x140143dad  xor     r8d, r8d; WaitMode
0x140143db0  xor     edx, edx; WaitReason
0x140143db2  call    cs:__imp_KeWaitForSingleObject
0x140143db9  nop     dword ptr [rax+rax+00h]
0x140143dbe  cmp     [rsi+30h], bpl
0x140143dc2  jnz     short loc_140143E15
0x140143dc4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140143dcb  mov     eax, [rcx+2Ch]
0x140143dce  test    al, 8
0x140143dd0  jz      short loc_140143DDA
0x140143dd2  cmp     byte ptr [rcx+29h], 2
0x140143dd6  mov     dl, bl
0x140143dd8  jnb     short loc_140143DDD
0x140143dda  mov     dl, bpl
0x140143ddd  mov     r9, [rcx+40h]
0x140143de1  mov     r8b, bl
0x140143de4  mov     rcx, [rcx+18h]
0x140143de8  mov     [rsp+68h+var_30], r12
0x140143ded  mov     word ptr [rsp+68h+StartContext], 10h
0x140143df4  mov     dword ptr [rsp+68h+StartRoutine], 4
0x140143dfc  mov     byte ptr [rsp+68h+ClientId], 2
0x140143e01  call    WPP_RECORDER_AND_TRACE_SF_
0x140143e06  mov     rcx, rsi; struct _SCO_THREAD *
0x140143e09  call    ?ScoThread_StopThread@@YAXPEAU_SCO_THREAD@@@Z; ScoThread_StopThread(_SCO_THREAD *)
0x140143e0e  mov     edi, 0C000009Ah
0x140143e13  jmp     short loc_140143E17
0x140143e15  mov     edi, ebp
0x140143e17  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140143e1e  mov     eax, [rcx+2Ch]
0x140143e21  test    al, 8
0x140143e23  jz      short loc_140143E2B
0x140143e25  cmp     byte ptr [rcx+29h], 5
0x140143e29  jnb     short loc_140143E2E
0x140143e2b  mov     bl, bpl
0x140143e2e  movzx   eax, word ptr [rcx+48h]
0x140143e32  test    ax, ax
0x140143e35  setnz   r8b
0x140143e39  test    bl, bl
0x140143e3b  jnz     short loc_140143E42
0x140143e3d  test    ax, ax
0x140143e40  jz      short loc_140143E73
0x140143e42  mov     r9, [rcx+40h]
0x140143e46  mov     dl, bl
0x140143e48  mov     rcx, [rcx+18h]
0x140143e4c  mov     [rsp+68h+var_20], edi
0x140143e50  mov     [rsp+68h+var_28], rsi
0x140143e55  mov     [rsp+68h+var_30], r12
0x140143e5a  mov     word ptr [rsp+68h+StartContext], 11h
0x140143e61  mov     dword ptr [rsp+68h+StartRoutine], 4
0x140143e69  mov     byte ptr [rsp+68h+ClientId], 5
0x140143e6e  call    WPP_RECORDER_AND_TRACE_SF_qL
0x140143e73  lea     r11, [rsp+68h+var_18]
0x140143e78  mov     eax, edi
0x140143e7a  mov     rbx, [r11+30h]
0x140143e7e  mov     rbp, [r11+38h]
0x140143e82  mov     rsp, r11
0x140143e85  pop     r12
0x140143e87  pop     rdi
0x140143e88  pop     rsi
0x140143e89  retn
```
