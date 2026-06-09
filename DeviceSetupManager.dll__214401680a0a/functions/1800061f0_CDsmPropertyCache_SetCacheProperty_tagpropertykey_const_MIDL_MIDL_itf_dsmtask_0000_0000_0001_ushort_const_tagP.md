# CDsmPropertyCache::SetCacheProperty(_tagpropertykey const &,__MIDL___MIDL_itf_dsmtask_0000_0000_0001,ushort const *,tagPROPVARIANT const *)

- ea: `0x1800061f0`
- end: `0x18000673b`
- name: `?SetCacheProperty@CDsmPropertyCache@@QEAAJAEBU_tagpropertykey@@W4__MIDL___MIDL_itf_dsmtask_0000_0000_0001@@PEBGPEBUtagPROPVARIANT@@@Z`
- size: `1355`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, __int128 *, __int64, unsigned __int16 *, PROPVARIANT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800061e0`

## callees

- `0x1800061f0`
- `0x180006744`
- `0x180006a80`
- `0x180007800`
- `0x180016c18`
- `0x180018d3c`
- `0x18001af70`
- `0x18001be40`
- `0x180031850`
- `0x18003197c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800063e2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800063e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006470`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006470`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006259`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006259`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000634e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800064db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000634e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800064db`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000635a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800064e7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000635a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800064e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800065d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800065d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800064a1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800064a1`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x1800065c5`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x1800065c5`

## pseudocode

