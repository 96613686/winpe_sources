# DiskPolicyEngine::RuntimeClassInitialize(IUserAccountStore *,DeletionPolicy)

- ea: `0x180021b30`
- end: `0x180021bcb`
- name: `?RuntimeClassInitialize@DiskPolicyEngine@@UEAAJPEAUIUserAccountStore@@W4DeletionPolicy@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18001b164`

## callees

- `0x180008a18`
- `0x180008a38`
- `0x18001c4c0`
- `0x180021b30`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x180021b7c`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x180021b7c`
- `USERENV!GetProfilesDirectoryW` at `0x180021b53`
- `USERENV!GetProfilesDirectoryW` at `0x180021b53`

## string_xrefs

- `0x180021b62`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\diskpolicyengine.cpp`
- `0x180021b92`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\diskpolicyengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiskPolicyEngine::RuntimeClassInitialize(__int64 a1, __int64 a2, unsigned int a3)
{
  const char *v6; // r9
  HRESULT v8; // ebx
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD cchSize; // [rsp+50h] [rbp+8h] BYREF

  cchSize = 260;
  if ( !GetProfilesDirectoryW((LPWSTR)(a1 + 74), &cchSize) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x19,
             (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\diskpolicyengine.cpp",
             v6);
  v8 = PathCchStripToRoot((PWSTR)(a1 + 74), 0x104u);
  if ( v8 < 0 )
  {
    v9 = 26;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\diskpolicyengine.cpp",
      (const char *)(unsigned int)v8,
      v10);
    return (unsigned int)v8;
  }
  v8 = BasePolicyEngine::RuntimeClassInitialize(a1, a2, a3);
  if ( v8 < 0 )
  {
    v9 = 27;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x180021b30  push    rbx
0x180021b32  push    rbp
0x180021b33  push    rsi
0x180021b34  push    rdi
0x180021b35  sub     rsp, 28h
0x180021b39  mov     rbp, rdx
0x180021b3c  mov     [rsp+48h+cchSize], 104h
0x180021b44  mov     rdi, rcx
0x180021b47  lea     rdx, [rsp+48h+cchSize]; lpcchSize
0x180021b4c  add     rcx, 4Ah ; 'J'; lpProfileDir
0x180021b50  mov     esi, r8d
0x180021b53  call    cs:__imp_GetProfilesDirectoryW
0x180021b59  test    eax, eax
0x180021b5b  jnz     short loc_180021B73
0x180021b5d  mov     rcx, [rsp+48h]; this
0x180021b62  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\sharedpc\\accountma"...
0x180021b69  lea     edx, [rax+19h]; void *
0x180021b6c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021b71  jmp     short loc_180021BC2
0x180021b73  mov     edx, 104h; cchPath
0x180021b78  lea     rcx, [rdi+4Ah]; pszPath
0x180021b7c  call    cs:__imp_PathCchStripToRoot
0x180021b82  mov     ebx, eax
0x180021b84  test    eax, eax
0x180021b86  jns     short loc_180021BA5
0x180021b88  mov     edx, 1Ah; void *
0x180021b8d  mov     rcx, [rsp+48h]; this
0x180021b92  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\sharedpc\\accountma"...
0x180021b99  mov     r9d, ebx; char *
0x180021b9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021ba1  mov     eax, ebx
0x180021ba3  jmp     short loc_180021BC2
0x180021ba5  mov     r8d, esi
0x180021ba8  mov     rdx, rbp
0x180021bab  mov     rcx, rdi
0x180021bae  call    ?RuntimeClassInitialize@BasePolicyEngine@@UEAAJPEAUIUserAccountStore@@W4DeletionPolicy@@@Z; BasePolicyEngine::RuntimeClassInitialize(IUserAccountStore *,DeletionPolicy)
0x180021bb3  mov     ebx, eax
0x180021bb5  test    eax, eax
0x180021bb7  jns     short loc_180021BC0
0x180021bb9  mov     edx, 1Bh
0x180021bbe  jmp     short loc_180021B8D
0x180021bc0  xor     eax, eax
0x180021bc2  add     rsp, 28h
0x180021bc6  pop     rdi
0x180021bc7  pop     rsi
0x180021bc8  pop     rbp
0x180021bc9  pop     rbx
0x180021bca  retn
```
