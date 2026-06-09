# Windows::Internal::AssignedAccess::RegistryDataStore::RuntimeClassInitialize(void)

- ea: `0x180055684`
- end: `0x180055903`
- name: `?RuntimeClassInitialize@RegistryDataStore@AssignedAccess@Internal@Windows@@QEAAJXZ`
- size: `639`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::RegistryDataStore *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004e224`

## callees

- `0x18000b6b4`
- `0x18002074c`
- `0x1800221e0`
- `0x180022d00`
- `0x180024544`
- `0x180051f48`
- `0x180054408`
- `0x1800544c0`
- `0x180054578`
- `0x1800548e0`
- `0x180055684`
- `0x180096010`

## string_xrefs

- `0x1800556a3`: `AssignedAccessConfiguration`
- `0x1800556aa`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration`
- `0x1800556c4`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`
- `0x180055721`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`
- `0x18005575a`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`
- `0x180055793`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`
- `0x1800557cc`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`
- `0x180055803`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`
- `0x1800558c0`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::RegistryDataStore::RuntimeClassInitialize(__int64 **this)
{
  int RedirectedPathIfNeeded; // eax
  unsigned int v3; // ebx
  __int64 result; // rax
  unsigned __int64 v5; // rax
  __int64 v6; // rdx
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  _QWORD *v16; // rax
  __int64 *v17; // rax
  __int64 i; // rdx
  int v19; // eax
  unsigned int v20; // ebx
  int v21[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v23; // [rsp+48h] [rbp+10h] BYREF

  v23 = 0;
  RedirectedPathIfNeeded = Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(
                             (__int64)L"SOFTWARE\\Microsoft\\Windows\\AssignedAccessConfiguration",
                             (__int64)L"AssignedAccessConfiguration",
                             (__int64)&v23);
  v3 = RedirectedPathIfNeeded;
  if ( RedirectedPathIfNeeded >= 0 )
  {
    v5 = std::_WChar_traits<unsigned short>::length(v23);
    try
    {
      std::wstring::_Assign<unsigned short>((__int64)(this + 8), v6, v5);
      v7 = ((__int64 (__fastcall *)(__int64 **, char *))(*this)[9])(this, (char *)this + 40);
      v8 = v7;
      if ( v7 >= 0 )
      {
        v10 = Windows::Internal::AssignedAccess::RegistryDataStore::AddDatastore<Windows::Internal::AssignedAccess::RegistryDataStoreV0>((__int64)this);
        v11 = v10;
        if ( v10 >= 0 )
        {
          v12 = Windows::Internal::AssignedAccess::RegistryDataStore::AddDatastore<Windows::Internal::AssignedAccess::RegistryDataStoreV1>((__int64)this);
          v13 = v12;
          if ( v12 >= 0 )
          {
            v14 = Windows::Internal::AssignedAccess::RegistryDataStore::AddDatastore<Windows::Internal::AssignedAccess::RegistryDataStoreV2>((__int64)this);
            v15 = v14;
            if ( v14 >= 0 )
            {
              if ( this[3] )
              {
                v16 = (_QWORD *)std::map<enum StoreVersion,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessDataStore,wil::err_exception_policy>>::_Try_emplace<enum StoreVersion const &,>(
                                  this + 2,
                                  (__int64)v21,
                                  (unsigned int *)this + 10);
                wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessDataStore,wil::err_exception_policy>::operator=(
                  this + 4,
                  *v16 + 40LL);
                v17 = this[2];
                if ( *((_BYTE *)v17 + 25) )
                {
                  i = v17[2];
                }
                else
                {
                  i = *v17;
                  if ( *(_BYTE *)(*v17 + 25) )
                  {
                    for ( i = v17[1]; !*(_BYTE *)(i + 25) && v17 == *(__int64 **)i; i = *(_QWORD *)(i + 8) )
                      v17 = (__int64 *)i;
                    if ( *((_BYTE *)v17 + 25) )
                      i = (__int64)v17;
                  }
                  else
                  {
                    while ( !*(_BYTE *)(*(_QWORD *)(i + 16) + 25LL) )
                      i = *(_QWORD *)(i + 16);
                  }
                }
                wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessDataStore,wil::err_exception_policy>::operator=(
                  this + 6,
                  i + 40);
                v19 = (*(__int64 (__fastcall **)(__int64 *, char *))(*this[6] + 72))(this[6], (char *)this + 56);
                v20 = v19;
                if ( v19 >= 0 )
                {
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
                  result = 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2F,
                    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
                    (const char *)(unsigned int)v19,
                    v21[0]);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
                  result = v20;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2C,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
                  (const char *)0x8000FFFFLL,
                  v21[0]);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
                result = 2147549183LL;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2B,
                (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
                (const char *)(unsigned int)v14,
                v21[0]);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
              result = v15;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2A,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
              (const char *)(unsigned int)v12,
              v21[0]);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
            result = v13;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x29,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
            (const char *)(unsigned int)v10,
            v21[0]);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
          result = v11;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
          (const char *)(unsigned int)v7,
          v21[0]);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
        result = v8;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x32,
                             (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
                             v9);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
      (const char *)(unsigned int)RedirectedPathIfNeeded,
      v21[0]);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180055684  mov     rax, rsp
0x180055687  mov     [rax+8], rbx
0x18005568b  mov     [rax+18h], rsi
0x18005568f  push    rdi
0x180055690  sub     rsp, 30h
0x180055694  mov     rdi, rcx
0x180055697  mov     qword ptr [rax+10h], 0
0x18005569f  lea     r8, [rax+10h]
0x1800556a3  lea     rdx, aAssignedaccess_6; "AssignedAccessConfiguration"
0x1800556aa  lea     rcx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x1800556b1  call    ?GetRedirectedPathIfNeeded@PersistentLocationHelper@AssignedAccess@Internal@Windows@@SAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800556b6  mov     ebx, eax
0x1800556b8  test    eax, eax
0x1800556ba  jns     short loc_1800556E7
0x1800556bc  mov     rcx, [rsp+38h]; this
0x1800556c1  mov     r9d, eax; char *
0x1800556c4  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800556cb  mov     edx, 25h ; '%'; void *
0x1800556d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800556d5  nop
0x1800556d6  lea     rcx, [rsp+38h+arg_8]
0x1800556db  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800556e0  mov     eax, ebx
0x1800556e2  jmp     loc_1800558F2
0x1800556e7  mov     rdx, [rsp+38h+arg_8]
0x1800556ec  mov     rcx, rdx
0x1800556ef  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800556f4  lea     rcx, [rdi+40h]
0x1800556f8  mov     r8, rax
0x1800556fb  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180055700  mov     rax, [rdi]
0x180055703  lea     rdx, [rdi+28h]
0x180055707  mov     rcx, rdi
0x18005570a  mov     rax, [rax+48h]
0x18005570e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055713  mov     ebx, eax
0x180055715  test    eax, eax
0x180055717  jns     short loc_180055744
0x180055719  mov     rcx, [rsp+38h]; this
0x18005571e  mov     r9d, eax; char *
0x180055721  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180055728  mov     edx, 27h ; '''; void *
0x18005572d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055732  nop
0x180055733  lea     rcx, [rsp+38h+arg_8]
0x180055738  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005573d  mov     eax, ebx
0x18005573f  jmp     loc_1800558F2
0x180055744  mov     rcx, rdi
0x180055747  call    ??$AddDatastore@VRegistryDataStoreV0@AssignedAccess@Internal@Windows@@@RegistryDataStore@AssignedAccess@Internal@Windows@@AEAAJXZ; Windows::Internal::AssignedAccess::RegistryDataStore::AddDatastore<Windows::Internal::AssignedAccess::RegistryDataStoreV0>(void)
0x18005574c  mov     ebx, eax
0x18005574e  test    eax, eax
0x180055750  jns     short loc_18005577D
0x180055752  mov     rcx, [rsp+38h]; this
0x180055757  mov     r9d, eax; char *
0x18005575a  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180055761  mov     edx, 29h ; ')'; void *
0x180055766  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005576b  nop
0x18005576c  lea     rcx, [rsp+38h+arg_8]
0x180055771  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180055776  mov     eax, ebx
0x180055778  jmp     loc_1800558F2
0x18005577d  mov     rcx, rdi
0x180055780  call    ??$AddDatastore@VRegistryDataStoreV1@AssignedAccess@Internal@Windows@@@RegistryDataStore@AssignedAccess@Internal@Windows@@AEAAJXZ; Windows::Internal::AssignedAccess::RegistryDataStore::AddDatastore<Windows::Internal::AssignedAccess::RegistryDataStoreV1>(void)
0x180055785  mov     ebx, eax
0x180055787  test    eax, eax
0x180055789  jns     short loc_1800557B6
0x18005578b  mov     rcx, [rsp+38h]; this
0x180055790  mov     r9d, eax; char *
0x180055793  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005579a  mov     edx, 2Ah ; '*'; void *
0x18005579f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800557a4  nop
0x1800557a5  lea     rcx, [rsp+38h+arg_8]
0x1800557aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800557af  mov     eax, ebx
0x1800557b1  jmp     loc_1800558F2
0x1800557b6  mov     rcx, rdi
0x1800557b9  call    ??$AddDatastore@VRegistryDataStoreV2@AssignedAccess@Internal@Windows@@@RegistryDataStore@AssignedAccess@Internal@Windows@@AEAAJXZ; Windows::Internal::AssignedAccess::RegistryDataStore::AddDatastore<Windows::Internal::AssignedAccess::RegistryDataStoreV2>(void)
0x1800557be  mov     ebx, eax
0x1800557c0  test    eax, eax
0x1800557c2  jns     short loc_1800557EF
0x1800557c4  mov     rcx, [rsp+38h]; this
0x1800557c9  mov     r9d, eax; char *
0x1800557cc  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800557d3  mov     edx, 2Bh ; '+'; void *
0x1800557d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800557dd  nop
0x1800557de  lea     rcx, [rsp+38h+arg_8]
0x1800557e3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800557e8  mov     eax, ebx
0x1800557ea  jmp     loc_1800558F2
0x1800557ef  cmp     qword ptr [rdi+18h], 0
0x1800557f4  jnz     short loc_180055826
0x1800557f6  mov     rcx, [rsp+38h]; this
0x1800557fb  mov     ebx, 8000FFFFh
0x180055800  mov     r9d, ebx; char *
0x180055803  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005580a  mov     edx, 2Ch ; ','; void *
0x18005580f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055814  nop
0x180055815  lea     rcx, [rsp+38h+arg_8]
0x18005581a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005581f  mov     eax, ebx
0x180055821  jmp     loc_1800558F2
0x180055826  lea     r8, [rdi+28h]
0x18005582a  lea     rdx, [rsp+38h+var_18]
0x18005582f  lea     rcx, [rdi+10h]
0x180055833  call    ??$_Try_emplace@AEBW4StoreVersion@@$$V@?$map@W4StoreVersion@@V?$com_ptr_t@UIAssignedAccessDataStore@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@U?$less@W4StoreVersion@@@std@@V?$allocator@U?$pair@$$CBW4StoreVersion@@V?$com_ptr_t@UIAssignedAccessDataStore@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4StoreVersion@@V?$com_ptr_t@UIAssignedAccessDataStore@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBW4StoreVersion@@@Z; std::map<StoreVersion,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessDataStore,wil::err_exception_policy>>::_Try_emplace<StoreVersion const &,>(StoreVersion const &)
0x180055838  mov     rdx, [rax]
0x18005583b  add     rdx, 28h ; '('
0x18005583f  lea     rcx, [rdi+20h]
0x180055843  call    ??4?$com_ptr_t@UIAssignedAccessDataStore@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessDataStore,wil::err_exception_policy>::operator=(wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessDataStore,wil::err_exception_policy> const &)
0x180055848  mov     rax, [rdi+10h]
0x18005584c  cmp     byte ptr [rax+19h], 0
0x180055850  jz      short loc_180055858
0x180055852  mov     rdx, [rax+10h]
0x180055856  jmp     short loc_180055891
0x180055858  mov     rdx, [rax]
0x18005585b  cmp     byte ptr [rdx+19h], 0
0x18005585f  jz      short loc_180055887
0x180055861  mov     rdx, [rax+8]
0x180055865  jmp     short loc_180055873
0x180055867  cmp     rax, [rdx]
0x18005586a  jnz     short loc_180055879
0x18005586c  mov     rax, rdx
0x18005586f  mov     rdx, [rdx+8]
0x180055873  cmp     byte ptr [rdx+19h], 0
0x180055877  jz      short loc_180055867
0x180055879  cmp     byte ptr [rax+19h], 0
0x18005587d  cmovnz  rdx, rax
0x180055881  jmp     short loc_180055891
0x180055883  mov     rdx, [rdx+10h]
0x180055887  mov     rax, [rdx+10h]
0x18005588b  cmp     byte ptr [rax+19h], 0
0x18005588f  jz      short loc_180055883
0x180055891  add     rdx, 28h ; '('
0x180055895  lea     rcx, [rdi+30h]
0x180055899  call    ??4?$com_ptr_t@UIAssignedAccessDataStore@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessDataStore,wil::err_exception_policy>::operator=(wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessDataStore,wil::err_exception_policy> const &)
0x18005589e  mov     rcx, [rdi+30h]
0x1800558a2  mov     rax, [rcx]
0x1800558a5  lea     rdx, [rdi+38h]
0x1800558a9  mov     rax, [rax+48h]
0x1800558ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800558b2  mov     ebx, eax
0x1800558b4  test    eax, eax
0x1800558b6  jns     short loc_1800558E0
0x1800558b8  mov     rcx, [rsp+38h]; this
0x1800558bd  mov     r9d, eax; char *
0x1800558c0  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800558c7  mov     edx, 2Fh ; '/'; void *
0x1800558cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800558d1  nop
0x1800558d2  lea     rcx, [rsp+38h+arg_8]
0x1800558d7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800558dc  mov     eax, ebx
0x1800558de  jmp     short loc_1800558F2
0x1800558e0  lea     rcx, [rsp+38h+arg_8]
0x1800558e5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800558ea  xor     eax, eax
0x1800558ec  jmp     short loc_1800558F2
0x1800558ee  mov     eax, dword ptr [rsp+38h+arg_8]
0x1800558f2  mov     rbx, [rsp+38h+arg_0]
0x1800558f7  mov     rsi, [rsp+38h+arg_10]
0x1800558fc  add     rsp, 30h
0x180055900  pop     rdi
0x180055901  retn
```
