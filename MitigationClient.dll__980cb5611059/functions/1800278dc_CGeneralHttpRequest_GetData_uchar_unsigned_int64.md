# CGeneralHttpRequest::GetData(uchar * *,unsigned __int64 *)

- ea: `0x1800278dc`
- end: `0x180027ac3`
- name: `?GetData@CGeneralHttpRequest@@IEAAJPEAPEAEPEA_K@Z`
- size: `487`
- prototype: `__int64 __fastcall(CGeneralHttpRequest *__hidden this, unsigned __int8 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027660`
- `0x180027acc`

## callees

- `0x18001208c`
- `0x180016250`
- `0x180016c30`
- `0x18001fab8`
- `0x18002545c`
- `0x1800271bc`
- `0x1800278dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800279e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800279e1`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18002794b`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18002794b`
- `WINHTTP!WinHttpReadData` at `0x180027a04`
- `WINHTTP!WinHttpReadData` at `0x180027a04`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CGeneralHttpRequest::GetData(HINTERNET *this, unsigned __int8 **a2, unsigned __int64 *a3)
{
  unsigned __int64 v6; // rsi
  int v7; // eax
  int Error; // ebx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  unsigned __int64 v11; // rdi
  char *v12; // r14
  DWORD v13; // r8d
  int v14; // eax
  unsigned int v15; // edx
  void *v16; // rcx
  unsigned __int64 v17; // r9
  int v18; // eax
  DWORD v19; // ecx
  int v21; // [rsp+20h] [rbp-20h]
  void *v22; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  DWORD dwNumberOfBytesAvailable; // [rsp+88h] [rbp+48h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+90h] [rbp+50h] BYREF
  void *v27; // [rsp+98h] [rbp+58h] BYREF

  *a2 = 0;
  *a3 = 0;
  dwNumberOfBytesRead = 0;
  v27 = 0;
  v6 = 1024;
  v23 = 1024;
  v7 = CTCoAllocPolicy::Alloc(this, 1u, 0x400u, &v27);
  Error = v7;
  if ( v7 >= 0 )
  {
    v11 = 0;
    v12 = (char *)v27;
    while ( 1 )
    {
      dwNumberOfBytesAvailable = 0;
      if ( WinHttpQueryDataAvailable(this[7], &dwNumberOfBytesAvailable) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
          v10 = 235;
          goto LABEL_26;
        }
      }
      v13 = dwNumberOfBytesAvailable;
      if ( dwNumberOfBytesAvailable )
      {
        if ( v11 + dwNumberOfBytesAvailable < v11 )
        {
          Error = -2147024362;
          v10 = 240;
LABEL_26:
          v9 = (unsigned int)Error;
          goto LABEL_27;
        }
        if ( v11 + dwNumberOfBytesAvailable > v6 )
        {
          do
          {
            v14 = ULongLongMult(v6, 2u, &v23);
            Error = v14;
            v6 = v23;
            if ( v14 < 0 )
            {
              v9 = (unsigned int)v14;
              v10 = 249;
              goto LABEL_27;
            }
          }
          while ( v23 < v17 );
          v22 = 0;
          Error = CTCoAllocPolicy::Realloc(v16, v15, v12, v23, &v22);
          if ( Error >= 0 )
          {
            v12 = (char *)v22;
            v22 = 0;
            CoTaskMemFree(0);
            v27 = v12;
            CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v22);
            v13 = dwNumberOfBytesAvailable;
            goto LABEL_14;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFD,
            (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\generalhttprequest.cpp",
            (const char *)(unsigned int)Error,
            v21);
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v22);
          goto LABEL_28;
        }
LABEL_14:
        if ( WinHttpReadData(this[7], &v12[v11], v13, &dwNumberOfBytesRead) )
        {
          Error = 0;
        }
        else
        {
          v18 = ResultFromKnownLastError();
          Error = v18;
          if ( v18 < 0 )
          {
            v9 = (unsigned int)v18;
            v10 = 267;
            goto LABEL_27;
          }
        }
        v19 = dwNumberOfBytesRead;
        v11 += dwNumberOfBytesRead;
      }
      else
      {
        v19 = 0;
        dwNumberOfBytesRead = 0;
      }
      if ( !v19 )
      {
        v27 = 0;
        *a2 = (unsigned __int8 *)v12;
        *a3 = v11;
        goto LABEL_28;
      }
    }
  }
  v9 = (unsigned int)v7;
  v10 = 229;
LABEL_27:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\generalhttprequest.cpp",
    (const char *)v9,
    v21);
