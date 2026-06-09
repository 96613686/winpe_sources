# CloudServiceAccount::_GetServiceTicketFromTokenBrokerResult(Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x18009c934`
- end: `0x18009cf38`
- name: `?_GetServiceTicketFromTokenBrokerResult@CloudServiceAccount@@AEAAJPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1540`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009c524`

## callees

- `0x180001484`
- `0x18000163c`
- `0x180001cc4`
- `0x18000b7d4`
- `0x18009c0a0`
- `0x18009c934`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009caf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009cd8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ce97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009caf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009cd8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ce97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ca87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cabc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cb1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cd18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cd4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cdcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cebd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ca87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cabc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cb1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cd18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cd4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cdcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cebd`

## pseudocode

```c
__int64 __fastcall CloudServiceAccount::_GetServiceTicketFromTokenBrokerResult(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v3; // rax
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // edi
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  void (*v25)(void); // rax
  int v26; // eax
  __int64 v27; // rcx
  void (*v28)(void); // rax
  __int64 v29; // rcx
  void (*v30)(void); // rax
  __int64 v31; // rcx
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rbx
  int v34; // eax
  __int64 v35; // rcx
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, HSTRING *); // rbx
  int v43; // eax
  PCWSTR v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rcx
  int v47; // [rsp+30h] [rbp-50h] BYREF
  PCWSTR StringRawBuffer; // [rsp+38h] [rbp-48h] BYREF
  __int64 v49; // [rsp+40h] [rbp-40h] BYREF
  __int64 v50; // [rsp+48h] [rbp-38h] BYREF
  __int64 v51; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  int v53; // [rsp+60h] [rbp-20h] BYREF
  HSTRING v54; // [rsp+68h] [rbp-18h] BYREF
  int v55; // [rsp+70h] [rbp-10h] BYREF

  v3 = *a2;
  v55 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, int *))(v3 + 56))(a2, &v55);
  v9 = v6;
  if ( v6 < 0 )
  {
    Log_HREvent_74(v6);
    return v9;
  }
  switch ( v55 )
  {
    case 0:
      v23 = *a2;
      v50 = 0;
      v24 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v23 + 48))(a2, &v50);
      v12 = v24;
      if ( v24 < 0 )
      {
        Log_HREvent_74(v24);
LABEL_33:
        v14 = v50;
        if ( !v50 )
          return (unsigned int)v12;
        v50 = 0;
        goto LABEL_35;
      }
      v51 = 0;
      v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v50 + 48LL))(v50, 0, &v51);
      v12 = v26;
      if ( v26 < 0 )
      {
        Log_HREvent_74(v26);
        v27 = v51;
        if ( !v51 )
        {
LABEL_42:
          v18 = v50;
          if ( !v50 )
            return (unsigned int)v12;
          v50 = 0;
          goto LABEL_44;
        }
        v51 = 0;
        v28 = *(void (**)(void))(*(_QWORD *)v27 + 16LL);
LABEL_41:
        v28();
        goto LABEL_42;
      }
      v49 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 56LL))(v51, &v49);
      if ( v12 < 0 )
        goto LABEL_46;
      if ( !v49 )
        goto LABEL_65;
      v53 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 48LL))(v49, &v53);
      if ( v12 < 0 )
      {
LABEL_46:
        Log_HREvent_74(v12);
        v29 = v49;
        if ( !v49 )
        {
LABEL_49:
          v31 = v51;
          if ( !v51 )
            goto LABEL_42;
          v51 = 0;
          v28 = *(void (**)(void))(*(_QWORD *)v31 + 16LL);
          goto LABEL_41;
        }
        v49 = 0;
        v30 = *(void (**)(void))(*(_QWORD *)v29 + 16LL);
LABEL_48:
        v30();
        goto LABEL_49;
      }
      if ( v53 )
      {
        v32 = v49;
        v54 = 0;
        v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v49 + 56LL);
        WindowsDeleteString(0);
        v54 = 0;
        v34 = v33(v32, &v54);
        v12 = v34;
        if ( v34 < 0 )
        {
          Log_HREvent_74(v34);
          WindowsDeleteString(v54);
          v54 = 0;
LABEL_56:
          v35 = v49;
          if ( !v49 )
            goto LABEL_49;
          v49 = 0;
          v30 = *(void (**)(void))(*(_QWORD *)v35 + 16LL);
          goto LABEL_48;
        }
        if ( (unsigned int)dword_1800FD5F0 > 2 )
        {
          v47 = v53;
          StringRawBuffer = WindowsGetStringRawBuffer(v54, 0);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v36,
            (unsigned int)&unk_1800F2A90,
            v37,
            v38,
            (__int64)&StringRawBuffer,
            (__int64)&v47);
        }
        v12 = -2147023652;
        Log_HREvent_74(-2147023652);
        WindowsDeleteString(v54);
        v54 = 0;
      }
      else
      {
LABEL_65:
        v41 = v51;
        string = 0;
        v42 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v51 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v43 = v42(v41, &string);
        v12 = v43;
        if ( v43 < 0 )
        {
          Log_HREvent_74(v43);
          WindowsDeleteString(string);
          string = 0;
          goto LABEL_56;
        }
        if ( string )
        {
          v44 = WindowsGetStringRawBuffer(string, 0);
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                  a3,
                                  v44) )
          {
            WindowsDeleteString(string);
            v45 = v49;
            string = 0;
            if ( v49 )
            {
              v49 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            }
            v46 = v51;
            if ( v51 )
            {
              v51 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
            }
            v22 = v50;
            if ( !v50 )
              return 0;
            v50 = 0;
            goto LABEL_78;
          }
          v12 = -2147024882;
        }
        else
        {
          v12 = -2147023728;
        }
        Log_HREvent_74(v12);
        WindowsDeleteString(string);
        string = 0;
      }
      v39 = v49;
      if ( v49 )
      {
        v49 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      }
      v40 = v51;
      if ( v51 )
      {
        v51 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
      goto LABEL_33;
    case 1:
      if ( (unsigned int)dword_1800FD5F0 > 2 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (unsigned int)(v55 - 1),
          (int)byte_1800F2991);
      return 0;
    case 2:
      if ( (unsigned int)dword_1800FD5F0 > 2 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (unsigned int)(v55 - 2),
          (int)byte_1800F28A3);
      return 0;
    case 3:
      if ( (unsigned int)dword_1800FD5F0 > 2 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (unsigned int)(v55 - 3),
          (int)byte_1800F2915);
      return 0;
  }
  v11 = (unsigned int)(v55 - 4);
  if ( v55 == 4 )
  {
    if ( (unsigned int)dword_1800FD5F0 > 2 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v11,
        (int)byte_1800F2823);
    return 0;
  }
  if ( v55 != 5 )
  {
    if ( (unsigned int)dword_1800FD5F0 > 2 )
    {
      v53 = v55;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v11,
        (int)&unk_1800F27A0,
        v7,
        v8,
        (__int64)&v53);
    }
    v12 = -2147418113;
    Log_HREvent_74(-2147418113);
    return (unsigned int)v12;
  }
  v13 = *a2;
  v49 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v13 + 64))(a2, &v49);
  if ( v12 < 0
    || (v53 = 0, v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 48LL))(v49, &v53), v12 < 0) )
  {
    Log_HREvent_74(v12);
    v14 = v49;
    if ( !v49 )
      return (unsigned int)v12;
    v49 = 0;
LABEL_35:
    v25 = *(void (**)(void))(*(_QWORD *)v14 + 16LL);
LABEL_36:
    v25();
    return (unsigned int)v12;
  }
  v15 = v49;
  string = 0;
  v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v49 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v17 = v16(v15, &string);
  v12 = v17;
  if ( v17 < 0 )
  {
    Log_HREvent_74(v17);
    WindowsDeleteString(string);
    v18 = v49;
    string = 0;
    if ( v49 )
    {
      v49 = 0;
LABEL_44:
      v25 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
      goto LABEL_36;
    }
    return (unsigned int)v12;
  }
  if ( (unsigned int)dword_1800FD5F0 > 2 )
  {
    v47 = v53;
    v54 = (HSTRING)WindowsGetStringRawBuffer(string, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v19,
      (unsigned int)&unk_1800F2A00,
      v20,
      v21,
      (__int64)&v54,
      (__int64)&v47);
  }
  WindowsDeleteString(string);
  v22 = v49;
  string = 0;
  if ( v49 )
  {
    v49 = 0;
LABEL_78:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return 0;
}

```

