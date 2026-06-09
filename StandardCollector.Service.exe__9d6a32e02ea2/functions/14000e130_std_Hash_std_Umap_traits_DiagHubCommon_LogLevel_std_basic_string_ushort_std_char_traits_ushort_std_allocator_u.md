# std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> *,std::_List_node<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> * const)

- ea: `0x14000e130`
- end: `0x14000e2df`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `431`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000e060`

## callees

- `0x140003010`
- `0x14000e130`
- `0x14001382c`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v5; // rsi
  _QWORD *v6; // r14
  __int64 v7; // r15
  __int64 v8; // r12
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // r15
  __int64 v12; // rcx
  void *v13; // rbx
  _QWORD *v14; // rdx
  _QWORD *v16; // rax
  __int64 v17; // rcx
  unsigned __int64 i; // r8
  __int64 v19; // rax
  __int64 v20; // rcx
  void *v21; // rbx
  _QWORD *v22; // [rsp+20h] [rbp-48h]
  void *v23; // [rsp+28h] [rbp-40h]
  void *v24; // [rsp+28h] [rbp-40h]
  _QWORD *v25; // [rsp+30h] [rbp-38h]

  if ( a2 != a3 )
  {
    v5 = a2;
    v6 = (_QWORD *)a2[1];
    v7 = 0xCBF29CE484222325uLL;
    v8 = a1[3];
    v9 = 0;
    v22 = (_QWORD *)a1[1];
    do
    {
      v10 = *((unsigned __int8 *)a2 + v9 + 16);
      ++v9;
      v7 = 0x100000001B3LL * (v10 ^ v7);
    }
    while ( v9 < 4 );
    v11 = 2 * (a1[6] & v7);
    v25 = *(_QWORD **)(v8 + 8 * v11);
    v23 = *(void **)(v8 + 8 * v11 + 8);
    while ( 1 )
    {
      v12 = (__int64)(v5 + 3);
      v13 = v5;
      v5 = (_QWORD *)*v5;
      std::wstring::~wstring(v12);
      operator delete(v13);
      v14 = a1;
      --a1[2];
      if ( v13 == v23 )
        break;
      if ( v5 == a3 )
      {
        if ( v25 == a2 )
LABEL_8:
          *(_QWORD *)(v8 + 8 * v11) = v5;
        goto LABEL_9;
      }
    }
    if ( v25 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v11) = v22;
      v16 = v22;
    }
    else
    {
      v16 = v6;
    }
    *(_QWORD *)(v8 + 8 * v11 + 8) = v16;
    while ( v5 != a3 )
    {
      v17 = 0xCBF29CE484222325uLL;
      for ( i = 0; i < 4; ++i )
      {
        v19 = *((unsigned __int8 *)v5 + i + 16);
        v17 = 0x100000001B3LL * (v19 ^ v17);
      }
      v11 = 2 * (v17 & v14[6]);
      v24 = *(void **)(v8 + 16 * (v17 & v14[6]) + 8);
      while ( 1 )
      {
        v20 = (__int64)(v5 + 3);
        v21 = v5;
        v5 = (_QWORD *)*v5;
        std::wstring::~wstring(v20);
        operator delete(v21);
        v14 = a1;
        --a1[2];
        if ( v21 == v24 )
          break;
        if ( v5 == a3 )
          goto LABEL_8;
      }
      *(_QWORD *)(v8 + 8 * v11) = v22;
      *(_QWORD *)(v8 + 8 * v11 + 8) = v22;
    }
LABEL_9:
    *v6 = v5;
    v5[1] = v6;
  }
  return a3;
}

```

## disassembly

