# CWCTInfoWriter::BuildNodeList(_WAITCHAIN_NODE_INFO *,uint,utl::forward_list<FileInfo,utl::allocator<FileInfo>> &)

- ea: `0x14002c4f4`
- end: `0x14002c913`
- name: `?BuildNodeList@CWCTInfoWriter@@AEAAJPEAU_WAITCHAIN_NODE_INFO@@IAEAV?$forward_list@UFileInfo@@V?$allocator@UFileInfo@@@utl@@@utl@@@Z`
- size: `1055`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002d8f4`

## callees

- `0x140002470`
- `0x140002494`
- `0x140002728`
- `0x1400030a8`
- `0x14000b540`
- `0x14000d28c`
- `0x14001444c`
- `0x140015b40`
- `0x14002c4f4`
- `0x140030550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x14002c733`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x14002c733`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14002c713`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14002c713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002c7aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002c7aa`

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
          WPP_SF_(*((_QWORD *)v11 + 2), 40, &WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids);
        return 2147500037LL;
      }
      v13 = (char *)operator new(0x258u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      if ( !v13 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids);
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
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids, v24);
        goto LABEL_50;
      }
      lpszProgID = 0;
      if ( ProgIDFromCLSID(&pclsid, &lpszProgID) >= 0 )
        break;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids, v24);
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
0x14002c4f4  push    rbx
0x14002c4f6  push    rbp
0x14002c4f7  push    rsi
0x14002c4f8  push    rdi
0x14002c4f9  push    r12
0x14002c4fb  push    r13
0x14002c4fd  push    r14
0x14002c4ff  push    r15
0x14002c501  sub     rsp, 58h
0x14002c505  mov     rax, cs:__security_cookie
0x14002c50c  xor     rax, rsp
0x14002c50f  mov     [rsp+98h+var_50], rax
0x14002c514  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x14002c518  mov     r13, r9
0x14002c51b  mov     r12d, r8d
0x14002c51e  mov     rbp, rdx
0x14002c521  mov     r15, rcx
0x14002c524  jz      short loc_14002C52B
0x14002c526  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002c52b  mov     rcx, [r15]; void *
0x14002c52e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002c532  jz      short loc_14002C548
0x14002c534  mov     rax, [rcx]
0x14002c537  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002c53e  mov     [r15], rax
0x14002c541  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002c546  jmp     short loc_14002C52B
0x14002c548  xor     r10d, r10d
0x14002c54b  mov     rsi, r15
0x14002c54e  mov     r14d, r10d
0x14002c551  test    r12d, r12d
0x14002c554  jz      loc_14002C846
0x14002c55a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c561  lea     rdx, WPP_GLOBAL_Control
0x14002c568  mov     eax, r14d
0x14002c56b  imul    rdi, rax, 118h
0x14002c572  cmp     dword ptr [rdi+rbp], 8
0x14002c576  jnz     loc_14002C899
0x14002c57c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002c583  mov     ecx, 258h; unsigned __int64
0x14002c588  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002c58d  mov     rbx, rax
0x14002c590  test    rax, rax
0x14002c593  jz      loc_14002C864
0x14002c599  lea     rcx, [rax+8]; void *
0x14002c59d  xor     edx, edx; Val
0x14002c59f  mov     r8d, 250h; Size
0x14002c5a5  call    memset_0
0x14002c5aa  mov     rax, [rsi]
0x14002c5ad  mov     [rbx], rax
0x14002c5b0  mov     [rsi], rbx
0x14002c5b3  cmp     rsi, r15
0x14002c5b6  jz      short loc_14002C5C3
0x14002c5b8  lea     rax, [rbx+8]
0x14002c5bc  mov     [rsi+220h], rax
0x14002c5c3  mov     ecx, cs:?currNodeId@@3IA; uint currNodeId
0x14002c5c9  lea     rdx, [rbx+14h]; wchar_t *
0x14002c5cd  mov     [rbx+8], ecx
0x14002c5d0  mov     r8d, 80h; unsigned __int64
0x14002c5d6  mov     rsi, rbx
0x14002c5d9  lea     eax, [rcx+1]
0x14002c5dc  mov     cs:?currNodeId@@3IA, eax; uint currNodeId
0x14002c5e2  mov     eax, r14d
0x14002c5e5  imul    rcx, rax, 118h
0x14002c5ec  mov     ecx, [rcx+rbp+8]; unsigned int
0x14002c5f0  mov     [rbx+0Ch], ecx
0x14002c5f3  call    ?UtilGetProcessName@@YAJKPEA_W_K@Z; UtilGetProcessName(ulong,wchar_t *,unsigned __int64)
0x14002c5f8  mov     rax, [r13+0]
0x14002c5fc  xor     r10d, r10d
0x14002c5ff  mov     r9d, r10d
0x14002c602  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002c606  jz      short loc_14002C651
0x14002c608  cmp     r9d, 3
0x14002c60c  jnb     short loc_14002C651
0x14002c60e  mov     ecx, [rbx+0Ch]
0x14002c611  cmp     [rax+28h], ecx
0x14002c614  jnz     short loc_14002C64C
0x14002c616  mov     ecx, [rax+2Ch]
0x14002c619  dec     ecx
0x14002c61b  test    ecx, 0FFFFFFFBh
0x14002c621  jnz     short loc_14002C64C
0x14002c623  mov     rcx, [rax+8]
0x14002c627  mov     edx, r9d
0x14002c62a  add     rdx, rdx
0x14002c62d  mov     r8d, r9d
0x14002c630  mov     [rbx+rdx*8+228h], rcx
0x14002c638  lea     rdx, [r8+23h]
0x14002c63c  mov     ecx, [rax+2Ch]
0x14002c63f  add     rdx, rdx
0x14002c642  inc     r9d
0x14002c645  mov     [rbx+rdx*8], ecx
0x14002c648  mov     [rax+28h], r10d
0x14002c64c  mov     rax, [rax]
0x14002c64f  jmp     short loc_14002C602
0x14002c651  mov     eax, [rdi+rbp+4]
0x14002c655  sub     eax, 4
0x14002c658  cmp     eax, 1
0x14002c65b  jbe     short loc_14002C66E
0x14002c65d  mov     eax, [rdi+rbp+0Ch]
0x14002c661  mov     [rbx+10h], eax
0x14002c664  mov     eax, [rdi+rbp+14h]
0x14002c668  mov     [rbx+118h], eax
0x14002c66e  cmp     dword ptr [rdi+rbp+4], 3
0x14002c673  jz      short loc_14002C67F
0x14002c675  mov     eax, [rdi+rbp+10h]
0x14002c679  mov     [rbx+114h], eax
0x14002c67f  inc     r14d
0x14002c682  cmp     r14d, r12d
0x14002c685  jnb     loc_14002C846
0x14002c68b  mov     eax, r14d
0x14002c68e  imul    rcx, rax, 118h
0x14002c695  mov     eax, [rcx+rbp]
0x14002c698  mov     [rbx+21Ch], eax
0x14002c69e  mov     edx, [rcx+rbp]
0x14002c6a1  lea     eax, [rdx-3]
0x14002c6a4  cmp     eax, 1
0x14002c6a7  jbe     loc_14002C7E5
0x14002c6ad  cmp     edx, 5
0x14002c6b0  jnz     loc_14002C82C
0x14002c6b6  lea     rdi, [rcx+rbp]
0x14002c6ba  add     rbx, 11Ch
0x14002c6c1  lea     r8, [rdi+8]
0x14002c6c5  mov     rcx, rbx
0x14002c6c8  mov     edx, 7FFFFFFEh
0x14002c6cd  mov     eax, 80h
0x14002c6d2  test    rdx, rdx
0x14002c6d5  jz      short loc_14002C6FF
0x14002c6d7  movzx   r9d, word ptr [r8]
0x14002c6db  test    r9w, r9w
0x14002c6df  jz      short loc_14002C6F6
0x14002c6e1  mov     [rcx], r9w
0x14002c6e5  add     r8, 2
0x14002c6e9  add     rcx, 2
0x14002c6ed  dec     rdx
0x14002c6f0  sub     rax, 1
0x14002c6f4  jnz     short loc_14002C6D2
0x14002c6f6  test    rax, rax
0x14002c6f9  jnz     short loc_14002C6FF
0x14002c6fb  sub     rcx, 2
0x14002c6ff  mov     [rcx], r10w
0x14002c703  lea     rdx, [rsp+98h+pclsid]; pclsid
0x14002c708  xorps   xmm0, xmm0
0x14002c70b  mov     rcx, rbx; lpsz
0x14002c70e  movups  xmmword ptr [rsp+98h+pclsid.Data1], xmm0
0x14002c713  call    cs:__imp_CLSIDFromString
0x14002c719  xor     r10d, r10d
0x14002c71c  test    eax, eax
0x14002c71e  js      loc_14002C7B2
0x14002c724  lea     rdx, [rsp+98h+lpszProgID]; lplpszProgID
0x14002c729  mov     [rsp+98h+lpszProgID], r10
0x14002c72e  lea     rcx, [rsp+98h+pclsid]; clsid
0x14002c733  call    cs:__imp_ProgIDFromCLSID
0x14002c739  test    eax, eax
0x14002c73b  js      short loc_14002C761
0x14002c73d  mov     rax, [rsp+98h+lpszProgID]
0x14002c742  lea     r9, [rdi+8]
0x14002c746  lea     r8, aSS_2; "%s|%s"
0x14002c74d  mov     [rsp+98h+var_78], rax
0x14002c752  mov     edx, 80h; unsigned __int64
0x14002c757  mov     rcx, rbx; wchar_t *
0x14002c75a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14002c75f  jmp     short loc_14002C792
0x14002c761  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c768  lea     rax, WPP_GLOBAL_Control
0x14002c76f  cmp     rcx, rax
0x14002c772  jz      short loc_14002C799
0x14002c774  test    byte ptr [rcx+1Ch], 2
0x14002c778  jz      short loc_14002C799
0x14002c77a  mov     rcx, [rcx+10h]
0x14002c77e  lea     r8, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids
0x14002c785  mov     edx, 2Ah ; '*'
0x14002c78a  mov     r9, rbx
0x14002c78d  call    WPP_SF_S
0x14002c792  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c799  mov     rax, [rsp+98h+lpszProgID]
0x14002c79e  test    rax, rax
0x14002c7a1  jz      loc_14002C833
0x14002c7a7  mov     rcx, rax; pv
0x14002c7aa  call    cs:__imp_CoTaskMemFree
0x14002c7b0  jmp     short loc_14002C82C
0x14002c7b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c7b9  lea     rdx, WPP_GLOBAL_Control
0x14002c7c0  cmp     rcx, rdx
0x14002c7c3  jz      short loc_14002C83A
0x14002c7c5  test    byte ptr [rcx+1Ch], 2
0x14002c7c9  jz      short loc_14002C83A
0x14002c7cb  mov     rcx, [rcx+10h]
0x14002c7cf  lea     r8, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids
0x14002c7d6  mov     edx, 2Bh ; '+'
0x14002c7db  mov     r9, rbx
0x14002c7de  call    WPP_SF_S
0x14002c7e3  jmp     short loc_14002C82C
0x14002c7e5  lea     r8, [rbp+8]
0x14002c7e9  mov     edx, 7FFFFFFEh
0x14002c7ee  add     r8, rcx
0x14002c7f1  mov     eax, 80h
0x14002c7f6  add     rbx, 11Ch
0x14002c7fd  test    rdx, rdx
0x14002c800  jz      short loc_14002C828
0x14002c802  movzx   ecx, word ptr [r8]
0x14002c806  test    cx, cx
0x14002c809  jz      short loc_14002C81F
0x14002c80b  mov     [rbx], cx
0x14002c80e  add     r8, 2
0x14002c812  add     rbx, 2
0x14002c816  dec     rdx
0x14002c819  sub     rax, 1
0x14002c81d  jnz     short loc_14002C7FD
0x14002c81f  test    rax, rax
0x14002c822  jnz     short loc_14002C828
0x14002c824  sub     rbx, 2
0x14002c828  mov     [rbx], r10w
0x14002c82c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c833  lea     rdx, WPP_GLOBAL_Control
0x14002c83a  inc     r14d
0x14002c83d  cmp     r14d, r12d
0x14002c840  jb      loc_14002C568
0x14002c846  mov     rbx, [r15]
0x14002c849  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14002c84d  jz      short loc_14002C8C0
0x14002c84f  mov     eax, [rsi+0Ch]
0x14002c852  cmp     [rbx+0Ch], eax
0x14002c855  jnz     short loc_14002C85F
0x14002c857  mov     eax, [rsi+10h]
0x14002c85a  cmp     [rbx+10h], eax
0x14002c85d  jz      short loc_14002C8C0
0x14002c85f  mov     rbx, [rbx]
0x14002c862  jmp     short loc_14002C849
0x14002c864  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c86b  lea     rax, WPP_GLOBAL_Control
0x14002c872  cmp     rcx, rax
0x14002c875  jz      short loc_14002C892
0x14002c877  test    byte ptr [rcx+1Ch], 1
0x14002c87b  jz      short loc_14002C892
0x14002c87d  mov     rcx, [rcx+10h]
0x14002c881  lea     r8, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids
0x14002c888  mov     edx, 29h ; ')'
0x14002c88d  call    WPP_SF_
0x14002c892  mov     eax, 8007000Eh
0x14002c897  jmp     short loc_14002C8F5
0x14002c899  cmp     rcx, rdx
0x14002c89c  jz      short loc_14002C8B9
0x14002c89e  test    byte ptr [rcx+1Ch], 1
0x14002c8a2  jz      short loc_14002C8B9
0x14002c8a4  mov     rcx, [rcx+10h]
0x14002c8a8  lea     r8, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids
0x14002c8af  mov     edx, 28h ; '('
0x14002c8b4  call    WPP_SF_
0x14002c8b9  mov     eax, 80004005h
0x14002c8be  jmp     short loc_14002C8F5
0x14002c8c0  mov     rdi, rbx
0x14002c8c3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14002c8c7  jz      short loc_14002C8F3
0x14002c8c9  mov     rcx, [rdi]; void *
0x14002c8cc  cmp     rcx, rsi
0x14002c8cf  jz      short loc_14002C8D6
0x14002c8d1  mov     rdi, rcx
0x14002c8d4  jmp     short loc_14002C8C3
0x14002c8d6  mov     rax, [rcx]
0x14002c8d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002c8e0  mov     [rdi], rax
0x14002c8e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002c8e8  add     rbx, 8
0x14002c8ec  mov     [rdi+220h], rbx
0x14002c8f3  xor     eax, eax
0x14002c8f5  mov     rcx, [rsp+98h+var_50]
0x14002c8fa  xor     rcx, rsp; StackCookie
0x14002c8fd  call    __security_check_cookie
0x14002c902  add     rsp, 58h
0x14002c906  pop     r15
0x14002c908  pop     r14
0x14002c90a  pop     r13
0x14002c90c  pop     r12
0x14002c90e  pop     rdi
0x14002c90f  pop     rsi
0x14002c910  pop     rbp
0x14002c911  pop     rbx
0x14002c912  retn
```
