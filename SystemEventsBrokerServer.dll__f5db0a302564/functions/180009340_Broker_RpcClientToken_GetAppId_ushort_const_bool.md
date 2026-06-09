# Broker::RpcClientToken::GetAppId(ushort const *,bool)

- ea: `0x180009340`
- end: `0x1800095ea`
- name: `?GetAppId@RpcClientToken@Broker@@QEAA?AUApplicationIdentity@2@PEBG_N@Z`
- size: `682`
- prototype: `_BYTE **__fastcall(__int64, _BYTE **, __int128 *, char)`
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800029c0`
- `0x180010560`
- `0x18001aee0`
- `0x18001b5d0`
- `0x18001bb90`
- `0x18001e150`

## callees

- `0x180009340`
- `0x18000b168`
- `0x18000b180`
- `0x18000bbc0`
- `0x18000beb4`
- `0x180019130`
- `0x18001ab64`
- `0x18001cf50`
- `0x18001d364`
- `0x18001e0d8`
- `0x18001e3bc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009555`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009555`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800094ac`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800094ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_BYTE **__fastcall Broker::RpcClientToken::GetAppId(__int64 a1, _BYTE **a2, __int128 *a3, char a4)
{
  __int64 PackageFullName; // rbx
  void *v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // r8
  WCHAR *v12; // rdx
  void *v13; // rcx
  DWORD LengthSid; // eax
  UINT32 packageFamilyNameLength[2]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v17[3]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v18; // [rsp+48h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+58h] [rbp-A8h]
  void *v20[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h]
  unsigned __int64 v22; // [rsp+80h] [rbp-80h]
  WCHAR packageFamilyName[128]; // [rsp+90h] [rbp-70h] BYREF

  v17[0] = (unsigned __int64)a2;
  v18 = 0;
  si128 = 0;
  std::wstring::_Construct_empty((__int64)&v18);
  PackageFullName = Broker::RpcClientToken::GetPackageFullName(a1, v20);
  if ( &v18 != (__int128 *)PackageFullName )
  {
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)v18, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v18) = 0;
    v18 = *(_OWORD *)PackageFullName;
    si128 = *(__m128i *)(PackageFullName + 16);
    *(_QWORD *)(PackageFullName + 16) = 0;
    *(_QWORD *)(PackageFullName + 24) = 7;
    *(_WORD *)PackageFullName = 0;
  }
  if ( v22 > 7 )
    std::_Deallocate<16>(v20[0], 2 * v22 + 2);
  if ( !a4 )
  {
    if ( si128.m128i_i64[0] )
    {
      a3 = &v18;
      if ( si128.m128i_i64[1] > 7uLL )
        a3 = (__int128 *)v18;
    }
  }
  v9 = *(void **)Broker::RpcClientToken::GetUserSid(a1, v20);
  std::vector<_GUID>::vector<_GUID>(a2);
  *(_OWORD *)(a2 + 3) = 0;
  a2[5] = 0;
  a2[6] = 0;
  std::wstring::_Construct_empty((__int64)(a2 + 3));
  *(_OWORD *)(a2 + 7) = 0;
  a2[9] = 0;
  a2[10] = 0;
  std::wstring::_Construct_empty((__int64)(a2 + 7));
  if ( v9 )
  {
    LengthSid = GetLengthSid(v9);
    std::vector<unsigned char>::_Insert_counted_range<unsigned char *>((__int64)a2, *a2, v9, LengthSid);
  }
  if ( a3 )
  {
    packageFamilyNameLength[0] = 0;
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)a3 + v11) );
    std::wstring::_Assign<unsigned short>(a2 + 7, a3, (char *)v11);
    packageFamilyNameLength[0] = 128;
    if ( PackageFamilyNameFromFullName((PCWSTR)a3, packageFamilyNameLength, packageFamilyName) )
    {
      do
        ++v10;
      while ( *((_WORD *)a3 + v10) );
      v12 = (WCHAR *)a3;
    }
    else
    {
      do
        ++v10;
      while ( packageFamilyName[v10] );
      v12 = packageFamilyName;
    }
    std::wstring::_Assign<unsigned short>(a2 + 3, v12, (char *)v10);
  }
  v13 = v20[0];
  if ( v20[0] )
  {
    v17[0] = v21 - (unsigned __int64)v20[0];
    *(void **)packageFamilyNameLength = v20[0];
    if ( v21 - (unsigned __int64)v20[0] >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)packageFamilyNameLength, v17);
      v13 = *(void **)packageFamilyNameLength;
    }
    operator delete(v13);
  }
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>((void *)v18, 2 * si128.m128i_i64[1] + 2);
  return a2;
}

```