```asm
0x14000e130  mov     [rsp+arg_8], rbx
0x14000e135  mov     [rsp+arg_10], rbp
0x14000e13a  mov     [rsp+arg_18], rsi
0x14000e13f  push    rdi
0x14000e140  push    r12
0x14000e142  push    r13
0x14000e144  push    r14
0x14000e146  push    r15
0x14000e148  sub     rsp, 40h
0x14000e14c  mov     [rsp+68h+var_30], rcx
0x14000e151  mov     rbp, r8
0x14000e154  mov     r13, rdx
0x14000e157  cmp     rdx, r8
0x14000e15a  jz      loc_14000E203
0x14000e160  mov     rax, [rcx+8]
0x14000e164  mov     rsi, rdx
0x14000e167  mov     r14, [rdx+8]
0x14000e16b  mov     r15, 0CBF29CE484222325h
0x14000e175  mov     r12, [rcx+18h]
0x14000e179  xor     edx, edx
0x14000e17b  mov     [rsp+68h+var_48], rax
0x14000e180  mov     r8, 100000001B3h
0x14000e18a  movzx   eax, byte ptr [rdx+r13+10h]
0x14000e190  inc     rdx
0x14000e193  xor     r15, rax
0x14000e196  imul    r15, r8
0x14000e19a  cmp     rdx, 4
0x14000e19e  jb      short loc_14000E18A
0x14000e1a0  and     r15, [rcx+30h]
0x14000e1a4  add     r15, r15
0x14000e1a7  mov     rax, [r12+r15*8]
0x14000e1ab  mov     [rsp+68h+var_38], rax
0x14000e1b0  mov     rax, [r12+r15*8+8]
0x14000e1b5  mov     [rsp+68h+var_40], rax
0x14000e1ba  mov     rcx, rsi
0x14000e1bd  mov     rdi, rsi
0x14000e1c0  add     rcx, 18h
0x14000e1c4  mov     rbx, rsi
0x14000e1c7  mov     rsi, [rsi]
0x14000e1ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000e1cf  mov     edx, 38h ; '8'
0x14000e1d4  mov     rcx, rbx; Block
0x14000e1d7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e1dc  mov     rdx, [rsp+68h+var_30]
0x14000e1e1  dec     qword ptr [rdx+10h]
0x14000e1e5  cmp     rbx, [rsp+68h+var_40]
0x14000e1ea  jz      short loc_14000E224
0x14000e1ec  cmp     rsi, rbp
0x14000e1ef  jnz     short loc_14000E1BA
0x14000e1f1  cmp     [rsp+68h+var_38], r13
0x14000e1f6  jnz     short loc_14000E1FC
0x14000e1f8  mov     [r12+r15*8], rsi
0x14000e1fc  mov     [r14], rsi
0x14000e1ff  mov     [rsi+8], r14
0x14000e203  lea     r11, [rsp+68h+var_28]
0x14000e208  mov     rax, rbp
0x14000e20b  mov     rbx, [r11+38h]
0x14000e20f  mov     rbp, [r11+40h]
0x14000e213  mov     rsi, [r11+48h]
0x14000e217  mov     rsp, r11
0x14000e21a  pop     r15
0x14000e21c  pop     r14
0x14000e21e  pop     r13
0x14000e220  pop     r12
0x14000e222  pop     rdi
0x14000e223  retn
0x14000e224  cmp     [rsp+68h+var_38], r13
0x14000e229  jnz     short loc_14000E239
0x14000e22b  mov     r13, [rsp+68h+var_48]
0x14000e230  mov     [r12+r15*8], r13
0x14000e234  mov     rax, r13
0x14000e237  jmp     short loc_14000E23C
0x14000e239  mov     rax, r14
0x14000e23c  mov     [r12+r15*8+8], rax
0x14000e241  jmp     loc_14000E2D1
0x14000e246  mov     rcx, 0CBF29CE484222325h
0x14000e250  xor     r8d, r8d
0x14000e253  mov     r13, 100000001B3h
0x14000e25d  movzx   eax, byte ptr [rsi+r8+10h]
0x14000e263  inc     r8
0x14000e266  xor     rcx, rax
0x14000e269  imul    rcx, r13
0x14000e26d  cmp     r8, 4
0x14000e271  jb      short loc_14000E25D
0x14000e273  mov     r15, [rdx+30h]
0x14000e277  mov     r13, [rsp+68h+var_48]
0x14000e27c  and     r15, rcx
0x14000e27f  add     r15, r15
0x14000e282  mov     rax, [r12+r15*8+8]
0x14000e287  mov     [rsp+68h+var_40], rax
0x14000e28c  mov     rcx, rsi
0x14000e28f  mov     rdi, rsi
0x14000e292  add     rcx, 18h
0x14000e296  mov     rbx, rsi
0x14000e299  mov     rsi, [rsi]
0x14000e29c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000e2a1  mov     edx, 38h ; '8'
0x14000e2a6  mov     rcx, rbx; Block
0x14000e2a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e2ae  mov     rdx, [rsp+68h+var_30]
0x14000e2b3  dec     qword ptr [rdx+10h]
0x14000e2b7  cmp     rbx, [rsp+68h+var_40]
0x14000e2bc  jz      short loc_14000E2C8
0x14000e2be  cmp     rsi, rbp
0x14000e2c1  jnz     short loc_14000E28C
0x14000e2c3  jmp     loc_14000E1F8
0x14000e2c8  mov     [r12+r15*8], r13
0x14000e2cc  mov     [r12+r15*8+8], r13
0x14000e2d1  cmp     rsi, rbp
0x14000e2d4  jnz     loc_14000E246
0x14000e2da  jmp     loc_14000E1FC
```
