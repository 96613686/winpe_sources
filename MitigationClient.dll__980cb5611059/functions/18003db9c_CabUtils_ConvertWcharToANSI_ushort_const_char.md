# CabUtils::ConvertWcharToANSI(ushort const *,char * *)

- ea: `0x18003db9c`
- end: `0x18003dcf2`
- name: `?ConvertWcharToANSI@CabUtils@@CAJPEBGPEAPEAD@Z`
- size: `342`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, char **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18003de68`

## callees

- `0x18001206c`
- `0x18001208c`
- `0x180016c30`
- `0x18001fab8`
- `0x18002545c`
- `0x1800271bc`
- `0x18003db9c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18003dbdd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18003dc8b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18003dbdd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18003dc8b`

## string_xrefs

- `0x18003dc01`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003dc9a`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003dcc7`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CabUtils::ConvertWcharToANSI(LPCWCH lpWideCharStr, char **a2)
{
  int v4; // eax
  int cbMultiByte; // edi
  int Error; // eax
  int LastError; // ebx
  void *v8; // rcx
  char v9; // r10
  char *v10; // rbx
  const char *v11; // r9
  int lpMultiByteStr; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPSTR v15; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v4 = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, 0, 0, 0, 0);
  cbMultiByte = v4;
  if ( v4 )
  {
    v15 = 0;
    v16 = 0;
    LastError = ULongLongMult(v4, 1u, &v16);
    if ( LastError < 0 || (LastError = CTCoAllocPolicy::Alloc(v8, v9, v16, (void **)&v15), LastError < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
        (const char *)(unsigned int)LastError,
        lpMultiByteStr);
    }
    else
    {
      v10 = v15;
      if ( WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, v15, cbMultiByte, 0, 0) )
      {
        v15 = 0;
        *a2 = v10;
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1DB,
                      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
                      v11);
      }
    }
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>((void **)&v15);
  }
  else
  {
    Error = ResultFromKnownLastError();
    LastError = Error;
    if ( Error < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D3,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
        (const char *)(unsigned int)Error,
        lpMultiByteStr);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18003db9c  mov     rax, rsp
0x18003db9f  mov     [rax+8], rbx
0x18003dba3  push    rbp
0x18003dba4  push    rsi
0x18003dba5  push    rdi
0x18003dba6  sub     rsp, 40h
0x18003dbaa  mov     rsi, rdx
0x18003dbad  mov     rbp, rcx
0x18003dbb0  mov     qword ptr [rax-20h], 0
0x18003dbb8  mov     qword ptr [rax-28h], 0
0x18003dbc0  mov     dword ptr [rax-30h], 0
0x18003dbc7  mov     qword ptr [rax-38h], 0
0x18003dbcf  or      r9d, 0FFFFFFFFh; cchWideChar
0x18003dbd3  mov     r8, rcx; lpWideCharStr
0x18003dbd6  xor     edx, edx; dwFlags
0x18003dbd8  mov     ecx, 0FDE9h; CodePage
0x18003dbdd  call    cs:__imp_WideCharToMultiByte
0x18003dbe3  movsxd  rdi, eax
0x18003dbe6  test    eax, eax
0x18003dbe8  jnz     short loc_18003DC17
0x18003dbea  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003dbef  mov     ebx, eax
0x18003dbf1  test    eax, eax
0x18003dbf3  jns     loc_18003DCE3
0x18003dbf9  mov     rcx, [rsp+58h]; this
0x18003dbfe  mov     r9d, eax; char *
0x18003dc01  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003dc08  mov     edx, 1D3h; void *
0x18003dc0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dc12  jmp     loc_18003DCE3
0x18003dc17  mov     [rsp+58h+arg_10], 0
0x18003dc20  mov     [rsp+58h+arg_18], 0
0x18003dc29  mov     rcx, rdi; unsigned __int64
0x18003dc2c  lea     r8, [rsp+58h+arg_18]; unsigned __int64 *
0x18003dc31  mov     r10d, 1
0x18003dc37  mov     edx, r10d; unsigned __int64
0x18003dc3a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003dc3f  mov     ebx, eax
0x18003dc41  test    eax, eax
0x18003dc43  js      short loc_18003DCBF
0x18003dc45  lea     r9, [rsp+58h+arg_10]; void **
0x18003dc4a  mov     r8, [rsp+58h+arg_18]; unsigned __int64
0x18003dc4f  mov     edx, r10d; unsigned int
0x18003dc52  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003dc57  mov     ebx, eax
0x18003dc59  test    eax, eax
0x18003dc5b  js      short loc_18003DCBF
0x18003dc5d  mov     [rsp+58h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18003dc66  mov     [rsp+58h+lpDefaultChar], 0; lpDefaultChar
0x18003dc6f  mov     [rsp+58h+cbMultiByte], edi; cbMultiByte
0x18003dc73  mov     rbx, [rsp+58h+arg_10]
0x18003dc78  mov     [rsp+58h+lpMultiByteStr], rbx; lpMultiByteStr
0x18003dc7d  or      r9d, 0FFFFFFFFh; cchWideChar
0x18003dc81  mov     r8, rbp; lpWideCharStr
0x18003dc84  xor     edx, edx; dwFlags
0x18003dc86  mov     ecx, 0FDE9h; CodePage
0x18003dc8b  call    cs:__imp_WideCharToMultiByte
0x18003dc91  test    eax, eax
0x18003dc93  jnz     short loc_18003DCAF
0x18003dc95  mov     rcx, [rsp+58h]; this
0x18003dc9a  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003dca1  mov     edx, 1DBh; void *
0x18003dca6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003dcab  mov     ebx, eax
0x18003dcad  jmp     short loc_18003DCD9
0x18003dcaf  mov     [rsp+58h+arg_10], 0
0x18003dcb8  mov     [rsi], rbx
0x18003dcbb  xor     ebx, ebx
0x18003dcbd  jmp     short loc_18003DCD9
0x18003dcbf  mov     rcx, [rsp+58h]; this
0x18003dcc4  mov     r9d, ebx; char *
0x18003dcc7  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003dcce  mov     edx, 1D8h; void *
0x18003dcd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dcd8  nop
0x18003dcd9  lea     rcx, [rsp+58h+arg_10]
0x18003dcde  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18003dce3  mov     eax, ebx
0x18003dce5  mov     rbx, [rsp+58h+arg_0]
0x18003dcea  add     rsp, 40h
0x18003dcee  pop     rdi
0x18003dcef  pop     rsi
0x18003dcf0  pop     rbp
0x18003dcf1  retn
```
