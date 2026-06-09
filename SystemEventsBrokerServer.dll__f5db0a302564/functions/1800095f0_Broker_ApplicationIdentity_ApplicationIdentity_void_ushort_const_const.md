# Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)

- ea: `0x1800095f0`
- end: `0x180009735`
- name: `??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z`
- size: `325`
- prototype: `Broker::ApplicationIdentity *__fastcall(char **this, void *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ea70`
- `0x18001eba0`
- `0x18001fd50`

## callees

- `0x1800095f0`
- `0x18000b168`
- `0x18000beb4`
- `0x18001ab64`
- `0x18001cf50`
- `0x18001e3bc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009718`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009718`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800096ac`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800096ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
Broker::ApplicationIdentity *__fastcall Broker::ApplicationIdentity::ApplicationIdentity(
        char **this,
        void *a2,
        unsigned __int16 *a3)
{
  __int128 v6; // xmm0
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // r8
  WCHAR *v11; // rdx
  DWORD LengthSid; // eax
  UINT32 packageFamilyNameLength[4]; // [rsp+20h] [rbp-158h] BYREF
  Broker::ApplicationIdentity *v15; // [rsp+30h] [rbp-148h]
  WCHAR packageFamilyName[128]; // [rsp+40h] [rbp-138h] BYREF

  v15 = (Broker::ApplicationIdentity *)this;
  std::vector<_GUID>::vector<_GUID>(this);
  v6 = 0;
  *(_OWORD *)(v7 + 24) = 0;
  *(_QWORD *)(v7 + 40) = 0;
  *(_QWORD *)(v7 + 48) = 0;
  *(double *)&v6 = std::wstring::_Construct_empty(v7 + 24);
  *(_OWORD *)(this + 7) = v6;
  this[9] = 0;
  this[10] = 0;
  std::wstring::_Construct_empty(this + 7);
  if ( v8 )
  {
    LengthSid = GetLengthSid(a2);
    std::vector<unsigned char>::_Insert_counted_range<unsigned char *>((__int64)this, *this, a2, LengthSid);
  }
  if ( a3 )
  {
    packageFamilyNameLength[0] = 0;
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    std::wstring::_Assign<unsigned short>(this + 7, a3, (char *)v10);
    packageFamilyNameLength[0] = 128;
    if ( PackageFamilyNameFromFullName(a3, packageFamilyNameLength, packageFamilyName) )
    {
      do
        ++v9;
      while ( a3[v9] );
      v11 = a3;
    }
    else
    {
      do
        ++v9;
      while ( packageFamilyName[v9] );
      v11 = packageFamilyName;
    }
    std::wstring::_Assign<unsigned short>(this + 3, v11, (char *)v9);
  }
  return (Broker::ApplicationIdentity *)this;
}

```

## disassembly

```asm
0x1800095f0  mov     [rsp+arg_18], rbx
0x1800095f5  push    rbp
0x1800095f6  push    rsi
0x1800095f7  push    rdi
0x1800095f8  push    r14
0x1800095fa  push    r15
0x1800095fc  sub     rsp, 150h
0x180009603  mov     rax, cs:__security_cookie
0x18000960a  xor     rax, rsp
0x18000960d  mov     [rsp+178h+var_38], rax
0x180009615  mov     rdi, r8
0x180009618  mov     rbx, rdx
0x18000961b  mov     rsi, rcx
0x18000961e  mov     [rsp+178h+var_148], rcx
0x180009623  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180009628  nop
0x180009629  xorps   xmm0, xmm0
0x18000962c  movups  xmmword ptr [rcx+18h], xmm0
0x180009630  xor     r15d, r15d
0x180009633  mov     [rcx+28h], r15
0x180009637  mov     [rcx+30h], r15
0x18000963b  add     rcx, 18h
0x18000963f  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180009644  nop
0x180009645  movups  xmmword ptr [rsi+38h], xmm0
0x180009649  mov     [rsi+48h], r15
0x18000964d  mov     [rsi+50h], r15
0x180009651  lea     rcx, [rsi+38h]
0x180009655  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000965a  nop
0x18000965b  test    rdx, rdx
0x18000965e  jnz     loc_180009715
0x180009664  test    rdi, rdi
0x180009667  jz      short loc_1800096DC
0x180009669  mov     [rsp+178h+packageFamilyNameLength], r15d
0x18000966e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180009675  mov     r8, rbx
0x180009678  nop     dword ptr [rax+rax+00000000h]
0x180009680  inc     r8
0x180009683  cmp     word ptr [rdi+r8*2], 0
0x180009689  jnz     short loc_180009680
0x18000968b  mov     rdx, rdi
0x18000968e  lea     rcx, [rsi+38h]
0x180009692  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180009697  mov     [rsp+178h+packageFamilyNameLength], 80h
0x18000969f  lea     r8, [rsp+178h+packageFamilyName]; packageFamilyName
0x1800096a4  lea     rdx, [rsp+178h+packageFamilyNameLength]; packageFamilyNameLength
0x1800096a9  mov     rcx, rdi; packageFullName
0x1800096ac  call    cs:__imp_PackageFamilyNameFromFullName
0x1800096b2  test    eax, eax
0x1800096b4  jnz     short loc_180009706
0x1800096b6  lea     rax, [rsp+178h+packageFamilyName]
0x1800096bb  nop     dword ptr [rax+rax+00h]
0x1800096c0  inc     rbx
0x1800096c3  cmp     word ptr [rax+rbx*2], 0
0x1800096c8  jnz     short loc_1800096C0
0x1800096ca  lea     rdx, [rsp+178h+packageFamilyName]
0x1800096cf  mov     r8, rbx
0x1800096d2  lea     rcx, [rsi+18h]
0x1800096d6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800096db  nop
0x1800096dc  mov     rax, rsi
0x1800096df  mov     rcx, [rsp+178h+var_38]
0x1800096e7  xor     rcx, rsp; StackCookie
0x1800096ea  call    __security_check_cookie
0x1800096ef  mov     rbx, [rsp+178h+arg_18]
0x1800096f7  add     rsp, 150h
0x1800096fe  pop     r15
0x180009700  pop     r14
0x180009702  pop     rdi
0x180009703  pop     rsi
0x180009704  pop     rbp
0x180009705  retn
0x180009706  inc     rbx
0x180009709  cmp     word ptr [rdi+rbx*2], 0
0x18000970e  jnz     short loc_180009706
0x180009710  mov     rdx, rdi
0x180009713  jmp     short loc_1800096CF
0x180009715  mov     rcx, rbx; pSid
0x180009718  call    cs:__imp_GetLengthSid
0x18000971e  mov     r9d, eax
0x180009721  mov     r8, rbx
0x180009724  mov     rdx, [rsi]
0x180009727  mov     rcx, rsi
0x18000972a  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18000972f  jmp     loc_180009664
```
