# CAppInfo::LogUpgrades(CGroupPolicyRecord *)

- ea: `0x1800071e4`
- end: `0x18000737f`
- name: `?LogUpgrades@CAppInfo@@AEAAXPEAVCGroupPolicyRecord@@@Z`
- size: `411`
- prototype: `void __fastcall(CAppInfo *this, struct CGroupPolicyRecord *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180009584`

## callees

- `0x180002024`
- `0x1800071e4`
- `0x180013058`
- `0x18001b1a0`
- `0x18002a1cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000733a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007350`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000735f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007368`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000733a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007350`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000735f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007368`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007222`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007245`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007222`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007245`

## string_xrefs

- `0x1800072fe`: `ReplaceableApplications`
- `0x180007320`: `ReplaceableApplications`

## pseudocode

```c
void __fastcall CAppInfo::LogUpgrades(CAppInfo *this, struct CGroupPolicyRecord *a2)
{
  char *v4; // r15
  SIZE_T v5; // rax
  char *v6; // r14
  SIZE_T v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rdi
  unsigned int i; // ebp
  __int64 v11; // rcx
  unsigned __int16 **v12; // r12
  int v13; // eax
  int v14; // eax
  __int64 j; // rbx
  __int64 k; // rbx

  if ( *((_DWORD *)this + 26) )
  {
    v4 = 0;
    v5 = 8LL * *((unsigned int *)this + 26);
    if ( !is_mul_ok(*((unsigned int *)this + 26), 8u) )
      v5 = -1;
    v6 = (char *)LocalAlloc(0, v5);
    if ( v6 )
    {
      v7 = 8LL * *((unsigned int *)this + 26);
      if ( !is_mul_ok(*((unsigned int *)this + 26), 8u) )
        v7 = -1;
      v4 = (char *)LocalAlloc(0, v7);
      memset_0(v6, 0, 8LL * *((unsigned int *)this + 26));
      memset_0(v4, 0, 8LL * *((unsigned int *)this + 26));
      v8 = 0;
      v9 = 0;
      for ( i = 0; i < *((_DWORD *)this + 26); ++i )
      {
        v11 = *((_QWORD *)this + 14) + 32LL * i;
        if ( (*(_BYTE *)(v11 + 16) & 0x48) == 0 )
        {
          if ( (*(_BYTE *)(v11 + 16) & 1) != 0 )
          {
            v12 = (unsigned __int16 **)&v4[8 * v9];
            v9 = (unsigned int)(v9 + 1);
          }
          else
          {
            v12 = (unsigned __int16 **)&v6[8 * v8];
            v8 = (unsigned int)(v8 + 1);
          }
          GuidToString((struct _GUID *)v11, v12);
          if ( !*v12 )
            break;
        }
      }
      if ( i == *((_DWORD *)this + 26) )
      {
        v13 = CGroupPolicyRecord::SetValue(a2, L"UpgradeableApplications", (unsigned __int16 **)v6, v8);
        if ( v13 < 0 && *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xC29u, L"UpgradeableApplications", (unsigned int)v13);
        v14 = CGroupPolicyRecord::SetValue(a2, L"ReplaceableApplications", (unsigned __int16 **)v4, v9);
        if ( v14 < 0 && *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xC29u, L"ReplaceableApplications", (unsigned int)v14);
      }
      for ( j = 0; (unsigned int)j < (unsigned int)v8; j = (unsigned int)(j + 1) )
        LocalFree(*(HLOCAL *)&v6[8 * j]);
      for ( k = 0; (unsigned int)k < (unsigned int)v9; k = (unsigned int)(k + 1) )
        LocalFree(*(HLOCAL *)&v4[8 * k]);
    }
    LocalFree(v6);
    LocalFree(v4);
  }
}

