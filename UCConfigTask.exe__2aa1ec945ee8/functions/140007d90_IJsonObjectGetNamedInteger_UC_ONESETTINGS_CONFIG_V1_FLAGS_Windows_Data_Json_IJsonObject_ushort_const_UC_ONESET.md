# IJsonObjectGetNamedInteger<_UC_ONESETTINGS_CONFIG_V1_FLAGS>(Windows::Data::Json::IJsonObject *,ushort const *,_UC_ONESETTINGS_CONFIG_V1_FLAGS *)

- ea: `0x140007d90`
- end: `0x140007e1e`
- name: `??$IJsonObjectGetNamedInteger@W4_UC_ONESETTINGS_CONFIG_V1_FLAGS@@@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAW4_UC_ONESETTINGS_CONFIG_V1_FLAGS@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400081bc`

## callees

- `0x1400014c0`
- `0x140007cb0`
- `0x140007d90`
- `0x140009010`

## pseudocode

```c
__int64 __fastcall IJsonObjectGetNamedInteger<enum _UC_ONESETTINGS_CONFIG_V1_FLAGS>(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 (__fastcall *v5)(__int64, PVOID, double *); // rbx
  HSTRING_HEADER *v6; // rax
  __int64 result; // rax
  double v8; // [rsp+20h] [rbp-48h] BYREF
  const WCHAR *v9; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER v10; // [rsp+30h] [rbp-38h] BYREF

  v9 = L"SearchFlag";
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
0x140007d90  mov     r11, rsp
0x140007d93  mov     [r11+10h], rbx
0x140007d97  mov     [r11+20h], rsi
0x140007d9b  push    rdi
0x140007d9c  sub     rsp, 60h
0x140007da0  mov     rax, cs:__security_cookie
0x140007da7  xor     rax, rsp
0x140007daa  mov     [rsp+68h+var_18], rax
0x140007daf  mov     rsi, r8
0x140007db2  mov     rdi, rcx
0x140007db5  lea     rax, aSearchflag; "SearchFlag"
0x140007dbc  mov     [r11-40h], rax
0x140007dc0  xorps   xmm0, xmm0
0x140007dc3  movsd   [rsp+68h+var_48], xmm0
0x140007dc9  mov     rax, [rcx]
0x140007dcc  mov     rbx, [rax+58h]
0x140007dd0  lea     rdx, [r11-40h]
0x140007dd4  lea     rcx, [r11-38h]
0x140007dd8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140007ddd  nop
0x140007dde  lea     r8, [rsp+68h+var_48]
0x140007de3  mov     rdx, [rax+18h]
0x140007de7  mov     rcx, rdi
0x140007dea  mov     rax, rbx
0x140007ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007df2  nop
0x140007df3  test    eax, eax
0x140007df5  js      short loc_140007DFF
0x140007df7  cvttsd2si ecx, [rsp+68h+var_48]
0x140007dfd  mov     [rsi], ecx
0x140007dff  mov     rcx, [rsp+68h+var_18]
0x140007e04  xor     rcx, rsp; StackCookie
0x140007e07  call    __security_check_cookie
0x140007e0c  lea     r11, [rsp+68h+var_8]
0x140007e11  mov     rbx, [r11+18h]
0x140007e15  mov     rsi, [r11+28h]
0x140007e19  mov     rsp, r11
0x140007e1c  pop     rdi
0x140007e1d  retn
```
