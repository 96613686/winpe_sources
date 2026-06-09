# IJsonObjectGetNamedInteger<ulong>(Windows::Data::Json::IJsonObject *,ushort const *,ulong *)

- ea: `0x140007d10`
- end: `0x140007d89`
- name: `??$IJsonObjectGetNamedInteger@K@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAK@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400081bc`

## callees

- `0x1400014c0`
- `0x140007cb0`
- `0x140007d10`
- `0x140009010`

## pseudocode

```c
__int64 __fastcall IJsonObjectGetNamedInteger<unsigned long>(__int64 a1, const WCHAR *a2, _DWORD *a3)
{
  __int64 (__fastcall *v5)(__int64, PVOID, double *); // rbx
  HSTRING_HEADER *v6; // rax
  __int64 result; // rax
  double v8; // [rsp+20h] [rbp-58h] BYREF
  const WCHAR *v9; // [rsp+28h] [rbp-50h] BYREF
  HSTRING_HEADER v10; // [rsp+30h] [rbp-48h] BYREF

  v9 = a2;
  v8 = 0.0;
  v5 = *(__int64 (__fastcall **)(__int64, PVOID, double *))(*(_QWORD *)a1 + 88LL);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v10, &v9);
  result = v5(a1, v6[1].Reserved.Reserved1, &v8);
  if ( (int)result >= 0 )
    *a3 = (int)v8;
  return result;
}

```

## disassembly

```asm
0x140007d10  push    rbx
0x140007d12  push    rsi
0x140007d13  push    rdi
0x140007d14  sub     rsp, 60h
0x140007d18  mov     rax, cs:__security_cookie
0x140007d1f  xor     rax, rsp
0x140007d22  mov     [rsp+78h+var_28], rax
0x140007d27  mov     rsi, r8
0x140007d2a  mov     rdi, rcx
0x140007d2d  mov     [rsp+78h+var_50], rdx
0x140007d32  xorps   xmm0, xmm0
0x140007d35  movsd   [rsp+78h+var_58], xmm0
0x140007d3b  mov     rax, [rcx]
0x140007d3e  mov     rbx, [rax+58h]
0x140007d42  lea     rdx, [rsp+78h+var_50]
0x140007d47  lea     rcx, [rsp+78h+var_48]
0x140007d4c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140007d51  nop
0x140007d52  lea     r8, [rsp+78h+var_58]
0x140007d57  mov     rdx, [rax+18h]
0x140007d5b  mov     rcx, rdi
0x140007d5e  mov     rax, rbx
0x140007d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d66  nop
0x140007d67  test    eax, eax
0x140007d69  js      short loc_140007D74
0x140007d6b  cvttsd2si rcx, [rsp+78h+var_58]
0x140007d72  mov     [rsi], ecx
0x140007d74  mov     rcx, [rsp+78h+var_28]
0x140007d79  xor     rcx, rsp; StackCookie
0x140007d7c  call    __security_check_cookie
0x140007d81  add     rsp, 60h
0x140007d85  pop     rdi
0x140007d86  pop     rsi
0x140007d87  pop     rbx
0x140007d88  retn
```
