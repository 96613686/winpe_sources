# CDsmDeviceTree::GetLevelSortedList(DDT_LIST_FILTER,tagPROPVARIANT *)

- ea: `0x1800088e0`
- end: `0x180008cf5`
- name: `?GetLevelSortedList@CDsmDeviceTree@@QEAAJW4DDT_LIST_FILTER@@PEAUtagPROPVARIANT@@@Z`
- size: `1045`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800191b0`

## callees

- `0x1800088e0`
- `0x18001ba48`
- `0x180022070`
- `0x180027678`
- `0x1800276d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008908`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008b93`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008908`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008b93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008a06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008a06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008cab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDsmDeviceTree::GetLevelSortedList(__int64 a1, int a2, __int64 a3)
{
  int v6; // r14d
  __int64 v7; // r15
  unsigned int i; // ecx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // r10d
  __int64 v12; // rdx
  unsigned int v13; // r9d
  __int64 v14; // rdx
  const wchar_t *v15; // rbx
  __int64 v16; // rax
  SIZE_T v17; // rsi
  const wchar_t *v18; // rcx
  size_t v19; // r8
  wchar_t *v20; // r11
  wchar_t *v21; // rdx
  _QWORD *v22; // rsi
  unsigned int v23; // r13d
  unsigned int v24; // r8d
  __int64 v25; // rdx
  __int64 v26; // rdi
  int j; // edx
  __int64 v28; // rcx
  unsigned int k; // edx
  size_t v30; // rsi
  HRESULT v31; // eax
  size_t v32; // rdx
  size_t *v33; // r8
  SIZE_T v34; // rbx
  void *v35; // rax
  size_t v37; // [rsp+20h] [rbp-88h]
  _QWORD *v38; // [rsp+40h] [rbp-68h]
  int v39; // [rsp+B0h] [rbp+8h]
  _QWORD *v42; // [rsp+C8h] [rbp+20h]

  PropVariantClear((PROPVARIANT *)a3);
  v6 = 0;
  v7 = a1 + 16;
  v38 = (_QWORD *)(a1 + 24);
  if ( *(_QWORD *)(a1 + 24) )
  {
    for ( i = 0; i < *(_DWORD *)(a1 + 32); ++i )
    {
      v9 = 8LL * i;
      if ( *(_QWORD *)(v9 + *(_QWORD *)v7) )
      {
        _mm_lfence();
        v10 = *(_QWORD *)(v9 + *(_QWORD *)v7);
        goto LABEL_7;
      }
    }
  }
  v10 = 0;
LABEL_7:
  v11 = 0;
  while ( v10 )
  {
    v12 = *(_QWORD *)(v10 + 8);
    if ( !a2 )
      goto LABEL_21;
    if ( a2 != 1 )
    {
      if ( a2 == 2 )
      {
        if ( *(_QWORD *)(v12 + 16) )
          goto LABEL_13;
      }
      else if ( a2 != 3 || !*(_BYTE *)(v12 + 32) )
      {
        goto LABEL_13;
      }
LABEL_21:
      ++v11;
      goto LABEL_13;
    }
    if ( *(_QWORD *)(v12 + 16) )
      goto LABEL_21;
LABEL_13:
    if ( *(_QWORD *)(v10 + 16) )
    {
      v10 = *(_QWORD *)(v10 + 16);
    }
    else
    {
      v13 = *(_DWORD *)(a1 + 32);
      LODWORD(v14) = *(_DWORD *)(v10 + 24) % v13;
      do
      {
        v14 = (unsigned int)(v14 + 1);
        v10 = 0;
        if ( (unsigned int)v14 >= v13 )
          break;
        v10 = *(_QWORD *)(*(_QWORD *)v7 + 8 * v14);
      }
      while ( !v10 );
    }
  }
  if ( !v11 )
    return (unsigned int)v6;
  *(_WORD *)a3 = 4127;
  *(_DWORD *)(a3 + 8) = v11;
  v34 = 8LL * v11;
  v35 = CoTaskMemAlloc(v34);
  v22 = (_QWORD *)(a3 + 16);
  v42 = v22;
  *v22 = v35;
  if ( v35 )
  {
    v6 = 0;
    memset_0(v35, 0, v34);
    v23 = 0;
    for ( j = *(_DWORD *)(a1 + 8); ; --j )
    {
      v39 = j;
      if ( !j )
        return (unsigned int)v6;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          &WPP_70ed05df840b3b152097d566b29f6267_Traceguids,
          (unsigned int)(j - 1));
        j = v39;
      }
      if ( *v38 )
      {
        for ( k = 0; k < *(_DWORD *)(v7 + 16); ++k )
        {
          v26 = *(_QWORD *)(*(_QWORD *)v7 + 8LL * k);
          if ( v26 )
            goto LABEL_37;
        }
        j = v39;
      }
      v26 = 0;
      while ( v6 >= 0 && v26 )
      {
        v28 = *(_QWORD *)(v26 + 8);
        if ( *(_DWORD *)v28 == j - 1 )
        {
          if ( a2 == 1 )
          {
            if ( *(_QWORD *)(v28 + 16) )
              goto LABEL_23;
          }
          else if ( a2 == 2 )
          {
            if ( !*(_QWORD *)(v28 + 16) )
              goto LABEL_23;
          }
          else if ( a2 == 3 && *(_BYTE *)(v28 + 32) )
          {
LABEL_23:
            v15 = *(const wchar_t **)v26;
            if ( *(_QWORD *)v26 )
            {
              v16 = -1;
              do
                ++v16;
              while ( v15[v16] );
              v17 = 2 * v16 + 2;
              v20 = (wchar_t *)CoTaskMemAlloc(v17);
              if ( !v20 )
              {
                v6 = -2147024882;
                goto LABEL_28;
              }
              v30 = v17 >> 1;
              v31 = StringValidateDestW(v18, v30, v19);
              v6 = v31;
              if ( v31 >= 0 )
              {
                v31 = StringCopyWorkerW_0(v20, v32, v33, v15, v37);
                goto LABEL_56;
              }
              if ( v30 )
              {
                *v20 = 0;
                goto LABEL_81;
              }
LABEL_56:
              v6 = v31;
              if ( v31 )
              {
LABEL_81:
                CoTaskMemFree(v20);
                v20 = 0;
                v21 = 0;
              }
              else
              {
LABEL_28:
                v21 = v20;
              }
              v22 = v42;
              if ( v6 >= 0 )
              {
LABEL_30:
                v20 = 0;
                *(_QWORD *)(*v22 + 8LL * v23++) = v21;
                v21 = 0;
              }
              if ( v21 )
                CoTaskMemFree(v20);
              goto LABEL_33;
            }
            v21 = 0;
            v6 = 0;
            goto LABEL_30;
          }
        }
LABEL_33:
        if ( *(_QWORD *)(v26 + 16) )
        {
          v26 = *(_QWORD *)(v26 + 16);
        }
        else
        {
          v24 = *(_DWORD *)(v7 + 16);
          LODWORD(v25) = *(_DWORD *)(v26 + 24) % v24;
          do
          {
            v25 = (unsigned int)(v25 + 1);
            v26 = 0;
            if ( (unsigned int)v25 >= v24 )
              break;
            v26 = *(_QWORD *)(*(_QWORD *)v7 + 8 * v25);
          }
          while ( !v26 );
        }
LABEL_37:
        j = v39;
      }
      if ( v6 < 0 )
        goto LABEL_60;
    }
  }
  v6 = -2147024882;
LABEL_60:
  PropVariantClear((PROPVARIANT *)a3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800088e0  mov     [rsp+pvar], r8
0x1800088e5  mov     [rsp+arg_8], edx
0x1800088e9  mov     [rsp+arg_0], rcx
0x1800088ee  push    rbx
0x1800088ef  push    rsi
0x1800088f0  push    rdi
0x1800088f1  push    r12
0x1800088f3  push    r13
0x1800088f5  push    r14
0x1800088f7  push    r15
0x1800088f9  sub     rsp, 70h
0x1800088fd  mov     rsi, r8
0x180008900  mov     ebx, edx
0x180008902  mov     rdi, rcx
0x180008905  mov     rcx, r8; pvar
0x180008908  call    cs:__imp_PropVariantClear
0x18000890e  xor     r12d, r12d
0x180008911  mov     r14d, r12d
0x180008914  lea     r15, [rdi+10h]
0x180008918  mov     [rsp+0A8h+var_70], r15
0x18000891d  lea     rax, [r15+8]
0x180008921  mov     [rsp+0A8h+var_68], rax
0x180008926  cmp     [rax], r12
0x180008929  jz      loc_1800089D3
0x18000892f  mov     ecx, r12d
0x180008932  mov     r8d, [r15+10h]
0x180008936  cmp     ecx, r8d
0x180008939  jnb     loc_1800089D3
0x18000893f  mov     eax, ecx
0x180008941  lea     rdx, ds:0[rax*8]
0x180008949  mov     rax, [r15]
0x18000894c  cmp     qword ptr [rdx+rax], 0
0x180008951  jnz     short loc_180008957
0x180008953  inc     ecx
0x180008955  jmp     short loc_180008936
0x180008957  lfence
0x18000895a  mov     rax, [r15]
0x18000895d  mov     r8, [rdx+rax]
0x180008961  mov     r10d, r12d
0x180008964  mov     [rsp+0A8h+var_78], r10d
0x180008969  test    r8, r8
0x18000896c  jz      short loc_1800089C2
0x18000896e  mov     rdx, [r8+8]
0x180008972  mov     ecx, ebx
0x180008974  test    ebx, ebx
0x180008976  jz      short loc_1800089CE
0x180008978  sub     ecx, 1
0x18000897b  jz      short loc_1800089C7
0x18000897d  sub     ecx, 1
0x180008980  jz      loc_180008BF1
0x180008986  cmp     ecx, 1
0x180008989  jz      loc_180008BE2
0x18000898f  mov     rax, [r8+10h]
0x180008993  test    rax, rax
0x180008996  jnz     short loc_1800089BD
0x180008998  mov     r9d, [r15+10h]
0x18000899c  xor     edx, edx
0x18000899e  mov     eax, [r8+18h]
0x1800089a2  div     r9d
0x1800089a5  inc     edx
0x1800089a7  mov     r8, r12
0x1800089aa  cmp     edx, r9d
0x1800089ad  jnb     short loc_180008964
0x1800089af  mov     rax, [r15]
0x1800089b2  mov     r8, [rax+rdx*8]
0x1800089b6  test    r8, r8
0x1800089b9  jnz     short loc_180008964
0x1800089bb  jmp     short loc_1800089A5
0x1800089bd  mov     r8, rax
0x1800089c0  jmp     short loc_180008964
0x1800089c2  jmp     loc_180008BD8
0x1800089c7  cmp     qword ptr [rdx+10h], 0
0x1800089cc  jz      short loc_18000898F
0x1800089ce  inc     r10d
0x1800089d1  jmp     short loc_18000898F
0x1800089d3  mov     r8, r12
0x1800089d6  jmp     short loc_180008961
0x1800089d8  mov     rbx, [rdi]
0x1800089db  test    rbx, rbx
0x1800089de  jz      loc_180008CBC
0x1800089e4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800089eb  nop     dword ptr [rax+rax+00h]
0x1800089f0  lea     rax, [rax+1]
0x1800089f4  cmp     word ptr [rbx+rax*2], 0
0x1800089f9  jnz     short loc_1800089F0
0x1800089fb  lea     rsi, ds:2[rax*2]
0x180008a03  mov     rcx, rsi; cb
0x180008a06  call    cs:__imp_CoTaskMemAlloc
0x180008a0c  mov     r11, rax
0x180008a0f  test    rax, rax
0x180008a12  jnz     loc_180008B23
0x180008a18  mov     r14d, 8007000Eh
0x180008a1e  mov     rdx, r11
0x180008a21  mov     rsi, [rsp+0A8h+arg_18]
0x180008a29  test    r14d, r14d
0x180008a2c  js      short loc_180008A46
0x180008a2e  mov     r11, r12
0x180008a31  mov     ecx, r13d
0x180008a34  mov     rax, [rsi]
0x180008a37  mov     [rax+rcx*8], rdx
0x180008a3b  inc     r13d
0x180008a3e  mov     [rsp+0A8h+var_78], r13d
0x180008a43  mov     rdx, r12
0x180008a46  test    rdx, rdx
0x180008a49  jz      short loc_180008A54
0x180008a4b  mov     rcx, r11; pv
0x180008a4e  call    cs:__imp_CoTaskMemFree
0x180008a54  mov     rax, [rdi+10h]
0x180008a58  test    rax, rax
0x180008a5b  jnz     short loc_180008AB8
0x180008a5d  mov     r8d, [r15+10h]
0x180008a61  xor     edx, edx
0x180008a63  mov     eax, [rdi+18h]
0x180008a66  div     r8d
0x180008a69  inc     edx
0x180008a6b  mov     rdi, r12
0x180008a6e  cmp     edx, r8d
0x180008a71  jnb     short loc_180008A7F
0x180008a73  mov     rax, [r15]
0x180008a76  mov     rdi, [rax+rdx*8]
0x180008a7a  test    rdi, rdi
0x180008a7d  jz      short loc_180008A69
0x180008a7f  mov     edx, dword ptr [rsp+0A8h+arg_0]
0x180008a86  test    r14d, r14d
0x180008a89  js      short loc_180008ABD
0x180008a8b  test    rdi, rdi
0x180008a8e  jz      short loc_180008ABD
0x180008a90  mov     rcx, [rdi+8]
0x180008a94  lea     eax, [rdx-1]
0x180008a97  cmp     [rcx], eax
0x180008a99  jnz     short loc_180008A54
0x180008a9b  mov     eax, [rsp+0A8h+arg_8]
0x180008aa2  cmp     eax, 1
0x180008aa5  jnz     loc_180008C6E
0x180008aab  cmp     qword ptr [rcx+10h], 0
0x180008ab0  jnz     loc_1800089D8
0x180008ab6  jmp     short loc_180008A54
0x180008ab8  mov     rdi, rax
0x180008abb  jmp     short loc_180008A7F
0x180008abd  lea     rax, WPP_GLOBAL_Control
0x180008ac4  test    r14d, r14d
0x180008ac7  js      loc_180008B8B
0x180008acd  dec     edx
0x180008acf  mov     dword ptr [rsp+0A8h+arg_0], edx
0x180008ad6  test    edx, edx
0x180008ad8  jz      loc_180008B99
0x180008ade  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ae5  cmp     rcx, rax
0x180008ae8  jnz     loc_180008C3F
0x180008aee  mov     rax, [rsp+0A8h+var_68]
0x180008af3  cmp     qword ptr [rax], 0
0x180008af7  jz      loc_180008BB3
0x180008afd  mov     edx, r12d
0x180008b00  mov     r8d, [r15+10h]
0x180008b04  cmp     edx, r8d
0x180008b07  jnb     loc_180008BAC
0x180008b0d  mov     ecx, edx
0x180008b0f  mov     rax, [r15]
0x180008b12  mov     rdi, [rax+rcx*8]
0x180008b16  test    rdi, rdi
0x180008b19  jnz     loc_180008A7F
0x180008b1f  inc     edx
0x180008b21  jmp     short loc_180008B04
0x180008b23  shr     rsi, 1
0x180008b26  mov     rdx, rsi; cchDest
0x180008b29  call    StringValidateDestW
0x180008b2e  mov     r14d, eax
0x180008b31  test    eax, eax
0x180008b33  js      loc_180008C9B
0x180008b39  mov     r9, rbx; pszSrc
0x180008b3c  mov     rcx, r11; pszDest
0x180008b3f  call    StringCopyWorkerW_0
0x180008b44  mov     r14d, eax
0x180008b47  test    eax, eax
0x180008b49  jz      loc_180008A1E
0x180008b4f  jmp     loc_180008CA8
0x180008b54  mov     word ptr [rsi], 101Fh
0x180008b59  mov     [rsi+8], r10d
0x180008b5d  mov     ebx, r10d
0x180008b60  shl     rbx, 3
0x180008b64  mov     rcx, rbx; cb
0x180008b67  call    cs:__imp_CoTaskMemAlloc
0x180008b6d  add     rsi, 10h
0x180008b71  mov     [rsp+0A8h+arg_18], rsi
0x180008b79  mov     [rsi], rax
0x180008b7c  test    rax, rax
0x180008b7f  jnz     loc_180008C13
0x180008b85  mov     r14d, 8007000Eh
0x180008b8b  mov     rcx, [rsp+0A8h+pvar]; pvar
0x180008b93  call    cs:__imp_PropVariantClear
0x180008b99  mov     eax, r14d
0x180008b9c  add     rsp, 70h
0x180008ba0  pop     r15
0x180008ba2  pop     r14
0x180008ba4  pop     r13
0x180008ba6  pop     r12
0x180008ba8  pop     rdi
0x180008ba9  pop     rsi
0x180008baa  pop     rbx
0x180008bab  retn
0x180008bac  mov     edx, dword ptr [rsp+0A8h+arg_0]
0x180008bb3  mov     rdi, r12
0x180008bb6  jmp     loc_180008A86
0x180008bbb  xor     r12d, r12d
0x180008bbe  mov     rdi, [rsp+0A8h+arg_0]
0x180008bc6  mov     r10d, [rsp+0A8h+var_78]
0x180008bcb  mov     r15, [rsp+0A8h+var_70]
0x180008bd0  mov     rsi, [rsp+0A8h+pvar]
0x180008bd8  test    r10d, r10d
0x180008bdb  jz      short loc_180008B99
0x180008bdd  jmp     loc_180008B54
0x180008be2  cmp     byte ptr [rdx+20h], 0
0x180008be6  jz      loc_18000898F
0x180008bec  jmp     loc_1800089CE
0x180008bf1  cmp     qword ptr [rdx+10h], 0
0x180008bf6  jnz     loc_18000898F
0x180008bfc  jmp     loc_1800089CE
0x180008c01  mov     r14d, dword ptr [rsp+0A8h+arg_18]
0x180008c09  test    r14d, r14d
0x180008c0c  jns     short loc_180008BBB
0x180008c0e  jmp     loc_180008B8B
0x180008c13  mov     [rsp+0A8h+var_58], rsi
0x180008c18  mov     r14d, r12d
0x180008c1b  mov     r8, rbx; Size
0x180008c1e  xor     edx, edx; Val
0x180008c20  mov     rcx, rax; void *
0x180008c23  call    memset_0
0x180008c28  mov     r13d, r12d
0x180008c2b  mov     [rsp+0A8h+var_78], r12d
0x180008c30  mov     edx, [rdi+8]
0x180008c33  lea     rax, WPP_GLOBAL_Control
0x180008c3a  jmp     loc_180008ACF
0x180008c3f  test    byte ptr [rcx+1Ch], 1
0x180008c43  jz      loc_180008AEE
0x180008c49  lea     r9d, [rdx-1]
0x180008c4d  mov     edx, 1Ch
0x180008c52  lea     r8, WPP_70ed05df840b3b152097d566b29f6267_Traceguids
0x180008c59  mov     rcx, [rcx+10h]
0x180008c5d  call    WPP_SF_d
0x180008c62  mov     edx, dword ptr [rsp+0A8h+arg_0]
0x180008c69  jmp     loc_180008AEE
0x180008c6e  cmp     eax, 2
0x180008c71  jnz     short loc_180008C83
0x180008c73  cmp     qword ptr [rcx+10h], 0
0x180008c78  jz      loc_1800089D8
0x180008c7e  jmp     loc_180008A54
0x180008c83  cmp     eax, 3
0x180008c86  jnz     loc_180008A54
0x180008c8c  cmp     byte ptr [rcx+20h], 0
0x180008c90  jz      loc_180008A54
0x180008c96  jmp     loc_1800089D8
0x180008c9b  test    rsi, rsi
0x180008c9e  jz      loc_180008B44
0x180008ca4  mov     [r11], r12w
0x180008ca8  mov     rcx, r11; pv
0x180008cab  call    cs:__imp_CoTaskMemFree
0x180008cb1  mov     r11, r12
0x180008cb4  mov     rdx, r12
0x180008cb7  jmp     loc_180008A21
0x180008cbc  mov     rdx, r12
0x180008cbf  mov     r14d, r12d
0x180008cc2  jmp     loc_180008A2E
0x180008cc7  xor     r12d, r12d
0x180008cca  mov     r14d, dword ptr [rsp+0A8h+arg_18]
0x180008cd2  mov     r13d, [rsp+0A8h+var_78]
0x180008cd7  mov     edx, dword ptr [rsp+0A8h+arg_0]
0x180008cde  mov     rsi, [rsp+0A8h+var_58]
0x180008ce3  mov     [rsp+0A8h+arg_18], rsi
0x180008ceb  mov     r15, [rsp+0A8h+var_70]
0x180008cf0  jmp     loc_180008ABD
```
