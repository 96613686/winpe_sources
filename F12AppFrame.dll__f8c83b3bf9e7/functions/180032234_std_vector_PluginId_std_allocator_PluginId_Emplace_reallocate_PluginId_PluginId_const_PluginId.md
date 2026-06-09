# std::vector<PluginId,std::allocator<PluginId>>::_Emplace_reallocate<PluginId>(PluginId * const,PluginId &&)

- ea: `0x180032234`
- end: `0x1800323d3`
- name: `??$_Emplace_reallocate@W4PluginId@@@?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@AEAAPEAW4PluginId@@QEAW42@$$QEAW42@@Z`
- size: `415`
- prototype: `_DWORD *__fastcall(__int64, _BYTE *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800326e8`

## callees

- `0x180001900`
- `0x18000193c`
- `0x1800056c4`
- `0x1800056ec`
- `0x180032234`
- `0x180032ad4`

## pseudocode

```c
_DWORD *__fastcall std::vector<enum PluginId>::_Emplace_reallocate<enum PluginId>(__int64 a1, _BYTE *a2, _DWORD *a3)
{
  _BYTE *v3; // rsi
  __int64 v6; // r9
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  __int64 v9; // r14
  unsigned __int64 v10; // rdi
  size_t v11; // rdi
  _QWORD *v12; // rbx
  void *v13; // rax
  _DWORD *v14; // rsi
  void *v15; // rcx
  const void *v16; // rdx
  size_t v17; // r8
  _BYTE *v18; // rax
  _DWORD *result; // rax

  v3 = F12::m_toolPlugins;
  v6 = (qword_180050858 - (__int64)F12::m_toolPlugins) >> 2;
  if ( v6 == 0x3FFFFFFFFFFFFFFFLL )
    std::vector<ATL::CComVariant>::_Xlength();
  v7 = (qword_180050860 - (__int64)F12::m_toolPlugins) >> 2;
  v8 = v7 >> 1;
  if ( v7 > 0x3FFFFFFFFFFFFFFFLL - (v7 >> 1) )
    goto LABEL_24;
  v9 = v6 + 1;
  v10 = v6 + 1;
  if ( v8 + v7 >= v6 + 1 )
    v10 = v8 + v7;
  if ( v10 > 0x3FFFFFFFFFFFFFFFLL )
    goto LABEL_24;
  v11 = 4 * v10;
  if ( !v11 )
  {
    v12 = 0;
    goto LABEL_13;
  }
  if ( v11 < 0x1000 )
  {
    v12 = operator new(v11);
    goto LABEL_13;
  }
  if ( v11 + 39 < v11 )
LABEL_24:
    __scrt_throw_std_bad_array_new_length();
  v13 = operator new(v11 + 39);
  if ( !v13 )
    goto LABEL_19;
  v12 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v12 - 1) = v13;
LABEL_13:
  v14 = (_DWORD *)v12 + ((a2 - v3) >> 2);
  *v14 = *a3;
  v15 = v12;
  v16 = F12::m_toolPlugins;
  if ( a2 == (_BYTE *)qword_180050858 )
  {
    v17 = qword_180050858 - (_QWORD)F12::m_toolPlugins;
  }
  else
  {
    memmove_0(v12, F12::m_toolPlugins, a2 - (_BYTE *)F12::m_toolPlugins);
    v15 = v14 + 1;
    v17 = qword_180050858 - (_QWORD)a2;
    v16 = a2;
  }
  memmove_0(v15, v16, v17);
  if ( F12::m_toolPlugins )
  {
    if ( (unsigned __int64)(4 * ((qword_180050860 - (__int64)F12::m_toolPlugins) >> 2)) < 0x1000 )
    {
      v18 = F12::m_toolPlugins;
    }
    else
    {
      v18 = (_BYTE *)*((_QWORD *)F12::m_toolPlugins - 1);
      if ( (unsigned __int64)((_BYTE *)F12::m_toolPlugins - v18 - 8) > 0x1F )
LABEL_19:
        __fastfail(5u);
    }
    operator delete(v18);
  }
  F12::m_toolPlugins = v12;
  qword_180050858 = (__int64)v12 + 4 * v9;
  result = v14;
  qword_180050860 = (__int64)v12 + v11;
  return result;
}

```

## disassembly

