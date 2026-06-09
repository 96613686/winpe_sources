# _anonymous_namespace_::GetPropertyValue_unsigned_long_

- ea: `0x180043964`
- end: `0x180043e71`
- name: `_anonymous_namespace_::GetPropertyValue_unsigned_long_`
- size: `1293`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180045b18`

## callees

- `0x180001304`
- `0x18003fe64`
- `0x180043964`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043bb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043bb6`

## string_xrefs

- `0x1800439d3`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180043aef`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180043c6c`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180043baf`: `GamepadAccessibilityVibrationSetting`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GetPropertyValue_unsigned_long_(__int64 *a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v6; // rcx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v11; // rdx
  int v12; // ebx
  __int64 v13; // r8
  int v14; // r9d
  int v15; // ecx
  int *v16; // rdx
  __int64 v17; // rcx
  __int64 (__fastcall ***v18)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 *v19; // rcx
  __int64 *v20; // rbx
  __int64 v21; // rsi
  HRESULT v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  __int64 v25; // rcx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 *v27; // rcx
  __int64 v28; // rcx
  __int64 (__fastcall ***v29)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 *v30; // rcx
  int v31; // [rsp+40h] [rbp-29h] BYREF
  int v32; // [rsp+44h] [rbp-25h] BYREF
  __int64 v33; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-19h] BYREF
  __int64 *v35; // [rsp+58h] [rbp-11h] BYREF
  const char *v36; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  HSTRING string; // [rsp+80h] [rbp+17h] BYREF

  v35 = 0;
  v34 = 0;
  v33 = 0;
  if ( !a1 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x800) != 0
      && (qword_180069018 & 0x800) == qword_180069018 )
    {
      v31 = -2147483637;
      v36 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
      v32 = 73;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_180063819,
        a3,
        a4,
        (__int64)&v36,
        (__int64)&v32,
        (__int64)&v31);
    }
    v6 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    v7 = v34;
    if ( v34 )
    {
      v34 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v7)[2])(v7);
    }
    v8 = v35;
    if ( !v35 )
      return 2147483659LL;
    v35 = 0;
    v9 = *v8;
LABEL_12:
    (*(void (**)(void))(v9 + 16))();
    return 2147483659LL;
  }
  (*(void (__fastcall **)(__int64 *))(*a1 + 8))(a1);
  v12 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 **))*a1)(
          a1,
          &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
          &v35);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_20;
    v13 = qword_180069018;
    v11 = 2048;
    v15 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_20;
    v31 = 76;
    v16 = &dword_180062BC4;
LABEL_19:
    v36 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
    v32 = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v15,
      (_DWORD)v16,
      v13,
      v14,
      (__int64)&v36,
      (__int64)&v31,
      (__int64)&v32);
LABEL_20:
    v17 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v17 + 16LL))(v17, v11, v13);
    }
    v18 = v34;
    if ( v34 )
    {
      v34 = 0;
      ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v18)[2](v18, (GUID *)v11, v13);
    }
    v19 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64 *, __int64, __int64))(*v19 + 16))(v19, v11, v13);
    }
    (*(void (__fastcall **)(__int64 *, __int64, __int64))(*a1 + 16))(a1, v11, v13);
    return (unsigned int)v12;
  }
  v20 = v35;
  v21 = *v35;
  string = 0;
  v22 = WindowsCreateStringReference(L"GamepadAccessibilityVibrationSetting", 0x24u, &hstringHeader, &string);
  if ( v22 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
    JUMPOUT(0x180043E70LL);
  }
  v12 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v21 + 48))(v20, string, &v34);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_20;
    v13 = qword_180069018;
    v11 = 2048;
    v15 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_20;
    v31 = 77;
    v16 = (int *)&byte_180062F97;
    goto LABEL_19;
  }
  if ( !v34 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x800) != 0
      && (qword_180069018 & 0x800) == qword_180069018 )
    {
      v32 = -2147483637;
      v36 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
      v31 = 78;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_180062C01,
        v13,
        v14,
        (__int64)&v36,
        (__int64)&v31,
        (__int64)&v32);
    }
    v25 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v34;
    if ( v34 )
    {
      v34 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v26)[2])(v26);
    }
    v27 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
    }
    v9 = *a1;
    goto LABEL_12;
  }
  v12 = (**v34)(v34, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v33);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_20;
    v13 = qword_180069018;
    v11 = 2048;
    v15 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_20;
    v31 = 79;
    v16 = &dword_1800637DC;
    goto LABEL_19;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 96LL))(v33, a3);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_20;
    v13 = qword_180069018;
    v11 = 2048;
    v15 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_20;
    v31 = 80;
    v16 = (int *)byte_180063379;
    goto LABEL_19;
  }
  v28 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v34;
  if ( v34 )
  {
    v34 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v29)[2])(v29);
  }
  v30 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
  }
  (*(void (__fastcall **)(__int64 *))(*a1 + 16))(a1);
  return 0;
}

```

