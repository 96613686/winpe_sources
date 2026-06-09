# FirstSync::GetStoragePath(ushort const *,ushort * *)

- ea: `0x18009d88c`
- end: `0x18009d9b2`
- name: `?GetStoragePath@FirstSync@@YAJPEBGPEAPEAG@Z`
- size: `294`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PWSTR *ppszPathOut, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18009cb04`

## callees

- `0x180004d50`
- `0x180005904`
- `0x18000a2a4`
- `0x18009d88c`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009d92e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009d94f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009d92e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009d94f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009d977`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009d977`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18009d90c`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18009d90c`

## pseudocode

```c
__int64 __fastcall FirstSync::GetStoragePath(PCWSTR pszMore, PWSTR *ppszPathOut, unsigned __int16 **a3)
{
  __int64 v5; // rdx
  HRESULT BasicProfileFolderPath; // ebx
  int pszPath[132]; // [rsp+20h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  if ( !pszMore )
  {
    v5 = 93;
LABEL_3:
    BasicProfileFolderPath = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      pszPath[0]);
    return (unsigned int)BasicProfileFolderPath;
  }
  if ( !ppszPathOut )
  {
    v5 = 94;
    goto LABEL_3;
  }
  memset_0(pszPath, 0, 0x208u);
  BasicProfileFolderPath = GetBasicProfileFolderPath(4, 0, pszPath, 260);
  if ( BasicProfileFolderPath < 0 )
  {
    v5 = 97;
    goto LABEL_4;
  }
  BasicProfileFolderPath = PathCchAppend((PWSTR)pszPath, 0x104u, L"Microsoft\\DMClient");
  if ( BasicProfileFolderPath < 0 )
  {
    v5 = 100;
    goto LABEL_4;
  }
  BasicProfileFolderPath = PathCchAppend((PWSTR)pszPath, 0x104u, pszMore);
  if ( BasicProfileFolderPath < 0 )
  {
    v5 = 103;
    goto LABEL_4;
  }
  BasicProfileFolderPath = PathAllocCombine((PCWSTR)pszPath, L"FirstSync", 0, ppszPathOut);
  if ( BasicProfileFolderPath < 0 )
  {
    v5 = 105;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x18009d88c  mov     [rsp+arg_10], rbx
0x18009d891  push    rbp
0x18009d892  push    rsi
0x18009d893  push    rdi
0x18009d894  sub     rsp, 240h
0x18009d89b  mov     rax, cs:__security_cookie
0x18009d8a2  xor     rax, rsp
0x18009d8a5  mov     [rsp+258h+var_28], rax
0x18009d8ad  mov     rdi, rdx
0x18009d8b0  mov     rsi, rcx
0x18009d8b3  test    rcx, rcx
0x18009d8b6  jnz     short loc_18009D8DE
0x18009d8b8  lea     edx, [rcx+5Dh]; void *
0x18009d8bb  mov     ebx, 80070057h
0x18009d8c0  mov     rcx, [rsp+258h]; this
0x18009d8c8  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009d8cf  mov     r9d, ebx; char *
0x18009d8d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d8d7  mov     eax, ebx
0x18009d8d9  jmp     loc_18009D98F
0x18009d8de  test    rdi, rdi
0x18009d8e1  jnz     short loc_18009D8E8
0x18009d8e3  lea     edx, [rdi+5Eh]
0x18009d8e6  jmp     short loc_18009D8BB
0x18009d8e8  xor     edx, edx; Val
0x18009d8ea  lea     rcx, [rsp+258h+pszPath]; void *
0x18009d8ef  mov     r8d, 208h; Size
0x18009d8f5  call    memset_0
0x18009d8fa  xor     edx, edx
0x18009d8fc  lea     r8, [rsp+258h+pszPath]
0x18009d901  mov     ebp, 104h
0x18009d906  mov     r9d, ebp
0x18009d909  lea     ecx, [rdx+4]
0x18009d90c  call    cs:__imp_GetBasicProfileFolderPath
0x18009d912  mov     ebx, eax
0x18009d914  test    eax, eax
0x18009d916  jns     short loc_18009D91F
0x18009d918  mov     edx, 61h ; 'a'
0x18009d91d  jmp     short loc_18009D8C0
0x18009d91f  lea     r8, aMicrosoftDmcli; "Microsoft\\DMClient"
0x18009d926  mov     rdx, rbp; cchPath
0x18009d929  lea     rcx, [rsp+258h+pszPath]; pszPath
0x18009d92e  call    cs:__imp_PathCchAppend
0x18009d934  mov     ebx, eax
0x18009d936  test    eax, eax
0x18009d938  jns     short loc_18009D944
0x18009d93a  mov     edx, 64h ; 'd'
0x18009d93f  jmp     loc_18009D8C0
0x18009d944  mov     r8, rsi; pszMore
0x18009d947  lea     rcx, [rsp+258h+pszPath]; pszPath
0x18009d94c  mov     rdx, rbp; cchPath
0x18009d94f  call    cs:__imp_PathCchAppend
0x18009d955  mov     ebx, eax
0x18009d957  test    eax, eax
0x18009d959  jns     short loc_18009D965
0x18009d95b  mov     edx, 67h ; 'g'
0x18009d960  jmp     loc_18009D8C0
0x18009d965  mov     r9, rdi; ppszPathOut
0x18009d968  lea     rdx, aFirstsync; "FirstSync"
0x18009d96f  xor     r8d, r8d; dwFlags
0x18009d972  lea     rcx, [rsp+258h+pszPath]; pszPathIn
0x18009d977  call    cs:__imp_PathAllocCombine
0x18009d97d  mov     ebx, eax
0x18009d97f  test    eax, eax
0x18009d981  jns     short loc_18009D98D
0x18009d983  mov     edx, 69h ; 'i'
0x18009d988  jmp     loc_18009D8C0
0x18009d98d  xor     eax, eax
0x18009d98f  mov     rcx, [rsp+258h+var_28]
0x18009d997  xor     rcx, rsp; StackCookie
0x18009d99a  call    __security_check_cookie
0x18009d99f  mov     rbx, [rsp+258h+arg_10]
0x18009d9a7  add     rsp, 240h
0x18009d9ae  pop     rdi
0x18009d9af  pop     rsi
0x18009d9b0  pop     rbp
0x18009d9b1  retn
```
