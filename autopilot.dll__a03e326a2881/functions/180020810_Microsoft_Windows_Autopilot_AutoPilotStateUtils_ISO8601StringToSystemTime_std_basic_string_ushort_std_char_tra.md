# Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_SYSTEMTIME &)

- ea: `0x180020810`
- end: `0x180020a7b`
- name: `?ISO8601StringToSystemTime@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SYSTEMTIME@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001ba54`
- `0x18001c894`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013be0`
- `0x1800174f0`
- `0x18001f85c`
- `0x18001fba4`
- `0x18001fcc0`
- `0x180020810`
- `0x180020fd8`
- `0x180021108`

## import_xrefs

- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x180020966`
- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x180020966`
- `msvcp_win!?exceptions@ios_base@std@@QEAAXH@Z` at `0x1800208dd`
- `msvcp_win!?exceptions@ios_base@std@@QEAAXH@Z` at `0x1800208dd`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002098a`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180020a10`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002098a`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180020a10`

## string_xrefs

- `0x180020a2f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime(__int64 a1, _WORD *a2)
{
  _QWORD *i; // rbx
  __int128 *v4; // rdx
  _WORD *v5; // rax
  bool v6; // zf
  __int16 v7; // cx
  __int16 v8; // dx
  __int16 v9; // r8
  __int16 v10; // r9
  __int16 v11; // r10
  int v13; // [rsp+20h] [rbp-198h]
  _QWORD v14[3]; // [rsp+28h] [rbp-190h] BYREF
  _QWORD v15[4]; // [rsp+40h] [rbp-178h] BYREF
  _QWORD v16[2]; // [rsp+60h] [rbp-158h] BYREF
  _BYTE v17[112]; // [rsp+70h] [rbp-148h] BYREF
  unsigned int v18; // [rsp+E0h] [rbp-D8h]
  _BYTE v19[96]; // [rsp+F0h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+150h] [rbp-68h] BYREF
  __int128 v21; // [rsp+160h] [rbp-58h]
  __int128 v22; // [rsp+170h] [rbp-48h] BYREF
  __int128 v23; // [rsp+180h] [rbp-38h]
  int v24; // [rsp+190h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v20 = 0;
  v21 = 0;
  std::wstring::_Construct<2,unsigned short const *>(&v20);
  v14[0] = L"%Y-%m-%dT%H:%M:%SZ";
  v14[1] = L"%Y-%m-%dT%H:%M:%Sz";
  v14[2] = L"%Y-%m-%dT%H:%M:%S";
  v22 = 0;
  v23 = 0;
  v24 = 0;
  for ( i = v14; i != v15; ++i )
  {
    std::basic_istringstream<unsigned short>::basic_istringstream<unsigned short>(v16);
    std::ios_base::exceptions((std::ios_base *)((char *)v16 + *(int *)(v16[0] + 4LL)), 2);
    std::basic_stringbuf<unsigned short>::_Tidy(v17);
    v4 = &v20;
    if ( *((_QWORD *)&v21 + 1) > 7u )
      v4 = (__int128 *)v20;
    std::basic_stringbuf<unsigned short>::_Init(v17, v4, v21, v18);
    v5 = (_WORD *)*i;
    v15[0] = &v22;
    v15[1] = v5;
    while ( 1 )
    {
      v6 = *v5 == 0;
      v15[2] = v5;
      if ( v6 )
        break;
      ++v5;
    }
    std::operator>><unsigned short,std::char_traits<unsigned short>>(v16, v15);
    if ( !std::ios_base::fail((std::ios_base *)((char *)v16 + *(int *)(v16[0] + 4LL))) )
    {
      std::basic_istringstream<unsigned short>::~basic_istringstream<unsigned short>(v19);
      std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v19);
      v7 = v23 + 1;
      v8 = WORD6(v22);
      v9 = WORD4(v22);
      v10 = WORD2(v22);
      v11 = v22;
      *a2 = WORD2(v23) + 1900;
      a2[1] = v7;
      a2[2] = 0;
      a2[3] = v8;
      a2[4] = v9;
      a2[5] = v10;
      a2[6] = v11;
      a2[7] = 0;
      std::wstring::_Tidy_deallocate(&v20);
      return 0;
    }
    std::basic_istringstream<unsigned short>::~basic_istringstream<unsigned short>(v19);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v19);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xBD,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
    (const char *)0x80070057LL,
    v13);
  std::wstring::_Tidy_deallocate(&v20);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180020810  mov     r11, rsp
