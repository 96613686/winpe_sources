# CGeneralHttpRequest::GetData(uchar * *,unsigned __int64 *)

- ea: `0x1800ae4e4`
- end: `0x1800ae6da`
- name: `?GetData@CGeneralHttpRequest@@IEAAJPEAPEAEPEA_K@Z`
- size: `502`
- prototype: `__int64 __fastcall(CGeneralHttpRequest *__hidden this, unsigned __int8 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ae6e0`

## callees

- `0x18000cc8c`
- `0x1800141d0`
- `0x180016898`
- `0x18001b2c0`
- `0x1800254ac`
- `0x18002f830`
- `0x1800ae4e4`
- `0x1800aec80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae5f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae5f8`
- `WINHTTP!WinHttpReadData` at `0x1800ae61b`
- `WINHTTP!WinHttpReadData` at `0x1800ae61b`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800ae553`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800ae553`

## string_xrefs

- `0x1800ae661`: `onecore\base\flighting\flightsettings\broker\libs\common\generalhttprequest.cpp`
- `0x1800ae6a6`: `onecore\base\flighting\flightsettings\broker\libs\common\generalhttprequest.cpp`

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
  CGeneralHttpRequest *v13; // rcx
  DWORD v14; // r8d
  int v15; // eax
  unsigned int v16; // edx
  void *v17; // rcx
  unsigned __int64 v18; // r9
  int v19; // eax
  DWORD v20; // ecx
  int v22; // [rsp+20h] [rbp-20h]
  void *v23; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v24; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  DWORD dwNumberOfBytesAvailable; // [rsp+88h] [rbp+48h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+90h] [rbp+50h] BYREF
  void *v28; // [rsp+98h] [rbp+58h] BYREF

  *a2 = 0;
  *a3 = 0;
  dwNumberOfBytesRead = 0;
  v28 = 0;
  v6 = 1024;
  v24 = 1024;
  v7 = CTCoAllocPolicy::Alloc(this, 1u, 0x400u, &v28);
  Error = v7;
  if ( v7 >= 0 )
  {
    v11 = 0;
    v12 = (char *)v28;
    while ( 1 )
    {
      dwNumberOfBytesAvailable = 0;
      if ( WinHttpQueryDataAvailable(this[6], &dwNumberOfBytesAvailable) )
        Error = 0;
      else
        Error = ResultFromKnownLastError();
      if ( CGeneralHttpRequest::IsExpectedHresult(v13, Error) )
        goto LABEL_30;
      if ( Error < 0 )
        break;
      v14 = dwNumberOfBytesAvailable;
      if ( dwNumberOfBytesAvailable )
      {
        if ( v11 + dwNumberOfBytesAvailable < v11 )
        {
          Error = -2147024362;
          v10 = 299;
LABEL_28:
          v9 = (unsigned int)Error;
          goto LABEL_29;
        }
        if ( v11 + dwNumberOfBytesAvailable > v6 )
        {
          do
          {
            v15 = ULongLongMult(v6, 2u, &v24);
            Error = v15;
            v6 = v24;
            if ( v15 < 0 )
            {
              v9 = (unsigned int)v15;
              v10 = 308;
              goto LABEL_29;
            }
          }
          while ( v24 < v18 );
          v23 = 0;
          Error = CTCoAllocPolicy::Realloc(v17, v16, v12, v24, &v23);
          if ( Error >= 0 )
          {
            v12 = (char *)v23;
            v23 = 0;
            CoTaskMemFree(0);
            v28 = v12;
            CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v23);
            v14 = dwNumberOfBytesAvailable;
            goto LABEL_16;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x138,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\generalhttprequest.cpp",
            (const char *)(unsigned int)Error,
            v22);
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v23);
          goto LABEL_30;
        }
LABEL_16:
        if ( WinHttpReadData(this[6], &v12[v11], v14, &dwNumberOfBytesRead) )
        {
          Error = 0;
        }
        else
        {
          v19 = ResultFromKnownLastError();
          Error = v19;
          if ( v19 < 0 )
          {
            v9 = (unsigned int)v19;
            v10 = 326;
            goto LABEL_29;
          }
        }
        v20 = dwNumberOfBytesRead;
        v11 += dwNumberOfBytesRead;
      }
      else
      {
        v20 = 0;
        dwNumberOfBytesRead = 0;
      }
      if ( !v20 )
      {
        v28 = 0;
        *a2 = (unsigned __int8 *)v12;
        *a3 = v11;
        goto LABEL_30;
      }
    }
    v10 = 293;
    goto LABEL_28;
  }
  v9 = (unsigned int)v7;
  v10 = 286;
