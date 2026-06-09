# BipIsVoipPackage

- ea: `0x1800304e8`
- end: `0x18003083f`
- name: `BipIsVoipPackage`
- size: `855`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005df20`
- `0x180081df0`

## callees

- `0x18001ef7c`
- `0x1800304e8`
- `0x180030850`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800307fe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030811`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030838`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800307fe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030811`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030838`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800305f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030727`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800305f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030727`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030566`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030611`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030566`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030611`

## string_xrefs

- `0x1800305ed`: `Windows.Internal.StateRepository.ApplicationExtension`

## pseudocode

```c
__int64 __fastcall BipIsVoipPackage(const WCHAR *a1, _BYTE *a2, int *a3)
{
  HRESULT v5; // eax
  int ActivationFactory; // edi
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, PVOID, __int64 *); // rdi
  HSTRING_HEADER *v9; // rax
  _QWORD *v10; // rcx
  HRESULT v11; // eax
  unsigned int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int i; // esi
  _QWORD *v18; // rdi
  __int64 v19; // rcx
  __int64 v20; // r14
  HRESULT v21; // eax
  __int64 v22; // rcx
  const WCHAR *v23; // rcx
  const WCHAR *v24; // rcx
  __int64 v25; // [rsp+30h] [rbp-39h] BYREF
  const WCHAR *v26; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v27; // [rsp+40h] [rbp-29h] BYREF
  __int64 v28; // [rsp+48h] [rbp-21h] BYREF
  _QWORD *v29; // [rsp+50h] [rbp-19h] BYREF
  __int64 v30; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-9h] BYREF
  HSTRING string; // [rsp+78h] [rbp+Fh] BYREF

  v26 = a1;
  *a2 = 0;
  v30 = 0;
  v28 = 0;
  v29 = 0;
  v27 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v30);
  if ( ActivationFactory < 0 )
    goto LABEL_8;
  v7 = v30;
  v8 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v30 + 264LL);
  v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v26);
  ActivationFactory = v8(v7, v9[1].Reserved.Reserved1, &v28);
  if ( ActivationFactory < 0 )
    goto LABEL_8;
  v10 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
  }
  string = 0;
  v11 = WindowsCreateStringReference(
          L"Windows.Internal.StateRepository.ApplicationExtension",
          0x35u,
          &hstringHeader,
          &string);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12, &v29);
  if ( ActivationFactory < 0
    || (ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 56LL))(v28, &v27),
        ActivationFactory < 0) )
  {
LABEL_8:
    v12 = -1073741823;
  }
  else
  {
    v12 = 0;
    for ( i = 0; i < v27; ++i )
    {
      v26 = 0;
      v25 = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, const WCHAR **))(*(_QWORD *)v28 + 48LL))(
                            v28,
                            i,
                            &v26);
      if ( ActivationFactory < 0 )
        goto LABEL_37;
      v18 = v29;
      v19 = v25;
      v20 = *v29;
      if ( v25 )
      {
        v25 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      string = 0;
      v21 = WindowsCreateStringReference(L"windows.voipCall", 0x10u, &hstringHeader, &string);
      if ( v21 < 0 )
      {
        RaiseException(v21, 1u, 0, 0);
        JUMPOUT(0x18003083ELL);
      }
      ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, const WCHAR *, HSTRING, __int64 *))(v20 + 136))(
                            v18,
                            v26,
                            string,
                            &v25);
      if ( ActivationFactory < 0
        || (ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 56LL))(v25, &v27),
            ActivationFactory < 0) )
      {
LABEL_37:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
      }
      else
      {
        v22 = v25;
        if ( v27 )
        {
          *a2 = 1;
          if ( v22 )
          {
            v25 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
          v24 = v26;
          if ( v26 )
          {
            v26 = 0;
            (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v24 + 16LL))(v24);
          }
          break;
        }
        if ( v25 )
        {
          v25 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        v23 = v26;
        if ( v26 )
        {
          v26 = 0;
          (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v23 + 16LL))(v23);
        }
      }
    }
  }
  v13 = v29;
  *a3 = ActivationFactory;
  if ( v13 )
  {
    v29 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
  }
  v14 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return v12;
}

