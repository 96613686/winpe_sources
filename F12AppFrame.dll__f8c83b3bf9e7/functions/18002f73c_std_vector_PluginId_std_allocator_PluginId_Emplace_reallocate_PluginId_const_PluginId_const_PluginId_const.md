# std::vector<PluginId,std::allocator<PluginId>>::_Emplace_reallocate<PluginId const &>(PluginId * const,PluginId const &)

- ea: `0x18002f73c`
- end: `0x18002f8db`
- name: `??$_Emplace_reallocate@AEBW4PluginId@@@?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@AEAAPEAW4PluginId@@QEAW42@AEBW42@@Z`
- size: `415`
- prototype: `_DWORD *__fastcall(__int64, _BYTE *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002fac0`

## callees

- `0x180001900`
- `0x18000193c`
- `0x1800056c4`
- `0x1800056ec`
- `0x18002f73c`
- `0x180032ad4`

## pseudocode

```c
_DWORD *__fastcall std::vector<enum PluginId>::_Emplace_reallocate<enum PluginId const &>(
        __int64 a1,
        _BYTE *a2,
        _DWORD *a3)
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

  v3 = F12::m_plugins;
  v6 = (qword_1800507E0 - (__int64)F12::m_plugins) >> 2;
  if ( v6 == 0x3FFFFFFFFFFFFFFFLL )
    std::vector<ATL::CComVariant>::_Xlength();
  v7 = (qword_1800507E8 - (__int64)F12::m_plugins) >> 2;
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
  v16 = F12::m_plugins;
  if ( a2 == (_BYTE *)qword_1800507E0 )
  {
    v17 = qword_1800507E0 - (_QWORD)F12::m_plugins;
  }
  else
  {
    memmove_0(v12, F12::m_plugins, a2 - (_BYTE *)F12::m_plugins);
    v15 = v14 + 1;
    v17 = qword_1800507E0 - (_QWORD)a2;
    v16 = a2;
  }
  memmove_0(v15, v16, v17);
  if ( F12::m_plugins )
  {
    if ( (unsigned __int64)(4 * ((qword_1800507E8 - (__int64)F12::m_plugins) >> 2)) < 0x1000 )
    {
      v18 = F12::m_plugins;
    }
    else
    {
      v18 = (_BYTE *)*((_QWORD *)F12::m_plugins - 1);
      if ( (unsigned __int64)((_BYTE *)F12::m_plugins - v18 - 8) > 0x1F )
LABEL_19:
        __fastfail(5u);
    }
    operator delete(v18);
  }
  F12::m_plugins = v12;
  qword_1800507E0 = (__int64)v12 + 4 * v9;
  result = v14;
  qword_1800507E8 = (__int64)v12 + v11;
  return result;
}

```

## disassembly

