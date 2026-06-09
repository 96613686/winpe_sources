# ReadPrivateScanSettings(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,SCAN_SETTINGS &)

- ea: `0x180014994`
- end: `0x180014ad5`
- name: `?ReadPrivateScanSettings@@YAJV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUSCAN_SETTINGS@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(__int64 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014550`

## callees

- `0x1800050f0`
- `0x18000fd08`
- `0x180010330`
- `0x180011438`
- `0x180014994`
- `0x1800152d4`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall ReadPrivateScanSettings(__int64 *a1, int *a2)
{
  __int64 (__fastcall *v4)(__int64, int *); // r15
  int v5; // ebx
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, __int64, __int64 *); // rbx
  __int64 v8; // rax
  __int64 v10; // [rsp+20h] [rbp-40h] BYREF
  _BYTE v11[8]; // [rsp+28h] [rbp-38h] BYREF
  __int64 *v12; // [rsp+30h] [rbp-30h]
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  __int64 v14; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v12 = a1;
  v4 = *(__int64 (__fastcall **)(__int64, int *))(STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings + 72LL * *a2 + 56);
  if ( v4 )
  {
    v10 = 0;
    v6 = *a1;
    v7 = *(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)*a1 + 64LL);
    v10 = 0;
    v14 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"PrivateSettings", 0x10u, 0xFu);
    if ( v7(v6, v14, &v10) >= 0 )
    {
      v8 = wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(
             v11,
             &v10);
      v5 = v4(v8, a2);
      if ( v5 >= 0 )
        a2[3] = 2;
      else
        a2[3] = 1;
    }
    else
    {
      v5 = -2147024883;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEC,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
        (const char *)0x8007000DLL,
        v10);
    }
    wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v10);
  }
  else
  {
    v5 = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
      (const char *)0x80004001LL,
      v10);
  }
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(a1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014994  mov     [rsp-28h+arg_10], rbx
0x180014999  push    rbp
0x18001499a  push    rsi
0x18001499b  push    rdi
0x18001499c  push    r14
0x18001499e  push    r15
0x1800149a0  mov     rbp, rsp
0x1800149a3  sub     rsp, 60h
0x1800149a7  mov     rax, cs:__security_cookie
0x1800149ae  xor     rax, rsp
0x1800149b1  mov     [rbp+var_8], rax
0x1800149b5  mov     rsi, rdx
0x1800149b8  mov     r14, rcx
0x1800149bb  mov     [rbp+var_30], rcx
0x1800149bf  movsxd  rax, dword ptr [rdx]
0x1800149c2  lea     rcx, [rax+rax*8]
0x1800149c6  mov     rax, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x1800149cd  mov     r15, [rax+rcx*8+38h]
0x1800149d2  test    r15, r15
0x1800149d5  jnz     short loc_1800149F9
0x1800149d7  mov     rcx, [rbp+28h]; this
0x1800149db  mov     ebx, 80004001h
0x1800149e0  mov     r9d, ebx; char *
0x1800149e3  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800149ea  mov     edx, 0E8h; void *
0x1800149ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800149f4  jmp     loc_180014AAB
0x1800149f9  mov     [rbp+var_40], 0
0x180014a01  mov     rdi, [r14]
0x180014a04  mov     rax, [rdi]
0x180014a07  mov     rbx, [rax+40h]
0x180014a0b  mov     [rbp+var_40], 0
0x180014a13  mov     [rbp+var_10], 0
0x180014a1b  mov     r9d, 0Fh; unsigned int
0x180014a21  lea     r8d, [r9+1]; unsigned int
0x180014a25  lea     rdx, aPrivatesetting; "PrivateSettings"
0x180014a2c  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180014a30  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014a35  nop
0x180014a36  lea     r8, [rbp+var_40]
0x180014a3a  mov     rdx, [rbp+var_10]
0x180014a3e  mov     rcx, rdi
0x180014a41  mov     rax, rbx
0x180014a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a49  nop
0x180014a4a  shr     eax, 1Fh
0x180014a4d  test    al, al
0x180014a4f  jz      short loc_180014A70
0x180014a51  mov     rcx, [rbp+28h]; this
0x180014a55  mov     ebx, 8007000Dh
0x180014a5a  mov     r9d, ebx; char *
0x180014a5d  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180014a64  mov     edx, 0ECh; void *
0x180014a69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a6e  jmp     short loc_180014AA1
0x180014a70  lea     rdx, [rbp+var_40]
0x180014a74  lea     rcx, [rbp+var_38]
0x180014a78  call    ??0?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &)
0x180014a7d  mov     rdx, rsi
0x180014a80  mov     rcx, rax
0x180014a83  mov     rax, r15
0x180014a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a8b  mov     ebx, eax
0x180014a8d  test    eax, eax
0x180014a8f  jns     short loc_180014A9A
0x180014a91  mov     dword ptr [rsi+0Ch], 1
0x180014a98  jmp     short loc_180014AA1
0x180014a9a  mov     dword ptr [rsi+0Ch], 2
0x180014aa1  lea     rcx, [rbp+var_40]
0x180014aa5  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x180014aaa  nop
0x180014aab  mov     rcx, r14
0x180014aae  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x180014ab3  mov     eax, ebx
0x180014ab5  mov     rcx, [rbp+var_8]
0x180014ab9  xor     rcx, rsp; StackCookie
0x180014abc  call    __security_check_cookie
0x180014ac1  mov     rbx, [rsp+60h+arg_10]
0x180014ac9  add     rsp, 60h
0x180014acd  pop     r15
0x180014acf  pop     r14
0x180014ad1  pop     rdi
0x180014ad2  pop     rsi
0x180014ad3  pop     rbp
0x180014ad4  retn
```
