# StateRepoHelper::ForEachChildElement__lambda_094ae5f9b4fc1013eabe3ab3e7d83e48___

- ea: `0x1400474c4`
- end: `0x14004786c`
- name: `StateRepoHelper::ForEachChildElement__lambda_094ae5f9b4fc1013eabe3ab3e7d83e48___`
- size: `936`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140047a80`

## callees

- `0x140005240`
- `0x140028044`
- `0x140041500`
- `0x140047408`
- `0x140047468`
- `0x1400474c4`
- `0x140047d1c`
- `0x140047d34`
- `0x140047d50`
- `0x140047e24`
- `0x140047e3c`
- `0x140047f2c`
- `0x140047fa8`
- `0x140047fb8`
- `0x140047fd8`
- `0x1400485a8`
- `0x1400485f8`
- `0x1400486ac`
- `0x140070010`

## string_xrefs

- `0x1400475d2`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x14004764b`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x1400476f8`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x140047772`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x1400477c7`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x140047827`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x1400474fe`: `SearchProtocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall StateRepoHelper::ForEachChildElement__lambda_094ae5f9b4fc1013eabe3ab3e7d83e48___(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, struct IInspectable **); // rbx
  __int64 v6; // rax
  int InspectableArray; // r14d
  bool v8; // r8
  bool v9; // r9
  const wchar_t *v10; // rbx
  const wchar_t *v11; // rax
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  int Type; // eax
  __int64 v15; // rax
  unsigned int *v16; // rdx
  struct IInspectable ***v17; // r8
  unsigned int i; // ebx
  struct IInspectable *v19; // rcx
  int v20; // eax
  __int64 v21; // rdx
  int Inspectable; // eax
  int v23; // eax
  __int64 v24; // rdx
  int v26; // [rsp+28h] [rbp-59h] BYREF
  struct IInspectable *v27; // [rsp+30h] [rbp-51h] BYREF
  const wchar_t *v28; // [rsp+38h] [rbp-49h] BYREF
  unsigned __int64 v29; // [rsp+40h] [rbp-41h]
  int v30; // [rsp+48h] [rbp-39h] BYREF
  const wchar_t **v31; // [rsp+50h] [rbp-31h] BYREF
  struct IInspectable *v32; // [rsp+58h] [rbp-29h] BYREF
  const wchar_t *v33; // [rsp+60h] [rbp-21h] BYREF
  int v34; // [rsp+68h] [rbp-19h]
  const wchar_t *v35; // [rsp+70h] [rbp-11h] BYREF
  int v36; // [rsp+78h] [rbp-9h]
  __int64 v37; // [rsp+80h] [rbp-1h]
  _BYTE v38[24]; // [rsp+88h] [rbp+7h] BYREF
  __int64 v39; // [rsp+A0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  v37 = -2;
  v4 = a2;
  v35 = L"SearchProtocol";
  v33 = 0;
  v34 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IInspectable **))(*(_QWORD *)a2 + 48LL);
  v31 = &v33;
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v38, &v35);
  InspectableArray = v5(v4, *(_QWORD *)(v6 + 24), &v32);
  v39 = 0;
  RoVariant::RoVariant((RoVariant *)&v28, v32, v8, v9);
  v10 = v28;
  v28 = 0;
  LODWORD(v4) = v29;
  LODWORD(v29) = 0;
  RoVariant::~RoVariant((RoVariant *)&v28);
  v11 = v33;
  v33 = v10;
  v28 = v11;
  LODWORD(v11) = v34;
  v34 = v4;
  LODWORD(v29) = (_DWORD)v11;
  RoVariant::~RoVariant((RoVariant *)&v28);
  if ( InspectableArray < 0 )
  {
    v12 = (unsigned int)InspectableArray;
    v13 = 67;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)v12,
      v26);
