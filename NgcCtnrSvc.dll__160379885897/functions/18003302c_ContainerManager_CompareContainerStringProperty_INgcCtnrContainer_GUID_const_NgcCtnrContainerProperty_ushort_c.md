# ContainerManager::CompareContainerStringProperty(INgcCtnrContainer *,_GUID const &,NgcCtnrContainerProperty,ushort const *,bool *)

- ea: `0x18003302c`
- end: `0x180033253`
- name: `?CompareContainerStringProperty@ContainerManager@@CAJPEAUINgcCtnrContainer@@AEBU_GUID@@W4NgcCtnrContainerProperty@@PEBGPEA_N@Z`
- size: `551`
- prototype: `static int __high(struct INgcCtnrContainer *, const struct _GUID *, enum NgcCtnrContainerProperty, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033d44`

## callees

- `0x180001144`
- `0x180012190`
- `0x1800143c0`
- `0x180018194`
- `0x1800204c4`
- `0x180029314`
- `0x18003302c`
- `0x1800341c0`
- `0x180080010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcreate_locale` at `0x180033118`
- `api-ms-win-crt-private-l1-1-0!_o__wcreate_locale` at `0x180033118`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp_l` at `0x1800331b2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp_l` at `0x1800331b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033233`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ContainerManager::CompareContainerStringProperty(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        char *a5)
{
  __int64 v7; // rax
  char v8; // di
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  __int16 *v13; // rdx
  struct localeinfo_struct *v14; // rax
  bool v15; // zf
  signed int v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  signed int LastError; // eax
  int v21; // edx
  unsigned int v22; // r8d
  int v23; // [rsp+40h] [rbp-40h] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-38h] BYREF
  __int64 v25; // [rsp+50h] [rbp-30h] BYREF
  void **v26; // [rsp+58h] [rbp-28h] BYREF
  struct localeinfo_struct *v27; // [rsp+60h] [rbp-20h]
  wchar_t **p_String2; // [rsp+68h] [rbp-18h] BYREF
  __int64 v29; // [rsp+70h] [rbp-10h] BYREF
  char v30; // [rsp+78h] [rbp-8h]
  int v31; // [rsp+A0h] [rbp+20h] BYREF
  unsigned __int8 *v32; // [rsp+B0h] [rbp+30h] BYREF

  String2 = 0;
  LODWORD(v32) = 0;
  v7 = *a1;
  p_String2 = &String2;
  v29 = 0;
  v8 = 1;
  v30 = 1;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, unsigned __int8 **))(v7 + 120))(a1, 1, &v29, &v32);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_String2);
  if ( v9 >= 0 )
  {
    if ( (_DWORD)v32 )
    {
      v9 = NgcUtils::ValidateStringPropertyData((NgcUtils *)String2, (const unsigned __int8 *)(unsigned int)v32, v10);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_1800BE0B8 <= 2 )
          goto LABEL_25;
        v13 = (__int16 *)byte_1800A6DAB;
        goto LABEL_4;
      }
    }
    v14 = (struct localeinfo_struct *)_o__wcreate_locale(0, &word_18008FA7C);
    v26 = &Microsoft::WRL::Wrappers::HandleT<LocaleHandleTraits>::`vftable';
    v27 = v14;
    if ( !v14 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v31 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)&dword_1800A6D84,
          0,
          0,
          (__int64)&v31);
      }
      v26 = &Microsoft::WRL::Wrappers::HandleT<LocaleHandleTraits>::`vftable';
      if ( v27 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocaleHandleTraits>::InternalClose(&v26) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v21, v22);
          JUMPOUT(0x180033252LL);
        }
        v27 = 0;
      }
      v9 = -2147467259;
      goto LABEL_25;
    }
    if ( a4 )
    {
      if ( !(_DWORD)v32 )
      {
LABEL_21:
        v8 = 0;
LABEL_22:
        *a5 = v8;
        v26 = &Microsoft::WRL::Wrappers::HandleT<LocaleHandleTraits>::`vftable';
        if ( v27 )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocaleHandleTraits>::InternalClose(&v26) )
          {
            v17 = GetLastError();
            if ( v17 > 0 )
              v17 = (unsigned __int16)v17 | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
            __debugbreak();
          }
          v27 = 0;
        }
        goto LABEL_25;
      }
      v15 = _wcsicmp_l(a4, String2, v14) == 0;
    }
    else
    {
      v15 = (_DWORD)v32 == 0;
    }
    if ( v15 )
      goto LABEL_22;
    goto LABEL_21;
  }
  v12 = (unsigned int)dword_1800BE0B8;
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v13 = word_1800A6DF2;
LABEL_4:
    v23 = v9;
    v25 = a2;
    v31 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v12,
      (__int64)v13,
      v10,
      v11,
      (__int64)&v23,
      &v25,
      (__int64)&v31);
  }
