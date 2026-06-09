# CodeIntegrity::Management::AuthorizationToken::ValidateSpecificData(void)

- ea: `0x180018b50`
- end: `0x180018d0a`
- name: `?ValidateSpecificData@AuthorizationToken@Management@CodeIntegrity@@EEAAXXZ`
- size: `442`
- prototype: `void __fastcall(CodeIntegrity::Management::AuthorizationToken *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018774`
- `0x180018834`

## callees

- `0x180003864`
- `0x1800052e4`
- `0x180016ce0`
- `0x180016d10`
- `0x180018b50`
- `0x180018e88`
- `0x180018f34`
- `0x180019108`
- `0x18001929c`
- `0x180019418`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::AuthorizationToken::ValidateSpecificData(
        CodeIntegrity::Management::AuthorizationToken *this)
{
  __int64 v2; // r8
  __int64 v3; // r9
  char v4; // di
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  _DWORD Buf2[4]; // [rsp+40h] [rbp-38h] BYREF
  _DWORD v10[4]; // [rsp+50h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v13; // [rsp+88h] [rbp+10h] BYREF
  _QWORD *v14; // [rsp+90h] [rbp+18h] BYREF

  v13 = 0;
  Buf2[0] = -358296965;
  Buf2[1] = 1115336418;
  Buf2[2] = -1465402998;
  Buf2[3] = 1587952196;
  v10[0] = -396471215;
  v10[1] = 1202408593;
  v10[2] = -518863191;
  v10[3] = -1392124565;
  Buf1 = *(_OWORD *)(*((_QWORD *)this + 2) + 4LL);
  if ( !memcmp_0(&Buf1, Buf2, 0x10u) )
  {
    v4 = 0;
  }
  else if ( !memcmp_0(&Buf1, v10, 0x10u) )
  {
    v4 = 1;
  }
  else
  {
    v4 = 2;
    *((_WORD *)this + 4) |= 0x100u;
  }
  try
  {
    CodeIntegrity::Management::detail::SbcpTokenView::get_guid((__int64)this, (__int64 *)&v14, v2, v3, L"PolicyID");
    if ( v4 )
    {
      if ( v4 != 1 )
      {
LABEL_14:
        *((_BYTE *)this + 224) = v4;
        if ( (unsigned int)CodeIntegrity::Management::detail::SbcpTokenView::get_dword_nothrow(
                             this,
                             v5,
                             L"Policy",
                             L"Merge",
                             &v13) != -2147023728
          || v13 == 1 )
        {
          *((_WORD *)this + 4) |= 8u;
        }
        CodeIntegrity::Management::AuthorizationToken::load_tenant_id(this);
        CodeIntegrity::Management::AuthorizationToken::load_device_id(this);
        CodeIntegrity::Management::AuthorizationToken::load_tbs_hashes(this);
        CodeIntegrity::Management::AuthorizationToken::load_sha384_hashes(this, v7);
        CodeIntegrity::Management::AuthorizationToken::load_sha512_hashes(this, v8);
        std::unique_ptr<_GUID>::~unique_ptr<_GUID>((void **)&v14);
        return;
      }
      v6 = *v14 - 0x4B4A8A3982443E1ELL;
      if ( *v14 == 0x4B4A8A3982443E1ELL )
        v6 = v14[1] + 0xC46FF23F20B576ALL;
    }
    else
    {
      v6 = *v14 - 0x4D3DE0B55951A96ALL;
      if ( *v14 == 0x4D3DE0B55951A96ALL )
        v6 = v14[1] + 0x7BF8FC9EA4C14771LL;
    }
    if ( v6 )
      *((_WORD *)this + 4) |= 0x200u;
    goto LABEL_14;
  }
  catch ( std::exception )
  {
    *((_WORD *)this + 4) |= 0x200u;
  }
}