```

## disassembly

```asm
0x1800304e8  mov     [rsp-8+arg_18], rbx
0x1800304ed  push    rbp
0x1800304ee  push    rsi
0x1800304ef  push    rdi
0x1800304f0  push    r12
0x1800304f2  push    r13
0x1800304f4  push    r14
0x1800304f6  push    r15
0x1800304f8  lea     rbp, [rsp-27h]
0x1800304fd  sub     rsp, 90h
0x180030504  mov     rax, cs:__security_cookie
0x18003050b  xor     rax, rsp
0x18003050e  mov     [rbp+57h+var_40], rax
0x180030512  xor     r13d, r13d
0x180030515  mov     [rbp+57h+var_88], rcx
0x180030519  mov     r12, r8
0x18003051c  mov     [rdx], r13b
0x18003051f  mov     r15, rdx
0x180030522  mov     [rbp+57h+var_68], r13
0x180030526  lea     r9, [rbp+57h+string]; string
0x18003052a  mov     [rbp+57h+var_78], r13
0x18003052e  lea     edx, [r13+2Ch]; length
0x180030532  mov     [rbp+57h+var_70], r13
0x180030536  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003053a  mov     [rbp+57h+var_80], r13d
0x18003053e  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180030545  mov     [rbp+57h+string], r13
0x180030549  call    cs:__imp_WindowsCreateStringReference
0x18003054f  test    eax, eax
0x180030551  js      loc_1800307F2
0x180030557  mov     rcx, [rbp+57h+string]
0x18003055b  lea     r8, [rbp+57h+var_68]
0x18003055f  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x180030566  call    cs:__imp_RoGetActivationFactory
0x18003056c  mov     edi, eax
0x18003056e  test    eax, eax
0x180030570  js      loc_18003061D
0x180030576  mov     rbx, [rbp+57h+var_68]
0x18003057a  mov     rcx, [rbp+57h+var_78]
0x18003057e  mov     rax, [rbx]
0x180030581  mov     rdi, [rax+108h]
0x180030588  test    rcx, rcx
0x18003058b  jz      short loc_18003059D
0x18003058d  mov     [rbp+57h+var_78], r13
0x180030591  mov     rax, [rcx]
0x180030594  mov     rax, [rax+10h]
0x180030598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003059d  lea     rdx, [rbp+57h+var_88]
0x1800305a1  lea     rcx, [rbp+57h+hstringHeader]
0x1800305a5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800305aa  lea     r8, [rbp+57h+var_78]
0x1800305ae  mov     rcx, rbx
0x1800305b1  mov     rdx, [rax+18h]
0x1800305b5  mov     rax, rdi
0x1800305b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305bd  mov     edi, eax
0x1800305bf  test    eax, eax
0x1800305c1  js      short loc_18003061D
0x1800305c3  mov     rcx, [rbp+57h+var_70]
0x1800305c7  test    rcx, rcx
0x1800305ca  jz      short loc_1800305DC
0x1800305cc  mov     [rbp+57h+var_70], r13
0x1800305d0  mov     rax, [rcx]
0x1800305d3  mov     rax, [rax+10h]
0x1800305d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305dc  lea     r9, [rbp+57h+string]; string
0x1800305e0  mov     [rbp+57h+string], r13
0x1800305e4  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800305e8  mov     edx, 35h ; '5'; length
0x1800305ed  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800305f4  call    cs:__imp_WindowsCreateStringReference
0x1800305fa  test    eax, eax
0x1800305fc  js      loc_180030805
0x180030602  mov     rcx, [rbp+57h+string]
0x180030606  lea     r8, [rbp+57h+var_70]
0x18003060a  lea     rdx, _GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12
0x180030611  call    cs:__imp_RoGetActivationFactory
0x180030617  mov     edi, eax
0x180030619  test    eax, eax
0x18003061b  jns     short loc_18003069A
0x18003061d  mov     ebx, 0C0000001h
0x180030622  mov     rcx, [rbp+57h+var_70]
0x180030626  mov     [r12], edi
0x18003062a  test    rcx, rcx
0x18003062d  jz      short loc_18003063F
0x18003062f  mov     [rbp+57h+var_70], r13
0x180030633  mov     rax, [rcx]
0x180030636  mov     rax, [rax+10h]
0x18003063a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003063f  mov     rcx, [rbp+57h+var_78]
0x180030643  test    rcx, rcx
0x180030646  jz      short loc_180030658
0x180030648  mov     [rbp+57h+var_78], r13
0x18003064c  mov     rax, [rcx]
0x18003064f  mov     rax, [rax+10h]
0x180030653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030658  mov     rcx, [rbp+57h+var_68]
0x18003065c  test    rcx, rcx
0x18003065f  jz      short loc_180030671
0x180030661  mov     [rbp+57h+var_68], r13
0x180030665  mov     rdx, [rcx]
0x180030668  mov     rax, [rdx+10h]
0x18003066c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030671  mov     eax, ebx
0x180030673  mov     rcx, [rbp+57h+var_40]
0x180030677  xor     rcx, rsp; StackCookie
0x18003067a  call    __security_check_cookie
0x18003067f  mov     rbx, [rsp+0C0h+arg_18]
0x180030687  add     rsp, 90h
0x18003068e  pop     r15
0x180030690  pop     r14
0x180030692  pop     r13
0x180030694  pop     r12
0x180030696  pop     rdi
0x180030697  pop     rsi
0x180030698  pop     rbp
0x180030699  retn
0x18003069a  mov     rcx, [rbp+57h+var_78]
0x18003069e  lea     rdx, [rbp+57h+var_80]
0x1800306a2  mov     rax, [rcx]
0x1800306a5  mov     rax, [rax+38h]
0x1800306a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306ae  mov     edi, eax
0x1800306b0  test    eax, eax
0x1800306b2  js      loc_18003061D
0x1800306b8  mov     ebx, r13d
0x1800306bb  mov     esi, r13d
0x1800306be  cmp     esi, [rbp+57h+var_80]
0x1800306c1  jnb     loc_180030622
0x1800306c7  mov     rcx, [rbp+57h+var_78]
0x1800306cb  lea     r8, [rbp+57h+var_88]
0x1800306cf  mov     [rbp+57h+var_88], r13
0x1800306d3  mov     edx, esi
0x1800306d5  mov     [rbp+57h+var_90], r13
0x1800306d9  mov     rax, [rcx]
0x1800306dc  mov     rax, [rax+30h]
0x1800306e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306e5  mov     edi, eax
0x1800306e7  test    eax, eax
0x1800306e9  js      loc_180030818
0x1800306ef  mov     rdi, [rbp+57h+var_70]
0x1800306f3  mov     rcx, [rbp+57h+var_90]
0x1800306f7  mov     r14, [rdi]
0x1800306fa  test    rcx, rcx
0x1800306fd  jz      short loc_18003070F
0x1800306ff  mov     [rbp+57h+var_90], r13
0x180030703  mov     rax, [rcx]
0x180030706  mov     rax, [rax+10h]
0x18003070a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003070f  lea     r9, [rbp+57h+string]; string
0x180030713  mov     [rbp+57h+string], r13
0x180030717  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003071b  mov     edx, 10h; length
0x180030720  lea     rcx, sourceString; "windows.voipCall"
0x180030727  call    cs:__imp_WindowsCreateStringReference
0x18003072d  test    eax, eax
0x18003072f  js      loc_18003082C
0x180030735  mov     r8, [rbp+57h+string]
0x180030739  lea     r9, [rbp+57h+var_90]
0x18003073d  mov     rdx, [rbp+57h+var_88]
0x180030741  mov     rcx, rdi
0x180030744  mov     rax, [r14+88h]
0x18003074b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030750  mov     edi, eax
0x180030752  test    eax, eax
0x180030754  js      loc_180030818
0x18003075a  mov     rcx, [rbp+57h+var_90]
0x18003075e  lea     rdx, [rbp+57h+var_80]
0x180030762  mov     rax, [rcx]
0x180030765  mov     rax, [rax+38h]
0x180030769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003076e  mov     edi, eax
0x180030770  test    eax, eax
0x180030772  js      loc_180030818
0x180030778  mov     rcx, [rbp+57h+var_90]
0x18003077c  cmp     [rbp+57h+var_80], r13d
0x180030780  ja      short loc_1800307B7
0x180030782  test    rcx, rcx
0x180030785  jz      short loc_180030797
0x180030787  mov     [rbp+57h+var_90], r13
0x18003078b  mov     rax, [rcx]
0x18003078e  mov     rax, [rax+10h]
0x180030792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030797  mov     rcx, [rbp+57h+var_88]
0x18003079b  test    rcx, rcx
0x18003079e  jz      short loc_1800307B0
0x1800307a0  mov     [rbp+57h+var_88], r13
0x1800307a4  mov     rax, [rcx]
0x1800307a7  mov     rax, [rax+10h]
0x1800307ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307b0  inc     esi
0x1800307b2  jmp     loc_1800306BE
0x1800307b7  mov     byte ptr [r15], 1
0x1800307bb  test    rcx, rcx
0x1800307be  jz      short loc_1800307D0
0x1800307c0  mov     [rbp+57h+var_90], r13
0x1800307c4  mov     rax, [rcx]
0x1800307c7  mov     rax, [rax+10h]
0x1800307cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307d0  mov     rcx, [rbp+57h+var_88]
0x1800307d4  test    rcx, rcx
0x1800307d7  jz      loc_180030622
0x1800307dd  mov     [rbp+57h+var_88], r13
0x1800307e1  mov     rax, [rcx]
0x1800307e4  mov     rax, [rax+10h]
0x1800307e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307ed  jmp     loc_180030622
0x1800307f2  xor     r9d, r9d; lpArguments
0x1800307f5  xor     r8d, r8d; nNumberOfArguments
0x1800307f8  mov     ecx, eax; dwExceptionCode
0x1800307fa  lea     edx, [r9+1]; dwExceptionFlags
0x1800307fe  call    cs:__imp_RaiseException
0x180030804  int     3; Trap to Debugger
0x180030805  xor     r9d, r9d; lpArguments
0x180030808  xor     r8d, r8d; nNumberOfArguments
0x18003080b  mov     ecx, eax; dwExceptionCode
0x18003080d  lea     edx, [r9+1]; dwExceptionFlags
0x180030811  call    cs:__imp_RaiseException
0x180030817  int     3; Trap to Debugger
0x180030818  lea     rcx, [rbp+57h+var_90]
0x18003081c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180030821  lea     rcx, [rbp+57h+var_88]
0x180030825  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003082a  jmp     short loc_1800307B0
0x18003082c  xor     r9d, r9d; lpArguments
0x18003082f  xor     r8d, r8d; nNumberOfArguments
0x180030832  mov     ecx, eax; dwExceptionCode
0x180030834  lea     edx, [r9+1]; dwExceptionFlags
0x180030838  call    cs:__imp_RaiseException
```
