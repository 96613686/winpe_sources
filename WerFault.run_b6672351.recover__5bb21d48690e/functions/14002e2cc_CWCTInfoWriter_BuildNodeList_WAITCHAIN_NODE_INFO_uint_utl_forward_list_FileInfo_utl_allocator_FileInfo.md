# CWCTInfoWriter::BuildNodeList(_WAITCHAIN_NODE_INFO *,uint,utl::forward_list<FileInfo,utl::allocator<FileInfo>> &)

- ea: `0x14002e2cc`
- end: `0x14002e6fe`
- name: `?BuildNodeList@CWCTInfoWriter@@AEAAJPEAU_WAITCHAIN_NODE_INFO@@IAEAV?$forward_list@UFileInfo@@V?$allocator@UFileInfo@@@utl@@@utl@@@Z`
- size: `1074`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002f70c`

## callees

- `0x140002490`
- `0x1400024b4`
- `0x140002748`
- `0x1400030f8`
- `0x14000b580`
- `0x14000d544`
- `0x140014ee4`
- `0x1400166ec`
- `0x14002e2cc`
- `0x140032700`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x14002e511`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x14002e511`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14002e4eb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14002e4eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002e58e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002e58e`

## pseudocode

```c
__int64 __fastcall CWCTInfoWriter::BuildNodeList(_QWORD *a1, __int64 a2, __int64 a3, __int64 **a4)
{
  unsigned int v5; // r12d
  _QWORD *v8; // rcx
  _QWORD *v9; // rsi
  unsigned int v10; // r14d
  CUserModeHangReport *v11; // rcx
  __int64 v12; // rdi
  char *v13; // rax
  char *v14; // rbx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  __int64 *v17; // rax
  unsigned int v18; // r9d
  __int64 v19; // rdx
  unsigned int v20; // r14d
  __int64 v21; // rcx
  int v22; // edx
  __int64 v23; // rdi
  OLECHAR *v24; // rbx
  OLECHAR *v25; // r8
  OLECHAR *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  _WORD *v30; // r8
  __int64 v31; // rax
  _WORD *v32; // rbx
  _QWORD *i; // rbx
  _QWORD *j; // rdi
  _QWORD *v36; // rcx
  LPOLESTR lpszProgID; // [rsp+30h] [rbp-68h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-60h] BYREF

  v5 = a3;
  if ( *a1 != -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3, a4);
  while ( 1 )
  {
    v8 = (_QWORD *)*a1;
    if ( *a1 == -1 )
      break;
    *a1 = *v8;
    operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
  }
  v9 = a1;
  v10 = 0;
  if ( v5 )
  {
    v11 = WPP_GLOBAL_Control;
    while ( 1 )
    {
      v12 = 280LL * v10;
      if ( *(_DWORD *)(v12 + a2) != 8 )
      {
        if ( v11 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)v11 + 2), 40, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids);
        return 2147500037LL;
      }
      v13 = (char *)operator new(0x258u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      if ( !v13 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids);
        }
        return 2147942414LL;
      }
      memset_0(v13 + 8, 0, 0x250u);
      *(_QWORD *)v14 = *v9;
      *v9 = v14;
      if ( v9 != a1 )
        v9[68] = v14 + 8;
      v15 = currNodeId;
      *((_DWORD *)v14 + 2) = currNodeId;
      v9 = v14;
      currNodeId = v15 + 1;
      v16 = *(_DWORD *)(280LL * v10 + a2 + 8);
      *((_DWORD *)v14 + 3) = v16;
      UtilGetProcessName(v16, (wchar_t *)v14 + 10, 0x80u);
      v17 = *a4;
      v18 = 0;
      while ( v17 != (__int64 *)-1LL && v18 < 3 )
      {
        if ( *((_DWORD *)v17 + 10) == *((_DWORD *)v14 + 3) && ((*((_DWORD *)v17 + 11) - 1) & 0xFFFFFFFB) == 0 )
        {
          *(_QWORD *)&v14[16 * v18 + 552] = v17[1];
          v19 = v18++ + 35LL;
          *(_DWORD *)&v14[16 * v19] = *((_DWORD *)v17 + 11);
          *((_DWORD *)v17 + 10) = 0;
        }
        v17 = (__int64 *)*v17;
      }
      if ( (unsigned int)(*(_DWORD *)(v12 + a2 + 4) - 4) > 1 )
      {
        *((_DWORD *)v14 + 4) = *(_DWORD *)(v12 + a2 + 12);
        *((_DWORD *)v14 + 70) = *(_DWORD *)(v12 + a2 + 20);
      }
      if ( *(_DWORD *)(v12 + a2 + 4) != 3 )
        *((_DWORD *)v14 + 69) = *(_DWORD *)(v12 + a2 + 16);
      v20 = v10 + 1;
      if ( v20 >= v5 )
        goto LABEL_52;
      v21 = 280LL * v20;
      *((_DWORD *)v14 + 135) = *(_DWORD *)(v21 + a2);
      v22 = *(_DWORD *)(v21 + a2);
      if ( (unsigned int)(v22 - 3) <= 1 )
      {
        v29 = 2147483646;
        v30 = (_WORD *)(v21 + a2 + 8);
        v31 = 128;
        v32 = v14 + 284;
        while ( v29 )
        {
          if ( *v30 )
          {
            *v32++ = *v30++;
            --v29;
            if ( --v31 )
              continue;
          }
          if ( !v31 )
            --v32;
          break;
        }
        *v32 = 0;
        goto LABEL_50;
      }
      if ( v22 != 5 )
        goto LABEL_50;
      v23 = v21 + a2;
      v24 = (OLECHAR *)(v14 + 284);
      v25 = (OLECHAR *)(v21 + a2 + 8);
      v26 = v24;
      v27 = 2147483646;
      v28 = 128;
      while ( v27 )
      {
        if ( *v25 )
        {
          *v26++ = *v25++;
          --v27;
          if ( --v28 )
            continue;
        }
        if ( !v28 )
          --v26;
        break;
      }
      *v26 = 0;
      pclsid = 0;
      if ( CLSIDFromString(v24, &pclsid) < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
          goto LABEL_51;
        }
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids, v24);
        goto LABEL_50;
      }
      lpszProgID = 0;
      if ( ProgIDFromCLSID(&pclsid, &lpszProgID) >= 0 )
        break;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids, v24);
        goto LABEL_37;
      }
LABEL_38:
      if ( lpszProgID )
      {
        CoTaskMemFree(lpszProgID);
LABEL_50:
        v11 = WPP_GLOBAL_Control;
      }
LABEL_51:
      v10 = v20 + 1;
      if ( v10 >= v5 )
        goto LABEL_52;
    }
    StringCchPrintfW(v24, 0x80u, L"%s|%s", v23 + 8, lpszProgID);
LABEL_37:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_38;
  }
LABEL_52:
  for ( i = (_QWORD *)*a1;
        i != (_QWORD *)-1LL && (*((_DWORD *)i + 3) != *((_DWORD *)v9 + 3) || *((_DWORD *)i + 4) != *((_DWORD *)v9 + 4));
        i = (_QWORD *)*i )
  {
    ;
  }
  for ( j = i; j != (_QWORD *)-1LL; j = (_QWORD *)*j )
  {
    v36 = (_QWORD *)*j;
    if ( (_QWORD *)*j == v9 )
    {
      *j = *v36;
      operator delete(v36, (const struct std::nothrow_t *)&std::nothrow);
      j[68] = i + 1;
      return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002e2cc  push    rbx
0x14002e2ce  push    rbp
0x14002e2cf  push    rsi
0x14002e2d0  push    rdi
0x14002e2d1  push    r12
0x14002e2d3  push    r13
0x14002e2d5  push    r14
0x14002e2d7  push    r15
0x14002e2d9  sub     rsp, 58h
0x14002e2dd  mov     rax, cs:__security_cookie
0x14002e2e4  xor     rax, rsp
0x14002e2e7  mov     [rsp+98h+var_50], rax
0x14002e2ec  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x14002e2f0  mov     r13, r9
0x14002e2f3  mov     r12d, r8d
0x14002e2f6  mov     rbp, rdx
0x14002e2f9  mov     r15, rcx
0x14002e2fc  jz      short loc_14002E303
0x14002e2fe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002e303  mov     rcx, [r15]; void *
0x14002e306  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002e30a  jz      short loc_14002E320
0x14002e30c  mov     rax, [rcx]
0x14002e30f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002e316  mov     [r15], rax
0x14002e319  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002e31e  jmp     short loc_14002E303
0x14002e320  xor     r10d, r10d
0x14002e323  mov     rsi, r15
0x14002e326  mov     r14d, r10d
0x14002e329  test    r12d, r12d
0x14002e32c  jz      loc_14002E630
0x14002e332  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e339  lea     rdx, WPP_GLOBAL_Control
0x14002e340  mov     eax, r14d
0x14002e343  imul    rdi, rax, 118h
0x14002e34a  cmp     dword ptr [rdi+rbp], 8
0x14002e34e  jnz     loc_14002E683
0x14002e354  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002e35b  mov     ecx, 258h; unsigned __int64
0x14002e360  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002e365  mov     rbx, rax
0x14002e368  test    rax, rax
0x14002e36b  jz      loc_14002E64E
0x14002e371  lea     rcx, [rax+8]; void *
0x14002e375  xor     edx, edx; Val
0x14002e377  mov     r8d, 250h; Size
0x14002e37d  call    memset_0
0x14002e382  mov     rax, [rsi]
0x14002e385  mov     [rbx], rax
0x14002e388  mov     [rsi], rbx
0x14002e38b  cmp     rsi, r15
0x14002e38e  jz      short loc_14002E39B
0x14002e390  lea     rax, [rbx+8]
0x14002e394  mov     [rsi+220h], rax
0x14002e39b  mov     ecx, cs:?currNodeId@@3IA; uint currNodeId
0x14002e3a1  lea     rdx, [rbx+14h]; wchar_t *
0x14002e3a5  mov     [rbx+8], ecx
0x14002e3a8  mov     r8d, 80h; unsigned __int64
0x14002e3ae  mov     rsi, rbx
0x14002e3b1  lea     eax, [rcx+1]
0x14002e3b4  mov     cs:?currNodeId@@3IA, eax; uint currNodeId
0x14002e3ba  mov     eax, r14d
0x14002e3bd  imul    rcx, rax, 118h
0x14002e3c4  mov     ecx, [rcx+rbp+8]; unsigned int
0x14002e3c8  mov     [rbx+0Ch], ecx
0x14002e3cb  call    ?UtilGetProcessName@@YAJKPEA_W_K@Z; UtilGetProcessName(ulong,wchar_t *,unsigned __int64)
0x14002e3d0  mov     rax, [r13+0]
0x14002e3d4  xor     r10d, r10d
0x14002e3d7  mov     r9d, r10d
0x14002e3da  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002e3de  jz      short loc_14002E429
0x14002e3e0  cmp     r9d, 3
0x14002e3e4  jnb     short loc_14002E429
0x14002e3e6  mov     ecx, [rbx+0Ch]
0x14002e3e9  cmp     [rax+28h], ecx
0x14002e3ec  jnz     short loc_14002E424
0x14002e3ee  mov     ecx, [rax+2Ch]
0x14002e3f1  dec     ecx
0x14002e3f3  test    ecx, 0FFFFFFFBh
0x14002e3f9  jnz     short loc_14002E424
0x14002e3fb  mov     rcx, [rax+8]
0x14002e3ff  mov     edx, r9d
0x14002e402  add     rdx, rdx
0x14002e405  mov     r8d, r9d
0x14002e408  mov     [rbx+rdx*8+228h], rcx
0x14002e410  lea     rdx, [r8+23h]
0x14002e414  mov     ecx, [rax+2Ch]
0x14002e417  add     rdx, rdx
0x14002e41a  inc     r9d
0x14002e41d  mov     [rbx+rdx*8], ecx
0x14002e420  mov     [rax+28h], r10d
0x14002e424  mov     rax, [rax]
0x14002e427  jmp     short loc_14002E3DA
0x14002e429  mov     eax, [rdi+rbp+4]
0x14002e42d  sub     eax, 4
0x14002e430  cmp     eax, 1
0x14002e433  jbe     short loc_14002E446
0x14002e435  mov     eax, [rdi+rbp+0Ch]
0x14002e439  mov     [rbx+10h], eax
0x14002e43c  mov     eax, [rdi+rbp+14h]
0x14002e440  mov     [rbx+118h], eax
0x14002e446  cmp     dword ptr [rdi+rbp+4], 3
0x14002e44b  jz      short loc_14002E457
0x14002e44d  mov     eax, [rdi+rbp+10h]
0x14002e451  mov     [rbx+114h], eax
0x14002e457  inc     r14d
0x14002e45a  cmp     r14d, r12d
0x14002e45d  jnb     loc_14002E630
0x14002e463  mov     eax, r14d
0x14002e466  imul    rcx, rax, 118h
0x14002e46d  mov     eax, [rcx+rbp]
0x14002e470  mov     [rbx+21Ch], eax
0x14002e476  mov     edx, [rcx+rbp]
0x14002e479  lea     eax, [rdx-3]
0x14002e47c  cmp     eax, 1
0x14002e47f  jbe     loc_14002E5CF
0x14002e485  cmp     edx, 5
0x14002e488  jnz     loc_14002E616
0x14002e48e  lea     rdi, [rcx+rbp]
0x14002e492  add     rbx, 11Ch
0x14002e499  lea     r8, [rdi+8]
0x14002e49d  mov     rcx, rbx
0x14002e4a0  mov     edx, 7FFFFFFEh
0x14002e4a5  mov     eax, 80h
0x14002e4aa  test    rdx, rdx
0x14002e4ad  jz      short loc_14002E4D7
0x14002e4af  movzx   r9d, word ptr [r8]
0x14002e4b3  test    r9w, r9w
0x14002e4b7  jz      short loc_14002E4CE
0x14002e4b9  mov     [rcx], r9w
0x14002e4bd  add     r8, 2
0x14002e4c1  add     rcx, 2
0x14002e4c5  dec     rdx
0x14002e4c8  sub     rax, 1
0x14002e4cc  jnz     short loc_14002E4AA
0x14002e4ce  test    rax, rax
0x14002e4d1  jnz     short loc_14002E4D7
0x14002e4d3  sub     rcx, 2
0x14002e4d7  mov     [rcx], r10w
0x14002e4db  lea     rdx, [rsp+98h+pclsid]; pclsid
0x14002e4e0  xorps   xmm0, xmm0
0x14002e4e3  mov     rcx, rbx; lpsz
0x14002e4e6  movups  xmmword ptr [rsp+98h+pclsid.Data1], xmm0
0x14002e4eb  call    cs:__imp_CLSIDFromString
0x14002e4f2  nop     dword ptr [rax+rax+00h]
0x14002e4f7  xor     r10d, r10d
0x14002e4fa  test    eax, eax
0x14002e4fc  js      loc_14002E59C
0x14002e502  lea     rdx, [rsp+98h+lpszProgID]; lplpszProgID
0x14002e507  mov     [rsp+98h+lpszProgID], r10
0x14002e50c  lea     rcx, [rsp+98h+pclsid]; clsid
0x14002e511  call    cs:__imp_ProgIDFromCLSID
0x14002e518  nop     dword ptr [rax+rax+00h]
0x14002e51d  test    eax, eax
0x14002e51f  js      short loc_14002E545
0x14002e521  mov     rax, [rsp+98h+lpszProgID]
0x14002e526  lea     r9, [rdi+8]
0x14002e52a  lea     r8, aSS_2; "%s|%s"
0x14002e531  mov     [rsp+98h+var_78], rax
0x14002e536  mov     edx, 80h; unsigned __int64
0x14002e53b  mov     rcx, rbx; wchar_t *
0x14002e53e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14002e543  jmp     short loc_14002E576
0x14002e545  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e54c  lea     rax, WPP_GLOBAL_Control
0x14002e553  cmp     rcx, rax
0x14002e556  jz      short loc_14002E57D
0x14002e558  test    byte ptr [rcx+1Ch], 2
0x14002e55c  jz      short loc_14002E57D
0x14002e55e  mov     rcx, [rcx+10h]
0x14002e562  lea     r8, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids
0x14002e569  mov     edx, 2Ah ; '*'
0x14002e56e  mov     r9, rbx
0x14002e571  call    WPP_SF_S
0x14002e576  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e57d  mov     rax, [rsp+98h+lpszProgID]
0x14002e582  test    rax, rax
0x14002e585  jz      loc_14002E61D
0x14002e58b  mov     rcx, rax; pv
0x14002e58e  call    cs:__imp_CoTaskMemFree
0x14002e595  nop     dword ptr [rax+rax+00h]
0x14002e59a  jmp     short loc_14002E616
0x14002e59c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e5a3  lea     rdx, WPP_GLOBAL_Control
0x14002e5aa  cmp     rcx, rdx
0x14002e5ad  jz      short loc_14002E624
0x14002e5af  test    byte ptr [rcx+1Ch], 2
0x14002e5b3  jz      short loc_14002E624
0x14002e5b5  mov     rcx, [rcx+10h]
0x14002e5b9  lea     r8, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids
0x14002e5c0  mov     edx, 2Bh ; '+'
0x14002e5c5  mov     r9, rbx
0x14002e5c8  call    WPP_SF_S
0x14002e5cd  jmp     short loc_14002E616
0x14002e5cf  lea     r8, [rbp+8]
0x14002e5d3  mov     edx, 7FFFFFFEh
0x14002e5d8  add     r8, rcx
0x14002e5db  mov     eax, 80h
0x14002e5e0  add     rbx, 11Ch
0x14002e5e7  test    rdx, rdx
0x14002e5ea  jz      short loc_14002E612
0x14002e5ec  movzx   ecx, word ptr [r8]
0x14002e5f0  test    cx, cx
0x14002e5f3  jz      short loc_14002E609
0x14002e5f5  mov     [rbx], cx
0x14002e5f8  add     r8, 2
0x14002e5fc  add     rbx, 2
0x14002e600  dec     rdx
0x14002e603  sub     rax, 1
0x14002e607  jnz     short loc_14002E5E7
0x14002e609  test    rax, rax
0x14002e60c  jnz     short loc_14002E612
0x14002e60e  sub     rbx, 2
0x14002e612  mov     [rbx], r10w
0x14002e616  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e61d  lea     rdx, WPP_GLOBAL_Control
0x14002e624  inc     r14d
0x14002e627  cmp     r14d, r12d
0x14002e62a  jb      loc_14002E340
0x14002e630  mov     rbx, [r15]
0x14002e633  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14002e637  jz      short loc_14002E6AA
0x14002e639  mov     eax, [rsi+0Ch]
0x14002e63c  cmp     [rbx+0Ch], eax
0x14002e63f  jnz     short loc_14002E649
0x14002e641  mov     eax, [rsi+10h]
0x14002e644  cmp     [rbx+10h], eax
0x14002e647  jz      short loc_14002E6AA
0x14002e649  mov     rbx, [rbx]
0x14002e64c  jmp     short loc_14002E633
0x14002e64e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e655  lea     rax, WPP_GLOBAL_Control
0x14002e65c  cmp     rcx, rax
0x14002e65f  jz      short loc_14002E67C
0x14002e661  test    byte ptr [rcx+1Ch], 1
0x14002e665  jz      short loc_14002E67C
0x14002e667  mov     rcx, [rcx+10h]
0x14002e66b  lea     r8, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids
0x14002e672  mov     edx, 29h ; ')'
0x14002e677  call    WPP_SF_
0x14002e67c  mov     eax, 8007000Eh
0x14002e681  jmp     short loc_14002E6DF
0x14002e683  cmp     rcx, rdx
0x14002e686  jz      short loc_14002E6A3
0x14002e688  test    byte ptr [rcx+1Ch], 1
0x14002e68c  jz      short loc_14002E6A3
0x14002e68e  mov     rcx, [rcx+10h]
0x14002e692  lea     r8, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids
0x14002e699  mov     edx, 28h ; '('
0x14002e69e  call    WPP_SF_
0x14002e6a3  mov     eax, 80004005h
0x14002e6a8  jmp     short loc_14002E6DF
0x14002e6aa  mov     rdi, rbx
0x14002e6ad  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14002e6b1  jz      short loc_14002E6DD
0x14002e6b3  mov     rcx, [rdi]; void *
0x14002e6b6  cmp     rcx, rsi
0x14002e6b9  jz      short loc_14002E6C0
0x14002e6bb  mov     rdi, rcx
0x14002e6be  jmp     short loc_14002E6AD
0x14002e6c0  mov     rax, [rcx]
0x14002e6c3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002e6ca  mov     [rdi], rax
0x14002e6cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002e6d2  add     rbx, 8
0x14002e6d6  mov     [rdi+220h], rbx
0x14002e6dd  xor     eax, eax
0x14002e6df  mov     rcx, [rsp+98h+var_50]
0x14002e6e4  xor     rcx, rsp; StackCookie
0x14002e6e7  call    __security_check_cookie
0x14002e6ec  add     rsp, 58h
0x14002e6f0  pop     r15
0x14002e6f2  pop     r14
0x14002e6f4  pop     r13
0x14002e6f6  pop     r12
0x14002e6f8  pop     rdi
0x14002e6f9  pop     rsi
0x14002e6fa  pop     rbp
0x14002e6fb  pop     rbx
0x14002e6fc  retn
```