```

## disassembly

```asm
0x180018b50  mov     rax, rsp
0x180018b53  mov     [rax+20h], rbx
0x180018b57  mov     [rax+8], rcx
0x180018b5b  push    rdi
0x180018b5c  sub     rsp, 70h
0x180018b60  mov     rbx, rcx
0x180018b63  mov     dword ptr [rax+10h], 0
0x180018b6a  mov     dword ptr [rax-38h], 0EAA4D27Bh
0x180018b71  mov     dword ptr [rax-34h], 427AAEE2h
0x180018b78  mov     dword ptr [rax-30h], 0A8A7B98Ah
0x180018b7f  mov     dword ptr [rax-2Ch], 5EA63A44h
0x180018b86  mov     dword ptr [rax-28h], 0E85E5451h
0x180018b8d  mov     dword ptr [rax-24h], 47AB4C91h
0x180018b94  mov     dword ptr [rax-20h], 0E112C6A9h
0x180018b9b  mov     dword ptr [rax-1Ch], 0AD05DD6Bh
0x180018ba2  mov     dword ptr [rax-48h], 82443E1Eh
0x180018ba9  mov     dword ptr [rax-44h], 4B4A8A39h
0x180018bb0  mov     dword ptr [rax-40h], 0DF4A896h
0x180018bb7  mov     dword ptr [rax-3Ch], 0F3B900DCh
0x180018bbe  mov     rax, [rcx+10h]
0x180018bc2  movups  xmm0, xmmword ptr [rax+4]
0x180018bc6  movdqu  [rsp+78h+Buf1], xmm0
0x180018bcc  mov     edi, 10h
0x180018bd1  mov     r8d, edi; Size
0x180018bd4  lea     rdx, [rsp+78h+Buf2]; Buf2
0x180018bd9  lea     rcx, [rsp+78h+Buf1]; Buf1
0x180018bde  call    memcmp_0
0x180018be3  test    eax, eax
0x180018be5  jnz     short loc_180018BEC
0x180018be7  xor     dil, dil
0x180018bea  jmp     short loc_180018C13
0x180018bec  mov     r8, rdi; Size
0x180018bef  lea     rdx, [rsp+78h+var_28]; Buf2
0x180018bf4  lea     rcx, [rsp+78h+Buf1]; Buf1
0x180018bf9  call    memcmp_0
0x180018bfe  test    eax, eax
0x180018c00  jnz     short loc_180018C07
0x180018c02  mov     dil, 1
0x180018c05  jmp     short loc_180018C13
0x180018c07  mov     dil, 2
0x180018c0a  mov     eax, 100h
0x180018c0f  or      [rbx+8], ax
0x180018c13  lea     rax, aPolicyid; "PolicyID"
0x180018c1a  mov     [rsp+78h+SourceString], rax; SourceString
0x180018c1f  lea     rdx, [rsp+78h+arg_10]; int
0x180018c27  mov     rcx, rbx; int
0x180018c2a  call    ?get_guid@SbcpTokenView@detail@Management@CodeIntegrity@@IEAA?AV?$unique_ptr@U_GUID@@U?$default_delete@U_GUID@@@std@@@std@@IPEBG0@Z; CodeIntegrity::Management::detail::SbcpTokenView::get_guid(uint,ushort const *,ushort const *)
0x180018c2f  test    dil, dil
0x180018c32  jnz     short loc_180018C55
0x180018c34  mov     rcx, [rsp+78h+arg_10]
0x180018c3c  mov     rax, [rcx]
0x180018c3f  sub     rax, cs:qword_18002F310
0x180018c46  jnz     short loc_180018C76
0x180018c48  mov     rax, [rcx+8]
0x180018c4c  sub     rax, cs:qword_18002F318
0x180018c53  jmp     short loc_180018C76
0x180018c55  cmp     dil, 1
0x180018c59  jnz     short loc_180018C84
0x180018c5b  mov     rcx, [rsp+78h+arg_10]
0x180018c63  mov     rax, [rcx]
0x180018c66  sub     rax, [rsp+78h+var_48]
0x180018c6b  jnz     short loc_180018C76
0x180018c6d  mov     rax, [rcx+8]
0x180018c71  sub     rax, [rsp+78h+var_40]
0x180018c76  test    rax, rax
0x180018c79  jz      short loc_180018C84
0x180018c7b  mov     eax, 200h
0x180018c80  or      [rbx+8], ax
0x180018c84  mov     [rbx+0E0h], dil
0x180018c8b  lea     rax, [rsp+78h+arg_8]
0x180018c93  mov     [rsp+78h+SourceString], rax; unsigned int *
0x180018c98  lea     r9, aMerge; "Merge"
0x180018c9f  lea     r8, aPolicy; "Policy"
0x180018ca6  mov     rcx, rbx; this
0x180018ca9  call    ?get_dword_nothrow@SbcpTokenView@detail@Management@CodeIntegrity@@IEAAJIPEBG0PEAI@Z; CodeIntegrity::Management::detail::SbcpTokenView::get_dword_nothrow(uint,ushort const *,ushort const *,uint *)
0x180018cae  cmp     eax, 80070490h
0x180018cb3  jnz     short loc_180018CBF
0x180018cb5  cmp     [rsp+78h+arg_8], 1
0x180018cbd  jnz     short loc_180018CC4
0x180018cbf  or      word ptr [rbx+8], 8
0x180018cc4  mov     rcx, rbx; this
0x180018cc7  call    ?load_tenant_id@AuthorizationToken@Management@CodeIntegrity@@AEAAXXZ; CodeIntegrity::Management::AuthorizationToken::load_tenant_id(void)
0x180018ccc  mov     rcx, rbx; this
0x180018ccf  call    ?load_device_id@AuthorizationToken@Management@CodeIntegrity@@AEAAXXZ; CodeIntegrity::Management::AuthorizationToken::load_device_id(void)
0x180018cd4  mov     rcx, rbx; this
0x180018cd7  call    ?load_tbs_hashes@AuthorizationToken@Management@CodeIntegrity@@AEAAXXZ; CodeIntegrity::Management::AuthorizationToken::load_tbs_hashes(void)
0x180018cdc  mov     rcx, rbx; this
0x180018cdf  call    ?load_sha384_hashes@AuthorizationToken@Management@CodeIntegrity@@AEAAXXZ; CodeIntegrity::Management::AuthorizationToken::load_sha384_hashes(void)
0x180018ce4  mov     rcx, rbx; this
0x180018ce7  call    ?load_sha512_hashes@AuthorizationToken@Management@CodeIntegrity@@AEAAXXZ; CodeIntegrity::Management::AuthorizationToken::load_sha512_hashes(void)
0x180018cec  lea     rcx, [rsp+78h+arg_10]
0x180018cf4  call    ??1?$unique_ptr@U_GUID@@U?$default_delete@U_GUID@@@std@@@std@@QEAA@XZ; std::unique_ptr<_GUID>::~unique_ptr<_GUID>(void)
0x180018cf9  nop
0x180018cfa  jmp     short $+2
0x180018cfc  mov     rbx, [rsp+78h+arg_18]
0x180018d04  add     rsp, 70h
0x180018d08  pop     rdi
0x180018d09  retn
```
