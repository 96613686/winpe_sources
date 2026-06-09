# FirstSync::GetStoragePath(ushort const *,ushort * *)

- ea: `0x1800a0804`
- end: `0x1800a0943`
- name: `?GetStoragePath@FirstSync@@YAJPEBGPEAPEAG@Z`
- size: `319`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PWSTR *ppszPathOut, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18009f9f4`

## callees

- `0x180004eb0`
- `0x180005a74`
- `0x18000a5c4`
- `0x1800a0804`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a08ac`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a08d3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a08ac`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a08d3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800a0901`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800a0901`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a0884`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a0884`

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
0x1800a0804  mov     [rsp+arg_10], rbx
0x1800a0809  push    rbp
0x1800a080a  push    rsi
0x1800a080b  push    rdi
0x1800a080c  sub     rsp, 240h
0x1800a0813  mov     rax, cs:__security_cookie
0x1800a081a  xor     rax, rsp
0x1800a081d  mov     [rsp+258h+var_28], rax
0x1800a0825  mov     rdi, rdx
0x1800a0828  mov     rsi, rcx
0x1800a082b  test    rcx, rcx
0x1800a082e  jnz     short loc_1800A0856
0x1800a0830  lea     edx, [rcx+5Dh]; void *
0x1800a0833  mov     ebx, 80070057h
0x1800a0838  mov     rcx, [rsp+258h]; this
0x1800a0840  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a0847  mov     r9d, ebx; char *
0x1800a084a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a084f  mov     eax, ebx
0x1800a0851  jmp     loc_1800A091F
0x1800a0856  test    rdi, rdi
0x1800a0859  jnz     short loc_1800A0860
0x1800a085b  lea     edx, [rdi+5Eh]
0x1800a085e  jmp     short loc_1800A0833
0x1800a0860  xor     edx, edx; Val
0x1800a0862  lea     rcx, [rsp+258h+pszPath]; void *
0x1800a0867  mov     r8d, 208h; Size
0x1800a086d  call    memset_0
0x1800a0872  xor     edx, edx
0x1800a0874  lea     r8, [rsp+258h+pszPath]
0x1800a0879  mov     ebp, 104h
0x1800a087e  mov     r9d, ebp
0x1800a0881  lea     ecx, [rdx+4]
0x1800a0884  call    cs:__imp_GetBasicProfileFolderPath
0x1800a088b  nop     dword ptr [rax+rax+00h]
0x1800a0890  mov     ebx, eax
0x1800a0892  test    eax, eax
0x1800a0894  jns     short loc_1800A089D
0x1800a0896  mov     edx, 61h ; 'a'
0x1800a089b  jmp     short loc_1800A0838
0x1800a089d  lea     r8, aMicrosoftDmcli; "Microsoft\\DMClient"
0x1800a08a4  mov     rdx, rbp; cchPath
0x1800a08a7  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800a08ac  call    cs:__imp_PathCchAppend
0x1800a08b3  nop     dword ptr [rax+rax+00h]
0x1800a08b8  mov     ebx, eax
0x1800a08ba  test    eax, eax
0x1800a08bc  jns     short loc_1800A08C8
0x1800a08be  mov     edx, 64h ; 'd'
0x1800a08c3  jmp     loc_1800A0838
0x1800a08c8  mov     r8, rsi; pszMore
0x1800a08cb  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800a08d0  mov     rdx, rbp; cchPath
0x1800a08d3  call    cs:__imp_PathCchAppend
0x1800a08da  nop     dword ptr [rax+rax+00h]
0x1800a08df  mov     ebx, eax
0x1800a08e1  test    eax, eax
0x1800a08e3  jns     short loc_1800A08EF
0x1800a08e5  mov     edx, 67h ; 'g'
0x1800a08ea  jmp     loc_1800A0838
0x1800a08ef  mov     r9, rdi; ppszPathOut
0x1800a08f2  lea     rdx, aFirstsync; "FirstSync"
0x1800a08f9  xor     r8d, r8d; dwFlags
0x1800a08fc  lea     rcx, [rsp+258h+pszPath]; pszPathIn
0x1800a0901  call    cs:__imp_PathAllocCombine
0x1800a0908  nop     dword ptr [rax+rax+00h]
0x1800a090d  mov     ebx, eax
0x1800a090f  test    eax, eax
0x1800a0911  jns     short loc_1800A091D
0x1800a0913  mov     edx, 69h ; 'i'
0x1800a0918  jmp     loc_1800A0838
0x1800a091d  xor     eax, eax
0x1800a091f  mov     rcx, [rsp+258h+var_28]
0x1800a0927  xor     rcx, rsp; StackCookie
0x1800a092a  call    __security_check_cookie
0x1800a092f  mov     rbx, [rsp+258h+arg_10]
0x1800a0937  add     rsp, 240h
0x1800a093e  pop     rdi
0x1800a093f  pop     rsi
0x1800a0940  pop     rbp
0x1800a0941  retn
```
