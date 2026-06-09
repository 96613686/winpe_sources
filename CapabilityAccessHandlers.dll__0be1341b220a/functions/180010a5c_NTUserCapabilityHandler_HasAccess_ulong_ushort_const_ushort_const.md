# NTUserCapabilityHandler::HasAccess(ulong,ushort const *,ushort const *)

- ea: `0x180010a5c`
- end: `0x180010bd7`
- name: `?HasAccess@NTUserCapabilityHandler@@AEBA_NKPEBG0@Z`
- size: `379`
- prototype: `bool __fastcall(NTUserCapabilityHandler *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800103c0`

## callees

- `0x180004c70`
- `0x18000f758`
- `0x18000f8bc`
- `0x18000f954`
- `0x180010a14`
- `0x180010a5c`
- `0x180014010`

## string_xrefs

- `0x180010ab8`: `Windows.Internal.CapabilityAccess.CapabilityAccess`

## pseudocode

```c
bool __fastcall NTUserCapabilityHandler::HasAccess(
        NTUserCapabilityHandler *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rbx
  int (__fastcall *v8)(__int64, __int64, __int64, _QWORD, _DWORD, __int64 *); // r14
  __int64 v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  bool v13; // bl
  int v14; // [rsp+40h] [rbp-49h] BYREF
  __int64 v15; // [rsp+48h] [rbp-41h] BYREF
  __int64 v16; // [rsp+50h] [rbp-39h] BYREF
  int v17; // [rsp+58h] [rbp-31h]
  const wchar_t *v18; // [rsp+60h] [rbp-29h] BYREF
  const unsigned __int16 *v19; // [rsp+68h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-19h] BYREF
  __int64 v21; // [rsp+88h] [rbp-1h]
  _BYTE v22[32]; // [rsp+90h] [rbp+7h] BYREF

  v19 = a3;
  v17 = 0;
  v18 = L"graphicsCaptureLegacy";
  v16 = 0;
  v21 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.CapabilityAccess.CapabilityAccess",
    0x33u,
    0x32u);
  if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(
              v21,
              (__int64)&v16) >= 0 )
  {
    v15 = 0;
    v7 = v16;
    v8 = *(int (__fastcall **)(__int64, __int64, __int64, _QWORD, _DWORD, __int64 *))(*(_QWORD *)v16 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v15);
    v9 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v18) + 24);
    if ( a3 )
    {
      v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v22, &v19);
      v17 = 1;
      v11 = *(_QWORD *)(v10 + 24);
    }
    else
    {
      v11 = 0;
    }
    v13 = v8(v7, v11, v9, a2, 0, &v15) >= 0
       && (v14 = 0,
           LOBYTE(v12) = 1,
           (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 88LL))(v15, v12),
           (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 152LL))(v15, &v14) >= 0)
       && v14 == 3;
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v15);
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v16);
    return v13;
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v16);
    return 0;
  }
}

```

## disassembly

