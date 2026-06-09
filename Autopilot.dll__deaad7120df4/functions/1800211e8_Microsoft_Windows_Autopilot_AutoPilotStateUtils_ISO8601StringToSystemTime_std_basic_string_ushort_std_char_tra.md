# Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_SYSTEMTIME &)

- ea: `0x1800211e8`
- end: `0x18002146b`
- name: `?ISO8601StringToSystemTime@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SYSTEMTIME@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(__int64 **, _WORD *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001c190`
- `0x18001cff4`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013f88`
- `0x180017a20`
- `0x180020140`
- `0x1800204c4`
- `0x1800205f0`
- `0x1800211e8`
- `0x180021a08`
- `0x180021b40`

## import_xrefs

- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x180021344`
- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x180021344`
- `msvcp_win!?exceptions@ios_base@std@@QEAAXH@Z` at `0x1800212b5`
- `msvcp_win!?exceptions@ios_base@std@@QEAAXH@Z` at `0x1800212b5`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002136e`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800213fa`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002136e`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800213fa`

## string_xrefs

- `0x18002141f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime(
        __int64 **a1,
        _WORD *a2)
{
  unsigned __int64 v3; // r8
  _QWORD *i; // rbx
  __int128 *v5; // rdx
  _WORD *v6; // rax
  bool v7; // zf
  __int16 v8; // cx
  __int16 v9; // dx
  __int16 v10; // r8
  __int16 v11; // r9
  __int16 v12; // r10
  int v14; // [rsp+20h] [rbp-198h]
  _QWORD v15[3]; // [rsp+28h] [rbp-190h] BYREF
  _QWORD v16[4]; // [rsp+40h] [rbp-178h] BYREF
  _QWORD v17[2]; // [rsp+60h] [rbp-158h] BYREF
  _BYTE v18[112]; // [rsp+70h] [rbp-148h] BYREF
  unsigned int v19; // [rsp+E0h] [rbp-D8h]
  _BYTE v20[96]; // [rsp+F0h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+150h] [rbp-68h] BYREF
  __int128 v22; // [rsp+160h] [rbp-58h]
  __int128 v23; // [rsp+170h] [rbp-48h] BYREF
  __int128 v24; // [rsp+180h] [rbp-38h]
  int v25; // [rsp+190h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v21 = 0;
  v22 = 0;
  v3 = (unsigned __int64)a1[2];
  if ( (unsigned __int64)a1[3] > 7 )
    a1 = (__int64 **)*a1;
  std::wstring::_Construct<2,unsigned short const *>((__int64)&v21, a1, v3);
  v15[0] = L"%Y-%m-%dT%H:%M:%SZ";
  v15[1] = L"%Y-%m-%dT%H:%M:%Sz";
  v15[2] = L"%Y-%m-%dT%H:%M:%S";
  v23 = 0;
  v24 = 0;
  v25 = 0;
  for ( i = v15; i != v16; ++i )
  {
    std::basic_istringstream<unsigned short>::basic_istringstream<unsigned short>(v17);
    std::ios_base::exceptions((std::ios_base *)((char *)v17 + *(int *)(v17[0] + 4LL)), 2);
    std::basic_stringbuf<unsigned short>::_Tidy(v18);
    v5 = &v21;
    if ( *((_QWORD *)&v22 + 1) > 7u )
      v5 = (__int128 *)v21;
    std::basic_stringbuf<unsigned short>::_Init(v18, v5, v22, v19);
    v6 = (_WORD *)*i;
    v16[0] = &v23;
    v16[1] = v6;
    while ( 1 )
    {
      v7 = *v6 == 0;
      v16[2] = v6;
      if ( v7 )
        break;
      ++v6;
    }
    std::operator>><unsigned short,std::char_traits<unsigned short>>(v17, v16);
    if ( !std::ios_base::fail((std::ios_base *)((char *)v17 + *(int *)(v17[0] + 4LL))) )
    {
      std::basic_istringstream<unsigned short>::~basic_istringstream<unsigned short>(v20);
      std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v20);
      v8 = v24 + 1;
      v9 = WORD6(v23);
      v10 = WORD4(v23);
      v11 = WORD2(v23);
      v12 = v23;
      *a2 = WORD2(v24) + 1900;
      a2[1] = v8;
      a2[2] = 0;
      a2[3] = v9;
      a2[4] = v10;
      a2[5] = v11;
      a2[6] = v12;
      a2[7] = 0;
      std::wstring::_Tidy_deallocate((char **)&v21);
      return 0;
    }
    std::basic_istringstream<unsigned short>::~basic_istringstream<unsigned short>(v20);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v20);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xBD,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
    (const char *)0x80070057LL,
    v14);
  std::wstring::_Tidy_deallocate((char **)&v21);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800211e8  mov     r11, rsp
