# bJTKeywordsToDocOptionArray

- ea: `0x180034208`
- end: `0x180034510`
- name: `bJTKeywordsToDocOptionArray`
- size: `776`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const wchar_t *, __int64, __int64, __int64, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034b94`

## callees

- `0x180004810`
- `0x180005020`
- `0x180005b20`
- `0x180007150`
- `0x18002d080`
- `0x180034208`
- `0x18003540c`
- `0x180036fc8`
- `0x180049d00`
- `0x18004a668`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800343c2`
- `KERNEL32!LocalFree` at `0x1800344dc`
- `KERNEL32!LocalFree` at `0x1800343c2`
- `KERNEL32!LocalFree` at `0x1800344dc`
- `KERNEL32!LocalAlloc` at `0x18003432f`
- `KERNEL32!LocalAlloc` at `0x180034359`
- `KERNEL32!LocalAlloc` at `0x18003432f`
- `KERNEL32!LocalAlloc` at `0x180034359`

## string_xrefs

- `0x1800342da`: `PrintConfig.dll`

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
  const char *v20; // rdi
  _BYTE *v21; // rsi
  HLOCAL v22; // rax
  void *v23; // rbx
  int v24; // ebp
  __int64 v25; // rax
  const char *v26; // rbx
  const char *v27; // rdx
  __int64 v28; // rax
  unsigned int *KeywordMatchFeature; // rax
  unsigned int v31; // [rsp+30h] [rbp-268h] BYREF
  unsigned int v32; // [rsp+34h] [rbp-264h] BYREF
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
            if ( *(_DWORD *)(a1 + 24) <= 0x100u )
            {
              v22 = LocalAlloc(0, 0x400u);
              v23 = v22;
              if ( v22 && (unsigned int)BinitDefaultOptionArray((__int64)v22, a1) )
              {
                v9 = 1;
                if ( (unsigned int)GPDSeparateOptionArray(a1, (__int64)v23, (__int64)v34, 0x100u, 1) )
                {
LABEL_20:
                  LocalFree(v23);
                  if ( v9 )
                  {
                    v24 = 0;
                    if ( (unsigned int)GPDCombineOptionArray(a1, (__int64)v21, 0x200u, a5, (__int64)v34) )
                    {
                      while ( *v20 )
                      {
                        v31 = 0;
                        v25 = -1;
                        v32 = 0;
                        do
                          ++v25;
                        while ( v20[v25] );
                        v26 = &v20[v25 + 1];
                        if ( (unsigned __int64)v26 >= v14 )
                          goto LABEL_38;
                        v27 = v20;
                        v28 = -1;
                        do
                          ++v28;
                        while ( v26[v28] );
                        v20 = &v26[v28 + 1];
                        if ( (unsigned __int64)v20 >= v14 )
                          goto LABEL_38;
                        if ( *v26 )
                        {
                          KeywordMatchFeature = PInternalGetKeywordMatchFeature(v33, v27, 0, &v31);
                          if ( KeywordMatchFeature )
                          {
                            if ( KeywordMatchFeature[11] != 2 && v31 < 0x200 )
                            {
                              if ( PInternalGetKeywordMatchOption(v33, KeywordMatchFeature, v26, 0, &v32) )
                              {
                                v24 = 1;
                                v21[2 * v31] = v32;
                              }
                            }
                          }
                        }
                      }
                      if ( v24 )
                        GPDSeparateOptionArray(a1, (__int64)v21, a5, 0x100u, 0);
                      v13 = 1;
                    }
                  }
                  goto LABEL_38;
                }
                v9 = 0;
              }
              WriteDbgTraceErrorGpd((__int64)"GPDInitDefaultOptions", "InitDefaultOptions: internal failure.");
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
0x180034208  push    rbx
0x18003420a  push    rbp
0x18003420b  push    rsi
0x18003420c  push    rdi
0x18003420d  push    r12
0x18003420f  push    r13
0x180034211  push    r14
0x180034213  push    r15
0x180034215  sub     rsp, 258h
0x18003421c  mov     rax, cs:__security_cookie
0x180034223  xor     rax, rsp
0x180034226  mov     [rsp+298h+var_58], rax
0x18003422e  movzx   r14d, [rsp+298h+arg_38]
0x180034237  xor     ebp, ebp
0x180034239  movzx   r10d, [rsp+298h+arg_40]
0x180034242  mov     rdi, r9
0x180034245  mov     r9, [rsp+298h+arg_30]
0x18003424d  mov     rsi, r8
0x180034250  mov     r13, [rsp+298h+arg_20]
0x180034258  mov     r15, rcx
0x18003425b  mov     [rsp+298h+var_260], rdx
0x180034260  mov     r12d, ebp
0x180034263  movzx   eax, word ptr [r9+44h]
0x180034268  add     rax, r9
0x18003426b  add     r14, rax
0x18003426e  mov     rdx, r14
0x180034271  sub     rdx, r10
0x180034274  lea     rax, [rdx+10h]
0x180034278  cmp     rax, r14
0x18003427b  ja      loc_1800344E8
0x180034281  cmp     dword ptr [rdx+4], 4A544D53h
0x180034288  jnz     loc_1800344E8
0x18003428e  cmp     word ptr [rdx+0Ch], 10h
0x180034293  jb      loc_1800344E8
0x180034299  movzx   r8d, word ptr [rdx+0Eh]
0x18003429e  movzx   ecx, word ptr [rdx+0Ch]
0x1800342a2  add     ecx, r8d
0x1800342a5  cmp     [rdx], ecx
0x1800342a7  jnz     loc_1800344E8
0x1800342ad  lea     eax, [rbp+2]
0x1800342b0  cmp     r8w, ax
0x1800342b4  jbe     loc_1800344E8
0x1800342ba  mov     eax, [rdx]
0x1800342bc  add     rax, rdx
0x1800342bf  cmp     rax, r14
0x1800342c2  jnz     loc_1800344E8
0x1800342c8  movzx   ebx, word ptr [rdx+0Ch]
0x1800342cc  xor     eax, eax
0x1800342ce  mov     [r14-3], ax
0x1800342d3  add     rbx, rdx
0x1800342d6  mov     [r14-1], al
0x1800342da  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x1800342e1  mov     rcx, [rsi+28h]; unsigned __int16 *
0x1800342e5  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x1800342ea  test    al, al
0x1800342ec  jnz     short loc_1800342F2
0x1800342ee  mov     rdi, [rsi+8]
0x1800342f2  mov     rdx, rbx; String2
0x1800342f5  mov     rcx, rdi; String1
0x1800342f8  call    _wcsicmp
0x1800342fd  test    eax, eax
0x1800342ff  jnz     loc_1800344E8
0x180034305  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034309  inc     rax
0x18003430c  cmp     [rbx+rax*2], bp
0x180034310  jnz     short loc_180034309
0x180034312  lea     rdi, [rbx+2]
0x180034316  lea     rdi, [rdi+rax*2]
0x18003431a  cmp     rdi, r14
0x18003431d  jnb     loc_1800344E8
0x180034323  mov     ebx, 400h
0x180034328  mov     ecx, 40h ; '@'; uFlags
0x18003432d  mov     edx, ebx; uBytes
0x18003432f  call    cs:__imp_LocalAlloc
0x180034336  nop     dword ptr [rax+rax+00h]
0x18003433b  mov     rsi, rax
0x18003433e  test    rax, rax
0x180034341  jz      loc_1800344E8
0x180034347  cmp     dword ptr [r15+18h], 100h
0x18003434f  ja      loc_1800344D9
0x180034355  mov     edx, ebx; uBytes
0x180034357  xor     ecx, ecx; uFlags
0x180034359  call    cs:__imp_LocalAlloc
0x180034360  nop     dword ptr [rax+rax+00h]
0x180034365  mov     rbx, rax
0x180034368  test    rax, rax
0x18003436b  jz      short loc_1800343A3
0x18003436d  mov     rdx, r15
0x180034370  mov     rcx, rax
0x180034373  call    BinitDefaultOptionArray
0x180034378  test    eax, eax
0x18003437a  jz      short loc_1800343A3
0x18003437c  mov     eax, 1
0x180034381  lea     r8, [rsp+298h+var_258]
0x180034386  mov     r9d, 100h
0x18003438c  mov     dword ptr [rsp+298h+var_278], eax
0x180034390  mov     rdx, rbx
0x180034393  mov     rcx, r15
0x180034396  mov     ebp, eax
0x180034398  call    GPDSeparateOptionArray
0x18003439d  test    eax, eax
0x18003439f  jnz     short loc_1800343BF
0x1800343a1  xor     ebp, ebp
0x1800343a3  lea     rdx, aInitdefaultopt; "InitDefaultOptions: internal failure."
0x1800343aa  lea     rcx, aGpdinitdefault; "GPDInitDefaultOptions"
0x1800343b1  call    WriteDbgTraceErrorGpd
0x1800343b6  test    rbx, rbx
0x1800343b9  jz      loc_1800344D9
0x1800343bf  mov     rcx, rbx; hMem
0x1800343c2  call    cs:__imp_LocalFree
0x1800343c9  nop     dword ptr [rax+rax+00h]
0x1800343ce  test    ebp, ebp
0x1800343d0  jz      loc_1800344D9
0x1800343d6  lea     rax, [rsp+298h+var_258]
0x1800343db  mov     r9, r13
0x1800343de  mov     r8d, 200h
0x1800343e4  mov     [rsp+298h+var_278], rax
0x1800343e9  mov     rdx, rsi
0x1800343ec  mov     rcx, r15
0x1800343ef  xor     ebp, ebp
0x1800343f1  call    GPDCombineOptionArray
0x1800343f6  xor     ecx, ecx
0x1800343f8  test    eax, eax
0x1800343fa  jz      loc_1800344D9
0x180034400  cmp     [rdi], cl
0x180034402  jz      loc_1800344B7
0x180034408  mov     [rsp+298h+var_268], ecx
0x18003440c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034410  mov     [rsp+298h+var_264], ecx
0x180034414  inc     rax
0x180034417  cmp     [rdi+rax], cl
0x18003441a  jnz     short loc_180034414
0x18003441c  lea     rbx, [rdi+1]
0x180034420  add     rbx, rax
0x180034423  cmp     rbx, r14
0x180034426  jnb     loc_1800344D9
0x18003442c  mov     rdx, rdi
0x18003442f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034433  inc     rax
0x180034436  cmp     [rbx+rax], cl
0x180034439  jnz     short loc_180034433
0x18003443b  lea     rdi, [rax+1]
0x18003443f  add     rdi, rbx
0x180034442  cmp     rdi, r14
0x180034445  jnb     loc_1800344D9
0x18003444b  cmp     [rbx], cl
0x18003444d  jz      short loc_180034400
0x18003444f  mov     rcx, [rsp+298h+var_260]
0x180034454  lea     r9, [rsp+298h+var_268]
0x180034459  xor     r8d, r8d
0x18003445c  call    PInternalGetKeywordMatchFeature
0x180034461  xor     ecx, ecx
0x180034463  test    rax, rax
0x180034466  jz      short loc_180034400
0x180034468  cmp     dword ptr [rax+2Ch], 2
0x18003446c  jz      short loc_180034400
0x18003446e  cmp     [rsp+298h+var_268], 200h
0x180034476  jnb     short loc_180034400
0x180034478  lea     rcx, [rsp+298h+var_264]
0x18003447d  xor     r9d, r9d
0x180034480  mov     [rsp+298h+var_278], rcx
0x180034485  mov     r8, rbx
0x180034488  mov     rcx, [rsp+298h+var_260]
0x18003448d  mov     rdx, rax
0x180034490  call    PInternalGetKeywordMatchOption
0x180034495  xor     ecx, ecx
0x180034497  test    rax, rax
0x18003449a  jz      loc_180034400
0x1800344a0  mov     ecx, [rsp+298h+var_268]
0x1800344a4  mov     ebp, 1
0x1800344a9  mov     al, byte ptr [rsp+298h+var_264]
0x1800344ad  mov     [rsi+rcx*2], al
0x1800344b0  xor     ecx, ecx
0x1800344b2  jmp     loc_180034400
0x1800344b7  test    ebp, ebp
0x1800344b9  jz      short loc_1800344D3
0x1800344bb  mov     dword ptr [rsp+298h+var_278], ecx
0x1800344bf  mov     r9d, 100h
0x1800344c5  mov     rcx, r15
0x1800344c8  mov     r8, r13
0x1800344cb  mov     rdx, rsi
0x1800344ce  call    GPDSeparateOptionArray
0x1800344d3  mov     r12d, 1
0x1800344d9  mov     rcx, rsi; hMem
0x1800344dc  call    cs:__imp_LocalFree
0x1800344e3  nop     dword ptr [rax+rax+00h]
0x1800344e8  mov     eax, r12d
0x1800344eb  mov     rcx, [rsp+298h+var_58]
0x1800344f3  xor     rcx, rsp; StackCookie
0x1800344f6  call    __security_check_cookie
0x1800344fb  add     rsp, 258h
0x180034502  pop     r15
0x180034504  pop     r14
0x180034506  pop     r13
0x180034508  pop     r12
0x18003450a  pop     rdi
0x18003450b  pop     rsi
0x18003450c  pop     rbp
0x18003450d  pop     rbx
0x18003450e  retn
```