## disassembly

```asm
0x180009340  push    rbp
0x180009342  push    rbx
0x180009343  push    rsi
0x180009344  push    rdi
0x180009345  push    r12
0x180009347  push    r14
0x180009349  push    r15
0x18000934b  lea     rbp, [rsp-0A0h]
0x180009353  sub     rsp, 1A0h
0x18000935a  mov     rax, cs:__security_cookie
0x180009361  xor     rax, rsp
0x180009364  mov     [rbp+0D0h+var_40], rax
0x18000936b  movzx   esi, r9b
0x18000936f  mov     rdi, r8
0x180009372  mov     r14, rdx
0x180009375  mov     r15, rcx
0x180009378  mov     [rsp+1D0h+var_1A0], rdx
0x18000937d  xor     r12d, r12d
0x180009380  xorps   xmm0, xmm0
0x180009383  movups  [rsp+1D0h+var_188], xmm0
0x180009388  xorps   xmm1, xmm1
0x18000938b  movdqu  [rsp+1D0h+var_178], xmm1
0x180009391  lea     rcx, [rsp+1D0h+var_188]
0x180009396  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000939b  nop
0x18000939c  lea     rdx, [rsp+1D0h+var_168]
0x1800093a1  mov     rcx, r15
0x1800093a4  call    ?GetPackageFullName@RpcClientToken@Broker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Broker::RpcClientToken::GetPackageFullName(void)
0x1800093a9  mov     rbx, rax
0x1800093ac  lea     rax, [rsp+1D0h+var_188]
0x1800093b1  cmp     rax, rbx
0x1800093b4  jz      short loc_1800093FA
0x1800093b6  mov     rdx, qword ptr [rsp+1D0h+var_178+8]
0x1800093bb  cmp     rdx, 7
0x1800093bf  ja      loc_180009571
0x1800093c5  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800093cd  movdqu  [rsp+1D0h+var_178], xmm0
0x1800093d3  mov     word ptr [rsp+1D0h+var_188], r12w
0x1800093d9  movups  xmm0, xmmword ptr [rbx]
0x1800093dc  movups  [rsp+1D0h+var_188], xmm0
0x1800093e1  movups  xmm1, xmmword ptr [rbx+10h]
0x1800093e5  movups  [rsp+1D0h+var_178], xmm1
0x1800093ea  mov     [rbx+10h], r12
0x1800093ee  mov     qword ptr [rbx+18h], 7
0x1800093f6  mov     [rbx], r12w
0x1800093fa  mov     rdx, [rbp+0D0h+var_150]
0x1800093fe  cmp     rdx, 7
0x180009402  ja      loc_180009588
0x180009408  test    sil, sil
0x18000940b  jnz     short loc_180009419
0x18000940d  cmp     qword ptr [rsp+1D0h+var_178], 0
0x180009413  jnz     loc_18000959F
0x180009419  lea     rdx, [rsp+1D0h+var_168]
0x18000941e  mov     rcx, r15
0x180009421  call    ?GetUserSid@RpcClientToken@Broker@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; Broker::RpcClientToken::GetUserSid(void)
0x180009426  nop
0x180009427  mov     rbx, [rax]
0x18000942a  mov     rcx, r14
0x18000942d  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180009432  nop
0x180009433  xorps   xmm0, xmm0
0x180009436  movups  xmmword ptr [r14+18h], xmm0
0x18000943b  mov     [r14+28h], r12
0x18000943f  mov     [r14+30h], r12
0x180009443  lea     rcx, [r14+18h]
0x180009447  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000944c  nop
0x18000944d  movups  xmmword ptr [r14+38h], xmm0
0x180009452  mov     [r14+48h], r12
0x180009456  mov     [r14+50h], r12
0x18000945a  lea     rcx, [r14+38h]
0x18000945e  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180009463  nop
0x180009464  test    rbx, rbx
0x180009467  jnz     loc_180009552
0x18000946d  test    rdi, rdi
0x180009470  jz      short loc_1800094DB
0x180009472  mov     [rsp+1D0h+packageFamilyNameLength], r12d
0x180009477  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000947e  mov     r8, rbx
0x180009481  inc     r8
0x180009484  cmp     word ptr [rdi+r8*2], 0
0x18000948a  jnz     short loc_180009481
0x18000948c  mov     rdx, rdi
0x18000948f  lea     rcx, [r14+38h]
0x180009493  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180009498  mov     [rsp+1D0h+packageFamilyNameLength], 80h
0x1800094a0  lea     r8, [rbp+0D0h+packageFamilyName]; packageFamilyName
0x1800094a4  lea     rdx, [rsp+1D0h+packageFamilyNameLength]; packageFamilyNameLength
0x1800094a9  mov     rcx, rdi; packageFullName
0x1800094ac  call    cs:__imp_PackageFamilyNameFromFullName
0x1800094b2  test    eax, eax
0x1800094b4  jnz     loc_180009540
0x1800094ba  lea     rax, [rbp+0D0h+packageFamilyName]
0x1800094be  xchg    ax, ax
0x1800094c0  inc     rbx
0x1800094c3  cmp     word ptr [rax+rbx*2], 0
0x1800094c8  jnz     short loc_1800094C0
0x1800094ca  lea     rdx, [rbp+0D0h+packageFamilyName]
0x1800094ce  mov     r8, rbx
0x1800094d1  lea     rcx, [r14+18h]
0x1800094d5  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800094da  nop
0x1800094db  mov     rcx, [rsp+1D0h+var_168]; void *
0x1800094e0  test    rcx, rcx
0x1800094e3  jz      short loc_18000950A
0x1800094e5  mov     rdx, [rsp+1D0h+var_158]
0x1800094ea  sub     rdx, rcx; unsigned __int64
0x1800094ed  mov     [rsp+1D0h+var_1A0], rdx
0x1800094f2  mov     qword ptr [rsp+1D0h+packageFamilyNameLength], rcx
0x1800094f7  cmp     rdx, 1000h
0x1800094fe  jnb     loc_1800095B5
0x180009504  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009509  nop
0x18000950a  mov     rdx, qword ptr [rsp+1D0h+var_178+8]
0x18000950f  cmp     rdx, 7
0x180009513  ja      loc_1800095D3
0x180009519  mov     rax, r14
0x18000951c  mov     rcx, [rbp+0D0h+var_40]
0x180009523  xor     rcx, rsp; StackCookie
0x180009526  call    __security_check_cookie
0x18000952b  add     rsp, 1A0h
0x180009532  pop     r15
0x180009534  pop     r14
0x180009536  pop     r12
0x180009538  pop     rdi
0x180009539  pop     rsi
0x18000953a  pop     rbx
0x18000953b  pop     rbp
0x18000953c  retn
0x180009540  inc     rbx
0x180009543  cmp     word ptr [rdi+rbx*2], 0
0x180009548  jnz     short loc_180009540
0x18000954a  mov     rdx, rdi
0x18000954d  jmp     loc_1800094CE
0x180009552  mov     rcx, rbx; pSid
0x180009555  call    cs:__imp_GetLengthSid
0x18000955b  mov     r9d, eax
0x18000955e  mov     r8, rbx
0x180009561  mov     rdx, [r14]
0x180009564  mov     rcx, r14
0x180009567  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18000956c  jmp     loc_18000946D
0x180009571  lea     rdx, ds:2[rdx*2]
0x180009579  mov     rcx, qword ptr [rsp+1D0h+var_188]
0x18000957e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009583  jmp     loc_1800093C5
0x180009588  lea     rdx, ds:2[rdx*2]
0x180009590  mov     rcx, [rsp+1D0h+var_168]
0x180009595  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000959a  jmp     loc_180009408
0x18000959f  lea     rdi, [rsp+1D0h+var_188]
0x1800095a4  cmp     qword ptr [rsp+1D0h+var_178+8], 7
0x1800095aa  cmova   rdi, qword ptr [rsp+1D0h+var_188]
0x1800095b0  jmp     loc_180009419
0x1800095b5  lea     rdx, [rsp+1D0h+var_1A0]; unsigned __int64 *
0x1800095ba  lea     rcx, [rsp+1D0h+packageFamilyNameLength]; void **
0x1800095bf  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1800095c4  mov     rcx, qword ptr [rsp+1D0h+packageFamilyNameLength]
0x1800095c9  mov     rdx, [rsp+1D0h+var_1A0]
0x1800095ce  jmp     loc_180009504
0x1800095d3  lea     rdx, ds:2[rdx*2]
0x1800095db  mov     rcx, qword ptr [rsp+1D0h+var_188]
0x1800095e0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800095e5  jmp     loc_180009519
```