0x1800211eb  mov     [r11+18h], rbx
0x1800211ef  push    rsi
0x1800211f0  push    rdi
0x1800211f1  push    r14
0x1800211f3  sub     rsp, 1A0h
0x1800211fa  mov     rax, cs:__security_cookie
0x180021201  xor     rax, rsp
0x180021204  mov     [rsp+1B8h+var_20], rax
0x18002120c  mov     rdi, rdx
0x18002120f  xorps   xmm0, xmm0
0x180021212  movups  xmmword ptr [r11-68h], xmm0
0x180021217  xorps   xmm1, xmm1
0x18002121a  movdqu  xmmword ptr [r11-58h], xmm1
0x180021220  mov     r8, [rcx+10h]
0x180021224  cmp     qword ptr [rcx+18h], 7
0x180021229  jbe     short loc_18002122E
0x18002122b  mov     rcx, [rcx]
0x18002122e  mov     rdx, rcx
0x180021231  lea     rcx, [rsp+1B8h+var_68]
0x180021239  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18002123e  nop
0x18002123f  lea     rax, aYMDtHMSz; "%Y-%m-%dT%H:%M:%SZ"
0x180021246  mov     [rsp+1B8h+var_190], rax
0x18002124b  lea     rax, aYMDtHMSz_0; "%Y-%m-%dT%H:%M:%Sz"
0x180021252  mov     [rsp+1B8h+var_188], rax
0x180021257  lea     rax, aYMDtHMS; "%Y-%m-%dT%H:%M:%S"
0x18002125e  mov     [rsp+1B8h+var_180], rax
0x180021263  xorps   xmm0, xmm0
0x180021266  xor     eax, eax
0x180021268  movups  [rsp+1B8h+var_48], xmm0
0x180021270  movups  [rsp+1B8h+var_38], xmm0
0x180021278  mov     [rsp+1B8h+var_28], eax
0x18002127f  lea     rbx, [rsp+1B8h+var_190]
0x180021284  lea     r14, [rsp+1B8h+var_178]
0x180021289  xor     esi, esi
0x18002128b  cmp     rbx, r14
0x18002128e  jz      loc_18002140F
0x180021294  lea     rcx, [rsp+1B8h+var_158]
0x180021299  call    ??0?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_istringstream<ushort>::basic_istringstream<ushort>(void)
0x18002129e  nop
0x18002129f  mov     rax, [rsp+1B8h+var_158]
0x1800212a4  movsxd  rcx, dword ptr [rax+4]
0x1800212a8  lea     rax, [rsp+1B8h+var_158]
0x1800212ad  add     rcx, rax
0x1800212b0  mov     edx, 2
0x1800212b5  call    cs:__imp_?exceptions@ios_base@std@@QEAAXH@Z; std::ios_base::exceptions(int)
0x1800212bc  nop     dword ptr [rax+rax+00h]
0x1800212c1  lea     rcx, [rsp+1B8h+var_148]
0x1800212c6  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x1800212cb  lea     rdx, [rsp+1B8h+var_68]
0x1800212d3  cmp     [rsp+1B8h+var_50], 7
0x1800212dc  cmova   rdx, qword ptr [rsp+1B8h+var_68]
0x1800212e5  mov     r9d, [rsp+1B8h+var_D8]
0x1800212ed  mov     r8, [rsp+1B8h+var_58]
0x1800212f5  lea     rcx, [rsp+1B8h+var_148]
0x1800212fa  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x1800212ff  mov     rax, [rbx]
0x180021302  lea     rcx, [rsp+1B8h+var_48]
0x18002130a  mov     [rsp+1B8h+var_178], rcx
0x18002130f  mov     [rsp+1B8h+var_170], rax
0x180021314  jmp     short loc_18002131A
0x180021316  add     rax, 2
0x18002131a  cmp     [rax], si
0x18002131d  mov     [rsp+1B8h+var_168], rax
0x180021322  jnz     short loc_180021316
0x180021324  lea     rdx, [rsp+1B8h+var_178]
0x180021329  lea     rcx, [rsp+1B8h+var_158]
0x18002132e  call    ??$?5GU?$char_traits@G@std@@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEBU?$_Timeobj@GPEAUtm@@@0@@Z; std::operator>><ushort,std::char_traits<ushort>>(std::basic_istream<ushort> &,std::_Timeobj<ushort,tm *> const &)
0x180021333  mov     rax, [rsp+1B8h+var_158]
0x180021338  movsxd  rcx, dword ptr [rax+4]
0x18002133c  lea     rax, [rsp+1B8h+var_158]
0x180021341  add     rcx, rax
0x180021344  call    cs:__imp_?fail@ios_base@std@@QEBA_NXZ; std::ios_base::fail(void)
0x18002134b  nop     dword ptr [rax+rax+00h]
0x180021350  nop
0x180021351  lea     rcx, [rsp+1B8h+var_C8]
0x180021359  test    al, al
0x18002135b  jnz     loc_1800213ED
0x180021361  call    ??1?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_istringstream<ushort>::~basic_istringstream<ushort>(void)
0x180021366  lea     rcx, [rsp+1B8h+var_C8]
0x18002136e  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180021375  nop     dword ptr [rax+rax+00h]
0x18002137a  movzx   ecx, word ptr [rsp+1B8h+var_38]
0x180021382  inc     cx
0x180021385  movzx   edx, word ptr [rsp+1B8h+var_48+0Ch]
0x18002138d  movzx   r8d, word ptr [rsp+1B8h+var_48+8]
0x180021396  movzx   r9d, word ptr [rsp+1B8h+var_48+4]
0x18002139f  movzx   r10d, word ptr [rsp+1B8h+var_48]
0x1800213a8  mov     r11d, 76Ch
0x1800213ae  movzx   eax, word ptr [rsp+1B8h+var_38+4]
0x1800213b6  add     ax, r11w
0x1800213ba  mov     [rdi], ax
0x1800213bd  mov     [rdi+2], cx
0x1800213c1  mov     [rdi+4], si
0x1800213c5  mov     [rdi+6], dx
0x1800213c9  mov     [rdi+8], r8w
0x1800213ce  mov     [rdi+0Ah], r9w
0x1800213d3  mov     [rdi+0Ch], r10w
0x1800213d8  mov     [rdi+0Eh], si
0x1800213dc  lea     rcx, [rsp+1B8h+var_68]
0x1800213e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800213e9  xor     eax, eax
0x1800213eb  jmp     short loc_180021446
0x1800213ed  call    ??1?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_istringstream<ushort>::~basic_istringstream<ushort>(void)
0x1800213f2  lea     rcx, [rsp+1B8h+var_C8]
0x1800213fa  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180021401  nop     dword ptr [rax+rax+00h]
0x180021406  add     rbx, 8
0x18002140a  jmp     loc_18002128B
0x18002140f  mov     rcx, [rsp+1B8h]; this
0x180021417  mov     ebx, 80070057h
0x18002141c  mov     r9d, ebx; char *
0x18002141f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180021426  mov     edx, 0BDh; void *
0x18002142b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021430  nop
0x180021431  lea     rcx, [rsp+1B8h+var_68]
0x180021439  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002143e  mov     eax, ebx
0x180021440  jmp     short loc_180021446
0x180021442  mov     eax, [rsp+1B8h+var_198]
0x180021446  mov     rcx, [rsp+1B8h+var_20]
0x18002144e  xor     rcx, rsp; StackCookie
0x180021451  call    __security_check_cookie
0x180021456  mov     rbx, [rsp+1B8h+arg_10]
0x18002145e  add     rsp, 1A0h
0x180021465  pop     r14
0x180021467  pop     rdi
0x180021468  pop     rsi
0x180021469  retn
```
