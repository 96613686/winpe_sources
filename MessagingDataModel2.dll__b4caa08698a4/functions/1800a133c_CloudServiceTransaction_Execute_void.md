# CloudServiceTransaction::Execute(void)

- ea: `0x1800a133c`
- end: `0x1800a15d1`
- name: `?Execute@CloudServiceTransaction@@QEAAJXZ`
- size: `661`
- prototype: `__int64 __fastcall(CloudServiceTransaction *__hidden this)`
- caller_count: `16`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18007ed38`
- `0x18007efc0`
- `0x18007f264`
- `0x18007f524`
- `0x18007f7c4`
- `0x18007fa4c`
- `0x18007fcd8`
- `0x18007ff5c`
- `0x1800801f8`
- `0x1800815c0`
- `0x1800817c0`
- `0x1800819c0`
- `0x180081bc0`
- `0x180081de0`
- `0x180081fe0`
- `0x180082200`

## callees

- `0x180001564`
- `0x180030bd0`
- `0x1800a0f98`
- `0x1800a133c`
- `0x1800a15d8`
- `0x1800a1f78`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a13f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a13f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a13a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a13d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a156e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a15a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a13a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a13d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a156e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a15a1`

## string_xrefs

- `0x1800a1403`: `[MessagingCloudServices] CloudServiceTransaction HTTP request`

## pseudocode

```c
__int64 __fastcall CloudServiceTransaction::Execute(CloudServiceTransaction *this)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // eax
  WCHAR *v12; // rbx
  int v13; // edi
  _QWORD *v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rax
  WCHAR *StringRawBuffer; // [rsp+30h] [rbp-38h] BYREF
  const char *v19; // [rsp+38h] [rbp-30h] BYREF
  _BYTE v20[8]; // [rsp+40h] [rbp-28h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF
  __int64 v22; // [rsp+50h] [rbp-18h] BYREF

  v2 = *((_QWORD *)this + 1);
  v22 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 96LL))(v2, &v22);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = v22;
    string = 0;
    v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v7 = v6(v5, &string);
    v4 = v7;
    if ( v7 < 0 )
    {
      Log_HREvent_77(v7);
LABEL_5:
      WindowsDeleteString(string);
LABEL_25:
      string = 0;
      goto LABEL_26;
    }
    if ( (unsigned int)dword_1800FD5F0 > 4 )
    {
      StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
      v19 = "[MessagingCloudServices] CloudServiceTransaction HTTP request";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (int)&unk_1800F2E80,
        v9,
        v10,
        (const unsigned __int16 **)&v19,
        (const OLECHAR **)&StringRawBuffer);
    }
    StringRawBuffer = 0;
    v11 = CloudServiceTransaction::_SendRequestAsync(this, &StringRawBuffer);
    v4 = v11;
    if ( v11 < 0 )
    {
      Log_HREvent_77(v11);
      if ( StringRawBuffer )
        (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)StringRawBuffer + 16LL))(StringRawBuffer);
      goto LABEL_5;
    }
    v12 = StringRawBuffer;
    v13 = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>((int (__fastcall ***)(_QWORD, GUID *, __int64 *))StringRawBuffer);
    if ( v13 < 0
      || (v14 = (_QWORD *)((char *)this + 16),
          v13 = (*(__int64 (__fastcall **)(WCHAR *, char *))(*(_QWORD *)v12 + 80LL))(v12, (char *)this + 16),
          v13 < 0) )
    {
      Log_HREvent_77(v13);
      if ( v12 )
        (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v12 + 16LL))(v12);
      goto LABEL_24;
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v14 + 128LL))(*v14, (char *)this + 24);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(CloudServiceTransaction *))(*(_QWORD *)this + 32LL))(this);
      if ( v13 >= 0 )
      {
        v15 = *v14;
        v20[0] = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 72LL))(v15, v20);
        if ( v13 >= 0 )
        {
          v16 = *(_QWORD *)this;
          if ( v20[0] )
          {
            v13 = (*(__int64 (__fastcall **)(CloudServiceTransaction *))(v16 + 40))(this);
            if ( v13 < 0 )
              goto LABEL_14;
LABEL_21:
            (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v12 + 16LL))(v12);
            WindowsDeleteString(string);
            v4 = 0;
            goto LABEL_25;
          }
          v13 = (*(__int64 (__fastcall **)(CloudServiceTransaction *))(v16 + 48))(this);
          if ( v13 >= 0 )
            goto LABEL_21;
        }
      }
    }
LABEL_14:
    Log_HREvent_77(v13);
    (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_24:
    WindowsDeleteString(string);
    v4 = v13;
    goto LABEL_25;
  }
  Log_HREvent_77(v3);
LABEL_26:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  return v4;
}

```

