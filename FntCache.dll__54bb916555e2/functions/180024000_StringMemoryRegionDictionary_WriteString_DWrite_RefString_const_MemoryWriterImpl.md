# StringMemoryRegionDictionary::WriteString(DWrite::RefString const &,MemoryWriterImpl &)

- ea: `0x180024000`
- end: `0x1800242c7`
- name: `?WriteString@StringMemoryRegionDictionary@@IEAAIAEBVRefString@DWrite@@AEAVMemoryWriterImpl@@@Z`
- size: `711`
- prototype: `unsigned int __fastcall(StringMemoryRegionDictionary *__hidden this, const struct DWrite::RefString *, struct MemoryWriterImpl *)`
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x180021fe0`
- `0x180022400`
- `0x1800246a0`
- `0x1800246cc`
- `0x1800268c0`

## callees

- `0x180013ad0`
- `0x180024000`
- `0x1800242d0`
- `0x18004d664`
- `0x18009c0e0`
- `0x18009e420`
- `0x1800aaa58`
- `0x1800aaf88`
- `0x1800ab0aa`
- `0x1800ab168`
- `0x1800ab180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180024219`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180024250`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002425e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180024219`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180024250`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002425e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StringMemoryRegionDictionary::WriteString(
        StringMemoryRegionDictionary *this,
        void **a2,
        struct MemoryWriterImpl *a3)
{
  StringMemoryRegionDictionary *v5; // r12
  __int64 **v6; // r14
  __int64 *v7; // rdi
  __int64 *v8; // rbx
  size_t v9; // rsi
  __int64 v10; // rcx
  size_t v11; // rbp
  size_t v12; // r8
  int v13; // eax
  __int64 *v14; // rax
  __int64 v15; // rdx
  size_t v16; // rbx
  size_t v17; // rsi
  size_t v18; // r8
  int v19; // eax
  __int64 v20; // rbx
  char *v21; // r9
  __int64 v22; // r8
  const char *v23; // rdx
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rbx
  unsigned __int64 v26; // rdi
  _QWORD *v27; // rcx
  void *v28; // rcx
  unsigned int v30; // r10d
  unsigned int v31; // r10d
  char *v32; // rsi
  unsigned __int64 v33; // r14
  char *v34; // rbp
  unsigned __int64 v35; // r12
  void *Block; // [rsp+20h] [rbp-68h] BYREF
  int v37; // [rsp+28h] [rbp-60h]
  char v38[12]; // [rsp+30h] [rbp-58h] BYREF
  int v39; // [rsp+3Ch] [rbp-4Ch]
  StringMemoryRegionDictionary *v40; // [rsp+90h] [rbp+8h]
  _QWORD *v41; // [rsp+A8h] [rbp+20h]

