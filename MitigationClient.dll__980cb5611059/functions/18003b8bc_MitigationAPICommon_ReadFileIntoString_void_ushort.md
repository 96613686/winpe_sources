# MitigationAPICommon::ReadFileIntoString(void *,ushort * *)

- ea: `0x18003b8bc`
- end: `0x18003b9f8`
- name: `?ReadFileIntoString@MitigationAPICommon@@SAJPEAXPEAPEAG@Z`
- size: `316`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003ccf0`

## callees

- `0x18001206c`
- `0x18001208c`
- `0x1800271bc`
- `0x18002b180`
- `0x18003b6f0`
- `0x18003b8bc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003b99c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003b99c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b94f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b94f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b93a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b9e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b93a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b9e3`

## string_xrefs

- `0x18003b917`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\mitigationapicommon.cpp`
- `0x18003b96d`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\mitigationapicommon.cpp`
- `0x18003b9aa`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\mitigationapicommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MitigationAPICommon::ReadFileIntoString(void *a1, unsigned __int16 **a2)
{
  int FileIntoByteArray; // ebx
  void *v4; // rcx
  int cchWideChar; // edi
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rbx
  const char *v9; // r9
  void *v10; // rcx
  int lpWideCharStr; // [rsp+20h] [rbp-30h]
  LPVOID *p_pv; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 *v13; // [rsp+38h] [rbp-18h] BYREF
  char v14; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned __int16 *v16; // [rsp+80h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+38h] BYREF

  pv = 0;
  LODWORD(v16) = 0;
  p_pv = &pv;
  v13 = 0;
  v14 = 1;
  FileIntoByteArray = MitigationAPICommon::ReadFileIntoByteArray(a1, (LPVOID *)&v13, (unsigned int *)&v16, 1);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
  if ( FileIntoByteArray < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\mitigationapicommon.cpp",
      (const char *)(unsigned int)FileIntoByteArray,
      lpWideCharStr);
LABEL_3:
    v4 = pv;
    pv = 0;
    if ( v4 )
      CoTaskMemFree(v4);
    return (unsigned int)FileIntoByteArray;
  }
  cchWideChar = (int)v16;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (unsigned int)v16);
  v8 = v7;
  v16 = v7;
  if ( !v7 )
  {
    FileIntoByteArray = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\mitigationapicommon.cpp",
      (const char *)0x8007000ELL,
      lpWideCharStr);
LABEL_8:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>((void **)&v16);
    goto LABEL_3;
  }
  if ( !MultiByteToWideChar(0, 0, (LPCCH)pv, -1, v7, cchWideChar) )
  {
    FileIntoByteArray = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x67,
                          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\mitigationapicommon.cpp",
                          v9);
    goto LABEL_8;
  }
  v16 = 0;
  *a2 = v8;
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>((void **)&v16);
  v10 = pv;
  pv = 0;
  if ( v10 )
    CoTaskMemFree(v10);
  return 0;
}

```

## disassembly

```asm
0x18003b8bc  mov     [rsp-18h+arg_0], rbx
0x18003b8c1  push    rbp
0x18003b8c2  push    rsi
0x18003b8c3  push    rdi
0x18003b8c4  mov     rbp, rsp
0x18003b8c7  sub     rsp, 50h
0x18003b8cb  mov     rsi, rdx
0x18003b8ce  mov     [rbp+pv], 0
0x18003b8d6  mov     dword ptr [rbp+arg_10], 0
0x18003b8dd  lea     rax, [rbp+pv]
0x18003b8e1  mov     [rbp+var_20], rax
0x18003b8e5  mov     [rbp+var_18], 0
0x18003b8ed  mov     [rbp+var_10], 1
0x18003b8f1  mov     r9b, 1; bool
0x18003b8f4  lea     r8, [rbp+arg_10]; unsigned int *
0x18003b8f8  lea     rdx, [rbp+var_18]; unsigned __int8 **
0x18003b8fc  call    ?ReadFileIntoByteArray@MitigationAPICommon@@SAJPEAXPEAPEAEPEAK_N@Z; MitigationAPICommon::ReadFileIntoByteArray(void *,uchar * *,ulong *,bool)
0x18003b901  mov     ebx, eax
0x18003b903  lea     rcx, [rbp+var_20]
0x18003b907  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003b90c  test    ebx, ebx
0x18003b90e  jns     short loc_18003B947
0x18003b910  mov     rcx, [rbp+18h]; this
0x18003b914  mov     r9d, ebx; char *
0x18003b917  lea     r8, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003b91e  mov     edx, 62h ; 'b'; void *
0x18003b923  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b928  nop
0x18003b929  mov     rcx, [rbp+pv]; pv
0x18003b92d  mov     [rbp+pv], 0
0x18003b935  test    rcx, rcx
0x18003b938  jz      short loc_18003B940
0x18003b93a  call    cs:__imp_CoTaskMemFree
0x18003b940  mov     eax, ebx
0x18003b942  jmp     loc_18003B9EB
0x18003b947  mov     edi, dword ptr [rbp+arg_10]
0x18003b94a  mov     ecx, edi
0x18003b94c  add     rcx, rcx; cb
0x18003b94f  call    cs:__imp_CoTaskMemAlloc
0x18003b955  mov     rbx, rax
0x18003b958  mov     [rbp+arg_10], rax
0x18003b95c  test    rax, rax
0x18003b95f  jnz     short loc_18003B987
0x18003b961  mov     rcx, [rbp+18h]; this
0x18003b965  mov     ebx, 8007000Eh
0x18003b96a  mov     r9d, ebx; char *
0x18003b96d  lea     r8, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003b974  lea     edx, [rax+66h]; void *
0x18003b977  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b97c  lea     rcx, [rbp+arg_10]
0x18003b980  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18003b985  jmp     short loc_18003B929
0x18003b987  mov     [rsp+50h+cchWideChar], edi; cchWideChar
0x18003b98b  mov     [rsp+50h+lpWideCharStr], rbx; lpWideCharStr
0x18003b990  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18003b994  mov     r8, [rbp+pv]; lpMultiByteStr
0x18003b998  xor     edx, edx; dwFlags
0x18003b99a  xor     ecx, ecx; CodePage
0x18003b99c  call    cs:__imp_MultiByteToWideChar
0x18003b9a2  test    eax, eax
0x18003b9a4  jnz     short loc_18003B9BD
0x18003b9a6  mov     rcx, [rbp+18h]; this
0x18003b9aa  lea     r8, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003b9b1  lea     edx, [rax+67h]; void *
0x18003b9b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b9b9  mov     ebx, eax
0x18003b9bb  jmp     short loc_18003B97C
0x18003b9bd  mov     [rbp+arg_10], 0
0x18003b9c5  mov     [rsi], rbx
0x18003b9c8  lea     rcx, [rbp+arg_10]
0x18003b9cc  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18003b9d1  nop
0x18003b9d2  mov     rcx, [rbp+pv]; pv
0x18003b9d6  mov     [rbp+pv], 0
0x18003b9de  test    rcx, rcx
0x18003b9e1  jz      short loc_18003B9E9
0x18003b9e3  call    cs:__imp_CoTaskMemFree
0x18003b9e9  xor     eax, eax
0x18003b9eb  mov     rbx, [rsp+50h+arg_0]
0x18003b9f0  add     rsp, 50h
0x18003b9f4  pop     rdi
0x18003b9f5  pop     rsi
0x18003b9f6  pop     rbp
0x18003b9f7  retn
```
