# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x140059cd4`
- end: `0x140059ef7`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `547`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140034968`

## callees

- `0x14000337b`
- `0x14000aad4`
- `0x1400597c8`
- `0x1400598dc`
- `0x140059cd4`
- `0x14005a130`
- `0x14005a2fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059d30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059d30`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140059d20`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140059d20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140059d03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140059d03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140059d6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140059d6c`
- `ntdll!RtlFreeHeap` at `0x140059e79`
- `ntdll!RtlFreeHeap` at `0x140059eab`
- `ntdll!RtlFreeHeap` at `0x140059ed8`
- `ntdll!RtlFreeHeap` at `0x140059e79`
- `ntdll!RtlFreeHeap` at `0x140059eab`
- `ntdll!RtlFreeHeap` at `0x140059ed8`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetProcessAppId(HANDLE ProcessHandle, _QWORD *a2, unsigned __int16 **a3)
{
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v5; // r9
  signed int LastError; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  PVOID v9; // r8
  const unsigned __int16 *v10; // rcx
  int v11; // eax
  void *v12; // rbx
  unsigned int AppUserModelId; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  unsigned int v16; // edi
  PVOID P[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  void *TokenHandle; // [rsp+40h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+48h] [rbp+18h] BYREF

  *a2 = 0;
  *(_OWORD *)P = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    v7 = -4;
    TokenHandle = (void *)-4LL;
  }
  else
  {
    if ( !OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_8;
    }
    v7 = (__int64)TokenHandle;
  }
  LastError = ARI::ProcessToken::SysAppId::Open((HANDLE)v7, P, (const UNICODE_STRING **)&P[1], v5);
  if ( TokenHandle != (void *)-4LL )
    CloseHandle(TokenHandle);
LABEL_8:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023728 || LastError == -2147024891 )
  {
    v9 = P[0];
    if ( !P[0] )
      return (unsigned int)LastError;
LABEL_28:
    if ( v9 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    return (unsigned int)LastError;
  }
  if ( LastError < 0 )
  {
    v8 = 165;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)LastError,
      (int)P[0]);
LABEL_15:
    v9 = P[0];
    goto LABEL_28;
  }
  LODWORD(TokenHandle) = 0;
  if ( ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(
         (ARI::ProcessToken::AutoSysAppId *)P,
         0,
         (unsigned int *)&TokenHandle,
         0) != 122 )
  {
    LastError = -2147418113;
    v8 = 168;
    goto LABEL_14;
  }
  pv = 0;
  CoTaskMemFree_0(0);
  v11 = CoAllocStringLen(v10, (unsigned int)TokenHandle, (unsigned __int16 **)&pv);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)v11,
      (int)P[0]);
    CoTaskMemFree_0(pv);
    goto LABEL_15;
  }
  v12 = pv;
  AppUserModelId = ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(
                     (ARI::ProcessToken::AutoSysAppId *)P,
                     (unsigned int)TokenHandle,
                     (unsigned int *)&TokenHandle,
                     (unsigned __int16 *)pv);
  if ( AppUserModelId )
  {
    v16 = wil::details::in1diag3::Return_Win32(retaddr, v14, v15, (const char *)AppUserModelId, (unsigned int)P[0]);
    CoTaskMemFree_0(v12);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return v16;
  }
  else
  {
    *a2 = v12;
    CoTaskMemFree_0(0);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x140059cd4  mov     [rsp-8+arg_10], rbx
0x140059cd9  mov     [rsp-8+arg_18], rdi
0x140059cde  push    rbp
0x140059cdf  mov     rbp, rsp
0x140059ce2  sub     rsp, 30h
0x140059ce6  xorps   xmm0, xmm0
0x140059ce9  mov     qword ptr [rdx], 0
0x140059cf0  movdqu  xmmword ptr [rbp+P], xmm0
0x140059cf5  mov     rdi, rdx
0x140059cf8  mov     [rbp+TokenHandle], 0
0x140059d00  mov     rbx, rcx
0x140059d03  call    cs:__imp_GetCurrentProcess
0x140059d0a  nop     dword ptr [rax+rax+00h]
0x140059d0f  cmp     rbx, rax
0x140059d12  jz      short loc_140059D48
0x140059d14  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140059d18  mov     edx, 8; DesiredAccess
0x140059d1d  mov     rcx, rbx; ProcessHandle
0x140059d20  call    cs:__imp_OpenProcessToken
0x140059d27  nop     dword ptr [rax+rax+00h]
0x140059d2c  test    eax, eax
0x140059d2e  jnz     short loc_140059D42
0x140059d30  call    cs:__imp_GetLastError
0x140059d37  nop     dword ptr [rax+rax+00h]
0x140059d3c  mov     ebx, eax
0x140059d3e  test    eax, eax
0x140059d40  jnz     short loc_140059D78
0x140059d42  mov     rcx, [rbp+TokenHandle]
0x140059d46  jmp     short loc_140059D53
0x140059d48  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x140059d4f  mov     [rbp+TokenHandle], rcx
0x140059d53  lea     r8, [rbp+P+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x140059d57  lea     rdx, [rbp+P]; void *
0x140059d5b  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x140059d60  mov     rcx, [rbp+TokenHandle]; hObject
0x140059d64  mov     ebx, eax
0x140059d66  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x140059d6a  jz      short loc_140059D78
0x140059d6c  call    cs:__imp_CloseHandle
0x140059d73  nop     dword ptr [rax+rax+00h]
0x140059d78  test    ebx, ebx
0x140059d7a  jle     short loc_140059D85
0x140059d7c  movzx   ebx, bx
0x140059d7f  or      ebx, 80070000h
0x140059d85  cmp     ebx, 80070490h
0x140059d8b  jz      loc_140059EBB
0x140059d91  cmp     ebx, 80070005h
0x140059d97  jz      loc_140059EBB
0x140059d9d  test    ebx, ebx
0x140059d9f  jns     short loc_140059DC2
0x140059da1  mov     edx, 0A5h; void *
0x140059da6  mov     rcx, [rbp+8]; this
0x140059daa  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x140059db1  mov     r9d, ebx; char *
0x140059db4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140059db9  mov     r8, [rbp+P]
0x140059dbd  jmp     loc_140059EC4
0x140059dc2  xor     r9d, r9d; unsigned __int16 *
0x140059dc5  mov     dword ptr [rbp+TokenHandle], 0
0x140059dcc  lea     r8, [rbp+TokenHandle]; unsigned int *
0x140059dd0  xor     edx, edx; unsigned int
0x140059dd2  lea     rcx, [rbp+P]; this
0x140059dd6  call    ?GetAppUserModelId@AutoSysAppId@ProcessToken@ARI@@QEBAJIPEAIPEAG@Z; ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(uint,uint *,ushort *)
0x140059ddb  cmp     eax, 7Ah ; 'z'
0x140059dde  jz      short loc_140059DEC
0x140059de0  mov     ebx, 8000FFFFh
0x140059de5  mov     edx, 0A8h
0x140059dea  jmp     short loc_140059DA6
0x140059dec  xor     ecx, ecx; pv
0x140059dee  mov     [rbp+pv], 0
0x140059df6  call    CoTaskMemFree_0
0x140059dfb  mov     edx, dword ptr [rbp+TokenHandle]; unsigned __int64
0x140059dfe  lea     r8, [rbp+pv]; unsigned __int16 **
0x140059e02  call    ?CoAllocStringLen@@YAJPEBG_KPEAPEAG@Z; CoAllocStringLen(ushort const *,unsigned __int64,ushort * *)
0x140059e07  mov     ebx, eax
0x140059e09  test    eax, eax
0x140059e0b  jns     short loc_140059E30
0x140059e0d  mov     rcx, [rbp+8]; this
0x140059e11  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x140059e18  mov     r9d, eax; char *
0x140059e1b  mov     edx, 0ABh; void *
0x140059e20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140059e25  mov     rcx, [rbp+pv]; pv
0x140059e29  call    CoTaskMemFree_0
0x140059e2e  jmp     short loc_140059DB9
0x140059e30  mov     rbx, [rbp+pv]
0x140059e34  lea     r8, [rbp+TokenHandle]; unsigned int *
0x140059e38  mov     edx, dword ptr [rbp+TokenHandle]; unsigned int
0x140059e3b  lea     rcx, [rbp+P]; this
0x140059e3f  mov     r9, rbx; unsigned __int16 *
0x140059e42  call    ?GetAppUserModelId@AutoSysAppId@ProcessToken@ARI@@QEBAJIPEAIPEAG@Z; ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(uint,uint *,ushort *)
0x140059e47  test    eax, eax
0x140059e49  jz      short loc_140059E89
0x140059e4b  mov     rcx, [rbp+8]; this
0x140059e4f  mov     r9d, eax; char *
0x140059e52  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140059e57  mov     rcx, rbx; pv
0x140059e5a  mov     edi, eax
0x140059e5c  call    CoTaskMemFree_0
0x140059e61  mov     r8, [rbp+P]; P
0x140059e65  test    r8, r8
0x140059e68  jz      short loc_140059E85
0x140059e6a  mov     rcx, gs:60h
0x140059e73  xor     edx, edx; Flags
0x140059e75  mov     rcx, [rcx+30h]; HeapHandle
0x140059e79  call    cs:__imp_RtlFreeHeap
0x140059e80  nop     dword ptr [rax+rax+00h]
0x140059e85  mov     eax, edi
0x140059e87  jmp     short loc_140059EE6
0x140059e89  xor     ecx, ecx; pv
0x140059e8b  mov     [rdi], rbx
0x140059e8e  call    CoTaskMemFree_0
0x140059e93  mov     r8, [rbp+P]; P
0x140059e97  test    r8, r8
0x140059e9a  jz      short loc_140059EB7
0x140059e9c  mov     rcx, gs:60h
0x140059ea5  xor     edx, edx; Flags
0x140059ea7  mov     rcx, [rcx+30h]; HeapHandle
0x140059eab  call    cs:__imp_RtlFreeHeap
0x140059eb2  nop     dword ptr [rax+rax+00h]
0x140059eb7  xor     eax, eax
0x140059eb9  jmp     short loc_140059EE6
0x140059ebb  mov     r8, [rbp+P]; P
0x140059ebf  test    r8, r8
0x140059ec2  jz      short loc_140059EE4
0x140059ec4  test    r8, r8
0x140059ec7  jz      short loc_140059EE4
0x140059ec9  mov     rcx, gs:60h
0x140059ed2  xor     edx, edx; Flags
0x140059ed4  mov     rcx, [rcx+30h]; HeapHandle
0x140059ed8  call    cs:__imp_RtlFreeHeap
0x140059edf  nop     dword ptr [rax+rax+00h]
0x140059ee4  mov     eax, ebx
0x140059ee6  mov     rbx, [rsp+30h+arg_10]
0x140059eeb  mov     rdi, [rsp+30h+arg_18]
0x140059ef0  add     rsp, 30h
0x140059ef4  pop     rbp
0x140059ef5  retn
```
