# RoutingTableFullDialog::CreateActionDialog(ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x1800410bc`
- end: `0x1800413c7`
- name: `?CreateActionDialog@RoutingTableFullDialog@@AEAAJPEBGAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030cb0`

## callees

- `0x1800049a0`
- `0x18000584c`
- `0x180005858`
- `0x18000d4ec`
- `0x180013014`
- `0x180035e6c`
- `0x1800410bc`
- `0x180041594`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004137a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004138b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004139c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004137a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004138b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004139c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall RoutingTableFullDialog::CreateActionDialog(void **a1, const wchar_t *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // r12
  const wchar_t *v10; // rcx
  size_t v11; // r8
  unsigned __int8 v12; // bl
  int appended; // esi
  __int64 v14; // r8
  void **v15; // rcx
  __int64 v16; // r8
  unsigned __int64 v17; // rdx
  char *v18; // r12
  __int64 v19; // rbx
  void *v20; // r9
  void **v21; // rcx
  unsigned __int64 v22; // rdx
  char *v23; // r12
  __int64 v24; // rbx
  __int64 v25; // r8
  void *v26; // r9
  void **v27; // rcx
  void *v28; // r15
  __int64 v30; // [rsp+20h] [rbp-A98h]
  LPVOID pv; // [rsp+28h] [rbp-A90h] BYREF
  void *v32; // [rsp+30h] [rbp-A88h] BYREF
  void *v33; // [rsp+38h] [rbp-A80h] BYREF
  _QWORD *v34; // [rsp+40h] [rbp-A78h]
  _BYTE v35[528]; // [rsp+50h] [rbp-A68h] BYREF
  unsigned __int16 Src[1032]; // [rsp+260h] [rbp-858h] BYREF

  v34 = a3;
  v33 = 0;
  v32 = 0;
  pv = 0;
  memset_0(Src, 0, 0x802u);
  memset_0(v35, 0, 0x208u);
  v6 = *a3;
  v30 = a3[1];
  v7 = -1;
  if ( *a3 == v30 )
  {
LABEL_13:
    v12 = 0;
  }
  else
  {
    while ( 1 )
    {
      v8 = -1;
      do
        ++v8;
      while ( a2[v8] );
      v9 = *(_QWORD *)(v6 + 16);
      if ( *(_QWORD *)(v6 + 24) <= 7u )
        v10 = (const wchar_t *)v6;
      else
        v10 = *(const wchar_t **)v6;
      v11 = *(_QWORD *)(v6 + 16);
      if ( v8 < v9 )
        v11 = v8;
      if ( wmemcmp(v10, a2, v11) || v9 < v8 || v9 > v8 )
        break;
      v6 += 32;
      if ( v6 == v30 )
        goto LABEL_13;
    }
    v12 = 1;
  }
  appended = (*((__int64 (__fastcall **)(void **, __int64, void **))*a1 + 5))(a1, 119, &v33);
  if ( appended >= 0 )
  {
    appended = (*((__int64 (__fastcall **)(void **, __int64, void **))*a1 + 5))(a1, 116, &v32);
    if ( appended >= 0 )
    {
      appended = (*((__int64 (__fastcall **)(void **, _QWORD, LPVOID *))*a1 + 5))(a1, (unsigned int)v12 + 117, &pv);
      if ( appended >= 0 )
      {
        appended = (*((__int64 (__fastcall **)(void **, const wchar_t *, _BYTE *))*a1 + 6))(a1, a2, v35);
        if ( appended >= 0 )
        {
          appended = StringCchPrintfW(Src, 0x401u, (const unsigned __int16 *)pv, v35);
          if ( appended >= 0 )
          {
            v15 = a1 + 5;
            if ( v12 )
            {
              appended = RoutingDialog::AppendConflictingAppTitles(a1, Src, v34, a1 + 5);
              if ( appended < 0 )
                goto LABEL_46;
            }
            else
            {
              v17 = -1;
              do
                ++v17;
              while ( Src[v17] );
              if ( v17 > (unsigned __int64)a1[8] )
              {
                ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
                  v15,
                  v17,
                  v14,
                  Src);
              }
              else
              {
                if ( (unsigned __int64)a1[8] <= 7 )
                  v18 = (char *)(a1 + 5);
                else
                  v18 = (char *)*v15;
                a1[7] = (void *)v17;
                v19 = 2 * v17;
                memmove_0(v18, Src, 2 * v17);
                *(_WORD *)&v18[v19] = 0;
              }
            }
            v20 = v32;
            v21 = a1 + 1;
            v22 = -1;
            do
              ++v22;
            while ( *((_WORD *)v32 + v22) );
            if ( v22 > (unsigned __int64)a1[4] )
            {
              ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
                v21,
                v22,
                v16,
                v32);
            }
            else
            {
              if ( (unsigned __int64)a1[4] <= 7 )
                v23 = (char *)(a1 + 1);
              else
                v23 = (char *)*v21;
              a1[3] = (void *)v22;
              v24 = 2 * v22;
              memmove_0(v23, v20, 2 * v22);
              *(_WORD *)&v23[v24] = 0;
            }
            v26 = v33;
            v27 = a1 + 9;
            do
              ++v7;
            while ( *((_WORD *)v33 + v7) );
            if ( v7 > (unsigned __int64)a1[12] )
            {
              ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
                v27,
                v7,
                v25,
                v33);
            }
            else
            {
              if ( (unsigned __int64)a1[12] <= 7 )
                v28 = a1 + 9;
              else
                v28 = *v27;
              v27[2] = (void *)v7;
              memmove_0(v28, v26, 2 * v7);
              *((_WORD *)v28 + v7) = 0;
            }
          }
        }
      }
    }
  }
