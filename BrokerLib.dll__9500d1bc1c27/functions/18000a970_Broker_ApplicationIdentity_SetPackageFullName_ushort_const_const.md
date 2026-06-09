# Broker::ApplicationIdentity::SetPackageFullName(ushort const * const)

- ea: `0x18000a970`
- end: `0x18000ab05`
- name: `?SetPackageFullName@ApplicationIdentity@Broker@@QEAAXQEBG@Z`
- size: `405`
- prototype: `void(Broker::ApplicationIdentity *__hidden this, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013500`

## callees

- `0x18000a970`
- `0x180012cd0`
- `0x180015af0`
- `0x1800165b6`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000aa21`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000aa21`

## pseudocode

```c
void __fastcall Broker::ApplicationIdentity::SetPackageFullName(
        Broker::ApplicationIdentity *this,
        unsigned __int16 *a2,
        __int64 a3)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v6; // rdx
  char *v7; // rcx
  unsigned __int64 v8; // rax
  char *v9; // rbp
  __int64 v10; // rdi
  char *v11; // r14
  __int64 v12; // r8
  unsigned __int64 v13; // rax
  char *v14; // rdi
  size_t v15; // rbx
  unsigned __int64 v16; // rax
  char *v17; // rdi
  size_t v18; // rbx
  WCHAR *v19; // r9
  UINT32 packageFamilyNameLength[4]; // [rsp+20h] [rbp-138h] BYREF
  WCHAR packageFamilyName[128]; // [rsp+30h] [rbp-128h] BYREF

  v3 = -1;
  packageFamilyNameLength[0] = 0;
  v6 = -1;
  v7 = (char *)this + 56;
  do
    ++v6;
  while ( a2[v6] );
  v8 = *((_QWORD *)v7 + 3);
  if ( v6 > v8 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v7, v6, a3, a2);
  }
  else
  {
    if ( v8 <= 7 )
      v9 = v7;
    else
      v9 = *(char **)v7;
    v10 = 2 * v6;
    *((_QWORD *)v7 + 2) = v6;
    memmove_0(v9, a2, 2 * v6);
    *(_WORD *)&v9[v10] = 0;
  }
  packageFamilyNameLength[0] = 128;
  v11 = (char *)this + 24;
  if ( !PackageFamilyNameFromFullName(a2, packageFamilyNameLength, packageFamilyName) )
  {
    do
      ++v3;
    while ( packageFamilyName[v3] );
    v13 = *((_QWORD *)v11 + 3);
    if ( v3 <= v13 )
    {
      if ( v13 <= 7 )
        v14 = v11;
      else
        v14 = *(char **)v11;
      *((_QWORD *)v11 + 2) = v3;
      v15 = 2 * v3;
      memmove_0(v14, packageFamilyName, v15);
      *(_WORD *)&v14[v15] = 0;
      return;
    }
    v19 = packageFamilyName;
LABEL_24:
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v11, v3, v12, v19);
    return;
  }
  do
    ++v3;
  while ( a2[v3] );
  v16 = *((_QWORD *)v11 + 3);
  if ( v3 > v16 )
  {
    v19 = a2;
    goto LABEL_24;
  }
  if ( v16 <= 7 )
    v17 = v11;
  else
    v17 = *(char **)v11;
  *((_QWORD *)v11 + 2) = v3;
  v18 = 2 * v3;
  memmove_0(v17, a2, v18);
  *(_WORD *)&v17[v18] = 0;
}

```

## disassembly

