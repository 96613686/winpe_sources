# HamQueryCallerTerminateReason

- ea: `0x18000c340`
- end: `0x18000c415`
- name: `HamQueryCallerTerminateReason`
- size: `213`
- prototype: `__int64 __fastcall(enum _HAM_TERMINATE_REASON *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c340`
- `0x18000c420`
- `0x18000c65c`
- `0x18001ae8e`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-core-psm-key-l1-1-0!PsmIsDynamicKey` at `0x18000c3e4`
- `api-ms-win-core-psm-key-l1-1-0!PsmIsDynamicKey` at `0x18000c3e4`
- `ntdll!NtClose` at `0x18000c3b2`
- `ntdll!NtClose` at `0x18000c3b2`
- `ntdll!NtOpenProcessToken` at `0x18000c38b`
- `ntdll!NtOpenProcessToken` at `0x18000c38b`

## pseudocode

```c
__int64 __fastcall HamQueryCallerTerminateReason(enum _HAM_TERMINATE_REASON *a1)
{
  int TokenHostInfo; // ebx
  void *TokenHandle; // [rsp+20h] [rbp-258h] BYREF
  unsigned __int16 v5[232]; // [rsp+30h] [rbp-248h] BYREF
  _BYTE v6[96]; // [rsp+200h] [rbp-78h] BYREF

  memset_0(v5, 0, 0x228u);
  TokenHandle = 0;
  TokenHostInfo = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( TokenHostInfo >= 0 )
    TokenHostInfo = CempGetTokenHostInfo(TokenHandle, (__int64)v5);
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( TokenHostInfo >= 0 )
  {
    if ( (unsigned __int8)PsmIsDynamicKey(v5) )
    {
      *(_DWORD *)a1 = 0;
    }
    else
    {
      TokenHostInfo = HampUtilQueryRegistryTerminateReason(v5, v6, a1);
      if ( TokenHostInfo < 0 )
        return (unsigned int)TokenHostInfo;
    }
    return 0;
  }
  return (unsigned int)TokenHostInfo;
}

```

## disassembly

```asm
0x18000c340  mov     [rsp+arg_8], rbx
0x18000c345  push    rdi
0x18000c346  sub     rsp, 270h
0x18000c34d  mov     rax, cs:__security_cookie
0x18000c354  xor     rax, rsp
0x18000c357  mov     [rsp+278h+var_18], rax
0x18000c35f  mov     rdi, rcx
0x18000c362  xor     edx, edx; Val
0x18000c364  lea     rcx, [rsp+278h+var_248]; void *
0x18000c369  mov     r8d, 228h; Size
0x18000c36f  call    memset_0
0x18000c374  lea     r8, [rsp+278h+TokenHandle]; TokenHandle
0x18000c379  mov     [rsp+278h+TokenHandle], 0
0x18000c382  mov     edx, 8; DesiredAccess
0x18000c387  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000c38b  call    cs:__imp_NtOpenProcessToken
0x18000c391  mov     ebx, eax
0x18000c393  test    eax, eax
0x18000c395  js      short loc_18000C3A8
0x18000c397  mov     rcx, [rsp+278h+TokenHandle]; TokenHandle
0x18000c39c  lea     rdx, [rsp+278h+var_248]
0x18000c3a1  call    CempGetTokenHostInfo
0x18000c3a6  mov     ebx, eax
0x18000c3a8  mov     rcx, [rsp+278h+TokenHandle]; Handle
0x18000c3ad  test    rcx, rcx
0x18000c3b0  jz      short loc_18000C3B8
0x18000c3b2  call    cs:__imp_NtClose
0x18000c3b8  test    ebx, ebx
0x18000c3ba  jns     short loc_18000C3DF
0x18000c3bc  mov     eax, ebx
0x18000c3be  mov     rcx, [rsp+278h+var_18]
0x18000c3c6  xor     rcx, rsp; StackCookie
0x18000c3c9  call    __security_check_cookie
0x18000c3ce  mov     rbx, [rsp+278h+arg_8]
0x18000c3d6  add     rsp, 270h
0x18000c3dd  pop     rdi
0x18000c3de  retn
0x18000c3df  lea     rcx, [rsp+278h+var_248]
0x18000c3e4  call    cs:__imp_PsmIsDynamicKey
0x18000c3ea  test    al, al
0x18000c3ec  jnz     short loc_18000C40D
0x18000c3ee  mov     r8, rdi; enum _HAM_TERMINATE_REASON *
0x18000c3f1  lea     rdx, [rsp+278h+var_78]; void *
0x18000c3f9  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x18000c3fe  call    ?HampUtilQueryRegistryTerminateReason@@YAJPEBGPEAXPEAW4_HAM_TERMINATE_REASON@@@Z; HampUtilQueryRegistryTerminateReason(ushort const *,void *,_HAM_TERMINATE_REASON *)
0x18000c403  mov     ebx, eax
0x18000c405  test    eax, eax
0x18000c407  js      short loc_18000C3BC
0x18000c409  xor     ebx, ebx
0x18000c40b  jmp     short loc_18000C3BC
0x18000c40d  mov     dword ptr [rdi], 0
0x18000c413  jmp     short loc_18000C409
```
