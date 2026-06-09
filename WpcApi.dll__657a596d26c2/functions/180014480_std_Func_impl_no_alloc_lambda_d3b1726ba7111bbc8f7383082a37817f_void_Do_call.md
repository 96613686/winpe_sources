# std::_Func_impl_no_alloc__lambda_d3b1726ba7111bbc8f7383082a37817f__void_::_Do_call

- ea: `0x180014480`
- end: `0x1800145f4`
- name: `std::_Func_impl_no_alloc__lambda_d3b1726ba7111bbc8f7383082a37817f__void_::_Do_call`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x1800032a0`
- `0x180005a04`
- `0x180005f9c`
- `0x180010488`
- `0x180014480`
- `0x180015dfc`
- `0x1800163c8`
- `0x1800183a4`
- `0x1800286e8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180014586`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180014586`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800144ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800144ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800144ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800144ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::_Func_impl_no_alloc__lambda_d3b1726ba7111bbc8f7383082a37817f__void_::_Do_call(__int64 a1)
{
  int StringRawBuffer; // eax
  PCWSTR v3; // rax
  __int64 v4; // rcx
  const WCHAR *v5; // rcx
  _BYTE v6[16]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v7[2]; // [rsp+30h] [rbp-D0h] BYREF
  PCNZWCH sourceString[2]; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 length; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v10; // [rsp+58h] [rbp-A8h]
  char v11; // [rsp+60h] [rbp-A0h]
  _OWORD v12[4]; // [rsp+68h] [rbp-98h] BYREF
  int v13; // [rsp+A8h] [rbp-58h]
  _BYTE v14[32]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v15[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v16; // [rsp+110h] [rbp+10h]
  char *v17[5]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v18[8]; // [rsp+140h] [rbp+40h] BYREF
  char *v19; // [rsp+148h] [rbp+48h] BYREF
  char v20; // [rsp+168h] [rbp+68h]
  char *v21; // [rsp+170h] [rbp+70h] BYREF

  ***(_QWORD ***)(a1 + 8) = 0;
  wpc::AppLimits::AppInventory::AppInventoryManager::AppInventoryManager((wpc::AppLimits::AppInventory::AppInventoryManager *)v6);
  StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(**(HSTRING **)(a1 + 16), 0);
  Sid::FromString((__int64)v15, StringRawBuffer);
  v3 = WindowsGetStringRawBuffer(**(HSTRING **)(a1 + 24), 0);
  v4 = -1;
  do
    ++v4;
  while ( v3[v4] );
  v7[0] = v3;
  v7[1] = v4;
  appids::FromPlatformIndependentString(v18, v7);
  v12[0] = v15[0];
  v12[1] = v15[1];
  v12[2] = v15[2];
  v12[3] = v15[3];
  v13 = v16;
  std::wstring::wstring((__int64)v14, (__int64)v17);
  wpc::AppLimits::AppInventory::AppInventoryManager::TryGetDisplayNameForUserApp(v6, sourceString, v12, v18);
  if ( v11 )
  {
    v5 = (const WCHAR *)sourceString;
    if ( v10 > 7 )
      v5 = sourceString[0];
    WindowsCreateString(v5, length, **(HSTRING ***)(a1 + 8));
    if ( v11 )
      std::wstring::~wstring((char **)sourceString);
  }
  std::wstring::~wstring(&v21);
  if ( v20 != -1 )
    std::wstring::~wstring(&v19);
  std::wstring::~wstring(v17);
  wpc::AppLimits::AppInventory::AppInventoryManager::~AppInventoryManager((wpc::AppLimits::AppInventory::AppInventoryManager *)v6);
}

```

## disassembly

```asm
0x180014480  mov     [rsp-8+arg_8], rbx
0x180014485  mov     [rsp-8+arg_10], rdi
0x18001448a  push    rbp
0x18001448b  lea     rbp, [rsp-0A0h]
0x180014493  sub     rsp, 1A0h
0x18001449a  mov     rax, cs:__security_cookie
0x1800144a1  xor     rax, rsp
0x1800144a4  mov     [rbp+0A0h+var_10], rax
0x1800144ab  mov     rbx, rcx
0x1800144ae  xor     edi, edi
0x1800144b0  mov     rax, [rcx+8]
0x1800144b4  mov     rdx, [rax]
0x1800144b7  mov     [rdx], rdi
0x1800144ba  lea     rcx, [rsp+1A0h+var_180]; this
0x1800144bf  call    ??0AppInventoryManager@AppInventory@AppLimits@wpc@@QEAA@XZ; wpc::AppLimits::AppInventory::AppInventoryManager::AppInventoryManager(void)
0x1800144c4  nop
0x1800144c5  mov     rcx, [rbx+10h]
0x1800144c9  xor     edx, edx; length
0x1800144cb  mov     rcx, [rcx]; string
0x1800144ce  call    cs:__imp_WindowsGetStringRawBuffer
0x1800144d4  mov     rdx, rax
0x1800144d7  lea     rcx, [rbp+0A0h+var_D0]
0x1800144db  call    ?FromString@Sid@@SA?AV1@PEBG@Z; Sid::FromString(ushort const *)
0x1800144e0  nop
0x1800144e1  mov     rcx, [rbx+18h]
0x1800144e5  xor     edx, edx; length
0x1800144e7  mov     rcx, [rcx]; string
0x1800144ea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800144f0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800144f4  inc     rcx
0x1800144f7  cmp     [rax+rcx*2], di
0x1800144fb  jnz     short loc_1800144F4
0x1800144fd  mov     [rsp+1A0h+var_170], rax
0x180014502  mov     [rsp+1A0h+var_168], rcx
0x180014507  lea     rdx, [rsp+1A0h+var_170]
0x18001450c  lea     rcx, [rbp+0A0h+var_60]
0x180014510  call    ?FromPlatformIndependentString@appids@@YA?AVAnyRuntimeApp@1@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; appids::FromPlatformIndependentString(std::basic_string_view<ushort>)
0x180014515  nop
0x180014516  movaps  xmm0, [rbp+0A0h+var_D0]
0x18001451a  movups  [rsp+1A0h+var_138], xmm0
0x18001451f  movaps  xmm1, [rbp+0A0h+var_C0]
0x180014523  movups  [rsp+1A0h+var_128], xmm1
0x180014528  movaps  xmm0, [rbp+0A0h+var_B0]
0x18001452c  movups  [rbp+0A0h+var_118], xmm0
0x180014530  movaps  xmm1, [rbp+0A0h+var_A0]
0x180014534  movups  [rbp+0A0h+var_108], xmm1
0x180014538  mov     eax, [rbp+0A0h+var_90]
0x18001453b  mov     [rbp+0A0h+var_F8], eax
0x18001453e  lea     rdx, [rbp+0A0h+var_88]
0x180014542  lea     rcx, [rbp+0A0h+var_F0]
0x180014546  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001454b  lea     r9, [rbp+0A0h+var_60]
0x18001454f  lea     r8, [rsp+1A0h+var_138]
0x180014554  lea     rdx, [rsp+1A0h+sourceString]
0x180014559  lea     rcx, [rsp+1A0h+var_180]
0x18001455e  call    ?TryGetDisplayNameForUserApp@AppInventoryManager@AppInventory@AppLimits@wpc@@QEAA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@VSid@@AEBVAnyRuntimeApp@appids@@@Z; wpc::AppLimits::AppInventory::AppInventoryManager::TryGetDisplayNameForUserApp(Sid,appids::AnyRuntimeApp const &)
0x180014563  cmp     [rsp+1A0h+var_140], dil
0x180014568  jz      short loc_18001459E
0x18001456a  mov     rax, [rbx+8]
0x18001456e  lea     rcx, [rsp+1A0h+sourceString]
0x180014573  cmp     [rsp+1A0h+var_148], 7
0x180014579  cmova   rcx, [rsp+1A0h+sourceString]; sourceString
0x18001457f  mov     r8, [rax]; string
0x180014582  mov     edx, [rsp+1A0h+length]; length
0x180014586  call    cs:__imp_WindowsCreateString
0x18001458c  cmp     [rsp+1A0h+var_140], dil
0x180014591  jz      short loc_18001459E
0x180014593  lea     rcx, [rsp+1A0h+sourceString]
0x180014598  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001459d  nop
0x18001459e  lea     rcx, [rbp+0A0h+var_30]
0x1800145a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800145a7  movsx   rax, [rbp+0A0h+var_38]
0x1800145ac  add     rax, 1
0x1800145b0  jz      short loc_1800145BC
0x1800145b2  lea     rcx, [rbp+0A0h+var_58]
0x1800145b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800145bb  nop
0x1800145bc  lea     rcx, [rbp+0A0h+var_88]
0x1800145c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800145c5  nop
0x1800145c6  lea     rcx, [rsp+1A0h+var_180]; this
0x1800145cb  call    ??1AppInventoryManager@AppInventory@AppLimits@wpc@@QEAA@XZ; wpc::AppLimits::AppInventory::AppInventoryManager::~AppInventoryManager(void)
0x1800145d0  mov     rcx, [rbp+0A0h+var_10]
0x1800145d7  xor     rcx, rsp; StackCookie
0x1800145da  call    __security_check_cookie
0x1800145df  lea     r11, [rsp+1A0h+var_s0]
0x1800145e7  mov     rbx, [r11+18h]
0x1800145eb  mov     rdi, [r11+20h]
0x1800145ef  mov     rsp, r11
0x1800145f2  pop     rbp
0x1800145f3  retn
```
