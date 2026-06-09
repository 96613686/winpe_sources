# CAudioSessionPropertyStore::~CAudioSessionPropertyStore(void)

- ea: `0x18000f8fc`
- end: `0x18000f9c8`
- name: `??1CAudioSessionPropertyStore@@EEAA@XZ`
- size: `204`
- prototype: `void __fastcall(CAudioSessionPropertyStore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000f8c0`

## callees

- `0x18000f8fc`
- `0x18000f9d0`
- `0x180031e00`
- `0x180039500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f935`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f935`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f955`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f955`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f95e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f95e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f997`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f997`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f9a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f9a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f98f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f98f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAudioSessionPropertyStore::~CAudioSessionPropertyStore(CAudioSessionPropertyStore *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rax
  HKEY v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  _QWORD *v7; // rcx

  *(_QWORD *)this = &CAudioSessionPropertyStore::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable,IPropertyStore>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &CAudioSessionPropertyStore::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IPropertyStore>'};
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  CAudioSessionPropertyStore::Commit((CAudioSessionPropertyStore *)((char *)this + 16));
  while ( 1 )
  {
    v3 = *((_QWORD *)this + 6);
    if ( !v3 )
      break;
    PropVariantClear((PROPVARIANT *)(v3 + 24));
    v7 = (_QWORD *)*((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = v7[6];
    operator delete(v7, 0);
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
  v4 = (HKEY)*((_QWORD *)this + 7);
  if ( v4 )
    RegCloseKey(v4);
  v5 = (void *)*((_QWORD *)this + 5);
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = *((_QWORD *)this + 4);
  if ( v6 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(2 * v6);
}

```

## disassembly

```asm
0x18000f8fc  mov     [rsp+arg_0], rbx
0x18000f901  mov     [rsp+arg_8], rsi
0x18000f906  push    rdi
0x18000f907  sub     rsp, 20h
0x18000f90b  lea     rax, ??_7CAudioSessionPropertyStore@@6B@; const CAudioSessionPropertyStore::`vftable'
0x18000f912  mov     rsi, rcx
0x18000f915  mov     [rcx], rax
0x18000f918  lea     rbx, [rcx+40h]
0x18000f91c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIInspectable@@UIPropertyStore@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable,IPropertyStore>::`vftable'{for `IWeakReferenceSource'}
0x18000f923  mov     [rcx+8], rax
0x18000f927  lea     rax, ??_7CAudioSessionPropertyStore@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIPropertyStore@@@Details@WRL@Microsoft@@@; const CAudioSessionPropertyStore::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IPropertyStore>'}
0x18000f92e  mov     [rcx+10h], rax
0x18000f932  mov     rcx, rbx; lpCriticalSection
0x18000f935  call    cs:__imp_EnterCriticalSection
0x18000f93b  lea     rcx, [rsi+10h]; this
0x18000f93f  call    ?Commit@CAudioSessionPropertyStore@@UEAAJXZ; CAudioSessionPropertyStore::Commit(void)
0x18000f944  mov     rax, [rsi+30h]
0x18000f948  test    rax, rax
0x18000f94b  jnz     short loc_18000F99F
0x18000f94d  test    rbx, rbx
0x18000f950  jz      short loc_18000F95B
0x18000f952  mov     rcx, rbx; lpCriticalSection
0x18000f955  call    cs:__imp_LeaveCriticalSection
0x18000f95b  mov     rcx, rbx; lpCriticalSection
0x18000f95e  call    cs:__imp_DeleteCriticalSection
0x18000f964  mov     rcx, [rsi+38h]; hKey
0x18000f968  test    rcx, rcx
0x18000f96b  jnz     short loc_18000F98F
0x18000f96d  mov     rcx, [rsi+28h]; pv
0x18000f971  test    rcx, rcx
0x18000f974  jnz     short loc_18000F997
0x18000f976  mov     rcx, [rsi+20h]
0x18000f97a  test    rcx, rcx
0x18000f97d  js      short loc_18000F9BE
0x18000f97f  mov     rbx, [rsp+28h+arg_0]
0x18000f984  mov     rsi, [rsp+28h+arg_8]
0x18000f989  add     rsp, 20h
0x18000f98d  pop     rdi
0x18000f98e  retn
0x18000f98f  call    cs:__imp_RegCloseKey
0x18000f995  jmp     short loc_18000F96D
0x18000f997  call    cs:__imp_CoTaskMemFree
0x18000f99d  jmp     short loc_18000F976
0x18000f99f  lea     rcx, [rax+18h]; pvar
0x18000f9a3  call    cs:__imp_PropVariantClear
0x18000f9a9  mov     rcx, [rsi+30h]; void *
0x18000f9ad  xor     edx, edx; struct std::nothrow_t *
0x18000f9af  mov     rax, [rcx+30h]
0x18000f9b3  mov     [rsi+30h], rax
0x18000f9b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f9bc  jmp     short loc_18000F944
0x18000f9be  add     rcx, rcx
0x18000f9c1  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18000f9c6  jmp     short loc_18000F97F
```