  v40 = this;
  v5 = this;
  v6 = *(__int64 ***)this;
  if ( !*(_QWORD *)this )
  {
    v41 = operator new(0x10u);
    *v41 = 0;
    v41[1] = 0;
    std::_Tree<std::_Tset_traits<FontFeatureCoverageRegion::ScriptLanguageFeature,std::less<FontFeatureCoverageRegion::ScriptLanguageFeature>,std::allocator<FontFeatureCoverageRegion::ScriptLanguageFeature>,0>>::_Alloc_sentinel_and_proxy(v41);
    *(_QWORD *)v5 = v41;
    goto LABEL_18;
  }
  v7 = *v6;
  v8 = (__int64 *)(*v6)[1];
  v39 = 0;
  if ( !*((_BYTE *)v8 + 25) )
  {
    while ( 1 )
    {
      v9 = *((unsigned int *)*a2 + 1);
      v10 = v8[4];
      v11 = *(unsigned int *)(v10 + 4);
      v12 = v9;
      if ( v9 >= v11 )
        v12 = (unsigned int)v11;
      v13 = wmemcmp((const wchar_t *)(v10 + 8), (const wchar_t *)*a2 + 4, v12);
      if ( v13 )
      {
        if ( v13 >= 0 )
          goto LABEL_21;
      }
      else if ( v11 >= v9 )
      {
LABEL_21:
        v7 = v8;
        v8 = (__int64 *)*v8;
        goto LABEL_8;
      }
      v8 = (__int64 *)v8[2];
LABEL_8:
      if ( *((_BYTE *)v8 + 25) )
      {
        v14 = *v6;
        goto LABEL_10;
      }
    }
  }
  v14 = v7;
LABEL_10:
  if ( !*((_BYTE *)v7 + 25) )
  {
    v15 = v7[4];
    v16 = *(unsigned int *)(v15 + 4);
    v17 = *((unsigned int *)*a2 + 1);
    v18 = v16;
    if ( v16 >= v17 )
      v18 = (unsigned int)v17;
    v19 = wmemcmp((const wchar_t *)*a2 + 4, (const wchar_t *)(v15 + 8), v18);
    if ( v19 )
    {
      if ( v19 >= 0 )
        goto LABEL_15;
    }
    else if ( v17 >= v16 )
    {
      goto LABEL_15;
    }
    v14 = *v6;
  }
  v7 = v14;
LABEL_15:
  LODWORD(v20) = -1;
  if ( v7 != *v6 )
    LODWORD(v20) = *((_DWORD *)v7 + 10);
  if ( (_DWORD)v20 == -1 )
  {
LABEL_18:
    v21 = (char *)*a2;
    v22 = *((unsigned int *)*a2 + 1);
    v23 = (const char *)(v22 + 1);
    if ( (unsigned __int64)(v22 + 1) > 0xFFFFFFFF )
      goto LABEL_19;
    v24 = *((unsigned int *)a3 + 4);
    v25 = v24 + 3;
    if ( v24 + 3 < v24 )
      goto LABEL_19;
    if ( v25 > 0xFFFFFFFF )
      goto LABEL_19;
    this = (StringMemoryRegionDictionary *)(2LL * (unsigned int)v23);
    if ( !is_mul_ok(2u, (unsigned int)v23) )
      goto LABEL_19;
    v26 = (unsigned int)this + 4LL;
    if ( v26 < (unsigned int)this )
      goto LABEL_19;
    this = *(StringMemoryRegionDictionary **)a3;
    v20 = (unsigned int)v25 & 0xFFFFFFFC;
    if ( v26 > 0xFFFFFFFF )
      goto LABEL_19;
    if ( !this )
    {
LABEL_32:
      if ( (int)v26 + (int)v20 >= (unsigned int)v20 )
      {
        *((_DWORD *)a3 + 4) = v26 + v20;
        v27 = *(_QWORD **)v5;
        Block = *a2;
        _InterlockedIncrement((volatile signed __int32 *)Block);
        v37 = v20;
        std::_Tree<std::_Tmap_traits<DWrite::RefString,unsigned int,std::less<DWrite::RefString>,std::allocator<std::pair<DWrite::RefString const,unsigned int>>,0>>::_Emplace<std::pair<DWrite::RefString const,unsigned int>>(
          v27,
          (__int64)v38,
          &Block);
        v28 = Block;
        if ( Block != &DWrite::RefString::empty_
          && _InterlockedExchangeAdd((volatile signed __int32 *)Block, 0xFFFFFFFF) == 1 )
        {
          operator delete(v28);
        }
        return (unsigned int)v20;
      }
LABEL_19:
      SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(this, v23, v22, v21);
    }
    v30 = *((_DWORD *)a3 + 2);
    if ( v30 < (unsigned int)v20 )
    {
      FailAssert(0x2Du, v23);
      __debugbreak();
    }
    v31 = v30 - v20;
    if ( v31 < (unsigned int)v26 )
    {
      FailAssert(0x2Eu, v23);
      JUMPOUT(0x1800242C6LL);
    }
    *(_DWORD *)((char *)this + v20) = (_DWORD)v23;
    v32 = (char *)this + (unsigned int)v20 + 4;
    v33 = 2 * v22;
    if ( !(2 * v22) )
    {
LABEL_48:
      *(_WORD *)&v32[v33] = 0;
      goto LABEL_32;
    }
    if ( !v32 )
    {
      *(_DWORD *)_o__errno(this, v23, v22) = 22;
      invalid_parameter_noinfo();
      *(_WORD *)v33 = 0;
      goto LABEL_32;
    }
    v34 = v21 + 8;
    v35 = v31 - 4LL;
    if ( v21 != (char *)-8LL && v35 >= v33 )
    {
      memcpy_0((char *)this + (unsigned int)v20 + 4, v21 + 8, 2 * v22);
      v5 = v40;
      *(_WORD *)&v32[v33] = 0;
      goto LABEL_32;
    }
    memset_0((char *)this + (unsigned int)v20 + 4, 0, v31 - 4LL);
    if ( v34 )
    {
      if ( v35 >= v33 )
      {
LABEL_47:
        v5 = v40;
        goto LABEL_48;
      }
      *(_DWORD *)_o__errno(this, v23, v22) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(this, v23, v22) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_47;
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180024000  mov     [rsp+arg_8], rbx
0x180024005  mov     [rsp+arg_0], rcx
0x18002400a  push    rbp
0x18002400b  push    rsi
0x18002400c  push    rdi
0x18002400d  push    r12
0x18002400f  push    r13
0x180024011  push    r14
0x180024013  push    r15
0x180024015  sub     rsp, 50h
0x180024019  mov     r13, r8
0x18002401c  mov     r15, rdx
0x18002401f  mov     r12, rcx
0x180024022  mov     r14, [rcx]
0x180024025  mov     ebp, 0FFFFFFFFh
0x18002402a  test    r14, r14
0x18002402d  jz      loc_18002427B
0x180024033  mov     rdi, [r14]
0x180024036  mov     rbx, [rdi+8]
0x18002403a  xor     eax, eax
0x18002403c  mov     [rsp+88h+var_4C], eax
0x180024040  cmp     [rbx+19h], al
0x180024043  jnz     loc_1800240EA
0x180024049  mov     rdx, [r15]
0x18002404c  mov     esi, [rdx+4]
0x18002404f  mov     rcx, [rbx+20h]
0x180024053  mov     ebp, [rcx+4]
0x180024056  mov     r8d, esi
0x180024059  cmp     rsi, rbp
0x18002405c  cmovnb  r8d, ebp; N
0x180024060  add     rdx, 8; S2
0x180024064  add     rcx, 8; S1
0x180024068  call    wmemcmp
0x18002406d  test    eax, eax
0x18002406f  jz      short loc_1800240DD
0x180024071  jns     short loc_1800240E2
0x180024073  mov     rbx, [rbx+10h]
0x180024077  cmp     byte ptr [rbx+19h], 0
0x18002407b  jz      short loc_180024049
0x18002407d  mov     rax, [r14]
0x180024080  mov     ebp, 0FFFFFFFFh
0x180024085  cmp     byte ptr [rdi+19h], 0
0x180024089  jnz     short loc_1800240F7
0x18002408b  mov     rdx, [rdi+20h]
0x18002408f  mov     ebx, [rdx+4]
0x180024092  mov     rcx, [r15]
0x180024095  mov     esi, [rcx+4]
0x180024098  mov     r8d, ebx
0x18002409b  cmp     rbx, rsi
0x18002409e  cmovnb  r8d, esi; N
0x1800240a2  add     rdx, 8; S2
0x1800240a6  add     rcx, 8; S1
0x1800240aa  call    wmemcmp
0x1800240af  test    eax, eax
0x1800240b1  jz      short loc_1800240EF
0x1800240b3  js      short loc_1800240F4
0x1800240b5  cmp     rdi, [r14]
0x1800240b8  mov     ebx, ebp
0x1800240ba  jz      short loc_1800240BF
0x1800240bc  mov     ebx, [rdi+28h]
0x1800240bf  cmp     ebx, ebp
0x1800240c1  jnz     loc_18002418C
0x1800240c7  mov     r9, [r15]
0x1800240ca  mov     r8d, [r9+4]
0x1800240ce  lea     rdx, [r8+1]; char *
0x1800240d2  cmp     rdx, rbp
0x1800240d5  jbe     short loc_1800240FC
0x1800240d7  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x1800240dd  cmp     rbp, rsi
0x1800240e0  jb      short loc_180024073
0x1800240e2  mov     rdi, rbx
0x1800240e5  mov     rbx, [rbx]
0x1800240e8  jmp     short loc_180024077
0x1800240ea  mov     rax, rdi
0x1800240ed  jmp     short loc_180024085
0x1800240ef  cmp     rsi, rbx
0x1800240f2  jnb     short loc_1800240B5
0x1800240f4  mov     rax, [r14]
0x1800240f7  mov     rdi, rax
0x1800240fa  jmp     short loc_1800240B5
0x1800240fc  mov     eax, [r13+10h]
0x180024100  lea     rbx, [rax+3]
0x180024104  cmp     rbx, rax
0x180024107  jb      short loc_1800240D7
0x180024109  cmp     rbx, rbp
0x18002410c  ja      short loc_1800240D7
0x18002410e  mov     ecx, edx
0x180024110  add     rcx, rcx
0x180024113  mov     rax, rcx
0x180024116  shr     rax, 20h
0x18002411a  test    eax, eax
0x18002411c  jnz     short loc_1800240D7
0x18002411e  mov     eax, ecx
0x180024120  lea     rdi, [rax+4]
0x180024124  cmp     rdi, rax
0x180024127  jb      short loc_1800240D7
0x180024129  mov     rcx, [r13+0]
0x18002412d  and     ebx, 0FFFFFFFCh
0x180024130  cmp     rdi, rbp
0x180024133  ja      short loc_1800240D7
0x180024135  test    rcx, rcx
0x180024138  jnz     short loc_1800241A6
0x18002413a  lea     eax, [rdi+rbx]
0x18002413d  cmp     eax, ebx
0x18002413f  jb      short loc_1800240D7
0x180024141  mov     [r13+10h], eax
0x180024145  mov     rcx, [r12]
0x180024149  mov     rax, [r15]
0x18002414c  mov     [rsp+88h+Block], rax
0x180024151  lock inc dword ptr [rax]
0x180024154  mov     [rsp+88h+var_60], ebx
0x180024158  lea     r8, [rsp+88h+Block]
0x18002415d  lea     rdx, [rsp+88h+var_58]
0x180024162  call    ??$_Emplace@U?$pair@$$CBVRefString@DWrite@@I@std@@@?$_Tree@V?$_Tmap_traits@VRefString@DWrite@@IU?$less@VRefString@DWrite@@@std@@V?$allocator@U?$pair@$$CBVRefString@DWrite@@I@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVRefString@DWrite@@I@std@@PEAX@std@@_N@1@$$QEAU?$pair@$$CBVRefString@DWrite@@I@1@@Z; std::_Tree<std::_Tmap_traits<DWrite::RefString,uint,std::less<DWrite::RefString>,std::allocator<std::pair<DWrite::RefString const,uint>>,0>>::_Emplace<std::pair<DWrite::RefString const,uint>>(std::pair<DWrite::RefString const,uint> &&)
0x180024167  nop
0x180024168  mov     rcx, [rsp+88h+Block]; Block
0x18002416d  lea     rax, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x180024174  cmp     rcx, rax
0x180024177  jz      short loc_18002418C
0x180024179  mov     eax, 0FFFFFFFFh
0x18002417e  lock xadd [rcx], eax
0x180024182  cmp     eax, 1
0x180024185  jnz     short loc_18002418C
0x180024187  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002418c  mov     eax, ebx
0x18002418e  mov     rbx, [rsp+88h+arg_8]
0x180024196  add     rsp, 50h
0x18002419a  pop     r15
0x18002419c  pop     r14
0x18002419e  pop     r13
0x1800241a0  pop     r12
0x1800241a2  pop     rdi
0x1800241a3  pop     rsi
0x1800241a4  pop     rbp
0x1800241a5  retn
0x1800241a6  mov     r10d, [r13+8]
0x1800241aa  cmp     r10d, ebx
0x1800241ad  jb      loc_1800242B1
0x1800241b3  sub     r10d, ebx
0x1800241b6  cmp     r10d, edi
0x1800241b9  jb      loc_1800242BC
0x1800241bf  mov     eax, ebx
0x1800241c1  mov     [rbx+rcx], edx
0x1800241c4  lea     rsi, [rcx+4]
0x1800241c8  add     rsi, rax
0x1800241cb  lea     r14, [r8+r8]
0x1800241cf  test    r14, r14
0x1800241d2  jz      short loc_180024232
0x1800241d4  test    rsi, rsi
0x1800241d7  jz      loc_18002425E
0x1800241dd  lea     rbp, [r9+8]
0x1800241e1  mov     r12d, r10d
0x1800241e4  add     r12, 0FFFFFFFFFFFFFFFCh
0x1800241e8  test    rbp, rbp
0x1800241eb  jz      short loc_18002423E
0x1800241ed  cmp     r12, r14
0x1800241f0  jb      short loc_18002423E
0x1800241f2  mov     r8, r14; Size
0x1800241f5  mov     rdx, rbp; Src
0x1800241f8  mov     rcx, rsi; void *
0x1800241fb  call    memcpy_0
0x180024200  mov     r12, [rsp+88h+arg_0]
0x180024208  xor     eax, eax
0x18002420a  mov     [r14+rsi], ax
0x18002420f  jmp     loc_18002413A
0x180024214  cmp     r12, r14
0x180024217  jnb     short loc_18002422A
0x180024219  call    cs:__imp__o__errno
0x18002421f  mov     dword ptr [rax], 22h ; '"'
0x180024225  call    _invalid_parameter_noinfo
0x18002422a  mov     r12, [rsp+88h+arg_0]
0x180024232  xor     eax, eax
0x180024234  mov     [r14+rsi], ax
0x180024239  jmp     loc_18002413A
0x18002423e  mov     r8, r12; Size
0x180024241  xor     edx, edx; Val
0x180024243  mov     rcx, rsi; void *
0x180024246  call    memset_0
0x18002424b  test    rbp, rbp
0x18002424e  jnz     short loc_180024214
0x180024250  call    cs:__imp__o__errno
0x180024256  mov     dword ptr [rax], 16h
0x18002425c  jmp     short loc_180024225
0x18002425e  call    cs:__imp__o__errno
0x180024264  mov     dword ptr [rax], 16h
0x18002426a  call    _invalid_parameter_noinfo
0x18002426f  xor     eax, eax
0x180024271  mov     [r14+rsi], ax
0x180024276  jmp     loc_18002413A
0x18002427b  mov     ecx, 10h; Size
0x180024280  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024285  mov     rbx, rax
0x180024288  mov     [rsp+88h+arg_18], rax
0x180024290  mov     qword ptr [rax], 0
0x180024297  mov     qword ptr [rax+8], 0
0x18002429f  mov     rcx, rax
0x1800242a2  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@UScriptLanguageFeature@FontFeatureCoverageRegion@@U?$less@UScriptLanguageFeature@FontFeatureCoverageRegion@@@std@@V?$allocator@UScriptLanguageFeature@FontFeatureCoverageRegion@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<FontFeatureCoverageRegion::ScriptLanguageFeature,std::less<FontFeatureCoverageRegion::ScriptLanguageFeature>,std::allocator<FontFeatureCoverageRegion::ScriptLanguageFeature>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800242a7  nop
0x1800242a8  mov     [r12], rbx
0x1800242ac  jmp     loc_1800240C7
0x1800242b1  mov     ecx, 2Dh ; '-'; unsigned int
0x1800242b6  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x1800242bb  int     3; Trap to Debugger
0x1800242bc  mov     ecx, 2Eh ; '.'; unsigned int
0x1800242c1  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
```
