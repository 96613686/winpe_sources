# AFDETW_TRACECREATE

- ea: `0x140015430`
- end: `0x1400156d9`
- name: `AFDETW_TRACECREATE`
- size: `681`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140014ed0`
- `0x1400153d0`
- `0x1400218d4`

## callees

- `0x140013990`
- `0x1400147d0`
- `0x140015430`
- `0x1400726a0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x1400154d9`
- `ntoskrnl!EtwActivityIdControl` at `0x1400154d9`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140015550`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140015550`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400156a5`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400156a5`
- `ntoskrnl!EtwWrite` at `0x14001563f`
- `ntoskrnl!EtwWrite` at `0x14001563f`

## pseudocode

```c
int __fastcall AFDETW_TRACECREATE(__int64 a1, int a2, __int64 a3, int a4, int a5, char a6, int a7)
{
  int result; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  HANDLE CurrentProcessId; // rax
  _WORD *v11; // rcx
  PEPROCESS CurrentProcess; // rax
  UCHAR v13; // al
  __int64 v14; // rax
  int UserData; // [rsp+20h] [rbp-E0h]
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  PEPROCESS v17; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v18; // [rsp+50h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  GUID v20; // [rsp+68h] [rbp-98h] BYREF
  GUID ActivityId; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+90h] [rbp-70h] BYREF
  int *v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+A8h] [rbp-58h]
  PEPROCESS *v25; // [rsp+B0h] [rbp-50h]
  __int64 v26; // [rsp+B8h] [rbp-48h]
  __int64 *v27; // [rsp+C0h] [rbp-40h]
  __int64 v28; // [rsp+C8h] [rbp-38h]
  int *v29; // [rsp+D0h] [rbp-30h]
  __int64 v30; // [rsp+D8h] [rbp-28h]
  int *v31; // [rsp+E0h] [rbp-20h]
  __int64 v32; // [rsp+E8h] [rbp-18h]
  char *v33; // [rsp+F0h] [rbp-10h]
  __int64 v34; // [rsp+F8h] [rbp-8h]
  HANDLE *v35; // [rsp+100h] [rbp+0h]
  __int64 v36; // [rsp+108h] [rbp+8h]
  int *v37; // [rsp+110h] [rbp+10h]
  __int64 v38; // [rsp+118h] [rbp+18h]
  unsigned int v39; // [rsp+150h] [rbp+50h] BYREF
  int v40; // [rsp+158h] [rbp+58h] BYREF
  int v41; // [rsp+168h] [rbp+68h] BYREF

  v41 = a4;
  v40 = a2;
  v39 = a1;
  v16 = a3;
  v17 = 0;
  EventDescriptor = 0;
  v18 = 0;
  v20 = 0;
  ActivityId = 0;
  if ( !g_AfdEtwTraceEnable )
  {
    result = Microsoft_Windows_Networking_CorrelationEnabled;
    if ( !Microsoft_Windows_Networking_CorrelationEnabled )
      goto LABEL_3;
    a1 = v39;
    a3 = v16;
  }
  if ( a3 )
  {
    *(_QWORD *)v20.Data4 = 0;
    *(_QWORD *)&v20.Data1 = a3;
    if ( !(_DWORD)a1 && Microsoft_Windows_Networking_CorrelationEnabled )
    {
      UserData = 1;
      EtwEx_tidActivityInfo(a1, &ActivityStart, &v20);
    }
  }
  else
  {
    v20 = (GUID)AfdEndpointCreateGuid;
  }
  result = EtwActivityIdControl(1u, &ActivityId);
  if ( v16 )
  {
    if ( !v39 && result >= 0 )
    {
      result = Microsoft_Windows_Networking_CorrelationEnabled;
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
        result = EtwEx_tidActivityInfoTransfer(v9, v8, &v20, &ActivityId, UserData);
    }
  }
LABEL_3:
  if ( g_AfdEtwTraceEnable )
  {
    *(_DWORD *)&EventDescriptor.Id = AFD_EVENT_CREATE;
    *(_WORD *)&EventDescriptor.Opcode = -6134;
    HIBYTE(EventDescriptor.Task) = 3;
    EventDescriptor.Keyword = 0x8000000000000004uLL;
    EventDescriptor.Level = 4;
    CurrentProcessId = PsGetCurrentProcessId();
    v11 = (_WORD *)v16;
    v18 = CurrentProcessId;
    if ( v16 )
    {
      CurrentProcess = *(PEPROCESS *)(v16 + 48);
    }
    else
    {
      CurrentProcess = IoGetCurrentProcess();
      v11 = 0;
    }
    v17 = CurrentProcess;
    v22.Ptr = (ULONGLONG)&v39;
    v23 = &v40;
    v25 = &v17;
    v27 = &v16;
    v29 = &v41;
    v31 = &a5;
    v33 = &a6;
    v35 = &v18;
    v37 = &a7;
    v13 = 2;
    if ( a7 >= 0 )
      v13 = 4;
    *(_QWORD *)&v22.Size = 4;
    EventDescriptor.Level = v13;
    v24 = 4;
    v26 = 8;
    v28 = 8;
    v30 = 4;
    v32 = 4;
    v34 = 4;
    v36 = 8;
    v38 = 4;
    if ( v39 )
    {
      v14 = 0;
      if ( v11 )
      {
        LOBYTE(v14) = *v11 != 0xAFD1;
        ++v14;
      }
      EventDescriptor.Keyword |= v14;
    }
    else if ( a5 == 2 )
    {
      EventDescriptor.Keyword |= 1uLL;
    }
    else
    {
      EventDescriptor.Keyword |= 2uLL;
    }
    return EtwWrite(g_AfdEtwHandle, &EventDescriptor, &v20, 9u, &v22);
  }
  return result;
}

