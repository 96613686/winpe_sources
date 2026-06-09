# SRCacheContext_Open

- ea: `0x18000d090`
- end: `0x18000d15c`
- name: `SRCacheContext_Open`
- size: `204`
- prototype: `__int64 __fastcall(Common::RegistryKey *, const unsigned __int16 *, char, HKEY **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000bf44`
- `0x18000bf7c`
- `0x18000c430`
- `0x18000d090`

## string_xrefs

- `0x18000d0ce`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000d107`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_Open(Common::RegistryKey *a1, const unsigned __int16 *a2, char a3, HKEY **a4)
{
  HKEY *v8; // rbx
  int v10; // eax
  unsigned int v11; // edi
  HKEY *v12; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SRCacheContext *v14; // [rsp+58h] [rbp+20h] BYREF

  *a4 = 0;
  wil::make_unique_nothrow<SRCacheContext,>(&v14);
  v8 = (HKEY *)v14;
  if ( v14 )
  {
    v10 = SRCacheContext::Open((HKEY *)v14, a1, a2, a3);
    v11 = v10;
    if ( v10 >= 0 )
    {
      if ( *v8 )
      {
        v12 = v8;
        v8 = 0;
        *a4 = v12;
      }
      if ( v8 )
        SRCacheContext::`scalar deleting destructor'(v8);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x191,
        (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
        (const char *)(unsigned int)v10);
      if ( v8 )
        SRCacheContext::`scalar deleting destructor'(v8);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18F,
      (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)0x8007000ELL);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000d090  mov     [rsp+arg_0], rbx
0x18000d095  mov     [rsp+arg_8], rbp
0x18000d09a  push    rsi
0x18000d09b  push    rdi
0x18000d09c  push    r14; int
0x18000d09e  sub     rsp, 20h
0x18000d0a2  mov     r14, rcx
0x18000d0a5  mov     qword ptr [r9], 0
0x18000d0ac  lea     rcx, [rsp+38h+arg_18]
0x18000d0b1  mov     rsi, r9
0x18000d0b4  mov     edi, r8d
0x18000d0b7  mov     rbp, rdx
0x18000d0ba  call    ??$make_unique_nothrow@USRCacheContext@@$$V@wil@@YA?AV?$unique_ptr@USRCacheContext@@U?$default_delete@USRCacheContext@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<SRCacheContext,>(void)
0x18000d0bf  mov     rbx, [rsp+38h+arg_18]
0x18000d0c4  test    rbx, rbx
0x18000d0c7  jnz     short loc_18000D0EB
0x18000d0c9  mov     rcx, [rsp+38h]; this
0x18000d0ce  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d0d5  mov     ebx, 8007000Eh
0x18000d0da  mov     edx, 18Fh; void *
0x18000d0df  mov     r9d, ebx; char *
0x18000d0e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d0e7  mov     eax, ebx
0x18000d0e9  jmp     short loc_18000D149
0x18000d0eb  mov     r9d, edi
0x18000d0ee  mov     r8, rbp
0x18000d0f1  mov     rdx, r14
0x18000d0f4  mov     rcx, rbx
0x18000d0f7  call    ?Open@SRCacheContext@@QEAAJAEAUSRCacheManager@@PEBGW4SRCacheFlags@@@Z; SRCacheContext::Open(SRCacheManager &,ushort const *,SRCacheFlags)
0x18000d0fc  mov     edi, eax
0x18000d0fe  test    eax, eax
0x18000d100  jns     short loc_18000D12C
0x18000d102  mov     rcx, [rsp+38h]; this
0x18000d107  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d10e  mov     r9d, eax; char *
0x18000d111  mov     edx, 191h; void *
0x18000d116  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d11b  test    rbx, rbx
0x18000d11e  jz      short loc_18000D128
0x18000d120  mov     rcx, rbx; this
0x18000d123  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000d128  mov     eax, edi
0x18000d12a  jmp     short loc_18000D149
0x18000d12c  cmp     qword ptr [rbx], 0
0x18000d130  jz      short loc_18000D13A
0x18000d132  mov     rax, rbx
0x18000d135  xor     ebx, ebx
0x18000d137  mov     [rsi], rax
0x18000d13a  test    rbx, rbx
0x18000d13d  jz      short loc_18000D147
0x18000d13f  mov     rcx, rbx; this
0x18000d142  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000d147  xor     eax, eax
0x18000d149  mov     rbx, [rsp+38h+arg_0]
0x18000d14e  mov     rbp, [rsp+38h+arg_8]
0x18000d153  add     rsp, 20h
0x18000d157  pop     r14
0x18000d159  pop     rdi
0x18000d15a  pop     rsi
0x18000d15b  retn
```