LABEL_46:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v32 )
    CoTaskMemFree(v32);
  if ( v33 )
    CoTaskMemFree(v33);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800410bc  push    rbx
0x1800410be  push    rsi
0x1800410bf  push    rdi
0x1800410c0  push    r12
0x1800410c2  push    r13
0x1800410c4  push    r14
0x1800410c6  push    r15
0x1800410c8  sub     rsp, 0A80h
0x1800410cf  mov     rax, cs:__security_cookie
0x1800410d6  xor     rax, rsp
0x1800410d9  mov     [rsp+0AB8h+var_48], rax
0x1800410e1  mov     rsi, r8
0x1800410e4  mov     [rsp+0AB8h+var_A78], r8
0x1800410e9  mov     r13, rdx
0x1800410ec  mov     r15, rcx
0x1800410ef  xor     edi, edi
0x1800410f1  mov     [rsp+0AB8h+var_A80], rdi
0x1800410f6  mov     [rsp+0AB8h+var_A88], rdi
0x1800410fb  mov     [rsp+0AB8h+pv], rdi
0x180041100  xor     edx, edx; Val
0x180041102  mov     r8d, 802h; Size
0x180041108  lea     rcx, [rsp+0AB8h+Src]; void *
0x180041110  call    memset_0
0x180041115  xor     edx, edx; Val
0x180041117  mov     r8d, 208h; Size
0x18004111d  lea     rcx, [rsp+0AB8h+var_A68]; void *
0x180041122  call    memset_0
0x180041127  mov     rbx, [rsi]
0x18004112a  mov     rax, [rsi+8]
0x18004112e  mov     [rsp+0AB8h+var_A98], rax
0x180041133  or      r14, 0FFFFFFFFFFFFFFFFh
0x180041137  cmp     rbx, rax
0x18004113a  jz      short loc_180041191
0x18004113c  mov     rsi, r14
0x18004113f  inc     rsi
0x180041142  cmp     [r13+rsi*2+0], di
0x180041148  jnz     short loc_18004113F
0x18004114a  mov     r12, [rbx+10h]
0x18004114e  cmp     qword ptr [rbx+18h], 7
0x180041153  jbe     short loc_18004115A
0x180041155  mov     rcx, [rbx]
0x180041158  jmp     short loc_18004115D
0x18004115a  mov     rcx, rbx; S1
0x18004115d  mov     r8, r12
0x180041160  cmp     rsi, r12
0x180041163  cmovb   r8, rsi; N
0x180041167  mov     rdx, r13; S2
0x18004116a  call    wmemcmp
0x18004116f  test    eax, eax
0x180041171  jnz     loc_180041296
0x180041177  cmp     r12, rsi
0x18004117a  jb      loc_180041296
0x180041180  ja      loc_180041296
0x180041186  add     rbx, 20h ; ' '
0x18004118a  cmp     rbx, [rsp+0AB8h+var_A98]
0x18004118f  jnz     short loc_18004113C
0x180041191  mov     bl, dil
0x180041194  mov     rax, [r15]
0x180041197  lea     r8, [rsp+0AB8h+var_A80]
0x18004119c  mov     edx, 77h ; 'w'
0x1800411a1  mov     rcx, r15
0x1800411a4  mov     rax, [rax+28h]
0x1800411a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411ad  mov     esi, eax
0x1800411af  test    eax, eax
0x1800411b1  js      loc_180041370
0x1800411b7  mov     rax, [r15]
0x1800411ba  lea     r8, [rsp+0AB8h+var_A88]
0x1800411bf  mov     edx, 74h ; 't'
0x1800411c4  mov     rcx, r15
0x1800411c7  mov     rax, [rax+28h]
0x1800411cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411d0  mov     esi, eax
0x1800411d2  test    eax, eax
0x1800411d4  js      loc_180041370
0x1800411da  mov     rax, [r15]
0x1800411dd  movzx   edx, bl
0x1800411e0  add     edx, 75h ; 'u'
0x1800411e3  lea     r8, [rsp+0AB8h+pv]
0x1800411e8  mov     rcx, r15
0x1800411eb  mov     rax, [rax+28h]
0x1800411ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411f4  mov     esi, eax
0x1800411f6  test    eax, eax
0x1800411f8  js      loc_180041370
0x1800411fe  mov     rax, [r15]
0x180041201  lea     r8, [rsp+0AB8h+var_A68]
0x180041206  mov     rdx, r13
0x180041209  mov     rcx, r15
0x18004120c  mov     rax, [rax+30h]
0x180041210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041215  mov     esi, eax
0x180041217  test    eax, eax
0x180041219  js      loc_180041370
0x18004121f  lea     r9, [rsp+0AB8h+var_A68]
0x180041224  mov     r8, [rsp+0AB8h+pv]; unsigned __int16 *
0x180041229  mov     edx, 401h; unsigned __int64
0x18004122e  lea     rcx, [rsp+0AB8h+Src]; unsigned __int16 *
0x180041236  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004123b  mov     esi, eax
0x18004123d  test    eax, eax
0x18004123f  js      loc_180041370
0x180041245  lea     rcx, [r15+28h]
0x180041249  test    bl, bl
0x18004124b  jz      short loc_180041270
0x18004124d  mov     r9, rcx
0x180041250  mov     r8, [rsp+0AB8h+var_A78]
0x180041255  lea     rdx, [rsp+0AB8h+Src]
0x18004125d  mov     rcx, r15
0x180041260  call    ?AppendConflictingAppTitles@RoutingDialog@@QEAAJPEBGAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; RoutingDialog::AppendConflictingAppTitles(ushort const *,std::vector<std::wstring> const &,std::wstring *)
0x180041265  mov     esi, eax
0x180041267  test    eax, eax
0x180041269  jns     short loc_1800412CF
0x18004126b  jmp     loc_180041370
0x180041270  lea     rax, [rsp+0AB8h+Src]
0x180041278  mov     rdx, r14
0x18004127b  inc     rdx
0x18004127e  cmp     [rax+rdx*2], di
0x180041282  jnz     short loc_18004127B
0x180041284  cmp     rdx, [rcx+18h]
0x180041288  ja      short loc_1800412C2
0x18004128a  cmp     qword ptr [rcx+18h], 7
0x18004128f  jbe     short loc_18004129D
0x180041291  mov     r12, [rcx]
0x180041294  jmp     short loc_1800412A0
0x180041296  mov     bl, 1
0x180041298  jmp     loc_180041194
0x18004129d  mov     r12, rcx
0x1800412a0  mov     [rcx+10h], rdx
0x1800412a4  lea     rbx, [rdx+rdx]
0x1800412a8  mov     r8, rbx; Size
0x1800412ab  lea     rdx, [rsp+0AB8h+Src]; Src
0x1800412b3  mov     rcx, r12; void *
0x1800412b6  call    memmove_0
0x1800412bb  mov     [rbx+r12], di
0x1800412c0  jmp     short loc_1800412CF
0x1800412c2  lea     r9, [rsp+0AB8h+Src]
0x1800412ca  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x1800412cf  mov     r9, [rsp+0AB8h+var_A88]
0x1800412d4  lea     rcx, [r15+8]
0x1800412d8  mov     rdx, r14
0x1800412db  inc     rdx
0x1800412de  cmp     [r9+rdx*2], di
0x1800412e3  jnz     short loc_1800412DB
0x1800412e5  cmp     rdx, [rcx+18h]
0x1800412e9  ja      short loc_180041317
0x1800412eb  cmp     qword ptr [rcx+18h], 7
0x1800412f0  jbe     short loc_1800412F7
0x1800412f2  mov     r12, [rcx]
0x1800412f5  jmp     short loc_1800412FA
0x1800412f7  mov     r12, rcx
0x1800412fa  mov     [rcx+10h], rdx
0x1800412fe  lea     rbx, [rdx+rdx]
0x180041302  mov     r8, rbx; Size
0x180041305  mov     rdx, r9; Src
0x180041308  mov     rcx, r12; void *
0x18004130b  call    memmove_0
0x180041310  mov     [rbx+r12], di
0x180041315  jmp     short loc_18004131C
0x180041317  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18004131c  mov     r9, [rsp+0AB8h+var_A80]
0x180041321  lea     rcx, [r15+48h]
0x180041325  inc     r14
0x180041328  cmp     [r9+r14*2], di
0x18004132d  jnz     short loc_180041325
0x18004132f  cmp     r14, [rcx+18h]
0x180041333  ja      short loc_180041361
0x180041335  cmp     qword ptr [rcx+18h], 7
0x18004133a  jbe     short loc_180041341
0x18004133c  mov     r15, [rcx]
0x18004133f  jmp     short loc_180041344
0x180041341  mov     r15, rcx
0x180041344  mov     [rcx+10h], r14
0x180041348  lea     rbx, [r14+r14]
0x18004134c  mov     r8, rbx; Size
0x18004134f  mov     rdx, r9; Src
0x180041352  mov     rcx, r15; void *
0x180041355  call    memmove_0
0x18004135a  mov     [rbx+r15], di
0x18004135f  jmp     short loc_18004136A
0x180041361  mov     rdx, r14
0x180041364  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180041369  nop
0x18004136a  jmp     short loc_180041370
0x18004136c  mov     esi, dword ptr [rsp+0AB8h+var_A98]
0x180041370  mov     rcx, [rsp+0AB8h+pv]; pv
0x180041375  test    rcx, rcx
0x180041378  jz      short loc_180041381
0x18004137a  call    cs:__imp_CoTaskMemFree
0x180041380  nop
0x180041381  mov     rcx, [rsp+0AB8h+var_A88]; pv
0x180041386  test    rcx, rcx
0x180041389  jz      short loc_180041392
0x18004138b  call    cs:__imp_CoTaskMemFree
0x180041391  nop
0x180041392  mov     rcx, [rsp+0AB8h+var_A80]; pv
0x180041397  test    rcx, rcx
0x18004139a  jz      short loc_1800413A2
0x18004139c  call    cs:__imp_CoTaskMemFree
0x1800413a2  mov     eax, esi
0x1800413a4  mov     rcx, [rsp+0AB8h+var_48]
0x1800413ac  xor     rcx, rsp; StackCookie
0x1800413af  call    __security_check_cookie
0x1800413b4  add     rsp, 0A80h
0x1800413bb  pop     r15
0x1800413bd  pop     r14
0x1800413bf  pop     r13
0x1800413c1  pop     r12
0x1800413c3  pop     rdi
0x1800413c4  pop     rsi
0x1800413c5  pop     rbx
0x1800413c6  retn
```
