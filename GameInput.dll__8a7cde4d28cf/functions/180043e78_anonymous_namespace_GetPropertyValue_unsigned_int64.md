# _anonymous_namespace_::GetPropertyValue_unsigned___int64_

- ea: `0x180043e78`
- end: `0x1800443d1`
- name: `_anonymous_namespace_::GetPropertyValue_unsigned___int64_`
- size: `1369`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180045b18`

## callees

- `0x180001304`
- `0x18003fe64`
- `0x180043e78`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044118`

## string_xrefs

- `0x180043ef3`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x180044033`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`
- `0x1800441ce`: `onecore\xbox\gameinput\xboxgipservices\SettingsHelper.cpp`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GetPropertyValue_unsigned___int64_(
        __int64 *a1,
        const WCHAR *a2,
        __int64 a3,
        int a4)
{
  __int64 v7; // rcx
  __int64 (__fastcall ***v8)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 v12; // rdx
  int v13; // ebx
  __int64 v14; // r8
  int v15; // r9d
  int v16; // ecx
  __int16 *v17; // rdx
  __int64 v18; // rcx
  __int64 (__fastcall ***v19)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 *v20; // rcx
  __int64 *v21; // rbx
  __int64 v22; // r14
  unsigned __int64 v23; // rdx
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  __int64 v27; // rcx
  __int64 (__fastcall ***v28)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 *v29; // rcx
  __int64 v30; // rcx
  __int64 (__fastcall ***v31)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 *v32; // rcx
  int v33; // [rsp+40h] [rbp-19h] BYREF
  int v34; // [rsp+44h] [rbp-15h] BYREF
  __int64 v35; // [rsp+48h] [rbp-11h] BYREF
  __int64 (__fastcall ***v36)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-9h] BYREF
  __int64 *v37; // [rsp+58h] [rbp-1h] BYREF
  const char *v38; // [rsp+60h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+80h] [rbp+27h] BYREF

  v37 = 0;
  v36 = 0;
  v35 = 0;
  if ( !a1 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x800) != 0
      && (qword_180069018 & 0x800) == qword_180069018 )
    {
      v33 = -2147483637;
      v38 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
      v34 = 73;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&word_180063A3E,
        a3,
        a4,
        (__int64)&v38,
        (__int64)&v34,
        (__int64)&v33);
    }
    v7 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v8 = v36;
    if ( v36 )
    {
      v36 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v8)[2])(v8);
    }
    v9 = v37;
    if ( !v37 )
      return 2147483659LL;
    v37 = 0;
    v10 = *v9;
LABEL_12:
    (*(void (**)(void))(v10 + 16))();
    return 2147483659LL;
  }
  (*(void (__fastcall **)(__int64 *))(*a1 + 8))(a1);
  v13 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 **))*a1)(
          a1,
          &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
          &v37);
  if ( v13 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_20;
    v14 = qword_180069018;
    v12 = 2048;
    v16 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_20;
    v33 = 76;
    v17 = word_180062D32;
LABEL_19:
    v38 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
    v34 = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v16,
      (_DWORD)v17,
      v14,
      v15,
      (__int64)&v38,
      (__int64)&v33,
      (__int64)&v34);
