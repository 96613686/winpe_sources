# SRCacheContext::Delete(ushort const *)

- ea: `0x18000c154`
- end: `0x18000c1ff`
- name: `?Delete@SRCacheContext@@QEAAJPEBG@Z`
- size: `171`
- prototype: `__int64 __fastcall(SRCacheContext *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000cc50`

## callees

- `0x18000940c`
- `0x18000c154`
- `0x18000f9d8`
- `0x18000fa2c`

## string_xrefs

- `0x18000c1de`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000c1c5`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext::Delete(SRCacheContext *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  unsigned int v6; // r8d
  __int64 v7; // rdx
  int v8; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  bool v12; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_QWORD *)this )
  {
    v12 = 0;
    v4 = Common::RegistryKey::DeleteSubKeyTreeIfExists(this, a2, &v12);
    if ( (v4 & 0x80000000) == 0 )
    {
      v8 = Common::RegistryKey::DeleteSubKey(this, a2, v6);
      v4 = v8;
      if ( v8 > -2147024895 && (unsigned int)(v8 + 2147024892) > 0x7FF8FFFB )
        return 0;
      v7 = 299;
    }
    else
    {
      v7 = 298;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
      (const char *)v4,
      v10);
    v5 = 94;
  }
  else
  {
    v4 = -2147024809;
    v5 = 91;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)v4,
    v10);
  return v4;
}

```

## disassembly

```asm
0x18000c154  mov     [rsp+arg_8], rbx
0x18000c159  mov     [rsp+arg_10], rsi
0x18000c15e  push    rdi; int
0x18000c15f  sub     rsp, 20h
0x18000c163  cmp     qword ptr [rcx], 0
0x18000c167  mov     rsi, rdx
0x18000c16a  mov     rdi, rcx
0x18000c16d  jnz     short loc_18000C17B
0x18000c16f  mov     ebx, 80070057h
0x18000c174  mov     edx, 5Bh ; '['; unsigned __int16 *
0x18000c179  jmp     short loc_18000C1D9
0x18000c17b  lea     r8, [rsp+28h+arg_0]; bool *
0x18000c180  mov     [rsp+28h+arg_0], 0
0x18000c185  call    ?DeleteSubKeyTreeIfExists@RegistryKey@Common@@QEAAJPEBGPEA_N@Z; Common::RegistryKey::DeleteSubKeyTreeIfExists(ushort const *,bool *)
0x18000c18a  mov     ebx, eax
0x18000c18c  test    eax, eax
0x18000c18e  jns     short loc_18000C197
0x18000c190  mov     edx, 12Ah
0x18000c195  jmp     short loc_18000C1C0
0x18000c197  mov     rdx, rsi; unsigned __int16 *
0x18000c19a  mov     rcx, rdi; this
0x18000c19d  call    ?DeleteSubKey@RegistryKey@Common@@QEAAJPEBGK@Z; Common::RegistryKey::DeleteSubKey(ushort const *,ulong)
0x18000c1a2  mov     ebx, eax
0x18000c1a4  cmp     eax, 80070001h
0x18000c1a9  jle     short loc_18000C1BB
0x18000c1ab  add     eax, 7FF8FFFCh
0x18000c1b0  cmp     eax, 7FF8FFFBh
0x18000c1b5  jbe     short loc_18000C1BB
0x18000c1b7  xor     eax, eax
0x18000c1b9  jmp     short loc_18000C1EF
0x18000c1bb  mov     edx, 12Bh; void *
0x18000c1c0  mov     rcx, [rsp+28h]; this
0x18000c1c5  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\regist"...
0x18000c1cc  mov     r9d, ebx; char *
0x18000c1cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c1d4  mov     edx, 5Eh ; '^'; void *
0x18000c1d9  mov     rcx, [rsp+28h]; this
0x18000c1de  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c1e5  mov     r9d, ebx; char *
0x18000c1e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c1ed  mov     eax, ebx
0x18000c1ef  mov     rbx, [rsp+28h+arg_8]
0x18000c1f4  mov     rsi, [rsp+28h+arg_10]
0x18000c1f9  add     rsp, 20h
0x18000c1fd  pop     rdi
0x18000c1fe  retn
```