```

## disassembly

```asm
0x1800071e4  push    rbx
0x1800071e6  push    rbp
0x1800071e7  push    rsi
0x1800071e8  push    rdi
0x1800071e9  push    r12
0x1800071eb  push    r13
0x1800071ed  push    r14
0x1800071ef  push    r15
0x1800071f1  sub     rsp, 28h
0x1800071f5  cmp     dword ptr [rcx+68h], 0
0x1800071f9  mov     r13, rdx
0x1800071fc  mov     rbx, rcx
0x1800071ff  jz      loc_18000736E
0x180007205  mov     r8d, [rcx+68h]
0x180007209  xor     r15d, r15d
0x18000720c  lea     edi, [r15+8]
0x180007210  mov     eax, edi
0x180007212  lea     rsi, [rdi-9]
0x180007216  mul     r8
0x180007219  cmovb   rax, rsi
0x18000721d  xor     ecx, ecx; uFlags
0x18000721f  mov     rdx, rax; uBytes
0x180007222  call    cs:__imp_LocalAlloc
0x180007228  mov     r14, rax
0x18000722b  test    rax, rax
0x18000722e  jz      loc_18000735C
0x180007234  mov     ecx, [rbx+68h]
0x180007237  mov     eax, edi
0x180007239  mul     rcx
0x18000723c  cmovb   rax, rsi
0x180007240  xor     ecx, ecx; uFlags
0x180007242  mov     rdx, rax; uBytes
0x180007245  call    cs:__imp_LocalAlloc
0x18000724b  mov     r8d, [rbx+68h]
0x18000724f  xor     edx, edx; Val
0x180007251  shl     r8, 3; Size
0x180007255  mov     rcx, r14; void *
0x180007258  mov     r15, rax
0x18000725b  call    memset_0
0x180007260  mov     r8d, [rbx+68h]
0x180007264  xor     edx, edx; Val
0x180007266  shl     r8, 3; Size
0x18000726a  mov     rcx, r15; void *
0x18000726d  call    memset_0
0x180007272  xor     esi, esi
0x180007274  xor     edi, edi
0x180007276  xor     ebp, ebp
0x180007278  cmp     [rbx+68h], esi
0x18000727b  jbe     short loc_1800072B7
0x18000727d  mov     ecx, ebp
0x18000727f  shl     rcx, 5
0x180007283  add     rcx, [rbx+70h]; struct _GUID *
0x180007287  test    byte ptr [rcx+10h], 48h
0x18000728b  jnz     short loc_1800072B0
0x18000728d  test    byte ptr [rcx+10h], 1
0x180007291  jz      short loc_18000729B
0x180007293  lea     r12, [r15+rdi*8]
0x180007297  inc     edi
0x180007299  jmp     short loc_1800072A1
0x18000729b  lea     r12, [r14+rsi*8]
0x18000729f  inc     esi
0x1800072a1  mov     rdx, r12; unsigned __int16 **
0x1800072a4  call    ?GuidToString@@YAXAEAU_GUID@@PEAPEAG@Z; GuidToString(_GUID &,ushort * *)
0x1800072a9  cmp     qword ptr [r12], 0
0x1800072ae  jz      short loc_1800072B7
0x1800072b0  inc     ebp
0x1800072b2  cmp     ebp, [rbx+68h]
0x1800072b5  jb      short loc_18000727D
0x1800072b7  cmp     ebp, [rbx+68h]
0x1800072ba  jnz     short loc_180007330
0x1800072bc  mov     r9d, esi; unsigned int
0x1800072bf  lea     rdx, aUpgradeableapp; "UpgradeableApplications"
0x1800072c6  mov     r8, r14; unsigned __int16 **
0x1800072c9  mov     rcx, r13; this
0x1800072cc  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGPEAPEAGK@Z; CGroupPolicyRecord::SetValue(ushort const *,ushort * *,ulong)
0x1800072d1  mov     ebx, 0C29h
0x1800072d6  mov     ebp, 4
0x1800072db  test    eax, eax
0x1800072dd  jns     short loc_1800072FB
0x1800072df  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x1800072e6  jz      short loc_1800072FB
0x1800072e8  mov     r9d, eax
0x1800072eb  lea     r8, aUpgradeableapp; "UpgradeableApplications"
0x1800072f2  mov     edx, ebx; unsigned int
0x1800072f4  mov     ecx, ebp; unsigned int
0x1800072f6  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800072fb  mov     r9d, edi; unsigned int
0x1800072fe  lea     rdx, aReplaceableapp; "ReplaceableApplications"
0x180007305  mov     r8, r15; unsigned __int16 **
0x180007308  mov     rcx, r13; this
0x18000730b  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGPEAPEAGK@Z; CGroupPolicyRecord::SetValue(ushort const *,ushort * *,ulong)
0x180007310  test    eax, eax
0x180007312  jns     short loc_180007330
0x180007314  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000731b  jz      short loc_180007330
0x18000731d  mov     r9d, eax
0x180007320  lea     r8, aReplaceableapp; "ReplaceableApplications"
0x180007327  mov     edx, ebx; unsigned int
0x180007329  mov     ecx, ebp; unsigned int
0x18000732b  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180007330  xor     ebx, ebx
0x180007332  test    esi, esi
0x180007334  jz      short loc_180007346
0x180007336  mov     rcx, [r14+rbx*8]; hMem
0x18000733a  call    cs:__imp_LocalFree
0x180007340  inc     ebx
0x180007342  cmp     ebx, esi
0x180007344  jb      short loc_180007336
0x180007346  xor     ebx, ebx
0x180007348  test    edi, edi
0x18000734a  jz      short loc_18000735C
0x18000734c  mov     rcx, [r15+rbx*8]; hMem
0x180007350  call    cs:__imp_LocalFree
0x180007356  inc     ebx
0x180007358  cmp     ebx, edi
0x18000735a  jb      short loc_18000734C
0x18000735c  mov     rcx, r14; hMem
0x18000735f  call    cs:__imp_LocalFree
0x180007365  mov     rcx, r15; hMem
0x180007368  call    cs:__imp_LocalFree
0x18000736e  add     rsp, 28h
0x180007372  pop     r15
0x180007374  pop     r14
0x180007376  pop     r13
0x180007378  pop     r12
0x18000737a  pop     rdi
0x18000737b  pop     rsi
0x18000737c  pop     rbp
0x18000737d  pop     rbx
0x18000737e  retn
```
