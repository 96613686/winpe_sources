# ChatServiceTransaction::_RemoveAuthCookie(Windows::Foundation::IUriRuntimeClass *)

- ea: `0x1800a3004`
- end: `0x1800a3358`
- name: `?_RemoveAuthCookie@ChatServiceTransaction@@IEAAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `852`
- prototype: `__int64 __fastcall(ChatServiceTransaction *__hidden this, struct Windows::Foundation::IUriRuntimeClass *)`
- caller_count: `9`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009ed30`
- `0x1800a0500`
- `0x1800a3cb0`
- `0x1800a47c0`
- `0x1800a53e0`
- `0x1800a6730`
- `0x1800a77c0`
- `0x1800a83f0`
- `0x1800a8fc0`

## callees

- `0x18006b108`
- `0x1800a0db0`
- `0x1800a23d4`
- `0x1800a3004`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800a31ff`
- `msvcrt!_wcsicmp` at `0x1800a3213`
- `msvcrt!_wcsicmp` at `0x1800a3227`
- `msvcrt!_wcsicmp` at `0x1800a31ff`
- `msvcrt!_wcsicmp` at `0x1800a3213`
- `msvcrt!_wcsicmp` at `0x1800a3227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a31e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a31e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a31be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a324f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a328f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a31be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a324f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a328f`

## string_xrefs

- `0x1800a303a`: `Windows.Web.Http.Filters.HttpBaseProtocolFilter`
- `0x1800a31f5`: `ssl-compact`
- `0x1800a321d`: `skypetoken`

## pseudocode

```c
__int64 __fastcall ChatServiceTransaction::_RemoveAuthCookie(
        ChatServiceTransaction *this,
        struct Windows::Foundation::IUriRuntimeClass *a2)
{
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rcx
  void (*v6)(void); // rax
  int v8; // eax
  __int64 v9; // rcx
  void (*v10)(void); // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  void (*v13)(void); // rax
  __int64 v14; // rcx
  unsigned int i; // esi
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  const wchar_t *StringRawBuffer; // rax
  const wchar_t *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-19h] BYREF
  __int64 v28; // [rsp+48h] [rbp-1h]
  __int64 v29; // [rsp+50h] [rbp+7h] BYREF
  __int64 v30; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v31; // [rsp+60h] [rbp+17h] BYREF
  __int64 v32; // [rsp+68h] [rbp+1Fh] BYREF
  HSTRING string; // [rsp+70h] [rbp+27h] BYREF
  unsigned int v34; // [rsp+78h] [rbp+2Fh] BYREF

  v29 = 0;
  v28 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Web.Http.Filters.HttpBaseProtocolFilter",
    0x30u,
    0x2Fu);
  v3 = Windows::Foundation::ActivateInstance<Windows::Web::Http::Filters::IHttpBaseProtocolFilter>(v28, &v29);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v30 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 104LL))(v29, &v30);
    v4 = v8;
    if ( v8 >= 0 )
    {
      v31 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, struct Windows::Foundation::IUriRuntimeClass *, __int64 *))(*(_QWORD *)v30 + 72LL))(
             v30,
             a2,
             &v31);
      if ( v4 < 0
        || (v34 = 0, v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 56LL))(v31, &v34),
                     v4 < 0) )
      {
        Log_HREvent_78(v4);
        v12 = v31;
        if ( v31 )
        {
          v31 = 0;
          v13 = *(void (**)(void))(*(_QWORD *)v12 + 16LL);
LABEL_15:
          v13();
        }
      }
      else
      {
        for ( i = 0; ; ++i )
        {
          v16 = v31;
          if ( i >= v34 )
          {
            if ( v31 )
            {
              v31 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            }
            v25 = v30;
            if ( v30 )
            {
              v30 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            }
            v26 = v29;
            if ( v29 )
            {
              v29 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
            }
            return 0;
          }
          v32 = 0;
          v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 48LL))(v31, i, &v32);
          v4 = v17;
          if ( v17 < 0 )
            break;
          v18 = v32;
          string = 0;
          v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL);
          WindowsDeleteString(0);
          string = 0;
          v4 = v19(v18, &string);
          if ( v4 < 0
            || (StringRawBuffer = WindowsGetStringRawBuffer(string, 0), (v21 = StringRawBuffer) != 0)
            && (!_wcsicmp(StringRawBuffer, L"ssl-compact") || !_wcsicmp(v21, L"WLSSC") || !_wcsicmp(v21, L"skypetoken"))
            && (v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 64LL))(v30, v32), v4 < 0) )
          {
            Log_HREvent_78(v4);
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_34;
          }
          WindowsDeleteString(string);
          v22 = v32;
          string = 0;
          if ( v32 )
          {
            v32 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
        }
        Log_HREvent_78(v17);
