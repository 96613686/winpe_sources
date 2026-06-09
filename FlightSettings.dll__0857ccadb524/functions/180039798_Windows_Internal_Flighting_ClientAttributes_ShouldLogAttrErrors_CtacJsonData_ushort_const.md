# Windows::Internal::Flighting::ClientAttributes::ShouldLogAttrErrors(CtacJsonData *,ushort const *)

- ea: `0x180039798`
- end: `0x1800399d0`
- name: `?ShouldLogAttrErrors@ClientAttributes@Flighting@Internal@Windows@@CAJPEAVCtacJsonData@@PEBG@Z`
- size: `568`
- prototype: `static int(struct CtacJsonData *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032ba0`
- `0x180032e60`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x18003286c`
- `0x1800335a4`
- `0x180034e30`
- `0x1800352d8`
- `0x1800352e8`
- `0x180039798`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800398e3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800398e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800398a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800398f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003990e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800398a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800398f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003990e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800398cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800398cc`

## string_xrefs

- `0x18003992e`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`
- `0x180039981`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::Flighting::ClientAttributes::ShouldLogAttrErrors(
        struct CtacJsonData *a1,
        const unsigned __int16 *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64); // rbx
  unsigned int v4; // esi
  int v5; // eax
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  _QWORD *v8; // rax
  int v9; // edx
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  unsigned int v14; // ebx
  const WCHAR *StringRawBuffer; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-38h] BYREF
  int v20; // [rsp+40h] [rbp-30h]
  _QWORD v21[5]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  int v23; // [rsp+A0h] [rbp+30h]
  HSTRING string; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v25; // [rsp+B8h] [rbp+48h] BYREF

  if ( (double)*((unsigned __int8 *)a1 + 40) == 0.0 || !a2 || !*a2 )
    return 1;
  v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)a1 + 6);
  v18 = v3;
  if ( !v3 )
  {
    v4 = 0;
LABEL_21:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
    return v4;
  }
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v3)[1])(v3);
  v25 = 0;
  v5 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>(
         &v18,
         (__int64)&v25);
  v4 = v5;
  v23 = v5;
  if ( v5 < 0 )
  {
    v6 = (unsigned int)v5;
    v7 = 287;
    goto LABEL_19;
  }
  wil::GetRangeNoThrow<Windows::Data::Json::IJsonValue *>((__int64)v21);
  v4 = 1;
  v8 = v21;
  v19 = v21;
  v9 = (v21[0] != 0) - 1;
  v20 = v9;
  while ( *(int *)v8[2] >= 0 && v9 != -1 )
  {
    v10 = wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator*(&v19);
    string = 0;
    v11 = *(_QWORD *)v10;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v10 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v13 = v12(v11, &string);
    v14 = v13;
    v23 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
        (const char *)(unsigned int)v13,
        bIgnoreCase);
      WindowsDeleteString(string);
      string = 0;
      wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(v21);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
      v4 = v14;
      goto LABEL_21;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(a2, -1, StringRawBuffer, -1, 1) == 2 )
    {
      WindowsDeleteString(string);
      string = 0;
      wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(v21);
      goto LABEL_20;
    }
    WindowsDeleteString(string);
    wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator++(&v19);
    v9 = v20;
    v8 = v19;
  }
  wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(v21);
  v4 = v23;
  if ( v23 < 0 )
  {
    v6 = (unsigned int)v23;
    v7 = 301;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
      (const char *)v6,
      bIgnoreCase);
LABEL_20:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    goto LABEL_21;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x180039798  push    rbp
0x18003979a  push    rbx
0x18003979b  push    rsi
0x18003979c  push    rdi
0x18003979d  push    r14
0x18003979f  mov     rbp, rsp
0x1800397a2  sub     rsp, 70h
0x1800397a6  mov     r14, rdx
0x1800397a9  mov     dword ptr [rbp+arg_0], 0
0x1800397b0  movzx   eax, byte ptr [rcx+28h]
0x1800397b4  movd    xmm0, eax
0x1800397b8  cvtdq2pd xmm0, xmm0
0x1800397bc  ucomisd xmm0, cs:__real@0000000000000000
0x1800397c4  jp      short loc_1800397CC
0x1800397c6  jz      loc_1800399C0
0x1800397cc  test    r14, r14
0x1800397cf  jz      loc_1800399C0
0x1800397d5  xor     eax, eax
0x1800397d7  cmp     ax, [rdx]
0x1800397da  jz      loc_1800399C0
0x1800397e0  mov     rbx, [rcx+30h]
0x1800397e4  mov     [rbp+var_40], rbx
0x1800397e8  test    rbx, rbx
0x1800397eb  jz      short loc_1800397FD
0x1800397ed  mov     rax, [rbx]
0x1800397f0  mov     rcx, rbx
0x1800397f3  mov     rax, [rax+8]
0x1800397f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397fc  nop
0x1800397fd  test    rbx, rbx
0x180039800  jnz     short loc_180039809
0x180039802  xor     esi, esi
0x180039804  jmp     loc_18003999C
0x180039809  mov     [rbp+arg_18], 0
0x180039811  lea     rdx, [rbp+arg_18]
0x180039815  lea     rcx, [rbp+var_40]
0x180039819  call    ??$As@U?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>>)
0x18003981e  mov     esi, eax
0x180039820  mov     dword ptr [rbp+arg_0], eax
0x180039823  test    eax, eax
0x180039825  jns     short loc_180039834
0x180039827  mov     r9d, eax
0x18003982a  mov     edx, 11Fh
0x18003982f  jmp     loc_180039981
0x180039834  lea     r8, [rbp+arg_0]
0x180039838  mov     rdx, [rbp+arg_18]
0x18003983c  lea     rcx, [rbp+var_28]
0x180039840  call    ??$GetRangeNoThrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@YA?AV?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@0@PEAU?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::GetRangeNoThrow<Windows::Data::Json::IJsonValue *>(Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *> *,long *)
0x180039845  nop
0x180039846  mov     rax, [rbp+var_28]
0x18003984a  neg     rax
0x18003984d  sbb     ecx, ecx
0x18003984f  neg     ecx
0x180039851  mov     esi, 1
0x180039856  sub     ecx, esi
0x180039858  lea     rax, [rbp+var_28]
0x18003985c  mov     [rbp+var_38], rax
0x180039860  xor     edx, edx
0x180039862  cmp     ecx, 0FFFFFFFFh
0x180039865  setnz   dl
0x180039868  sub     edx, esi
0x18003986a  mov     [rbp+var_30], edx
0x18003986d  mov     rax, [rax+10h]
0x180039871  cmp     dword ptr [rax], 0
0x180039874  jl      loc_180039969
0x18003987a  cmp     edx, 0FFFFFFFFh
0x18003987d  jz      loc_180039969
0x180039883  lea     rcx, [rbp+var_38]
0x180039887  call    ??Diterable_iterator_nothrow@?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEBAAEBV?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator*(void)
0x18003988c  mov     [rbp+string], 0
0x180039894  mov     rdi, [rax]
0x180039897  mov     rax, [rdi]
0x18003989a  mov     rbx, [rax+40h]
0x18003989e  xor     ecx, ecx; string
0x1800398a0  call    cs:__imp_WindowsDeleteString
0x1800398a6  mov     [rbp+string], 0
0x1800398ae  lea     rdx, [rbp+string]
0x1800398b2  mov     rcx, rdi
0x1800398b5  mov     rax, rbx
0x1800398b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398bd  mov     ebx, eax
0x1800398bf  mov     dword ptr [rbp+arg_0], eax
0x1800398c2  test    eax, eax
0x1800398c4  js      short loc_180039927
0x1800398c6  xor     edx, edx; length
0x1800398c8  mov     rcx, [rbp+string]; string
0x1800398cc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800398d2  mov     [rsp+70h+bIgnoreCase], esi; bIgnoreCase
0x1800398d6  or      r9d, 0FFFFFFFFh; cchCount2
0x1800398da  mov     r8, rax; lpString2
0x1800398dd  or      edx, r9d; cchCount1
0x1800398e0  mov     rcx, r14; lpString1
0x1800398e3  call    cs:__imp_CompareStringOrdinal
0x1800398e9  nop
0x1800398ea  mov     rcx, [rbp+string]; string
0x1800398ee  cmp     eax, 2
0x1800398f1  jz      short loc_18003990E
0x1800398f3  call    cs:__imp_WindowsDeleteString
0x1800398f9  lea     rcx, [rbp+var_38]
0x1800398fd  call    ??Eiterable_iterator_nothrow@?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAAAEAV012@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator++(void)
0x180039902  mov     edx, [rbp+var_30]
0x180039905  mov     rax, [rbp+var_38]
0x180039909  jmp     loc_18003986D
0x18003990e  call    cs:__imp_WindowsDeleteString
0x180039914  mov     [rbp+string], 0
0x18003991c  lea     rcx, [rbp+var_28]
0x180039920  call    ??1?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(void)
0x180039925  jmp     short loc_180039992
0x180039927  mov     rcx, [rbp+28h]; this
0x18003992b  mov     r9d, ebx; char *
0x18003992e  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180039935  mov     edx, 126h; void *
0x18003993a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003993f  nop
0x180039940  mov     rcx, [rbp+string]; string
0x180039944  call    cs:__imp_WindowsDeleteString
0x18003994a  mov     [rbp+string], 0
0x180039952  lea     rcx, [rbp+var_28]
0x180039956  call    ??1?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(void)
0x18003995b  nop
0x18003995c  lea     rcx, [rbp+arg_18]
0x180039960  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039965  mov     esi, ebx
0x180039967  jmp     short loc_18003999C
0x180039969  lea     rcx, [rbp+var_28]
0x18003996d  call    ??1?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(void)
0x180039972  mov     esi, dword ptr [rbp+arg_0]
0x180039975  test    esi, esi
0x180039977  jns     short loc_1800399A9
0x180039979  mov     r9d, esi; char *
0x18003997c  mov     edx, 12Dh; void *
0x180039981  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180039988  mov     rcx, [rbp+28h]; this
0x18003998c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039991  nop
0x180039992  lea     rcx, [rbp+arg_18]
0x180039996  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003999b  nop
0x18003999c  lea     rcx, [rbp+var_40]
0x1800399a0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800399a5  mov     eax, esi
0x1800399a7  jmp     short loc_1800399C5
0x1800399a9  lea     rcx, [rbp+arg_18]
0x1800399ad  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800399b2  nop
0x1800399b3  lea     rcx, [rbp+var_40]
0x1800399b7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800399bc  xor     eax, eax
0x1800399be  jmp     short loc_1800399C5
0x1800399c0  mov     eax, 1
0x1800399c5  add     rsp, 70h
0x1800399c9  pop     r14
0x1800399cb  pop     rdi
0x1800399cc  pop     rsi
0x1800399cd  pop     rbx
0x1800399ce  pop     rbp
0x1800399cf  retn
```
