# Broker::ApplicationIdentity::SetPackageFullName(ushort const * const)

- ea: `0x18000ca68`
- end: `0x18000cb1e`
- name: `?SetPackageFullName@ApplicationIdentity@Broker@@QEAAXQEBG@Z`
- size: `182`
- prototype: `void __fastcall(Broker::ApplicationIdentity *this, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800042e8`

## callees

- `0x18000ca68`
- `0x180012dd0`
- `0x180019420`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000cac4`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000cac4`

## pseudocode

```c
void __fastcall Broker::ApplicationIdentity::SetPackageFullName(Broker::ApplicationIdentity *this, const WCHAR *a2)
{
  __int64 v3; // rbx
  __int64 v4; // r8
  UINT32 packageFamilyNameLength[4]; // [rsp+20h] [rbp-138h] BYREF
  WCHAR packageFamilyName[128]; // [rsp+30h] [rbp-128h] BYREF

  v3 = -1;
  packageFamilyNameLength[0] = 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  std::wstring::_Assign<unsigned short>((char *)this + 56);
  packageFamilyNameLength[0] = 128;
  if ( PackageFamilyNameFromFullName(a2, packageFamilyNameLength, packageFamilyName) )
  {
    do
      ++v3;
    while ( a2[v3] );
  }
  else
  {
    do
      ++v3;
    while ( packageFamilyName[v3] );
  }
  std::wstring::_Assign<unsigned short>((char *)this + 24);
}

```

## disassembly

```asm
0x18000ca68  mov     [rsp+arg_10], rbx
0x18000ca6d  push    rbp
0x18000ca6e  push    rsi
0x18000ca6f  push    rdi
0x18000ca70  sub     rsp, 140h
0x18000ca77  mov     rax, cs:__security_cookie
0x18000ca7e  xor     rax, rsp
0x18000ca81  mov     [rsp+158h+var_28], rax
0x18000ca89  xor     ebp, ebp
0x18000ca8b  mov     rdi, rdx
0x18000ca8e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ca92  mov     [rsp+158h+packageFamilyNameLength], ebp
0x18000ca96  mov     r8, rbx
0x18000ca99  mov     rsi, rcx
0x18000ca9c  inc     r8
0x18000ca9f  cmp     [rdx+r8*2], bp
0x18000caa4  jnz     short loc_18000CA9C
0x18000caa6  add     rcx, 38h ; '8'
0x18000caaa  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000caaf  lea     r8, [rsp+158h+packageFamilyName]; packageFamilyName
0x18000cab4  mov     [rsp+158h+packageFamilyNameLength], 80h
0x18000cabc  lea     rdx, [rsp+158h+packageFamilyNameLength]; packageFamilyNameLength
0x18000cac1  mov     rcx, rdi; packageFullName
0x18000cac4  call    cs:__imp_PackageFamilyNameFromFullName
0x18000caca  test    eax, eax
0x18000cacc  jnz     short loc_18000CB13
0x18000cace  lea     rax, [rsp+158h+packageFamilyName]
0x18000cad3  inc     rbx
0x18000cad6  cmp     [rax+rbx*2], bp
0x18000cada  jnz     short loc_18000CAD3
0x18000cadc  lea     rdi, [rsp+158h+packageFamilyName]
0x18000cae1  mov     r8, rbx
0x18000cae4  lea     rcx, [rsi+18h]
0x18000cae8  mov     rdx, rdi
0x18000caeb  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000caf0  mov     rcx, [rsp+158h+var_28]
0x18000caf8  xor     rcx, rsp; StackCookie
0x18000cafb  call    __security_check_cookie
0x18000cb00  mov     rbx, [rsp+158h+arg_10]
0x18000cb08  add     rsp, 140h
0x18000cb0f  pop     rdi
0x18000cb10  pop     rsi
0x18000cb11  pop     rbp
0x18000cb12  retn
0x18000cb13  inc     rbx
0x18000cb16  cmp     [rdi+rbx*2], bp
0x18000cb1a  jnz     short loc_18000CB13
0x18000cb1c  jmp     short loc_18000CAE1
```
