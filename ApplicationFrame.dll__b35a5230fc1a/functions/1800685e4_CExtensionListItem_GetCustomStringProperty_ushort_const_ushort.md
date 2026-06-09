# CExtensionListItem::_GetCustomStringProperty(ushort const *,ushort * *)

- ea: `0x1800685e4`
- end: `0x180068797`
- name: `?_GetCustomStringProperty@CExtensionListItem@@AEAAJPEBGPEAPEAG@Z`
- size: `435`
- prototype: `int(CExtensionListItem *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180067f84`

## callees

- `0x18002dc90`
- `0x18003f150`
- `0x180041764`
- `0x180043c30`
- `0x18006295c`
- `0x180062c98`
- `0x180062ccc`
- `0x1800685e4`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006867e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006867e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180068747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180068747`

## pseudocode

```c
__int64 __fastcall CExtensionListItem::_GetCustomStringProperty(
        CExtensionListItem *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 **); // rbx
  int v7; // r14d
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  HSTRING *v11; // rsi
  bool v12; // r8
  bool v13; // r9
  HSTRING v14; // rbx
  int v15; // edi
  HSTRING v16; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  UINT32 length[2]; // [rsp+20h] [rbp-60h] BYREF
  int v22; // [rsp+28h] [rbp-58h]
  __int64 *v23; // [rsp+30h] [rbp-50h] BYREF
  __int64 v24; // [rsp+38h] [rbp-48h] BYREF
  int v25; // [rsp+40h] [rbp-40h]
  HSTRING *v26; // [rsp+48h] [rbp-38h]
  struct IInspectable *v27; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-20h] BYREF

  *a3 = 0;
  v5 = *((_QWORD *)this + 4);
  v23 = 0;
  v6 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v5 + 128LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&v23);
  v7 = v6(v5, &v23);
  if ( v7 >= 0 )
  {
    v24 = 0;
    v8 = -1;
    v25 = 0;
    length[0] = 0;
    do
      ++v8;
    while ( a2[v8] );
    if ( (int)ULongLongToULong(v8, length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(a2, length[0], &hstringHeader, &string);
    v9 = *v23;
    v26 = (HSTRING *)&v24;
    v27 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, struct IInspectable **))(v9 + 48))(v23, string, &v27);
    v11 = v26;
    v7 = v10;
    RoVariant::RoVariant((RoVariant *)length, v27, v12, v13);
    v14 = *(HSTRING *)length;
    v15 = v22;
    *(_QWORD *)length = 0;
    v22 = 0;
    RoVariant::~RoVariant((RoVariant *)length);
    v16 = *v11;
    *v11 = v14;
    *(_QWORD *)length = v16;
    LODWORD(v16) = *((_DWORD *)v11 + 2);
    *((_DWORD *)v11 + 2) = v15;
    v22 = (int)v16;
    RoVariant::~RoVariant((RoVariant *)length);
    if ( v7 >= 0 )
    {
      *(_QWORD *)length = 0;
      if ( v25 == 7 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v24 + 152LL))(v24, length);
        if ( v7 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)length, 0);
          v7 = _AllocString<CTCoAllocPolicy>(v19, v18, StringRawBuffer, a3);
        }
      }
      else
      {
        v7 = -2147316576;
        if ( v25 < 0 )
          v7 = v25;
      }
      Windows::Internal::String::~String((Windows::Internal::String *)length);
    }
    RoVariant::~RoVariant((RoVariant *)&v24);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&v23);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800685e4  push    rbp
