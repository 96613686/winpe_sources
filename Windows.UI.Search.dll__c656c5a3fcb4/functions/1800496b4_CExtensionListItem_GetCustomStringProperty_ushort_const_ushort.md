# CExtensionListItem::_GetCustomStringProperty(ushort const *,ushort * *)

- ea: `0x1800496b4`
- end: `0x18004982d`
- name: `?_GetCustomStringProperty@CExtensionListItem@@AEAAJPEBGPEAPEAG@Z`
- size: `377`
- prototype: `int(CExtensionListItem *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800491a8`

## callees

- `0x180007b3c`
- `0x18001599c`
- `0x180015a18`
- `0x180015a78`
- `0x180015ab8`
- `0x18001f424`
- `0x18002b230`
- `0x1800496b4`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049753`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800497cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800497cb`

## pseudocode

```c
__int64 __fastcall CExtensionListItem::_GetCustomStringProperty(
        CExtensionListItem *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 **); // rbx
  int v6; // edi
  __int64 v7; // rbx
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  UINT32 length[2]; // [rsp+30h] [rbp-29h] BYREF
  __int64 v15; // [rsp+38h] [rbp-21h] BYREF
  __int64 *v16; // [rsp+40h] [rbp-19h] BYREF
  __int64 v17; // [rsp+48h] [rbp-11h] BYREF
  int v18; // [rsp+50h] [rbp-9h]
  __int64 v19; // [rsp+58h] [rbp-1h] BYREF
  int v20; // [rsp+60h] [rbp+7h]
  HSTRING string; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+17h] BYREF

  *a3 = 0;
  v4 = *((_QWORD *)this + 4);
  v16 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v4 + 128LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v16);
  v6 = v5(v4, &v16);
  if ( v6 >= 0 )
  {
    v7 = -1;
    v17 = 0;
    v8 = -1;
    v18 = 0;
    length[0] = 0;
    do
      ++v8;
    while ( a2[v8] );
    if ( (int)ULongLongToULong(v8, length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(a2, length[0], &hstringHeader, &string);
    v9 = *v16;
    *(_QWORD *)length = &v17;
    v15 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v9 + 48))(v16, string, &v15);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)length);
    if ( v6 >= 0 )
    {
      v19 = v17;
      v20 = v18;
      *(_QWORD *)length = 0;
      v6 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v19, (HSTRING *)length);
      if ( v6 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)length, 0);
        do
          ++v7;
        while ( StringRawBuffer[v7] );
        v6 = _AllocStringWorker<CTCoAllocPolicy>(v12, v11, StringRawBuffer);
      }
      Windows::Internal::String::~String((Windows::Internal::String *)length);
    }
    RoVariant::~RoVariant((RoVariant *)&v17);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800496b4  mov     [rsp-8+arg_18], rbx
0x1800496b9  push    rbp
0x1800496ba  push    rsi
0x1800496bb  push    rdi
0x1800496bc  push    r14
0x1800496be  push    r15
0x1800496c0  lea     rbp, [rsp-37h]
0x1800496c5  sub     rsp, 90h
0x1800496cc  mov     rax, cs:__security_cookie
0x1800496d3  xor     rax, rsp
0x1800496d6  mov     [rbp+57h+var_28], rax
0x1800496da  xor     r15d, r15d
0x1800496dd  mov     r14, r8
0x1800496e0  mov     [r8], r15
0x1800496e3  mov     rsi, rdx
0x1800496e6  mov     rdi, [rcx+20h]
0x1800496ea  lea     rcx, [rbp+57h+var_70]
0x1800496ee  mov     [rbp+57h+var_70], r15
0x1800496f2  mov     rax, [rdi]
0x1800496f5  mov     rbx, [rax+80h]
0x1800496fc  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180049701  lea     rdx, [rbp+57h+var_70]
0x180049705  mov     rcx, rdi
0x180049708  mov     rax, rbx
0x18004970b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049710  mov     edi, eax
0x180049712  test    eax, eax
0x180049714  js      loc_1800497FF
0x18004971a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004971e  mov     [rbp+57h+var_68], r15
0x180049722  mov     rcx, rbx
0x180049725  mov     [rbp+57h+var_60], r15d
0x180049729  mov     [rbp+57h+length], r15d
0x18004972d  inc     rcx; unsigned __int64
0x180049730  cmp     [rsi+rcx*2], r15w
0x180049735  jnz     short loc_18004972D
0x180049737  lea     rdx, [rbp+57h+length]; unsigned int *
0x18004973b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180049740  test    eax, eax
0x180049742  jns     short loc_180049759
0x180049744  xor     r9d, r9d; lpArguments
0x180049747  xor     r8d, r8d; nNumberOfArguments
0x18004974a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004974f  lea     edx, [r9+1]; dwExceptionFlags
0x180049753  call    cs:__imp_RaiseException
0x180049759  mov     edx, [rbp+57h+length]; length
0x18004975c  lea     r9, [rbp+57h+string]; string
0x180049760  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180049764  mov     rcx, rsi; sourceString
0x180049767  call    cs:__imp_WindowsCreateStringReference
0x18004976d  mov     rcx, [rbp+57h+var_70]
0x180049771  lea     rdx, [rbp+57h+var_68]
0x180049775  lea     r8, [rbp+57h+var_78]
0x180049779  mov     rax, [rcx]
0x18004977c  mov     qword ptr [rbp+57h+length], rdx
0x180049780  mov     rdx, [rbp+57h+string]
0x180049784  mov     [rbp+57h+var_78], r15
0x180049788  mov     rax, [rax+30h]
0x18004978c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049791  lea     rcx, [rbp+57h+length]; this
0x180049795  mov     edi, eax
0x180049797  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x18004979c  test    edi, edi
0x18004979e  js      short loc_1800497F6
0x1800497a0  mov     rax, [rbp+57h+var_68]
0x1800497a4  lea     rdx, [rbp+57h+length]; HSTRING *
0x1800497a8  mov     [rbp+57h+var_58], rax
0x1800497ac  lea     rcx, [rbp+57h+var_58]; this
0x1800497b0  mov     eax, [rbp+57h+var_60]
0x1800497b3  mov     [rbp+57h+var_50], eax
0x1800497b6  mov     qword ptr [rbp+57h+length], r15
0x1800497ba  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x1800497bf  mov     edi, eax
0x1800497c1  test    eax, eax
0x1800497c3  js      short loc_1800497ED
0x1800497c5  mov     rcx, qword ptr [rbp+57h+length]; string
0x1800497c9  xor     edx, edx; length
0x1800497cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800497d1  inc     rbx
0x1800497d4  cmp     [rax+rbx*2], r15w
0x1800497d9  jnz     short loc_1800497D1
0x1800497db  mov     r9, rbx
0x1800497de  mov     [rsp+0B0h+var_88], r14
0x1800497e3  mov     r8, rax
0x1800497e6  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800497eb  mov     edi, eax
0x1800497ed  lea     rcx, [rbp+57h+length]; this
0x1800497f1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800497f6  lea     rcx, [rbp+57h+var_68]; this
0x1800497fa  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800497ff  lea     rcx, [rbp+57h+var_70]
0x180049803  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180049808  mov     eax, edi
0x18004980a  mov     rcx, [rbp+57h+var_28]
0x18004980e  xor     rcx, rsp; StackCookie
0x180049811  call    __security_check_cookie
0x180049816  mov     rbx, [rsp+0B0h+arg_18]
0x18004981e  add     rsp, 90h
0x180049825  pop     r15
0x180049827  pop     r14
0x180049829  pop     rdi
0x18004982a  pop     rsi
0x18004982b  pop     rbp
0x18004982c  retn
```