```c
__int64 __fastcall CDsmPropertyCache::SetCacheProperty(
        RTL_SRWLOCK *a1,
        __int128 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        PROPVARIANT *a5)
{
  unsigned int v6; // edi
  LPCWSTR *v9; // r15
  _QWORD *v10; // rdi
  __int64 v11; // rax
  _QWORD *i; // rax
  _QWORD *v13; // rbx
  LPCWSTR v14; // rax
  int v15; // ecx
  _DWORD *v16; // r12
  __int64 v17; // rbx
  __int64 v18; // rax
  PROPVARIANT *v19; // rdi
  PROPVARIANT *v20; // rax
  unsigned int v21; // edx
  PROPVARIANT *v22; // rbx
  HRESULT v23; // eax
  int v24; // edi
  LPCWSTR v25; // rsi
  unsigned __int64 v26; // rcx
  __int64 v27; // rcx
  WCHAR *v28; // rax
  int v29; // r8d
  WCHAR *j; // rcx
  const WCHAR **v31; // rcx
  const WCHAR *v32; // rax
  WCHAR *v33; // rax
  bool v35; // zf
  HRESULT v36; // eax
  PVOID v37; // rcx
  int v38; // ebx
  RTL_SRWLOCK *Ptr; // rdx
  __int64 v40; // rcx
  unsigned int v41; // edx
  int v42; // [rsp+30h] [rbp-D8h]
  LPCWSTR *v43; // [rsp+38h] [rbp-D0h]
  PROPVARIANT *pvarSrc; // [rsp+40h] [rbp-C8h]
  PROPVARIANT *v45; // [rsp+48h] [rbp-C0h]
  LPCWSTR *v46; // [rsp+50h] [rbp-B8h]
  unsigned __int16 *v47; // [rsp+58h] [rbp-B0h]
  RTL_SRWLOCK *v48; // [rsp+60h] [rbp-A8h]
  PROPVARIANT *v49; // [rsp+68h] [rbp-A0h]
  __int128 *v50; // [rsp+70h] [rbp-98h]
  PSRWLOCK SRWLock; // [rsp+78h] [rbp-90h]
  ATL::CAtlException *v52; // [rsp+88h] [rbp-80h] BYREF
  __int128 v53; // [rsp+90h] [rbp-78h] BYREF
  __int128 v54; // [rsp+A0h] [rbp-68h]
  LPVOID pv[2]; // [rsp+B0h] [rbp-58h]
  int v56; // [rsp+120h] [rbp+18h]

  v56 = a3;
  v47 = a4;
  v6 = a3;
  v48 = a1;
  v50 = a2;
  pvarSrc = a5;
  v49 = a5;
  if ( (a3 & 4) != 0 )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, a3, a2, *((_DWORD *)a2 + 4));
    v53 = 0;
    v54 = 0;
    *(_OWORD *)pv = 0;
    v38 = CDsmPropertyCache::_PropVariantToDevProp((__int64)v37, (unsigned __int16 *)a5, v6, (__int64)&v53);
    if ( v38 >= 0 )
    {
      v53 = *a2;
      *(_QWORD *)&v54 = *((unsigned int *)a2 + 4);
      *((_QWORD *)&v54 + 1) = a4;
      Ptr = (RTL_SRWLOCK *)a1[26].Ptr;
      if ( Ptr )
      {
        v40 = 3;
      }
      else
      {
        Ptr = a1 + 16;
        v40 = 2;
      }
      v38 = DevSetObjectProperties(v40, Ptr, 1, &v53);
      CoTaskMemFree(pv[1]);
    }
    return (unsigned int)v38;
  }
  SRWLock = a1 + 1;
  AcquireSRWLockExclusive(a1 + 1);
  v42 = 0;
  v9 = 0;
  v10 = 0;
  if ( a1[26].Ptr )
    v11 = 8;
  else
    v11 = 2;
  for ( i = a1[v11].Ptr; ; i = v13 )
  {
    if ( !i )
    {
      v15 = v42;
      goto LABEL_10;
    }
    v13 = (_QWORD *)*i;
    v9 = (LPCWSTR *)i[2];
    v14 = *v9;
    if ( a4 )
    {
      if ( !v14 )
        continue;
      v35 = lstrcmpiW(a4, *v9) == 0;
    }
    else
    {
      v35 = v14 == 0;
    }
    if ( v35 )
      break;
  }
  v15 = 1;
  v10 = v9[1];
LABEL_10:
  v16 = a2 + 1;
  v45 = (PROPVARIANT *)(a2 + 1);
  while ( v10 )
  {
    v17 = v10[2];
    v18 = *(_QWORD *)a2 - *(_QWORD *)(v17 + 24);
    if ( *(_QWORD *)a2 == *(_QWORD *)(v17 + 24) )
      v18 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v17 + 32);
    if ( !v18 && *v16 == *(_DWORD *)(v17 + 40) )
    {
      *(_DWORD *)(v17 + 44) = 1;
      *(_DWORD *)(v17 + 48) = v56;
      if ( (PROPVARIANT *)v17 != pvarSrc )
      {
        PropVariantClear((PROPVARIANT *)v17);
        v36 = PropVariantCopy((PROPVARIANT *)v17, pvarSrc);
        if ( v36 < 0 )
        {
          *(_WORD *)v17 = 10;
          *(_DWORD *)(v17 + 8) = v36;
        }
      }
      if ( *(_WORD *)v17 == 10 )
        v24 = *(_DWORD *)(v17 + 8);
      else
        v24 = 0;
      goto LABEL_36;
    }
    v10 = (_QWORD *)*v10;
  }
  if ( !v15 )
  {
    v9 = (LPCWSTR *)operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
    v46 = v9;
    if ( v9 )
    {
      *(_OWORD *)v9 = 0;
      *((_OWORD *)v9 + 1) = 0;
      *((_OWORD *)v9 + 2) = 0;
      v9[6] = 0;
      *v9 = 0;
      v9[1] = 0;
      v9[2] = 0;
      v9[3] = 0;
      v9[4] = 0;
      v9[5] = 0;
      *((_DWORD *)v9 + 12) = 10;
      v46 = v9;
      v43 = v9;
      v24 = CCoMemString::Assign((CCoMemString *)v9, v47);
      if ( v24 < 0 )
      {
        ((void (__fastcall *)(CDsmPropertyCache::CPropertySet *, unsigned int))CDsmPropertyCache::CPropertySet::`scalar deleting destructor')(
          (CDsmPropertyCache::CPropertySet *)v9,
          v41);
        goto LABEL_36;
      }
      if ( v48[26].Ptr )
        ATL::CAtlList<CDsmPropertyCache::CPropertySet *,ATL::CElementTraits<CDsmPropertyCache::CPropertySet *>>::AddTail(&v48[8]);
      else
        ATL::CAtlList<CDsmPropertyCache::CPropertySet *,ATL::CElementTraits<CDsmPropertyCache::CPropertySet *>>::AddTail(&v48[2]);
      goto LABEL_18;
    }
