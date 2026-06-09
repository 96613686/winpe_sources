# CEcsWinHttpClient::GetResponseData(IStream * *,unsigned __int64 *)

- ea: `0x18006e330`
- end: `0x18006e61b`
- name: `?GetResponseData@CEcsWinHttpClient@@UEAAXPEAPEAUIStream@@PEA_K@Z`
- size: `747`
- prototype: `void __fastcall(CEcsWinHttpClient *__hidden this, struct IStream **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180002f98`
- `0x180003604`
- `0x18000444c`
- `0x180007b9c`
- `0x180007e10`
- `0x180009188`
- `0x180011314`
- `0x1800155b8`
- `0x18006e22c`
- `0x18006e330`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006e3f6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006e3f6`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18006e453`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18006e453`
- `WINHTTP!WinHttpReadData` at `0x18006e498`
- `WINHTTP!WinHttpReadData` at `0x18006e498`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CEcsWinHttpClient::GetResponseData(CEcsWinHttpClient *this, struct IStream **a2, unsigned __int64 *a3)
{
  _BYTE *v6; // rax
  char v7; // cl
  void *v8; // rax
  HRESULT v9; // eax
  unsigned __int64 v10; // rbx
  void *RequestHandle; // rax
  DWORD v12; // esi
  void *v13; // rax
  int v14; // eax
  int v15; // eax
  struct IStream *v16; // rax
  DWORD dwNumberOfBytesAvailable; // [rsp+30h] [rbp-40h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-38h] BYREF
  LPVOID lpBuffer; // [rsp+40h] [rbp-30h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-28h] BYREF
  int v21; // [rsp+4Ch] [rbp-24h]
  char v22; // [rsp+50h] [rbp-20h]
  const char *v23; // [rsp+58h] [rbp-18h]
  __int64 v24; // [rsp+60h] [rbp-10h]
  HRESULT pExceptionObject; // [rsp+B8h] [rbp+48h] BYREF
  int v26; // [rsp+C0h] [rbp+50h] BYREF
  int v27; // [rsp+C8h] [rbp+58h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, &WPP_13baba31ff4d3f580777c125170b76f8_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (v6[68] & 8) == 0 || (v7 = 1, v6[65] < 6u) )
    v7 = 0;
  LastFailureAsHRESULT = 0;
  v21 = 566;
  v22 = v7;
  v23 = "CEcsWinHttpClient::GetResponseData";
  v24 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  ppstm = 0;
  v8 = operator new[](0x200000u);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&lpBuffer, (__int64)v8);
  dwNumberOfBytesAvailable = 0;
  v9 = CreateStreamOnHGlobal(0, 1, &ppstm);
  LastFailureAsHRESULT = v9;
  if ( v9 < 0 )
  {
    HIWORD(v21) = 576;
    pExceptionObject = v9;
    throw (long *)&pExceptionObject;
  }
  v10 = 0;
  LOWORD(v21) = 576;
  do
  {
    pExceptionObject = 0;
    v26 = 0;
    dwNumberOfBytesAvailable = 0;
    LastFailureAsHRESULT = v9;
    RequestHandle = CEcsWinHttpClient::GetRequestHandle(this);
    if ( !WinHttpQueryDataAvailable(RequestHandle, &dwNumberOfBytesAvailable) )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v21) = 585;
      v27 = LastFailureAsHRESULT;
      throw (long *)&v27;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v21) = 585;
    v12 = dwNumberOfBytesAvailable;
    if ( !dwNumberOfBytesAvailable )
      break;
    if ( dwNumberOfBytesAvailable > 0x200000 )
      v12 = 0x200000;
    LastFailureAsHRESULT = 0;
    v13 = CEcsWinHttpClient::GetRequestHandle(this);
    if ( !WinHttpReadData(v13, lpBuffer, v12, (LPDWORD)&pExceptionObject) )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v21) = 592;
      v27 = LastFailureAsHRESULT;
      throw (long *)&v27;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v21) = 592;
    v14 = (*(__int64 (__fastcall **)(LPSTREAM, LPVOID, _QWORD, int *))(*(_QWORD *)ppstm + 32LL))(
            ppstm,
            lpBuffer,
            (unsigned int)pExceptionObject,
            &v26);
    LastFailureAsHRESULT = v14;
    if ( v14 < 0 )
    {
      HIWORD(v21) = 595;
      v27 = v14;
      throw (long *)&v27;
    }
    LOWORD(v21) = 595;
    if ( v10 + (unsigned int)pExceptionObject < v10 )
    {
      LastFailureAsHRESULT = -2147024362;
      HIWORD(v21) = 598;
      v27 = -2147024362;
      throw (long *)&v27;
    }
    v9 = 0;
    LastFailureAsHRESULT = 0;
    LOWORD(v21) = 598;
    v10 += (unsigned int)pExceptionObject;
  }
  while ( dwNumberOfBytesAvailable );
  v15 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
  LastFailureAsHRESULT = v15;
  if ( v15 < 0 )
  {
    HIWORD(v21) = 605;
    pExceptionObject = v15;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v21) = 605;
  v16 = ppstm;
  ppstm = 0;
  *a2 = v16;
  *a3 = v10;
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpBuffer);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppstm);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
}

```

