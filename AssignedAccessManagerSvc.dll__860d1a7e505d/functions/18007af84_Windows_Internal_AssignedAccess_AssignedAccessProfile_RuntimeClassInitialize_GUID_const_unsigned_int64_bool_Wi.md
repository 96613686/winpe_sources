# Windows::Internal::AssignedAccess::AssignedAccessProfile::RuntimeClassInitialize(_GUID const &,unsigned __int64,bool,Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessApplication *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessApplication *>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,bool,Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation> *,Windows::Internal::AssignedAccess::IAssignedAccessFileExplorerRestrictions *)

- ea: `0x18007af84`
- end: `0x18007b219`
- name: `?RuntimeClassInitialize@AssignedAccessProfile@AssignedAccess@Internal@Windows@@QEAAJAEBU_GUID@@_K_NPEAV?$AgileObservableVector@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@3674@@3Collections@Foundation@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@22PEAU?$IVectorView@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@@784@PEAUIAssignedAccessFileExplorerRestrictions@234@@Z`
- size: `661`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007af34`

## callees

- `0x1800088bc`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x18000f8dc`
- `0x180010bf8`
- `0x18001d290`
- `0x18002729c`
- `0x18005b540`
- `0x18005eca0`
- `0x18007af84`
- `0x18007b780`
- `0x18007ba20`
- `0x18007ba50`
- `0x18007bab0`
- `0x18007bb90`

## string_xrefs

- `0x18007b021`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessprofile.cpp`
- `0x18007b067`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessprofile.cpp`
- `0x18007b098`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessprofile.cpp`
- `0x18007b131`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessprofile.cpp`
- `0x18007b166`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessprofile.cpp`
- `0x18007b19f`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessprofile.cpp`
- `0x18007b1d9`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessProfile::RuntimeClassInitialize(
        _QWORD *a1,
        struct _GUID *a2,
        __int64 a3,
        unsigned __int8 a4,
        volatile int *a5,
        __int64 a6,
        unsigned __int8 a7,
        unsigned __int8 a8)
{
  __int64 v12; // rcx
  struct Windows::Internal::AssignedAccess::IAssignedAccessFileExplorerRestrictions *v13; // rax
  __int64 v14; // rsi
  int v15; // edi
  __int64 result; // rax
  Windows::Internal::AssignedAccess::AssignedAccessProfile *v17; // rdi
  int v18; // eax
  unsigned int v19; // esi
  int IsSingleAppProfile; // eax
  unsigned int v21; // esi
  __int64 v22; // r10
  volatile int *v23; // rdx
  signed __int64 v24; // rax
  signed __int64 v25; // rtt
  int v26; // eax
  unsigned int v27; // ebx
  const char *v28; // r9
  int v29; // eax
  unsigned int v30; // ebx
  int v31; // eax
  unsigned int v32; // ebx
  int v33; // eax
  unsigned int v34; // ebx
  struct _GUID v35; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  struct Windows::Internal::AssignedAccess::IAssignedAccessFileExplorerRestrictions *v37; // [rsp+70h] [rbp+8h] BYREF

  v12 = a1[26];
  a1[26] = 0;
  if ( v12 )
    ((void (*)(void))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::IIterable<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::IObservableVector<Windows::Internal::AssignedAccess::AssignedAccessConfig *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release)();
  a1[26] = 0;
  v13 = (struct Windows::Internal::AssignedAccess::IAssignedAccessFileExplorerRestrictions *)operator new(
                                                                                               0xB8u,
                                                                                               (const struct std::nothrow_t *)&std::nothrow);
  v37 = v13;
  v14 = 0;
  if ( v13 )
  {
    v14 = Windows::Foundation::Collections::Internal::Vector<enum Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>,Windows::Foundation::Collections::Internal::VectorOptions<enum Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation,1,1,0>>::Vector<enum Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>,Windows::Foundation::Collections::Internal::VectorOptions<enum Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation,1,1,0>>(v13);
    v37 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>::~MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>(&v37);
  if ( v14 )
  {
    v15 = 0;
    a1[26] = v14;
  }
  else
  {
    v15 = -2147024882;
  }
  if ( v15 >= 0 )
  {
    v17 = (Windows::Internal::AssignedAccess::AssignedAccessProfile *)(a1 + 6);
    a1[9] = a3;
    v35 = *a2;
    v18 = Windows::Internal::AssignedAccess::AssignedAccessProfile::put_ProfileId(
            (Windows::Internal::AssignedAccess::AssignedAccessProfile *)(a1 + 6),
            &v35);
    v19 = v18;
    if ( v18 >= 0 )
    {
      IsSingleAppProfile = Windows::Internal::AssignedAccess::AssignedAccessProfile::put_IsSingleAppProfile(
                             (Windows::Internal::AssignedAccess::AssignedAccessProfile *)(a1 + 6),
                             a4);
      v21 = IsSingleAppProfile;
      if ( IsSingleAppProfile >= 0 )
      {
        v22 = a1[25];
        v23 = a5;
        a1[25] = a5;
        if ( v23 )
        {
          v24 = *((_QWORD *)v23 + 11);
          while ( v24 >= 0 )
          {
            if ( (_DWORD)v24 != 0x7FFFFFFF )
            {
              v25 = v24;
              v24 = _InterlockedCompareExchange64((volatile signed __int64 *)v23 + 11, v24 + 1, v24);
              if ( v25 != v24 )
                continue;
            }
            goto LABEL_21;
          }
          Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(2 * v24 + 16), v23);
        }
LABEL_21:
        if ( v22 )
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::IIterable<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::IObservableVector<Windows::Internal::AssignedAccess::AssignedAccessConfig *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release(v22);
        try
        {
          std::wstring::operator=();
          v26 = Windows::Internal::AssignedAccess::AssignedAccessProfile::put_TaskbarAllowed(
                  (Windows::Internal::AssignedAccess::AssignedAccessProfile *)(a1 + 6),
                  a7);
          v27 = v26;
          if ( v26 >= 0 )
          {
            v29 = Windows::Internal::AssignedAccess::AssignedAccessProfile::put_AllAppListAllowed(v17, a8);
            v30 = v29;
            if ( v29 >= 0 )
            {
              v37 = 0;
              v31 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessFileExplorerRestrictions,Windows::Internal::AssignedAccess::IAssignedAccessFileExplorerRestrictions,>(&v37);
              v32 = v31;
              if ( v31 >= 0 )
              {
                v33 = Windows::Internal::AssignedAccess::AssignedAccessProfile::put_FileExplorerRestrictions(v17, v37);
                v34 = v33;
                if ( v33 >= 0 )
                {
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v37);
                  result = 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x48,
                    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessprofile.cpp",
                    (const char *)(unsigned int)v33,
                    v35.Data1);
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v37);
                  result = v34;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x47,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessprofile.cpp",
                  (const char *)(unsigned int)v31,
                  v35.Data1);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v37);
                result = v32;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3F,
                (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessprofile.cpp",
                (const char *)(unsigned int)v29,
                v35.Data1);
              result = v30;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3E,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessprofile.cpp",
              (const char *)(unsigned int)v26,
              v35.Data1);
            result = v27;
          }
        }
        catch ( ... )
        {
          LODWORD(v37) = wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4C,
                           (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessprofile.cpp",
                           v28);
          return (unsigned int)v37;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessprofile.cpp",
          (const char *)(unsigned int)IsSingleAppProfile,
          v35.Data1);
        return v21;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessprofile.cpp",
        (const char *)(unsigned int)v18,
        v35.Data1);
      return v19;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessprofile.cpp",
      (const char *)(unsigned int)v15,
      v35.Data1);
    return (unsigned int)v15;
  }
  return result;
}

