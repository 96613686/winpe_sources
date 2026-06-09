# bJTKeywordsToDocOptionArray

- ea: `0x180034774`
- end: `0x1800349ff`
- name: `bJTKeywordsToDocOptionArray`
- size: `651`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const wchar_t *, int, __int64, __int64, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029d7c`

## callees

- `0x180001f20`
- `0x18000289c`
- `0x180031044`
- `0x1800310e4`
- `0x180034774`
- `0x180036224`
- `0x18005d890`
- `0x18005dbe8`
- `0x18005dde4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800349cb`
- `KERNEL32!LocalFree` at `0x1800349cb`
- `KERNEL32!LocalAlloc` at `0x180034899`
- `KERNEL32!LocalAlloc` at `0x180034899`

## string_xrefs

- `0x180034845`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall bJTKeywordsToDocOptionArray(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        __int64 a5,
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
  const char *v20; // rbx
  _BYTE *v21; // rdi
  __int64 v22; // r8
  int v23; // r9d
  __int64 v24; // rax
  const char *v25; // rsi
  const char *v26; // rdx
  __int64 v27; // rax
  unsigned int *KeywordMatchFeature; // rax
  __int64 v29; // rcx
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
        v20 = (const char *)&v18[v19 + 1];
        if ( (unsigned __int64)v20 < v14 )
        {
          v21 = LocalAlloc(0x40u, 0x400u);
          if ( v21 )
          {
            if ( InitDefaultOptions(a1, v34, v22, 1)
              && (unsigned int)CombineOptionArray((__int64)a1, (__int64)v21, 0x200u, a5, (__int64)v34) )
            {
              if ( *v20 )
              {
                while ( 1 )
                {
                  v31 = 0;
                  v24 = -1;
                  v32 = 0;
                  do
                    ++v24;
                  while ( v20[v24] );
                  v25 = &v20[v24 + 1];
                  if ( (unsigned __int64)v25 >= v14 )
                    break;
                  v26 = v20;
                  v27 = -1;
                  do
                    ++v27;
                  while ( v25[v27] );
                  v20 = &v25[v27 + 1];
                  if ( (unsigned __int64)v20 >= v14 )
                    break;
                  if ( *v26 )
                  {
                    if ( *v25 )
                    {
                      KeywordMatchFeature = PInternalGetKeywordMatchFeature(v33, v26, 0, &v31);
                      if ( KeywordMatchFeature )
                      {
                        if ( KeywordMatchFeature[11] != 2
                          && v31 < 0x200
                          && PInternalGetKeywordMatchOption(v29, KeywordMatchFeature, v25, 0, &v32) )
                        {
                          v9 = 1;
                          v21[2 * v31] = v32;
                        }
                      }
                    }
                  }
                  if ( !*v20 )
                  {
                    if ( v9 )
                      SeparateOptionArray((__int64)a1, (__int64)v21, a5, v23, 0);
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
0x180034774  push    rbx
0x180034776  push    rbp
0x180034777  push    rsi
0x180034778  push    rdi
0x180034779  push    r12
0x18003477b  push    r13
0x18003477d  push    r14
0x18003477f  push    r15
0x180034781  sub     rsp, 258h
0x180034788  mov     rax, cs:__security_cookie
0x18003478f  xor     rax, rsp
0x180034792  mov     [rsp+298h+var_58], rax
0x18003479a  movzx   ebp, [rsp+298h+arg_38]
0x1800347a2  xor     r14d, r14d
0x1800347a5  movzx   r10d, [rsp+298h+arg_40]
0x1800347ae  mov     rdi, r9
0x1800347b1  mov     r9, [rsp+298h+arg_30]
0x1800347b9  mov     rsi, r8
0x1800347bc  mov     r13, [rsp+298h+arg_20]
0x1800347c4  mov     r12, rcx
0x1800347c7  mov     [rsp+298h+var_260], rdx
0x1800347cc  mov     r15d, r14d
0x1800347cf  movzx   eax, word ptr [r9+44h]
0x1800347d4  add     rax, r9
0x1800347d7  add     rbp, rax
0x1800347da  mov     rdx, rbp
0x1800347dd  sub     rdx, r10
0x1800347e0  lea     rax, [rdx+10h]
0x1800347e4  cmp     rax, rbp
0x1800347e7  ja      loc_1800349D7
0x1800347ed  cmp     dword ptr [rdx+4], 4A544D53h
0x1800347f4  jnz     loc_1800349D7
0x1800347fa  cmp     word ptr [rdx+0Ch], 10h
0x1800347ff  jb      loc_1800349D7
0x180034805  movzx   r8d, word ptr [rdx+0Eh]
0x18003480a  movzx   ecx, word ptr [rdx+0Ch]
0x18003480e  add     ecx, r8d
0x180034811  cmp     [rdx], ecx
0x180034813  jnz     loc_1800349D7
0x180034819  lea     eax, [r14+2]
0x18003481d  cmp     r8w, ax
0x180034821  jbe     loc_1800349D7
0x180034827  mov     eax, [rdx]
0x180034829  add     rax, rdx
0x18003482c  cmp     rax, rbp
0x18003482f  jnz     loc_1800349D7
0x180034835  movzx   ebx, word ptr [rdx+0Ch]
0x180034839  xor     eax, eax
0x18003483b  mov     [rbp-3], ax
0x18003483f  add     rbx, rdx
0x180034842  mov     [rbp-1], al
0x180034845  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x18003484c  mov     rcx, [rsi+28h]; unsigned __int16 *
0x180034850  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x180034855  test    al, al
0x180034857  jnz     short loc_18003485D
0x180034859  mov     rdi, [rsi+8]
0x18003485d  mov     rdx, rbx; String2
0x180034860  mov     rcx, rdi; String1
0x180034863  call    _wcsicmp
0x180034868  test    eax, eax
0x18003486a  jnz     loc_1800349D7
0x180034870  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034874  inc     rax
0x180034877  cmp     [rbx+rax*2], r14w
0x18003487c  jnz     short loc_180034874
0x18003487e  lea     rbx, [rbx+rax*2]
0x180034882  add     rbx, 2
0x180034886  cmp     rbx, rbp
0x180034889  jnb     loc_1800349D7
0x18003488f  mov     edx, 400h; uBytes
0x180034894  mov     ecx, 40h ; '@'; uFlags
0x180034899  call    cs:__imp_LocalAlloc
0x1800348a0  nop     dword ptr [rax+rax+00h]
0x1800348a5  mov     rdi, rax
0x1800348a8  test    rax, rax
0x1800348ab  jz      loc_1800349D7
0x1800348b1  mov     r9d, 1
0x1800348b7  lea     rdx, [rsp+298h+var_258]
0x1800348bc  mov     rcx, r12
0x1800348bf  call    InitDefaultOptions
0x1800348c4  test    eax, eax
0x1800348c6  jz      loc_1800349C8
0x1800348cc  lea     rax, [rsp+298h+var_258]
0x1800348d1  mov     r9, r13
0x1800348d4  mov     r8d, 200h
0x1800348da  mov     [rsp+298h+var_278], rax
0x1800348df  mov     rdx, rdi
0x1800348e2  mov     rcx, r12
0x1800348e5  call    CombineOptionArray
0x1800348ea  test    eax, eax
0x1800348ec  jz      loc_1800349C8
0x1800348f2  cmp     [rbx], r14b
0x1800348f5  jz      loc_1800349C2
0x1800348fb  mov     [rsp+298h+var_268], r15d
0x180034900  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034904  mov     [rsp+298h+var_264], r15d
0x180034909  inc     rax
0x18003490c  cmp     [rbx+rax], r15b
0x180034910  jnz     short loc_180034909
0x180034912  lea     rsi, [rbx+1]
0x180034916  add     rsi, rax
0x180034919  cmp     rsi, rbp
0x18003491c  jnb     loc_1800349C8
0x180034922  mov     rdx, rbx
0x180034925  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034929  inc     rax
0x18003492c  cmp     [rsi+rax], r15b
0x180034930  jnz     short loc_180034929
0x180034932  lea     rbx, [rax+1]
0x180034936  add     rbx, rsi
0x180034939  cmp     rbx, rbp
0x18003493c  jnb     loc_1800349C8
0x180034942  cmp     [rdx], r15b
0x180034945  jz      short loc_1800349A1
0x180034947  cmp     [rsi], r15b
0x18003494a  jz      short loc_1800349A1
0x18003494c  mov     rcx, [rsp+298h+var_260]
0x180034951  lea     r9, [rsp+298h+var_268]
0x180034956  xor     r8d, r8d
0x180034959  call    PInternalGetKeywordMatchFeature
0x18003495e  test    rax, rax
0x180034961  jz      short loc_1800349A1
0x180034963  cmp     dword ptr [rax+2Ch], 2
0x180034967  jz      short loc_1800349A1
0x180034969  cmp     [rsp+298h+var_268], 200h
0x180034971  jnb     short loc_1800349A1
0x180034973  lea     rdx, [rsp+298h+var_264]
0x180034978  xor     r9d, r9d
0x18003497b  mov     [rsp+298h+var_278], rdx
0x180034980  mov     r8, rsi
0x180034983  mov     rdx, rax
0x180034986  call    PInternalGetKeywordMatchOption
0x18003498b  test    rax, rax
0x18003498e  jz      short loc_1800349A1
0x180034990  mov     edx, [rsp+298h+var_268]
0x180034994  mov     r14d, 1
0x18003499a  mov     al, byte ptr [rsp+298h+var_264]
0x18003499e  mov     [rdi+rdx*2], al
0x1800349a1  cmp     [rbx], r15b
0x1800349a4  jnz     loc_1800348FB
0x1800349aa  test    r14d, r14d
0x1800349ad  jz      short loc_1800349C2
0x1800349af  mov     r8, r13
0x1800349b2  mov     dword ptr [rsp+298h+var_278], r15d
0x1800349b7  mov     rdx, rdi
0x1800349ba  mov     rcx, r12
0x1800349bd  call    SeparateOptionArray
0x1800349c2  mov     r15d, 1
0x1800349c8  mov     rcx, rdi; hMem
0x1800349cb  call    cs:__imp_LocalFree
0x1800349d2  nop     dword ptr [rax+rax+00h]
0x1800349d7  mov     eax, r15d
0x1800349da  mov     rcx, [rsp+298h+var_58]
0x1800349e2  xor     rcx, rsp; StackCookie
0x1800349e5  call    __security_check_cookie
0x1800349ea  add     rsp, 258h
0x1800349f1  pop     r15
0x1800349f3  pop     r14
0x1800349f5  pop     r13
0x1800349f7  pop     r12
0x1800349f9  pop     rdi
0x1800349fa  pop     rsi
0x1800349fb  pop     rbp
0x1800349fc  pop     rbx
0x1800349fd  retn
```
