# WctGetWaitThreadOrProcInfo(void *,_WCT_OBJECT_TYPE,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x18005e9f4`
- end: `0x18005eaf2`
- name: `?WctGetWaitThreadOrProcInfo@@YAKPEAXW4_WCT_OBJECT_TYPE@@PEAU_WAITCHAIN_NODE_INFO@@PEAK3@Z`
- size: `254`
- prototype: `unsigned int __usercall@<eax>(HANDLE Process@<rcx>, enum _WCT_OBJECT_TYPE@<edx>, struct _WAITCHAIN_NODE_INFO *@<r8>, unsigned int *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18005d450`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x18005e9f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005ead6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005ead6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eaea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eaea`
- `ntdll!RtlNtStatusToDosError` at `0x18005ea72`
- `ntdll!RtlNtStatusToDosError` at `0x18005ea72`
- `ntdll!NtQueryInformationThread` at `0x18005ea66`
- `ntdll!NtQueryInformationThread` at `0x18005ea66`

## pseudocode

```c
__int64 __fastcall WctGetWaitThreadOrProcInfo(
        HANDLE Process,
        WCT_OBJECT_TYPE a2,
        struct _WAITCHAIN_NODE_INFO *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  DWORD v9; // ebx
  int v10; // eax
  DWORD LastError; // eax
  DWORD ProcessId; // eax
  __int128 ThreadInformation; // [rsp+30h] [rbp-68h] BYREF
  __int128 v15; // [rsp+40h] [rbp-58h]
  __int128 v16; // [rsp+50h] [rbp-48h]

  ThreadInformation = 0;
  v15 = 0;
  v16 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  v9 = 0;
  if ( a2 != WctThreadWaitType )
  {
    *a4 = 0;
    ProcessId = GetProcessId(Process);
    *a5 = ProcessId;
    if ( !ProcessId )
    {
      LastError = GetLastError();
      goto LABEL_7;
    }
LABEL_9:
    a3->ObjectType = a2;
    a3->ObjectStatus = WctStatusOwned;
    goto LABEL_10;
  }
  v10 = NtQueryInformationThread(Process, ThreadBasicInformation, &ThreadInformation, 0x30u, 0);
  if ( v10 >= 0 )
  {
    *a4 = DWORD2(v15);
    *a5 = v15;
    goto LABEL_9;
  }
  LastError = RtlNtStatusToDosError(v10);
LABEL_7:
  v9 = LastError;
LABEL_10:
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18005e9f4  push    rbx
0x18005e9f6  push    rbp
0x18005e9f7  push    rsi
0x18005e9f8  push    rdi
0x18005e9f9  push    r14
0x18005e9fb  push    r15
0x18005e9fd  sub     rsp, 68h
0x18005ea01  xorps   xmm0, xmm0
0x18005ea04  mov     r14, r9
0x18005ea07  movups  [rsp+98h+ThreadInformation], xmm0
0x18005ea0c  mov     rsi, r8
0x18005ea0f  mov     edi, edx
0x18005ea11  movups  [rsp+98h+var_58], xmm0
0x18005ea16  mov     rbp, rcx
0x18005ea19  movups  [rsp+98h+var_48], xmm0
0x18005ea1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ea25  lea     r15, WPP_GLOBAL_Control
0x18005ea2c  cmp     rcx, r15
0x18005ea2f  jz      short loc_18005EA4C
0x18005ea31  test    byte ptr [rcx+1Ch], 4
0x18005ea35  jz      short loc_18005EA4C
0x18005ea37  mov     rcx, [rcx+10h]
0x18005ea3b  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005ea42  mov     edx, 20h ; ' '
0x18005ea47  call    WPP_SF_
0x18005ea4c  xor     ebx, ebx
0x18005ea4e  mov     rcx, rbp; Process
0x18005ea51  cmp     edi, 6
0x18005ea54  jnz     short loc_18005EAD3
0x18005ea56  lea     r9d, [rbx+30h]; ThreadInformationLength
0x18005ea5a  mov     [rsp+98h+ReturnLength], rbx; ReturnLength
0x18005ea5f  lea     r8, [rsp+98h+ThreadInformation]; ThreadInformation
0x18005ea64  xor     edx, edx; ThreadInformationClass
0x18005ea66  call    cs:__imp_NtQueryInformationThread
0x18005ea6c  test    eax, eax
0x18005ea6e  jns     short loc_18005EA7C
0x18005ea70  mov     ecx, eax; Status
0x18005ea72  call    cs:__imp_RtlNtStatusToDosError
0x18005ea78  mov     ebx, eax
0x18005ea7a  jmp     short loc_18005EA9A
0x18005ea7c  mov     eax, dword ptr [rsp+98h+var_58+8]
0x18005ea80  mov     rcx, [rsp+98h+arg_20]
0x18005ea88  mov     [r14], eax
0x18005ea8b  mov     eax, dword ptr [rsp+98h+var_58]
0x18005ea8f  mov     [rcx], eax
0x18005ea91  mov     [rsi], edi
0x18005ea93  mov     dword ptr [rsi+4], 6
0x18005ea9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eaa1  cmp     rcx, r15
0x18005eaa4  jz      short loc_18005EAC4
0x18005eaa6  test    byte ptr [rcx+1Ch], 4
0x18005eaaa  jz      short loc_18005EAC4
0x18005eaac  mov     rcx, [rcx+10h]
0x18005eab0  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005eab7  mov     edx, 21h ; '!'
0x18005eabc  mov     r9d, ebx
0x18005eabf  call    WPP_SF_d
0x18005eac4  mov     eax, ebx
0x18005eac6  add     rsp, 68h
0x18005eaca  pop     r15
0x18005eacc  pop     r14
0x18005eace  pop     rdi
0x18005eacf  pop     rsi
0x18005ead0  pop     rbp
0x18005ead1  pop     rbx
0x18005ead2  retn
0x18005ead3  mov     [r14], ebx
0x18005ead6  call    cs:__imp_GetProcessId
0x18005eadc  mov     rcx, [rsp+98h+arg_20]
0x18005eae4  mov     [rcx], eax
0x18005eae6  test    eax, eax
0x18005eae8  jnz     short loc_18005EA91
0x18005eaea  call    cs:__imp_GetLastError
0x18005eaf0  jmp     short loc_18005EA78
```