LABEL_29:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\generalhttprequest.cpp",
    (const char *)v9,
    v22);
LABEL_30:
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v28);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800ae4e4  mov     [rsp-38h+arg_0], rbx
0x1800ae4e9  push    rbp
0x1800ae4ea  push    rsi
0x1800ae4eb  push    rdi
0x1800ae4ec  push    r12
0x1800ae4ee  push    r13
0x1800ae4f0  push    r14
0x1800ae4f2  push    r15
0x1800ae4f4  mov     rbp, rsp
0x1800ae4f7  sub     rsp, 40h
0x1800ae4fb  mov     r15, r8
0x1800ae4fe  mov     r12, rdx
0x1800ae501  mov     r13, rcx
0x1800ae504  xor     eax, eax
0x1800ae506  mov     [rdx], rax
0x1800ae509  mov     [r8], rax
0x1800ae50c  mov     [rbp+dwNumberOfBytesRead], eax
0x1800ae50f  mov     [rbp+arg_18], rax
0x1800ae513  mov     esi, 400h
0x1800ae518  mov     [rbp+var_8], rsi
0x1800ae51c  lea     r9, [rbp+arg_18]; void **
0x1800ae520  mov     r8d, esi; unsigned __int64
0x1800ae523  lea     edx, [rax+1]; unsigned int
0x1800ae526  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800ae52b  mov     ebx, eax
0x1800ae52d  test    eax, eax
0x1800ae52f  jns     short loc_1800AE53E
0x1800ae531  mov     r9d, eax
0x1800ae534  mov     edx, 11Eh
0x1800ae539  jmp     loc_1800AE6A6
0x1800ae53e  xor     edi, edi
0x1800ae540  mov     r14, [rbp+arg_18]
0x1800ae544  mov     [rbp+dwNumberOfBytesAvailable], 0
0x1800ae54b  lea     rdx, [rbp+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1800ae54f  mov     rcx, [r13+30h]; hRequest
0x1800ae553  call    cs:__imp_WinHttpQueryDataAvailable
0x1800ae559  test    eax, eax
0x1800ae55b  jz      short loc_1800AE561
0x1800ae55d  xor     ebx, ebx
0x1800ae55f  jmp     short loc_1800AE568
0x1800ae561  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ae566  mov     ebx, eax
0x1800ae568  mov     edx, ebx; int
0x1800ae56a  call    ?IsExpectedHresult@CGeneralHttpRequest@@AEAA_NJ@Z; CGeneralHttpRequest::IsExpectedHresult(long)
0x1800ae56f  test    al, al
0x1800ae571  jnz     loc_1800AE6B7
0x1800ae577  test    ebx, ebx
0x1800ae579  js      loc_1800AE69E
0x1800ae57f  mov     r8d, [rbp+dwNumberOfBytesAvailable]
0x1800ae583  test    r8d, r8d
0x1800ae586  jz      loc_1800AE63C
0x1800ae58c  lea     r9, [rdi+r8]
0x1800ae590  cmp     r9, rdi
0x1800ae593  jb      loc_1800AE692
0x1800ae599  cmp     r9, rsi
0x1800ae59c  jbe     short loc_1800AE60F
0x1800ae59e  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800ae5a2  mov     edx, 2; unsigned __int64
0x1800ae5a7  mov     rcx, rsi; unsigned __int64
0x1800ae5aa  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800ae5af  mov     ebx, eax
0x1800ae5b1  mov     rsi, [rbp+var_8]
0x1800ae5b5  test    eax, eax
0x1800ae5b7  js      loc_1800AE67E
0x1800ae5bd  cmp     rsi, r9
0x1800ae5c0  jb      short loc_1800AE59E
0x1800ae5c2  test    eax, eax
0x1800ae5c4  js      loc_1800AE67E
0x1800ae5ca  mov     [rbp+var_10], 0
0x1800ae5d2  lea     rax, [rbp+var_10]
0x1800ae5d6  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800ae5db  mov     r9, rsi; unsigned __int64
0x1800ae5de  mov     r8, r14; void *
0x1800ae5e1  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x1800ae5e6  mov     ebx, eax
0x1800ae5e8  xor     eax, eax
0x1800ae5ea  test    ebx, ebx
0x1800ae5ec  js      short loc_1800AE65A
0x1800ae5ee  mov     r14, [rbp+var_10]
0x1800ae5f2  mov     [rbp+var_10], rax
0x1800ae5f6  xor     ecx, ecx; pv
0x1800ae5f8  call    cs:__imp_CoTaskMemFree
0x1800ae5fe  mov     [rbp+arg_18], r14
0x1800ae602  lea     rcx, [rbp+var_10]
0x1800ae606  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800ae60b  mov     r8d, [rbp+dwNumberOfBytesAvailable]; dwNumberOfBytesToRead
0x1800ae60f  lea     rdx, [r14+rdi]; lpBuffer
0x1800ae613  lea     r9, [rbp+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1800ae617  mov     rcx, [r13+30h]; hRequest
0x1800ae61b  call    cs:__imp_WinHttpReadData
0x1800ae621  test    eax, eax
0x1800ae623  jz      short loc_1800AE629
0x1800ae625  xor     ebx, ebx
0x1800ae627  jmp     short loc_1800AE634
0x1800ae629  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ae62e  mov     ebx, eax
0x1800ae630  test    eax, eax
0x1800ae632  js      short loc_1800AE688
0x1800ae634  mov     ecx, [rbp+dwNumberOfBytesRead]
0x1800ae637  add     rdi, rcx
0x1800ae63a  jmp     short loc_1800AE641
0x1800ae63c  xor     ecx, ecx
0x1800ae63e  mov     [rbp+dwNumberOfBytesRead], ecx
0x1800ae641  test    ecx, ecx
0x1800ae643  jnz     loc_1800AE544
0x1800ae649  mov     [rbp+arg_18], 0
0x1800ae651  mov     [r12], r14
0x1800ae655  mov     [r15], rdi
0x1800ae658  jmp     short loc_1800AE6B7
0x1800ae65a  mov     rcx, [rbp+38h]; this
0x1800ae65e  mov     r9d, ebx; char *
0x1800ae661  lea     r8, aOnecoreBaseFli_56; "onecore\\base\\flighting\\flightsetting"...
0x1800ae668  mov     edx, 138h; void *
0x1800ae66d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae672  nop
0x1800ae673  lea     rcx, [rbp+var_10]
0x1800ae677  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800ae67c  jmp     short loc_1800AE6B7
0x1800ae67e  mov     r9d, eax
0x1800ae681  mov     edx, 134h
0x1800ae686  jmp     short loc_1800AE6A6
0x1800ae688  mov     r9d, eax
0x1800ae68b  mov     edx, 146h
0x1800ae690  jmp     short loc_1800AE6A6
0x1800ae692  mov     ebx, 80070216h
0x1800ae697  mov     edx, 12Bh
0x1800ae69c  jmp     short loc_1800AE6A3
0x1800ae69e  mov     edx, 125h; void *
0x1800ae6a3  mov     r9d, ebx; char *
0x1800ae6a6  lea     r8, aOnecoreBaseFli_56; "onecore\\base\\flighting\\flightsetting"...
0x1800ae6ad  mov     rcx, [rbp+38h]; this
0x1800ae6b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae6b6  nop
0x1800ae6b7  lea     rcx, [rbp+arg_18]
0x1800ae6bb  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800ae6c0  mov     eax, ebx
0x1800ae6c2  mov     rbx, [rsp+40h+arg_0]
0x1800ae6ca  add     rsp, 40h
0x1800ae6ce  pop     r15
0x1800ae6d0  pop     r14
0x1800ae6d2  pop     r13
0x1800ae6d4  pop     r12
0x1800ae6d6  pop     rdi
0x1800ae6d7  pop     rsi
0x1800ae6d8  pop     rbp
0x1800ae6d9  retn
```