## disassembly

```asm
0x180043964  push    rbp
0x180043966  push    rbx
0x180043967  push    rsi
0x180043968  push    rdi
0x180043969  push    r14
0x18004396b  push    r15
0x18004396d  lea     rbp, [rsp-2Fh]
0x180043972  sub     rsp, 98h
0x180043979  mov     rax, cs:__security_cookie
0x180043980  xor     rax, rsp
0x180043983  mov     [rbp+57h+var_38], rax
0x180043987  xor     r15d, r15d
0x18004398a  mov     r14, r8
0x18004398d  mov     [rbp+57h+var_68], r15
0x180043991  mov     rdi, rcx
0x180043994  mov     [rbp+57h+var_70], r15
0x180043998  mov     [rbp+57h+var_78], r15
0x18004399c  test    rcx, rcx
0x18004399f  jnz     loc_180043A68
0x1800439a5  mov     eax, cs:dword_180069000
0x1800439ab  cmp     eax, 2
0x1800439ae  jbe     short loc_180043A13
0x1800439b0  mov     rcx, cs:qword_180069018
0x1800439b7  mov     edx, 800h
0x1800439bc  mov     rax, cs:qword_180069010
0x1800439c3  test    rdx, rax
0x1800439c6  jz      short loc_180043A13
0x1800439c8  mov     rax, rcx
0x1800439cb  and     rax, rdx
0x1800439ce  cmp     rax, rcx
0x1800439d1  jnz     short loc_180043A13
0x1800439d3  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x1800439da  mov     [rbp+57h+var_80], 8000000Bh
0x1800439e1  mov     [rbp+57h+var_60], rax
0x1800439e5  lea     rdx, byte_180063819
0x1800439ec  lea     rax, [rbp+57h+var_80]
0x1800439f0  mov     [rbp+57h+var_7C], 49h ; 'I'
0x1800439f7  mov     [rsp+0C0h+var_90], rax
0x1800439fc  lea     rax, [rbp+57h+var_7C]
0x180043a00  mov     [rsp+0C0h+var_98], rax
0x180043a05  lea     rax, [rbp+57h+var_60]
0x180043a09  mov     [rsp+0C0h+var_A0], rax
0x180043a0e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180043a13  mov     rcx, [rbp+57h+var_78]
0x180043a17  test    rcx, rcx
0x180043a1a  jz      short loc_180043A2C
0x180043a1c  mov     [rbp+57h+var_78], r15
0x180043a20  mov     rax, [rcx]
0x180043a23  mov     rax, [rax+10h]
0x180043a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a2c  mov     rcx, [rbp+57h+var_70]
0x180043a30  test    rcx, rcx
0x180043a33  jz      short loc_180043A45
0x180043a35  mov     [rbp+57h+var_70], r15
0x180043a39  mov     rax, [rcx]
0x180043a3c  mov     rax, [rax+10h]
0x180043a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a45  mov     rcx, [rbp+57h+var_68]
0x180043a49  test    rcx, rcx
0x180043a4c  jz      short loc_180043A5E
0x180043a4e  mov     [rbp+57h+var_68], r15
0x180043a52  mov     rax, [rcx]
0x180043a55  mov     rax, [rax+10h]
0x180043a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a5e  mov     eax, 8000000Bh
0x180043a63  jmp     loc_180043E4C
0x180043a68  mov     rax, [rcx]
0x180043a6b  mov     rax, [rax+8]
0x180043a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a74  mov     rax, [rdi]
0x180043a77  mov     rcx, [rbp+57h+var_68]
0x180043a7b  mov     rbx, [rax]
0x180043a7e  test    rcx, rcx
0x180043a81  jz      short loc_180043A93
0x180043a83  mov     [rbp+57h+var_68], r15
0x180043a87  mov     rdx, [rcx]
0x180043a8a  mov     rax, [rdx+10h]
0x180043a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a93  lea     r8, [rbp+57h+var_68]
0x180043a97  mov     rcx, rdi
0x180043a9a  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180043aa1  mov     rax, rbx
0x180043aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043aa9  mov     ebx, eax
0x180043aab  test    eax, eax
0x180043aad  jns     loc_180043B7E
0x180043ab3  mov     ecx, cs:dword_180069000
0x180043ab9  cmp     ecx, 2
0x180043abc  jbe     short loc_180043B1D
0x180043abe  mov     r8, cs:qword_180069018
0x180043ac5  mov     edx, 800h
0x180043aca  mov     rcx, cs:qword_180069010
0x180043ad1  test    rdx, rcx
0x180043ad4  jz      short loc_180043B1D
0x180043ad6  mov     rax, r8
0x180043ad9  and     rax, rdx
0x180043adc  cmp     rax, r8
0x180043adf  jnz     short loc_180043B1D
0x180043ae1  mov     [rbp+57h+var_80], 4Ch ; 'L'
0x180043ae8  lea     rdx, dword_180062BC4
0x180043aef  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180043af6  mov     [rbp+57h+var_60], rax
0x180043afa  lea     rax, [rbp+57h+var_7C]
0x180043afe  mov     [rsp+0C0h+var_90], rax
0x180043b03  lea     rax, [rbp+57h+var_80]
0x180043b07  mov     [rsp+0C0h+var_98], rax
0x180043b0c  lea     rax, [rbp+57h+var_60]
0x180043b10  mov     [rsp+0C0h+var_A0], rax
0x180043b15  mov     [rbp+57h+var_7C], ebx
0x180043b18  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180043b1d  mov     rcx, [rbp+57h+var_78]
0x180043b21  test    rcx, rcx
0x180043b24  jz      short loc_180043B36
0x180043b26  mov     [rbp+57h+var_78], r15
0x180043b2a  mov     rax, [rcx]
0x180043b2d  mov     rax, [rax+10h]
0x180043b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b36  mov     rcx, [rbp+57h+var_70]
0x180043b3a  test    rcx, rcx
0x180043b3d  jz      short loc_180043B4F
0x180043b3f  mov     [rbp+57h+var_70], r15
0x180043b43  mov     rax, [rcx]
0x180043b46  mov     rax, [rax+10h]
0x180043b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b4f  mov     rcx, [rbp+57h+var_68]
0x180043b53  test    rcx, rcx
0x180043b56  jz      short loc_180043B68
0x180043b58  mov     [rbp+57h+var_68], r15
0x180043b5c  mov     rax, [rcx]
0x180043b5f  mov     rax, [rax+10h]
0x180043b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b68  mov     rax, [rdi]
0x180043b6b  mov     rcx, rdi
0x180043b6e  mov     rax, [rax+10h]
0x180043b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b77  mov     eax, ebx
0x180043b79  jmp     loc_180043E4C
0x180043b7e  mov     rbx, [rbp+57h+var_68]
0x180043b82  mov     rcx, [rbp+57h+var_70]
0x180043b86  mov     rsi, [rbx]
0x180043b89  test    rcx, rcx
0x180043b8c  jz      short loc_180043B9E
0x180043b8e  mov     [rbp+57h+var_70], r15
0x180043b92  mov     rax, [rcx]
0x180043b95  mov     rax, [rax+10h]
0x180043b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b9e  lea     r9, [rbp+57h+string]; string
0x180043ba2  mov     [rbp+57h+string], r15
0x180043ba6  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180043baa  mov     edx, 24h ; '$'; length
0x180043baf  lea     rcx, sourceString; "GamepadAccessibilityVibrationSetting"
0x180043bb6  call    cs:__imp_WindowsCreateStringReference
0x180043bbd  nop     dword ptr [rax+rax+00h]
0x180043bc2  test    eax, eax
0x180043bc4  js      loc_180043E69
0x180043bca  mov     rdx, [rbp+57h+string]
0x180043bce  lea     r8, [rbp+57h+var_70]
0x180043bd2  mov     rax, [rsi+30h]
0x180043bd6  mov     rcx, rbx
0x180043bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bde  mov     ebx, eax
0x180043be0  test    eax, eax
0x180043be2  jns     short loc_180043C31
0x180043be4  mov     ecx, cs:dword_180069000
0x180043bea  cmp     ecx, 2
0x180043bed  jbe     loc_180043B1D
0x180043bf3  mov     r8, cs:qword_180069018
0x180043bfa  mov     edx, 800h
0x180043bff  mov     rcx, cs:qword_180069010
0x180043c06  test    rdx, rcx
0x180043c09  jz      loc_180043B1D
0x180043c0f  mov     rax, r8
0x180043c12  and     rax, rdx
0x180043c15  cmp     rax, r8
0x180043c18  jnz     loc_180043B1D
0x180043c1e  mov     [rbp+57h+var_80], 4Dh ; 'M'
0x180043c25  lea     rdx, byte_180062F97
0x180043c2c  jmp     loc_180043AEF
0x180043c31  mov     rbx, [rbp+57h+var_70]
0x180043c35  test    rbx, rbx
0x180043c38  jnz     loc_180043D02
0x180043c3e  mov     eax, cs:dword_180069000
0x180043c44  cmp     eax, 2
0x180043c47  jbe     short loc_180043CAC
0x180043c49  mov     rcx, cs:qword_180069018
0x180043c50  mov     edx, 800h
0x180043c55  mov     rax, cs:qword_180069010
0x180043c5c  test    rdx, rax
0x180043c5f  jz      short loc_180043CAC
0x180043c61  mov     rax, rcx
0x180043c64  and     rax, rdx
0x180043c67  cmp     rax, rcx
0x180043c6a  jnz     short loc_180043CAC
0x180043c6c  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180043c73  mov     [rbp+57h+var_7C], 8000000Bh
0x180043c7a  mov     [rbp+57h+var_60], rax
0x180043c7e  lea     rdx, byte_180062C01
0x180043c85  lea     rax, [rbp+57h+var_7C]
0x180043c89  mov     [rbp+57h+var_80], 4Eh ; 'N'
0x180043c90  mov     [rsp+0C0h+var_90], rax
0x180043c95  lea     rax, [rbp+57h+var_80]
0x180043c99  mov     [rsp+0C0h+var_98], rax
0x180043c9e  lea     rax, [rbp+57h+var_60]
0x180043ca2  mov     [rsp+0C0h+var_A0], rax
0x180043ca7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180043cac  mov     rcx, [rbp+57h+var_78]
0x180043cb0  test    rcx, rcx
0x180043cb3  jz      short loc_180043CC5
0x180043cb5  mov     [rbp+57h+var_78], r15
0x180043cb9  mov     rax, [rcx]
0x180043cbc  mov     rax, [rax+10h]
0x180043cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043cc5  mov     rcx, [rbp+57h+var_70]
0x180043cc9  test    rcx, rcx
0x180043ccc  jz      short loc_180043CDE
0x180043cce  mov     [rbp+57h+var_70], r15
0x180043cd2  mov     rax, [rcx]
0x180043cd5  mov     rax, [rax+10h]
0x180043cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043cde  mov     rcx, [rbp+57h+var_68]
0x180043ce2  test    rcx, rcx
0x180043ce5  jz      short loc_180043CF7
0x180043ce7  mov     [rbp+57h+var_68], r15
0x180043ceb  mov     rax, [rcx]
0x180043cee  mov     rax, [rax+10h]
0x180043cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043cf7  mov     rax, [rdi]
0x180043cfa  mov     rcx, rdi
0x180043cfd  jmp     loc_180043A55
0x180043d02  mov     rax, [rbx]
0x180043d05  mov     rcx, [rbp+57h+var_78]
0x180043d09  mov     rsi, [rax]
0x180043d0c  test    rcx, rcx
0x180043d0f  jz      short loc_180043D21
0x180043d11  mov     [rbp+57h+var_78], r15
0x180043d15  mov     rdx, [rcx]
0x180043d18  mov     rax, [rdx+10h]
0x180043d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d21  lea     r8, [rbp+57h+var_78]
0x180043d25  mov     rcx, rbx
0x180043d28  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180043d2f  mov     rax, rsi
0x180043d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d37  mov     ebx, eax
0x180043d39  test    eax, eax
0x180043d3b  jns     short loc_180043D8A
0x180043d3d  mov     ecx, cs:dword_180069000
0x180043d43  cmp     ecx, 2
0x180043d46  jbe     loc_180043B1D
0x180043d4c  mov     r8, cs:qword_180069018
0x180043d53  mov     edx, 800h
0x180043d58  mov     rcx, cs:qword_180069010
0x180043d5f  test    rdx, rcx
0x180043d62  jz      loc_180043B1D
0x180043d68  mov     rax, r8
0x180043d6b  and     rax, rdx
0x180043d6e  cmp     rax, r8
0x180043d71  jnz     loc_180043B1D
0x180043d77  mov     [rbp+57h+var_80], 4Fh ; 'O'
0x180043d7e  lea     rdx, dword_1800637DC
0x180043d85  jmp     loc_180043AEF
0x180043d8a  mov     rcx, [rbp+57h+var_78]
0x180043d8e  mov     rdx, r14
0x180043d91  mov     rax, [rcx]
0x180043d94  mov     rax, [rax+60h]
0x180043d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d9d  mov     ebx, eax
0x180043d9f  test    eax, eax
0x180043da1  jns     short loc_180043DF0
0x180043da3  mov     ecx, cs:dword_180069000
0x180043da9  cmp     ecx, 2
0x180043dac  jbe     loc_180043B1D
0x180043db2  mov     r8, cs:qword_180069018
0x180043db9  mov     edx, 800h
0x180043dbe  mov     rcx, cs:qword_180069010
0x180043dc5  test    rdx, rcx
0x180043dc8  jz      loc_180043B1D
0x180043dce  mov     rax, r8
0x180043dd1  and     rax, rdx
0x180043dd4  cmp     rax, r8
0x180043dd7  jnz     loc_180043B1D
0x180043ddd  mov     [rbp+57h+var_80], 50h ; 'P'
0x180043de4  lea     rdx, byte_180063379
0x180043deb  jmp     loc_180043AEF
0x180043df0  mov     rcx, [rbp+57h+var_78]
0x180043df4  test    rcx, rcx
0x180043df7  jz      short loc_180043E09
0x180043df9  mov     [rbp+57h+var_78], r15
0x180043dfd  mov     rax, [rcx]
0x180043e00  mov     rax, [rax+10h]
0x180043e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e09  mov     rcx, [rbp+57h+var_70]
0x180043e0d  test    rcx, rcx
0x180043e10  jz      short loc_180043E22
0x180043e12  mov     [rbp+57h+var_70], r15
0x180043e16  mov     rax, [rcx]
0x180043e19  mov     rax, [rax+10h]
0x180043e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e22  mov     rcx, [rbp+57h+var_68]
0x180043e26  test    rcx, rcx
  ... truncated ...
```