LABEL_28:
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v27);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800278dc  mov     [rsp-38h+arg_0], rbx
0x1800278e1  push    rbp
0x1800278e2  push    rsi
0x1800278e3  push    rdi
0x1800278e4  push    r12
0x1800278e6  push    r13
0x1800278e8  push    r14
0x1800278ea  push    r15
0x1800278ec  mov     rbp, rsp
0x1800278ef  sub     rsp, 40h
0x1800278f3  mov     r15, r8
0x1800278f6  mov     r12, rdx
0x1800278f9  mov     r13, rcx
0x1800278fc  xor     eax, eax
0x1800278fe  mov     [rdx], rax
0x180027901  mov     [r8], rax
0x180027904  mov     [rbp+dwNumberOfBytesRead], eax
0x180027907  mov     [rbp+arg_18], rax
0x18002790b  mov     esi, 400h
0x180027910  mov     [rbp+var_8], rsi
0x180027914  lea     r9, [rbp+arg_18]; void **
0x180027918  mov     r8d, esi; unsigned __int64
0x18002791b  lea     edx, [rax+1]; unsigned int
0x18002791e  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180027923  mov     ebx, eax
0x180027925  test    eax, eax
0x180027927  jns     short loc_180027936
0x180027929  mov     r9d, eax
0x18002792c  mov     edx, 0E5h
0x180027931  jmp     loc_180027A8F
0x180027936  xor     edi, edi
0x180027938  mov     r14, [rbp+arg_18]
0x18002793c  mov     [rbp+dwNumberOfBytesAvailable], 0
0x180027943  lea     rdx, [rbp+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x180027947  mov     rcx, [r13+38h]; hRequest
0x18002794b  call    cs:__imp_WinHttpQueryDataAvailable
0x180027951  test    eax, eax
0x180027953  jz      short loc_180027959
0x180027955  xor     ebx, ebx
0x180027957  jmp     short loc_180027968
0x180027959  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002795e  mov     ebx, eax
0x180027960  test    eax, eax
0x180027962  js      loc_180027A87
0x180027968  mov     r8d, [rbp+dwNumberOfBytesAvailable]
0x18002796c  test    r8d, r8d
0x18002796f  jz      loc_180027A25
0x180027975  lea     r9, [rdi+r8]
0x180027979  cmp     r9, rdi
0x18002797c  jb      loc_180027A7B
0x180027982  cmp     r9, rsi
0x180027985  jbe     short loc_1800279F8
0x180027987  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18002798b  mov     edx, 2; unsigned __int64
0x180027990  mov     rcx, rsi; unsigned __int64
0x180027993  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180027998  mov     ebx, eax
0x18002799a  mov     rsi, [rbp+var_8]
0x18002799e  test    eax, eax
0x1800279a0  js      loc_180027A67
0x1800279a6  cmp     rsi, r9
0x1800279a9  jb      short loc_180027987
0x1800279ab  test    eax, eax
0x1800279ad  js      loc_180027A67
0x1800279b3  mov     [rbp+var_10], 0
0x1800279bb  lea     rax, [rbp+var_10]
0x1800279bf  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800279c4  mov     r9, rsi; unsigned __int64
0x1800279c7  mov     r8, r14; void *
0x1800279ca  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x1800279cf  mov     ebx, eax
0x1800279d1  xor     eax, eax
0x1800279d3  test    ebx, ebx
0x1800279d5  js      short loc_180027A43
0x1800279d7  mov     r14, [rbp+var_10]
0x1800279db  mov     [rbp+var_10], rax
0x1800279df  xor     ecx, ecx; pv
0x1800279e1  call    cs:__imp_CoTaskMemFree
0x1800279e7  mov     [rbp+arg_18], r14
0x1800279eb  lea     rcx, [rbp+var_10]
0x1800279ef  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800279f4  mov     r8d, [rbp+dwNumberOfBytesAvailable]; dwNumberOfBytesToRead
0x1800279f8  lea     rdx, [r14+rdi]; lpBuffer
0x1800279fc  lea     r9, [rbp+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x180027a00  mov     rcx, [r13+38h]; hRequest
0x180027a04  call    cs:__imp_WinHttpReadData
0x180027a0a  test    eax, eax
0x180027a0c  jz      short loc_180027A12
0x180027a0e  xor     ebx, ebx
0x180027a10  jmp     short loc_180027A1D
0x180027a12  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180027a17  mov     ebx, eax
0x180027a19  test    eax, eax
0x180027a1b  js      short loc_180027A71
0x180027a1d  mov     ecx, [rbp+dwNumberOfBytesRead]
0x180027a20  add     rdi, rcx
0x180027a23  jmp     short loc_180027A2A
0x180027a25  xor     ecx, ecx
0x180027a27  mov     [rbp+dwNumberOfBytesRead], ecx
0x180027a2a  test    ecx, ecx
0x180027a2c  jnz     loc_18002793C
0x180027a32  mov     [rbp+arg_18], 0
0x180027a3a  mov     [r12], r14
0x180027a3e  mov     [r15], rdi
0x180027a41  jmp     short loc_180027AA0
0x180027a43  mov     rcx, [rbp+38h]; this
0x180027a47  mov     r9d, ebx; char *
0x180027a4a  lea     r8, aOnecoreBaseDia_9; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180027a51  mov     edx, 0FDh; void *
0x180027a56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a5b  nop
0x180027a5c  lea     rcx, [rbp+var_10]
0x180027a60  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180027a65  jmp     short loc_180027AA0
0x180027a67  mov     r9d, eax
0x180027a6a  mov     edx, 0F9h
0x180027a6f  jmp     short loc_180027A8F
0x180027a71  mov     r9d, eax
0x180027a74  mov     edx, 10Bh
0x180027a79  jmp     short loc_180027A8F
0x180027a7b  mov     ebx, 80070216h
0x180027a80  mov     edx, 0F0h
0x180027a85  jmp     short loc_180027A8C
0x180027a87  mov     edx, 0EBh; void *
0x180027a8c  mov     r9d, ebx; char *
0x180027a8f  lea     r8, aOnecoreBaseDia_9; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180027a96  mov     rcx, [rbp+38h]; this
0x180027a9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a9f  nop
0x180027aa0  lea     rcx, [rbp+arg_18]
0x180027aa4  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180027aa9  mov     eax, ebx
0x180027aab  mov     rbx, [rsp+40h+arg_0]
0x180027ab3  add     rsp, 40h
0x180027ab7  pop     r15
0x180027ab9  pop     r14
0x180027abb  pop     r13
0x180027abd  pop     r12
0x180027abf  pop     rdi
0x180027ac0  pop     rsi
0x180027ac1  pop     rbp
0x180027ac2  retn
```
