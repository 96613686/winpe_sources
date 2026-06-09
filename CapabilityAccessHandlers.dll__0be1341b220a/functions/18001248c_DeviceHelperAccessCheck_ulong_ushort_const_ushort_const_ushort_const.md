# _DeviceHelperAccessCheck(ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x18001248c`
- end: `0x180012605`
- name: `?_DeviceHelperAccessCheck@@YAEKPEBG00@Z`
- size: `377`
- prototype: `bool __fastcall(unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012bbc`

## callees

- `0x180004c70`
- `0x18000f758`
- `0x18000f8bc`
- `0x18000f954`
- `0x180010a14`
- `0x18001248c`
- `0x180014010`

## string_xrefs

- `0x1800124d6`: `Windows.Internal.CapabilityAccess.CapabilityAccess`

## pseudocode

```c
bool __fastcall _DeviceHelperAccessCheck(
        unsigned int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v6; // rsi
  int (__fastcall *v7)(__int64, _QWORD, __int64, _QWORD, _DWORD, __int64 *); // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdi
  void (__fastcall *v12)(__int64, _QWORD); // rbx
  __int64 v13; // rax
  bool v14; // bl
  __int64 v15; // [rsp+40h] [rbp-49h] BYREF
  int v16; // [rsp+48h] [rbp-41h] BYREF
  __int64 v17; // [rsp+50h] [rbp-39h] BYREF
  const unsigned __int16 *v18; // [rsp+58h] [rbp-31h] BYREF
  const unsigned __int16 *v19; // [rsp+60h] [rbp-29h] BYREF
  const unsigned __int16 *v20; // [rsp+68h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-19h] BYREF
  __int64 v22; // [rsp+88h] [rbp-1h]
  _BYTE v23[32]; // [rsp+90h] [rbp+7h] BYREF

  v19 = a2;
  v20 = a3;
  v18 = a4;
  v17 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.CapabilityAccess.CapabilityAccess",
    0x33u,
    0x32u);
  if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(
              v22,
              (__int64)&v17) >= 0 )
  {
    v15 = 0;
    v6 = v17;
    v7 = *(int (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD, __int64 *))(*(_QWORD *)v17 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v15);
    v8 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v18) + 24);
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v23, &v19);
    v14 = v7(v6, *(_QWORD *)(v9 + 24), v8, a1, 0, &v15) >= 0
       && (v16 = 0,
           LOBYTE(v10) = 1,
           (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 88LL))(v15, v10),
           v11 = v15,
           v12 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 104LL),
           v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v23, &v20),
           v12(v11, *(_QWORD *)(v13 + 24)),
           (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 152LL))(v15, &v16) >= 0)
       && v16 == 3;
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v15);
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v17);
    return v14;
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v17);
    return 0;
  }
}

```

## disassembly

```asm
0x18001248c  push    rbp
0x18001248e  push    rbx
0x18001248f  push    rsi
0x180012490  push    rdi
0x180012491  push    r14
0x180012493  lea     rbp, [rsp-37h]
0x180012498  sub     rsp, 0C0h
0x18001249f  mov     rax, cs:__security_cookie
0x1800124a6  xor     rax, rsp
0x1800124a9  mov     [rbp+57h+var_30], rax
0x1800124ad  mov     r14d, ecx
0x1800124b0  mov     [rbp+57h+var_80], rdx
0x1800124b4  mov     [rbp+57h+var_78], r8
0x1800124b8  mov     [rbp+57h+var_88], r9
0x1800124bc  mov     [rbp+57h+var_90], 0
0x1800124c4  mov     [rbp+57h+var_58], 0
0x1800124cc  mov     r9d, 32h ; '2'; unsigned int
0x1800124d2  lea     r8d, [r9+1]; unsigned int
0x1800124d6  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x1800124dd  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800124e1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800124e6  lea     rdx, [rbp+57h+var_90]
0x1800124ea  mov     rcx, [rbp+57h+var_58]
0x1800124ee  call    ??$GetActivationFactory@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>)
0x1800124f3  test    eax, eax
0x1800124f5  jns     short loc_180012507
0x1800124f7  lea     rcx, [rbp+57h+var_90]
0x1800124fb  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x180012500  xor     al, al
0x180012502  jmp     loc_1800125EB
0x180012507  mov     [rbp+57h+var_A0], 0
0x18001250f  mov     rsi, [rbp+57h+var_90]
0x180012513  mov     rax, [rsi]
0x180012516  mov     rdi, [rax+38h]
0x18001251a  lea     rcx, [rbp+57h+var_A0]
0x18001251e  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x180012523  lea     rdx, [rbp+57h+var_88]
0x180012527  lea     rcx, [rbp+57h+hstringHeader]
0x18001252b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180012530  nop
0x180012531  mov     rbx, [rax+18h]
0x180012535  lea     rdx, [rbp+57h+var_80]
0x180012539  lea     rcx, [rbp+57h+var_50]
0x18001253d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180012542  nop
0x180012543  lea     rcx, [rbp+57h+var_A0]
0x180012547  mov     [rsp+0E0h+var_B8], rcx
0x18001254c  mov     [rsp+0E0h+var_C0], 0
0x180012554  mov     r9d, r14d
0x180012557  mov     r8, rbx
0x18001255a  mov     rdx, [rax+18h]
0x18001255e  mov     rcx, rsi
0x180012561  mov     rax, rdi
0x180012564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012569  nop
0x18001256a  test    eax, eax
0x18001256c  js      short loc_1800125D4
0x18001256e  mov     [rbp+57h+var_98], 0
0x180012575  mov     rcx, [rbp+57h+var_A0]
0x180012579  mov     rax, [rcx]
0x18001257c  mov     dl, 1
0x18001257e  mov     rax, [rax+58h]
0x180012582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012587  mov     rdi, [rbp+57h+var_A0]
0x18001258b  mov     rax, [rdi]
0x18001258e  mov     rbx, [rax+68h]
0x180012592  lea     rdx, [rbp+57h+var_78]
0x180012596  lea     rcx, [rbp+57h+var_50]
0x18001259a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001259f  nop
0x1800125a0  mov     rdx, [rax+18h]
0x1800125a4  mov     rcx, rdi
0x1800125a7  mov     rax, rbx
0x1800125aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125af  nop
0x1800125b0  mov     rcx, [rbp+57h+var_A0]
0x1800125b4  mov     rax, [rcx]
0x1800125b7  lea     rdx, [rbp+57h+var_98]
0x1800125bb  mov     rax, [rax+98h]
0x1800125c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125c7  test    eax, eax
0x1800125c9  js      short loc_1800125D4
0x1800125cb  cmp     [rbp+57h+var_98], 3
0x1800125cf  setz    bl
0x1800125d2  jmp     short loc_1800125D6
0x1800125d4  xor     bl, bl
0x1800125d6  lea     rcx, [rbp+57h+var_A0]
0x1800125da  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x1800125df  nop
0x1800125e0  lea     rcx, [rbp+57h+var_90]
0x1800125e4  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x1800125e9  mov     al, bl
0x1800125eb  mov     rcx, [rbp+57h+var_30]
0x1800125ef  xor     rcx, rsp; StackCookie
0x1800125f2  call    __security_check_cookie
0x1800125f7  add     rsp, 0C0h
0x1800125fe  pop     r14
0x180012600  pop     rdi
0x180012601  pop     rsi
0x180012602  pop     rbx
0x180012603  pop     rbp
0x180012604  retn
```