```

## disassembly

```asm
0x18007af84  push    rbx
0x18007af86  push    rsi
0x18007af87  push    rdi
0x18007af88  push    r12
0x18007af8a  push    r14
0x18007af8c  push    r15
0x18007af8e  sub     rsp, 38h
0x18007af92  mov     r14b, r9b
0x18007af95  mov     r15, r8
0x18007af98  mov     r12, rdx
0x18007af9b  mov     rbx, rcx
0x18007af9e  mov     rcx, [rcx+0D0h]
0x18007afa5  mov     qword ptr [rbx+0D0h], 0
0x18007afb0  test    rcx, rcx
0x18007afb3  jz      short loc_18007AFBA
0x18007afb5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@U?$IIterable@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@234@U?$IObservableVector@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::IIterable<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::IObservableVector<Windows::Internal::AssignedAccess::AssignedAccessConfig *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release(void)
0x18007afba  mov     qword ptr [rbx+0D0h], 0
0x18007afc5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007afcc  mov     ecx, 0B8h; unsigned __int64
0x18007afd1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007afd6  mov     [rsp+68h+arg_0], rax
0x18007afdb  xor     esi, esi
0x18007afdd  test    rax, rax
0x18007afe0  jz      short loc_18007AFF6
0x18007afe2  mov     rcx, rax
0x18007afe5  call    ??0?$Vector@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@@3674@U?$VectorOptions@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@$00$00$0A@@3674@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation,1,1,0>>::Vector<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation> const &,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation,1,1,0>>::permission)
0x18007afea  mov     rsi, rax
0x18007afed  mov     [rsp+68h+arg_0], 0
0x18007aff6  lea     rcx, [rsp+68h+arg_0]
0x18007affb  call    ??1?$MakeAllocator@U?$GitInvokeHelper@U?$VectorChangedEventHandler@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@VGitPtr@Internal@4@$01@Details@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>::~MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>(void)
0x18007b000  test    rsi, rsi
0x18007b003  jnz     short loc_18007B00C
0x18007b005  mov     edi, 8007000Eh
0x18007b00a  jmp     short loc_18007B015
0x18007b00c  xor     edi, edi
0x18007b00e  mov     [rbx+0D0h], rsi
0x18007b015  test    edi, edi
0x18007b017  jns     short loc_18007B039
0x18007b019  mov     rcx, [rsp+68h]; this
0x18007b01e  mov     r9d, edi; char *
0x18007b021  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007b028  mov     edx, 34h ; '4'; void *
0x18007b02d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b032  mov     eax, edi
0x18007b034  jmp     loc_18007B20A
0x18007b039  lea     rdi, [rbx+30h]
0x18007b03d  mov     [rbx+48h], r15
0x18007b041  movups  xmm0, xmmword ptr [r12]
0x18007b046  movdqu  xmmword ptr [rsp+68h+var_48.Data1], xmm0; int
0x18007b04c  lea     rdx, [rsp+68h+var_48]; struct _GUID
0x18007b051  mov     rcx, rdi; this
0x18007b054  call    ?put_ProfileId@AssignedAccessProfile@AssignedAccess@Internal@Windows@@UEAAJU_GUID@@@Z; Windows::Internal::AssignedAccess::AssignedAccessProfile::put_ProfileId(_GUID)
0x18007b059  mov     esi, eax
0x18007b05b  test    eax, eax
0x18007b05d  jns     short loc_18007B07F
0x18007b05f  mov     rcx, [rsp+68h]; this
0x18007b064  mov     r9d, eax; char *
0x18007b067  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007b06e  mov     edx, 3Ah ; ':'; void *
0x18007b073  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b078  mov     eax, esi
0x18007b07a  jmp     loc_18007B20A
0x18007b07f  mov     dl, r14b; unsigned __int8
0x18007b082  mov     rcx, rdi; this
0x18007b085  call    ?put_IsSingleAppProfile@AssignedAccessProfile@AssignedAccess@Internal@Windows@@UEAAJE@Z; Windows::Internal::AssignedAccess::AssignedAccessProfile::put_IsSingleAppProfile(uchar)
0x18007b08a  mov     esi, eax
0x18007b08c  test    eax, eax
0x18007b08e  jns     short loc_18007B0B0
0x18007b090  mov     rcx, [rsp+68h]; this
0x18007b095  mov     r9d, eax; char *
0x18007b098  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007b09f  mov     edx, 3Bh ; ';'; void *
0x18007b0a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b0a9  mov     eax, esi
0x18007b0ab  jmp     loc_18007B20A
0x18007b0b0  mov     r10, [rbx+0C8h]
0x18007b0b7  mov     rdx, [rsp+68h+arg_20]; volatile int *
0x18007b0bf  mov     [rbx+0C8h], rdx
0x18007b0c6  test    rdx, rdx
0x18007b0c9  jz      short loc_18007B0F6
0x18007b0cb  mov     rax, [rdx+58h]
0x18007b0cf  test    rax, rax
0x18007b0d2  js      short loc_18007B0E9
0x18007b0d4  cmp     eax, 7FFFFFFFh
0x18007b0d9  jz      short loc_18007B0F6
0x18007b0db  lea     rcx, [rax+1]
0x18007b0df  lock cmpxchg [rdx+58h], rcx
0x18007b0e5  jnz     short loc_18007B0CF
0x18007b0e7  jmp     short loc_18007B0F6
0x18007b0e9  lea     rcx, ds:10h[rax*2]; this
0x18007b0f1  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18007b0f6  test    r10, r10
0x18007b0f9  jz      short loc_18007B103
0x18007b0fb  mov     rcx, r10
0x18007b0fe  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@U?$IIterable@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@234@U?$IObservableVector@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::IIterable<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::IObservableVector<Windows::Internal::AssignedAccess::AssignedAccessConfig *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release(void)
0x18007b103  lea     rcx, [rbx+68h]
0x18007b107  mov     rdx, [rsp+68h+arg_28]
0x18007b10f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007b114  mov     dl, [rsp+68h+arg_30]; unsigned __int8
0x18007b11b  mov     rcx, rdi; this
0x18007b11e  call    ?put_TaskbarAllowed@AssignedAccessProfile@AssignedAccess@Internal@Windows@@UEAAJE@Z; Windows::Internal::AssignedAccess::AssignedAccessProfile::put_TaskbarAllowed(uchar)
0x18007b123  mov     ebx, eax
0x18007b125  test    eax, eax
0x18007b127  jns     short loc_18007B149
0x18007b129  mov     rcx, [rsp+68h]; this
0x18007b12e  mov     r9d, eax; char *
0x18007b131  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007b138  mov     edx, 3Eh ; '>'; void *
0x18007b13d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b142  mov     eax, ebx
0x18007b144  jmp     loc_18007B20A
0x18007b149  mov     dl, [rsp+68h+arg_38]; unsigned __int8
0x18007b150  mov     rcx, rdi; this
0x18007b153  call    ?put_AllAppListAllowed@AssignedAccessProfile@AssignedAccess@Internal@Windows@@UEAAJE@Z; Windows::Internal::AssignedAccess::AssignedAccessProfile::put_AllAppListAllowed(uchar)
0x18007b158  mov     ebx, eax
0x18007b15a  test    eax, eax
0x18007b15c  jns     short loc_18007B17E
0x18007b15e  mov     rcx, [rsp+68h]; this
0x18007b163  mov     r9d, eax; char *
0x18007b166  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007b16d  mov     edx, 3Fh ; '?'; void *
0x18007b172  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b177  mov     eax, ebx
0x18007b179  jmp     loc_18007B20A
0x18007b17e  mov     [rsp+68h+arg_0], 0
0x18007b187  lea     rcx, [rsp+68h+arg_0]
0x18007b18c  call    ??$MakeAndInitialize@VAssignedAccessFileExplorerRestrictions@AssignedAccess@Internal@Windows@@UIAssignedAccessFileExplorerRestrictions@234@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIAssignedAccessFileExplorerRestrictions@AssignedAccess@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessFileExplorerRestrictions,Windows::Internal::AssignedAccess::IAssignedAccessFileExplorerRestrictions,>(Windows::Internal::AssignedAccess::IAssignedAccessFileExplorerRestrictions * *)
0x18007b191  mov     ebx, eax
0x18007b193  test    eax, eax
0x18007b195  jns     short loc_18007B1BE
0x18007b197  mov     rcx, [rsp+68h]; this
0x18007b19c  mov     r9d, eax; char *
0x18007b19f  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007b1a6  mov     edx, 47h ; 'G'; void *
0x18007b1ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b1b0  lea     rcx, [rsp+68h+arg_0]
0x18007b1b5  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18007b1ba  mov     eax, ebx
0x18007b1bc  jmp     short loc_18007B20A
0x18007b1be  mov     rdx, [rsp+68h+arg_0]; struct Windows::Internal::AssignedAccess::IAssignedAccessFileExplorerRestrictions *
0x18007b1c3  mov     rcx, rdi; this
0x18007b1c6  call    ?put_FileExplorerRestrictions@AssignedAccessProfile@AssignedAccess@Internal@Windows@@UEAAJPEAUIAssignedAccessFileExplorerRestrictions@234@@Z; Windows::Internal::AssignedAccess::AssignedAccessProfile::put_FileExplorerRestrictions(Windows::Internal::AssignedAccess::IAssignedAccessFileExplorerRestrictions *)
0x18007b1cb  mov     ebx, eax
0x18007b1cd  test    eax, eax
0x18007b1cf  jns     short loc_18007B1F8
0x18007b1d1  mov     rcx, [rsp+68h]; this
0x18007b1d6  mov     r9d, eax; char *
0x18007b1d9  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007b1e0  mov     edx, 48h ; 'H'; void *
0x18007b1e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b1ea  lea     rcx, [rsp+68h+arg_0]
0x18007b1ef  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18007b1f4  mov     eax, ebx
0x18007b1f6  jmp     short loc_18007B20A
0x18007b1f8  lea     rcx, [rsp+68h+arg_0]
0x18007b1fd  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18007b202  xor     eax, eax
0x18007b204  jmp     short loc_18007B20A
0x18007b206  mov     eax, dword ptr [rsp+68h+arg_0]
0x18007b20a  add     rsp, 38h
0x18007b20e  pop     r15
0x18007b210  pop     r14
0x18007b212  pop     r12
0x18007b214  pop     rdi
0x18007b215  pop     rsi
0x18007b216  pop     rbx
0x18007b217  retn
```
