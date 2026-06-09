# StateRepository::ResourcePriority::AutoPriority::Revert(void)

- ea: `0x180029b24`
- end: `0x180029bf3`
- name: `?Revert@AutoPriority@ResourcePriority@StateRepository@@QEAAJXZ`
- size: `207`
- prototype: `int(StateRepository::ResourcePriority::AutoPriority *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180018254`

## callees

- `0x18000c3bc`
- `0x180019730`
- `0x180019788`
- `0x1800197e0`
- `0x180019838`
- `0x180029b24`

## string_xrefs

- `0x180029b46`: `onecore\base\appmodel\staterepository\dataaccesslayer\resourcepriority.cpp`
- `0x180029b6e`: `onecore\base\appmodel\staterepository\dataaccesslayer\resourcepriority.cpp`
- `0x180029b9b`: `onecore\base\appmodel\staterepository\dataaccesslayer\resourcepriority.cpp`
- `0x180029bc8`: `onecore\base\appmodel\staterepository\dataaccesslayer\resourcepriority.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::ResourcePriority::AutoPriority::Revert(
        StateRepository::ResourcePriority::AutoPriority *this)
{
  int v2; // eax
  int v3; // ebx
  int v4; // eax
  int v5; // esi
  int v6; // eax
  int v7; // esi
  int v8; // eax
  unsigned int v9; // edi
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::Revert();
  v3 = v2;
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\resourcepriority.cpp",
      (const char *)(unsigned int)v2,
      v11);
  v4 = StateRepository::ResourcePriority::AutoThreadPriority<24,unsigned long,_MEMORY_PRIORITY_INFORMATION>::Revert((char *)this + 16);
  v5 = v4;
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\resourcepriority.cpp",
      (const char *)(unsigned int)v4,
      v11);
  if ( v3 >= 0 )
    v3 = v5;
  v6 = StateRepository::ResourcePriority::AutoThreadPriority<22,enum _IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::Revert((char *)this + 32);
  v7 = v6;
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\resourcepriority.cpp",
      (const char *)(unsigned int)v6,
      v11);
  if ( v3 >= 0 )
    v3 = v7;
  v8 = StateRepository::ResourcePriority::AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>::Revert((char *)this + 48);
  v9 = v8;
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\resourcepriority.cpp",
      (const char *)(unsigned int)v8,
      v11);
  if ( v3 >= 0 )
    return v9;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180029b24  mov     [rsp+arg_0], rbx
0x180029b29  mov     [rsp+arg_8], rsi
0x180029b2e  push    rdi; int
0x180029b2f  sub     rsp, 20h
0x180029b33  mov     rdi, rcx
0x180029b36  call    ?Revert@?$AutoThreadPriority@$0BJ@JJ@ResourcePriority@StateRepository@@QEAAJXZ; StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::Revert(void)
0x180029b3b  mov     ebx, eax
0x180029b3d  test    eax, eax
0x180029b3f  jns     short loc_180029B5A
0x180029b41  mov     rcx, [rsp+28h]; this
0x180029b46  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x180029b4d  mov     r9d, eax; char *
0x180029b50  mov     edx, 78h ; 'x'; void *
0x180029b55  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029b5a  lea     rcx, [rdi+10h]
0x180029b5e  call    ?Revert@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@QEAAJXZ; StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::Revert(void)
0x180029b63  mov     esi, eax
0x180029b65  test    eax, eax
0x180029b67  jns     short loc_180029B82
0x180029b69  mov     rcx, [rsp+28h]; this
0x180029b6e  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x180029b75  mov     r9d, eax; char *
0x180029b78  mov     edx, 79h ; 'y'; void *
0x180029b7d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029b82  test    ebx, ebx
0x180029b84  lea     rcx, [rdi+20h]
0x180029b88  cmovns  ebx, esi
0x180029b8b  call    ?Revert@?$AutoThreadPriority@$0BG@W4_IO_PRIORITY_HINT@@U_FILE_IO_PRIORITY_HINT_INFORMATION@@@ResourcePriority@StateRepository@@QEAAJXZ; StateRepository::ResourcePriority::AutoThreadPriority<22,_IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::Revert(void)
0x180029b90  mov     esi, eax
0x180029b92  test    eax, eax
0x180029b94  jns     short loc_180029BAF
0x180029b96  mov     rcx, [rsp+28h]; this
0x180029b9b  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x180029ba2  mov     r9d, eax; char *
0x180029ba5  mov     edx, 7Ah ; 'z'; void *
0x180029baa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029baf  test    ebx, ebx
0x180029bb1  lea     rcx, [rdi+30h]
0x180029bb5  cmovns  ebx, esi
0x180029bb8  call    ?Revert@?$AutoThreadPriority@$0DB@_NU_THREAD_POWER_THROTTLING_STATE@@@ResourcePriority@StateRepository@@QEAAJXZ; StateRepository::ResourcePriority::AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>::Revert(void)
0x180029bbd  mov     edi, eax
0x180029bbf  test    eax, eax
0x180029bc1  jns     short loc_180029BDC
0x180029bc3  mov     rcx, [rsp+28h]; this
0x180029bc8  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x180029bcf  mov     r9d, eax; char *
0x180029bd2  mov     edx, 7Bh ; '{'; void *
0x180029bd7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029bdc  mov     rsi, [rsp+28h+arg_8]
0x180029be1  test    ebx, ebx
0x180029be3  cmovns  ebx, edi
0x180029be6  mov     eax, ebx
0x180029be8  mov     rbx, [rsp+28h+arg_0]
0x180029bed  add     rsp, 20h
0x180029bf1  pop     rdi
0x180029bf2  retn
```
