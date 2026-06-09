# TerminateExtension

- ea: `0x18000d930`
- end: `0x18000d99a`
- name: `TerminateExtension`
- size: `106`
- prototype: `BOOL __stdcall(DWORD dwFlags)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180002df0`
- `0x180005fb8`
- `0x18000c614`
- `0x18000d930`
- `0x18000f214`

## pseudocode

```c
BOOL __stdcall TerminateExtension(DWORD dwFlags)
{
  struct CReadWriteLock *v1; // rdx
  __int64 v2; // rax
  __int64 v3; // rbx
  CReadWriteLock *v5; // [rsp+38h] [rbp+10h] BYREF
  char v6; // [rsp+40h] [rbp+18h] BYREF

  CSW::CSW((CSW *)&v5, v1);
  v2 = qword_180017CB8;
  v3 = *(_QWORD *)qword_180017CB8;
  while ( v3 != v2 )
  {
    if ( !*(_DWORD *)(v3 + 72) )
      FreeRpcBindHandle(*(_QWORD *)(v3 + 64));
    v3 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::erase(
                      &qword_180017CB0,
                      &v6,
                      v3);
    v2 = qword_180017CB8;
  }
  if ( v5 )
    CReadWriteLock::UnlockWrite(v5);
  return 1;
}

```

## disassembly

```asm
0x18000d930  push    rbx
0x18000d932  sub     rsp, 20h
0x18000d936  lea     rcx, [rsp+28h+arg_8]; this
0x18000d93b  call    ??0CSW@@QEAA@AEAVCReadWriteLock@@@Z; CSW::CSW(CReadWriteLock &)
0x18000d940  nop
0x18000d941  mov     rax, cs:qword_180017CB8
0x18000d948  mov     rbx, [rax]
0x18000d94b  cmp     rbx, rax
0x18000d94e  jz      short loc_18000D97F
0x18000d950  cmp     dword ptr [rbx+48h], 0
0x18000d954  jnz     short loc_18000D95F
0x18000d956  mov     rcx, [rbx+40h]
0x18000d95a  call    FreeRpcBindHandle
0x18000d95f  mov     r8, rbx
0x18000d962  lea     rdx, [rsp+28h+arg_10]
0x18000d967  lea     rcx, qword_180017CB0
0x18000d96e  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@@std@@@2@$00@std@@@std@@QEAA?AViterator@12@V312@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::erase(std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::iterator)
0x18000d973  mov     rbx, [rax]
0x18000d976  mov     rax, cs:qword_180017CB8
0x18000d97d  jmp     short loc_18000D94B
0x18000d97f  mov     rcx, [rsp+28h+arg_8]; this
0x18000d984  test    rcx, rcx
0x18000d987  jz      short loc_18000D98F
0x18000d989  call    ?UnlockWrite@CReadWriteLock@@QEAAXXZ; CReadWriteLock::UnlockWrite(void)
0x18000d98e  nop
0x18000d98f  mov     eax, 1
0x18000d994  add     rsp, 20h
0x18000d998  pop     rbx
0x18000d999  retn
```