```asm
0x180032234  push    rbx
0x180032236  push    rbp
0x180032237  push    rsi
0x180032238  push    rdi
0x180032239  push    r14
0x18003223b  push    r15
0x18003223d  sub     rsp, 28h
0x180032241  mov     rsi, cs:?m_toolPlugins@F12@@3V?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@A; std::vector<PluginId> F12::m_toolPlugins
0x180032248  mov     r15, r8
0x18003224b  mov     r9, cs:qword_180050858
0x180032252  mov     r8, 3FFFFFFFFFFFFFFFh
0x18003225c  sub     r9, rsi
0x18003225f  mov     rbp, rdx
0x180032262  sar     r9, 2
0x180032266  cmp     r9, r8
0x180032269  jz      loc_1800323C7
0x18003226f  mov     rcx, cs:qword_180050860
0x180032276  mov     rax, r8
0x180032279  sub     rcx, rsi
0x18003227c  sar     rcx, 2
0x180032280  mov     rdx, rcx
0x180032283  shr     rdx, 1
0x180032286  sub     rax, rdx
0x180032289  cmp     rcx, rax
0x18003228c  ja      loc_1800323CD
0x180032292  lea     r14, [r9+1]
0x180032296  lea     rax, [rdx+rcx]
0x18003229a  mov     rdi, r14
0x18003229d  cmp     rax, r14
0x1800322a0  cmovnb  rdi, rax
0x1800322a4  cmp     rdi, r8
0x1800322a7  ja      loc_1800323CD
0x1800322ad  shl     rdi, 2
0x1800322b1  test    rdi, rdi
0x1800322b4  jnz     short loc_1800322BA
0x1800322b6  xor     ebx, ebx
0x1800322b8  jmp     short loc_1800322F7
0x1800322ba  cmp     rdi, 1000h
0x1800322c1  jb      short loc_1800322EC
0x1800322c3  lea     rcx, [rdi+27h]; Size
0x1800322c7  cmp     rcx, rdi
0x1800322ca  jbe     loc_1800323CD
0x1800322d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800322d5  test    rax, rax
0x1800322d8  jz      loc_180032388
0x1800322de  lea     rbx, [rax+27h]
0x1800322e2  and     rbx, 0FFFFFFFFFFFFFFE0h
0x1800322e6  mov     [rbx-8], rax
0x1800322ea  jmp     short loc_1800322F7
0x1800322ec  mov     rcx, rdi; Size
0x1800322ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800322f4  mov     rbx, rax
0x1800322f7  mov     rcx, rbp
0x1800322fa  sub     rcx, rsi
0x1800322fd  sar     rcx, 2
0x180032301  lea     rsi, [rbx+rcx*4]
0x180032305  mov     ecx, [r15]
0x180032308  mov     [rsi], ecx
0x18003230a  mov     rcx, rbx; void *
0x18003230d  mov     r8, cs:qword_180050858
0x180032314  mov     rdx, cs:?m_toolPlugins@F12@@3V?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@A; Src
0x18003231b  cmp     rbp, r8
0x18003231e  jnz     short loc_180032325
0x180032320  sub     r8, rdx
0x180032323  jmp     short loc_180032341
0x180032325  mov     r8, rbp
0x180032328  sub     r8, rdx; Size
0x18003232b  call    memmove_0
0x180032330  mov     r8, cs:qword_180050858
0x180032337  lea     rcx, [rsi+4]; void *
0x18003233b  sub     r8, rbp; Size
0x18003233e  mov     rdx, rbp; Src
0x180032341  call    memmove_0
0x180032346  mov     rcx, cs:?m_toolPlugins@F12@@3V?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@A; std::vector<PluginId> F12::m_toolPlugins
0x18003234d  test    rcx, rcx
0x180032350  jz      short loc_18003239A
0x180032352  mov     rax, cs:qword_180050860
0x180032359  sub     rax, rcx
0x18003235c  sar     rax, 2
0x180032360  lea     rdx, ds:0[rax*4]
0x180032368  cmp     rdx, 1000h
0x18003236f  jb      short loc_18003238F
0x180032371  mov     rax, [rcx-8]
0x180032375  sub     rcx, rax
0x180032378  sub     rcx, 8
0x18003237c  cmp     rcx, 1Fh
0x180032380  ja      short loc_180032388
0x180032382  add     rdx, 27h ; '''
0x180032386  jmp     short loc_180032392
0x180032388  mov     ecx, 5
0x18003238d  int     29h; Win8: RtlFailFast(ecx)
0x18003238f  mov     rax, rcx
0x180032392  mov     rcx, rax; Block
0x180032395  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003239a  lea     rcx, [rbx+r14*4]
0x18003239e  mov     cs:?m_toolPlugins@F12@@3V?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@A, rbx; std::vector<PluginId> F12::m_toolPlugins
0x1800323a5  mov     cs:qword_180050858, rcx
0x1800323ac  mov     rax, rsi
0x1800323af  lea     rcx, [rdi+rbx]
0x1800323b3  mov     cs:qword_180050860, rcx
0x1800323ba  add     rsp, 28h
0x1800323be  pop     r15
0x1800323c0  pop     r14
0x1800323c2  pop     rdi
0x1800323c3  pop     rsi
0x1800323c4  pop     rbp
0x1800323c5  pop     rbx
0x1800323c6  retn
0x1800323c7  call    ?_Xlength@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@CAXXZ; std::vector<ATL::CComVariant>::_Xlength(void)
0x1800323cd  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
