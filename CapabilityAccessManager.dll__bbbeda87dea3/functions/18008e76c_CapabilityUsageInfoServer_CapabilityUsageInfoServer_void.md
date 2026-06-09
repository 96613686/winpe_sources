# CapabilityUsageInfoServer::~CapabilityUsageInfoServer(void)

- ea: `0x18008e76c`
- end: `0x18008e7ed`
- name: `??1CapabilityUsageInfoServer@@UEAA@XZ`
- size: `129`
- prototype: `void __fastcall(CapabilityUsageInfoServer *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008e8e0`

## callees

- `0x180020fcc`
- `0x180086d74`
- `0x18008e76c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e78e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e78e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7c4`

## pseudocode

```c
void __fastcall CapabilityUsageInfoServer::~CapabilityUsageInfoServer(CapabilityUsageInfoServer *this)
{
  std::_Ref_count_base *v2; // rcx

  *(_QWORD *)this = &CapabilityUsageInfoServer::`vftable'{for `Windows::Internal::CapabilityAccess::Management::ICapabilityUsageInfo'};
  *((_QWORD *)this + 1) = &CapabilityUsageInfoServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  WindowsDeleteString(*((HSTRING *)this + 6));
  *((_QWORD *)this + 6) = 0;
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 5);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::CapabilityAccess::Management::ICapabilityConsentManager>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::CapabilityAccess::Management::ICapabilityConsentManager>(this);
}

```

## disassembly

```asm
0x18008e76c  push    rbx
0x18008e76e  sub     rsp, 20h
0x18008e772  lea     rax, ??_7CapabilityUsageInfoServer@@6BICapabilityUsageInfo@Management@CapabilityAccess@Internal@Windows@@@; const CapabilityUsageInfoServer::`vftable'{for `Windows::Internal::CapabilityAccess::Management::ICapabilityUsageInfo'}
0x18008e779  mov     rbx, rcx
0x18008e77c  mov     [rcx], rax
0x18008e77f  lea     rax, ??_7CapabilityUsageInfoServer@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const CapabilityUsageInfoServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x18008e786  mov     [rcx+8], rax
0x18008e78a  mov     rcx, [rcx+48h]; string
0x18008e78e  call    cs:__imp_WindowsDeleteString
0x18008e794  mov     qword ptr [rbx+48h], 0
0x18008e79c  mov     rcx, [rbx+40h]; string
0x18008e7a0  call    cs:__imp_WindowsDeleteString
0x18008e7a6  mov     qword ptr [rbx+40h], 0
0x18008e7ae  mov     rcx, [rbx+38h]; string
0x18008e7b2  call    cs:__imp_WindowsDeleteString
0x18008e7b8  mov     qword ptr [rbx+38h], 0
0x18008e7c0  mov     rcx, [rbx+30h]; string
0x18008e7c4  call    cs:__imp_WindowsDeleteString
0x18008e7ca  mov     qword ptr [rbx+30h], 0
0x18008e7d2  mov     rcx, [rbx+28h]; this
0x18008e7d6  test    rcx, rcx
0x18008e7d9  jz      short loc_18008E7E0
0x18008e7db  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008e7e0  mov     rcx, rbx
0x18008e7e3  add     rsp, 20h
0x18008e7e7  pop     rbx
0x18008e7e8  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UICapabilityConsentManager@Management@CapabilityAccess@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::CapabilityAccess::Management::ICapabilityConsentManager>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::CapabilityAccess::Management::ICapabilityConsentManager>(void)
```
