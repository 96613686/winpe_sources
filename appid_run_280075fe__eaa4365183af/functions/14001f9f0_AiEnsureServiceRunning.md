# AiEnsureServiceRunning

- ea: `0x14001f9f0`
- end: `0x14001faee`
- name: `AiEnsureServiceRunning`
- size: `254`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001f900`
- `0x140021114`
- `0x14002bff0`
- `0x1400373b0`

## callees

- `0x14001f9f0`
- `0x14002522c`

## import_xrefs

- `ntoskrnl!ZwOpenEvent` at `0x14001fa61`
- `ntoskrnl!ZwOpenEvent` at `0x14001fa61`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14001fa80`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14001faa6`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14001fa80`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14001faa6`
- `ntoskrnl!ZwSetEvent` at `0x14001fac4`
- `ntoskrnl!ZwSetEvent` at `0x14001fac4`
- `ntoskrnl!ZwClose` at `0x14001fad9`
- `ntoskrnl!ZwClose` at `0x14001fad9`

## pseudocode

```c
int __fastcall AiEnsureServiceRunning(char a1)
{
  const wchar_t *v1; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  union _LARGE_INTEGER v7; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v8[2]; // [rsp+28h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF
  LONG PreviousState; // [rsp+98h] [rbp+28h] BYREF
  void *EventHandle; // [rsp+A0h] [rbp+30h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+A8h] [rbp+38h] BYREF

  v7.QuadPart = -10000000;
  v1 = L"\\BaseNamedObjects\\SC_AutoStartPhase1Done";
  Timeout.QuadPart = 0;
  EventHandle = 0;
  v8[0] = 5374032;
  v8[1] = L"\\BaseNamedObjects\\SC_AutoStartPhase1Done";
  if ( !WPP_MAIN_CB.Dpc.SystemArgument2 )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v8;
    *(_QWORD *)&ObjectAttributes.Attributes = 512;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    LODWORD(v1) = ZwOpenEvent(&EventHandle, 1u, &ObjectAttributes);
    if ( (int)v1 >= 0 )
    {
      if ( !EventHandle )
        return (int)v1;
      LODWORD(v1) = ZwWaitForSingleObject(EventHandle, 1u, &Timeout);
      if ( !(_DWORD)v1 )
      {
        LODWORD(v1) = AiLogTriggerServiceStartEvent(v4, v3, v5);
        if ( a1 )
        {
          LODWORD(v1) = ZwWaitForSingleObject(Handle, 1u, &v7);
          if ( (int)v1 < 0 )
          {
            PreviousState = 0;
            LODWORD(v1) = ZwSetEvent(Handle, &PreviousState);
          }
        }
      }
    }
    if ( EventHandle )
      LODWORD(v1) = ZwClose(EventHandle);
  }
  return (int)v1;
}

```

## disassembly

```asm
0x14001f9f0  push    rbp
0x14001f9f2  push    rbx
0x14001f9f3  push    rdi
0x14001f9f4  mov     rbp, rsp
0x14001f9f7  sub     rsp, 70h
0x14001f9fb  xor     edi, edi
0x14001f9fd  mov     qword ptr [rbp+var_50], 0FFFFFFFFFF676980h
0x14001fa05  cmp     cs:WPP_MAIN_CB.Dpc.SystemArgument2, rdi
0x14001fa0c  lea     rax, aBasenamedobjec; "\\BaseNamedObjects\\SC_AutoStartPhase1D"...
0x14001fa13  movzx   ebx, cl
0x14001fa16  mov     qword ptr [rbp+Timeout], rdi
0x14001fa1a  mov     [rbp+EventHandle], rdi
0x14001fa1e  mov     [rbp+var_48], 520050h
0x14001fa26  mov     [rbp+var_40], rax
0x14001fa2a  jnz     loc_14001FAE5
0x14001fa30  lea     rax, [rbp+var_48]
0x14001fa34  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001fa3c  xorps   xmm0, xmm0
0x14001fa3f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001fa43  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001fa47  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x14001fa4f  mov     edx, 1; DesiredAccess
0x14001fa54  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x14001fa58  lea     rcx, [rbp+EventHandle]; EventHandle
0x14001fa5c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001fa61  call    cs:__imp_ZwOpenEvent
0x14001fa68  nop     dword ptr [rax+rax+00h]
0x14001fa6d  test    eax, eax
0x14001fa6f  js      short loc_14001FAD0
0x14001fa71  mov     rcx, [rbp+EventHandle]; Handle
0x14001fa75  test    rcx, rcx
0x14001fa78  jz      short loc_14001FAE5
0x14001fa7a  lea     r8, [rbp+Timeout]; Timeout
0x14001fa7e  mov     dl, 1; Alertable
0x14001fa80  call    cs:__imp_ZwWaitForSingleObject
0x14001fa87  nop     dword ptr [rax+rax+00h]
0x14001fa8c  test    eax, eax
0x14001fa8e  jnz     short loc_14001FAD0
0x14001fa90  call    AiLogTriggerServiceStartEvent
0x14001fa95  test    bl, bl
0x14001fa97  jz      short loc_14001FAD0
0x14001fa99  mov     rcx, cs:Handle; Handle
0x14001faa0  lea     r8, [rbp+var_50]; Timeout
0x14001faa4  mov     dl, 1; Alertable
0x14001faa6  call    cs:__imp_ZwWaitForSingleObject
0x14001faad  nop     dword ptr [rax+rax+00h]
0x14001fab2  test    eax, eax
0x14001fab4  jns     short loc_14001FAD0
0x14001fab6  mov     rcx, cs:Handle; EventHandle
0x14001fabd  lea     rdx, [rbp+PreviousState]; PreviousState
0x14001fac1  mov     [rbp+PreviousState], edi
0x14001fac4  call    cs:__imp_ZwSetEvent
0x14001facb  nop     dword ptr [rax+rax+00h]
0x14001fad0  mov     rcx, [rbp+EventHandle]; Handle
0x14001fad4  test    rcx, rcx
0x14001fad7  jz      short loc_14001FAE5
0x14001fad9  call    cs:__imp_ZwClose
0x14001fae0  nop     dword ptr [rax+rax+00h]
0x14001fae5  add     rsp, 70h
0x14001fae9  pop     rdi
0x14001faea  pop     rbx
0x14001faeb  pop     rbp
0x14001faec  retn
```