LABEL_31:
    RoVariant::~RoVariant((RoVariant *)&v33);
    return (unsigned int)InspectableArray;
  }
  v30 = 0;
  v28 = v33;
  LODWORD(v29) = v34;
  Type = RoVariant::Accessor::get_Type((RoVariant::Accessor *)&v28, (enum Windows::Foundation::PropertyType *)&v30);
  InspectableArray = Type;
  if ( Type < 0 )
  {
    v12 = (unsigned int)Type;
    v13 = 70;
    goto LABEL_5;
  }
  if ( v30 == 1037 )
  {
    wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v28);
    v35 = v33;
    v36 = v34;
    v15 = wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator&(&v28);
    v16 = (unsigned int *)(wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::size_address<unsigned int>(
                             &v28,
                             &v31,
                             v15)
                         + 8);
    InspectableArray = RoVariant::Accessor::GetInspectableArray((RoVariant::Accessor *)&v35, v16, v17);
    wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::size_address_ptr<unsigned int>::~size_address_ptr<unsigned int>(&v31);
    if ( InspectableArray < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
        (const char *)(unsigned int)InspectableArray,
        v26);
LABEL_9:
      wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v28);
      goto LABEL_31;
    }
    for ( i = 0; i < v29; ++i )
    {
      v19 = *(struct IInspectable **)wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator[](&v28);
      v27 = v19;
      if ( v19 )
        ((void (__fastcall *)(struct IInspectable *))v19->lpVtbl->AddRef)(v19);
      v31 = 0;
      v20 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
              &v27,
              &v31);
      InspectableArray = v20;
      if ( v20 < 0 )
      {
        v21 = 81;
        goto LABEL_20;
      }
      LOBYTE(v26) = 0;
      v20 = lambda_094ae5f9b4fc1013eabe3ab3e7d83e48_::operator()(a3, (__int64)v31, (__int64)&v26);
      InspectableArray = v20;
      if ( v20 < 0 )
      {
        v21 = 84;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
          (const char *)(unsigned int)v20,
          v26);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v31);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v27);
        goto LABEL_9;
      }
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v31);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v27);
      if ( (_BYTE)v26 )
        break;
    }
    wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v28);
    goto LABEL_33;
  }
  if ( v30 == 13 )
  {
    v27 = 0;
    v28 = v33;
    LODWORD(v29) = v34;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v27);
    Inspectable = RoVariant::Accessor::GetInspectable((RoVariant::Accessor *)&v28, &v27);
    InspectableArray = Inspectable;
    if ( Inspectable >= 0 )
    {
      v35 = 0;
      v23 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
              &v27,
              &v35);
      InspectableArray = v23;
      if ( v23 >= 0 )
      {
        LOBYTE(v26) = 0;
        v23 = lambda_094ae5f9b4fc1013eabe3ab3e7d83e48_::operator()(a3, (__int64)v35, (__int64)&v26);
        InspectableArray = v23;
        if ( v23 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v35);
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v27);
LABEL_33:
          RoVariant::~RoVariant((RoVariant *)&v33);
          return 0;
        }
        v24 = 101;
      }
      else
      {
        v24 = 98;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
        (const char *)(unsigned int)v23,
        v26);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v35);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
        (const char *)(unsigned int)Inspectable,
        v26);
    }
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v27);
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x69,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
    (const char *)0x8000FFFFLL,
    v26);
  RoVariant::~RoVariant((RoVariant *)&v33);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1400474c4  mov     rax, rsp