LABEL_20:
    v18 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 16LL))(v18, v12, v14);
    }
    v19 = v36;
    if ( v36 )
    {
      v36 = 0;
      ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v19)[2](v19, (GUID *)v12, v14);
    }
    v20 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64 *, __int64, __int64))(*v20 + 16))(v20, v12, v14);
    }
    (*(void (__fastcall **)(__int64 *, __int64, __int64))(*a1 + 16))(a1, v12, v14);
    return (unsigned int)v13;
  }
  v21 = v37;
  v22 = *v37;
  string = 0;
  v23 = -1;
  do
    ++v23;
  while ( a2[v23] );
  if ( v23 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v23, v14);
    __debugbreak();
  }
  if ( (int)v23 + 1 < (unsigned int)v23 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v23, v14);
    JUMPOUT(0x1800443D0LL);
  }
  v24 = WindowsCreateStringReference(a2, v23, &hstringHeader, &string);
  if ( v24 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
    __debugbreak();
  }
  v13 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v22 + 48))(v21, string, &v36);
  if ( v13 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_20;
    v14 = qword_180069018;
    v12 = 2048;
    v16 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_20;
    v33 = 77;
    v17 = word_180063272;
    goto LABEL_19;
  }
  if ( !v36 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x800) != 0
      && (qword_180069018 & 0x800) == qword_180069018 )
    {
      v34 = -2147483637;
      v38 = "onecore\\xbox\\gameinput\\xboxgipservices\\SettingsHelper.cpp";
      v33 = 78;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&unk_180062EE0,
        v14,
        v15,
        (__int64)&v38,
        (__int64)&v33,
        (__int64)&v34);
    }
    v27 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v36;
    if ( v36 )
    {
      v36 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v28)[2])(v28);
    }
    v29 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
    }
    v10 = *a1;
    goto LABEL_12;
  }
  v13 = (**v36)(v36, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v35);
  if ( v13 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_20;
    v14 = qword_180069018;
    v12 = 2048;
    v16 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_20;
    v33 = 79;
    v17 = word_18006353A;
    goto LABEL_19;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 112LL))(v35, a3);
  if ( v13 < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_20;
    v14 = qword_180069018;
    v12 = 2048;
    v16 = qword_180069010;
    if ( (qword_180069010 & 0x800) == 0 || (qword_180069018 & 0x800) != qword_180069018 )
      goto LABEL_20;
    v33 = 80;
    v17 = (__int16 *)&dword_180063024;
    goto LABEL_19;
  }
  v30 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v36;
  if ( v36 )
  {
    v36 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v31)[2])(v31);
  }
  v32 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
  }
  (*(void (__fastcall **)(__int64 *))(*a1 + 16))(a1);
  return 0;
}

