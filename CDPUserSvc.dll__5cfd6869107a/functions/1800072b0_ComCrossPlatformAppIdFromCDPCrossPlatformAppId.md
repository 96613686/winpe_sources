# ComCrossPlatformAppIdFromCDPCrossPlatformAppId

- ea: `0x1800072b0`
- end: `0x1800077b9`
- name: `ComCrossPlatformAppIdFromCDPCrossPlatformAppId`
- size: `1289`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800069c0`

## callees

- `0x1800072b0`
- `0x1800097d0`
- `0x1800098e0`
- `0x18001d16c`
- `0x18001e798`
- `0x18002c5a0`
- `0x18002d1c8`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000752e`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180007618`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000752e`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180007618`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800077ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800077ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007571`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007571`

## string_xrefs

- `0x18000745d`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800074f6`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000758d`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800075f4`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180007675`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800076cc`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ComCrossPlatformAppIdFromCDPCrossPlatformAppId(__int64 a1, _OWORD *a2)
{
  unsigned int v4; // r12d
  void *v5; // rax
  int v6; // esi
  __int64 v7; // rbx
  _DWORD *v8; // rax
  __int64 v9; // rcx
  volatile signed __int32 *v10; // rbx
  unsigned int i; // r13d
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rax
  const char *v15; // rbx
  __int64 v16; // rcx
  rsize_t v17; // r14
  char *v18; // rax
  char *v19; // rsi
  char *v20; // rbx
  volatile signed __int32 *v22; // rbx
  char *v23; // rdi
  __int64 v24; // rax
  const char *v25; // rbx
  __int64 v26; // rcx
  rsize_t v27; // r14
  char *v28; // rax
  char *v29; // rsi
  __int64 v30; // rdi
  char *v31; // rbx
  __int64 v32; // rdi
  __int64 v33; // rdi
  __int64 v34; // rsi
  int pv; // [rsp+20h] [rbp-48h]
  LPVOID pva[2]; // [rsp+20h] [rbp-48h]
  std::_Ref_count_base *v37[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v38; // [rsp+40h] [rbp-28h] BYREF
  std::_Ref_count_base *v39[2]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  char v41; // [rsp+B8h] [rbp+50h] BYREF

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x80004003LL,
      pv);
    return 2147500035LL;
  }
  *a2 = 0;
  if ( !a1 )
    return 0;
  HIDWORD(pva[0]) = 0;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1);
  LODWORD(pva[0]) = v4;
  v5 = CoTaskMemAlloc(16LL * v4);
  pva[1] = v5;
  if ( !v5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x8007000ELL,
      v4);
    return 2147942414LL;
  }
  *(_OWORD *)v37 = 0;
  memset_0(v5, 0, 16LL * v4);
  *(_QWORD *)&v38 = 0;
  *((_QWORD *)&v38 + 1) = v37;
  v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 40LL))(a1, &v38);
  v7 = v38;
  if ( (_QWORD)v38 )
  {
    v8 = operator new(0x18u);
    v8[2] = 1;
    v8[3] = 1;
    *(_QWORD *)v8 = &std::_Ref_count_resource<ICDPCrossPlatformAppIdEnumerator *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppIdEnumerator>>::`vftable';
    *((_QWORD *)v8 + 2) = v7;
    v9 = *((_QWORD *)&v38 + 1);
    **((_QWORD **)&v38 + 1) = v7;
    v10 = *(volatile signed __int32 **)(v9 + 8);
    *(_QWORD *)(v9 + 8) = v8;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
  }
  else
  {
    *(_OWORD *)v39 = 0;
    std::shared_ptr<CDPComActivityStoreManagementControl::ActivityStoreManagementCallback>::operator=(
      *((_QWORD *)&v38 + 1),
      v39);
    if ( v39[1] )
      std::_Ref_count_base::_Decref(v39[1]);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v6,
      v4);
    if ( v37[1] )
      std::_Ref_count_base::_Decref(v37[1]);
    v31 = (char *)pva[1];
    if ( pva[1] )
    {
      v32 = (__int64)pva[1] + 16 * LODWORD(pva[0]);
      if ( pva[1] != (LPVOID)v32 )
      {
        do
        {
          FreeCDPComCrossPlatformAppIdEntry(v31);
          v31 += 16;
        }
        while ( v31 != (char *)v32 );
        v31 = (char *)pva[1];
      }
      CoTaskMemFree(v31);
    }
    return (unsigned int)v6;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v4 )
    {
LABEL_22:
      *a2 = *(_OWORD *)pva;
      v22 = (volatile signed __int32 *)v37[1];
      if ( v37[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v37[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        }
      }
      return 0;
    }
    v12 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, char *))(*(_QWORD *)v37[0] + 24LL))(v37[0], &v41);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)(unsigned int)v12,
        v4);
      if ( v37[1] )
        std::_Ref_count_base::_Decref(v37[1]);
      v23 = (char *)pva[1];
      if ( pva[1] )
      {
        v34 = (__int64)pva[1] + 16 * LODWORD(pva[0]);
        if ( pva[1] != (LPVOID)v34 )
        {
          do
          {
            FreeCDPComCrossPlatformAppIdEntry(v23);
            v23 += 16;
          }
          while ( v23 != (char *)v34 );
          v23 = (char *)pva[1];
        }
        CoTaskMemFree(v23);
      }
      return v13;
    }
    if ( !v41 )
      goto LABEL_22;
    v38 = 0;
    v14 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v37[0] + 48LL))(v37[0]);
    v15 = (const char *)v14;
    *((_QWORD *)&v38 + 1) = 0;
    if ( v14 )
    {
      v16 = -1;
      do
        ++v16;
      while ( *(_BYTE *)(v14 + v16) );
      v17 = v16 + 1;
      v18 = (char *)CoTaskMemAlloc(v16 + 1);
      v19 = v18;
      if ( !v18 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
          (const char *)0x8007000ELL,
          v4);
        FreeCDPComCrossPlatformAppIdEntry(&v38);
        if ( v37[1] )
          std::_Ref_count_base::_Decref(v37[1]);
        v20 = (char *)pva[1];
        if ( !pva[1] )
          return 2147942414LL;
        v33 = (__int64)pva[1] + 16 * LODWORD(pva[0]);
        if ( pva[1] != (LPVOID)v33 )
        {
          do
          {
            FreeCDPComCrossPlatformAppIdEntry(v20);
            v20 += 16;
          }
          while ( v20 != (char *)v33 );
          goto LABEL_48;
        }
        goto LABEL_49;
      }
      strcpy_s(v18, v17, v15);
      *((_QWORD *)&v38 + 1) = v19;
    }
    v24 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v37[0] + 40LL))(v37[0]);
    v25 = (const char *)v24;
    *(_QWORD *)&v38 = 0;
    if ( v24 )
      break;
LABEL_44:
    *((_OWORD *)pva[1] + i) = v38;
  }
  v26 = -1;
  do
    ++v26;
  while ( *(_BYTE *)(v24 + v26) );
  v27 = v26 + 1;
  v28 = (char *)CoTaskMemAlloc(v26 + 1);
  v29 = v28;
  if ( v28 )
  {
    strcpy_s(v28, v27, v25);
    *(_QWORD *)&v38 = v29;
    goto LABEL_44;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x75,
    (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
    (const char *)0x8007000ELL,
    v4);
  FreeCDPComCrossPlatformAppIdEntry(&v38);
  if ( v37[1] )
    std::_Ref_count_base::_Decref(v37[1]);
  v20 = (char *)pva[1];
  if ( pva[1] )
  {
    v30 = (__int64)pva[1] + 16 * LODWORD(pva[0]);
    if ( pva[1] != (LPVOID)v30 )
    {
      do
      {
        FreeCDPComCrossPlatformAppIdEntry(v20);
        v20 += 16;
      }
      while ( v20 != (char *)v30 );
LABEL_48:
      v20 = (char *)pva[1];
    }
LABEL_49:
    CoTaskMemFree(v20);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800072b0  push    rbp
0x1800072b2  push    rbx
0x1800072b3  push    rsi
0x1800072b4  push    rdi
0x1800072b5  push    r12
0x1800072b7  push    r13
0x1800072b9  push    r14
0x1800072bb  push    r15
0x1800072bd  mov     rbp, rsp
0x1800072c0  sub     rsp, 68h
0x1800072c4  mov     r15, rdx
0x1800072c7  mov     rbx, rcx
0x1800072ca  test    rdx, rdx
0x1800072cd  jz      loc_1800075EA
0x1800072d3  xorps   xmm0, xmm0
0x1800072d6  movups  xmmword ptr [rdx], xmm0
0x1800072d9  test    rcx, rcx
0x1800072dc  jz      loc_1800074DC
0x1800072e2  movups  xmmword ptr [rbp+pv], xmm0
0x1800072e6  mov     rax, [rcx]
0x1800072e9  mov     rax, [rax+38h]
0x1800072ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072f2  mov     r12d, eax
0x1800072f5  mov     dword ptr [rbp+pv], r12d
0x1800072f9  mov     edi, eax
0x1800072fb  shl     rdi, 4
0x1800072ff  mov     rcx, rdi; cb
0x180007302  call    cs:__imp_CoTaskMemAlloc
0x180007308  mov     [rbp+pv+8], rax
0x18000730c  test    rax, rax
0x18000730f  jz      loc_18000766B
0x180007315  xorps   xmm0, xmm0
0x180007318  movdqu  xmmword ptr [rbp+var_38], xmm0
0x18000731d  mov     r8, rdi; Size
0x180007320  xor     edx, edx; Val
0x180007322  mov     rcx, rax; void *
0x180007325  call    memset_0
0x18000732a  xor     r14d, r14d
0x18000732d  mov     qword ptr [rbp+var_28], r14
0x180007331  lea     rax, [rbp+var_38]
0x180007335  mov     qword ptr [rbp+var_28+8], rax
0x180007339  mov     rax, [rbx]
0x18000733c  lea     rdx, [rbp+var_28]
0x180007340  mov     rcx, rbx
0x180007343  mov     rax, [rax+28h]
0x180007347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000734c  mov     esi, eax
0x18000734e  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180007355  mov     rbx, qword ptr [rbp+var_28]
0x180007359  test    rbx, rbx
0x18000735c  jz      loc_18000763F
0x180007362  mov     ecx, 18h; Size
0x180007367  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000736c  mov     dword ptr [rax+8], 1
0x180007373  mov     dword ptr [rax+0Ch], 1
0x18000737a  lea     rcx, ??_7?$_Ref_count_resource@PEAVICDPCrossPlatformAppIdEnumerator@@U?$iunknown_deleter@VICDPCrossPlatformAppIdEnumerator@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPCrossPlatformAppIdEnumerator *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppIdEnumerator>>::`vftable'
0x180007381  mov     [rax], rcx
0x180007384  mov     [rax+10h], rbx
0x180007388  mov     rcx, qword ptr [rbp+var_28+8]
0x18000738c  mov     [rcx], rbx
0x18000738f  mov     rbx, [rcx+8]
0x180007393  mov     [rcx+8], rax
0x180007397  test    rbx, rbx
0x18000739a  jz      short loc_1800073C6
0x18000739c  mov     eax, edi
0x18000739e  lock xadd [rbx+8], eax
0x1800073a3  cmp     eax, 1
0x1800073a6  jnz     short loc_1800073C6
0x1800073a8  mov     rax, [rbx]
0x1800073ab  mov     rcx, rbx
0x1800073ae  mov     rax, [rax]
0x1800073b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b6  mov     eax, edi
0x1800073b8  lock xadd [rbx+0Ch], eax
0x1800073bd  cmp     eax, 1
0x1800073c0  jz      loc_1800076F6
0x1800073c6  test    esi, esi
0x1800073c8  js      loc_1800076C5
0x1800073ce  mov     r13d, r14d
0x1800073d1  cmp     r13d, r12d
0x1800073d4  jnb     loc_180007498
0x1800073da  mov     rcx, [rbp+var_38]
0x1800073de  mov     rax, [rcx]
0x1800073e1  lea     rdx, [rbp+arg_8]
0x1800073e5  mov     rax, [rax+18h]
0x1800073e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073ee  mov     ebx, eax
0x1800073f0  test    eax, eax
0x1800073f2  js      loc_1800074EF
0x1800073f8  cmp     [rbp+arg_8], 0
0x1800073fc  jz      loc_180007498
0x180007402  xorps   xmm0, xmm0
0x180007405  movups  [rbp+var_28], xmm0
0x180007409  mov     rcx, [rbp+var_38]
0x18000740d  mov     rax, [rcx]
0x180007410  mov     rax, [rax+30h]
0x180007414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007419  mov     rbx, rax
0x18000741c  mov     qword ptr [rbp+var_28+8], r14
0x180007420  test    rax, rax
0x180007423  jz      loc_18000753B
0x180007429  mov     rcx, rdi
0x18000742c  nop     dword ptr [rax+00h]
0x180007430  lea     rcx, [rcx+1]
0x180007434  cmp     byte ptr [rax+rcx], 0
0x180007438  jnz     short loc_180007430
0x18000743a  lea     r14, [rcx+1]
0x18000743e  mov     rcx, r14; cb
0x180007441  call    cs:__imp_CoTaskMemAlloc
0x180007447  mov     rsi, rax
0x18000744a  test    rax, rax
0x18000744d  jnz     loc_180007525
0x180007453  mov     rcx, [rbp+40h]; this
0x180007457  mov     r9d, 8007000Eh; char *
0x18000745d  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180007464  mov     edx, 74h ; 't'; void *
0x180007469  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000746e  lea     rcx, [rbp+var_28]
0x180007472  call    FreeCDPComCrossPlatformAppIdEntry
0x180007477  mov     rcx, [rbp+var_38+8]; this
0x18000747b  test    rcx, rcx
0x18000747e  jnz     loc_180007740
0x180007484  mov     rbx, [rbp+pv+8]
0x180007488  test    rbx, rbx
0x18000748b  jnz     loc_18000774A
0x180007491  mov     eax, 8007000Eh
0x180007496  jmp     short loc_1800074DE
0x180007498  movups  xmm0, xmmword ptr [rbp+pv]
0x18000749c  movups  xmmword ptr [r15], xmm0
0x1800074a0  mov     rbx, [rbp+var_38+8]
0x1800074a4  test    rbx, rbx
0x1800074a7  jz      short loc_1800074DC
0x1800074a9  mov     eax, edi
0x1800074ab  lock xadd [rbx+8], eax
0x1800074b0  cmp     eax, 1
0x1800074b3  jnz     short loc_1800074DC
0x1800074b5  mov     rax, [rbx]
0x1800074b8  mov     rcx, rbx
0x1800074bb  mov     rax, [rax]
0x1800074be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074c3  lock xadd [rbx+0Ch], edi
0x1800074c8  cmp     edi, 1
0x1800074cb  jnz     short loc_1800074DC
0x1800074cd  mov     rax, [rbx]
0x1800074d0  mov     rcx, rbx
0x1800074d3  mov     rax, [rax+8]
0x1800074d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074dc  xor     eax, eax
0x1800074de  add     rsp, 68h
0x1800074e2  pop     r15
0x1800074e4  pop     r14
0x1800074e6  pop     r13
0x1800074e8  pop     r12
0x1800074ea  pop     rdi
0x1800074eb  pop     rsi
0x1800074ec  pop     rbx
0x1800074ed  pop     rbp
0x1800074ee  retn
0x1800074ef  mov     rcx, [rbp+40h]; this
0x1800074f3  mov     r9d, ebx; char *
0x1800074f6  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800074fd  mov     edx, 7Ah ; 'z'; void *
0x180007502  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007507  mov     rcx, [rbp+var_38+8]; this
0x18000750b  test    rcx, rcx
0x18000750e  jnz     loc_18000777D
0x180007514  mov     rdi, [rbp+pv+8]
0x180007518  test    rdi, rdi
0x18000751b  jnz     loc_180007787
0x180007521  mov     eax, ebx
0x180007523  jmp     short loc_1800074DE
0x180007525  mov     r8, rbx; Source
0x180007528  mov     rdx, r14; SizeInBytes
0x18000752b  mov     rcx, rsi; Destination
0x18000752e  call    cs:__imp_strcpy_s
0x180007534  mov     qword ptr [rbp+var_28+8], rsi
0x180007538  xor     r14d, r14d
0x18000753b  mov     rcx, [rbp+var_38]
0x18000753f  mov     rax, [rcx]
0x180007542  mov     rax, [rax+28h]
0x180007546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000754b  mov     rbx, rax
0x18000754e  mov     qword ptr [rbp+var_28], r14
0x180007552  test    rax, rax
0x180007555  jz      loc_180007625
0x18000755b  mov     rcx, rdi
0x18000755e  xchg    ax, ax
0x180007560  lea     rcx, [rcx+1]
0x180007564  cmp     byte ptr [rax+rcx], 0
0x180007568  jnz     short loc_180007560
0x18000756a  lea     r14, [rcx+1]
0x18000756e  mov     rcx, r14; cb
0x180007571  call    cs:__imp_CoTaskMemAlloc
0x180007577  mov     rsi, rax
0x18000757a  test    rax, rax
0x18000757d  jnz     loc_18000760F
0x180007583  mov     rcx, [rbp+40h]; this
0x180007587  mov     r9d, 8007000Eh; char *
0x18000758d  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180007594  mov     edx, 75h ; 'u'; void *
0x180007599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000759e  lea     rcx, [rbp+var_28]
0x1800075a2  call    FreeCDPComCrossPlatformAppIdEntry
0x1800075a7  mov     rcx, [rbp+var_38+8]; this
0x1800075ab  test    rcx, rcx
0x1800075ae  jnz     loc_180007773
0x1800075b4  mov     rbx, [rbp+pv+8]
0x1800075b8  test    rbx, rbx
0x1800075bb  jz      loc_180007491
0x1800075c1  mov     edi, dword ptr [rbp+pv]
0x1800075c4  shl     rdi, 4
0x1800075c8  add     rdi, rbx
0x1800075cb  cmp     rbx, rdi
0x1800075ce  jz      loc_1800076B7
0x1800075d4  mov     rcx, rbx
0x1800075d7  call    FreeCDPComCrossPlatformAppIdEntry
0x1800075dc  add     rbx, 10h
0x1800075e0  cmp     rbx, rdi
0x1800075e3  jnz     short loc_1800075D4
0x1800075e5  jmp     loc_1800076B3
0x1800075ea  mov     rcx, [rbp+40h]; this
0x1800075ee  mov     r9d, 80004003h; char *
0x1800075f4  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800075fb  mov     edx, 55h ; 'U'; void *
0x180007600  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007605  mov     eax, 80004003h
0x18000760a  jmp     loc_1800074DE
0x18000760f  mov     r8, rbx; Source
0x180007612  mov     rdx, r14; SizeInBytes
0x180007615  mov     rcx, rsi; Destination
0x180007618  call    cs:__imp_strcpy_s
0x18000761e  mov     qword ptr [rbp+var_28], rsi
0x180007622  xor     r14d, r14d
0x180007625  mov     ecx, r13d
0x180007628  add     rcx, rcx
0x18000762b  mov     rax, [rbp+pv+8]
0x18000762f  movups  xmm0, [rbp+var_28]
0x180007633  movups  xmmword ptr [rax+rcx*8], xmm0
0x180007637  inc     r13d
0x18000763a  jmp     loc_1800073D1
0x18000763f  xorps   xmm0, xmm0
0x180007642  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180007647  lea     rdx, [rbp+var_18]
0x18000764b  mov     rcx, qword ptr [rbp+var_28+8]
0x18000764f  call    ??4?$shared_ptr@VActivityStoreManagementCallback@CDPComActivityStoreManagementControl@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CDPComActivityStoreManagementControl::ActivityStoreManagementCallback>::operator=(std::shared_ptr<CDPComActivityStoreManagementControl::ActivityStoreManagementCallback> &&)
0x180007654  mov     rcx, [rbp+var_18+8]; this
0x180007658  test    rcx, rcx
0x18000765b  jz      loc_1800073C6
0x180007661  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180007666  jmp     loc_1800073C6
0x18000766b  mov     rcx, [rbp+40h]; this
0x18000766f  mov     r9d, 8007000Eh; char *
0x180007675  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000767c  mov     edx, 63h ; 'c'; void *
0x180007681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007686  mov     rbx, [rbp+pv+8]
0x18000768a  test    rbx, rbx
0x18000768d  jz      loc_180007491
0x180007693  mov     edi, dword ptr [rbp+pv]
0x180007696  shl     rdi, 4
0x18000769a  add     rdi, rbx
0x18000769d  cmp     rbx, rdi
0x1800076a0  jz      short loc_1800076B7
0x1800076a2  mov     rcx, rbx
0x1800076a5  call    FreeCDPComCrossPlatformAppIdEntry
0x1800076aa  add     rbx, 10h
0x1800076ae  cmp     rbx, rdi
0x1800076b1  jnz     short loc_1800076A2
0x1800076b3  mov     rbx, [rbp+pv+8]
0x1800076b7  mov     rcx, rbx; pv
0x1800076ba  call    cs:__imp_CoTaskMemFree
0x1800076c0  jmp     loc_180007491
0x1800076c5  mov     rcx, [rbp+40h]; this
0x1800076c9  mov     r9d, esi; char *
0x1800076cc  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800076d3  mov     edx, 67h ; 'g'; void *
0x1800076d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076dd  mov     rcx, [rbp+var_38+8]; this
0x1800076e1  test    rcx, rcx
0x1800076e4  jnz     short loc_18000770A
0x1800076e6  mov     rbx, [rbp+pv+8]
0x1800076ea  test    rbx, rbx
0x1800076ed  jnz     short loc_180007711
0x1800076ef  mov     eax, esi
0x1800076f1  jmp     loc_1800074DE
0x1800076f6  mov     rax, [rbx]
0x1800076f9  mov     rcx, rbx
0x1800076fc  mov     rax, [rax+8]
0x180007700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007705  jmp     loc_1800073C6
0x18000770a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000770f  jmp     short loc_1800076E6
0x180007711  mov     edi, dword ptr [rbp+pv]
0x180007714  shl     rdi, 4
0x180007718  add     rdi, rbx
0x18000771b  cmp     rbx, rdi
0x18000771e  jz      short loc_180007735
0x180007720  mov     rcx, rbx
0x180007723  call    FreeCDPComCrossPlatformAppIdEntry
0x180007728  add     rbx, 10h
  ... truncated ...
```