LABEL_25:
  wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &String2,
    0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003302c  mov     [rsp-18h+arg_8], rbx
0x180033031  mov     [rsp-18h+arg_18], rsi
0x180033036  mov     dword ptr [rsp-18h+arg_10], r8d
0x18003303b  push    rbp
0x18003303c  push    rdi
0x18003303d  push    r14
0x18003303f  mov     rbp, rsp
0x180033042  sub     rsp, 80h
0x180033049  mov     r14, r9
0x18003304c  mov     rsi, rdx
0x18003304f  mov     [rbp+String2], 0
0x180033057  mov     dword ptr [rbp+arg_10], 0
0x18003305e  mov     rax, [rcx]
0x180033061  lea     rdx, [rbp+String2]
0x180033065  mov     [rbp+var_18], rdx
0x180033069  mov     [rbp+var_10], 0
0x180033071  mov     edi, 1
0x180033076  mov     [rbp+var_8], dil
0x18003307a  lea     r9, [rbp+arg_10]
0x18003307e  lea     r8, [rbp+var_10]
0x180033082  mov     edx, edi
0x180033084  mov     rax, [rax+78h]
0x180033088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003308d  mov     ebx, eax
0x18003308f  lea     rcx, [rbp+var_18]
0x180033093  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180033098  test    ebx, ebx
0x18003309a  jns     short loc_1800330E1
0x18003309c  mov     ecx, cs:dword_1800BE0B8
0x1800330a2  cmp     ecx, 2
0x1800330a5  jbe     loc_1800331EC
0x1800330ab  lea     rdx, word_1800A6DF2
0x1800330b2  lea     rax, [rbp+arg_0]
0x1800330b6  mov     [rsp+80h+var_50], rax
0x1800330bb  lea     rax, [rbp+var_30]
0x1800330bf  mov     [rsp+80h+var_58], rax
0x1800330c4  lea     rax, [rbp+var_40]
0x1800330c8  mov     [rsp+80h+var_60], rax
0x1800330cd  mov     [rbp+var_40], ebx
0x1800330d0  mov     [rbp+var_30], rsi
0x1800330d4  mov     [rbp+arg_0], edi
0x1800330d7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800330dc  jmp     loc_1800331EC
0x1800330e1  mov     edx, dword ptr [rbp+arg_10]; unsigned __int8 *
0x1800330e4  test    edx, edx
0x1800330e6  jz      short loc_18003310F
0x1800330e8  mov     rcx, [rbp+String2]; this
0x1800330ec  call    ?ValidateStringPropertyData@NgcUtils@@YAJPEBEK@Z; NgcUtils::ValidateStringPropertyData(uchar const *,ulong)
0x1800330f1  mov     ebx, eax
0x1800330f3  test    eax, eax
0x1800330f5  jns     short loc_18003310F
0x1800330f7  mov     eax, cs:dword_1800BE0B8
0x1800330fd  cmp     eax, 2
0x180033100  jbe     loc_1800331EC
0x180033106  lea     rdx, byte_1800A6DAB
0x18003310d  jmp     short loc_1800330B2
0x18003310f  lea     rdx, word_18008FA7C
0x180033116  xor     ecx, ecx
0x180033118  call    cs:__imp__o__wcreate_locale
0x18003311f  nop     dword ptr [rax+rax+00h]
0x180033124  lea     rsi, ??_7?$HandleT@ULocaleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocaleHandleTraits>::`vftable'
0x18003312b  mov     [rbp+var_28], rsi
0x18003312f  mov     [rbp+var_20], rax
0x180033133  test    rax, rax
0x180033136  jnz     short loc_180033197
0x180033138  mov     eax, cs:dword_1800BE0B8
0x18003313e  cmp     eax, 2
0x180033141  jbe     short loc_18003316C
0x180033143  mov     [rbp+arg_0], 80004005h
0x18003314a  lea     rax, [rbp+arg_0]
0x18003314e  mov     [rsp+80h+var_60], rax
0x180033153  xor     r9d, r9d
0x180033156  xor     r8d, r8d
0x180033159  lea     rdx, dword_1800A6D84
0x180033160  lea     rcx, dword_1800BE0B8
0x180033167  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003316c  mov     [rbp+var_28], rsi
0x180033170  cmp     [rbp+var_20], 0
0x180033175  jz      short loc_180033190
0x180033177  lea     rcx, [rbp+var_28]
0x18003317b  call    ?InternalClose@?$HandleT@ULocaleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocaleHandleTraits>::InternalClose(void)
0x180033180  test    al, al
0x180033182  jz      loc_180033233
0x180033188  mov     [rbp+var_20], 0
0x180033190  mov     ebx, 80004005h
0x180033195  jmp     short loc_1800331EC
0x180033197  test    r14, r14
0x18003319a  jnz     short loc_1800331A2
0x18003319c  cmp     dword ptr [rbp+arg_10], r14d
0x1800331a0  jmp     short loc_1800331C0
0x1800331a2  cmp     dword ptr [rbp+arg_10], 0
0x1800331a6  jz      short loc_1800331C2
0x1800331a8  mov     r8, rax; Locale
0x1800331ab  mov     rdx, [rbp+String2]; String2
0x1800331af  mov     rcx, r14; String1
0x1800331b2  call    cs:__imp__wcsicmp_l
0x1800331b9  nop     dword ptr [rax+rax+00h]
0x1800331be  test    eax, eax
0x1800331c0  jz      short loc_1800331C5
0x1800331c2  xor     dil, dil
0x1800331c5  mov     rax, [rbp+arg_20]
0x1800331c9  mov     [rax], dil
0x1800331cc  mov     [rbp+var_28], rsi
0x1800331d0  cmp     [rbp+var_20], 0
0x1800331d5  jz      short loc_1800331EC
0x1800331d7  lea     rcx, [rbp+var_28]
0x1800331db  call    ?InternalClose@?$HandleT@ULocaleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocaleHandleTraits>::InternalClose(void)
0x1800331e0  test    al, al
0x1800331e2  jz      short loc_180033212
0x1800331e4  mov     [rbp+var_20], 0
0x1800331ec  xor     edx, edx
0x1800331ee  lea     rcx, [rbp+String2]
0x1800331f2  call    ?reset@?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uchar *)
0x1800331f7  mov     eax, ebx
0x1800331f9  lea     r11, [rsp+80h+var_s0]
0x180033201  mov     rbx, [r11+28h]
0x180033205  mov     rsi, [r11+38h]
0x180033209  mov     rsp, r11
0x18003320c  pop     r14
0x18003320e  pop     rdi
0x18003320f  pop     rbp
0x180033210  retn
0x180033212  call    cs:__imp_GetLastError
0x180033219  nop     dword ptr [rax+rax+00h]
0x18003321e  nop
0x18003321f  test    eax, eax
0x180033221  jle     short loc_18003322B
0x180033223  movzx   eax, ax
0x180033226  or      eax, 80070000h
0x18003322b  mov     ecx, eax; this
0x18003322d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180033232  int     3; Trap to Debugger
0x180033233  call    cs:__imp_GetLastError
0x18003323a  nop     dword ptr [rax+rax+00h]
0x18003323f  test    eax, eax
0x180033241  jle     short loc_18003324B
0x180033243  movzx   eax, ax
0x180033246  or      eax, 80070000h
0x18003324b  mov     ecx, eax; this
0x18003324d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