```asm
0x18002f73c  push    rbx
0x18002f73e  push    rbp
0x18002f73f  push    rsi
0x18002f740  push    rdi
0x18002f741  push    r14
0x18002f743  push    r15
0x18002f745  sub     rsp, 28h
0x18002f749  mov     rsi, cs:?m_plugins@F12@@3V?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@A; std::vector<PluginId> F12::m_plugins
0x18002f750  mov     r15, r8
0x18002f753  mov     r9, cs:qword_1800507E0
0x18002f75a  mov     r8, 3FFFFFFFFFFFFFFFh
0x18002f764  sub     r9, rsi
0x18002f767  mov     rbp, rdx
0x18002f76a  sar     r9, 2
0x18002f76e  cmp     r9, r8
0x18002f771  jz      loc_18002F8CF
0x18002f777  mov     rcx, cs:qword_1800507E8
0x18002f77e  mov     rax, r8
0x18002f781  sub     rcx, rsi
0x18002f784  sar     rcx, 2
0x18002f788  mov     rdx, rcx
0x18002f78b  shr     rdx, 1
0x18002f78e  sub     rax, rdx
0x18002f791  cmp     rcx, rax
0x18002f794  ja      loc_18002F8D5
0x18002f79a  lea     r14, [r9+1]
0x18002f79e  lea     rax, [rdx+rcx]
0x18002f7a2  mov     rdi, r14
0x18002f7a5  cmp     rax, r14
0x18002f7a8  cmovnb  rdi, rax
0x18002f7ac  cmp     rdi, r8
0x18002f7af  ja      loc_18002F8D5
0x18002f7b5  shl     rdi, 2
0x18002f7b9  test    rdi, rdi
0x18002f7bc  jnz     short loc_18002F7C2
0x18002f7be  xor     ebx, ebx
0x18002f7c0  jmp     short loc_18002F7FF
0x18002f7c2  cmp     rdi, 1000h
0x18002f7c9  jb      short loc_18002F7F4
0x18002f7cb  lea     rcx, [rdi+27h]; Size
0x18002f7cf  cmp     rcx, rdi
0x18002f7d2  jbe     loc_18002F8D5
0x18002f7d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f7dd  test    rax, rax
0x18002f7e0  jz      loc_18002F890
0x18002f7e6  lea     rbx, [rax+27h]
0x18002f7ea  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18002f7ee  mov     [rbx-8], rax
0x18002f7f2  jmp     short loc_18002F7FF
0x18002f7f4  mov     rcx, rdi; Size
0x18002f7f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f7fc  mov     rbx, rax
0x18002f7ff  mov     rcx, rbp
0x18002f802  sub     rcx, rsi
0x18002f805  sar     rcx, 2
0x18002f809  lea     rsi, [rbx+rcx*4]
0x18002f80d  mov     ecx, [r15]
0x18002f810  mov     [rsi], ecx
0x18002f812  mov     rcx, rbx; void *
0x18002f815  mov     r8, cs:qword_1800507E0
0x18002f81c  mov     rdx, cs:?m_plugins@F12@@3V?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@A; Src
0x18002f823  cmp     rbp, r8
0x18002f826  jnz     short loc_18002F82D
0x18002f828  sub     r8, rdx
0x18002f82b  jmp     short loc_18002F849
0x18002f82d  mov     r8, rbp
0x18002f830  sub     r8, rdx; Size
0x18002f833  call    memmove_0
0x18002f838  mov     r8, cs:qword_1800507E0
0x18002f83f  lea     rcx, [rsi+4]; void *
0x18002f843  sub     r8, rbp; Size
0x18002f846  mov     rdx, rbp; Src
0x18002f849  call    memmove_0
0x18002f84e  mov     rcx, cs:?m_plugins@F12@@3V?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@A; std::vector<PluginId> F12::m_plugins
0x18002f855  test    rcx, rcx
0x18002f858  jz      short loc_18002F8A2
0x18002f85a  mov     rax, cs:qword_1800507E8
0x18002f861  sub     rax, rcx
0x18002f864  sar     rax, 2
0x18002f868  lea     rdx, ds:0[rax*4]
0x18002f870  cmp     rdx, 1000h
0x18002f877  jb      short loc_18002F897
0x18002f879  mov     rax, [rcx-8]
0x18002f87d  sub     rcx, rax
0x18002f880  sub     rcx, 8
0x18002f884  cmp     rcx, 1Fh
0x18002f888  ja      short loc_18002F890
0x18002f88a  add     rdx, 27h ; '''
0x18002f88e  jmp     short loc_18002F89A
0x18002f890  mov     ecx, 5
0x18002f895  int     29h; Win8: RtlFailFast(ecx)
0x18002f897  mov     rax, rcx
0x18002f89a  mov     rcx, rax; Block
0x18002f89d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002f8a2  lea     rcx, [rbx+r14*4]
0x18002f8a6  mov     cs:?m_plugins@F12@@3V?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@A, rbx; std::vector<PluginId> F12::m_plugins
0x18002f8ad  mov     cs:qword_1800507E0, rcx
0x18002f8b4  mov     rax, rsi
0x18002f8b7  lea     rcx, [rdi+rbx]
0x18002f8bb  mov     cs:qword_1800507E8, rcx
0x18002f8c2  add     rsp, 28h
0x18002f8c6  pop     r15
0x18002f8c8  pop     r14
0x18002f8ca  pop     rdi
0x18002f8cb  pop     rsi
0x18002f8cc  pop     rbp
0x18002f8cd  pop     rbx
0x18002f8ce  retn
0x18002f8cf  call    ?_Xlength@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@CAXXZ; std::vector<ATL::CComVariant>::_Xlength(void)
0x18002f8d5  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