## disassembly

```asm
0x18009c934  mov     [rsp-18h+arg_0], rbx
0x18009c939  mov     [rsp-18h+arg_18], rsi
0x18009c93e  push    rbp
0x18009c93f  push    rdi
0x18009c940  push    r14
0x18009c942  mov     rbp, rsp
0x18009c945  sub     rsp, 80h
0x18009c94c  mov     rax, cs:__security_cookie
0x18009c953  xor     rax, rsp
0x18009c956  mov     [rbp+var_8], rax
0x18009c95a  mov     rax, [rdx]
0x18009c95d  mov     rbx, rdx
0x18009c960  xor     r14d, r14d
0x18009c963  lea     rdx, [rbp+var_10]
0x18009c967  mov     rcx, rbx
0x18009c96a  mov     [rbp+var_10], r14d
0x18009c96e  mov     rsi, r8
0x18009c971  mov     rax, [rax+38h]
0x18009c975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c97a  mov     edi, eax
0x18009c97c  test    eax, eax
0x18009c97e  jns     short loc_18009C998
0x18009c980  lea     edx, [r14+1]
0x18009c984  mov     r9d, 0B2h
0x18009c98a  mov     ecx, eax; int
0x18009c98c  call    Log_HREvent_74
0x18009c991  mov     eax, edi
0x18009c993  jmp     loc_18009CF14
0x18009c998  mov     ecx, [rbp+var_10]
0x18009c99b  test    ecx, ecx
0x18009c99d  jz      loc_18009CBBF
0x18009c9a3  sub     ecx, 1
0x18009c9a6  jz      loc_18009CB9F
0x18009c9ac  sub     ecx, 1
0x18009c9af  jz      loc_18009CB7F
0x18009c9b5  sub     ecx, 1
0x18009c9b8  jz      loc_18009CB5F
0x18009c9be  sub     ecx, 1
0x18009c9c1  jz      loc_18009CB3F
0x18009c9c7  cmp     ecx, 1
0x18009c9ca  jz      short loc_18009CA0B
0x18009c9cc  mov     eax, cs:dword_1800FD5F0
0x18009c9d2  cmp     eax, 2
0x18009c9d5  jbe     short loc_18009C9F2
0x18009c9d7  mov     eax, [rbp+var_10]
0x18009c9da  lea     rdx, unk_1800F27A0
0x18009c9e1  mov     [rbp+var_20], eax
0x18009c9e4  lea     rax, [rbp+var_20]
0x18009c9e8  mov     [rsp+80h+var_60], rax
0x18009c9ed  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18009c9f2  mov     ebx, 8000FFFFh
0x18009c9f7  xor     edx, edx
0x18009c9f9  mov     ecx, ebx; int
0x18009c9fb  mov     r9d, 11Ah
0x18009ca01  call    Log_HREvent_74
0x18009ca06  jmp     loc_18009CC07
0x18009ca0b  mov     rax, [rbx]
0x18009ca0e  lea     rdx, [rbp+var_40]
0x18009ca12  mov     rcx, rbx
0x18009ca15  mov     [rbp+var_40], r14
0x18009ca19  mov     rax, [rax+40h]
0x18009ca1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ca22  mov     ebx, eax
0x18009ca24  test    eax, eax
0x18009ca26  jns     short loc_18009CA50
0x18009ca28  mov     r9d, 0E1h
0x18009ca2e  mov     edx, 1
0x18009ca33  mov     ecx, ebx; int
0x18009ca35  call    Log_HREvent_74
0x18009ca3a  mov     rcx, [rbp+var_40]
0x18009ca3e  test    rcx, rcx
0x18009ca41  jz      loc_18009CC07
0x18009ca47  mov     [rbp+var_40], r14
0x18009ca4b  jmp     loc_18009CBFB
0x18009ca50  mov     rcx, [rbp+var_40]
0x18009ca54  lea     rdx, [rbp+var_20]
0x18009ca58  mov     [rbp+var_20], r14d
0x18009ca5c  mov     rax, [rcx]
0x18009ca5f  mov     rax, [rax+30h]
0x18009ca63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ca68  mov     ebx, eax
0x18009ca6a  test    eax, eax
0x18009ca6c  jns     short loc_18009CA76
0x18009ca6e  mov     r9d, 0E4h
0x18009ca74  jmp     short loc_18009CA2E
0x18009ca76  mov     rdi, [rbp+var_40]
0x18009ca7a  xor     ecx, ecx; string
0x18009ca7c  mov     [rbp+string], r14
0x18009ca80  mov     rax, [rdi]
0x18009ca83  mov     rbx, [rax+38h]
0x18009ca87  call    cs:__imp_WindowsDeleteString
0x18009ca8d  lea     rdx, [rbp+string]
0x18009ca91  mov     [rbp+string], r14
0x18009ca95  mov     rcx, rdi
0x18009ca98  mov     rax, rbx
0x18009ca9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009caa0  mov     ebx, eax
0x18009caa2  test    eax, eax
0x18009caa4  jns     short loc_18009CADC
0x18009caa6  mov     edx, 1
0x18009caab  mov     r9d, 0E7h
0x18009cab1  mov     ecx, eax; int
0x18009cab3  call    Log_HREvent_74
0x18009cab8  mov     rcx, [rbp+string]; string
0x18009cabc  call    cs:__imp_WindowsDeleteString
0x18009cac2  mov     rcx, [rbp+var_40]
0x18009cac6  mov     [rbp+string], r14
0x18009caca  test    rcx, rcx
0x18009cacd  jz      loc_18009CC07
0x18009cad3  mov     [rbp+var_40], r14
0x18009cad7  jmp     loc_18009CC66
0x18009cadc  mov     eax, cs:dword_1800FD5F0
0x18009cae2  cmp     eax, 2
0x18009cae5  jbe     short loc_18009CB1B
0x18009cae7  mov     eax, [rbp+var_20]
0x18009caea  xor     edx, edx; length
0x18009caec  mov     rcx, [rbp+string]; string
0x18009caf0  mov     [rbp+var_50], eax
0x18009caf3  call    cs:__imp_WindowsGetStringRawBuffer
0x18009caf9  mov     [rbp+var_18], rax
0x18009cafd  lea     rdx, unk_1800F2A00
0x18009cb04  lea     rax, [rbp+var_50]
0x18009cb08  mov     [rsp+80h+var_58], rax
0x18009cb0d  lea     rax, [rbp+var_18]
0x18009cb11  mov     [rsp+80h+var_60], rax
0x18009cb16  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18009cb1b  mov     rcx, [rbp+string]; string
0x18009cb1f  call    cs:__imp_WindowsDeleteString
0x18009cb25  mov     rcx, [rbp+var_40]
0x18009cb29  mov     [rbp+string], r14
0x18009cb2d  test    rcx, rcx
0x18009cb30  jz      loc_18009CF12
0x18009cb36  mov     [rbp+var_40], r14
0x18009cb3a  jmp     loc_18009CF06
0x18009cb3f  mov     eax, cs:dword_1800FD5F0
0x18009cb45  cmp     eax, 2
0x18009cb48  jbe     loc_18009CF12
0x18009cb4e  lea     rdx, byte_1800F2823
0x18009cb55  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18009cb5a  jmp     loc_18009CF12
0x18009cb5f  mov     eax, cs:dword_1800FD5F0
0x18009cb65  cmp     eax, 2
0x18009cb68  jbe     loc_18009CF12
0x18009cb6e  lea     rdx, byte_1800F2915
0x18009cb75  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18009cb7a  jmp     loc_18009CF12
0x18009cb7f  mov     eax, cs:dword_1800FD5F0
0x18009cb85  cmp     eax, 2
0x18009cb88  jbe     loc_18009CF12
0x18009cb8e  lea     rdx, byte_1800F28A3
0x18009cb95  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18009cb9a  jmp     loc_18009CF12
0x18009cb9f  mov     eax, cs:dword_1800FD5F0
0x18009cba5  cmp     eax, 2
0x18009cba8  jbe     loc_18009CF12
0x18009cbae  lea     rdx, byte_1800F2991
0x18009cbb5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18009cbba  jmp     loc_18009CF12
0x18009cbbf  mov     rax, [rbx]
0x18009cbc2  lea     rdx, [rbp+var_38]
0x18009cbc6  mov     rcx, rbx
0x18009cbc9  mov     [rbp+var_38], r14
0x18009cbcd  mov     rax, [rax+30h]
0x18009cbd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cbd6  mov     ebx, eax
0x18009cbd8  test    eax, eax
0x18009cbda  jns     short loc_18009CC0E
0x18009cbdc  mov     edx, 1
0x18009cbe1  mov     r9d, 0B9h
0x18009cbe7  mov     ecx, eax; int
0x18009cbe9  call    Log_HREvent_74
0x18009cbee  mov     rcx, [rbp+var_38]
0x18009cbf2  test    rcx, rcx
0x18009cbf5  jz      short loc_18009CC07
0x18009cbf7  mov     [rbp+var_38], r14
0x18009cbfb  mov     rdx, [rcx]
0x18009cbfe  mov     rax, [rdx+10h]
0x18009cc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cc07  mov     eax, ebx
0x18009cc09  jmp     loc_18009CF14
0x18009cc0e  mov     rcx, [rbp+var_38]
0x18009cc12  lea     r8, [rbp+var_30]
0x18009cc16  mov     [rbp+var_30], r14
0x18009cc1a  xor     edx, edx
0x18009cc1c  mov     rax, [rcx]
0x18009cc1f  mov     rax, [rax+30h]
0x18009cc23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cc28  mov     ebx, eax
0x18009cc2a  test    eax, eax
0x18009cc2c  jns     short loc_18009CC6F
0x18009cc2e  mov     edx, 1
0x18009cc33  mov     r9d, 0BCh
0x18009cc39  mov     ecx, eax; int
0x18009cc3b  call    Log_HREvent_74
0x18009cc40  mov     rcx, [rbp+var_30]
0x18009cc44  test    rcx, rcx
0x18009cc47  jz      short loc_18009CC59
0x18009cc49  mov     [rbp+var_30], r14
0x18009cc4d  mov     rdx, [rcx]
0x18009cc50  mov     rax, [rdx+10h]
0x18009cc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cc59  mov     rcx, [rbp+var_38]
0x18009cc5d  test    rcx, rcx
0x18009cc60  jz      short loc_18009CC07
0x18009cc62  mov     [rbp+var_38], r14
0x18009cc66  mov     rax, [rcx]
0x18009cc69  mov     rax, [rax+10h]
0x18009cc6d  jmp     short loc_18009CC02
0x18009cc6f  mov     rcx, [rbp+var_30]
0x18009cc73  lea     rdx, [rbp+var_40]
0x18009cc77  mov     [rbp+var_40], r14
0x18009cc7b  mov     rax, [rcx]
0x18009cc7e  mov     rax, [rax+38h]
0x18009cc82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cc87  mov     ebx, eax
0x18009cc89  test    eax, eax
0x18009cc8b  jns     short loc_18009CCCE
0x18009cc8d  mov     r9d, 0BFh
0x18009cc93  mov     edx, 1
0x18009cc98  mov     ecx, ebx; int
0x18009cc9a  call    Log_HREvent_74
0x18009cc9f  mov     rcx, [rbp+var_40]
0x18009cca3  test    rcx, rcx
0x18009cca6  jz      short loc_18009CCB8
0x18009cca8  mov     [rbp+var_40], r14
0x18009ccac  mov     rdx, [rcx]
0x18009ccaf  mov     rax, [rdx+10h]
0x18009ccb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ccb8  mov     rcx, [rbp+var_30]
0x18009ccbc  test    rcx, rcx
0x18009ccbf  jz      short loc_18009CC59
0x18009ccc1  mov     [rbp+var_30], r14
0x18009ccc5  mov     rax, [rcx]
0x18009ccc8  mov     rax, [rax+10h]
0x18009cccc  jmp     short loc_18009CC54
0x18009ccce  mov     rcx, [rbp+var_40]
0x18009ccd2  test    rcx, rcx
0x18009ccd5  jz      loc_18009CE10
0x18009ccdb  mov     [rbp+var_20], r14d
0x18009ccdf  lea     rdx, [rbp+var_20]
0x18009cce3  mov     rax, [rcx]
0x18009cce6  mov     rax, [rax+30h]
0x18009ccea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ccef  mov     ebx, eax
0x18009ccf1  test    eax, eax
0x18009ccf3  jns     short loc_18009CCFD
0x18009ccf5  mov     r9d, 0C4h
0x18009ccfb  jmp     short loc_18009CC93
0x18009ccfd  cmp     [rbp+var_20], r14d
0x18009cd01  jz      loc_18009CE10
0x18009cd07  mov     rdi, [rbp+var_40]
0x18009cd0b  xor     ecx, ecx; string
0x18009cd0d  mov     [rbp+var_18], r14
0x18009cd11  mov     rax, [rdi]
0x18009cd14  mov     rbx, [rax+38h]
0x18009cd18  call    cs:__imp_WindowsDeleteString
0x18009cd1e  lea     rdx, [rbp+var_18]
0x18009cd22  mov     [rbp+var_18], r14
0x18009cd26  mov     rcx, rdi
0x18009cd29  mov     rax, rbx
0x18009cd2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cd31  mov     ebx, eax
0x18009cd33  test    eax, eax
0x18009cd35  jns     short loc_18009CD74
0x18009cd37  mov     edx, 1
0x18009cd3c  mov     r9d, 0C9h
0x18009cd42  mov     ecx, eax; int
0x18009cd44  call    Log_HREvent_74
0x18009cd49  mov     rcx, [rbp+var_18]; string
0x18009cd4d  call    cs:__imp_WindowsDeleteString
0x18009cd53  mov     [rbp+var_18], r14
0x18009cd57  mov     rcx, [rbp+var_40]
0x18009cd5b  test    rcx, rcx
0x18009cd5e  jz      loc_18009CCB8
0x18009cd64  mov     [rbp+var_40], r14
0x18009cd68  mov     rax, [rcx]
0x18009cd6b  mov     rax, [rax+10h]
0x18009cd6f  jmp     loc_18009CCB3
0x18009cd74  mov     eax, cs:dword_1800FD5F0
0x18009cd7a  cmp     eax, 2
0x18009cd7d  jbe     short loc_18009CDB3
0x18009cd7f  mov     eax, [rbp+var_20]
0x18009cd82  xor     edx, edx; length
0x18009cd84  mov     rcx, [rbp+var_18]; string
0x18009cd88  mov     [rbp+var_50], eax
0x18009cd8b  call    cs:__imp_WindowsGetStringRawBuffer
0x18009cd91  mov     [rbp+var_48], rax
0x18009cd95  lea     rdx, unk_1800F2A90
0x18009cd9c  lea     rax, [rbp+var_50]
0x18009cda0  mov     [rsp+80h+var_58], rax
0x18009cda5  lea     rax, [rbp+var_48]
0x18009cda9  mov     [rsp+80h+var_60], rax
0x18009cdae  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18009cdb3  mov     ebx, 800704DCh
0x18009cdb8  xor     edx, edx
0x18009cdba  mov     ecx, ebx; int
0x18009cdbc  mov     r9d, 0D2h
0x18009cdc2  call    Log_HREvent_74
0x18009cdc7  mov     rcx, [rbp+var_18]; string
0x18009cdcb  call    cs:__imp_WindowsDeleteString
  ... truncated ...
```
