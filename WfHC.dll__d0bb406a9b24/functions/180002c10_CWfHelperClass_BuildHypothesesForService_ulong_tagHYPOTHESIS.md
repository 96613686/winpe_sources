# CWfHelperClass::BuildHypothesesForService(ulong *,tagHYPOTHESIS * *)

- ea: `0x180002c10`
- end: `0x180003166`
- name: `?BuildHypothesesForService@CWfHelperClass@@AEAAJPEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `1366`
- prototype: `__int64 __fastcall(CWfHelperClass *__hidden this, unsigned int *, struct tagHYPOTHESIS **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180004080`

## callees

- `0x180001244`
- `0x1800020a4`
- `0x18000218c`
- `0x180002c10`
- `0x1800033a0`
- `0x180007714`
- `0x180008540`
- `0x18000c57e`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180003126`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003126`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002e47`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002e47`
- `FirewallAPI!FwFree` at `0x180002ccc`
- `FirewallAPI!FwFree` at `0x180002ccc`
- `FirewallAPI!FwAlloc` at `0x180002e79`
- `FirewallAPI!FwAlloc` at `0x180002e79`
- `FirewallAPI!FWOpenPolicyStore` at `0x180002d35`
- `FirewallAPI!FWOpenPolicyStore` at `0x180002d35`
- `FirewallAPI!FWQueryFirewallRules` at `0x180002d9d`
- `FirewallAPI!FWQueryFirewallRules` at `0x180002d9d`
- `FirewallAPI!FWFreeFirewallRules` at `0x180002f81`
- `FirewallAPI!FWFreeFirewallRules` at `0x180002f81`
- `FirewallAPI!FWClosePolicyStore` at `0x180002f90`
- `FirewallAPI!FWClosePolicyStore` at `0x180002f90`

## string_xrefs

- `0x180002c78`: `serviceid`

## pseudocode

```c
__int64 __fastcall CWfHelperClass::BuildHypothesesForService(
        CWfHelperClass *this,
        unsigned int *a2,
        struct tagHYPOTHESIS **a3)
{
  __int64 v3; // r14
  unsigned int v4; // ebx
  unsigned int v5; // esi
  const wchar_t *v6; // rcx
  signed int v7; // r14d
  __int64 *v8; // rcx
  __int64 *v9; // rax
  __int64 v10; // rbx
  __int64 *v11; // rdi
  const WCHAR *v12; // r12
  __int16 v13; // si
  __int16 v14; // r15
  __int16 **v15; // rax
  unsigned int *v16; // r8
  unsigned int v17; // r8d
  int v18; // ecx
  __int16 *v19; // rax
  const WCHAR *v20; // rbx
  __int64 v21; // r10
  __int16 v22; // r11
  __int16 v23; // bx
  __int16 **v24; // rax
  unsigned int *v25; // r8
  unsigned int v26; // r8d
  int v27; // ecx
  __int16 *v28; // rax
  __int64 v29; // rcx
  _WORD *v30; // rdx
  __int64 v31; // r8
  _WORD *v32; // rax
  _WORD *v33; // rcx
  __int64 *v34; // rax
  __int64 *v35; // rax
  int v36; // ecx
  int v37; // r13d
  unsigned __int64 v38; // rbx
  __int64 v39; // rax
  bool v40; // cf
  unsigned __int64 v41; // rax
  unsigned __int64 *v42; // rax
  _QWORD *v43; // rsi
  __int64 v44; // rdi
  __int64 *v45; // rbx
  unsigned int v46; // edi
  __int64 v48; // [rsp+30h] [rbp-49h] BYREF
  __int64 *v49; // [rsp+38h] [rbp-41h] BYREF
  __int64 *v50; // [rsp+40h] [rbp-39h]
  __int128 v51; // [rsp+48h] [rbp-31h] BYREF
  __int128 v52; // [rsp+58h] [rbp-21h] BYREF
  __int64 v53; // [rsp+68h] [rbp-11h]
  __int128 v54; // [rsp+70h] [rbp-9h] BYREF
  __int64 v55; // [rsp+80h] [rbp+7h]
  unsigned __int64 *v56; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int *v57; // [rsp+E8h] [rbp+6Fh]
  struct tagHYPOTHESIS **v58; // [rsp+F0h] [rbp+77h]
  __int64 *v59; // [rsp+F8h] [rbp+7Fh] BYREF

  v58 = a3;
  v57 = a2;
  *a2 = 0;
  *a3 = 0;
  v50 = (__int64 *)&v49;
  v49 = (__int64 *)&v49;
  v3 = *((_QWORD *)this + 4);
  if ( !v3 )
    goto LABEL_6;
  v4 = 0;
  v5 = *((_DWORD *)this + 6);
  if ( !v5 )
    goto LABEL_6;
  while ( 1 )
  {
    v6 = *(const wchar_t **)(v3 + 144LL * v4);
    if ( v6 )
    {
      if ( !wcsncmp_0(v6, L"serviceid", 0xFFu) )
        break;
    }
    if ( ++v4 >= v5 )
      goto LABEL_6;
  }
  if ( *(_DWORD *)(v3 + 144LL * v4 + 8) != 10 )
  {
LABEL_6:
    v7 = -2147418113;
    goto LABEL_7;
  }
  v10 = *(_QWORD *)(v3 + 144LL * v4 + 16);
  v48 = 0;
  v52 = 0;
  v53 = 0;
  v51 = 0;
  v54 = 0;
  v55 = 0;
  v59 = 0;
  LODWORD(v56) = 0;
  if ( !v10 )
  {
    v7 = -2147024809;
    goto LABEL_7;
  }
  v7 = FWOpenPolicyStore(545, 0, 2, 1, 0, &v48);
  if ( v7 )
    goto LABEL_57;
  *(_QWORD *)&v52 = 8;
  v53 = v10;
  DWORD2(v52) = 5;
  LODWORD(v51) = 1;
  *((_QWORD *)&v51 + 1) = &v52;
  DWORD1(v54) = 1;
  *((_QWORD *)&v54 + 1) = &v51;
  LODWORD(v55) = 0x10000;
  LOWORD(v54) = 545;
  v7 = FWQueryFirewallRules(v48, &v54, 4, &v56, &v59);
  if ( v7 )
  {
LABEL_57:
    if ( v59 )
      FWFreeFirewallRules(v59);
  }
  else
  {
    v11 = v59;
    if ( v59 )
    {
      while ( 1 )
      {
        if ( v11[39] )
        {
          v12 = (const WCHAR *)v11[34];
          if ( v12 )
          {
            v13 = *((_WORD *)v11 + 24);
            v14 = 0;
            if ( v13 != 1 && v13 != 58 )
            {
              if ( *((_DWORD *)v11 + 11) == 1 )
              {
                v15 = (__int16 **)(v11 + 9);
                v16 = (unsigned int *)(v11 + 8);
              }
              else
              {
                v15 = (__int16 **)(v11 + 12);
                v16 = (unsigned int *)(v11 + 11);
              }
              v17 = *v16;
              if ( v17 )
              {
                v18 = 0;
                v19 = *v15;
                while ( *v19 != v19[1] )
                {
                  if ( ++v18 >= v17 )
                    goto LABEL_29;
                }
                v14 = *v19;
              }
            }
LABEL_29:
            v20 = (const WCHAR *)v49;
            if ( v49 == (__int64 *)&v49 )
            {
LABEL_34:
              v21 = FwAlloc(544);
              if ( !v21 )
              {
                v7 = 14;
                goto LABEL_57;
              }
              v22 = *((_WORD *)v11 + 24);
              v23 = 0;
              if ( v22 != 1 && v22 != 58 )
              {
                if ( *((_DWORD *)v11 + 11) == 1 )
                {
                  v24 = (__int16 **)(v11 + 9);
                  v25 = (unsigned int *)(v11 + 8);
                }
                else
                {
                  v24 = (__int16 **)(v11 + 12);
                  v25 = (unsigned int *)(v11 + 11);
                }
                v26 = *v25;
                if ( v26 )
                {
                  v27 = 0;
                  v28 = *v24;
                  while ( *v28 != v28[1] )
                  {
                    if ( ++v27 >= v26 )
                      goto LABEL_46;
                  }
                  v23 = *v28;
                }
              }
LABEL_46:
              v29 = 2147483646;
              v30 = (_WORD *)v11[34];
              v31 = 261;
              v32 = (_WORD *)(v21 + 16);
              do
              {
                if ( !v29 )
                  break;
                if ( !*v30 )
                  break;
                *v32++ = *v30++;
                --v29;
                --v31;
              }
              while ( v31 );
              v33 = v32 - 1;
              if ( v31 )
                v33 = v32;
              *v33 = 0;
              *(_WORD *)(v21 + 538) = v23;
              *(_WORD *)(v21 + 540) = v22;
              v34 = v50;
              if ( (__int64 **)*v50 != &v49 )
LABEL_83:
                __fastfail(3u);
              v7 = 0;
              *(_QWORD *)v21 = &v49;
              *(_QWORD *)(v21 + 8) = v34;
              *v34 = v21;
              v50 = (__int64 *)v21;
            }
            else
            {
              while ( lstrcmpiW(v12, v20 + 8) || v20[270] != v13 || v20[269] != v14 )
              {
                v20 = *(const WCHAR **)v20;
                if ( v20 == (const WCHAR *)&v49 )
                  goto LABEL_34;
              }
            }
          }
        }
        v11 = (__int64 *)*v11;
        if ( !v11 )
          goto LABEL_57;
      }
    }
  }
  if ( v48 )
    FWClosePolicyStore();
  if ( !v7 )
  {
    v7 = 0;
    v35 = v49;
    if ( v49 == (__int64 *)&v49 )
      goto LABEL_7;
    v36 = 0;
    do
    {
      v35 = (__int64 *)*v35;
      ++v36;
    }
    while ( v35 != (__int64 *)&v49 );
    v37 = 2 * v36;
    v38 = (unsigned int)(2 * v36);
    v39 = 40 * v38;
    if ( !is_mul_ok(v38, 0x28u) )
      v39 = -1;
    v40 = __CFADD__(v39, 8);
    v41 = v39 + 8;
    if ( v40 )
      v41 = -1;
    v42 = (unsigned __int64 *)operator new[](v41);
    v56 = v42;
    if ( v42 )
    {
      *v42 = v38;
      v43 = v42 + 1;
      `eh vector constructor iterator'(
        v42 + 1,
        0x28u,
        (unsigned int)v38,
        (void (*)(void *))_hypothesis_builder::_hypothesis_builder,
        (void (*)(void *))_hypothesis_builder::~_hypothesis_builder);
    }
    else
    {
      v43 = 0;
    }
    if ( !v43 )
    {
      v7 = -2147024882;
      goto LABEL_7;
    }
    v44 = 0;
    v45 = v49;
    if ( v49 == (__int64 *)&v49 )
    {
LABEL_80:
      v7 = _hypothesis_builder::AppendAndDetach(
             (_hypothesis_builder *)v43,
             v37 - 1,
             (struct _hypothesis_builder *)(v43 + 5),
             v57,
             v58);
    }
    else
    {
      while ( 1 )
      {
        v7 = CWfHelperClass::CreateAndSetAttributes(
               (CWfHelperClass *)(5 * v44),
               (struct _hypothesis_builder *)&v43[5 * v44],
               (const unsigned __int16 *)v45 + 8,
               2u,
               *((_WORD *)v45 + 270),
               *((_WORD *)v45 + 269));
        if ( v7 < 0 )
          break;
        v46 = v44 + 1;
        v7 = CWfHelperClass::CreateAndSetAttributes(
               (CWfHelperClass *)(5LL * v46),
               (struct _hypothesis_builder *)&v43[5 * v46],
               (const unsigned __int16 *)v45 + 8,
               0x17u,
               *((_WORD *)v45 + 270),
               *((_WORD *)v45 + 269));
        if ( v7 < 0 )
          break;
        v45 = (__int64 *)*v45;
        v44 = v46 + 1;
        if ( v45 == (__int64 *)&v49 )
          goto LABEL_80;
      }
    }
    `eh vector destructor iterator'(v43, 0x28u, *(v43 - 1), (void (*)(void *))_hypothesis_builder::~_hypothesis_builder);
    operator delete[](v43 - 1);
    goto LABEL_7;
  }
  FwDiagFreeAppInfoList(&v49);
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
LABEL_7:
  while ( 1 )
  {
    v8 = v49;
    if ( v49 == (__int64 *)&v49 )
      return (unsigned int)v7;
    if ( (__int64 **)v49[1] != &v49 )
      goto LABEL_83;
    v9 = (__int64 *)*v49;
    if ( *(__int64 **)(*v49 + 8) != v49 )
      goto LABEL_83;
    v49 = (__int64 *)*v49;
    v9[1] = (__int64)&v49;
    FwFree(v8);
  }
}

```

## disassembly

```asm
0x180002c10  mov     [rsp-8+arg_10], r8
0x180002c15  mov     [rsp-8+arg_8], rdx
0x180002c1a  push    rbp
0x180002c1b  push    rbx
0x180002c1c  push    rsi
0x180002c1d  push    rdi
0x180002c1e  push    r12
0x180002c20  push    r13
0x180002c22  push    r14
0x180002c24  push    r15
0x180002c26  lea     rbp, [rsp-1Fh]
0x180002c2b  sub     rsp, 98h
0x180002c32  xor     r13d, r13d
0x180002c35  mov     [rdx], r13d
0x180002c38  mov     [r8], r13
0x180002c3b  lea     rax, [rbp+57h+var_98]
0x180002c3f  mov     [rbp+57h+var_90], rax
0x180002c43  lea     rax, [rbp+57h+var_98]
0x180002c47  mov     [rbp+57h+var_98], rax
0x180002c4b  mov     r14, [rcx+20h]
0x180002c4f  test    r14, r14
0x180002c52  jz      short loc_180002C8E
0x180002c54  mov     ebx, r13d
0x180002c57  mov     esi, [rcx+18h]
0x180002c5a  test    esi, esi
0x180002c5c  jz      short loc_180002C8E
0x180002c5e  xchg    ax, ax
0x180002c60  mov     eax, ebx
0x180002c62  lea     rdi, [rax+rax*8]
0x180002c66  add     rdi, rdi
0x180002c69  mov     rcx, [r14+rdi*8]; String1
0x180002c6d  test    rcx, rcx
0x180002c70  jz      short loc_180002C88
0x180002c72  mov     r8d, 0FFh; MaxCount
0x180002c78  lea     rdx, aServiceid; "serviceid"
0x180002c7f  call    wcsncmp_0
0x180002c84  test    eax, eax
0x180002c86  jz      short loc_180002CD4
0x180002c88  inc     ebx
0x180002c8a  cmp     ebx, esi
0x180002c8c  jb      short loc_180002C60
0x180002c8e  mov     r14d, 8000FFFFh
0x180002c94  mov     rcx, [rbp+57h+var_98]
0x180002c98  lea     rax, [rbp+57h+var_98]
0x180002c9c  cmp     rcx, rax
0x180002c9f  jz      loc_18000314F
0x180002ca5  lea     rax, [rbp+57h+var_98]
0x180002ca9  cmp     [rcx+8], rax
0x180002cad  jnz     loc_180003148
0x180002cb3  mov     rax, [rcx]
0x180002cb6  cmp     [rax+8], rcx
0x180002cba  jnz     loc_180003148
0x180002cc0  mov     [rbp+57h+var_98], rax
0x180002cc4  lea     rdx, [rbp+57h+var_98]
0x180002cc8  mov     [rax+8], rdx
0x180002ccc  call    cs:__imp_FwFree
0x180002cd2  jmp     short loc_180002C94
0x180002cd4  cmp     dword ptr [r14+rdi*8+8], 0Ah
0x180002cda  jnz     short loc_180002C8E
0x180002cdc  mov     rbx, [r14+rdi*8+10h]
0x180002ce1  mov     [rbp+57h+var_A0], r13
0x180002ce5  xorps   xmm0, xmm0
0x180002ce8  xor     eax, eax
0x180002cea  movups  [rbp+57h+var_78], xmm0
0x180002cee  mov     [rbp+57h+var_68], rax
0x180002cf2  movups  [rbp+57h+var_88], xmm0
0x180002cf6  xorps   xmm1, xmm1
0x180002cf9  movups  [rbp+57h+var_60], xmm1
0x180002cfd  mov     [rbp+57h+var_50], rax
0x180002d01  mov     [rbp+57h+arg_18], r13
0x180002d05  mov     dword ptr [rbp+57h+arg_0], r13d
0x180002d09  test    rbx, rbx
0x180002d0c  jz      loc_180003132
0x180002d12  mov     edi, 221h
0x180002d17  mov     ecx, edi
0x180002d19  lea     rax, [rbp+57h+var_A0]
0x180002d1d  mov     qword ptr [rsp+0D0h+var_A8], rax
0x180002d22  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x180002d27  xor     edx, edx
0x180002d29  mov     r9d, 1
0x180002d2f  mov     r8d, 2
0x180002d35  call    cs:__imp_FWOpenPolicyStore
0x180002d3b  mov     r14d, eax
0x180002d3e  test    eax, eax
0x180002d40  jnz     loc_180002F75
0x180002d46  mov     qword ptr [rbp+57h+var_78], 8
0x180002d4e  mov     [rbp+57h+var_68], rbx
0x180002d52  mov     dword ptr [rbp+57h+var_78+8], 5
0x180002d59  mov     dword ptr [rbp+57h+var_88], 1
0x180002d60  lea     rax, [rbp+57h+var_78]
0x180002d64  mov     qword ptr [rbp+57h+var_88+8], rax
0x180002d68  mov     dword ptr [rbp+57h+var_60+4], 1
0x180002d6f  lea     rax, [rbp+57h+var_88]
0x180002d73  mov     qword ptr [rbp+57h+var_60+8], rax
0x180002d77  mov     dword ptr [rbp+57h+var_50], 10000h
0x180002d7e  mov     word ptr [rbp+57h+var_60], di
0x180002d82  mov     r8d, 4
0x180002d88  lea     rax, [rbp+57h+arg_18]
0x180002d8c  mov     [rsp+0D0h+var_B0], rax
0x180002d91  lea     r9, [rbp+57h+arg_0]
0x180002d95  lea     rdx, [rbp+57h+var_60]
0x180002d99  mov     rcx, [rbp+57h+var_A0]
0x180002d9d  call    cs:__imp_FWQueryFirewallRules
0x180002da3  mov     r14d, eax
0x180002da6  test    eax, eax
0x180002da8  jnz     loc_180002F75
0x180002dae  mov     rdi, [rbp+57h+arg_18]
0x180002db2  test    rdi, rdi
0x180002db5  jz      loc_180002F87
0x180002dbb  nop     dword ptr [rax+rax+00h]
0x180002dc0  cmp     [rdi+138h], r13
0x180002dc7  jz      loc_180002F61
0x180002dcd  mov     r12, [rdi+110h]
0x180002dd4  test    r12, r12
0x180002dd7  jz      loc_180002F61
0x180002ddd  movzx   esi, word ptr [rdi+30h]
0x180002de1  mov     r15d, r13d
0x180002de4  cmp     si, 1
0x180002de8  jz      short loc_180002E33
0x180002dea  cmp     si, 3Ah ; ':'
0x180002dee  jz      short loc_180002E33
0x180002df0  cmp     dword ptr [rdi+2Ch], 1
0x180002df4  jnz     short loc_180002E00
0x180002df6  lea     rax, [rdi+48h]
0x180002dfa  lea     r8, [rdi+40h]
0x180002dfe  jmp     short loc_180002E08
0x180002e00  lea     rax, [rdi+60h]
0x180002e04  lea     r8, [rdi+58h]
0x180002e08  mov     r8d, [r8]
0x180002e0b  test    r8d, r8d
0x180002e0e  jz      short loc_180002E33
0x180002e10  mov     ecx, r13d
0x180002e13  mov     rax, [rax]
0x180002e16  movzx   r9d, word ptr [rax+2]
0x180002e1b  movzx   edx, word ptr [rax]
0x180002e1e  xchg    ax, ax
0x180002e20  cmp     dx, r9w
0x180002e24  jz      short loc_180002E2F
0x180002e26  inc     ecx
0x180002e28  cmp     ecx, r8d
0x180002e2b  jb      short loc_180002E20
0x180002e2d  jmp     short loc_180002E33
0x180002e2f  movzx   r15d, dx
0x180002e33  mov     rbx, [rbp+57h+var_98]
0x180002e37  lea     rax, [rbp+57h+var_98]
0x180002e3b  cmp     rbx, rax
0x180002e3e  jz      short loc_180002E74
0x180002e40  lea     rdx, [rbx+10h]; lpString2
0x180002e44  mov     rcx, r12; lpString1
0x180002e47  call    cs:__imp_lstrcmpiW
0x180002e4d  test    eax, eax
0x180002e4f  jnz     short loc_180002E68
0x180002e51  cmp     [rbx+21Ch], si
0x180002e58  jnz     short loc_180002E68
0x180002e5a  cmp     [rbx+21Ah], r15w
0x180002e62  jz      loc_180002F61
0x180002e68  mov     rbx, [rbx]
0x180002e6b  lea     rax, [rbp+57h+var_98]
0x180002e6f  cmp     rbx, rax
0x180002e72  jnz     short loc_180002E40
0x180002e74  mov     ecx, 220h
0x180002e79  call    cs:__imp_FwAlloc
0x180002e7f  mov     r10, rax
0x180002e82  test    rax, rax
0x180002e85  jz      loc_180002F6F
0x180002e8b  movzx   r11d, word ptr [rdi+30h]
0x180002e90  mov     ebx, r13d
0x180002e93  cmp     r11w, 1
0x180002e98  jz      short loc_180002EE2
0x180002e9a  cmp     r11w, 3Ah ; ':'
0x180002e9f  jz      short loc_180002EE2
0x180002ea1  cmp     dword ptr [rdi+2Ch], 1
0x180002ea5  jnz     short loc_180002EB1
0x180002ea7  lea     rax, [rdi+48h]
0x180002eab  lea     r8, [rdi+40h]
0x180002eaf  jmp     short loc_180002EB9
0x180002eb1  lea     rax, [rdi+60h]
0x180002eb5  lea     r8, [rdi+58h]
0x180002eb9  mov     r8d, [r8]
0x180002ebc  test    r8d, r8d
0x180002ebf  jz      short loc_180002EE2
0x180002ec1  mov     ecx, r13d
0x180002ec4  mov     rax, [rax]
0x180002ec7  movzx   r9d, word ptr [rax+2]
0x180002ecc  movzx   edx, word ptr [rax]
0x180002ecf  nop
0x180002ed0  cmp     dx, r9w
0x180002ed4  jz      short loc_180002EDF
0x180002ed6  inc     ecx
0x180002ed8  cmp     ecx, r8d
0x180002edb  jb      short loc_180002ED0
0x180002edd  jmp     short loc_180002EE2
0x180002edf  movzx   ebx, dx
0x180002ee2  mov     ecx, 7FFFFFFEh
0x180002ee7  mov     rdx, [rdi+110h]
0x180002eee  mov     r8d, 105h
0x180002ef4  lea     rax, [r10+10h]
0x180002ef8  test    rcx, rcx
0x180002efb  jz      short loc_180002F1C
0x180002efd  movzx   r9d, word ptr [rdx]
0x180002f01  test    r9w, r9w
0x180002f05  jz      short loc_180002F1C
0x180002f07  mov     [rax], r9w
0x180002f0b  add     rax, 2
0x180002f0f  add     rdx, 2
0x180002f13  dec     rcx
0x180002f16  sub     r8, 1
0x180002f1a  jnz     short loc_180002EF8
0x180002f1c  lea     rcx, [rax-2]
0x180002f20  test    r8, r8
0x180002f23  cmovnz  rcx, rax
0x180002f27  mov     [rcx], r13w
0x180002f2b  mov     [r10+21Ah], bx
0x180002f33  mov     [r10+21Ch], r11w
0x180002f3b  mov     rax, [rbp+57h+var_90]
0x180002f3f  lea     rcx, [rbp+57h+var_98]
0x180002f43  cmp     [rax], rcx
0x180002f46  jnz     loc_180003148
0x180002f4c  mov     r14d, r13d
0x180002f4f  lea     rcx, [rbp+57h+var_98]
0x180002f53  mov     [r10], rcx
0x180002f56  mov     [r10+8], rax
0x180002f5a  mov     [rax], r10
0x180002f5d  mov     [rbp+57h+var_90], r10
0x180002f61  mov     rdi, [rdi]
0x180002f64  test    rdi, rdi
0x180002f67  jnz     loc_180002DC0
0x180002f6d  jmp     short loc_180002F75
0x180002f6f  mov     r14d, 0Eh
0x180002f75  mov     rdi, [rbp+57h+arg_18]
0x180002f79  test    rdi, rdi
0x180002f7c  jz      short loc_180002F87
0x180002f7e  mov     rcx, rdi
0x180002f81  call    cs:__imp_FWFreeFirewallRules
0x180002f87  mov     rcx, [rbp+57h+var_A0]
0x180002f8b  test    rcx, rcx
0x180002f8e  jz      short loc_180002F96
0x180002f90  call    cs:__imp_FWClosePolicyStore
0x180002f96  lea     rcx, [rbp+57h+var_98]
0x180002f9a  test    r14d, r14d
0x180002f9d  jz      short loc_180002FBD
0x180002f9f  call    FwDiagFreeAppInfoList
0x180002fa4  test    r14d, r14d
0x180002fa7  jle     loc_180002C94
0x180002fad  movzx   r14d, r14w
0x180002fb1  or      r14d, 80070000h
0x180002fb8  jmp     loc_180002C94
0x180002fbd  mov     r14d, r13d
0x180002fc0  mov     rax, [rbp+57h+var_98]
0x180002fc4  cmp     rax, rcx
0x180002fc7  jz      loc_180002C94
0x180002fcd  mov     ecx, r13d
0x180002fd0  lea     rdx, [rbp+57h+var_98]
0x180002fd4  cmp     rax, rdx
0x180002fd7  jz      short loc_180002FEE
0x180002fd9  nop     dword ptr [rax+00000000h]
0x180002fe0  mov     rax, [rax]
0x180002fe3  inc     ecx
0x180002fe5  lea     rdx, [rbp+57h+var_98]
0x180002fe9  cmp     rax, rdx
0x180002fec  jnz     short loc_180002FE0
0x180002fee  lea     r13d, [rcx+rcx]
0x180002ff2  mov     ebx, r13d
0x180002ff5  mov     eax, 28h ; '('
0x180002ffa  mul     rbx
0x180002ffd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003004  cmovb   rax, rcx
0x180003008  add     rax, 8
0x18000300c  cmovb   rax, rcx
0x180003010  mov     rcx, rax; unsigned __int64
0x180003013  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003018  mov     [rbp+57h+arg_0], rax
0x18000301c  lea     r12, ??1_hypothesis_builder@@QEAA@XZ; _hypothesis_builder::~_hypothesis_builder(void)
0x180003023  test    rax, rax
0x180003026  jz      short loc_18000304D
0x180003028  mov     [rax], rbx
0x18000302b  lea     rsi, [rax+8]
0x18000302f  mov     [rsp+0D0h+var_B0], r12; void (*)(void *)
0x180003034  lea     r9, ??0_hypothesis_builder@@QEAA@XZ; void (*)(void *)
0x18000303b  mov     r8d, ebx; unsigned __int64
0x18000303e  mov     edx, 28h ; '('; unsigned __int64
0x180003043  mov     rcx, rsi; void *
0x180003046  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000304b  jmp     short loc_18000304F
0x18000304d  xor     esi, esi
0x18000304f  test    rsi, rsi
0x180003052  jnz     short loc_18000305F
0x180003054  mov     r14d, 8007000Eh
0x18000305a  jmp     loc_180002C94
0x18000305f  xor     edi, edi
0x180003061  mov     rbx, [rbp+57h+var_98]
0x180003065  lea     rax, [rbp+57h+var_98]
0x180003069  cmp     rbx, rax
0x18000306c  jz      loc_1800030EE
0x180003072  mov     r9d, 2; unsigned __int16
0x180003078  lea     rcx, [rdi+rdi*4]; this
0x18000307c  lea     rdx, [rsi+rcx*8]; struct _hypothesis_builder *
0x180003080  movzx   eax, word ptr [rbx+21Ah]
0x180003087  mov     [rsp+0D0h+var_A8], ax; unsigned __int16
0x18000308c  movzx   eax, word ptr [rbx+21Ch]
  ... truncated ...
```
