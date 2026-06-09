# Windows::System::ShutdownManagerImpl::s_InitiateSystemShutdownThread(void *)

- ea: `0x18000fad0`
- end: `0x18000fbd8`
- name: `?s_InitiateSystemShutdownThread@ShutdownManagerImpl@System@Windows@@CAKPEAX@Z`
- size: `264`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002dc0`
- `0x18000e940`
- `0x18000fad0`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x18000fb5d`
- `ntdll!RtlAcquirePrivilege` at `0x18000fb5d`
- `ntdll!RtlReleasePrivilege` at `0x18000fba8`
- `ntdll!RtlReleasePrivilege` at `0x18000fba8`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18000fb96`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18000fb96`

## pseudocode

```c
_BOOL8 __fastcall Windows::System::ShutdownManagerImpl::s_InitiateSystemShutdownThread(PVOID Parameter)
{
  int bRebootAfterShutdown; // ebp
  DWORD v3; // r14d
  BOOL v4; // edi
  NTSTATUS v5; // eax
  unsigned __int64 v6; // rdx
  int v7; // esi
  ULONG v9; // [rsp+30h] [rbp-78h] BYREF
  PVOID ReturnedState; // [rsp+38h] [rbp-70h] BYREF
  WCHAR Message[8]; // [rsp+40h] [rbp-68h] BYREF
  __int128 v12; // [rsp+60h] [rbp-48h]
  __int128 v13; // [rsp+70h] [rbp-38h]

  bRebootAfterShutdown = *((_DWORD *)Parameter + 32);
  v3 = *((_DWORD *)Parameter + 31);
  wmemcpy(Message, L"User initiated system shutdown.", 16);
  v4 = 1;
  *((_DWORD *)Parameter + 30) = 0;
  ReturnedState = 0;
  v9 = 19;
  v12 = *(_OWORD *)L"ystem shutdown.";
  v13 = *(_OWORD *)L"utdown.";
  v5 = RtlAcquirePrivilege(&v9, 1u, 0, &ReturnedState);
  v7 = v5;
  if ( v5 < 0 )
  {
    v6 = (unsigned int)v5;
    LODWORD(v6) = v5 | 0x10000000;
    *((_DWORD *)Parameter + 30) = v5 | 0x10000000;
  }
  wil::details::SetEvent(*((wil::details **)Parameter + 13), (void *)v6);
  if ( v7 >= 0 )
  {
    v4 = !InitiateSystemShutdownExW(0, Message, v3, 1, bRebootAfterShutdown, 0);
    RtlReleasePrivilege(ReturnedState);
  }
  return v4;
}

```

## disassembly

```asm
0x18000fad0  mov     r11, rsp
0x18000fad3  mov     [r11+10h], rbx
0x18000fad7  mov     [r11+18h], rbp
0x18000fadb  push    rsi
0x18000fadc  push    rdi
0x18000fadd  push    r14
0x18000fadf  sub     rsp, 90h
0x18000fae6  mov     rax, cs:__security_cookie
0x18000faed  xor     rax, rsp
0x18000faf0  mov     [rsp+0A8h+var_28], rax
0x18000faf8  movaps  xmm0, xmmword ptr cs:aUserInitiatedS; "User initiated system shutdown."
0x18000faff  lea     r9, [r11-70h]; ReturnedState
0x18000fb03  movaps  xmm1, xmmword ptr cs:aUserInitiatedS+10h; "tiated system shutdown."
0x18000fb0a  xor     r8d, r8d; Flags
0x18000fb0d  mov     ebp, [rcx+80h]
0x18000fb13  mov     rbx, rcx
0x18000fb16  mov     r14d, [rcx+7Ch]
0x18000fb1a  movaps  xmmword ptr [rsp+0A8h+Message], xmm0
0x18000fb1f  movaps  xmm0, xmmword ptr cs:aUserInitiatedS+20h; "ystem shutdown."
0x18000fb26  lea     edi, [r8+1]
0x18000fb2a  movaps  [rsp+0A8h+var_58], xmm1
0x18000fb2f  mov     edx, edi; NumPriv
0x18000fb31  movaps  xmm1, xmmword ptr cs:aUserInitiatedS+30h; "utdown."
0x18000fb38  mov     dword ptr [rcx+78h], 0
0x18000fb3f  lea     rcx, [r11-78h]; Privilege
0x18000fb43  mov     qword ptr [r11-70h], 0
0x18000fb4b  mov     [rsp+0A8h+var_78], 13h
0x18000fb53  movaps  [rsp+0A8h+var_48], xmm0
0x18000fb58  movaps  [rsp+0A8h+var_38], xmm1
0x18000fb5d  call    cs:__imp_RtlAcquirePrivilege
0x18000fb63  mov     esi, eax
0x18000fb65  test    eax, eax
0x18000fb67  jns     short loc_18000FB72
0x18000fb69  mov     edx, eax
0x18000fb6b  bts     edx, 1Ch; void *
0x18000fb6f  mov     [rbx+78h], edx
0x18000fb72  mov     rcx, [rbx+68h]; this
0x18000fb76  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18000fb7b  test    esi, esi
0x18000fb7d  js      short loc_18000FBAE
0x18000fb7f  xor     ebx, ebx
0x18000fb81  lea     rdx, [rsp+0A8h+Message]; lpMessage
0x18000fb86  mov     [rsp+0A8h+dwReason], ebx; dwReason
0x18000fb8a  mov     r9d, edi; bForceAppsClosed
0x18000fb8d  mov     r8d, r14d; dwTimeout
0x18000fb90  mov     [rsp+0A8h+bRebootAfterShutdown], ebp; bRebootAfterShutdown
0x18000fb94  xor     ecx, ecx; lpMachineName
0x18000fb96  call    cs:__imp_InitiateSystemShutdownExW
0x18000fb9c  mov     rcx, [rsp+0A8h+ReturnedState]; ReturnedState
0x18000fba1  test    eax, eax
0x18000fba3  cmovz   ebx, edi
0x18000fba6  mov     edi, ebx
0x18000fba8  call    cs:__imp_RtlReleasePrivilege
0x18000fbae  mov     eax, edi
0x18000fbb0  mov     rcx, [rsp+0A8h+var_28]
0x18000fbb8  xor     rcx, rsp; StackCookie
0x18000fbbb  call    __security_check_cookie
0x18000fbc0  lea     r11, [rsp+0A8h+var_18]
0x18000fbc8  mov     rbx, [r11+28h]
0x18000fbcc  mov     rbp, [r11+30h]
0x18000fbd0  mov     rsp, r11
0x18000fbd3  pop     r14
0x18000fbd5  pop     rdi
0x18000fbd6  pop     rsi
0x18000fbd7  retn
```
