# Windows::Networking::UX::Internal::MBCategory::MBCategory(void)

- ea: `0x180006bcc`
- end: `0x180006ee4`
- name: `??0MBCategory@Internal@UX@Networking@Windows@@QEAA@XZ`
- size: `792`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MBCategory *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800068f8`

## callees

- `0x1800028d4`
- `0x180006688`
- `0x180006bcc`
- `0x18001f34c`
- `0x18001f7a4`
- `0x18001fb00`
- `0x180023f28`
- `0x18002d20c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006e09`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006e16`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006e2b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006e38`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006e6d`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006e7a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006e09`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006e16`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006e2b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006e38`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006e6d`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006e7a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006c96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006c96`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180006ec0`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180006ecc`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180006ec0`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180006ecc`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
Windows::Networking::UX::Internal::MBCategory *__fastcall Windows::Networking::UX::Internal::MBCategory::MBCategory(
        Windows::Networking::UX::Internal::MBCategory *this)
{
  void *v2; // rax
  __int64 v3; // rax

  Microsoft::WRL::RuntimeClass<Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>::RuntimeClass<Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>();
  *(_QWORD *)this = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Windows::Networking::UX::IUXCategory'};
  *((_QWORD *)this + 1) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IAvailableNetworkStore>'};
  *((_QWORD *)this + 25) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 26) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>'};
  *((_QWORD *)this + 27) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Windows::Networking::UX::IMBUXCategory'};
  *((_QWORD *)this + 28) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>'};
  *((_QWORD *)this + 29) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 30) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Windows::Networking::UX::Internal::IInterfaceNlmChangeListener'};
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 0;
  *((_DWORD *)this + 73) = 1;
  *((_WORD *)this + 148) = 0;
  *(_WORD *)((char *)this + 299) = 0;
  *((_QWORD *)this + 38) = -1;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 312), 0, 0);
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  std::wstring::wstring((char *)this + 368, &sourceString);
  std::wstring::wstring((char *)this + 400, &sourceString);
  std::wstring::wstring((char *)this + 432, &sourceString);
  *((_DWORD *)this + 116) = 0;
  *(_QWORD *)((char *)this + 468) = 1;
  *(_QWORD *)((char *)this + 476) = 0;
  *((_BYTE *)this + 484) = 0;
  *(_WORD *)((char *)this + 485) = 0;
  *((_BYTE *)this + 487) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_QWORD *)this + 62) = 0;
  *((_QWORD *)this + 63) = 0;
  *((_BYTE *)this + 512) = 0;
  *((_DWORD *)this + 149) = 0;
  *((_QWORD *)this + 75) = 1;
  *(_QWORD *)((char *)this + 612) = 0;
  *(_QWORD *)((char *)this + 620) = 0;
  *((_BYTE *)this + 628) = 0;
  std::wstring::wstring((char *)this + 632, &sourceString);
  *((_QWORD *)this + 83) = 0;
  std::wstring::wstring((char *)this + 672, &sourceString);
  *((_QWORD *)this + 88) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 90) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 92) = 0;
  *((_QWORD *)this + 93) = 0;
  std::wstring::wstring((char *)this + 752, &sourceString);
  *((_DWORD *)this + 196) = 3;
  *((_WORD *)this + 394) = 256;
  *((_BYTE *)this + 790) = 1;
  *((_QWORD *)this + 99) = 0;
  std::wstring::wstring((char *)this + 800);
  *((_QWORD *)this + 104) = 0;
  std::wstring::wstring((char *)this + 840, &sourceString);
  *((_QWORD *)this + 109) = 0;
  InitializeSRWLock((PSRWLOCK)this + 110);
  InitializeSRWLock((PSRWLOCK)this + 111);
  *((_QWORD *)this + 112) = 0;
  InitializeSRWLock((PSRWLOCK)this + 113);
  InitializeSRWLock((PSRWLOCK)this + 114);
  *((_QWORD *)this + 115) = 0;
  std::map<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>::map<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>((char *)this + 928);
  std::map<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>::map<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>((char *)this + 944);
  *((_QWORD *)this + 120) = 0;
  InitializeSRWLock((PSRWLOCK)this + 121);
  InitializeSRWLock((PSRWLOCK)this + 122);
  *((_WORD *)this + 304) = 0;
  *((_DWORD *)this + 14) = 2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease((char *)this + 792);
  *((_QWORD *)this + 99) = 0;
  v2 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
  {
    v3 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>(v2);
    if ( v3 )
      *((_QWORD *)this + 99) = v3;
  }
  *((_DWORD *)this + 178) = SHTaskPoolGetUniqueContext();
  *((_DWORD *)this + 179) = SHTaskPoolGetUniqueContext();
  return this;
}

```

