# GetIsMultiInstanceFromExtensionRegistration(Windows::Foundation::IExtensionRegistration *,bool *,bool *)

- ea: `0x180032464`
- end: `0x18003280f`
- name: `?GetIsMultiInstanceFromExtensionRegistration@@YAJPEAUIExtensionRegistration@Foundation@Windows@@PEA_N1@Z`
- size: `939`
- prototype: `__int64 __fastcall(struct Windows::Foundation::IExtensionRegistration *, bool *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007ea90`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180031540`
- `0x180032464`
- `0x180032820`
- `0x180034430`
- `0x180037824`
- `0x18005ae90`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032544`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032544`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003277b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003277b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800326f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003272b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032795`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800326f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003272b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032795`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003275d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003275d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003252e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003252e`

## string_xrefs

- `0x1800324c9`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`
- `0x18003264e`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`
- `0x180032715`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall GetIsMultiInstanceFromExtensionRegistration(
        struct Windows::Foundation::IExtensionRegistration *a1,
        bool *a2,
        bool *a3)
{
  HSTRING v5; // rsi
  int v6; // eax
  unsigned int v7; // ebx
  __int64 *v8; // rcx
  __int64 *v10; // rbx
  __int64 v11; // rdi
  HRESULT v12; // eax
  bool v13; // r12
  HSTRING *v14; // r14
  HSTRING v15; // rbx
  int v16; // edi
  int v17; // eax
  HSTRING v18; // rcx
  int v19; // eax
  __int64 *v20; // rdi
  unsigned int (__fastcall *v21)(__int64 *, HSTRING, struct IInspectable **); // rbx
  int v22; // eax
  const WCHAR *StringRawBuffer; // rax
  __int64 *v24; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-59h]
  __int64 *v26; // [rsp+30h] [rbp-49h] BYREF
  HSTRING v27; // [rsp+38h] [rbp-41h] BYREF
  struct IInspectable *v28; // [rsp+40h] [rbp-39h] BYREF
  int v29; // [rsp+48h] [rbp-31h] BYREF
  HSTRING *v30; // [rsp+50h] [rbp-29h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, HSTRING *); // [rsp+58h] [rbp-21h] BYREF
  __int64 v32; // [rsp+60h] [rbp-19h] BYREF
  char *v33; // [rsp+68h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  HSTRING string; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v5 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( a1 )
  {
    v26 = 0;
    v6 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IExtensionRegistration *, __int64 **))(*(_QWORD *)a1 + 128LL))(
           a1,
           &v26);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
        (const char *)(unsigned int)v6,
        bIgnoreCase);
      v8 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64 *))(*v8 + 16))(v8);
      }
      return v7;
    }
    v32 = 0;
    LODWORD(v33) = 0;
    v10 = v26;
    v11 = *v26;
    v30 = (HSTRING *)&v32;
    v31 = 0;
    string = 0;
    v12 = WindowsCreateStringReference(L"SupportsMultipleInstances", 0x19u, &hstringHeader, &string);
    if ( v12 < 0 )
      RaiseException(v12, 1u, 0, 0);
    v13 = (*(int (__fastcall **)(__int64 *, HSTRING, _QWORD))(v11 + 48))(v10, string, &v31) >= 0;
    string = 0;
    v14 = v30;
    v15 = (HSTRING)v31;
    if ( v31 )
    {
      v27 = 0;
      v17 = (**v31)(v31, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v27);
      v16 = v17;
      if ( v17 < 0 )
      {
        if ( v17 == -2147467262 )
        {
          v5 = v15;
          v16 = 3;
        }
        else
        {
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v15 + 16LL))(v15);
        }
      }
      else
      {
        v5 = v27;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v15 + 16LL))(v15);
        v16 = 7;
      }
    }
    else
    {
      v16 = 0;
    }
    v18 = *v14;
    *v14 = v5;
    v19 = *((_DWORD *)v14 + 2);
    *((_DWORD *)v14 + 2) = v16;
    if ( v18 && ((v19 - 3) & 0xFFFFFFFB) == 0 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v13 )
    {
      v29 = 0;
      if ( (_DWORD)v33 != 7 )
      {
        v7 = -2147316576;
        if ( (int)v33 < 0 )
          v7 = (unsigned int)v33;
        goto LABEL_24;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 96LL))(v32, &v29);
      if ( (v7 & 0x80000000) != 0 )
      {
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x145,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
          (const char *)v7,
          bIgnoreCase);