## disassembly

```asm
0x1800a133c  push    rbp
0x1800a133e  push    rbx
0x1800a133f  push    rsi
0x1800a1340  push    rdi
0x1800a1341  push    r14
0x1800a1343  push    r15
0x1800a1345  mov     rbp, rsp
0x1800a1348  sub     rsp, 68h
0x1800a134c  mov     rax, cs:__security_cookie
0x1800a1353  xor     rax, rsp
0x1800a1356  mov     [rbp+var_10], rax
0x1800a135a  mov     rsi, rcx
0x1800a135d  lea     rdx, [rbp+var_18]
0x1800a1361  mov     rcx, [rcx+8]
0x1800a1365  xor     r15d, r15d
0x1800a1368  mov     [rbp+var_18], r15
0x1800a136c  mov     rax, [rcx]
0x1800a136f  mov     rax, [rax+60h]
0x1800a1373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1378  mov     ebx, eax
0x1800a137a  test    eax, eax
0x1800a137c  jns     short loc_1800A1392
0x1800a137e  lea     edx, [r15+1]
0x1800a1382  mov     ecx, eax; int
0x1800a1384  lea     r9d, [r15+30h]
0x1800a1388  call    Log_HREvent_77
0x1800a138d  jmp     loc_1800A15AD
0x1800a1392  mov     rdi, [rbp+var_18]
0x1800a1396  xor     ecx, ecx; string
0x1800a1398  mov     [rbp+string], r15
0x1800a139c  mov     rax, [rdi]
0x1800a139f  mov     rbx, [rax+30h]
0x1800a13a3  call    cs:__imp_WindowsDeleteString
0x1800a13a9  lea     rdx, [rbp+string]
0x1800a13ad  mov     [rbp+string], r15
0x1800a13b1  mov     rcx, rdi
0x1800a13b4  mov     rax, rbx
0x1800a13b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a13bc  mov     ebx, eax
0x1800a13be  test    eax, eax
0x1800a13c0  jns     short loc_1800A13E1
0x1800a13c2  mov     edx, 1
0x1800a13c7  mov     ecx, eax; int
0x1800a13c9  lea     r9d, [rdx+31h]
0x1800a13cd  call    Log_HREvent_77
0x1800a13d2  mov     rcx, [rbp+string]; string
0x1800a13d6  call    cs:__imp_WindowsDeleteString
0x1800a13dc  jmp     loc_1800A15A9
0x1800a13e1  mov     eax, cs:dword_1800FD5F0
0x1800a13e7  cmp     eax, 4
0x1800a13ea  jbe     short loc_1800A1425
0x1800a13ec  mov     rcx, [rbp+string]; string
0x1800a13f0  xor     edx, edx; length
0x1800a13f2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a13f8  mov     [rbp+var_38], rax
0x1800a13fc  lea     rdx, unk_1800F2E80
0x1800a1403  lea     rax, aMessagingcloud_3; "[MessagingCloudServices] CloudServiceTr"...
0x1800a140a  mov     [rbp+var_30], rax
0x1800a140e  lea     rax, [rbp+var_38]
0x1800a1412  mov     [rsp+68h+var_40], rax
0x1800a1417  lea     rax, [rbp+var_30]
0x1800a141b  mov     [rsp+68h+var_48], rax
0x1800a1420  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800a1425  lea     rdx, [rbp+var_38]
0x1800a1429  mov     [rbp+var_38], r15
0x1800a142d  mov     rcx, rsi
0x1800a1430  call    ?_SendRequestAsync@CloudServiceTransaction@@IEAAJPEAPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@@Z; CloudServiceTransaction::_SendRequestAsync(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> * *)
0x1800a1435  mov     ebx, eax
0x1800a1437  test    eax, eax
0x1800a1439  jns     short loc_1800A146C
0x1800a143b  mov     edx, 1
0x1800a1440  mov     ecx, eax; int
0x1800a1442  lea     r9d, [rdx+3Ch]
0x1800a1446  call    Log_HREvent_77
0x1800a144b  mov     rdx, [rbp+var_38]
0x1800a144f  test    rdx, rdx
0x1800a1452  jz      loc_1800A13D2
0x1800a1458  mov     rcx, [rdx]
0x1800a145b  mov     rax, [rcx+10h]
0x1800a145f  mov     rcx, rdx
0x1800a1462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1467  jmp     loc_1800A13D2
0x1800a146c  mov     rbx, [rbp+var_38]
0x1800a1470  mov     rcx, rbx
0x1800a1473  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)
0x1800a1478  mov     edi, eax
0x1800a147a  test    eax, eax
0x1800a147c  js      loc_1800A1579
0x1800a1482  mov     rax, [rbx]
0x1800a1485  lea     r14, [rsi+10h]
0x1800a1489  mov     rdx, r14
0x1800a148c  mov     rcx, rbx
0x1800a148f  mov     rax, [rax+50h]
0x1800a1493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1498  mov     edi, eax
0x1800a149a  test    eax, eax
0x1800a149c  js      loc_1800A1579
0x1800a14a2  mov     rcx, [r14]
0x1800a14a5  lea     rdx, [rsi+18h]
0x1800a14a9  mov     rax, [rcx]
0x1800a14ac  mov     rax, [rax+80h]
0x1800a14b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a14b8  mov     edi, eax
0x1800a14ba  test    eax, eax
0x1800a14bc  jns     short loc_1800A14DC
0x1800a14be  mov     r9d, 42h ; 'B'
0x1800a14c4  mov     edx, 1
0x1800a14c9  mov     ecx, edi; int
0x1800a14cb  call    Log_HREvent_77
0x1800a14d0  mov     rcx, [rbx]
0x1800a14d3  mov     rax, [rcx+10h]
0x1800a14d7  jmp     loc_1800A1595
0x1800a14dc  mov     rax, [rsi]
0x1800a14df  mov     rcx, rsi
0x1800a14e2  mov     rax, [rax+20h]
0x1800a14e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a14eb  mov     edi, eax
0x1800a14ed  test    eax, eax
0x1800a14ef  jns     short loc_1800A14F9
0x1800a14f1  mov     r9d, 43h ; 'C'
0x1800a14f7  jmp     short loc_1800A14C4
0x1800a14f9  mov     rcx, [r14]
0x1800a14fc  lea     rdx, [rbp+var_28]
0x1800a1500  mov     [rbp+var_28], r15b
0x1800a1504  mov     rax, [rcx]
0x1800a1507  mov     rax, [rax+48h]
0x1800a150b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1510  mov     edi, eax
0x1800a1512  test    eax, eax
0x1800a1514  jns     short loc_1800A151E
0x1800a1516  mov     r9d, 46h ; 'F'
0x1800a151c  jmp     short loc_1800A14C4
0x1800a151e  mov     rcx, rsi
0x1800a1521  mov     rax, [rsi]
0x1800a1524  cmp     [rbp+var_28], r15b
0x1800a1528  jz      short loc_1800A1541
0x1800a152a  mov     rax, [rax+28h]
0x1800a152e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1533  mov     edi, eax
0x1800a1535  test    eax, eax
0x1800a1537  jns     short loc_1800A155B
0x1800a1539  mov     r9d, 49h ; 'I'
0x1800a153f  jmp     short loc_1800A14C4
0x1800a1541  mov     rax, [rax+30h]
0x1800a1545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a154a  mov     edi, eax
0x1800a154c  test    eax, eax
0x1800a154e  jns     short loc_1800A155B
0x1800a1550  mov     r9d, 4Dh ; 'M'
0x1800a1556  jmp     loc_1800A14C4
0x1800a155b  mov     rax, [rbx]
0x1800a155e  mov     rcx, rbx
0x1800a1561  mov     rax, [rax+10h]
0x1800a1565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a156a  mov     rcx, [rbp+string]; string
0x1800a156e  call    cs:__imp_WindowsDeleteString
0x1800a1574  mov     ebx, r15d
0x1800a1577  jmp     short loc_1800A15A9
0x1800a1579  mov     edx, 1
0x1800a157e  mov     ecx, edi; int
0x1800a1580  lea     r9d, [rdx+3Eh]
0x1800a1584  call    Log_HREvent_77
0x1800a1589  test    rbx, rbx
0x1800a158c  jz      short loc_1800A159D
0x1800a158e  mov     rax, [rbx]
0x1800a1591  mov     rax, [rax+10h]
0x1800a1595  mov     rcx, rbx
0x1800a1598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a159d  mov     rcx, [rbp+string]; string
0x1800a15a1  call    cs:__imp_WindowsDeleteString
0x1800a15a7  mov     ebx, edi
0x1800a15a9  mov     [rbp+string], r15
0x1800a15ad  lea     rcx, [rbp+var_18]
0x1800a15b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a15b6  mov     eax, ebx
0x1800a15b8  mov     rcx, [rbp+var_10]
0x1800a15bc  xor     rcx, rsp; StackCookie
0x1800a15bf  call    __security_check_cookie
0x1800a15c4  add     rsp, 68h
0x1800a15c8  pop     r15
0x1800a15ca  pop     r14
0x1800a15cc  pop     rdi
0x1800a15cd  pop     rsi
0x1800a15ce  pop     rbx
0x1800a15cf  pop     rbp
0x1800a15d0  retn
```
