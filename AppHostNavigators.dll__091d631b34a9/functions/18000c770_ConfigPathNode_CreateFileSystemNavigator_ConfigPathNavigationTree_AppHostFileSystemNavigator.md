# ConfigPathNode::CreateFileSystemNavigator(ConfigPathNavigationTree *,AppHostFileSystemNavigator * *)

- ea: `0x18000c770`
- end: `0x18000c83b`
- name: `?CreateFileSystemNavigator@ConfigPathNode@@QEAAXPEAVConfigPathNavigationTree@@PEAPEAVAppHostFileSystemNavigator@@@Z`
- size: `203`
- prototype: `void __fastcall(ConfigPathNode *this, struct ConfigNameTablePair **, struct AppHostFileSystemNavigator **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180004b90`
- `0x18000d920`

## callees

- `0x180005dc8`
- `0x180005fdc`
- `0x18000c770`
- `0x180012768`
- `0x180012f3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConfigPathNode::CreateFileSystemNavigator(
        ConfigPathNode *this,
        struct ConfigNameTablePair **a2,
        struct AppHostFileSystemNavigator **a3)
{
  struct AppHostFileSystemNavigator **v4; // rbx
  const unsigned __int16 **v6; // rdx
  const unsigned __int16 *v7; // rcx
  int Instance; // eax
  int v9; // eax
  int v10; // eax
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v4 = (struct AppHostFileSystemNavigator **)((char *)this + 32);
  if ( String::QueryCCH((ConfigPathNode *)((char *)this + 40)) && !*v4 )
  {
    v7 = &qword_1800181B0;
    if ( *v6 )
      v7 = *v6;
    Instance = AppHostFileSystemNavigator::CreateInstance(v7, a2[2], v4);
    if ( Instance < 0 )
    {
      pExceptionObject = Instance;
      throw (long *)&pExceptionObject;
    }
  }
  if ( *v4 )
  {
    v9 = AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::Clone(*v4, a3);
    if ( v9 < 0 )
    {
      pExceptionObject = v9;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    v10 = AppHostFileSystemNavigator::CreateInstance(&qword_1800181B0, a2[2], a3);
    if ( v10 < 0 )
    {
      pExceptionObject = v10;
      throw (long *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x18000c770  mov     [rsp+arg_8], rbx
0x18000c775  mov     [rsp+arg_10], rsi
0x18000c77a  push    rdi
0x18000c77b  sub     rsp, 20h
0x18000c77f  mov     rsi, rdx
0x18000c782  lea     rbx, [rcx+20h]
0x18000c786  lea     rdx, [rcx+28h]
0x18000c78a  mov     rdi, r8
0x18000c78d  mov     rcx, rdx; this
0x18000c790  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000c795  test    eax, eax
0x18000c797  jz      short loc_18000C7D4
0x18000c799  cmp     qword ptr [rbx], 0
0x18000c79d  jnz     short loc_18000C7D4
0x18000c79f  cmp     qword ptr [rdx], 0
0x18000c7a3  lea     rcx, qword_1800181B0
0x18000c7aa  mov     r8, rbx; struct AppHostFileSystemNavigator **
0x18000c7ad  cmovnz  rcx, [rdx]; unsigned __int16 *
0x18000c7b1  mov     rdx, [rsi+10h]; struct ConfigNameTablePair *
0x18000c7b5  call    ?CreateInstance@AppHostFileSystemNavigator@@SAJPEBGPEAVConfigNameTablePair@@PEAPEAV1@@Z; AppHostFileSystemNavigator::CreateInstance(ushort const *,ConfigNameTablePair *,AppHostFileSystemNavigator * *)
0x18000c7ba  test    eax, eax
0x18000c7bc  jns     short loc_18000C7D4
0x18000c7be  lea     rdx, _TI1J; pThrowInfo
0x18000c7c5  mov     [rsp+28h+pExceptionObject], eax
0x18000c7c9  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c7ce  call    _CxxThrowException_0
0x18000c7d4  mov     rcx, [rbx]
0x18000c7d7  test    rcx, rcx
0x18000c7da  jz      short loc_18000C7FE
0x18000c7dc  mov     rdx, rdi
0x18000c7df  call    ?Clone@?$AppHostNavigatorTemplate@VAppHostFileSystemNavigator@@UIAppHostFileSystemNavigator@@VFileSystemTree@@@@QEAAJPEAPEAVAppHostFileSystemNavigator@@@Z; AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::Clone(AppHostFileSystemNavigator * *)
0x18000c7e4  test    eax, eax
0x18000c7e6  jns     short loc_18000C82B
0x18000c7e8  lea     rdx, _TI1J; pThrowInfo
0x18000c7ef  mov     [rsp+28h+pExceptionObject], eax
0x18000c7f3  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c7f8  call    _CxxThrowException_0
0x18000c7fe  mov     rdx, [rsi+10h]; struct ConfigNameTablePair *
0x18000c802  lea     rcx, qword_1800181B0; unsigned __int16 *
0x18000c809  mov     r8, rdi; struct AppHostFileSystemNavigator **
0x18000c80c  call    ?CreateInstance@AppHostFileSystemNavigator@@SAJPEBGPEAVConfigNameTablePair@@PEAPEAV1@@Z; AppHostFileSystemNavigator::CreateInstance(ushort const *,ConfigNameTablePair *,AppHostFileSystemNavigator * *)
0x18000c811  test    eax, eax
0x18000c813  jns     short loc_18000C82B
0x18000c815  lea     rdx, _TI1J; pThrowInfo
0x18000c81c  mov     [rsp+28h+pExceptionObject], eax
0x18000c820  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c825  call    _CxxThrowException_0
0x18000c82b  mov     rbx, [rsp+28h+arg_8]
0x18000c830  mov     rsi, [rsp+28h+arg_10]
0x18000c835  add     rsp, 20h
0x18000c839  pop     rdi
0x18000c83a  retn
```