0x1400474c7  push    rbp
0x1400474c8  push    rdi
0x1400474c9  push    r12
0x1400474cb  push    r14
0x1400474cd  push    r15
0x1400474cf  lea     rbp, [rax-5Fh]
0x1400474d3  sub     rsp, 0B0h
0x1400474da  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x1400474e2  mov     [rax+8], rbx
0x1400474e6  mov     [rax+20h], rsi
0x1400474ea  mov     rax, cs:__security_cookie
0x1400474f1  xor     rax, rsp
0x1400474f4  mov     [rbp+57h+var_30], rax
0x1400474f8  mov     r15, r8
0x1400474fb  mov     rdi, rdx
0x1400474fe  lea     rax, aSearchprotocol_0; "SearchProtocol"
0x140047505  mov     [rbp+57h+var_68], rax
0x140047509  xor     r12d, r12d
0x14004750c  mov     [rbp+57h+var_78], r12
0x140047510  mov     [rbp+57h+var_70], r12d
0x140047514  mov     rax, [rdx]
0x140047517  mov     rbx, [rax+30h]
0x14004751b  lea     rax, [rbp+57h+var_78]
0x14004751f  mov     [rbp+57h+var_88], rax
0x140047523  mov     [rbp+57h+var_80], r12
0x140047527  lea     rdx, [rbp+57h+var_68]
0x14004752b  lea     rcx, [rbp+57h+var_50]
0x14004752f  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140047534  nop
0x140047535  lea     r8, [rbp+57h+var_80]
0x140047539  mov     rdx, [rax+18h]
0x14004753d  mov     rcx, rdi
0x140047540  mov     rax, rbx
0x140047543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047548  mov     r14d, eax
0x14004754b  mov     [rbp+57h+var_38], r12
0x14004754f  mov     rsi, [rbp+57h+var_88]
0x140047553  mov     rdx, [rbp+57h+var_80]; struct IInspectable *
0x140047557  lea     rcx, [rbp+57h+var_A0]; this
0x14004755b  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x140047560  mov     rbx, [rbp+57h+var_A0]
0x140047564  mov     [rbp+57h+var_A0], r12
0x140047568  mov     edi, dword ptr [rbp+57h+var_98]
0x14004756b  mov     dword ptr [rbp+57h+var_98], r12d
0x14004756f  lea     rcx, [rbp+57h+var_A0]; this
0x140047573  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x140047578  mov     rax, [rsi]
0x14004757b  mov     [rsi], rbx
0x14004757e  mov     [rbp+57h+var_A0], rax
0x140047582  mov     eax, [rsi+8]
0x140047585  mov     [rsi+8], edi
0x140047588  mov     dword ptr [rbp+57h+var_98], eax
0x14004758b  lea     rcx, [rbp+57h+var_A0]; this
0x14004758f  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x140047594  nop
0x140047595  test    r14d, r14d
0x140047598  jns     short loc_1400475A4
0x14004759a  mov     r9d, r14d
0x14004759d  lea     edx, [r12+43h]
0x1400475a2  jmp     short loc_1400475D2
0x1400475a4  mov     [rbp+57h+var_90], r12d
0x1400475a8  mov     rax, [rbp+57h+var_78]
0x1400475ac  mov     [rbp+57h+var_A0], rax
0x1400475b0  mov     eax, [rbp+57h+var_70]
0x1400475b3  mov     dword ptr [rbp+57h+var_98], eax
0x1400475b6  lea     rdx, [rbp+57h+var_90]; enum Windows::Foundation::PropertyType *
0x1400475ba  lea     rcx, [rbp+57h+var_A0]; this
0x1400475be  call    ?get_Type@Accessor@RoVariant@@QEBAJPEAW4PropertyType@Foundation@Windows@@@Z; RoVariant::Accessor::get_Type(Windows::Foundation::PropertyType *)
0x1400475c3  mov     r14d, eax
0x1400475c6  test    eax, eax
0x1400475c8  jns     short loc_1400475E7
0x1400475ca  mov     r9d, eax; char *
0x1400475cd  mov     edx, 46h ; 'F'; void *
0x1400475d2  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400475d9  mov     rcx, [rbp+5Fh]; this
0x1400475dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400475e2  jmp     loc_1400477EC
0x1400475e7  cmp     [rbp+57h+var_90], 40Dh
0x1400475ee  jnz     loc_140047732
0x1400475f4  lea     rcx, [rbp+57h+var_A0]
0x1400475f8  call    ??0?$unique_any_array_ptr@PEAUIInspectable@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(void)
0x1400475fd  nop
0x1400475fe  mov     rax, [rbp+57h+var_78]
0x140047602  mov     [rbp+57h+var_68], rax
0x140047606  mov     eax, [rbp+57h+var_70]
0x140047609  mov     [rbp+57h+var_60], eax
0x14004760c  lea     rcx, [rbp+57h+var_A0]
0x140047610  call    ??I?$unique_any_array_ptr@PEAUIInspectable@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAPEAPEAPEAUIInspectable@@XZ; wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator&(void)
0x140047615  mov     r8, rax
0x140047618  lea     rdx, [rbp+57h+var_88]
0x14004761c  lea     rcx, [rbp+57h+var_A0]
0x140047620  call    ??$size_address@I@?$unique_any_array_ptr@PEAUIInspectable@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAA?AU?$size_address_ptr@I@01@XZ; wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::size_address<uint>(void)
0x140047625  nop
0x140047626  lea     rdx, [rax+8]; unsigned int *
0x14004762a  lea     rcx, [rbp+57h+var_68]; this
0x14004762e  call    ?GetInspectableArray@Accessor@RoVariant@@QEBAJPEAIPEAPEAPEAUIInspectable@@@Z; RoVariant::Accessor::GetInspectableArray(uint *,IInspectable * * *)
0x140047633  mov     r14d, eax
0x140047636  lea     rcx, [rbp+57h+var_88]
0x14004763a  call    ??1?$size_address_ptr@I@?$unique_any_array_ptr@PEAUIInspectable@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::size_address_ptr<uint>::~size_address_ptr<uint>(void)
0x14004763f  test    r14d, r14d
0x140047642  jns     short loc_14004766B
0x140047644  mov     rcx, [rbp+5Fh]; this
0x140047648  mov     r9d, r14d; char *
0x14004764b  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x140047652  mov     edx, 4Bh ; 'K'; void *
0x140047657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004765c  nop
0x14004765d  lea     rcx, [rbp+57h+var_A0]
0x140047661  call    ??1?$unique_any_array_ptr@PEAUIInspectable@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(void)
0x140047666  jmp     loc_1400477EC
0x14004766b  mov     ebx, r12d
0x14004766e  mov     edx, ebx
0x140047670  cmp     rdx, [rbp+57h+var_98]
0x140047674  jnb     loc_140047724
0x14004767a  lea     rcx, [rbp+57h+var_A0]
0x14004767e  call    ??A?$unique_any_array_ptr@PEAUIInspectable@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAAEAPEAUIInspectable@@_K@Z; wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator[](unsigned __int64)
0x140047683  mov     rcx, [rax]
0x140047686  mov     [rbp+57h+var_A8], rcx
0x14004768a  test    rcx, rcx
0x14004768d  jz      short loc_14004769C
0x14004768f  mov     rax, [rcx]
0x140047692  mov     rax, [rax+8]
0x140047696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004769b  nop
0x14004769c  mov     [rbp+57h+var_88], r12
0x1400476a0  lea     rdx, [rbp+57h+var_88]
0x1400476a4  lea     rcx, [rbp+57h+var_A8]
0x1400476a8  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1400476ad  mov     r14d, eax
0x1400476b0  test    eax, eax
0x1400476b2  js      short loc_1400476F3
0x1400476b4  mov     byte ptr [rbp+57h+var_B0], r12b
0x1400476b8  lea     r8, [rbp+57h+var_B0]
0x1400476bc  mov     rdx, [rbp+57h+var_88]
0x1400476c0  mov     rcx, r15
0x1400476c3  call    _lambda_094ae5f9b4fc1013eabe3ab3e7d83e48___operator__
0x1400476c8  mov     r14d, eax
0x1400476cb  test    eax, eax
0x1400476cd  js      short loc_1400476EC
0x1400476cf  lea     rcx, [rbp+57h+var_88]
0x1400476d3  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x1400476d8  nop
0x1400476d9  lea     rcx, [rbp+57h+var_A8]
0x1400476dd  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x1400476e2  cmp     byte ptr [rbp+57h+var_B0], r12b
0x1400476e6  jnz     short loc_140047724
0x1400476e8  inc     ebx
0x1400476ea  jmp     short loc_14004766E
0x1400476ec  mov     edx, 54h ; 'T'
0x1400476f1  jmp     short loc_1400476F8
0x1400476f3  mov     edx, 51h ; 'Q'; void *
0x1400476f8  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400476ff  mov     r9d, eax; char *
0x140047702  mov     rcx, [rbp+5Fh]; this
0x140047706  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004770b  nop
0x14004770c  lea     rcx, [rbp+57h+var_88]
0x140047710  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047715  nop
0x140047716  lea     rcx, [rbp+57h+var_A8]
0x14004771a  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14004771f  jmp     loc_14004765D
0x140047724  lea     rcx, [rbp+57h+var_A0]
0x140047728  call    ??1?$unique_any_array_ptr@PEAUIInspectable@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(void)
0x14004772d  jmp     loc_14004780E
0x140047732  cmp     [rbp+57h+var_90], 0Dh
0x140047736  jnz     loc_14004781B
0x14004773c  mov     [rbp+57h+var_A8], r12
0x140047740  mov     rax, [rbp+57h+var_78]
0x140047744  mov     [rbp+57h+var_A0], rax
0x140047748  mov     eax, [rbp+57h+var_70]
0x14004774b  mov     dword ptr [rbp+57h+var_98], eax
0x14004774e  lea     rcx, [rbp+57h+var_A8]
0x140047752  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047757  lea     rdx, [rbp+57h+var_A8]; struct IInspectable **
0x14004775b  lea     rcx, [rbp+57h+var_A0]; this
0x14004775f  call    ?GetInspectable@Accessor@RoVariant@@QEBAJPEAPEAUIInspectable@@@Z; RoVariant::Accessor::GetInspectable(IInspectable * *)
0x140047764  mov     r14d, eax
0x140047767  test    eax, eax
0x140047769  jns     short loc_140047785
0x14004776b  mov     rcx, [rbp+5Fh]; this
0x14004776f  mov     r9d, eax; char *
0x140047772  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x140047779  mov     edx, 5Fh ; '_'; void *
0x14004777e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047783  jmp     short loc_1400477E2
0x140047785  mov     [rbp+57h+var_68], r12
0x140047789  lea     rdx, [rbp+57h+var_68]
0x14004778d  lea     rcx, [rbp+57h+var_A8]
0x140047791  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x140047796  mov     r14d, eax
0x140047799  test    eax, eax
0x14004779b  jns     short loc_1400477A4
0x14004779d  mov     edx, 62h ; 'b'
0x1400477a2  jmp     short loc_1400477C4
0x1400477a4  mov     byte ptr [rbp+57h+var_B0], r12b
0x1400477a8  lea     r8, [rbp+57h+var_B0]
0x1400477ac  mov     rdx, [rbp+57h+var_68]
0x1400477b0  mov     rcx, r15
0x1400477b3  call    _lambda_094ae5f9b4fc1013eabe3ab3e7d83e48___operator__
0x1400477b8  mov     r14d, eax
0x1400477bb  test    eax, eax
0x1400477bd  jns     short loc_1400477FA
0x1400477bf  mov     edx, 65h ; 'e'; void *
0x1400477c4  mov     r9d, eax; char *
0x1400477c7  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400477ce  mov     rcx, [rbp+5Fh]; this
0x1400477d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400477d7  nop
0x1400477d8  lea     rcx, [rbp+57h+var_68]
0x1400477dc  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x1400477e1  nop
0x1400477e2  lea     rcx, [rbp+57h+var_A8]
0x1400477e6  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x1400477eb  nop
0x1400477ec  lea     rcx, [rbp+57h+var_78]; this
0x1400477f0  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1400477f5  mov     eax, r14d
0x1400477f8  jmp     short loc_140047844
0x1400477fa  lea     rcx, [rbp+57h+var_68]
0x1400477fe  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047803  nop
0x140047804  lea     rcx, [rbp+57h+var_A8]
0x140047808  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14004780d  nop
0x14004780e  lea     rcx, [rbp+57h+var_78]; this
0x140047812  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x140047817  xor     eax, eax
0x140047819  jmp     short loc_140047844
0x14004781b  mov     rcx, [rbp+5Fh]; this
0x14004781f  mov     ebx, 8000FFFFh
0x140047824  mov     r9d, ebx; char *
0x140047827  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x14004782e  mov     edx, 69h ; 'i'; void *
0x140047833  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047838  nop
0x140047839  lea     rcx, [rbp+57h+var_78]; this
0x14004783d  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x140047842  mov     eax, ebx
0x140047844  mov     rcx, [rbp+57h+var_30]
0x140047848  xor     rcx, rsp; StackCookie
0x14004784b  call    __security_check_cookie
0x140047850  lea     r11, [rsp+0D0h+var_20]
0x140047858  mov     rbx, [r11+30h]
0x14004785c  mov     rsi, [r11+48h]
0x140047860  mov     rsp, r11
0x140047863  pop     r15
0x140047865  pop     r14
0x140047867  pop     r12
0x140047869  pop     rdi
0x14004786a  pop     rbp
0x14004786b  retn
```