0x180020813  mov     [r11+18h], rbx
0x180020817  push    rsi
0x180020818  push    rdi
0x180020819  push    r14
0x18002081b  sub     rsp, 1A0h
0x180020822  mov     rax, cs:__security_cookie
0x180020829  xor     rax, rsp
0x18002082c  mov     [rsp+1B8h+var_20], rax
0x180020834  mov     rdi, rdx
0x180020837  xorps   xmm0, xmm0
0x18002083a  movups  xmmword ptr [r11-68h], xmm0
0x18002083f  xorps   xmm1, xmm1
0x180020842  movdqu  xmmword ptr [r11-58h], xmm1
0x180020848  mov     r8, [rcx+10h]
0x18002084c  cmp     qword ptr [rcx+18h], 7
0x180020851  jbe     short loc_180020856
0x180020853  mov     rcx, [rcx]
0x180020856  mov     rdx, rcx
0x180020859  lea     rcx, [rsp+1B8h+var_68]
0x180020861  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180020866  nop
0x180020867  lea     rax, aYMDtHMSz; "%Y-%m-%dT%H:%M:%SZ"
0x18002086e  mov     [rsp+1B8h+var_190], rax
0x180020873  lea     rax, aYMDtHMSz_0; "%Y-%m-%dT%H:%M:%Sz"
0x18002087a  mov     [rsp+1B8h+var_188], rax
0x18002087f  lea     rax, aYMDtHMS; "%Y-%m-%dT%H:%M:%S"
0x180020886  mov     [rsp+1B8h+var_180], rax
0x18002088b  xorps   xmm0, xmm0
0x18002088e  xor     eax, eax
0x180020890  movups  [rsp+1B8h+var_48], xmm0
0x180020898  movups  [rsp+1B8h+var_38], xmm0
0x1800208a0  mov     [rsp+1B8h+var_28], eax
0x1800208a7  lea     rbx, [rsp+1B8h+var_190]
0x1800208ac  lea     r14, [rsp+1B8h+var_178]
0x1800208b1  xor     esi, esi
0x1800208b3  cmp     rbx, r14
0x1800208b6  jz      loc_180020A1F
0x1800208bc  lea     rcx, [rsp+1B8h+var_158]
0x1800208c1  call    ??0?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_istringstream<ushort>::basic_istringstream<ushort>(void)
0x1800208c6  nop
0x1800208c7  mov     rax, [rsp+1B8h+var_158]
0x1800208cc  movsxd  rcx, dword ptr [rax+4]
0x1800208d0  lea     rax, [rsp+1B8h+var_158]
0x1800208d5  add     rcx, rax
0x1800208d8  mov     edx, 2
0x1800208dd  call    cs:__imp_?exceptions@ios_base@std@@QEAAXH@Z; std::ios_base::exceptions(int)
0x1800208e3  lea     rcx, [rsp+1B8h+var_148]
0x1800208e8  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x1800208ed  lea     rdx, [rsp+1B8h+var_68]
0x1800208f5  cmp     [rsp+1B8h+var_50], 7
0x1800208fe  cmova   rdx, qword ptr [rsp+1B8h+var_68]
0x180020907  mov     r9d, [rsp+1B8h+var_D8]
0x18002090f  mov     r8, [rsp+1B8h+var_58]
0x180020917  lea     rcx, [rsp+1B8h+var_148]
0x18002091c  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x180020921  mov     rax, [rbx]
0x180020924  lea     rcx, [rsp+1B8h+var_48]
0x18002092c  mov     [rsp+1B8h+var_178], rcx
0x180020931  mov     [rsp+1B8h+var_170], rax
0x180020936  jmp     short loc_18002093C
0x180020938  add     rax, 2
0x18002093c  cmp     [rax], si
0x18002093f  mov     [rsp+1B8h+var_168], rax
0x180020944  jnz     short loc_180020938
0x180020946  lea     rdx, [rsp+1B8h+var_178]
0x18002094b  lea     rcx, [rsp+1B8h+var_158]
0x180020950  call    ??$?5GU?$char_traits@G@std@@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEBU?$_Timeobj@GPEAUtm@@@0@@Z; std::operator>><ushort,std::char_traits<ushort>>(std::basic_istream<ushort> &,std::_Timeobj<ushort,tm *> const &)
0x180020955  mov     rax, [rsp+1B8h+var_158]
0x18002095a  movsxd  rcx, dword ptr [rax+4]
0x18002095e  lea     rax, [rsp+1B8h+var_158]
0x180020963  add     rcx, rax
0x180020966  call    cs:__imp_?fail@ios_base@std@@QEBA_NXZ; std::ios_base::fail(void)
0x18002096c  nop
0x18002096d  lea     rcx, [rsp+1B8h+var_C8]
0x180020975  test    al, al
0x180020977  jnz     loc_180020A03
0x18002097d  call    ??1?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_istringstream<ushort>::~basic_istringstream<ushort>(void)
0x180020982  lea     rcx, [rsp+1B8h+var_C8]
0x18002098a  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180020990  movzx   ecx, word ptr [rsp+1B8h+var_38]
0x180020998  inc     cx
0x18002099b  movzx   edx, word ptr [rsp+1B8h+var_48+0Ch]
0x1800209a3  movzx   r8d, word ptr [rsp+1B8h+var_48+8]
0x1800209ac  movzx   r9d, word ptr [rsp+1B8h+var_48+4]
0x1800209b5  movzx   r10d, word ptr [rsp+1B8h+var_48]
0x1800209be  mov     r11d, 76Ch
0x1800209c4  movzx   eax, word ptr [rsp+1B8h+var_38+4]
0x1800209cc  add     ax, r11w
0x1800209d0  mov     [rdi], ax
0x1800209d3  mov     [rdi+2], cx
0x1800209d7  mov     [rdi+4], si
0x1800209db  mov     [rdi+6], dx
0x1800209df  mov     [rdi+8], r8w
0x1800209e4  mov     [rdi+0Ah], r9w
0x1800209e9  mov     [rdi+0Ch], r10w
0x1800209ee  mov     [rdi+0Eh], si
0x1800209f2  lea     rcx, [rsp+1B8h+var_68]
0x1800209fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800209ff  xor     eax, eax
0x180020a01  jmp     short loc_180020A56
0x180020a03  call    ??1?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_istringstream<ushort>::~basic_istringstream<ushort>(void)
0x180020a08  lea     rcx, [rsp+1B8h+var_C8]
0x180020a10  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180020a16  add     rbx, 8
0x180020a1a  jmp     loc_1800208B3
0x180020a1f  mov     rcx, [rsp+1B8h]; this
0x180020a27  mov     ebx, 80070057h
0x180020a2c  mov     r9d, ebx; char *
0x180020a2f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180020a36  mov     edx, 0BDh; void *
0x180020a3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020a40  nop
0x180020a41  lea     rcx, [rsp+1B8h+var_68]
0x180020a49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020a4e  mov     eax, ebx
0x180020a50  jmp     short loc_180020A56
0x180020a52  mov     eax, [rsp+1B8h+var_198]
0x180020a56  mov     rcx, [rsp+1B8h+var_20]
0x180020a5e  xor     rcx, rsp; StackCookie
0x180020a61  call    __security_check_cookie
0x180020a66  mov     rbx, [rsp+1B8h+arg_10]
0x180020a6e  add     rsp, 1A0h
0x180020a75  pop     r14
0x180020a77  pop     rdi
0x180020a78  pop     rsi
0x180020a79  retn
```
