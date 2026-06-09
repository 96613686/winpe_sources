# ReadWindirSettings(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,SCAN_SETTINGS &)

- ea: `0x180014cd0`
- end: `0x180014dfe`
- name: `?ReadWindirSettings@@YAJV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUSCAN_SETTINGS@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800050f0`
- `0x180010330`
- `0x180011438`
- `0x180014cd0`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall ReadWindirSettings(__int64 *a1, __int64 a2)
{
  __int64 v4; // rdi
  unsigned int (__fastcall *v5)(__int64, __int64, double *); // rbx
  unsigned int v6; // eax
  int v7; // edx
  unsigned int v8; // esi
  unsigned int v9; // ebp
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, __int64, __int64); // rbx
  double v13[2]; // [rsp+20h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-58h] BYREF
  __int64 v15; // [rsp+48h] [rbp-40h]

  *(_QWORD *)&v13[1] = a1;
  v13[0] = 0.0;
  v4 = *a1;
  v5 = *(unsigned int (__fastcall **)(__int64, __int64, double *))(*(_QWORD *)*a1 + 88LL);
  v15 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ColdFileThresholdHours", 0x17u, 0x16u);
  v6 = v5(v4, v15, v13) >> 31;
  if ( (_BYTE)v6 )
    v7 = *(_DWORD *)(STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings + 236);
  else
    v7 = (int)v13[0];
  v8 = -2147024883;
  v9 = (_BYTE)v6 != 0 ? 0x8007000D : 0;
  *(_DWORD *)(a2 + 16) = v7;
  v10 = *a1;
  v11 = *(int (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)*a1 + 96LL);
  v15 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UseWERForTelemetry", 0x13u, 0x12u);
  if ( v11(v10, v15, a2 + 20) >= 0 )
    v8 = v9;
  else
    *(_BYTE *)(a2 + 20) = *(_BYTE *)(STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings + 240);
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(a1);
  return v8;
}

```

## disassembly

```asm
0x180014cd0  mov     r11, rsp
0x180014cd3  mov     [r11+18h], rbx
0x180014cd7  push    rbp
0x180014cd8  push    rsi
0x180014cd9  push    rdi
0x180014cda  push    r14
0x180014cdc  push    r15
0x180014cde  sub     rsp, 60h
0x180014ce2  mov     rax, cs:__security_cookie
0x180014ce9  xor     rax, rsp
0x180014cec  mov     [rsp+88h+var_38], rax
0x180014cf1  mov     r15, rdx
0x180014cf4  mov     r14, rcx
0x180014cf7  mov     [r11-60h], rcx
0x180014cfb  xorps   xmm0, xmm0
0x180014cfe  movsd   [rsp+88h+var_68], xmm0
0x180014d04  mov     rdi, [rcx]
0x180014d07  mov     rax, [rdi]
0x180014d0a  mov     rbx, [rax+58h]
0x180014d0e  mov     qword ptr [r11-40h], 0
0x180014d16  mov     r9d, 16h; unsigned int
0x180014d1c  lea     r8d, [r9+1]; unsigned int
0x180014d20  lea     rdx, aColdfilethresh; "ColdFileThresholdHours"
0x180014d27  lea     rcx, [r11-58h]; hstringHeader
0x180014d2b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014d30  nop
0x180014d31  lea     r8, [rsp+88h+var_68]
0x180014d36  mov     rdx, [rsp+88h+var_40]
0x180014d3b  mov     rcx, rdi
0x180014d3e  mov     rax, rbx
0x180014d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d46  nop
0x180014d47  shr     eax, 1Fh
0x180014d4a  test    al, al
0x180014d4c  jz      short loc_180014D5D
0x180014d4e  mov     rcx, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x180014d55  mov     edx, [rcx+0ECh]
0x180014d5b  jmp     short loc_180014D64
0x180014d5d  cvttsd2si rdx, [rsp+88h+var_68]
0x180014d64  neg     al
0x180014d66  sbb     ebp, ebp
0x180014d68  mov     esi, 8007000Dh
0x180014d6d  and     ebp, esi
0x180014d6f  mov     [r15+10h], edx
0x180014d73  mov     rdi, [r14]
0x180014d76  mov     rax, [rdi]
0x180014d79  mov     rbx, [rax+60h]
0x180014d7d  mov     [rsp+88h+var_40], 0
0x180014d86  mov     r9d, 12h; unsigned int
0x180014d8c  lea     r8d, [r9+1]; unsigned int
0x180014d90  lea     rdx, aUsewerfortelem; "UseWERForTelemetry"
0x180014d97  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x180014d9c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014da1  nop
0x180014da2  lea     r8, [r15+14h]
0x180014da6  mov     rdx, [rsp+88h+var_40]
0x180014dab  mov     rcx, rdi
0x180014dae  mov     rax, rbx
0x180014db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014db6  nop
0x180014db7  shr     eax, 1Fh
0x180014dba  test    al, al
0x180014dbc  jz      short loc_180014DD1
0x180014dbe  mov     rax, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x180014dc5  mov     cl, [rax+0F0h]
0x180014dcb  mov     [r15+14h], cl
0x180014dcf  jmp     short loc_180014DD3
0x180014dd1  mov     esi, ebp
0x180014dd3  mov     rcx, r14
0x180014dd6  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x180014ddb  mov     eax, esi
0x180014ddd  mov     rcx, [rsp+88h+var_38]
0x180014de2  xor     rcx, rsp; StackCookie
0x180014de5  call    __security_check_cookie
0x180014dea  mov     rbx, [rsp+88h+arg_10]
0x180014df2  add     rsp, 60h
0x180014df6  pop     r15
0x180014df8  pop     r14
0x180014dfa  pop     rdi
0x180014dfb  pop     rsi
0x180014dfc  pop     rbp
0x180014dfd  retn
```
