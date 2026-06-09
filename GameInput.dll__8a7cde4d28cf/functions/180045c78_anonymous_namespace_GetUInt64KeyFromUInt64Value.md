# _anonymous_namespace_::GetUInt64KeyFromUInt64Value

- ea: `0x180045c78`
- end: `0x18004655f`
- name: `_anonymous_namespace_::GetUInt64KeyFromUInt64Value`
- size: `2279`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180045b18`

## callees

- `0x180001304`
- `0x180045c78`
- `0x18004d010`

## import_xrefs

- `ntdll!_wcstoui64` at `0x180046253`
- `ntdll!_wcstoui64` at `0x180046253`
- `ntdll!wcsspn` at `0x1800460f5`
- `ntdll!wcsspn` at `0x1800460f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004612c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046266`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800464a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004612c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046266`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800464a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800460d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800460d9`

## string_xrefs

- `0x180045ce5`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180045df0`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180045f48`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x1800461bf`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180046472`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GetUInt64KeyFromUInt64Value(
        __int64 *a1,
        const char *a2,
        unsigned __int64 *a3,
        int a4)
{
  __int64 v7; // rcx
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v11; // rdx
  signed int v12; // ebx
  __int64 v13; // r8
  int v14; // r9d
  int v15; // ecx
  __int16 *v16; // rdx
  __int64 v17; // rcx
  __int64 *v18; // rcx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  __int64 v23; // rbx
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall *v25)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rdi
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 v27; // rcx
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64 *); // rdi
  const wchar_t *StringRawBuffer; // rax
  __int64 v30; // rbx
  const wchar_t *v31; // rdi
  int v32; // r8d
  int v33; // r9d
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v37; // rcx
  __int64 *v38; // rcx
  unsigned __int64 v39; // rax
  HSTRING v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 (__fastcall ***v43)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v44; // rcx
  __int64 *v45; // rcx
  int v46; // ecx
  char *v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 (__fastcall ***v50)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v51; // rcx
  __int64 *v52; // rcx
  int v53; // [rsp+40h] [rbp-19h] BYREF
  __int64 v54; // [rsp+48h] [rbp-11h] BYREF
  __int64 *v55; // [rsp+50h] [rbp-9h] BYREF
  HSTRING string; // [rsp+58h] [rbp-1h] BYREF
  __int64 v57; // [rsp+60h] [rbp+7h] BYREF
  __int64 (__fastcall ***v58)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp+Fh] BYREF
  __int64 v59; // [rsp+70h] [rbp+17h] BYREF
  const char *v60; // [rsp+78h] [rbp+1Fh] BYREF
  const char *v61; // [rsp+80h] [rbp+27h] BYREF
  char v62; // [rsp+C0h] [rbp+67h] BYREF
  UINT32 length; // [rsp+D8h] [rbp+7Fh] BYREF

  v55 = 0;
  v54 = 0;
  v62 = 0;
  if ( !a1 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x800) != 0
      && (qword_180069018 & 0x800) == qword_180069018 )
    {
      length = -2147483637;
      v60 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
      v53 = 96;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&dword_1800635B4,
        (_DWORD)a3,
        a4,
        (__int64)&v60,
        (__int64)&v53,
        (__int64)&length);
    }
    v7 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v8 = v55;
    if ( !v55 )
      return 2147483659LL;
    v55 = 0;
    v9 = *v8;
LABEL_10:
    (*(void (**)(void))(v9 + 16))();
    return 2147483659LL;
  }
  (*(void (__fastcall **)(__int64 *))(*a1 + 8))(a1);
  v12 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 **))*a1)(
          a1,
          &GUID_fe2f3d47_5d47_5499_8374_430c7cda0204,
          &v55);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_104;
    v13 = qword_180069018;
    v11 = 2048;
    v15 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_104;
    v53 = 99;
    v16 = (__int16 *)&unk_1800631F8;
LABEL_17:
    v60 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
    length = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v15,
      (_DWORD)v16,
      v13,
      v14,
      (__int64)&v60,
      (__int64)&v53,
      (__int64)&length);
LABEL_104:
    v51 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v51 + 16LL))(v51, v11, v13);
    }
    v52 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64 *, __int64, __int64))(*v52 + 16))(v52, v11, v13);
    }
    (*(void (__fastcall **)(__int64 *, __int64, __int64))(*a1 + 16))(a1, v11, v13);
    return (unsigned int)v12;
  }
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*v55 + 48))(v55, &v54);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_104;
    v13 = qword_180069018;
    v11 = 2048;
    v15 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_104;
    v53 = 100;
    v16 = &word_180062E66;
    goto LABEL_17;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v54 + 56LL))(v54, &v62);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_104;
    v13 = qword_180069018;
    v11 = 2048;
    v15 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_104;
    v53 = 101;
    v16 = (__int16 *)&byte_18006375F;
    goto LABEL_17;
  }
  if ( !v62 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x800) != 0
      && (qword_180069018 & 0x800) == qword_180069018 )
    {
      length = -2147483637;
      v60 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
      v53 = 102;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_180063A01,
        v13,
        v14,
        (__int64)&v60,
        (__int64)&v53,
        (__int64)&length);
    }
    v17 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
    }
    v9 = *a1;
    goto LABEL_10;
  }
  while ( 1 )
  {
    v58 = 0;
    v57 = 0;
    v59 = 0;
    string = 0;
    v60 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 48LL))(v54, &v59);
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_98;
      v46 = qword_180069018;
      if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
        goto LABEL_98;
      v53 = 112;
      v47 = (char *)&unk_180062CB8;
LABEL_97:
      v61 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
      length = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v46,
        (_DWORD)v47,
        v19,
        v20,
        (__int64)&v61,
        (__int64)&v53,
        (__int64)&length);
      goto LABEL_98;
    }
    v21 = v59;
    v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v59 + 48LL);
    WindowsDeleteString(string);
    string = 0;
    v12 = v22(v21, &string);
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_98;
      v46 = qword_180069018;
      if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
        goto LABEL_98;
      v53 = 113;
      v47 = (char *)word_180063722;
      goto LABEL_97;
    }
    v23 = v59;
    v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
    v25 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v59 + 56LL);
    if ( v58 )
    {
      v58 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v24)[2])(v24);
    }
    v12 = v25(v23, &v58);
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v46 = qword_180069018;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v53 = 114;
          v47 = byte_1800634FD;
          goto LABEL_97;
        }
      }
LABEL_98:
      WindowsDeleteString(string);
      v48 = v59;
      string = 0;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      }
      v49 = v57;
      if ( v57 )
      {
        v57 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
      v50 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
      if ( v58 )
      {
        v58 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v50)[2])(v50);
      }
      goto LABEL_104;
    }
    v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
    v27 = v57;
    v28 = **v58;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v12 = v28(v26, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v57);
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v46 = qword_180069018;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v53 = 115;
          v47 = byte_18006312B;
          goto LABEL_97;
        }
      }
      goto LABEL_98;
    }
    if ( (*(int (__fastcall **)(__int64, const char **))(*(_QWORD *)v57 + 112LL))(v57, &v60) >= 0 && v60 == a2 )
    {
      length = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      v30 = length;
      v31 = StringRawBuffer;
      if ( wcsspn(StringRawBuffer, L"0123456789abcdefABCDEF") == v30 )
        break;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v54 + 64LL))(v54, &v62);
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v46 = qword_180069018;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          v53 = 132;
          v47 = byte_180063235;
          goto LABEL_97;
        }
      }
      goto LABEL_98;
    }
    WindowsDeleteString(string);
    v34 = v59;
    string = 0;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
    if ( v58 )
    {
      v58 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v36)[2])(v36);
    }
    if ( !v62 )
    {
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x800) != 0
        && (qword_180069018 & 0x800) == qword_180069018 )
      {
        length = -2147023728;
        v60 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
        v53 = 135;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned int)byte_1800635F1,
          v32,
          v33,
          (__int64)&v60,
          (__int64)&v53,
          (__int64)&length);
      }
      v37 = v54;
      if ( v54 )
      {
        v54 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      v38 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64 *))(*v38 + 16))(v38);
      }
      (*(void (__fastcall **)(__int64 *))(*a1 + 16))(a1);
      return 2147943568LL;
    }
  }
  v39 = _wcstoui64(v31, 0, 16);
  v40 = string;
  *a3 = v39;
  WindowsDeleteString(v40);
  v41 = v59;
  string = 0;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  v43 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
  if ( v58 )
  {
    v58 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v43)[2])(v43);
  }
  v44 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
  }
  (*(void (__fastcall **)(__int64 *))(*a1 + 16))(a1);
  return 0;
}

```