0x1800685e6  push    rbx
0x1800685e7  push    rsi
0x1800685e8  push    rdi
0x1800685e9  push    r12
0x1800685eb  push    r14
0x1800685ed  push    r15
0x1800685ef  mov     rbp, rsp
0x1800685f2  sub     rsp, 80h
0x1800685f9  mov     rax, cs:__security_cookie
0x180068600  xor     rax, rsp
0x180068603  mov     [rbp+var_8], rax
0x180068607  xor     r12d, r12d
0x18006860a  mov     r15, r8
0x18006860d  mov     [r8], r12
0x180068610  mov     rsi, rdx
0x180068613  mov     rdi, [rcx+20h]
0x180068617  lea     rcx, [rbp+var_50]
0x18006861b  mov     [rbp+var_50], r12
0x18006861f  mov     rax, [rdi]
0x180068622  mov     rbx, [rax+80h]
0x180068629  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18006862e  lea     rdx, [rbp+var_50]
0x180068632  mov     rcx, rdi
0x180068635  mov     rax, rbx
0x180068638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006863d  mov     r14d, eax
0x180068640  test    eax, eax
0x180068642  js      loc_18006876D
0x180068648  mov     [rbp+var_48], r12
0x18006864c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180068650  mov     [rbp+var_40], r12d
0x180068654  mov     [rbp+length], r12d
0x180068658  inc     rcx; unsigned __int64
0x18006865b  cmp     [rsi+rcx*2], r12w
0x180068660  jnz     short loc_180068658
0x180068662  lea     rdx, [rbp+length]; unsigned int *
0x180068666  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18006866b  test    eax, eax
0x18006866d  jns     short loc_180068684
0x18006866f  xor     r9d, r9d; lpArguments
0x180068672  xor     r8d, r8d; nNumberOfArguments
0x180068675  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006867a  lea     edx, [r9+1]; dwExceptionFlags
0x18006867e  call    cs:__imp_RaiseException
0x180068684  mov     edx, [rbp+length]; length
0x180068687  lea     r9, [rbp+string]; string
0x18006868b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18006868f  mov     rcx, rsi; sourceString
0x180068692  call    cs:__imp_WindowsCreateStringReference
0x180068698  mov     rcx, [rbp+var_50]
0x18006869c  lea     rdx, [rbp+var_48]
0x1800686a0  lea     r8, [rbp+var_30]
0x1800686a4  mov     rax, [rcx]
0x1800686a7  mov     [rbp+var_38], rdx
0x1800686ab  mov     rdx, [rbp+string]
0x1800686af  mov     [rbp+var_30], r12
0x1800686b3  mov     rax, [rax+30h]
0x1800686b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800686bc  mov     rdx, [rbp+var_30]; struct IInspectable *
0x1800686c0  lea     rcx, [rbp+length]; this
0x1800686c4  mov     rsi, [rbp+var_38]
0x1800686c8  mov     r14d, eax
0x1800686cb  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x1800686d0  mov     rbx, qword ptr [rbp+length]
0x1800686d4  lea     rcx, [rbp+length]; this
0x1800686d8  mov     edi, [rbp+var_58]
0x1800686db  mov     qword ptr [rbp+length], r12
0x1800686df  mov     [rbp+var_58], r12d
0x1800686e3  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800686e8  mov     rax, [rsi]
0x1800686eb  lea     rcx, [rbp+length]; this
0x1800686ef  mov     [rsi], rbx
0x1800686f2  mov     qword ptr [rbp+length], rax
0x1800686f6  mov     eax, [rsi+8]
0x1800686f9  mov     [rsi+8], edi
0x1800686fc  mov     [rbp+var_58], eax
0x1800686ff  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180068704  test    r14d, r14d
0x180068707  js      short loc_180068764
0x180068709  mov     eax, [rbp+var_40]
0x18006870c  mov     qword ptr [rbp+length], r12
0x180068710  cmp     eax, 7
0x180068713  jz      short loc_180068723
0x180068715  test    eax, eax
0x180068717  mov     r14d, 80028CA0h
0x18006871d  cmovs   r14d, eax
0x180068721  jmp     short loc_18006875B
0x180068723  mov     rcx, [rbp+var_48]
0x180068727  lea     rdx, [rbp+length]
0x18006872b  mov     rax, [rcx]
0x18006872e  mov     rax, [rax+98h]
0x180068735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006873a  mov     r14d, eax
0x18006873d  test    eax, eax
0x18006873f  js      short loc_18006875B
0x180068741  mov     rcx, qword ptr [rbp+length]; string
0x180068745  xor     edx, edx; length
0x180068747  call    cs:__imp_WindowsGetStringRawBuffer
0x18006874d  mov     r8, rax
0x180068750  mov     r9, r15
0x180068753  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180068758  mov     r14d, eax
0x18006875b  lea     rcx, [rbp+length]; this
0x18006875f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180068764  lea     rcx, [rbp+var_48]; this
0x180068768  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18006876d  lea     rcx, [rbp+var_50]
0x180068771  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x180068776  mov     eax, r14d
0x180068779  mov     rcx, [rbp+var_8]
0x18006877d  xor     rcx, rsp; StackCookie
0x180068780  call    __security_check_cookie
0x180068785  add     rsp, 80h
0x18006878c  pop     r15
0x18006878e  pop     r14
0x180068790  pop     r12
0x180068792  pop     rdi
0x180068793  pop     rsi
0x180068794  pop     rbx
0x180068795  pop     rbp
0x180068796  retn
```