```

## disassembly

```asm
0x180043e78  mov     [rsp-8+arg_0], rbx
0x180043e7d  mov     [rsp-8+arg_18], rsi
0x180043e82  push    rbp
0x180043e83  push    rdi
0x180043e84  push    r12
0x180043e86  push    r14
0x180043e88  push    r15
0x180043e8a  lea     rbp, [rsp-37h]
0x180043e8f  sub     rsp, 90h
0x180043e96  mov     rax, cs:__security_cookie
0x180043e9d  xor     rax, rsp
0x180043ea0  mov     [rbp+57h+var_28], rax
0x180043ea4  xor     r12d, r12d
0x180043ea7  mov     r15, r8
0x180043eaa  mov     [rbp+57h+var_58], r12
0x180043eae  mov     rsi, rdx
0x180043eb1  mov     [rbp+57h+var_60], r12
0x180043eb5  mov     rdi, rcx
0x180043eb8  mov     [rbp+57h+var_68], r12
0x180043ebc  test    rcx, rcx
0x180043ebf  jnz     loc_180043FAC
0x180043ec5  mov     eax, cs:dword_180069000
0x180043ecb  cmp     eax, 2
0x180043ece  jbe     short loc_180043F33
0x180043ed0  mov     rcx, cs:qword_180069018
0x180043ed7  mov     edx, 800h
0x180043edc  mov     rax, cs:qword_180069010
0x180043ee3  test    rdx, rax
0x180043ee6  jz      short loc_180043F33
0x180043ee8  mov     rax, rcx
0x180043eeb  and     rax, rdx
0x180043eee  cmp     rax, rcx
0x180043ef1  jnz     short loc_180043F33
0x180043ef3  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180043efa  mov     [rbp+57h+var_70], 8000000Bh
0x180043f01  mov     [rbp+57h+var_50], rax
0x180043f05  lea     rdx, word_180063A3E
0x180043f0c  lea     rax, [rbp+57h+var_70]
0x180043f10  mov     [rbp+57h+var_6C], 49h ; 'I'
0x180043f17  mov     [rsp+0B0h+var_80], rax
0x180043f1c  lea     rax, [rbp+57h+var_6C]
0x180043f20  mov     [rsp+0B0h+var_88], rax
0x180043f25  lea     rax, [rbp+57h+var_50]
0x180043f29  mov     [rsp+0B0h+var_90], rax
0x180043f2e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180043f33  mov     rcx, [rbp+57h+var_68]
0x180043f37  test    rcx, rcx
0x180043f3a  jz      short loc_180043F4C
0x180043f3c  mov     [rbp+57h+var_68], r12
0x180043f40  mov     rax, [rcx]
0x180043f43  mov     rax, [rax+10h]
0x180043f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f4c  mov     rcx, [rbp+57h+var_60]
0x180043f50  test    rcx, rcx
0x180043f53  jz      short loc_180043F65
0x180043f55  mov     [rbp+57h+var_60], r12
0x180043f59  mov     rax, [rcx]
0x180043f5c  mov     rax, [rax+10h]
0x180043f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f65  mov     rcx, [rbp+57h+var_58]
0x180043f69  test    rcx, rcx
0x180043f6c  jz      short loc_180043F7E
0x180043f6e  mov     [rbp+57h+var_58], r12
0x180043f72  mov     rax, [rcx]
0x180043f75  mov     rax, [rax+10h]
0x180043f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f7e  mov     eax, 8000000Bh
0x180043f83  mov     rcx, [rbp+57h+var_28]
0x180043f87  xor     rcx, rsp; StackCookie
0x180043f8a  call    __security_check_cookie
0x180043f8f  lea     r11, [rsp+0B0h+var_20]
0x180043f97  mov     rbx, [r11+30h]
0x180043f9b  mov     rsi, [r11+48h]
0x180043f9f  mov     rsp, r11
0x180043fa2  pop     r15
0x180043fa4  pop     r14
0x180043fa6  pop     r12
0x180043fa8  pop     rdi
0x180043fa9  pop     rbp
0x180043faa  retn
0x180043fac  mov     rax, [rcx]
0x180043faf  mov     rax, [rax+8]
0x180043fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fb8  mov     rax, [rdi]
0x180043fbb  mov     rcx, [rbp+57h+var_58]
0x180043fbf  mov     rbx, [rax]
0x180043fc2  test    rcx, rcx
0x180043fc5  jz      short loc_180043FD7
0x180043fc7  mov     [rbp+57h+var_58], r12
0x180043fcb  mov     rdx, [rcx]
0x180043fce  mov     rax, [rdx+10h]
0x180043fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fd7  lea     r8, [rbp+57h+var_58]
0x180043fdb  mov     rcx, rdi
0x180043fde  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180043fe5  mov     rax, rbx
0x180043fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fed  mov     ebx, eax
0x180043fef  test    eax, eax
0x180043ff1  jns     loc_1800440C2
0x180043ff7  mov     ecx, cs:dword_180069000
0x180043ffd  cmp     ecx, 2
0x180044000  jbe     short loc_180044061
0x180044002  mov     r8, cs:qword_180069018
0x180044009  mov     edx, 800h
0x18004400e  mov     rcx, cs:qword_180069010
0x180044015  test    rdx, rcx
0x180044018  jz      short loc_180044061
0x18004401a  mov     rax, r8
0x18004401d  and     rax, rdx
0x180044020  cmp     rax, r8
0x180044023  jnz     short loc_180044061
0x180044025  mov     [rbp+57h+var_70], 4Ch ; 'L'
0x18004402c  lea     rdx, word_180062D32
0x180044033  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x18004403a  mov     [rbp+57h+var_50], rax
0x18004403e  lea     rax, [rbp+57h+var_6C]
0x180044042  mov     [rsp+0B0h+var_80], rax
0x180044047  lea     rax, [rbp+57h+var_70]
0x18004404b  mov     [rsp+0B0h+var_88], rax
0x180044050  lea     rax, [rbp+57h+var_50]
0x180044054  mov     [rsp+0B0h+var_90], rax
0x180044059  mov     [rbp+57h+var_6C], ebx
0x18004405c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180044061  mov     rcx, [rbp+57h+var_68]
0x180044065  test    rcx, rcx
0x180044068  jz      short loc_18004407A
0x18004406a  mov     [rbp+57h+var_68], r12
0x18004406e  mov     rax, [rcx]
0x180044071  mov     rax, [rax+10h]
0x180044075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004407a  mov     rcx, [rbp+57h+var_60]
0x18004407e  test    rcx, rcx
0x180044081  jz      short loc_180044093
0x180044083  mov     [rbp+57h+var_60], r12
0x180044087  mov     rax, [rcx]
0x18004408a  mov     rax, [rax+10h]
0x18004408e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044093  mov     rcx, [rbp+57h+var_58]
0x180044097  test    rcx, rcx
0x18004409a  jz      short loc_1800440AC
0x18004409c  mov     [rbp+57h+var_58], r12
0x1800440a0  mov     rax, [rcx]
0x1800440a3  mov     rax, [rax+10h]
0x1800440a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440ac  mov     rax, [rdi]
0x1800440af  mov     rcx, rdi
0x1800440b2  mov     rax, [rax+10h]
0x1800440b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440bb  mov     eax, ebx
0x1800440bd  jmp     loc_180043F83
0x1800440c2  mov     rbx, [rbp+57h+var_58]
0x1800440c6  mov     rcx, [rbp+57h+var_60]
0x1800440ca  mov     r14, [rbx]
0x1800440cd  test    rcx, rcx
0x1800440d0  jz      short loc_1800440E2
0x1800440d2  mov     [rbp+57h+var_60], r12
0x1800440d6  mov     rax, [rcx]
0x1800440d9  mov     rax, [rax+10h]
0x1800440dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440e2  mov     [rbp+57h+string], r12
0x1800440e6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800440ea  inc     rdx; int
0x1800440ed  cmp     [rsi+rdx*2], r12w
0x1800440f2  jnz     short loc_1800440EA
0x1800440f4  mov     eax, 0FFFFFFFFh
0x1800440f9  cmp     rdx, rax
0x1800440fc  ja      loc_1800443BB
0x180044102  lea     eax, [rdx+1]
0x180044105  cmp     eax, edx
0x180044107  jb      loc_1800443C6
0x18004410d  lea     r9, [rbp+57h+string]; string
0x180044111  mov     rcx, rsi; sourceString
0x180044114  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180044118  call    cs:__imp_WindowsCreateStringReference
0x18004411f  nop     dword ptr [rax+rax+00h]
0x180044124  test    eax, eax
0x180044126  js      loc_1800443B3
0x18004412c  mov     rdx, [rbp+57h+string]
0x180044130  lea     r8, [rbp+57h+var_60]
0x180044134  mov     rax, [r14+30h]
0x180044138  mov     rcx, rbx
0x18004413b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044140  mov     ebx, eax
0x180044142  test    eax, eax
0x180044144  jns     short loc_180044193
0x180044146  mov     ecx, cs:dword_180069000
0x18004414c  cmp     ecx, 2
0x18004414f  jbe     loc_180044061
0x180044155  mov     r8, cs:qword_180069018
0x18004415c  mov     edx, 800h
0x180044161  mov     rcx, cs:qword_180069010
0x180044168  test    rdx, rcx
0x18004416b  jz      loc_180044061
0x180044171  mov     rax, r8
0x180044174  and     rax, rdx
0x180044177  cmp     rax, r8
0x18004417a  jnz     loc_180044061
0x180044180  mov     [rbp+57h+var_70], 4Dh ; 'M'
0x180044187  lea     rdx, word_180063272
0x18004418e  jmp     loc_180044033
0x180044193  mov     rbx, [rbp+57h+var_60]
0x180044197  test    rbx, rbx
0x18004419a  jnz     loc_180044264
0x1800441a0  mov     eax, cs:dword_180069000
0x1800441a6  cmp     eax, 2
0x1800441a9  jbe     short loc_18004420E
0x1800441ab  mov     rcx, cs:qword_180069018
0x1800441b2  mov     edx, 800h
0x1800441b7  mov     rax, cs:qword_180069010
0x1800441be  test    rdx, rax
0x1800441c1  jz      short loc_18004420E
0x1800441c3  mov     rax, rcx
0x1800441c6  and     rax, rdx
0x1800441c9  cmp     rax, rcx
0x1800441cc  jnz     short loc_18004420E
0x1800441ce  lea     rax, aOnecoreXboxGam_53; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x1800441d5  mov     [rbp+57h+var_6C], 8000000Bh
0x1800441dc  mov     [rbp+57h+var_50], rax
0x1800441e0  lea     rdx, unk_180062EE0
0x1800441e7  lea     rax, [rbp+57h+var_6C]
0x1800441eb  mov     [rbp+57h+var_70], 4Eh ; 'N'
0x1800441f2  mov     [rsp+0B0h+var_80], rax
0x1800441f7  lea     rax, [rbp+57h+var_70]
0x1800441fb  mov     [rsp+0B0h+var_88], rax
0x180044200  lea     rax, [rbp+57h+var_50]
0x180044204  mov     [rsp+0B0h+var_90], rax
0x180044209  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004420e  mov     rcx, [rbp+57h+var_68]
0x180044212  test    rcx, rcx
0x180044215  jz      short loc_180044227
0x180044217  mov     [rbp+57h+var_68], r12
0x18004421b  mov     rax, [rcx]
0x18004421e  mov     rax, [rax+10h]
0x180044222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044227  mov     rcx, [rbp+57h+var_60]
0x18004422b  test    rcx, rcx
0x18004422e  jz      short loc_180044240
0x180044230  mov     [rbp+57h+var_60], r12
0x180044234  mov     rax, [rcx]
0x180044237  mov     rax, [rax+10h]
0x18004423b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044240  mov     rcx, [rbp+57h+var_58]
0x180044244  test    rcx, rcx
0x180044247  jz      short loc_180044259
0x180044249  mov     [rbp+57h+var_58], r12
0x18004424d  mov     rax, [rcx]
0x180044250  mov     rax, [rax+10h]
0x180044254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044259  mov     rax, [rdi]
0x18004425c  mov     rcx, rdi
0x18004425f  jmp     loc_180043F75
0x180044264  mov     rax, [rbx]
0x180044267  mov     rcx, [rbp+57h+var_68]
0x18004426b  mov     rsi, [rax]
0x18004426e  test    rcx, rcx
0x180044271  jz      short loc_180044283
0x180044273  mov     [rbp+57h+var_68], r12
0x180044277  mov     rdx, [rcx]
0x18004427a  mov     rax, [rdx+10h]
0x18004427e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044283  lea     r8, [rbp+57h+var_68]
0x180044287  mov     rcx, rbx
0x18004428a  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180044291  mov     rax, rsi
0x180044294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044299  mov     ebx, eax
0x18004429b  test    eax, eax
0x18004429d  jns     short loc_1800442EC
0x18004429f  mov     ecx, cs:dword_180069000
0x1800442a5  cmp     ecx, 2
0x1800442a8  jbe     loc_180044061
0x1800442ae  mov     r8, cs:qword_180069018
0x1800442b5  mov     edx, 800h
0x1800442ba  mov     rcx, cs:qword_180069010
0x1800442c1  test    rdx, rcx
0x1800442c4  jz      loc_180044061
0x1800442ca  mov     rax, r8
0x1800442cd  and     rax, rdx
0x1800442d0  cmp     rax, r8
0x1800442d3  jnz     loc_180044061
0x1800442d9  mov     [rbp+57h+var_70], 4Fh ; 'O'
0x1800442e0  lea     rdx, word_18006353A
0x1800442e7  jmp     loc_180044033
0x1800442ec  mov     rcx, [rbp+57h+var_68]
0x1800442f0  mov     rdx, r15
0x1800442f3  mov     rax, [rcx]
0x1800442f6  mov     rax, [rax+70h]
0x1800442fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442ff  mov     ebx, eax
0x180044301  test    eax, eax
0x180044303  jns     short loc_180044352
0x180044305  mov     ecx, cs:dword_180069000
0x18004430b  cmp     ecx, 2
0x18004430e  jbe     loc_180044061
0x180044314  mov     r8, cs:qword_180069018
0x18004431b  mov     edx, 800h
0x180044320  mov     rcx, cs:qword_180069010
0x180044327  test    rdx, rcx
0x18004432a  jz      loc_180044061
  ... truncated ...
```
