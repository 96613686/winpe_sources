# ComCrossPlatformAppIdFromCDPCrossPlatformAppId_0

- ea: `0x18000f890`
- end: `0x18000fe25`
- name: `ComCrossPlatformAppIdFromCDPCrossPlatformAppId_0`
- size: `1429`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000efb0`

## callees

- `0x1800097d0`
- `0x18000f890`
- `0x18001d16c`
- `0x18001e798`
- `0x18002c5a0`
- `0x18002d1c8`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000fc29`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000fd22`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000fc29`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000fd22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fac3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fc12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fdef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fac3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fc12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fdef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f8e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fa21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f8e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fa21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc71`

## string_xrefs

- `0x18000fa3d`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000fb25`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000fb47`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000fb95`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000fc8d`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000fd72`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ComCrossPlatformAppIdFromCDPCrossPlatformAppId_0(__int64 a1, _OWORD *a2)
{
  unsigned int v4; // r14d
  void *v5; // rax
  int v6; // r15d
  __int64 v7; // rbx
  _DWORD *v8; // rax
  __int64 v9; // rcx
  volatile signed __int32 *v10; // rbx
  unsigned int i; // r15d
  int v12; // eax
  unsigned int v13; // r12d
  __int64 v14; // rax
  const char *v15; // rbx
  __int64 v16; // rcx
  rsize_t v17; // r13
  char *v18; // rax
  char *v19; // r12
  volatile signed __int32 *v20; // rbx
  char *v21; // rbx
  __int64 v22; // rdi
  volatile signed __int32 *v24; // rbx
  volatile signed __int32 *v25; // rbx
  char *v26; // rbx
  __int64 v27; // rdi
  __int64 v28; // rax
  const char *v29; // rbx
  __int64 v30; // rcx
  rsize_t v31; // r13
  char *v32; // rax
  char *v33; // r12
  volatile signed __int32 *v34; // rbx
  __int64 v35; // rdi
  __int64 v36; // rdx
  std::_Ref_count_base *v37; // rcx
  volatile signed __int32 *v38; // rbx
  char *v39; // rbx
  __int64 v40; // rdi
  int pv; // [rsp+20h] [rbp-38h]
  LPVOID pva[2]; // [rsp+20h] [rbp-38h]
  __int128 v43; // [rsp+30h] [rbp-28h] BYREF
  __int128 v44; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  char v46; // [rsp+A8h] [rbp+50h] BYREF

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
  v43 = 0;
  memset_0(v5, 0, 16LL * v4);
  *(_QWORD *)&v44 = 0;
  *((_QWORD *)&v44 + 1) = &v43;
  v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 40LL))(a1, &v44);
  v7 = v44;
  if ( (_QWORD)v44 )
  {
    v8 = operator new(0x18u);
    v8[2] = 1;
    v8[3] = 1;
    *(_QWORD *)v8 = &std::_Ref_count_resource<ICDPCrossPlatformAppIdEnumerator *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppIdEnumerator>>::`vftable';
    *((_QWORD *)v8 + 2) = v7;
    v9 = *((_QWORD *)&v44 + 1);
    **((_QWORD **)&v44 + 1) = v7;
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
    v36 = *((_QWORD *)&v44 + 1);
    **((_QWORD **)&v44 + 1) = 0;
    v37 = *(std::_Ref_count_base **)(v36 + 8);
    *(_QWORD *)(v36 + 8) = 0;
    if ( v37 )
      std::_Ref_count_base::_Decref(v37);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v6,
      v4);
    v25 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
    if ( *((_QWORD *)&v43 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
        if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
      }
    }
    v26 = (char *)pva[1];
    if ( pva[1] )
    {
      v27 = (__int64)pva[1] + 16 * LODWORD(pva[0]);
      if ( pva[1] != (LPVOID)v27 )
      {
        do
        {
          FreeCDPComCrossPlatformAppIdEntry(v26);
          v26 += 16;
        }
        while ( v26 != (char *)v27 );
        v26 = (char *)pva[1];
      }
      CoTaskMemFree(v26);
    }
    return (unsigned int)v6;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v4 )
    {
LABEL_28:
      *a2 = *(_OWORD *)pva;
      v24 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
      if ( *((_QWORD *)&v43 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
          if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
        }
      }
      return 0;
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)v43 + 24LL))(v43, &v46);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)(unsigned int)v12,
        v4);
      v38 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
      if ( *((_QWORD *)&v43 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
          if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
        }
      }
      v39 = (char *)pva[1];
      if ( pva[1] )
      {
        v40 = (__int64)pva[1] + 16 * LODWORD(pva[0]);
        if ( pva[1] != (LPVOID)v40 )
        {
          do
          {
            FreeCDPComCrossPlatformAppIdEntry(v39);
            v39 += 16;
          }
          while ( v39 != (char *)v40 );
          v39 = (char *)pva[1];
        }
        CoTaskMemFree(v39);
      }
      return v13;
    }
    if ( !v46 )
      goto LABEL_28;
    v44 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v43 + 48LL))(v43);
    v15 = (const char *)v14;
    *((_QWORD *)&v44 + 1) = 0;
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
        FreeCDPComCrossPlatformAppIdEntry(&v44);
        v20 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
        if ( *((_QWORD *)&v43 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
            if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
          }
        }
        v21 = (char *)pva[1];
        if ( pva[1] )
        {
          v22 = (__int64)pva[1] + 16 * LODWORD(pva[0]);
          if ( pva[1] != (LPVOID)v22 )
          {
            do
            {
              FreeCDPComCrossPlatformAppIdEntry(v21);
              v21 += 16;
            }
            while ( v21 != (char *)v22 );
            goto LABEL_25;
          }
          goto LABEL_26;
        }
        return 2147942414LL;
      }
      strcpy_s(v18, v17, v15);
      *((_QWORD *)&v44 + 1) = v19;
    }
    v28 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v43 + 40LL))(v43);
    v29 = (const char *)v28;
    *(_QWORD *)&v44 = 0;
    if ( v28 )
      break;
LABEL_59:
    *((_OWORD *)pva[1] + i) = v44;
  }
  v30 = -1;
  do
    ++v30;
  while ( *(_BYTE *)(v28 + v30) );
  v31 = v30 + 1;
  v32 = (char *)CoTaskMemAlloc(v30 + 1);
  v33 = v32;
  if ( v32 )
  {
    strcpy_s(v32, v31, v29);
    *(_QWORD *)&v44 = v33;
    goto LABEL_59;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x75,
    (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
    (const char *)0x8007000ELL,
    v4);
  FreeCDPComCrossPlatformAppIdEntry(&v44);
  v34 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
  if ( *((_QWORD *)&v43 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
      if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
    }
  }
  v21 = (char *)pva[1];
  if ( pva[1] )
  {
    v35 = (__int64)pva[1] + 16 * LODWORD(pva[0]);
    if ( pva[1] != (LPVOID)v35 )
    {
      do
      {
        FreeCDPComCrossPlatformAppIdEntry(v21);
        v21 += 16;
      }
      while ( v21 != (char *)v35 );
LABEL_25:
      v21 = (char *)pva[1];
    }
LABEL_26:
    CoTaskMemFree(v21);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000f890  push    rbp
0x18000f892  push    rbx
0x18000f893  push    rsi
0x18000f894  push    rdi
0x18000f895  push    r12
0x18000f897  push    r13
0x18000f899  push    r14
0x18000f89b  push    r15
0x18000f89d  mov     rbp, rsp
0x18000f8a0  sub     rsp, 58h
0x18000f8a4  mov     rsi, rdx
0x18000f8a7  mov     rbx, rcx
0x18000f8aa  test    rdx, rdx
0x18000f8ad  jz      loc_18000FB1B
0x18000f8b3  xorps   xmm0, xmm0
0x18000f8b6  movups  xmmword ptr [rdx], xmm0
0x18000f8b9  test    rcx, rcx
0x18000f8bc  jz      loc_18000FB17
0x18000f8c2  movups  xmmword ptr [rbp+pv], xmm0
0x18000f8c6  mov     rax, [rcx]
0x18000f8c9  mov     rax, [rax+38h]
0x18000f8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8d2  mov     r14d, eax
0x18000f8d5  mov     dword ptr [rbp+pv], r14d
0x18000f8d9  mov     edi, eax
0x18000f8db  shl     rdi, 4
0x18000f8df  mov     rcx, rdi; cb
0x18000f8e2  call    cs:__imp_CoTaskMemAlloc
0x18000f8e8  mov     [rbp+pv+8], rax
0x18000f8ec  test    rax, rax
0x18000f8ef  jz      loc_18000FB3D
0x18000f8f5  xorps   xmm0, xmm0
0x18000f8f8  movdqu  [rbp+var_28], xmm0
0x18000f8fd  mov     r8, rdi; Size
0x18000f900  xor     edx, edx; Val
0x18000f902  mov     rcx, rax; void *
0x18000f905  call    memset_0
0x18000f90a  xor     r13d, r13d
0x18000f90d  mov     qword ptr [rbp+var_18], r13
0x18000f911  lea     rax, [rbp+var_28]
0x18000f915  mov     qword ptr [rbp+var_18+8], rax
0x18000f919  mov     rax, [rbx]
0x18000f91c  lea     rdx, [rbp+var_18]
0x18000f920  mov     rcx, rbx
0x18000f923  mov     rax, [rax+28h]
0x18000f927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f92c  mov     r15d, eax
0x18000f92f  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000f936  mov     rbx, qword ptr [rbp+var_18]
0x18000f93a  test    rbx, rbx
0x18000f93d  jz      loc_18000FD49
0x18000f943  mov     ecx, 18h; Size
0x18000f948  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f94d  mov     dword ptr [rax+8], 1
0x18000f954  mov     dword ptr [rax+0Ch], 1
0x18000f95b  lea     rcx, ??_7?$_Ref_count_resource@PEAVICDPCrossPlatformAppIdEnumerator@@U?$iunknown_deleter@VICDPCrossPlatformAppIdEnumerator@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPCrossPlatformAppIdEnumerator *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppIdEnumerator>>::`vftable'
0x18000f962  mov     [rax], rcx
0x18000f965  mov     [rax+10h], rbx
0x18000f969  mov     rcx, qword ptr [rbp+var_18+8]
0x18000f96d  mov     [rcx], rbx
0x18000f970  mov     rbx, [rcx+8]
0x18000f974  mov     [rcx+8], rax
0x18000f978  test    rbx, rbx
0x18000f97b  jz      short loc_18000F9A7
0x18000f97d  mov     eax, edi
0x18000f97f  lock xadd [rbx+8], eax
0x18000f984  cmp     eax, 1
0x18000f987  jnz     short loc_18000F9A7
0x18000f989  mov     rax, [rbx]
0x18000f98c  mov     rcx, rbx
0x18000f98f  mov     rax, [rax]
0x18000f992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f997  mov     eax, edi
0x18000f999  lock xadd [rbx+0Ch], eax
0x18000f99e  cmp     eax, 1
0x18000f9a1  jz      loc_18000FDFD
0x18000f9a7  test    r15d, r15d
0x18000f9aa  js      loc_18000FB8E
0x18000f9b0  mov     r15d, r13d
0x18000f9b3  cmp     r15d, r14d
0x18000f9b6  jnb     loc_18000FADF
0x18000f9bc  mov     rcx, qword ptr [rbp+var_28]
0x18000f9c0  mov     rax, [rcx]
0x18000f9c3  lea     rdx, [rbp+arg_8]
0x18000f9c7  mov     rax, [rax+18h]
0x18000f9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9d0  mov     r12d, eax
0x18000f9d3  test    eax, eax
0x18000f9d5  js      loc_18000FD6B
0x18000f9db  cmp     [rbp+arg_8], 0
0x18000f9df  jz      loc_18000FADF
0x18000f9e5  xorps   xmm0, xmm0
0x18000f9e8  movups  [rbp+var_18], xmm0
0x18000f9ec  mov     rcx, qword ptr [rbp+var_28]
0x18000f9f0  mov     rax, [rcx]
0x18000f9f3  mov     rax, [rax+30h]
0x18000f9f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9fc  mov     rbx, rax
0x18000f9ff  mov     qword ptr [rbp+var_18+8], r13
0x18000fa03  test    rax, rax
0x18000fa06  jz      loc_18000FC36
0x18000fa0c  mov     rcx, rdi
0x18000fa0f  nop
0x18000fa10  lea     rcx, [rcx+1]
0x18000fa14  cmp     byte ptr [rax+rcx], 0
0x18000fa18  jnz     short loc_18000FA10
0x18000fa1a  lea     r13, [rcx+1]
0x18000fa1e  mov     rcx, r13; cb
0x18000fa21  call    cs:__imp_CoTaskMemAlloc
0x18000fa27  mov     r12, rax
0x18000fa2a  test    rax, rax
0x18000fa2d  jnz     loc_18000FC20
0x18000fa33  mov     rcx, [rbp+40h]; this
0x18000fa37  mov     r9d, 8007000Eh; char *
0x18000fa3d  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000fa44  mov     edx, 74h ; 't'; void *
0x18000fa49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa4e  lea     rcx, [rbp+var_18]
0x18000fa52  call    FreeCDPComCrossPlatformAppIdEntry
0x18000fa57  mov     rbx, qword ptr [rbp+var_28+8]
0x18000fa5b  test    rbx, rbx
0x18000fa5e  jz      short loc_18000FA93
0x18000fa60  mov     eax, edi
0x18000fa62  lock xadd [rbx+8], eax
0x18000fa67  cmp     eax, 1
0x18000fa6a  jnz     short loc_18000FA93
0x18000fa6c  mov     rax, [rbx]
0x18000fa6f  mov     rcx, rbx
0x18000fa72  mov     rax, [rax]
0x18000fa75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa7a  lock xadd [rbx+0Ch], edi
0x18000fa7f  cmp     edi, 1
0x18000fa82  jnz     short loc_18000FA93
0x18000fa84  mov     rax, [rbx]
0x18000fa87  mov     rcx, rbx
0x18000fa8a  mov     rax, [rax+8]
0x18000fa8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa93  mov     rbx, [rbp+pv+8]
0x18000fa97  test    rbx, rbx
0x18000fa9a  jz      short loc_18000FAC9
0x18000fa9c  mov     edi, dword ptr [rbp+pv]
0x18000fa9f  shl     rdi, 4
0x18000faa3  add     rdi, rbx
0x18000faa6  cmp     rbx, rdi
0x18000faa9  jz      short loc_18000FAC0
0x18000faab  mov     rcx, rbx
0x18000faae  call    FreeCDPComCrossPlatformAppIdEntry
0x18000fab3  add     rbx, 10h
0x18000fab7  cmp     rbx, rdi
0x18000faba  jnz     short loc_18000FAAB
0x18000fabc  mov     rbx, [rbp+pv+8]
0x18000fac0  mov     rcx, rbx; pv
0x18000fac3  call    cs:__imp_CoTaskMemFree
0x18000fac9  mov     eax, 8007000Eh
0x18000face  add     rsp, 58h
0x18000fad2  pop     r15
0x18000fad4  pop     r14
0x18000fad6  pop     r13
0x18000fad8  pop     r12
0x18000fada  pop     rdi
0x18000fadb  pop     rsi
0x18000fadc  pop     rbx
0x18000fadd  pop     rbp
0x18000fade  retn
0x18000fadf  movups  xmm0, xmmword ptr [rbp+pv]
0x18000fae3  movups  xmmword ptr [rsi], xmm0
0x18000fae6  mov     rbx, qword ptr [rbp+var_28+8]
0x18000faea  test    rbx, rbx
0x18000faed  jz      short loc_18000FB17
0x18000faef  mov     eax, edi
0x18000faf1  lock xadd [rbx+8], eax
0x18000faf6  cmp     eax, 1
0x18000faf9  jnz     short loc_18000FB17
0x18000fafb  mov     rax, [rbx]
0x18000fafe  mov     rcx, rbx
0x18000fb01  mov     rax, [rax]
0x18000fb04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb09  lock xadd [rbx+0Ch], edi
0x18000fb0e  cmp     edi, 1
0x18000fb11  jz      loc_18000FE11
0x18000fb17  xor     eax, eax
0x18000fb19  jmp     short loc_18000FACE
0x18000fb1b  mov     rcx, [rbp+40h]; this
0x18000fb1f  mov     r9d, 80004003h; char *
0x18000fb25  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000fb2c  mov     edx, 55h ; 'U'; void *
0x18000fb31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fb36  mov     eax, 80004003h
0x18000fb3b  jmp     short loc_18000FACE
0x18000fb3d  mov     rcx, [rbp+40h]; this
0x18000fb41  mov     r9d, 8007000Eh; char *
0x18000fb47  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000fb4e  mov     edx, 63h ; 'c'; void *
0x18000fb53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fb58  mov     rbx, [rbp+pv+8]
0x18000fb5c  test    rbx, rbx
0x18000fb5f  jz      loc_18000FAC9
0x18000fb65  mov     edi, dword ptr [rbp+pv]
0x18000fb68  shl     rdi, 4
0x18000fb6c  add     rdi, rbx
0x18000fb6f  cmp     rbx, rdi
0x18000fb72  jz      loc_18000FAC0
0x18000fb78  mov     rcx, rbx
0x18000fb7b  call    FreeCDPComCrossPlatformAppIdEntry
0x18000fb80  add     rbx, 10h
0x18000fb84  cmp     rbx, rdi
0x18000fb87  jnz     short loc_18000FB78
0x18000fb89  jmp     loc_18000FABC
0x18000fb8e  mov     rcx, [rbp+40h]; this
0x18000fb92  mov     r9d, r15d; char *
0x18000fb95  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000fb9c  mov     edx, 67h ; 'g'; void *
0x18000fba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fba6  mov     rbx, qword ptr [rbp+var_28+8]
0x18000fbaa  test    rbx, rbx
0x18000fbad  jz      short loc_18000FBE2
0x18000fbaf  mov     eax, edi
0x18000fbb1  lock xadd [rbx+8], eax
0x18000fbb6  cmp     eax, 1
0x18000fbb9  jnz     short loc_18000FBE2
0x18000fbbb  mov     rax, [rbx]
0x18000fbbe  mov     rcx, rbx
0x18000fbc1  mov     rax, [rax]
0x18000fbc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbc9  lock xadd [rbx+0Ch], edi
0x18000fbce  cmp     edi, 1
0x18000fbd1  jnz     short loc_18000FBE2
0x18000fbd3  mov     rax, [rbx]
0x18000fbd6  mov     rcx, rbx
0x18000fbd9  mov     rax, [rax+8]
0x18000fbdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbe2  mov     rbx, [rbp+pv+8]
0x18000fbe6  test    rbx, rbx
0x18000fbe9  jz      short loc_18000FC18
0x18000fbeb  mov     edi, dword ptr [rbp+pv]
0x18000fbee  shl     rdi, 4
0x18000fbf2  add     rdi, rbx
0x18000fbf5  cmp     rbx, rdi
0x18000fbf8  jz      short loc_18000FC0F
0x18000fbfa  mov     rcx, rbx
0x18000fbfd  call    FreeCDPComCrossPlatformAppIdEntry
0x18000fc02  add     rbx, 10h
0x18000fc06  cmp     rbx, rdi
0x18000fc09  jnz     short loc_18000FBFA
0x18000fc0b  mov     rbx, [rbp+pv+8]
0x18000fc0f  mov     rcx, rbx; pv
0x18000fc12  call    cs:__imp_CoTaskMemFree
0x18000fc18  mov     eax, r15d
0x18000fc1b  jmp     loc_18000FACE
0x18000fc20  mov     r8, rbx; Source
0x18000fc23  mov     rdx, r13; SizeInBytes
0x18000fc26  mov     rcx, r12; Destination
0x18000fc29  call    cs:__imp_strcpy_s
0x18000fc2f  mov     qword ptr [rbp+var_18+8], r12
0x18000fc33  xor     r13d, r13d
0x18000fc36  mov     rcx, qword ptr [rbp+var_28]
0x18000fc3a  mov     rax, [rcx]
0x18000fc3d  mov     rax, [rax+28h]
0x18000fc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc46  mov     rbx, rax
0x18000fc49  mov     qword ptr [rbp+var_18], r13
0x18000fc4d  test    rax, rax
0x18000fc50  jz      loc_18000FD2F
0x18000fc56  mov     rcx, rdi
0x18000fc59  nop     dword ptr [rax+00000000h]
0x18000fc60  lea     rcx, [rcx+1]
0x18000fc64  cmp     byte ptr [rax+rcx], 0
0x18000fc68  jnz     short loc_18000FC60
0x18000fc6a  lea     r13, [rcx+1]
0x18000fc6e  mov     rcx, r13; cb
0x18000fc71  call    cs:__imp_CoTaskMemAlloc
0x18000fc77  mov     r12, rax
0x18000fc7a  test    rax, rax
0x18000fc7d  jnz     loc_18000FD19
0x18000fc83  mov     rcx, [rbp+40h]; this
0x18000fc87  mov     r9d, 8007000Eh; char *
0x18000fc8d  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000fc94  mov     edx, 75h ; 'u'; void *
0x18000fc99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc9e  lea     rcx, [rbp+var_18]
0x18000fca2  call    FreeCDPComCrossPlatformAppIdEntry
0x18000fca7  mov     rbx, qword ptr [rbp+var_28+8]
0x18000fcab  test    rbx, rbx
0x18000fcae  jz      short loc_18000FCE3
0x18000fcb0  mov     eax, edi
0x18000fcb2  lock xadd [rbx+8], eax
0x18000fcb7  cmp     eax, 1
0x18000fcba  jnz     short loc_18000FCE3
0x18000fcbc  mov     rax, [rbx]
0x18000fcbf  mov     rcx, rbx
0x18000fcc2  mov     rax, [rax]
0x18000fcc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcca  lock xadd [rbx+0Ch], edi
0x18000fccf  cmp     edi, 1
0x18000fcd2  jnz     short loc_18000FCE3
0x18000fcd4  mov     rax, [rbx]
0x18000fcd7  mov     rcx, rbx
0x18000fcda  mov     rax, [rax+8]
0x18000fcde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fce3  mov     rbx, [rbp+pv+8]
  ... truncated ...
```