```asm
0x180010a5c  mov     [rsp-8+arg_0], rbx
0x180010a61  push    rbp
0x180010a62  push    rsi
0x180010a63  push    rdi
0x180010a64  push    r14
0x180010a66  push    r15
0x180010a68  lea     rbp, [rsp-37h]
0x180010a6d  sub     rsp, 0C0h
0x180010a74  mov     rax, cs:__security_cookie
0x180010a7b  xor     rax, rsp
0x180010a7e  mov     [rbp+57h+var_30], rax
0x180010a82  mov     rdi, r8
0x180010a85  mov     r15d, edx
0x180010a88  mov     [rbp+57h+var_78], r8
0x180010a8c  mov     [rbp+57h+var_88], 0
0x180010a93  lea     rax, aGraphicscaptur_0; "graphicsCaptureLegacy"
0x180010a9a  mov     [rbp+57h+var_80], rax
0x180010a9e  mov     [rbp+57h+var_90], 0
0x180010aa6  mov     [rbp+57h+var_58], 0
0x180010aae  mov     r9d, 32h ; '2'; unsigned int
0x180010ab4  lea     r8d, [r9+1]; unsigned int
0x180010ab8  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x180010abf  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180010ac3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180010ac8  lea     rdx, [rbp+57h+var_90]
0x180010acc  mov     rcx, [rbp+57h+var_58]
0x180010ad0  call    ??$GetActivationFactory@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>)
0x180010ad5  test    eax, eax
0x180010ad7  jns     short loc_180010AE9
0x180010ad9  lea     rcx, [rbp+57h+var_90]
0x180010add  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x180010ae2  xor     al, al
0x180010ae4  jmp     loc_180010BB4
0x180010ae9  mov     [rbp+57h+var_98], 0
0x180010af1  mov     rbx, [rbp+57h+var_90]
0x180010af5  mov     rax, [rbx]
0x180010af8  mov     r14, [rax+38h]
0x180010afc  lea     rcx, [rbp+57h+var_98]
0x180010b00  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x180010b05  lea     rdx, [rbp+57h+var_80]
0x180010b09  lea     rcx, [rbp+57h+hstringHeader]
0x180010b0d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180010b12  nop
0x180010b13  mov     rsi, [rax+18h]
0x180010b17  test    rdi, rdi
0x180010b1a  jz      short loc_180010B37
0x180010b1c  lea     rdx, [rbp+57h+var_78]
0x180010b20  lea     rcx, [rbp+57h+var_50]
0x180010b24  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180010b29  nop
0x180010b2a  mov     [rbp+57h+var_88], 1
0x180010b31  mov     rdx, [rax+18h]
0x180010b35  jmp     short loc_180010B39
0x180010b37  xor     edx, edx
0x180010b39  lea     rax, [rbp+57h+var_98]
0x180010b3d  mov     [rsp+0E0h+var_B8], rax
0x180010b42  mov     [rsp+0E0h+var_C0], 0
0x180010b4a  mov     r9d, r15d
0x180010b4d  mov     r8, rsi
0x180010b50  mov     rcx, rbx
0x180010b53  mov     rax, r14
0x180010b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b5b  nop
0x180010b5c  test    eax, eax
0x180010b5e  js      short loc_180010B9D
0x180010b60  mov     [rbp+57h+var_A0], 0
0x180010b67  mov     rcx, [rbp+57h+var_98]
0x180010b6b  mov     rax, [rcx]
0x180010b6e  mov     dl, 1
0x180010b70  mov     rax, [rax+58h]
0x180010b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b79  mov     rcx, [rbp+57h+var_98]
0x180010b7d  mov     rax, [rcx]
0x180010b80  lea     rdx, [rbp+57h+var_A0]
0x180010b84  mov     rax, [rax+98h]
0x180010b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b90  test    eax, eax
0x180010b92  js      short loc_180010B9D
0x180010b94  cmp     [rbp+57h+var_A0], 3
0x180010b98  setz    bl
0x180010b9b  jmp     short loc_180010B9F
0x180010b9d  xor     bl, bl
0x180010b9f  lea     rcx, [rbp+57h+var_98]
0x180010ba3  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x180010ba8  nop
0x180010ba9  lea     rcx, [rbp+57h+var_90]
0x180010bad  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x180010bb2  mov     al, bl
0x180010bb4  mov     rcx, [rbp+57h+var_30]
0x180010bb8  xor     rcx, rsp; StackCookie
0x180010bbb  call    __security_check_cookie
0x180010bc0  mov     rbx, [rsp+0E0h+arg_0]
0x180010bc8  add     rsp, 0C0h
0x180010bcf  pop     r15
0x180010bd1  pop     r14
0x180010bd3  pop     rdi
0x180010bd4  pop     rsi
0x180010bd5  pop     rbp
0x180010bd6  retn
```