## disassembly

```asm
0x18006e330  mov     [rsp-38h+arg_0], rbx
0x18006e335  push    rbp
0x18006e336  push    rsi
0x18006e337  push    rdi
0x18006e338  push    r12
0x18006e33a  push    r13
0x18006e33c  push    r14
0x18006e33e  push    r15
0x18006e340  mov     rbp, rsp
0x18006e343  sub     rsp, 70h
0x18006e347  mov     rdi, r8
0x18006e34a  mov     r14, rdx
0x18006e34d  mov     r15, rcx
0x18006e350  lea     rcx, WPP_GLOBAL_Control
0x18006e357  mov     rax, cs:WPP_GLOBAL_Control
0x18006e35e  cmp     rax, rcx
0x18006e361  jz      short loc_18006E38B
0x18006e363  test    byte ptr [rax+44h], 8
0x18006e367  jz      short loc_18006E38B
0x18006e369  cmp     byte ptr [rax+41h], 6
0x18006e36d  jb      short loc_18006E38B
0x18006e36f  mov     edx, 15h
0x18006e374  lea     r8, WPP_13baba31ff4d3f580777c125170b76f8_Traceguids
0x18006e37b  mov     rcx, [rax+38h]
0x18006e37f  call    WPP_SF_
0x18006e384  mov     rax, cs:WPP_GLOBAL_Control
0x18006e38b  xor     r12d, r12d
0x18006e38e  test    byte ptr [rax+44h], 8
0x18006e392  jz      short loc_18006E39C
0x18006e394  cmp     byte ptr [rax+41h], 6
0x18006e398  mov     cl, 1
0x18006e39a  jnb     short loc_18006E39F
0x18006e39c  mov     cl, r12b
0x18006e39f  mov     [rbp+var_28], r12d
0x18006e3a3  mov     [rbp+var_24], 236h
0x18006e3aa  mov     [rbp+var_20], cl
0x18006e3ad  lea     rax, aCecswinhttpcli_24; "CEcsWinHttpClient::GetResponseData"
0x18006e3b4  mov     [rbp+var_18], rax
0x18006e3b8  mov     [rbp+var_10], r12
0x18006e3bc  test    r14, r14
0x18006e3bf  jz      short loc_18006E3C4
0x18006e3c1  mov     [r14], r12
0x18006e3c4  test    rdi, rdi
0x18006e3c7  jz      short loc_18006E3CC
0x18006e3c9  mov     [rdi], r12
0x18006e3cc  mov     [rbp+ppstm], r12
0x18006e3d0  mov     ecx, 200000h; unsigned __int64
0x18006e3d5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006e3da  mov     rdx, rax
0x18006e3dd  lea     rcx, [rbp+lpBuffer]
0x18006e3e1  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18006e3e6  nop
0x18006e3e7  mov     [rbp+dwNumberOfBytesAvailable], r12d
0x18006e3eb  lea     r8, [rbp+ppstm]; ppstm
0x18006e3ef  mov     edx, 1; fDeleteOnRelease
0x18006e3f4  xor     ecx, ecx; hGlobal
0x18006e3f6  call    cs:__imp_CreateStreamOnHGlobal
0x18006e3fc  mov     [rbp+var_28], eax
0x18006e3ff  mov     [rbp+var_28], eax
0x18006e402  mov     ecx, 240h
0x18006e407  test    eax, eax
0x18006e409  jns     short loc_18006E423
0x18006e40b  mov     word ptr [rbp+var_24+2], cx
0x18006e40f  mov     [rbp+pExceptionObject], eax
0x18006e412  lea     rdx, _TI1J; pThrowInfo
0x18006e419  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18006e41d  call    _CxxThrowException_0
0x18006e423  mov     rbx, r12
0x18006e426  mov     word ptr [rbp+var_24], cx
0x18006e42a  mov     r13d, 256h
0x18006e430  mov     esi, 249h
0x18006e435  mov     [rbp+pExceptionObject], r12d
0x18006e439  mov     [rbp+arg_10], r12d
0x18006e43d  mov     [rbp+dwNumberOfBytesAvailable], r12d
0x18006e441  mov     [rbp+var_28], eax
0x18006e444  mov     rcx, r15; this
0x18006e447  call    ?GetRequestHandle@CEcsWinHttpClient@@AEAAPEAXXZ; CEcsWinHttpClient::GetRequestHandle(void)
0x18006e44c  mov     rcx, rax; hRequest
0x18006e44f  lea     rdx, [rbp+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x18006e453  call    cs:__imp_WinHttpQueryDataAvailable
0x18006e459  test    eax, eax
0x18006e45b  jz      loc_18006E5FA
0x18006e461  mov     [rbp+var_28], r12d
0x18006e465  mov     word ptr [rbp+var_24], si
0x18006e469  mov     esi, [rbp+dwNumberOfBytesAvailable]
0x18006e46c  test    esi, esi
0x18006e46e  jz      loc_18006E50D
0x18006e474  mov     eax, 200000h
0x18006e479  cmp     esi, eax
0x18006e47b  cmova   esi, eax
0x18006e47e  mov     [rbp+var_28], r12d
0x18006e482  mov     rcx, r15; this
0x18006e485  call    ?GetRequestHandle@CEcsWinHttpClient@@AEAAPEAXXZ; CEcsWinHttpClient::GetRequestHandle(void)
0x18006e48a  lea     r9, [rbp+pExceptionObject]; lpdwNumberOfBytesRead
0x18006e48e  mov     r8d, esi; dwNumberOfBytesToRead
0x18006e491  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x18006e495  mov     rcx, rax; hRequest
0x18006e498  call    cs:__imp_WinHttpReadData
0x18006e49e  test    eax, eax
0x18006e4a0  jz      loc_18006E58E
0x18006e4a6  mov     [rbp+var_28], r12d
0x18006e4aa  mov     eax, 250h
0x18006e4af  mov     word ptr [rbp+var_24], ax
0x18006e4b3  mov     rcx, [rbp+ppstm]
0x18006e4b7  mov     rax, [rcx]
0x18006e4ba  lea     r9, [rbp+arg_10]
0x18006e4be  mov     r8d, [rbp+pExceptionObject]
0x18006e4c2  mov     rdx, [rbp+lpBuffer]
0x18006e4c6  mov     rax, [rax+20h]
0x18006e4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e4cf  mov     [rbp+var_28], eax
0x18006e4d2  mov     [rbp+var_28], eax
0x18006e4d5  test    eax, eax
0x18006e4d7  js      loc_18006E571
0x18006e4dd  mov     eax, 253h
0x18006e4e2  mov     word ptr [rbp+var_24], ax
0x18006e4e6  mov     ecx, [rbp+pExceptionObject]
0x18006e4e9  add     rcx, rbx
0x18006e4ec  cmp     rcx, rbx
0x18006e4ef  jb      short loc_18006E54D
0x18006e4f1  mov     [rbp+var_28], r12d
0x18006e4f5  mov     eax, r12d
0x18006e4f8  mov     [rbp+var_28], eax
0x18006e4fb  mov     word ptr [rbp+var_24], r13w
0x18006e500  mov     rbx, rcx
0x18006e503  cmp     [rbp+dwNumberOfBytesAvailable], r12d
0x18006e507  ja      loc_18006E430
0x18006e50d  mov     rcx, [rbp+ppstm]
0x18006e511  mov     rdx, r12
0x18006e514  mov     rax, [rcx]
0x18006e517  xor     r9d, r9d
0x18006e51a  xor     r8d, r8d
0x18006e51d  mov     rax, [rax+28h]
0x18006e521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e526  mov     [rbp+var_28], eax
0x18006e529  mov     [rbp+var_28], eax
0x18006e52c  mov     ecx, 25Dh
0x18006e531  test    eax, eax
0x18006e533  jns     short loc_18006E5B3
0x18006e535  mov     word ptr [rbp+var_24+2], cx
0x18006e539  mov     [rbp+pExceptionObject], eax
0x18006e53c  lea     rdx, _TI1J; pThrowInfo
0x18006e543  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18006e547  call    _CxxThrowException_0
0x18006e54d  mov     eax, 80070216h
0x18006e552  mov     [rbp+var_28], eax
0x18006e555  mov     [rbp+var_28], eax
0x18006e558  mov     word ptr [rbp+var_24+2], r13w
0x18006e55d  mov     [rbp+arg_18], eax
0x18006e560  lea     rdx, _TI1J; pThrowInfo
0x18006e567  lea     rcx, [rbp+arg_18]; pExceptionObject
0x18006e56b  call    _CxxThrowException_0
0x18006e571  mov     ecx, 253h
0x18006e576  mov     word ptr [rbp+var_24+2], cx
0x18006e57a  mov     [rbp+arg_18], eax
0x18006e57d  lea     rdx, _TI1J; pThrowInfo
0x18006e584  lea     rcx, [rbp+arg_18]; pExceptionObject
0x18006e588  call    _CxxThrowException_0
0x18006e58e  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18006e593  mov     [rbp+var_28], eax
0x18006e596  mov     ecx, 250h
0x18006e59b  mov     word ptr [rbp+var_24+2], cx
0x18006e59f  mov     [rbp+arg_18], eax
0x18006e5a2  lea     rdx, _TI1J; pThrowInfo
0x18006e5a9  lea     rcx, [rbp+arg_18]; pExceptionObject
0x18006e5ad  call    _CxxThrowException_0
0x18006e5b3  mov     word ptr [rbp+var_24], cx
0x18006e5b7  mov     rax, [rbp+ppstm]
0x18006e5bb  mov     [rbp+ppstm], r12
0x18006e5bf  mov     [r14], rax
0x18006e5c2  mov     [rdi], rbx
0x18006e5c5  lea     rcx, [rbp+lpBuffer]
0x18006e5c9  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18006e5ce  nop
0x18006e5cf  lea     rcx, [rbp+ppstm]
0x18006e5d3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006e5d8  nop
0x18006e5d9  lea     rcx, [rbp+var_28]; this
0x18006e5dd  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18006e5e2  mov     rbx, [rsp+70h+arg_0]
0x18006e5ea  add     rsp, 70h
0x18006e5ee  pop     r15
0x18006e5f0  pop     r14
0x18006e5f2  pop     r13
0x18006e5f4  pop     r12
0x18006e5f6  pop     rdi
0x18006e5f7  pop     rsi
0x18006e5f8  pop     rbp
0x18006e5f9  retn
0x18006e5fa  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18006e5ff  nop
0x18006e600  mov     [rbp+var_28], eax
0x18006e603  mov     word ptr [rbp+var_24+2], si
0x18006e607  mov     [rbp+arg_18], eax
0x18006e60a  lea     rdx, _TI1J; pThrowInfo
0x18006e611  lea     rcx, [rbp+arg_18]; pExceptionObject
0x18006e615  call    _CxxThrowException_0
```