## disassembly

```asm
0x180006bcc  mov     [rsp+arg_0], rcx
0x180006bd1  push    rbx
0x180006bd2  push    rbp
0x180006bd3  push    rsi
0x180006bd4  push    rdi
0x180006bd5  sub     rsp, 28h
0x180006bd9  mov     rbx, rcx
0x180006bdc  call    ??0?$RuntimeClass@VCategoryBase@Internal@UX@Networking@Windows@@UIMBCategory@2345@UIMBUXCategory@345@UIMBConnectionFlowCallback@2345@UIInspectableInterfaceNlmChangeListener@2345@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>::RuntimeClass<Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>(void)
0x180006be1  nop
0x180006be2  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6BIUXCategory@234@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Windows::Networking::UX::IUXCategory'}
0x180006be9  mov     [rbx], rax
0x180006bec  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIAvailableNetworkStore@Internal@UX@Networking@Windows@@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IAvailableNetworkStore>'}
0x180006bf3  mov     [rbx+8], rax
0x180006bf7  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6BIWeakReferenceSource@@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `IWeakReferenceSource'}
0x180006bfe  mov     [rbx+0C8h], rax
0x180006c05  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIMBCategory@Internal@UX@Networking@Windows@@UIMBUXCategory@678@UIMBConnectionFlowCallback@5678@UIInspectableInterfaceNlmChangeListener@5678@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>'}
0x180006c0c  mov     [rbx+0D0h], rax
0x180006c13  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6BIMBUXCategory@234@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Windows::Networking::UX::IMBUXCategory'}
0x180006c1a  mov     [rbx+0D8h], rax
0x180006c21  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIMBConnectionFlowCallback@Internal@UX@Networking@Windows@@UIInspectableInterfaceNlmChangeListener@5678@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>'}
0x180006c28  mov     [rbx+0E0h], rax
0x180006c2f  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6BIInspectable@@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `IInspectable'}
0x180006c36  mov     [rbx+0E8h], rax
0x180006c3d  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6BIInterfaceNlmChangeListener@1234@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Windows::Networking::UX::Internal::IInterfaceNlmChangeListener'}
0x180006c44  mov     [rbx+0F0h], rax
0x180006c4b  xor     ebp, ebp
0x180006c4d  mov     [rbx+108h], rbp
0x180006c54  mov     [rbx+110h], rbp
0x180006c5b  mov     [rbx+118h], rbp
0x180006c62  mov     [rbx+120h], ebp
0x180006c68  lea     edi, [rbp+1]
0x180006c6b  mov     [rbx+124h], edi
0x180006c71  mov     [rbx+128h], bp
0x180006c78  mov     [rbx+12Bh], bp
0x180006c7f  mov     qword ptr [rbx+130h], 0FFFFFFFFFFFFFFFFh
0x180006c8a  lea     rcx, [rbx+138h]; lpCriticalSection
0x180006c91  xor     r8d, r8d; Flags
0x180006c94  xor     edx, edx; dwSpinCount
0x180006c96  call    cs:__imp_InitializeCriticalSectionEx
0x180006c9c  nop
0x180006c9d  mov     [rbx+160h], rbp
0x180006ca4  mov     [rbx+168h], rbp
0x180006cab  lea     rcx, [rbx+170h]
0x180006cb2  lea     rsi, sourceString
0x180006cb9  mov     rdx, rsi
0x180006cbc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006cc1  nop
0x180006cc2  lea     rcx, [rbx+190h]
0x180006cc9  mov     rdx, rsi
0x180006ccc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006cd1  nop
0x180006cd2  lea     rcx, [rbx+1B0h]
0x180006cd9  mov     rdx, rsi
0x180006cdc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006ce1  nop
0x180006ce2  mov     [rbx+1D0h], ebp
0x180006ce8  mov     qword ptr [rbx+1D4h], 1
0x180006cf3  mov     [rbx+1DCh], rbp
0x180006cfa  mov     [rbx+1E4h], bpl
0x180006d01  xor     eax, eax
0x180006d03  mov     [rbx+1E5h], ax
0x180006d0a  mov     [rbx+1E7h], al
0x180006d10  mov     [rbx+1E8h], rbp
0x180006d17  mov     [rbx+1F0h], rbp
0x180006d1e  mov     [rbx+1F8h], rbp
0x180006d25  mov     [rbx+200h], bpl
0x180006d2c  mov     [rbx+254h], ebp
0x180006d32  mov     qword ptr [rbx+258h], 1
0x180006d3d  mov     [rbx+264h], rbp
0x180006d44  mov     [rbx+26Ch], rbp
0x180006d4b  mov     [rbx+274h], bpl
0x180006d52  lea     rcx, [rbx+278h]
0x180006d59  mov     rdx, rsi
0x180006d5c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006d61  nop
0x180006d62  mov     [rbx+298h], rbp
0x180006d69  lea     rcx, [rbx+2A0h]
0x180006d70  mov     rdx, rsi
0x180006d73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006d78  nop
0x180006d79  mov     [rbx+2C0h], rbp
0x180006d80  mov     [rbx+2C8h], rbp
0x180006d87  mov     [rbx+2D0h], rbp
0x180006d8e  mov     [rbx+2D8h], rbp
0x180006d95  mov     [rbx+2E0h], rbp
0x180006d9c  mov     [rbx+2E8h], rbp
0x180006da3  lea     rcx, [rbx+2F0h]
0x180006daa  mov     rdx, rsi
0x180006dad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006db2  nop
0x180006db3  mov     dword ptr [rbx+310h], 3
0x180006dbd  mov     word ptr [rbx+314h], 100h
0x180006dc6  mov     [rbx+316h], dil
0x180006dcd  lea     rdi, [rbx+318h]
0x180006dd4  mov     [rdi], rbp
0x180006dd7  lea     rcx, [rbx+320h]
0x180006dde  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180006de3  nop
0x180006de4  mov     [rbx+340h], rbp
0x180006deb  lea     rcx, [rbx+348h]
0x180006df2  mov     rdx, rsi
0x180006df5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006dfa  nop
0x180006dfb  mov     [rbx+368h], rbp
0x180006e02  lea     rcx, [rbx+370h]; SRWLock
0x180006e09  call    cs:__imp_InitializeSRWLock
0x180006e0f  lea     rcx, [rbx+378h]; SRWLock
0x180006e16  call    cs:__imp_InitializeSRWLock
0x180006e1c  nop
0x180006e1d  mov     [rbx+380h], rbp
0x180006e24  lea     rcx, [rbx+388h]; SRWLock
0x180006e2b  call    cs:__imp_InitializeSRWLock
0x180006e31  lea     rcx, [rbx+390h]; SRWLock
0x180006e38  call    cs:__imp_InitializeSRWLock
0x180006e3e  nop
0x180006e3f  mov     [rbx+398h], rbp
0x180006e46  lea     rcx, [rbx+3A0h]
0x180006e4d  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>::map<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>(void)
0x180006e52  nop
0x180006e53  lea     rcx, [rbx+3B0h]
0x180006e5a  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>::map<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>(void)
0x180006e5f  mov     [rbx+3C0h], rbp
0x180006e66  lea     rcx, [rbx+3C8h]; SRWLock
0x180006e6d  call    cs:__imp_InitializeSRWLock
0x180006e73  lea     rcx, [rbx+3D0h]; SRWLock
0x180006e7a  call    cs:__imp_InitializeSRWLock
0x180006e80  mov     [rbx+260h], bp
0x180006e87  mov     dword ptr [rbx+38h], 2
0x180006e8e  mov     rcx, rdi
0x180006e91  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x180006e96  mov     [rdi], rbp
0x180006e99  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006ea0  mov     ecx, 90h; unsigned __int64
0x180006ea5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006eaa  test    rax, rax
0x180006ead  jz      short loc_180006EC0
0x180006eaf  mov     rcx, rax
0x180006eb2  call    ??0?$Vector@UMbOperatorInfo@UX@Networking@Windows@@UMboEqualityPredicate@Internal@234@UMboLifetimePredicate@6234@U?$VectorOptions@UMbOperatorInfo@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@QEAA@AEBUMboEqualityPredicate@1UX@Networking@4@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>(Windows::Networking::UX::Internal::MboEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>::permission)
0x180006eb7  nop
0x180006eb8  test    rax, rax
0x180006ebb  jz      short loc_180006EC0
0x180006ebd  mov     [rdi], rax
0x180006ec0  call    cs:__imp_SHTaskPoolGetUniqueContext
0x180006ec6  mov     [rbx+2C8h], eax
0x180006ecc  call    cs:__imp_SHTaskPoolGetUniqueContext
0x180006ed2  mov     [rbx+2CCh], eax
0x180006ed8  mov     rax, rbx
0x180006edb  add     rsp, 28h
0x180006edf  pop     rdi
0x180006ee0  pop     rsi
0x180006ee1  pop     rbp
0x180006ee2  pop     rbx
0x180006ee3  retn
```