LABEL_29:
        RoVariant::~RoVariant((RoVariant *)&v32);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
        return v7;
      }
      if ( v29 )
      {
        v30 = 0;
        LODWORD(v31) = 0;
        v20 = v26;
        v21 = *(unsigned int (__fastcall **)(__int64 *, HSTRING, struct IInspectable **))(*v26 + 48);
        v27 = (HSTRING)&v30;
        v28 = 0;
        string = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Subsystem", 0xAu, 9u);
        LODWORD(v21) = v21(v20, string, &v28) >> 31;
        string = 0;
        RoVariant::Attach((RoVariant *)v27, v28);
        if ( (unsigned __int8)v21 != 1 )
        {
          v27 = 0;
          hstringHeader.Reserved.Reserved1 = v30;
          *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = (_DWORD)v31;
          WindowsDeleteString(0);
          v27 = 0;
          v22 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&hstringHeader, &v27);
          v7 = v22;
          if ( v22 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x14D,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
              (const char *)(unsigned int)v22,
              bIgnoreCase);
            WindowsDeleteString(v27);
            v27 = 0;
            RoVariant::~RoVariant((RoVariant *)&v30);
            goto LABEL_29;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(v27, 0);
          if ( CompareStringOrdinal(StringRawBuffer, -1, L"Console", -1, 1) == 2 )
            *a3 = 1;
          else
            *a2 = 1;
          WindowsDeleteString(v27);
        }
        else
        {
          *a2 = 1;
        }
        RoVariant::~RoVariant((RoVariant *)&v30);
      }
    }
    if ( v32 && (((_DWORD)v33 - 3) & 0xFFFFFFFB) == 0 )
      (*(void (**)(void))(*(_QWORD *)v32 + 16LL))();
    v24 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180032464  mov     [rsp-8+arg_18], rbx
