# bJTKeywordsToDocOptionArray

- ea: `0x18003388c`
- end: `0x180033b7b`
- name: `bJTKeywordsToDocOptionArray`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800341e8`

## callees

- `0x18000490c`
- `0x180005100`
- `0x180005bf0`
- `0x180007220`
- `0x18002c810`
- `0x18003388c`
- `0x180034a60`
- `0x1800365a4`
- `0x1800487e0`
- `0x180049128`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180033a3a`
- `KERNEL32!LocalFree` at `0x180033b4e`
- `KERNEL32!LocalFree` at `0x180033a3a`
- `KERNEL32!LocalFree` at `0x180033b4e`
- `KERNEL32!LocalAlloc` at `0x1800339b3`
- `KERNEL32!LocalAlloc` at `0x1800339d7`
- `KERNEL32!LocalAlloc` at `0x1800339b3`
- `KERNEL32!LocalAlloc` at `0x1800339d7`

## string_xrefs

- `0x18003395e`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall bJTKeywordsToDocOptionArray(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        unsigned __int16 a8,
        unsigned __int16 a9)
{
  int v9; // ebp
  unsigned int v13; // r12d
  unsigned __int64 v14; // r14
  unsigned int *v15; // rdx
  int v16; // r8d
  __int64 v17; // rbx
  const wchar_t *v18; // rbx
  __int64 v19; // rax
  const wchar_t *v20; // rdi
  _BYTE *v21; // rsi
  HLOCAL v22; // rax
  void *v23; // rbx
  int v24; // ebp
  __int64 v25; // rax
  _BYTE *v26; // rbx
  const wchar_t *v27; // rdx
  __int64 v28; // rax
  __int64 KeywordMatchFeature; // rax
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
            if ( *(_DWORD *)(a1 + 24) <= 0x100u )
            {
              v22 = LocalAlloc(0, 0x400u);
              v23 = v22;
              if ( v22 && (unsigned int)BinitDefaultOptionArray(v22, a1) )
              {
                v9 = 1;
                if ( (unsigned int)GPDSeparateOptionArray(a1, (_DWORD)v23, (unsigned int)v34, 256, 1) )
                {
LABEL_20:
                  LocalFree(v23);
                  if ( v9 )
                  {
                    v24 = 0;
                    if ( (unsigned int)GPDCombineOptionArray(a1, (__int64)v21, 512, a5, (__int64)v34) )
                    {
                      while ( *(_BYTE *)v20 )
                      {
                        v31 = 0;
                        v25 = -1;
                        v32 = 0;
                        do
                          ++v25;
                        while ( *((_BYTE *)v20 + v25) );
                        v26 = (char *)v20 + v25 + 1;
                        if ( (unsigned __int64)v26 >= v14 )
                          goto LABEL_38;
                        v27 = v20;
                        v28 = -1;
                        do
                          ++v28;
                        while ( v26[v28] );
                        v20 = (const wchar_t *)&v26[v28 + 1];
                        if ( (unsigned __int64)v20 >= v14 )
                          goto LABEL_38;
                        if ( *v26 )
                        {
                          KeywordMatchFeature = PInternalGetKeywordMatchFeature(v33, v27, 0, &v31);
                          if ( KeywordMatchFeature )
                          {
                            if ( *(_DWORD *)(KeywordMatchFeature + 44) != 2 && v31 < 0x200 )
                            {
                              if ( PInternalGetKeywordMatchOption(
                                     v33,
                                     KeywordMatchFeature,
                                     (_DWORD)v26,
                                     0,
                                     (__int64)&v32) )
                              {
                                v24 = 1;
                                v21[2 * v31] = v32;
                              }
                            }
                          }
                        }
                      }
                      if ( v24 )
                        GPDSeparateOptionArray(a1, (_DWORD)v21, a5, 256, 0);
                      v13 = 1;
                    }
                  }
                  goto LABEL_38;
                }
                v9 = 0;
              }
              WriteDbgTraceErrorGpd("GPDInitDefaultOptions", "InitDefaultOptions: internal failure.");
              if ( v23 )
                goto LABEL_20;
            }
LABEL_38:
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
0x18003388c  push    rbx
0x18003388e  push    rbp
0x18003388f  push    rsi
0x180033890  push    rdi
0x180033891  push    r12
0x180033893  push    r13
0x180033895  push    r14
0x180033897  push    r15
0x180033899  sub     rsp, 258h
0x1800338a0  mov     rax, cs:__security_cookie
0x1800338a7  xor     rax, rsp
0x1800338aa  mov     [rsp+298h+var_58], rax
0x1800338b2  movzx   r14d, [rsp+298h+arg_38]
0x1800338bb  xor     ebp, ebp
0x1800338bd  movzx   r10d, [rsp+298h+arg_40]
0x1800338c6  mov     rdi, r9
0x1800338c9  mov     r9, [rsp+298h+arg_30]
0x1800338d1  mov     rsi, r8
0x1800338d4  mov     r13, [rsp+298h+arg_20]
0x1800338dc  mov     r15, rcx
0x1800338df  mov     [rsp+298h+var_260], rdx
0x1800338e4  mov     r12d, ebp
0x1800338e7  movzx   eax, word ptr [r9+44h]
0x1800338ec  add     rax, r9
0x1800338ef  add     r14, rax
0x1800338f2  mov     rdx, r14
0x1800338f5  sub     rdx, r10
0x1800338f8  lea     rax, [rdx+10h]
0x1800338fc  cmp     rax, r14
0x1800338ff  ja      loc_180033B54
0x180033905  cmp     dword ptr [rdx+4], 4A544D53h
0x18003390c  jnz     loc_180033B54
0x180033912  cmp     word ptr [rdx+0Ch], 10h
0x180033917  jb      loc_180033B54
0x18003391d  movzx   r8d, word ptr [rdx+0Eh]
0x180033922  movzx   ecx, word ptr [rdx+0Ch]
0x180033926  add     ecx, r8d
0x180033929  cmp     [rdx], ecx
0x18003392b  jnz     loc_180033B54
0x180033931  lea     eax, [rbp+2]
0x180033934  cmp     r8w, ax
0x180033938  jbe     loc_180033B54
0x18003393e  mov     eax, [rdx]
0x180033940  add     rax, rdx
0x180033943  cmp     rax, r14
0x180033946  jnz     loc_180033B54
0x18003394c  movzx   ebx, word ptr [rdx+0Ch]
0x180033950  xor     eax, eax
0x180033952  mov     [r14-3], ax
0x180033957  add     rbx, rdx
0x18003395a  mov     [r14-1], al
0x18003395e  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x180033965  mov     rcx, [rsi+28h]; unsigned __int16 *
0x180033969  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x18003396e  test    al, al
0x180033970  jnz     short loc_180033976
0x180033972  mov     rdi, [rsi+8]
0x180033976  mov     rdx, rbx; String2
0x180033979  mov     rcx, rdi; String1
0x18003397c  call    _wcsicmp
0x180033981  test    eax, eax
0x180033983  jnz     loc_180033B54
0x180033989  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003398d  inc     rax
0x180033990  cmp     [rbx+rax*2], bp
0x180033994  jnz     short loc_18003398D
0x180033996  lea     rdi, [rbx+2]
0x18003399a  lea     rdi, [rdi+rax*2]
0x18003399e  cmp     rdi, r14
0x1800339a1  jnb     loc_180033B54
0x1800339a7  mov     ebx, 400h
0x1800339ac  mov     ecx, 40h ; '@'; uFlags
0x1800339b1  mov     edx, ebx; uBytes
0x1800339b3  call    cs:__imp_LocalAlloc
0x1800339b9  mov     rsi, rax
0x1800339bc  test    rax, rax
0x1800339bf  jz      loc_180033B54
0x1800339c5  cmp     dword ptr [r15+18h], 100h
0x1800339cd  ja      loc_180033B4B
0x1800339d3  mov     edx, ebx; uBytes
0x1800339d5  xor     ecx, ecx; uFlags
0x1800339d7  call    cs:__imp_LocalAlloc
0x1800339dd  mov     rbx, rax
0x1800339e0  test    rax, rax
0x1800339e3  jz      short loc_180033A1B
0x1800339e5  mov     rdx, r15
0x1800339e8  mov     rcx, rax
0x1800339eb  call    BinitDefaultOptionArray
0x1800339f0  test    eax, eax
0x1800339f2  jz      short loc_180033A1B
0x1800339f4  mov     eax, 1
0x1800339f9  lea     r8, [rsp+298h+var_258]
0x1800339fe  mov     r9d, 100h
0x180033a04  mov     dword ptr [rsp+298h+var_278], eax
0x180033a08  mov     rdx, rbx
0x180033a0b  mov     rcx, r15
0x180033a0e  mov     ebp, eax
0x180033a10  call    GPDSeparateOptionArray
0x180033a15  test    eax, eax
0x180033a17  jnz     short loc_180033A37
0x180033a19  xor     ebp, ebp
0x180033a1b  lea     rdx, aInitdefaultopt; "InitDefaultOptions: internal failure."
0x180033a22  lea     rcx, aGpdinitdefault; "GPDInitDefaultOptions"
0x180033a29  call    WriteDbgTraceErrorGpd
0x180033a2e  test    rbx, rbx
0x180033a31  jz      loc_180033B4B
0x180033a37  mov     rcx, rbx; hMem
0x180033a3a  call    cs:__imp_LocalFree
0x180033a40  test    ebp, ebp
0x180033a42  jz      loc_180033B4B
0x180033a48  lea     rax, [rsp+298h+var_258]
0x180033a4d  mov     r9, r13
0x180033a50  mov     r8d, 200h
0x180033a56  mov     [rsp+298h+var_278], rax
0x180033a5b  mov     rdx, rsi
0x180033a5e  mov     rcx, r15
0x180033a61  xor     ebp, ebp
0x180033a63  call    GPDCombineOptionArray
0x180033a68  xor     ecx, ecx
0x180033a6a  test    eax, eax
0x180033a6c  jz      loc_180033B4B
0x180033a72  cmp     [rdi], cl
0x180033a74  jz      loc_180033B29
0x180033a7a  mov     [rsp+298h+var_268], ecx
0x180033a7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033a82  mov     [rsp+298h+var_264], ecx
0x180033a86  inc     rax
0x180033a89  cmp     [rdi+rax], cl
0x180033a8c  jnz     short loc_180033A86
0x180033a8e  lea     rbx, [rdi+1]
0x180033a92  add     rbx, rax
0x180033a95  cmp     rbx, r14
0x180033a98  jnb     loc_180033B4B
0x180033a9e  mov     rdx, rdi
0x180033aa1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033aa5  inc     rax
0x180033aa8  cmp     [rbx+rax], cl
0x180033aab  jnz     short loc_180033AA5
0x180033aad  lea     rdi, [rax+1]
0x180033ab1  add     rdi, rbx
0x180033ab4  cmp     rdi, r14
0x180033ab7  jnb     loc_180033B4B
0x180033abd  cmp     [rbx], cl
0x180033abf  jz      short loc_180033A72
0x180033ac1  mov     rcx, [rsp+298h+var_260]
0x180033ac6  lea     r9, [rsp+298h+var_268]
0x180033acb  xor     r8d, r8d
0x180033ace  call    PInternalGetKeywordMatchFeature
0x180033ad3  xor     ecx, ecx
0x180033ad5  test    rax, rax
0x180033ad8  jz      short loc_180033A72
0x180033ada  cmp     dword ptr [rax+2Ch], 2
0x180033ade  jz      short loc_180033A72
0x180033ae0  cmp     [rsp+298h+var_268], 200h
0x180033ae8  jnb     short loc_180033A72
0x180033aea  lea     rcx, [rsp+298h+var_264]
0x180033aef  xor     r9d, r9d
0x180033af2  mov     [rsp+298h+var_278], rcx
0x180033af7  mov     r8, rbx
0x180033afa  mov     rcx, [rsp+298h+var_260]
0x180033aff  mov     rdx, rax
0x180033b02  call    PInternalGetKeywordMatchOption
0x180033b07  xor     ecx, ecx
0x180033b09  test    rax, rax
0x180033b0c  jz      loc_180033A72
0x180033b12  mov     ecx, [rsp+298h+var_268]
0x180033b16  mov     ebp, 1
0x180033b1b  mov     al, byte ptr [rsp+298h+var_264]
0x180033b1f  mov     [rsi+rcx*2], al
0x180033b22  xor     ecx, ecx
0x180033b24  jmp     loc_180033A72
0x180033b29  test    ebp, ebp
0x180033b2b  jz      short loc_180033B45
0x180033b2d  mov     dword ptr [rsp+298h+var_278], ecx
0x180033b31  mov     r9d, 100h
0x180033b37  mov     rcx, r15
0x180033b3a  mov     r8, r13
0x180033b3d  mov     rdx, rsi
0x180033b40  call    GPDSeparateOptionArray
0x180033b45  mov     r12d, 1
0x180033b4b  mov     rcx, rsi; hMem
0x180033b4e  call    cs:__imp_LocalFree
0x180033b54  mov     eax, r12d
0x180033b57  mov     rcx, [rsp+298h+var_58]
0x180033b5f  xor     rcx, rsp; StackCookie
0x180033b62  call    __security_check_cookie
0x180033b67  add     rsp, 258h
0x180033b6e  pop     r15
0x180033b70  pop     r14
0x180033b72  pop     r13
0x180033b74  pop     r12
0x180033b76  pop     rdi
0x180033b77  pop     rsi
0x180033b78  pop     rbp
0x180033b79  pop     rbx
0x180033b7a  retn
```
