# bJTKeywordsToDocOptionArray

- ea: `0x1800330fc`
- end: `0x18003337a`
- name: `bJTKeywordsToDocOptionArray`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028c30`

## callees

- `0x180001ee0`
- `0x18000283c`
- `0x18002fac0`
- `0x18002fb5c`
- `0x1800330fc`
- `0x180034afc`
- `0x18005bc24`
- `0x18005bf74`
- `0x18005c158`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18003334d`
- `KERNEL32!LocalFree` at `0x18003334d`
- `KERNEL32!LocalAlloc` at `0x180033221`
- `KERNEL32!LocalAlloc` at `0x180033221`

## string_xrefs

- `0x1800331cd`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall bJTKeywordsToDocOptionArray(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        int a5,
        __int64 a6,
        __int64 a7,
        unsigned __int16 a8,
        unsigned __int16 a9)
{
  int v9; // r14d
  unsigned int v13; // r15d
  unsigned __int64 v14; // rbp
  unsigned int *v15; // rdx
  int v16; // r8d
  __int64 v17; // rbx
  const wchar_t *v18; // rbx
  __int64 v19; // rax
  const wchar_t *v20; // rbx
  _BYTE *v21; // rdi
  __int64 v22; // r8
  int v23; // r9d
  __int64 v24; // rax
  _BYTE *v25; // rsi
  const wchar_t *v26; // rdx
  __int64 v27; // rax
  __int64 KeywordMatchFeature; // rax
  int v29; // ecx
  unsigned int v31; // [rsp+30h] [rbp-268h] BYREF
  int v32; // [rsp+34h] [rbp-264h] BYREF
  __int64 v33; // [rsp+38h] [rbp-260h]
  _BYTE v34[512]; // [rsp+40h] [rbp-258h] BYREF

  v9 = 0;
  v33 = a2;
  v13 = 0;
  v14 = a7 + *(unsigned __int16 *)(a7 + 68) + a8;
  v15 = (unsigned int *)(v14 - a9);
  if ( (unsigned __int64)(v15 + 4) <= v14 && v15[1] == 1247038803 && *((_WORD *)v15 + 6) >= 0x10u )
  {
    v16 = *((unsigned __int16 *)v15 + 7);
    if ( *v15 == v16 + *((unsigned __int16 *)v15 + 6)
      && (unsigned __int16)v16 > 2u
      && (unsigned int *)((char *)v15 + *v15) == (unsigned int *)v14 )
    {
      v17 = *((unsigned __int16 *)v15 + 6);
      *(_WORD *)(v14 - 3) = 0;
      v18 = (const wchar_t *)((char *)v15 + v17);
      *(_BYTE *)(v14 - 1) = 0;
      if ( !DoesFullPathMatchFile(*(const unsigned __int16 **)(a3 + 40), L"PrintConfig.dll") )
        a4 = *(const wchar_t **)(a3 + 8);
      if ( !wcsicmp(a4, v18) )
      {
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        v20 = &v18[v19 + 1];
        if ( (unsigned __int64)v20 < v14 )
        {
          v21 = LocalAlloc(0x40u, 0x400u);
          if ( v21 )
          {
            if ( (unsigned int)InitDefaultOptions(a1, v34, v22, 1)
              && (unsigned int)CombineOptionArray(a1, (_DWORD)v21, 512, a5, (__int64)v34) )
            {
              if ( *(_BYTE *)v20 )
              {
                while ( 1 )
                {
                  v31 = 0;
                  v24 = -1;
                  v32 = 0;
                  do
                    ++v24;
                  while ( *((_BYTE *)v20 + v24) );
                  v25 = (char *)v20 + v24 + 1;
                  if ( (unsigned __int64)v25 >= v14 )
                    break;
                  v26 = v20;
                  v27 = -1;
                  do
                    ++v27;
                  while ( v25[v27] );
                  v20 = (const wchar_t *)&v25[v27 + 1];
                  if ( (unsigned __int64)v20 >= v14 )
                    break;
                  if ( *(_BYTE *)v26 )
                  {
                    if ( *v25 )
                    {
                      KeywordMatchFeature = PInternalGetKeywordMatchFeature(v33, v26, 0, &v31);
                      if ( KeywordMatchFeature )
                      {
                        if ( *(_DWORD *)(KeywordMatchFeature + 44) != 2
                          && v31 < 0x200
                          && PInternalGetKeywordMatchOption(v29, KeywordMatchFeature, (_DWORD)v25, 0, (__int64)&v32) )
                        {
                          v9 = 1;
                          v21[2 * v31] = v32;
                        }
                      }
                    }
                  }
                  if ( !*(_BYTE *)v20 )
                  {
                    if ( v9 )
                      SeparateOptionArray(a1, (_DWORD)v21, a5, v23, 0);
                    goto LABEL_33;
                  }
                }
              }
              else
              {
LABEL_33:
                v13 = 1;
              }
            }
            LocalFree(v21);
          }
        }
      }
    }
  }
  return v13;
}