## disassembly

```asm
0x180045c78  mov     [rsp-8+arg_8], rbx
0x180045c7d  mov     [rsp-8+arg_10], rsi
0x180045c82  push    rbp
0x180045c83  push    rdi
0x180045c84  push    r12
0x180045c86  push    r14
0x180045c88  push    r15
0x180045c8a  lea     rbp, [rsp-37h]
0x180045c8f  sub     rsp, 90h
0x180045c96  xor     r12d, r12d
0x180045c99  mov     r15, r8
0x180045c9c  mov     [rbp+57h+var_60], r12
0x180045ca0  mov     r14, rdx
0x180045ca3  mov     [rbp+57h+var_68], r12
0x180045ca7  mov     rsi, rcx
0x180045caa  mov     [rbp+57h+arg_0], r12b
0x180045cae  test    rcx, rcx
0x180045cb1  jnz     loc_180045D61
0x180045cb7  mov     eax, cs:dword_180069000
0x180045cbd  cmp     eax, 2
0x180045cc0  jbe     short loc_180045D25
0x180045cc2  mov     rcx, cs:qword_180069018
0x180045cc9  mov     edx, 800h
0x180045cce  mov     rax, cs:qword_180069010
0x180045cd5  test    rdx, rax
0x180045cd8  jz      short loc_180045D25
0x180045cda  mov     rax, rcx
0x180045cdd  and     rax, rdx
0x180045ce0  cmp     rax, rcx
0x180045ce3  jnz     short loc_180045D25
0x180045ce5  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180045cec  mov     [rbp+57h+length], 8000000Bh
0x180045cf3  mov     [rbp+57h+var_38], rax
0x180045cf7  lea     rdx, dword_1800635B4
0x180045cfe  lea     rax, [rbp+57h+length]
0x180045d02  mov     [rbp+57h+var_70], 60h ; '`'
0x180045d09  mov     [rsp+0B0h+var_80], rax
0x180045d0e  lea     rax, [rbp+57h+var_70]
0x180045d12  mov     [rsp+0B0h+var_88], rax
0x180045d17  lea     rax, [rbp+57h+var_38]
0x180045d1b  mov     [rsp+0B0h+var_90], rax
0x180045d20  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180045d25  mov     rcx, [rbp+57h+var_68]
0x180045d29  test    rcx, rcx
0x180045d2c  jz      short loc_180045D3E
0x180045d2e  mov     [rbp+57h+var_68], r12
0x180045d32  mov     rax, [rcx]
0x180045d35  mov     rax, [rax+10h]
0x180045d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d3e  mov     rcx, [rbp+57h+var_60]
0x180045d42  test    rcx, rcx
0x180045d45  jz      short loc_180045D57
0x180045d47  mov     [rbp+57h+var_60], r12
0x180045d4b  mov     rax, [rcx]
0x180045d4e  mov     rax, [rax+10h]
0x180045d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d57  mov     eax, 8000000Bh
0x180045d5c  jmp     loc_180046542
0x180045d61  mov     rax, [rcx]
0x180045d64  mov     rax, [rax+8]
0x180045d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d6d  mov     rax, [rsi]
0x180045d70  mov     rcx, [rbp+57h+var_60]
0x180045d74  mov     rbx, [rax]
0x180045d77  test    rcx, rcx
0x180045d7a  jz      short loc_180045D8C
0x180045d7c  mov     [rbp+57h+var_60], r12
0x180045d80  mov     rdx, [rcx]
0x180045d83  mov     rax, [rdx+10h]
0x180045d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d8c  lea     r8, [rbp+57h+var_60]
0x180045d90  mov     rcx, rsi
0x180045d93  lea     rdx, _GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x180045d9a  mov     rax, rbx
0x180045d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045da2  mov     ebx, eax
0x180045da4  test    eax, eax
0x180045da6  jns     short loc_180045E23
0x180045da8  mov     ecx, cs:dword_180069000
0x180045dae  cmp     ecx, 2
0x180045db1  jbe     loc_1800464FF
0x180045db7  mov     r8, cs:qword_180069018
0x180045dbe  mov     edx, 800h
0x180045dc3  mov     rcx, cs:qword_180069010
0x180045dca  test    rdx, rcx
0x180045dcd  jz      loc_1800464FF
0x180045dd3  mov     rax, r8
0x180045dd6  and     rax, rdx
0x180045dd9  cmp     rax, r8
0x180045ddc  jnz     loc_1800464FF
0x180045de2  mov     [rbp+57h+var_70], 63h ; 'c'
0x180045de9  lea     rdx, unk_1800631F8
0x180045df0  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180045df7  mov     [rbp+57h+var_38], rax
0x180045dfb  lea     rax, [rbp+57h+length]
0x180045dff  mov     [rsp+0B0h+var_80], rax
0x180045e04  lea     rax, [rbp+57h+var_70]
0x180045e08  mov     [rsp+0B0h+var_88], rax
0x180045e0d  lea     rax, [rbp+57h+var_38]
0x180045e11  mov     [rsp+0B0h+var_90], rax
0x180045e16  mov     [rbp+57h+length], ebx
0x180045e19  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180045e1e  jmp     loc_1800464FF
0x180045e23  mov     rbx, [rbp+57h+var_60]
0x180045e27  mov     rcx, [rbp+57h+var_68]
0x180045e2b  mov     rax, [rbx]
0x180045e2e  mov     rdi, [rax+30h]
0x180045e32  test    rcx, rcx
0x180045e35  jz      short loc_180045E47
0x180045e37  mov     [rbp+57h+var_68], r12
0x180045e3b  mov     rdx, [rcx]
0x180045e3e  mov     rax, [rdx+10h]
0x180045e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e47  lea     rdx, [rbp+57h+var_68]
0x180045e4b  mov     rcx, rbx
0x180045e4e  mov     rax, rdi
0x180045e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e56  mov     ebx, eax
0x180045e58  test    eax, eax
0x180045e5a  jns     short loc_180045EA9
0x180045e5c  mov     ecx, cs:dword_180069000
0x180045e62  cmp     ecx, 2
0x180045e65  jbe     loc_1800464FF
0x180045e6b  mov     r8, cs:qword_180069018
0x180045e72  mov     edx, 800h
0x180045e77  mov     rcx, cs:qword_180069010
0x180045e7e  test    rdx, rcx
0x180045e81  jz      loc_1800464FF
0x180045e87  mov     rax, r8
0x180045e8a  and     rax, rdx
0x180045e8d  cmp     rax, r8
0x180045e90  jnz     loc_1800464FF
0x180045e96  mov     [rbp+57h+var_70], 64h ; 'd'
0x180045e9d  lea     rdx, word_180062E66
0x180045ea4  jmp     loc_180045DF0
0x180045ea9  mov     rcx, [rbp+57h+var_68]
0x180045ead  lea     rdx, [rbp+57h+arg_0]
0x180045eb1  mov     rax, [rcx]
0x180045eb4  mov     rax, [rax+38h]
0x180045eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ebd  mov     ebx, eax
0x180045ebf  test    eax, eax
0x180045ec1  jns     short loc_180045F10
0x180045ec3  mov     ecx, cs:dword_180069000
0x180045ec9  cmp     ecx, 2
0x180045ecc  jbe     loc_1800464FF
0x180045ed2  mov     r8, cs:qword_180069018
0x180045ed9  mov     edx, 800h
0x180045ede  mov     rcx, cs:qword_180069010
0x180045ee5  test    rdx, rcx
0x180045ee8  jz      loc_1800464FF
0x180045eee  mov     rax, r8
0x180045ef1  and     rax, rdx
0x180045ef4  cmp     rax, r8
0x180045ef7  jnz     loc_1800464FF
0x180045efd  mov     [rbp+57h+var_70], 65h ; 'e'
0x180045f04  lea     rdx, byte_18006375F
0x180045f0b  jmp     loc_180045DF0
0x180045f10  cmp     [rbp+57h+arg_0], r12b
0x180045f14  jnz     loc_180045FC5
0x180045f1a  mov     eax, cs:dword_180069000
0x180045f20  cmp     eax, 2
0x180045f23  jbe     short loc_180045F88
0x180045f25  mov     rcx, cs:qword_180069018
0x180045f2c  mov     edx, 800h
0x180045f31  mov     rax, cs:qword_180069010
0x180045f38  test    rdx, rax
0x180045f3b  jz      short loc_180045F88
0x180045f3d  mov     rax, rcx
0x180045f40  and     rax, rdx
0x180045f43  cmp     rax, rcx
0x180045f46  jnz     short loc_180045F88
0x180045f48  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180045f4f  mov     [rbp+57h+length], 8000000Bh
0x180045f56  mov     [rbp+57h+var_38], rax
0x180045f5a  lea     rdx, byte_180063A01
0x180045f61  lea     rax, [rbp+57h+length]
0x180045f65  mov     [rbp+57h+var_70], 66h ; 'f'
0x180045f6c  mov     [rsp+0B0h+var_80], rax
0x180045f71  lea     rax, [rbp+57h+var_70]
0x180045f75  mov     [rsp+0B0h+var_88], rax
0x180045f7a  lea     rax, [rbp+57h+var_38]
0x180045f7e  mov     [rsp+0B0h+var_90], rax
0x180045f83  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180045f88  mov     rcx, [rbp+57h+var_68]
0x180045f8c  test    rcx, rcx
0x180045f8f  jz      short loc_180045FA1
0x180045f91  mov     [rbp+57h+var_68], r12
0x180045f95  mov     rax, [rcx]
0x180045f98  mov     rax, [rax+10h]
0x180045f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fa1  mov     rcx, [rbp+57h+var_60]
0x180045fa5  test    rcx, rcx
0x180045fa8  jz      short loc_180045FBA
0x180045faa  mov     [rbp+57h+var_60], r12
0x180045fae  mov     rax, [rcx]
0x180045fb1  mov     rax, [rax+10h]
0x180045fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fba  mov     rax, [rsi]
0x180045fbd  mov     rcx, rsi
0x180045fc0  jmp     loc_180045D4E
0x180045fc5  mov     rcx, [rbp+57h+var_68]
0x180045fc9  lea     rdx, [rbp+57h+var_40]
0x180045fcd  mov     [rbp+57h+var_48], r12
0x180045fd1  mov     [rbp+57h+var_50], r12
0x180045fd5  mov     [rbp+57h+var_40], r12
0x180045fd9  mov     [rbp+57h+string], r12
0x180045fdd  mov     [rbp+57h+var_38], r12
0x180045fe1  mov     rax, [rcx]
0x180045fe4  mov     rax, [rax+30h]
0x180045fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fed  mov     ebx, eax
0x180045fef  test    eax, eax
0x180045ff1  js      loc_180046436
0x180045ff7  mov     rdi, [rbp+57h+var_40]
0x180045ffb  mov     rcx, [rbp+57h+string]; string
0x180045fff  mov     rax, [rdi]
0x180046002  mov     rbx, [rax+30h]
0x180046006  call    cs:__imp_WindowsDeleteString
0x18004600d  nop     dword ptr [rax+rax+00h]
0x180046012  lea     rdx, [rbp+57h+string]
0x180046016  mov     [rbp+57h+string], r12
0x18004601a  mov     rcx, rdi
0x18004601d  mov     rax, rbx
0x180046020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046025  mov     ebx, eax
0x180046027  test    eax, eax
0x180046029  js      loc_1800463F0
0x18004602f  mov     rbx, [rbp+57h+var_40]
0x180046033  mov     rcx, [rbp+57h+var_48]
0x180046037  mov     rax, [rbx]
0x18004603a  mov     rdi, [rax+38h]
0x18004603e  test    rcx, rcx
0x180046041  jz      short loc_180046053
0x180046043  mov     [rbp+57h+var_48], r12
0x180046047  mov     rdx, [rcx]
0x18004604a  mov     rax, [rdx+10h]
0x18004604e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046053  lea     rdx, [rbp+57h+var_48]
0x180046057  mov     rcx, rbx
0x18004605a  mov     rax, rdi
0x18004605d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046062  mov     ebx, eax
0x180046064  test    eax, eax
0x180046066  js      loc_1800463A3
0x18004606c  mov     rbx, [rbp+57h+var_48]
0x180046070  mov     rcx, [rbp+57h+var_50]
0x180046074  mov     rax, [rbx]
0x180046077  mov     rdi, [rax]
0x18004607a  test    rcx, rcx
0x18004607d  jz      short loc_18004608F
0x18004607f  mov     [rbp+57h+var_50], r12
0x180046083  mov     rdx, [rcx]
0x180046086  mov     rax, [rdx+10h]
0x18004608a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004608f  lea     r8, [rbp+57h+var_50]
0x180046093  mov     rcx, rbx
0x180046096  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18004609d  mov     rax, rdi
0x1800460a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460a5  mov     ebx, eax
0x1800460a7  test    eax, eax
0x1800460a9  js      loc_180046356
0x1800460af  mov     rcx, [rbp+57h+var_50]
0x1800460b3  lea     rdx, [rbp+57h+var_38]
0x1800460b7  mov     rax, [rcx]
0x1800460ba  mov     rax, [rax+70h]
0x1800460be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460c3  test    eax, eax
0x1800460c5  js      short loc_18004610A
0x1800460c7  cmp     [rbp+57h+var_38], r14
0x1800460cb  jnz     short loc_18004610A
0x1800460cd  mov     rcx, [rbp+57h+string]; string
0x1800460d1  lea     rdx, [rbp+57h+length]; length
0x1800460d5  mov     [rbp+57h+length], r12d
0x1800460d9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800460e0  nop     dword ptr [rax+rax+00h]
0x1800460e5  mov     ebx, [rbp+57h+length]
0x1800460e8  lea     rdx, a0123456789abcd; "0123456789abcdefABCDEF"
0x1800460ef  mov     rcx, rax; String
0x1800460f2  mov     rdi, rax
0x1800460f5  call    cs:__imp_wcsspn
0x1800460fc  nop     dword ptr [rax+rax+00h]
0x180046101  cmp     rax, rbx
0x180046104  jz      loc_18004624A
0x18004610a  mov     rcx, [rbp+57h+var_68]
0x18004610e  lea     rdx, [rbp+57h+arg_0]
0x180046112  mov     rax, [rcx]
0x180046115  mov     rax, [rax+40h]
0x180046119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004611e  mov     ebx, eax
0x180046120  test    eax, eax
0x180046122  js      loc_180046309
0x180046128  mov     rcx, [rbp+57h+string]; string
0x18004612c  call    cs:__imp_WindowsDeleteString
0x180046133  nop     dword ptr [rax+rax+00h]
0x180046138  mov     rcx, [rbp+57h+var_40]
0x18004613c  mov     [rbp+57h+string], r12
0x180046140  test    rcx, rcx
0x180046143  jz      short loc_180046155
  ... truncated ...
```
