# std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x14000e060`
- end: `0x14000e12d`
- name: `??1_Clear_guard@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000dc98`

## callees

- `0x140003010`
- `0x14000e060`
- `0x14000e130`
- `0x14001382c`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  _QWORD **v2; // rcx
  _QWORD *v3; // rsi
  _QWORD *v4; // rdi
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = (_QWORD **)v1[1];
    if ( v1[7] >> 3 <= v1[2] )
    {
      *v2[1] = 0;
      v3 = *v2;
      if ( *v2 )
      {
        do
        {
          v4 = (_QWORD *)*v3;
          std::wstring::~wstring(v3 + 3);
          operator delete(v3);
          v3 = v4;
        }
        while ( v4 );
      }
      *(_QWORD *)v1[1] = v1[1];
      *(_QWORD *)(v1[1] + 8LL) = v1[1];
      v1[2] = 0;
      v5 = (void *)v1[3];
      v6 = (unsigned __int64)(v1[4] - (_QWORD)v5 + 7LL) >> 3;
      if ( (unsigned __int64)v5 > v1[4] )
        v6 = 0;
      if ( v6 )
        memset64(v5, v1[1], v6);
    }
    else
    {
      std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Unchecked_erase(
        v1,
        *v2,
        (_QWORD *)v1[1]);
    }
  }
}

```

## disassembly

```asm
0x14000e060  mov     [rsp+arg_8], rbx
0x14000e065  mov     [rsp+arg_10], rbp
0x14000e06a  mov     [rsp+arg_18], rsi
0x14000e06f  push    rdi
0x14000e070  sub     rsp, 20h
0x14000e074  mov     rbx, [rcx]
0x14000e077  xor     ebp, ebp
0x14000e079  test    rbx, rbx
0x14000e07c  jz      loc_14000E118
0x14000e082  cmp     [rbx+10h], rbp
0x14000e086  jz      loc_14000E118
0x14000e08c  mov     rax, [rbx+38h]
0x14000e090  mov     rcx, [rbx+8]
0x14000e094  shr     rax, 3
0x14000e098  cmp     rax, [rbx+10h]
0x14000e09c  jbe     short loc_14000E0AE
0x14000e09e  mov     rdx, [rcx]
0x14000e0a1  mov     r8, rcx
0x14000e0a4  mov     rcx, rbx
0x14000e0a7  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Unchecked_erase(std::_List_node<std::pair<DiagHubCommon::LogLevel const,std::wstring>,void *> *,std::_List_node<std::pair<DiagHubCommon::LogLevel const,std::wstring>,void *> * const)
0x14000e0ac  jmp     short loc_14000E118
0x14000e0ae  mov     rax, [rcx+8]
0x14000e0b2  mov     [rax], rbp
0x14000e0b5  mov     rsi, [rcx]
0x14000e0b8  test    rsi, rsi
0x14000e0bb  jz      short loc_14000E0DE
0x14000e0bd  mov     rdi, [rsi]
0x14000e0c0  lea     rcx, [rsi+18h]
0x14000e0c4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000e0c9  mov     edx, 38h ; '8'
0x14000e0ce  mov     rcx, rsi; Block
0x14000e0d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e0d6  mov     rsi, rdi
0x14000e0d9  test    rdi, rdi
0x14000e0dc  jnz     short loc_14000E0BD
0x14000e0de  mov     rax, [rbx+8]
0x14000e0e2  mov     [rax], rax
0x14000e0e5  mov     rax, [rbx+8]
0x14000e0e9  mov     [rax+8], rax
0x14000e0ed  mov     [rbx+10h], rbp
0x14000e0f1  mov     rdi, [rbx+18h]
0x14000e0f5  mov     rcx, [rbx+20h]
0x14000e0f9  sub     rcx, rdi
0x14000e0fc  add     rcx, 7
0x14000e100  shr     rcx, 3
0x14000e104  cmp     rdi, [rbx+20h]
0x14000e108  cmova   rcx, rbp
0x14000e10c  test    rcx, rcx
0x14000e10f  jz      short loc_14000E118
0x14000e111  mov     rax, [rbx+8]
0x14000e115  rep stosq
0x14000e118  mov     rbx, [rsp+28h+arg_8]
0x14000e11d  mov     rbp, [rsp+28h+arg_10]
0x14000e122  mov     rsi, [rsp+28h+arg_18]
0x14000e127  add     rsp, 20h
0x14000e12b  pop     rdi
0x14000e12c  retn
```
