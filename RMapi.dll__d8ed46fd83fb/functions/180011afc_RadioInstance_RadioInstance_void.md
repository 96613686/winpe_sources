# RadioInstance::~RadioInstance(void)

- ea: `0x180011afc`
- end: `0x180011b37`
- name: `??1RadioInstance@@UEAA@XZ`
- size: `59`
- prototype: `void __fastcall(RadioInstance *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011d50`

## callees

- `0x180003fa0`
- `0x18000c1e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011b1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011b1b`

## pseudocode

```c
void __fastcall RadioInstance::~RadioInstance(struct _RTL_CRITICAL_SECTION *this)
{
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&this[3]);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&this[2].SpinCount);
  DeleteCriticalSection(this + 1);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&this->SpinCount);
  HIDWORD(this->LockSemaphore) = -1073741823;
}

```

## disassembly

```asm
0x180011afc  push    rbx
0x180011afe  sub     rsp, 20h
0x180011b02  mov     rbx, rcx
0x180011b05  add     rcx, 78h ; 'x'
0x180011b09  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180011b0e  lea     rcx, [rbx+70h]
0x180011b12  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180011b17  lea     rcx, [rbx+28h]; lpCriticalSection
0x180011b1b  call    cs:__imp_DeleteCriticalSection
0x180011b21  lea     rcx, [rbx+20h]
0x180011b25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011b2a  mov     dword ptr [rbx+1Ch], 0C0000001h
0x180011b31  add     rsp, 20h
0x180011b35  pop     rbx
0x180011b36  retn
```
