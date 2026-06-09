# Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)

- ea: `0x180006b30`
- end: `0x180006ce6`
- name: `??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z`
- size: `438`
- prototype: `Broker::ApplicationIdentity *__fastcall(Broker::ApplicationIdentity *this, void *, const unsigned __int16 *)`
- caller_count: `14`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001208`
- `0x180007350`
- `0x180008724`
- `0x1800087e8`
- `0x180009bb0`
- `0x180009ee0`
- `0x1800110a0`
- `0x180014a7c`
- `0x180014f50`
- `0x180017578`
- `0x18001764c`
- `0x1800178fc`
- `0x1800187b8`
- `0x18001ab8c`

## callees

- `0x180006b30`
- `0x180006cec`
- `0x18000ab10`
- `0x180012cd0`
- `0x180015af0`
- `0x1800165b6`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006bb7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006bb7`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180006c3f`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180006c3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
Broker::ApplicationIdentity *__fastcall Broker::ApplicationIdentity::ApplicationIdentity(
        Broker::ApplicationIdentity *this,
        void *a2,
        const unsigned __int16 *a3)
{
  _QWORD *v6; // r15
  unsigned __int64 *v7; // r12
  _QWORD *v8; // r14
  unsigned __int64 *v9; // rdi
  DWORD LengthSid; // eax
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // r8
  unsigned __int64 v16; // rax
  size_t v17; // rbx
  UINT32 packageFamilyNameLength[4]; // [rsp+20h] [rbp-168h] BYREF
  Broker::ApplicationIdentity *v20; // [rsp+30h] [rbp-158h]
  WCHAR packageFamilyName[128]; // [rsp+40h] [rbp-148h] BYREF

  v20 = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v6 = (_QWORD *)((char *)this + 24);
  *(_OWORD *)((char *)this + 24) = 0;
  v7 = (unsigned __int64 *)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 7;
  *((_WORD *)this + 12) = 0;
  v8 = (_QWORD *)((char *)this + 56);
  *(_OWORD *)((char *)this + 56) = 0;
  v9 = (unsigned __int64 *)((char *)this + 72);
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 7;
  *((_WORD *)this + 28) = 0;
  if ( a2 )
  {
    LengthSid = GetLengthSid(a2);
    std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(this, *(_QWORD *)this, a2, LengthSid);
  }
  if ( a3 )
  {
    packageFamilyNameLength[0] = 0;
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    v13 = v8[3];
    if ( v12 > v13 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v8, v12, a3, a3);
    }
    else
    {
      if ( v13 > 7 )
        v8 = (_QWORD *)*v8;
      *v9 = v12;
      v14 = 2 * v12;
      memmove_0(v8, a3, 2 * v12);
      *(_WORD *)((char *)v8 + v14) = 0;
    }
    packageFamilyNameLength[0] = 128;
    if ( PackageFamilyNameFromFullName(a3, packageFamilyNameLength, packageFamilyName) )
    {
      std::wstring::assign(v6, a3);
    }
    else
    {
      do
        ++v11;
      while ( packageFamilyName[v11] );
      v16 = v6[3];
      if ( v11 > v16 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v6,
          v11,
          v15,
          packageFamilyName);
      }
      else
      {
        if ( v16 > 7 )
          v6 = (_QWORD *)*v6;
        *v7 = v11;
        v17 = 2 * v11;
        memmove_0(v6, packageFamilyName, v17);
        *(_WORD *)((char *)v6 + v17) = 0;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180006b30  mov     [rsp+arg_18], rbx
0x180006b35  push    rbp
0x180006b36  push    rsi
0x180006b37  push    rdi
0x180006b38  push    r12
0x180006b3a  push    r13
0x180006b3c  push    r14
0x180006b3e  push    r15
0x180006b40  sub     rsp, 150h
0x180006b47  mov     rax, cs:__security_cookie
0x180006b4e  xor     rax, rsp
0x180006b51  mov     [rsp+188h+var_48], rax
0x180006b59  mov     rsi, r8
0x180006b5c  mov     rbx, rdx
0x180006b5f  mov     rbp, rcx
0x180006b62  mov     [rsp+188h+var_158], rcx
0x180006b67  xor     r13d, r13d
0x180006b6a  mov     [rcx], r13
0x180006b6d  mov     [rcx+8], r13
0x180006b71  mov     [rcx+10h], r13
0x180006b75  lea     r15, [rcx+18h]
0x180006b79  xorps   xmm0, xmm0
0x180006b7c  movups  xmmword ptr [r15], xmm0
0x180006b80  lea     r12, [r15+10h]
0x180006b84  mov     [r12], r13
0x180006b88  mov     qword ptr [r15+18h], 7
0x180006b90  mov     [r15], r13w
0x180006b94  lea     r14, [rcx+38h]
0x180006b98  movups  xmmword ptr [r14], xmm0
0x180006b9c  lea     rdi, [r14+10h]
0x180006ba0  mov     [rdi], r13
0x180006ba3  mov     qword ptr [r14+18h], 7
0x180006bab  mov     [r14], r13w
0x180006baf  test    rdx, rdx
0x180006bb2  jz      short loc_180006BCF
0x180006bb4  mov     rcx, rdx; pSid
0x180006bb7  call    cs:__imp_GetLengthSid
0x180006bbd  mov     r9d, eax
0x180006bc0  mov     r8, rbx
0x180006bc3  mov     rdx, [rbp+0]
0x180006bc7  mov     rcx, rbp
0x180006bca  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x180006bcf  test    rsi, rsi
0x180006bd2  jz      loc_180006C88
0x180006bd8  mov     [rsp+188h+packageFamilyNameLength], r13d
0x180006bdd  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180006be4  mov     rdx, rbx
0x180006be7  nop     word ptr [rax+rax+00000000h]
0x180006bf0  inc     rdx
0x180006bf3  cmp     word ptr [rsi+rdx*2], 0
0x180006bf8  jnz     short loc_180006BF0
0x180006bfa  mov     rax, [r14+18h]
0x180006bfe  cmp     rdx, rax
0x180006c01  ja      loc_180006CC3
0x180006c07  cmp     rax, 7
0x180006c0b  jbe     short loc_180006C10
0x180006c0d  mov     r14, [r14]
0x180006c10  mov     [rdi], rdx
0x180006c13  lea     rdi, [rdx+rdx]
0x180006c17  mov     r8, rdi; Size
0x180006c1a  mov     rdx, rsi; Src
0x180006c1d  mov     rcx, r14; void *
0x180006c20  call    memmove_0
0x180006c25  mov     [rdi+r14], r13w
0x180006c2a  mov     [rsp+188h+packageFamilyNameLength], 80h
0x180006c32  lea     r8, [rsp+188h+packageFamilyName]; packageFamilyName
0x180006c37  lea     rdx, [rsp+188h+packageFamilyNameLength]; packageFamilyNameLength
0x180006c3c  mov     rcx, rsi; packageFullName
0x180006c3f  call    cs:__imp_PackageFamilyNameFromFullName
0x180006c45  test    eax, eax
0x180006c47  jnz     short loc_180006CB6
0x180006c49  lea     rax, [rsp+188h+packageFamilyName]
0x180006c4e  xchg    ax, ax
0x180006c50  inc     rbx
0x180006c53  cmp     word ptr [rax+rbx*2], 0
0x180006c58  jnz     short loc_180006C50
0x180006c5a  mov     rax, [r15+18h]
0x180006c5e  cmp     rbx, rax
0x180006c61  ja      short loc_180006CD3
0x180006c63  cmp     rax, 7
0x180006c67  jbe     short loc_180006C6C
0x180006c69  mov     r15, [r15]
0x180006c6c  mov     [r12], rbx
0x180006c70  add     rbx, rbx
0x180006c73  mov     r8, rbx; Size
0x180006c76  lea     rdx, [rsp+188h+packageFamilyName]; Src
0x180006c7b  mov     rcx, r15; void *
0x180006c7e  call    memmove_0
0x180006c83  mov     [rbx+r15], r13w
0x180006c88  mov     rax, rbp
0x180006c8b  mov     rcx, [rsp+188h+var_48]
0x180006c93  xor     rcx, rsp; StackCookie
0x180006c96  call    __security_check_cookie
0x180006c9b  mov     rbx, [rsp+188h+arg_18]
0x180006ca3  add     rsp, 150h
0x180006caa  pop     r15
0x180006cac  pop     r14
0x180006cae  pop     r13
0x180006cb0  pop     r12
0x180006cb2  pop     rdi
0x180006cb3  pop     rsi
0x180006cb4  pop     rbp
0x180006cb5  retn
0x180006cb6  mov     rdx, rsi
0x180006cb9  mov     rcx, r15
0x180006cbc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180006cc1  jmp     short loc_180006C88
0x180006cc3  mov     r9, rsi
0x180006cc6  mov     rcx, r14
0x180006cc9  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180006cce  jmp     loc_180006C2A
0x180006cd3  lea     r9, [rsp+188h+packageFamilyName]
0x180006cd8  mov     rdx, rbx
0x180006cdb  mov     rcx, r15
0x180006cde  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180006ce3  jmp     short loc_180006C88
```