```

## disassembly

```asm
0x140015430  mov     [rsp-8+arg_18], r9d
0x140015435  mov     [rsp-8+arg_8], edx
0x140015439  mov     [rsp-8+arg_0], ecx
0x14001543d  push    rbp
0x14001543e  push    rbx
0x14001543f  lea     rbp, [rsp-38h]
0x140015444  sub     rsp, 138h
0x14001544b  mov     rax, cs:__security_cookie
0x140015452  xor     rax, rsp
0x140015455  mov     [rbp+40h+var_20], rax
0x140015459  xor     ebx, ebx
0x14001545b  mov     [rsp+140h+var_100], r8
0x140015460  cmp     cs:g_AfdEtwTraceEnable, ebx
0x140015466  xorps   xmm0, xmm0
0x140015469  xorps   xmm1, xmm1
0x14001546c  mov     [rsp+140h+var_F8], rbx
0x140015471  movups  xmmword ptr [rsp+140h+EventDescriptor.Id], xmm0
0x140015476  mov     [rsp+140h+var_F0], rbx
0x14001547b  movups  xmmword ptr [rsp+140h+var_D8.Data1], xmm0
0x140015480  movups  xmmword ptr [rsp+140h+ActivityId.Data1], xmm1
0x140015485  jnz     short loc_1400154B4
0x140015487  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14001548d  test    eax, eax
0x14001548f  jnz     loc_1400156BB
0x140015495  cmp     cs:g_AfdEtwTraceEnable, ebx
0x14001549b  jnz     short loc_14001551B
0x14001549d  mov     rcx, [rbp+40h+var_20]
0x1400154a1  xor     rcx, rsp; StackCookie
0x1400154a4  call    __security_check_cookie
0x1400154a9  add     rsp, 138h
0x1400154b0  pop     rbx
0x1400154b1  pop     rbp
0x1400154b2  retn
0x1400154b4  test    r8, r8
0x1400154b7  jz      loc_1400156C8
0x1400154bd  mov     qword ptr [rsp+140h+var_D8.Data4], rbx
0x1400154c2  mov     qword ptr [rsp+140h+var_D8.Data1], r8
0x1400154c7  test    ecx, ecx
0x1400154c9  jz      loc_140015650
0x1400154cf  lea     rdx, [rsp+140h+ActivityId]; ActivityId
0x1400154d4  mov     ecx, 1; ControlCode
0x1400154d9  call    cs:__imp_EtwActivityIdControl
0x1400154e0  nop     dword ptr [rax+rax+00h]
0x1400154e5  cmp     [rsp+140h+var_100], rbx
0x1400154ea  jz      short loc_140015495
0x1400154ec  cmp     [rbp+40h+arg_0], ebx
0x1400154ef  jnz     short loc_140015495
0x1400154f1  test    eax, eax
0x1400154f3  js      short loc_140015495
0x1400154f5  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400154fb  test    eax, eax
0x1400154fd  jz      short loc_140015495
0x1400154ff  lea     r9, [rsp+140h+ActivityId]
0x140015504  mov     [rsp+140h+var_110], 1
0x14001550c  lea     r8, [rsp+140h+var_D8]
0x140015511  call    EtwEx_tidActivityInfoTransfer
0x140015516  jmp     loc_140015495
0x14001551b  mov     eax, cs:AFD_EVENT_CREATE
0x140015521  mov     dword ptr [rsp+140h+EventDescriptor.Id], eax
0x140015525  movzx   eax, cs:word_14007DADD
0x14001552c  mov     word ptr [rsp+140h+EventDescriptor.Opcode], ax
0x140015531  movzx   eax, cs:byte_14007DADF
0x140015538  mov     byte ptr [rsp+140h+EventDescriptor.Task+1], al
0x14001553c  mov     rax, 8000000000000004h
0x140015546  mov     [rsp+140h+EventDescriptor.Keyword], rax
0x14001554b  mov     [rsp+140h+EventDescriptor.Level], 4
0x140015550  call    cs:__imp_PsGetCurrentProcessId
0x140015557  nop     dword ptr [rax+rax+00h]
0x14001555c  mov     rcx, [rsp+140h+var_100]
0x140015561  mov     [rsp+140h+var_F0], rax
0x140015566  test    rcx, rcx
0x140015569  jz      loc_1400156A5
0x14001556f  mov     rax, [rcx+30h]
0x140015573  cmp     [rbp+40h+arg_30], ebx
0x140015579  mov     edx, 4
0x14001557e  mov     [rsp+140h+var_F8], rax
0x140015583  lea     rax, [rbp+40h+arg_0]
0x140015587  mov     [rbp+40h+var_B0.Ptr], rax
0x14001558b  lea     rax, [rbp+40h+arg_8]
0x14001558f  mov     [rbp+40h+var_A0], rax
0x140015593  lea     rax, [rsp+140h+var_F8]
0x140015598  mov     [rbp+40h+var_90], rax
0x14001559c  lea     rax, [rsp+140h+var_100]
0x1400155a1  mov     [rbp+40h+var_80], rax
0x1400155a5  lea     rax, [rbp+40h+arg_18]
0x1400155a9  mov     [rbp+40h+var_70], rax
0x1400155ad  lea     rax, [rbp+40h+arg_20]
0x1400155b1  mov     [rbp+40h+var_60], rax
0x1400155b5  lea     rax, [rbp+40h+arg_28]
0x1400155b9  mov     [rbp+40h+var_50], rax
0x1400155bd  lea     rax, [rsp+140h+var_F0]
0x1400155c2  mov     [rbp+40h+var_40], rax
0x1400155c6  lea     rax, [rbp+40h+arg_30]
0x1400155cd  mov     [rbp+40h+var_30], rax
0x1400155d1  mov     eax, 2
0x1400155d6  cmovge  eax, edx
0x1400155d9  mov     qword ptr [rbp+40h+var_B0.Size], rdx
0x1400155dd  mov     [rsp+140h+EventDescriptor.Level], al
0x1400155e1  mov     [rbp+40h+var_98], rdx
0x1400155e5  mov     [rbp+40h+var_88], 8
0x1400155ed  mov     [rbp+40h+var_78], 8
0x1400155f5  mov     [rbp+40h+var_68], rdx
0x1400155f9  mov     [rbp+40h+var_58], rdx
0x1400155fd  mov     [rbp+40h+var_48], rdx
0x140015601  mov     [rbp+40h+var_38], 8
0x140015609  mov     [rbp+40h+var_28], rdx
0x14001560d  cmp     [rbp+40h+arg_0], ebx
0x140015610  jz      short loc_14001568C
0x140015612  mov     rax, rbx
0x140015615  test    rcx, rcx
0x140015618  jnz     short loc_14001567C
0x14001561a  or      [rsp+140h+EventDescriptor.Keyword], rax
0x14001561f  mov     rcx, cs:g_AfdEtwHandle; RegHandle
0x140015626  lea     rax, [rbp+40h+var_B0]
0x14001562a  mov     r9d, 9; UserDataCount
0x140015630  mov     qword ptr [rsp+140h+UserData], rax; UserData
0x140015635  lea     r8, [rsp+140h+var_D8]; ActivityId
0x14001563a  lea     rdx, [rsp+140h+EventDescriptor]; EventDescriptor
0x14001563f  call    cs:__imp_EtwWrite
0x140015646  nop     dword ptr [rax+rax+00h]
0x14001564b  jmp     loc_14001549D
0x140015650  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140015656  test    eax, eax
0x140015658  jz      loc_1400154CF
0x14001565e  lea     r8, [rsp+140h+var_D8]
0x140015663  mov     [rsp+140h+UserData], 1
0x14001566b  lea     rdx, ActivityStart
0x140015672  call    EtwEx_tidActivityInfo
0x140015677  jmp     loc_1400154CF
0x14001567c  mov     edx, 0AFD1h
0x140015681  cmp     [rcx], dx
0x140015684  setnz   al
0x140015687  inc     rax
0x14001568a  jmp     short loc_14001561A
0x14001568c  cmp     [rbp+40h+arg_20], 2
0x140015690  jnz     short loc_14001569A
0x140015692  or      [rsp+140h+EventDescriptor.Keyword], 1
0x140015698  jmp     short loc_14001561F
0x14001569a  or      [rsp+140h+EventDescriptor.Keyword], 2
0x1400156a0  jmp     loc_14001561F
0x1400156a5  call    cs:__imp_IoGetCurrentProcess
0x1400156ac  nop     dword ptr [rax+rax+00h]
0x1400156b1  mov     rcx, [rsp+140h+var_100]
0x1400156b6  jmp     loc_140015573
0x1400156bb  mov     ecx, [rbp+40h+arg_0]
0x1400156be  mov     r8, [rsp+140h+var_100]
0x1400156c3  jmp     loc_1400154B4
0x1400156c8  movups  xmm0, cs:AfdEndpointCreateGuid
0x1400156cf  movups  xmmword ptr [rsp+140h+var_D8.Data1], xmm0
0x1400156d4  jmp     loc_1400154CF
```