```

## disassembly

```asm
0x1800330fc  push    rbx
0x1800330fe  push    rbp
0x1800330ff  push    rsi
0x180033100  push    rdi
0x180033101  push    r12
0x180033103  push    r13
0x180033105  push    r14
0x180033107  push    r15
0x180033109  sub     rsp, 258h
0x180033110  mov     rax, cs:__security_cookie
0x180033117  xor     rax, rsp
0x18003311a  mov     [rsp+298h+var_58], rax
0x180033122  movzx   ebp, [rsp+298h+arg_38]
0x18003312a  xor     r14d, r14d
0x18003312d  movzx   r10d, [rsp+298h+arg_40]
0x180033136  mov     rdi, r9
0x180033139  mov     r9, [rsp+298h+arg_30]
0x180033141  mov     rsi, r8
0x180033144  mov     r13, [rsp+298h+arg_20]
0x18003314c  mov     r12, rcx
0x18003314f  mov     [rsp+298h+var_260], rdx
0x180033154  mov     r15d, r14d
0x180033157  movzx   eax, word ptr [r9+44h]
0x18003315c  add     rax, r9
0x18003315f  add     rbp, rax
0x180033162  mov     rdx, rbp
0x180033165  sub     rdx, r10
0x180033168  lea     rax, [rdx+10h]
0x18003316c  cmp     rax, rbp
0x18003316f  ja      loc_180033353
0x180033175  cmp     dword ptr [rdx+4], 4A544D53h
0x18003317c  jnz     loc_180033353
0x180033182  cmp     word ptr [rdx+0Ch], 10h
0x180033187  jb      loc_180033353
0x18003318d  movzx   r8d, word ptr [rdx+0Eh]
0x180033192  movzx   ecx, word ptr [rdx+0Ch]
0x180033196  add     ecx, r8d
0x180033199  cmp     [rdx], ecx
0x18003319b  jnz     loc_180033353
0x1800331a1  lea     eax, [r14+2]
0x1800331a5  cmp     r8w, ax
0x1800331a9  jbe     loc_180033353
0x1800331af  mov     eax, [rdx]
0x1800331b1  add     rax, rdx
0x1800331b4  cmp     rax, rbp
0x1800331b7  jnz     loc_180033353
0x1800331bd  movzx   ebx, word ptr [rdx+0Ch]
0x1800331c1  xor     eax, eax
0x1800331c3  mov     [rbp-3], ax
0x1800331c7  add     rbx, rdx
0x1800331ca  mov     [rbp-1], al
0x1800331cd  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x1800331d4  mov     rcx, [rsi+28h]; unsigned __int16 *
0x1800331d8  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x1800331dd  test    al, al
0x1800331df  jnz     short loc_1800331E5
0x1800331e1  mov     rdi, [rsi+8]
0x1800331e5  mov     rdx, rbx; String2
0x1800331e8  mov     rcx, rdi; String1
0x1800331eb  call    _wcsicmp
0x1800331f0  test    eax, eax
0x1800331f2  jnz     loc_180033353
0x1800331f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800331fc  inc     rax
0x1800331ff  cmp     [rbx+rax*2], r14w
0x180033204  jnz     short loc_1800331FC
0x180033206  lea     rbx, [rbx+rax*2]
0x18003320a  add     rbx, 2
0x18003320e  cmp     rbx, rbp
0x180033211  jnb     loc_180033353
0x180033217  mov     edx, 400h; uBytes
0x18003321c  mov     ecx, 40h ; '@'; uFlags
0x180033221  call    cs:__imp_LocalAlloc
0x180033227  mov     rdi, rax
0x18003322a  test    rax, rax
0x18003322d  jz      loc_180033353
0x180033233  mov     r9d, 1
0x180033239  lea     rdx, [rsp+298h+var_258]
0x18003323e  mov     rcx, r12
0x180033241  call    InitDefaultOptions
0x180033246  test    eax, eax
0x180033248  jz      loc_18003334A
0x18003324e  lea     rax, [rsp+298h+var_258]
0x180033253  mov     r9, r13
0x180033256  mov     r8d, 200h
0x18003325c  mov     [rsp+298h+var_278], rax
0x180033261  mov     rdx, rdi
0x180033264  mov     rcx, r12
0x180033267  call    CombineOptionArray
0x18003326c  test    eax, eax
0x18003326e  jz      loc_18003334A
0x180033274  cmp     [rbx], r14b
0x180033277  jz      loc_180033344
0x18003327d  mov     [rsp+298h+var_268], r15d
0x180033282  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033286  mov     [rsp+298h+var_264], r15d
0x18003328b  inc     rax
0x18003328e  cmp     [rbx+rax], r15b
0x180033292  jnz     short loc_18003328B
0x180033294  lea     rsi, [rbx+1]
0x180033298  add     rsi, rax
0x18003329b  cmp     rsi, rbp
0x18003329e  jnb     loc_18003334A
0x1800332a4  mov     rdx, rbx
0x1800332a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800332ab  inc     rax
0x1800332ae  cmp     [rsi+rax], r15b
0x1800332b2  jnz     short loc_1800332AB
0x1800332b4  lea     rbx, [rax+1]
0x1800332b8  add     rbx, rsi
0x1800332bb  cmp     rbx, rbp
0x1800332be  jnb     loc_18003334A
0x1800332c4  cmp     [rdx], r15b
0x1800332c7  jz      short loc_180033323
0x1800332c9  cmp     [rsi], r15b
0x1800332cc  jz      short loc_180033323
0x1800332ce  mov     rcx, [rsp+298h+var_260]
0x1800332d3  lea     r9, [rsp+298h+var_268]
0x1800332d8  xor     r8d, r8d
0x1800332db  call    PInternalGetKeywordMatchFeature
0x1800332e0  test    rax, rax
0x1800332e3  jz      short loc_180033323
0x1800332e5  cmp     dword ptr [rax+2Ch], 2
0x1800332e9  jz      short loc_180033323
0x1800332eb  cmp     [rsp+298h+var_268], 200h
0x1800332f3  jnb     short loc_180033323
0x1800332f5  lea     rdx, [rsp+298h+var_264]
0x1800332fa  xor     r9d, r9d
0x1800332fd  mov     [rsp+298h+var_278], rdx
0x180033302  mov     r8, rsi
0x180033305  mov     rdx, rax
0x180033308  call    PInternalGetKeywordMatchOption
0x18003330d  test    rax, rax
0x180033310  jz      short loc_180033323
0x180033312  mov     edx, [rsp+298h+var_268]
0x180033316  mov     r14d, 1
0x18003331c  mov     al, byte ptr [rsp+298h+var_264]
0x180033320  mov     [rdi+rdx*2], al
0x180033323  cmp     [rbx], r15b
0x180033326  jnz     loc_18003327D
0x18003332c  test    r14d, r14d
0x18003332f  jz      short loc_180033344
0x180033331  mov     r8, r13
0x180033334  mov     dword ptr [rsp+298h+var_278], r15d
0x180033339  mov     rdx, rdi
0x18003333c  mov     rcx, r12
0x18003333f  call    SeparateOptionArray
0x180033344  mov     r15d, 1
0x18003334a  mov     rcx, rdi; hMem
0x18003334d  call    cs:__imp_LocalFree
0x180033353  mov     eax, r15d
0x180033356  mov     rcx, [rsp+298h+var_58]
0x18003335e  xor     rcx, rsp; StackCookie
0x180033361  call    __security_check_cookie
0x180033366  add     rsp, 258h
0x18003336d  pop     r15
0x18003336f  pop     r14
0x180033371  pop     r13
0x180033373  pop     r12
0x180033375  pop     rdi
0x180033376  pop     rsi
0x180033377  pop     rbp
0x180033378  pop     rbx
0x180033379  retn
```