0x180032469  push    rbp
0x18003246a  push    rsi
0x18003246b  push    rdi
0x18003246c  push    r12
0x18003246e  push    r13
0x180032470  push    r14
0x180032472  push    r15
0x180032474  lea     rbp, [rsp-27h]
0x180032479  sub     rsp, 0A0h
0x180032480  mov     rax, cs:__security_cookie
0x180032487  xor     rax, rsp
0x18003248a  mov     [rbp+57h+var_40], rax
0x18003248e  mov     r13, r8
0x180032491  mov     r15, rdx
0x180032494  xor     esi, esi
0x180032496  mov     [rdx], sil
0x180032499  mov     [r8], sil
0x18003249c  test    rcx, rcx
0x18003249f  jz      loc_1800327E6
0x1800324a5  mov     [rbp+57h+var_A0], rsi
0x1800324a9  mov     rax, [rcx]
0x1800324ac  lea     rdx, [rbp+57h+var_A0]
0x1800324b0  mov     rax, [rax+80h]
0x1800324b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324bc  mov     ebx, eax
0x1800324be  test    eax, eax
0x1800324c0  jns     short loc_1800324FC
0x1800324c2  mov     rcx, [rbp+5Fh]; this
0x1800324c6  mov     r9d, eax; char *
0x1800324c9  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800324d0  mov     edx, 13Fh; void *
0x1800324d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800324da  nop
0x1800324db  mov     rcx, [rbp+57h+var_A0]
0x1800324df  test    rcx, rcx
0x1800324e2  jz      short loc_1800324F5
0x1800324e4  mov     [rbp+57h+var_A0], rsi
0x1800324e8  mov     rax, [rcx]
0x1800324eb  mov     rax, [rax+10h]
0x1800324ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324f4  nop
0x1800324f5  mov     eax, ebx
0x1800324f7  jmp     loc_1800327E8
0x1800324fc  mov     [rbp+57h+var_70], rsi
0x180032500  mov     dword ptr [rbp+57h+var_68], esi
0x180032503  mov     rbx, [rbp+57h+var_A0]
0x180032507  mov     rdi, [rbx]
0x18003250a  lea     rax, [rbp+57h+var_70]
0x18003250e  mov     [rbp+57h+var_80], rax
0x180032512  mov     [rbp+57h+var_78], rsi
0x180032516  mov     [rbp+57h+string], rsi
0x18003251a  lea     r9, [rbp+57h+string]; string
0x18003251e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180032522  mov     edx, 19h; length
0x180032527  lea     rcx, aSupportsmultip; "SupportsMultipleInstances"
0x18003252e  call    cs:__imp_WindowsCreateStringReference
0x180032534  test    eax, eax
0x180032536  jns     short loc_18003254B
0x180032538  xor     r9d, r9d; lpArguments
0x18003253b  xor     r8d, r8d; nNumberOfArguments
0x18003253e  lea     edx, [r9+1]; dwExceptionFlags
0x180032542  mov     ecx, eax; dwExceptionCode
0x180032544  call    cs:__imp_RaiseException
0x18003254a  nop
0x18003254b  lea     r8, [rbp+57h+var_78]
0x18003254f  mov     rdx, [rbp+57h+string]
0x180032553  mov     rcx, rbx
0x180032556  mov     rax, [rdi+30h]
0x18003255a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003255f  mov     r12d, eax
0x180032562  shr     r12d, 1Fh
0x180032566  xor     r12b, 1
0x18003256a  mov     [rbp+57h+string], rsi
0x18003256e  mov     r14, [rbp+57h+var_80]
0x180032572  mov     rbx, [rbp+57h+var_78]
0x180032576  test    rbx, rbx
0x180032579  jnz     short loc_18003257F
0x18003257b  xor     edi, edi
0x18003257d  jmp     short loc_1800325DD
0x18003257f  mov     [rbp+57h+var_98], rsi
0x180032583  mov     rax, [rbx]
0x180032586  lea     r8, [rbp+57h+var_98]
0x18003258a  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180032591  mov     rcx, rbx
0x180032594  mov     rax, [rax]
0x180032597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003259c  mov     edi, eax
0x18003259e  test    eax, eax
0x1800325a0  js      short loc_1800325BC
0x1800325a2  mov     rsi, [rbp+57h+var_98]
0x1800325a6  mov     rax, [rbx]
0x1800325a9  mov     rcx, rbx
0x1800325ac  mov     rax, [rax+10h]
0x1800325b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325b5  mov     edi, 7
0x1800325ba  jmp     short loc_1800325DD
0x1800325bc  cmp     eax, 80004002h
0x1800325c1  jnz     short loc_1800325CD
0x1800325c3  mov     rsi, rbx
0x1800325c6  mov     edi, 3
0x1800325cb  jmp     short loc_1800325DD
0x1800325cd  mov     rax, [rbx]
0x1800325d0  mov     rcx, rbx
0x1800325d3  mov     rax, [rax+10h]
0x1800325d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325dc  nop
0x1800325dd  mov     rcx, [r14]
0x1800325e0  mov     [r14], rsi
0x1800325e3  mov     eax, [r14+8]
0x1800325e7  mov     [r14+8], edi
0x1800325eb  xor     esi, esi
0x1800325ed  mov     r14d, 0FFFFFFFBh
0x1800325f3  test    rcx, rcx
0x1800325f6  jz      short loc_18003260D
0x1800325f8  add     eax, 0FFFFFFFDh
0x1800325fb  test    r14d, eax
0x1800325fe  jnz     short loc_18003260D
0x180032600  mov     rax, [rcx]
0x180032603  mov     rax, [rax+10h]
0x180032607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003260c  nop
0x18003260d  test    r12b, r12b
0x180032610  jz      loc_1800327AB
0x180032616  mov     eax, dword ptr [rbp+57h+var_68]
0x180032619  mov     [rbp+57h+var_88], esi
0x18003261c  cmp     eax, 7
0x18003261f  jz      short loc_18003262D
0x180032621  mov     ebx, 80028CA0h
0x180032626  test    eax, eax
0x180032628  cmovs   ebx, eax
0x18003262b  jmp     short loc_180032647
0x18003262d  mov     rcx, [rbp+57h+var_70]
0x180032631  mov     rax, [rcx]
0x180032634  lea     rdx, [rbp+57h+var_88]
0x180032638  mov     rax, [rax+60h]
0x18003263c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032641  mov     ebx, eax
0x180032643  test    eax, eax
0x180032645  jns     short loc_180032664
0x180032647  mov     rcx, [rbp+5Fh]; this
0x18003264b  mov     r9d, ebx; char *
0x18003264e  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180032655  mov     edx, 145h; void *
0x18003265a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003265f  jmp     loc_18003273F
0x180032664  cmp     [rbp+57h+var_88], esi
0x180032667  jz      loc_1800327AB
0x18003266d  mov     [rbp+57h+var_80], rsi
0x180032671  mov     dword ptr [rbp+57h+var_78], esi
0x180032674  mov     rdi, [rbp+57h+var_A0]
0x180032678  mov     rax, [rdi]
0x18003267b  mov     rbx, [rax+30h]
0x18003267f  lea     rax, [rbp+57h+var_80]
0x180032683  mov     [rbp+57h+var_98], rax
0x180032687  mov     [rbp+57h+var_90], rsi
0x18003268b  mov     [rbp+57h+string], rsi
0x18003268f  mov     r9d, 9; unsigned int
0x180032695  lea     r8d, [r9+1]; unsigned int
0x180032699  lea     rdx, aSubsystem; "Subsystem"
0x1800326a0  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800326a4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800326a9  nop
0x1800326aa  lea     r8, [rbp+57h+var_90]
0x1800326ae  mov     rdx, [rbp+57h+string]
0x1800326b2  mov     rcx, rdi
0x1800326b5  mov     rax, rbx
0x1800326b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800326bd  mov     ebx, eax
0x1800326bf  shr     ebx, 1Fh
0x1800326c2  mov     [rbp+57h+string], rsi
0x1800326c6  mov     rdx, [rbp+57h+var_90]; struct IInspectable *
0x1800326ca  mov     rcx, [rbp+57h+var_98]; this
0x1800326ce  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x1800326d3  nop
0x1800326d4  xor     bl, 1
0x1800326d7  jz      loc_18003279D
0x1800326dd  mov     [rbp+57h+var_98], rsi
0x1800326e1  mov     rax, [rbp+57h+var_80]
0x1800326e5  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800326e9  mov     eax, dword ptr [rbp+57h+var_78]
0x1800326ec  mov     dword ptr [rbp+57h+hstringHeader.Reserved+8], eax
0x1800326ef  xor     ecx, ecx; string
0x1800326f1  call    cs:__imp_WindowsDeleteString
0x1800326f7  mov     [rbp+57h+var_98], rsi
0x1800326fb  lea     rdx, [rbp+57h+var_98]; HSTRING *
0x1800326ff  lea     rcx, [rbp+57h+hstringHeader]; this
0x180032703  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x180032708  mov     ebx, eax
0x18003270a  test    eax, eax
0x18003270c  jns     short loc_180032757
0x18003270e  mov     rcx, [rbp+5Fh]; this
0x180032712  mov     r9d, eax; char *
0x180032715  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18003271c  mov     edx, 14Dh; void *
0x180032721  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032726  nop
0x180032727  mov     rcx, [rbp+57h+var_98]; string
0x18003272b  call    cs:__imp_WindowsDeleteString
0x180032731  mov     [rbp+57h+var_98], rsi
0x180032735  lea     rcx, [rbp+57h+var_80]; this
0x180032739  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18003273e  nop
0x18003273f  lea     rcx, [rbp+57h+var_70]; this
0x180032743  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180032748  nop
0x180032749  lea     rcx, [rbp+57h+var_A0]
0x18003274d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180032752  jmp     loc_1800324F5
0x180032757  xor     edx, edx; length
0x180032759  mov     rcx, [rbp+57h+var_98]; string
0x18003275d  call    cs:__imp_WindowsGetStringRawBuffer
0x180032763  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18003276b  or      edx, 0FFFFFFFFh; cchCount1
0x18003276e  mov     r9d, edx; cchCount2
0x180032771  lea     r8, aConsole; "Console"
0x180032778  mov     rcx, rax; lpString1
0x18003277b  call    cs:__imp_CompareStringOrdinal
0x180032781  cmp     eax, 2
0x180032784  jnz     short loc_18003278D
0x180032786  mov     byte ptr [r13+0], 1
0x18003278b  jmp     short loc_180032791
0x18003278d  mov     byte ptr [r15], 1
0x180032791  mov     rcx, [rbp+57h+var_98]; string
0x180032795  call    cs:__imp_WindowsDeleteString
0x18003279b  jmp     short loc_1800327A1
0x18003279d  mov     byte ptr [r15], 1
0x1800327a1  lea     rcx, [rbp+57h+var_80]; this
0x1800327a5  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800327aa  nop
0x1800327ab  mov     rcx, [rbp+57h+var_70]
0x1800327af  test    rcx, rcx
0x1800327b2  jz      short loc_1800327CC
0x1800327b4  mov     eax, dword ptr [rbp+57h+var_68]
0x1800327b7  add     eax, 0FFFFFFFDh
0x1800327ba  test    r14d, eax
0x1800327bd  jnz     short loc_1800327CC
0x1800327bf  mov     rax, [rcx]
0x1800327c2  mov     rax, [rax+10h]
0x1800327c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327cb  nop
0x1800327cc  mov     rcx, [rbp+57h+var_A0]
0x1800327d0  test    rcx, rcx
0x1800327d3  jz      short loc_1800327E6
0x1800327d5  mov     [rbp+57h+var_A0], rsi
0x1800327d9  mov     rax, [rcx]
0x1800327dc  mov     rax, [rax+10h]
0x1800327e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327e5  nop
0x1800327e6  xor     eax, eax
0x1800327e8  mov     rcx, [rbp+57h+var_40]
0x1800327ec  xor     rcx, rsp; StackCookie
0x1800327ef  call    __security_check_cookie
0x1800327f4  mov     rbx, [rsp+0D0h+arg_18]
0x1800327fc  add     rsp, 0A0h
0x180032803  pop     r15
0x180032805  pop     r14
0x180032807  pop     r13
0x180032809  pop     r12
0x18003280b  pop     rdi
0x18003280c  pop     rsi
0x18003280d  pop     rbp
0x18003280e  retn
```