```asm
0x18000a970  push    rbx
0x18000a972  push    rsi
0x18000a973  push    r14
0x18000a975  sub     rsp, 140h
0x18000a97c  mov     rax, cs:__security_cookie
0x18000a983  xor     rax, rsp
0x18000a986  mov     [rsp+158h+var_28], rax
0x18000a98e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a995  mov     [rsp+158h+packageFamilyNameLength], 0
0x18000a99d  mov     rsi, rdx
0x18000a9a0  mov     r14, rcx
0x18000a9a3  mov     rdx, rbx
0x18000a9a6  add     rcx, 38h ; '8'
0x18000a9aa  nop     word ptr [rax+rax+00h]
0x18000a9b0  inc     rdx
0x18000a9b3  cmp     word ptr [rsi+rdx*2], 0
0x18000a9b8  jnz     short loc_18000A9B0
0x18000a9ba  mov     rax, [rcx+18h]
0x18000a9be  mov     [rsp+158h+arg_18], rdi
0x18000a9c6  cmp     rdx, rax
0x18000a9c9  ja      loc_18000AADE
0x18000a9cf  mov     [rsp+158h+arg_10], rbp
0x18000a9d7  cmp     rax, 7
0x18000a9db  jbe     loc_18000AA91
0x18000a9e1  mov     rbp, [rcx]
0x18000a9e4  lea     rdi, [rdx+rdx]
0x18000a9e8  mov     [rcx+10h], rdx
0x18000a9ec  mov     r8, rdi; Size
0x18000a9ef  mov     rdx, rsi; Src
0x18000a9f2  mov     rcx, rbp; void *
0x18000a9f5  call    memmove_0
0x18000a9fa  xor     eax, eax
0x18000a9fc  mov     [rdi+rbp], ax
0x18000aa00  mov     rbp, [rsp+158h+arg_10]
0x18000aa08  lea     r8, [rsp+158h+packageFamilyName]; packageFamilyName
0x18000aa0d  mov     [rsp+158h+packageFamilyNameLength], 80h
0x18000aa15  lea     rdx, [rsp+158h+packageFamilyNameLength]; packageFamilyNameLength
0x18000aa1a  mov     rcx, rsi; packageFullName
0x18000aa1d  add     r14, 18h
0x18000aa21  call    cs:__imp_PackageFamilyNameFromFullName
0x18000aa27  test    eax, eax
0x18000aa29  jnz     short loc_18000AAA0
0x18000aa2b  lea     rax, [rsp+158h+packageFamilyName]
0x18000aa30  inc     rbx
0x18000aa33  cmp     word ptr [rax+rbx*2], 0
0x18000aa38  jnz     short loc_18000AA30
0x18000aa3a  mov     rax, [r14+18h]
0x18000aa3e  cmp     rbx, rax
0x18000aa41  ja      loc_18000AAEB
0x18000aa47  cmp     rax, 7
0x18000aa4b  jbe     short loc_18000AA99
0x18000aa4d  mov     rdi, [r14]
0x18000aa50  mov     [r14+10h], rbx
0x18000aa54  lea     rdx, [rsp+158h+packageFamilyName]; Src
0x18000aa59  add     rbx, rbx
0x18000aa5c  mov     rcx, rdi; void *
0x18000aa5f  mov     r8, rbx; Size
0x18000aa62  call    memmove_0
0x18000aa67  xor     eax, eax
0x18000aa69  mov     [rbx+rdi], ax
0x18000aa6d  mov     rdi, [rsp+158h+arg_18]
0x18000aa75  mov     rcx, [rsp+158h+var_28]
0x18000aa7d  xor     rcx, rsp; StackCookie
0x18000aa80  call    __security_check_cookie
0x18000aa85  add     rsp, 140h
0x18000aa8c  pop     r14
0x18000aa8e  pop     rsi
0x18000aa8f  pop     rbx
0x18000aa90  retn
0x18000aa91  mov     rbp, rcx
0x18000aa94  jmp     loc_18000A9E4
0x18000aa99  mov     rdi, r14
0x18000aa9c  jmp     short loc_18000AA50
0x18000aaa0  inc     rbx
0x18000aaa3  cmp     word ptr [rsi+rbx*2], 0
0x18000aaa8  jnz     short loc_18000AAA0
0x18000aaaa  mov     rax, [r14+18h]
0x18000aaae  cmp     rbx, rax
0x18000aab1  ja      short loc_18000AAF2
0x18000aab3  cmp     rax, 7
0x18000aab7  jbe     short loc_18000AAD9
0x18000aab9  mov     rdi, [r14]
0x18000aabc  mov     [r14+10h], rbx
0x18000aac0  mov     rdx, rsi; Src
0x18000aac3  add     rbx, rbx
0x18000aac6  mov     rcx, rdi; void *
0x18000aac9  mov     r8, rbx; Size
0x18000aacc  call    memmove_0
0x18000aad1  xor     eax, eax
0x18000aad3  mov     [rbx+rdi], ax
0x18000aad7  jmp     short loc_18000AA6D
0x18000aad9  mov     rdi, r14
0x18000aadc  jmp     short loc_18000AABC
0x18000aade  mov     r9, rsi
0x18000aae1  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000aae6  jmp     loc_18000AA08
0x18000aaeb  lea     r9, [rsp+158h+packageFamilyName]
0x18000aaf0  jmp     short loc_18000AAF5
0x18000aaf2  mov     r9, rsi
0x18000aaf5  mov     rdx, rbx
0x18000aaf8  mov     rcx, r14
0x18000aafb  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000ab00  jmp     loc_18000AA6D
```