LABEL_34:
        v23 = v32;
        if ( v32 )
        {
          v32 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = v31;
        if ( v31 )
        {
          v31 = 0;
          v13 = *(void (**)(void))(*(_QWORD *)v24 + 16LL);
          goto LABEL_15;
        }
      }
      v14 = v30;
      if ( !v30 )
        goto LABEL_10;
      v30 = 0;
      v10 = *(void (**)(void))(*(_QWORD *)v14 + 16LL);
    }
    else
    {
      Log_HREvent_78(v8);
      v9 = v30;
      if ( !v30 )
      {
LABEL_10:
        v11 = v29;
        if ( !v29 )
          return (unsigned int)v4;
        v29 = 0;
        v6 = *(void (**)(void))(*(_QWORD *)v11 + 16LL);
        goto LABEL_4;
      }
      v30 = 0;
      v10 = *(void (**)(void))(*(_QWORD *)v9 + 16LL);
    }
    v10();
    goto LABEL_10;
  }
  Log_HREvent_78(v3);
  v5 = v29;
  if ( v29 )
  {
    v29 = 0;
    v6 = *(void (**)(void))(*(_QWORD *)v5 + 16LL);
LABEL_4:
    v6();
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800a3004  mov     [rsp-8+arg_0], rbx
0x1800a3009  mov     [rsp-8+arg_10], rsi
0x1800a300e  push    rbp
0x1800a300f  push    rdi
0x1800a3010  push    r14
0x1800a3012  lea     rbp, [rsp-47h]
0x1800a3017  sub     rsp, 90h
0x1800a301e  mov     rax, cs:__security_cookie
0x1800a3025  xor     rax, rsp
0x1800a3028  mov     [rbp+57h+var_20], rax
0x1800a302c  xor     r14d, r14d
0x1800a302f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a3033  mov     rdi, rdx
0x1800a3036  mov     [rbp+57h+var_50], r14
0x1800a303a  lea     rdx, ?RuntimeClass_Windows_Web_Http_Filters_HttpBaseProtocolFilter@@3QBGB; "Windows.Web.Http.Filters.HttpBaseProtoc"...
0x1800a3041  mov     [rbp+57h+var_58], r14
0x1800a3045  lea     r9d, [r14+2Fh]; unsigned int
0x1800a3049  lea     r8d, [r14+30h]; unsigned int
0x1800a304d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a3052  mov     rcx, [rbp+57h+var_58]
0x1800a3056  lea     rdx, [rbp+57h+var_50]
0x1800a305a  call    ??$ActivateInstance@UIHttpBaseProtocolFilter@Filters@Http@Web@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIHttpBaseProtocolFilter@Filters@Http@Web@1@@Z; Windows::Foundation::ActivateInstance<Windows::Web::Http::Filters::IHttpBaseProtocolFilter>(HSTRING__ *,Windows::Web::Http::Filters::IHttpBaseProtocolFilter * *)
0x1800a305f  mov     ebx, eax
0x1800a3061  test    eax, eax
0x1800a3063  jns     short loc_1800A3096
0x1800a3065  lea     edx, [r14+1]
0x1800a3069  mov     r9d, 9Fh
0x1800a306f  mov     ecx, eax; int
0x1800a3071  call    Log_HREvent_78
0x1800a3076  mov     rcx, [rbp+57h+var_50]
0x1800a307a  test    rcx, rcx
0x1800a307d  jz      short loc_1800A308F
0x1800a307f  mov     [rbp+57h+var_50], r14
0x1800a3083  mov     rdx, [rcx]
0x1800a3086  mov     rax, [rdx+10h]
0x1800a308a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a308f  mov     eax, ebx
0x1800a3091  jmp     loc_1800A3334
0x1800a3096  mov     rcx, [rbp+57h+var_50]
0x1800a309a  lea     rdx, [rbp+57h+var_48]
0x1800a309e  mov     [rbp+57h+var_48], r14
0x1800a30a2  mov     rax, [rcx]
0x1800a30a5  mov     rax, [rax+68h]
0x1800a30a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a30ae  mov     ebx, eax
0x1800a30b0  test    eax, eax
0x1800a30b2  jns     short loc_1800A30F5
0x1800a30b4  mov     edx, 1
0x1800a30b9  mov     r9d, 0A2h
0x1800a30bf  mov     ecx, eax; int
0x1800a30c1  call    Log_HREvent_78
0x1800a30c6  mov     rcx, [rbp+57h+var_48]
0x1800a30ca  test    rcx, rcx
0x1800a30cd  jz      short loc_1800A30DF
0x1800a30cf  mov     [rbp+57h+var_48], r14
0x1800a30d3  mov     rdx, [rcx]
0x1800a30d6  mov     rax, [rdx+10h]
0x1800a30da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a30df  mov     rcx, [rbp+57h+var_50]
0x1800a30e3  test    rcx, rcx
0x1800a30e6  jz      short loc_1800A308F
0x1800a30e8  mov     [rbp+57h+var_50], r14
0x1800a30ec  mov     rax, [rcx]
0x1800a30ef  mov     rax, [rax+10h]
0x1800a30f3  jmp     short loc_1800A308A
0x1800a30f5  mov     rcx, [rbp+57h+var_48]
0x1800a30f9  lea     r8, [rbp+57h+var_40]
0x1800a30fd  mov     [rbp+57h+var_40], r14
0x1800a3101  mov     rdx, rdi
0x1800a3104  mov     rax, [rcx]
0x1800a3107  mov     rax, [rax+48h]
0x1800a310b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3110  mov     ebx, eax
0x1800a3112  test    eax, eax
0x1800a3114  jns     short loc_1800A3157
0x1800a3116  mov     r9d, 0A5h
0x1800a311c  mov     edx, 1
0x1800a3121  mov     ecx, ebx; int
0x1800a3123  call    Log_HREvent_78
0x1800a3128  mov     rcx, [rbp+57h+var_40]
0x1800a312c  test    rcx, rcx
0x1800a312f  jz      short loc_1800A3141
0x1800a3131  mov     [rbp+57h+var_40], r14
0x1800a3135  mov     rdx, [rcx]
0x1800a3138  mov     rax, [rdx+10h]
0x1800a313c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3141  mov     rcx, [rbp+57h+var_48]
0x1800a3145  test    rcx, rcx
0x1800a3148  jz      short loc_1800A30DF
0x1800a314a  mov     [rbp+57h+var_48], r14
0x1800a314e  mov     rax, [rcx]
0x1800a3151  mov     rax, [rax+10h]
0x1800a3155  jmp     short loc_1800A30DA
0x1800a3157  mov     rcx, [rbp+57h+var_40]
0x1800a315b  lea     rdx, [rbp+57h+var_28]
0x1800a315f  mov     [rbp+57h+var_28], r14d
0x1800a3163  mov     rax, [rcx]
0x1800a3166  mov     rax, [rax+38h]
0x1800a316a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a316f  mov     ebx, eax
0x1800a3171  test    eax, eax
0x1800a3173  jns     short loc_1800A317D
0x1800a3175  mov     r9d, 0A8h
0x1800a317b  jmp     short loc_1800A311C
0x1800a317d  mov     esi, r14d
0x1800a3180  mov     rcx, [rbp+57h+var_40]
0x1800a3184  cmp     esi, [rbp+57h+var_28]
0x1800a3187  jnb     loc_1800A32EB
0x1800a318d  mov     [rbp+57h+var_38], r14
0x1800a3191  lea     r8, [rbp+57h+var_38]
0x1800a3195  mov     rax, [rcx]
0x1800a3198  mov     edx, esi
0x1800a319a  mov     rax, [rax+30h]
0x1800a319e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a31a3  mov     ebx, eax
0x1800a31a5  test    eax, eax
0x1800a31a7  js      loc_1800A32A3
0x1800a31ad  mov     rdi, [rbp+57h+var_38]
0x1800a31b1  xor     ecx, ecx; string
0x1800a31b3  mov     [rbp+57h+string], r14
0x1800a31b7  mov     rax, [rdi]
0x1800a31ba  mov     rbx, [rax+30h]
0x1800a31be  call    cs:__imp_WindowsDeleteString
0x1800a31c4  lea     rdx, [rbp+57h+string]
0x1800a31c8  mov     [rbp+57h+string], r14
0x1800a31cc  mov     rcx, rdi
0x1800a31cf  mov     rax, rbx
0x1800a31d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a31d7  mov     ebx, eax
0x1800a31d9  test    eax, eax
0x1800a31db  js      loc_1800A329B
0x1800a31e1  mov     rcx, [rbp+57h+string]; string
0x1800a31e5  xor     edx, edx; length
0x1800a31e7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a31ed  mov     rbx, rax
0x1800a31f0  test    rax, rax
0x1800a31f3  jz      short loc_1800A324B
0x1800a31f5  lea     rdx, aSslCompact; "ssl-compact"
0x1800a31fc  mov     rcx, rax; String1
0x1800a31ff  call    cs:__imp__wcsicmp
0x1800a3205  test    eax, eax
0x1800a3207  jz      short loc_1800A3231
0x1800a3209  lea     rdx, aWlssc; "WLSSC"
0x1800a3210  mov     rcx, rbx; String1
0x1800a3213  call    cs:__imp__wcsicmp
0x1800a3219  test    eax, eax
0x1800a321b  jz      short loc_1800A3231
0x1800a321d  lea     rdx, aSkypetoken; "skypetoken"
0x1800a3224  mov     rcx, rbx; String1
0x1800a3227  call    cs:__imp__wcsicmp
0x1800a322d  test    eax, eax
0x1800a322f  jnz     short loc_1800A324B
0x1800a3231  mov     rcx, [rbp+57h+var_48]
0x1800a3235  mov     rdx, [rbp+57h+var_38]
0x1800a3239  mov     rax, [rcx]
0x1800a323c  mov     rax, [rax+40h]
0x1800a3240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3245  mov     ebx, eax
0x1800a3247  test    eax, eax
0x1800a3249  js      short loc_1800A3279
0x1800a324b  mov     rcx, [rbp+57h+string]; string
0x1800a324f  call    cs:__imp_WindowsDeleteString
0x1800a3255  mov     rcx, [rbp+57h+var_38]
0x1800a3259  mov     [rbp+57h+string], r14
0x1800a325d  test    rcx, rcx
0x1800a3260  jz      short loc_1800A3272
0x1800a3262  mov     [rbp+57h+var_38], r14
0x1800a3266  mov     rax, [rcx]
0x1800a3269  mov     rax, [rax+10h]
0x1800a326d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3272  inc     esi
0x1800a3274  jmp     loc_1800A3180
0x1800a3279  mov     r9d, 0BBh
0x1800a327f  mov     edx, 1
0x1800a3284  mov     ecx, ebx; int
0x1800a3286  call    Log_HREvent_78
0x1800a328b  mov     rcx, [rbp+57h+string]; string
0x1800a328f  call    cs:__imp_WindowsDeleteString
0x1800a3295  mov     [rbp+57h+string], r14
0x1800a3299  jmp     short loc_1800A32B5
0x1800a329b  mov     r9d, 0B0h
0x1800a32a1  jmp     short loc_1800A327F
0x1800a32a3  mov     edx, 1
0x1800a32a8  mov     r9d, 0ADh
0x1800a32ae  mov     ecx, ebx; int
0x1800a32b0  call    Log_HREvent_78
0x1800a32b5  mov     rcx, [rbp+57h+var_38]
0x1800a32b9  test    rcx, rcx
0x1800a32bc  jz      short loc_1800A32CE
0x1800a32be  mov     [rbp+57h+var_38], r14
0x1800a32c2  mov     rax, [rcx]
0x1800a32c5  mov     rax, [rax+10h]
0x1800a32c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a32ce  mov     rcx, [rbp+57h+var_40]
0x1800a32d2  test    rcx, rcx
0x1800a32d5  jz      loc_1800A3141
0x1800a32db  mov     [rbp+57h+var_40], r14
0x1800a32df  mov     rax, [rcx]
0x1800a32e2  mov     rax, [rax+10h]
0x1800a32e6  jmp     loc_1800A313C
0x1800a32eb  test    rcx, rcx
0x1800a32ee  jz      short loc_1800A3300
0x1800a32f0  mov     [rbp+57h+var_40], r14
0x1800a32f4  mov     rax, [rcx]
0x1800a32f7  mov     rax, [rax+10h]
0x1800a32fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3300  mov     rcx, [rbp+57h+var_48]
0x1800a3304  test    rcx, rcx
0x1800a3307  jz      short loc_1800A3319
0x1800a3309  mov     [rbp+57h+var_48], r14
0x1800a330d  mov     rax, [rcx]
0x1800a3310  mov     rax, [rax+10h]
0x1800a3314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3319  mov     rcx, [rbp+57h+var_50]
0x1800a331d  test    rcx, rcx
0x1800a3320  jz      short loc_1800A3332
0x1800a3322  mov     [rbp+57h+var_50], r14
0x1800a3326  mov     rax, [rcx]
0x1800a3329  mov     rax, [rax+10h]
0x1800a332d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3332  xor     eax, eax
0x1800a3334  mov     rcx, [rbp+57h+var_20]
0x1800a3338  xor     rcx, rsp; StackCookie
0x1800a333b  call    __security_check_cookie
0x1800a3340  lea     r11, [rsp+0A0h+var_10]
0x1800a3348  mov     rbx, [r11+20h]
0x1800a334c  mov     rsi, [r11+30h]
0x1800a3350  mov     rsp, r11
0x1800a3353  pop     r14
0x1800a3355  pop     rdi
0x1800a3356  pop     rbp
0x1800a3357  retn
```
