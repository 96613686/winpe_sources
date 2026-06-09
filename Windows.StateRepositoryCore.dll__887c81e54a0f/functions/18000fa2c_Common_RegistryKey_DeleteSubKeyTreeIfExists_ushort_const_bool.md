# Common::RegistryKey::DeleteSubKeyTreeIfExists(ushort const *,bool *)

- ea: `0x18000fa2c`
- end: `0x18000fa81`
- name: `?DeleteSubKeyTreeIfExists@RegistryKey@Common@@QEAAJPEBGPEA_N@Z`
- size: `85`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c154`

## callees

- `0x18000940c`
- `0x18000fa08`
- `0x18000fa2c`

## string_xrefs

- `0x18000fa58`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c
__int64 __fastcall Common::RegistryKey::DeleteSubKeyTreeIfExists(HKEY *this, const unsigned __int16 *a2, bool *a3)
{
  LSTATUS v4; // ebx
  bool v5; // al
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = Common::RegistryKey::DeleteSubKeyTree(this, a2);
  v5 = 1;
  if ( (unsigned int)(v4 + 2147024894) <= 1 )
  {
    v5 = 0;
  }
  else if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
      (const char *)(unsigned int)v4,
      v7);
    return (unsigned int)v4;
  }
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000fa2c  mov     [rsp+arg_0], rbx
0x18000fa31  push    rdi; int
0x18000fa32  sub     rsp, 20h
0x18000fa36  mov     rdi, r8
0x18000fa39  call    ?DeleteSubKeyTree@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteSubKeyTree(ushort const *)
0x18000fa3e  mov     ebx, eax
0x18000fa40  lea     ecx, [rax+7FF8FFFEh]
0x18000fa46  mov     eax, 1
0x18000fa4b  cmp     ecx, eax
0x18000fa4d  jbe     short loc_18000FA70
0x18000fa4f  test    ebx, ebx
0x18000fa51  jns     short loc_18000FA72
0x18000fa53  mov     rcx, [rsp+28h]; this
0x18000fa58  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\regist"...
0x18000fa5f  mov     r9d, ebx; char *
0x18000fa62  mov     edx, 105h; void *
0x18000fa67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa6c  mov     eax, ebx
0x18000fa6e  jmp     short loc_18000FA76
0x18000fa70  xor     al, al
0x18000fa72  mov     [rdi], al
0x18000fa74  xor     eax, eax
0x18000fa76  mov     rbx, [rsp+28h+arg_0]
0x18000fa7b  add     rsp, 20h
0x18000fa7f  pop     rdi
0x18000fa80  retn
```