LABEL_51:
    v24 = -2147024882;
    goto LABEL_36;
  }
LABEL_18:
  v19 = pvarSrc;
  v20 = (PROPVARIANT *)operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
  v22 = v20;
  if ( !v20 )
    goto LABEL_51;
  v45 = v20;
  v20[3] = 0;
  v20[4] = 0;
  v20[5] = 0;
  v20[6] = 0;
  *(_OWORD *)v20 = 0;
  v20[2] = 0;
  if ( v20 != v19 )
  {
    PropVariantClear(v20);
    v23 = PropVariantCopy(v22, v19);
    if ( v23 < 0 )
    {
      *(_WORD *)v22 = 10;
      *((_DWORD *)v22 + 2) = v23;
    }
  }
  if ( *(_WORD *)v22 == 10 )
  {
    v24 = *((_DWORD *)v22 + 2);
    if ( v24 < 0 )
    {
      ((void (__fastcall *)(CDsmPropertyCache::CPropertyElement *, unsigned int))CDsmPropertyCache::CPropertyElement::`scalar deleting destructor')(
        (CDsmPropertyCache::CPropertyElement *)v22,
        v21);
      goto LABEL_36;
    }
  }
  else
  {
    v24 = 0;
  }
  *(_OWORD *)(v22 + 3) = *a2;
  *((_DWORD *)v22 + 10) = *v16;
  *((_DWORD *)v22 + 12) = v56;
  *((_DWORD *)v22 + 11) = 1;
  v25 = v9[2];
  if ( !v9[5] )
  {
    v26 = *((unsigned int *)v9 + 12);
    if ( !*((_DWORD *)v9 + 12) )
    {
      v27 = 0;
      goto LABEL_30;
    }
    if ( 0xFFFFFFFFFFFFFFFFuLL / v26 < 0x18 )
      goto LABEL_68;
    while ( 1 )
    {
      v27 = 24 * v26;
LABEL_30:
      v28 = (WCHAR *)malloc(v27 + 8);
      if ( v28 )
        break;
LABEL_68:
      if ( __eh34_try(-1, 2) )
      {
        __eh34_scope_strut(2);
        ATL::AtlThrowImpl(-2147024882);
      }
      if ( __eh34_catch(2) )
      {
        if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', &v52) )
        {
          v42 = *(_DWORD *)v52;
          v24 = v42;
          __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000672D);
          goto LABEL_36;
        }
      }
    }
    *(_QWORD *)v28 = v9[4];
    v9[4] = v28;
    v29 = *((_DWORD *)v9 + 12) - 1;
    for ( j = &v28[8 * v29 + 4 + 4 * v29]; v29 >= 0; --v29 )
    {
      *(_QWORD *)j = v9[5];
      v9[5] = j;
      j -= 12;
    }
  }
  v31 = (const WCHAR **)v9[5];
  v32 = *v31;
  v31[2] = (const WCHAR *)v22;
  v9[5] = v32;
  v31[1] = v25;
  *v31 = 0;
  v9[3] = (LPCWSTR)((char *)v9[3] + 1);
  v33 = (WCHAR *)v9[2];
  if ( v33 )
    *(_QWORD *)v33 = v31;
  else
    v9[1] = (LPCWSTR)v31;
  v9[2] = (LPCWSTR)v31;
LABEL_36:
  ReleaseSRWLockExclusive(SRWLock);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1800061f0  mov     [rsp+arg_10], r8d
0x1800061f5  push    rbx
0x1800061f6  push    rsi
0x1800061f7  push    rdi
0x1800061f8  push    r12
0x1800061fa  push    r13
0x1800061fc  push    r14
0x1800061fe  push    r15
0x180006200  sub     rsp, 0D0h
0x180006207  mov     rax, cs:__security_cookie
0x18000620e  xor     rax, rsp
0x180006211  mov     [rsp+108h+var_48], rax
0x180006219  mov     r12, r9
0x18000621c  mov     [rsp+108h+var_B0], r9
0x180006221  mov     edi, r8d
0x180006224  mov     rsi, rdx
0x180006227  mov     r14, rcx
0x18000622a  mov     [rsp+108h+var_A8], rcx
0x18000622f  mov     [rsp+108h+var_98], rdx
0x180006234  mov     rbx, [rsp+108h+arg_20]
0x18000623c  mov     [rsp+108h+pvarSrc], rbx
0x180006241  mov     [rsp+108h+var_A0], rbx
0x180006246  test    r8b, 4
0x18000624a  jnz     loc_18000650C
0x180006250  add     rcx, 8; SRWLock
0x180006254  mov     [rsp+108h+SRWLock], rcx
0x180006259  call    cs:__imp_AcquireSRWLockExclusive
0x18000625f  xor     r13d, r13d
0x180006262  mov     [rsp+108h+var_D8], r13d
0x180006267  mov     r15d, r13d
0x18000626a  mov     edi, r13d
0x18000626d  cmp     [r14+0D0h], r13
0x180006274  jnz     loc_1800065F6
0x18000627a  mov     eax, 10h
0x18000627f  mov     rax, [r14+rax]
0x180006283  test    rax, rax
0x180006286  jz      short loc_1800062B7
0x180006288  mov     rbx, [rax]
0x18000628b  cmp     qword ptr [r14+0D0h], 0
0x180006293  jnz     loc_180006600
0x180006299  mov     r15, [rax+10h]
0x18000629d  mov     rax, [r15]
0x1800062a0  test    r12, r12
0x1800062a3  jz      loc_180006507
0x1800062a9  test    rax, rax
0x1800062ac  jnz     loc_18000649B
0x1800062b2  mov     rax, rbx
0x1800062b5  jmp     short loc_180006283
0x1800062b7  mov     ecx, [rsp+108h+var_D8]
0x1800062bb  lea     r12, [rsi+10h]
0x1800062bf  mov     [rsp+108h+var_C0], r12
0x1800062c4  test    rdi, rdi
0x1800062c7  jz      short loc_1800062F5
0x1800062c9  mov     rbx, [rdi+10h]
0x1800062cd  mov     rax, [rsi]
0x1800062d0  sub     rax, [rbx+18h]
0x1800062d4  jnz     short loc_1800062DE
0x1800062d6  mov     rax, [rsi+8]
0x1800062da  sub     rax, [rbx+20h]
0x1800062de  test    rax, rax
0x1800062e1  jnz     short loc_1800062F0
0x1800062e3  mov     eax, [rbx+28h]
0x1800062e6  cmp     [r12], eax
0x1800062ea  jz      loc_1800064BD
0x1800062f0  mov     rdi, [rdi]
0x1800062f3  jmp     short loc_1800062C4
0x1800062f5  test    ecx, ecx
0x1800062f7  jz      loc_180006637
0x1800062fd  mov     r14d, 0Ah
0x180006303  mov     rdi, [rsp+108h+pvarSrc]
0x180006308  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000630f  mov     ecx, 38h ; '8'; unsigned __int64
0x180006314  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006319  mov     rbx, rax
0x18000631c  test    rax, rax
0x18000631f  jz      loc_180006564
0x180006325  mov     [rsp+108h+var_C0], rax
0x18000632a  mov     [rax+18h], r13
0x18000632e  mov     [rax+20h], r13
0x180006332  mov     [rax+28h], r13
0x180006336  mov     [rax+30h], r13
0x18000633a  xorps   xmm0, xmm0
0x18000633d  xor     eax, eax
0x18000633f  movups  xmmword ptr [rbx], xmm0
0x180006342  mov     [rbx+10h], rax
0x180006346  cmp     rbx, rdi
0x180006349  jz      short loc_180006368
0x18000634b  mov     rcx, rbx; pvar
0x18000634e  call    cs:__imp_PropVariantClear
0x180006354  mov     rdx, rdi; pvarSrc
0x180006357  mov     rcx, rbx; pvarDest
0x18000635a  call    cs:__imp_PropVariantCopy
0x180006360  test    eax, eax
0x180006362  js      loc_180006721
0x180006368  cmp     word ptr [rbx], 0Ah
0x18000636c  jnz     short loc_180006382
0x18000636e  mov     edi, [rbx+8]
0x180006371  test    edi, edi
0x180006373  jns     short loc_180006385
0x180006375  mov     rcx, rbx; this
0x180006378  call    ??_GCPropertyElement@CDsmPropertyCache@@QEAAPEAXI@Z; CDsmPropertyCache::CPropertyElement::`scalar deleting destructor'(uint)
0x18000637d  jmp     loc_18000646B
0x180006382  mov     edi, r13d
0x180006385  movups  xmm0, xmmword ptr [rsi]
0x180006388  movups  xmmword ptr [rbx+18h], xmm0
0x18000638c  mov     eax, [r12]
0x180006390  mov     [rbx+28h], eax
0x180006393  mov     eax, [rsp+108h+arg_10]
0x18000639a  mov     [rbx+30h], eax
0x18000639d  mov     dword ptr [rbx+2Ch], 1
0x1800063a4  mov     rsi, [r15+10h]
0x1800063a8  cmp     qword ptr [r15+28h], 0
0x1800063ad  jnz     loc_180006435
0x1800063b3  mov     ecx, [r15+30h]
0x1800063b7  test    rcx, rcx
0x1800063ba  jz      loc_1800065E7
0x1800063c0  xor     edx, edx
0x1800063c2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800063c9  div     rcx
0x1800063cc  cmp     rax, 18h
0x1800063d0  jb      loc_1800065DD
0x1800063d6  lea     rcx, [rcx+rcx*2]
0x1800063da  shl     rcx, 3
0x1800063de  add     rcx, 8; Size
0x1800063e2  call    cs:__imp_malloc
0x1800063e8  test    rax, rax
0x1800063eb  jz      loc_1800065DD
0x1800063f1  mov     rcx, [r15+20h]
0x1800063f5  mov     [rax], rcx
0x1800063f8  mov     [r15+20h], rax
0x1800063fc  mov     r8d, [r15+30h]
0x180006400  sub     r8d, 1
0x180006404  lea     rcx, ds:1[r8*2]
0x18000640c  lea     rcx, [rcx+r8]
0x180006410  lea     rcx, [rax+rcx*8]
0x180006414  js      short loc_180006435
0x180006416  nop     word ptr [rax+rax+00000000h]
0x180006420  mov     rax, [r15+28h]
0x180006424  mov     [rcx], rax
0x180006427  mov     [r15+28h], rcx
0x18000642b  sub     rcx, 18h
0x18000642f  sub     r8d, 1
0x180006433  jns     short loc_180006420
0x180006435  mov     rcx, [r15+28h]
0x180006439  mov     rax, [rcx]
0x18000643c  mov     [rcx+10h], rbx
0x180006440  mov     [r15+28h], rax
0x180006444  mov     [rcx+8], rsi
0x180006448  mov     [rcx], r13
0x18000644b  inc     qword ptr [r15+18h]
0x18000644f  mov     rax, [r15+10h]
0x180006453  test    rax, rax
0x180006456  jz      loc_18000656E
0x18000645c  mov     [rax], rcx
0x18000645f  mov     [r15+10h], rcx
0x180006463  test    edi, edi
0x180006465  js      loc_180006375
0x18000646b  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x180006470  call    cs:__imp_ReleaseSRWLockExclusive
0x180006476  mov     eax, edi
0x180006478  mov     rcx, [rsp+108h+var_48]
0x180006480  xor     rcx, rsp; StackCookie
0x180006483  call    __security_check_cookie
0x180006488  add     rsp, 0D0h
0x18000648f  pop     r15
0x180006491  pop     r14
0x180006493  pop     r13
0x180006495  pop     r12
0x180006497  pop     rdi
0x180006498  pop     rsi
0x180006499  pop     rbx
0x18000649a  retn
0x18000649b  mov     rdx, rax; lpString2
0x18000649e  mov     rcx, r12; lpString1
0x1800064a1  call    cs:__imp_lstrcmpiW
0x1800064a7  test    eax, eax
0x1800064a9  jnz     loc_1800062B2
0x1800064af  mov     ecx, 1
0x1800064b4  mov     rdi, [r15+8]
0x1800064b8  jmp     loc_1800062BB
0x1800064bd  mov     dword ptr [rbx+2Ch], 1
0x1800064c4  mov     eax, [rsp+108h+arg_10]
0x1800064cb  mov     [rbx+30h], eax
0x1800064ce  mov     rdi, [rsp+108h+pvarSrc]
0x1800064d3  cmp     rbx, rdi
0x1800064d6  jz      short loc_1800064F5
0x1800064d8  mov     rcx, rbx; pvar
0x1800064db  call    cs:__imp_PropVariantClear
0x1800064e1  mov     rdx, rdi; pvarSrc
0x1800064e4  mov     rcx, rbx; pvarDest
0x1800064e7  call    cs:__imp_PropVariantCopy
0x1800064ed  test    eax, eax
0x1800064ef  js      loc_180006622
0x1800064f5  cmp     word ptr [rbx], 0Ah
0x1800064f9  jz      loc_18000662F
0x1800064ff  mov     edi, r13d
0x180006502  jmp     loc_18000646B
0x180006507  cmp     r12, rax
0x18000650a  jmp     short loc_1800064A9
0x18000650c  lea     rax, WPP_GLOBAL_Control
0x180006513  mov     rcx, cs:WPP_GLOBAL_Control
0x18000651a  cmp     rcx, rax
0x18000651d  jz      short loc_180006529
0x18000651f  test    byte ptr [rcx+1Ch], 1
0x180006523  jnz     loc_180006605
0x180006529  xorps   xmm0, xmm0
0x18000652c  movups  [rsp+108h+var_78], xmm0
0x180006534  movups  [rsp+108h+var_68], xmm0
0x18000653c  movups  xmmword ptr [rsp+108h+pv], xmm0
0x180006544  lea     r9, [rsp+108h+var_78]
0x18000654c  mov     r8d, edi
0x18000654f  mov     rdx, rbx
0x180006552  call    ?_PropVariantToDevProp@CDsmPropertyCache@@AEAAJPEBUtagPROPVARIANT@@W4__MIDL___MIDL_itf_dsmtask_0000_0000_0001@@PEAU_DEVPROPERTY@@@Z; CDsmPropertyCache::_PropVariantToDevProp(tagPROPVARIANT const *,__MIDL___MIDL_itf_dsmtask_0000_0000_0001,_DEVPROPERTY *)
0x180006557  mov     ebx, eax
0x180006559  test    eax, eax
0x18000655b  jns     short loc_180006577
0x18000655d  mov     eax, ebx
0x18000655f  jmp     loc_180006478
0x180006564  mov     edi, 8007000Eh
0x180006569  jmp     loc_18000646B
0x18000656e  mov     [r15+8], rcx
0x180006572  jmp     loc_18000645F
0x180006577  movups  xmm0, xmmword ptr [rsi]
0x18000657a  movups  [rsp+108h+var_78], xmm0
0x180006582  mov     eax, [rsi+10h]
0x180006585  mov     dword ptr [rsp+108h+var_68], eax
0x18000658c  xor     r13d, r13d
0x18000658f  mov     dword ptr [rsp+108h+var_68+4], r13d
0x180006597  mov     qword ptr [rsp+108h+var_68+8], r12
0x18000659f  mov     rdx, [r14+0D0h]
0x1800065a6  lea     r9, [rsp+108h+var_78]
0x1800065ae  mov     r8d, 1
0x1800065b4  test    rdx, rdx
0x1800065b7  jnz     short loc_1800065EF
0x1800065b9  lea     rdx, [r14+80h]
0x1800065c0  mov     ecx, 2
0x1800065c5  call    cs:__imp_DevSetObjectProperties
0x1800065cb  mov     ebx, eax
0x1800065cd  mov     rcx, [rsp+108h+pv+8]; pv
0x1800065d5  call    cs:__imp_CoTaskMemFree
0x1800065db  jmp     short loc_18000655D
0x1800065dd  mov     ecx, 8007000Eh; int
0x1800065e2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800065e7  mov     rcx, r13
0x1800065ea  jmp     loc_1800063DE
0x1800065ef  mov     ecx, 3
0x1800065f4  jmp     short loc_1800065C5
0x1800065f6  mov     eax, 40h ; '@'
0x1800065fb  jmp     loc_18000627F
0x180006600  jmp     loc_180006299
0x180006605  mov     edx, 0Ch
0x18000660a  mov     eax, [rsi+10h]
0x18000660d  mov     [rsp+108h+var_E8], eax
0x180006611  mov     r9, rsi
0x180006614  mov     rcx, [rcx+10h]
0x180006618  call    WPP_SF__guid_d
0x18000661d  jmp     loc_180006529
0x180006622  mov     word ptr [rbx], 0Ah
0x180006627  mov     [rbx+8], eax
0x18000662a  jmp     loc_1800064F5
0x18000662f  mov     edi, [rbx+8]
0x180006632  jmp     loc_18000646B
0x180006637  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000663e  mov     ecx, 38h ; '8'; unsigned __int64
0x180006643  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006648  mov     r15, rax
0x18000664b  mov     [rsp+108h+var_B8], rax
0x180006650  test    rax, rax
0x180006653  jz      loc_180006564
0x180006659  xorps   xmm0, xmm0
0x18000665c  xor     eax, eax
0x18000665e  movups  xmmword ptr [r15], xmm0
0x180006662  movups  xmmword ptr [r15+10h], xmm0
0x180006667  movups  xmmword ptr [r15+20h], xmm0
0x18000666c  mov     [r15+30h], rax
0x180006670  mov     [r15], r13
0x180006673  mov     [r15+8], r13
0x180006677  mov     [r15+10h], r13
0x18000667b  mov     [r15+18h], r13
0x18000667f  mov     [r15+20h], r13
0x180006683  mov     [r15+28h], r13
0x180006687  mov     r14d, 0Ah
0x18000668d  mov     [r15+30h], r14d
0x180006691  mov     [rsp+108h+var_B8], r15
0x180006696  mov     [rsp+108h+var_D0], r15
0x18000669b  test    r15, r15
0x18000669e  jz      loc_180006564
0x1800066a4  mov     rdx, [rsp+108h+var_B0]; unsigned __int16 *
0x1800066a9  mov     rcx, r15; this
0x1800066ac  call    ?Assign@CCoMemString@@QEAAJPEBG@Z; CCoMemString::Assign(ushort const *)
0x1800066b1  mov     edi, eax
0x1800066b3  test    eax, eax
0x1800066b5  js      short loc_1800066F2
0x1800066b7  mov     rcx, [rsp+108h+var_A8]
0x1800066bc  lea     rdx, [rsp+108h+var_D0]
0x1800066c1  cmp     qword ptr [rcx+0D0h], 0
0x1800066c9  jnz     short loc_1800066D6
0x1800066cb  add     rcx, 10h
0x1800066cf  call    ?AddTail@?$CAtlList@PEAVCPropertySet@CDsmPropertyCache@@V?$CElementTraits@PEAVCPropertySet@CDsmPropertyCache@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBQEAVCPropertySet@CDsmPropertyCache@@@Z; ATL::CAtlList<CDsmPropertyCache::CPropertySet *,ATL::CElementTraits<CDsmPropertyCache::CPropertySet *>>::AddTail(CDsmPropertyCache::CPropertySet * const &)
0x1800066d4  jmp     short loc_1800066E0
  ... truncated ...
```
