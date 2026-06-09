# SRCacheContext_Create

- ea: `0x18000caa0`
- end: `0x18000cb53`
- name: `SRCacheContext_Create`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000bf44`
- `0x18000bf7c`
- `0x18000c05c`
- `0x18000caa0`

## string_xrefs

- `0x18000cad2`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000cb08`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_Create(
        Common::RegistryKey *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        SRCacheContext **a4)
{
  SRCacheContext *v7; // rbx
  int v9; // eax
  unsigned int v10; // edx
  unsigned int v11; // edi
  unsigned int v12; // edx
  SRCacheContext *v13; // rax
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  SRCacheContext *v16; // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  wil::make_unique_nothrow<SRCacheContext,>(&v16);
  v7 = v16;
  if ( v16 )
  {
    v9 = SRCacheContext::Create(v16, a1, a2);
    v11 = v9;
    if ( v9 >= 0 )
    {
      if ( *(_QWORD *)v7 )
      {
        v13 = v7;
        v7 = 0;
        *a4 = v13;
      }
      if ( v7 )
        SRCacheContext::`scalar deleting destructor'(v7, v10);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DF,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
        (const char *)(unsigned int)v9,
        v14);
      if ( v7 )
        SRCacheContext::`scalar deleting destructor'(v7, v12);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)0x8007000ELL,
      v14);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000caa0  push    rbx
0x18000caa2  push    rbp
0x18000caa3  push    rsi
0x18000caa4  push    rdi
0x18000caa5  sub     rsp, 28h
0x18000caa9  mov     rbp, rcx
0x18000caac  mov     qword ptr [r9], 0
0x18000cab3  lea     rcx, [rsp+48h+arg_18]
0x18000cab8  mov     rsi, r9
0x18000cabb  mov     rdi, rdx
0x18000cabe  call    ??$make_unique_nothrow@USRCacheContext@@$$V@wil@@YA?AV?$unique_ptr@USRCacheContext@@U?$default_delete@USRCacheContext@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<SRCacheContext,>(void)
0x18000cac3  mov     rbx, [rsp+48h+arg_18]
0x18000cac8  test    rbx, rbx
0x18000cacb  jnz     short loc_18000CAEF
0x18000cacd  mov     rcx, [rsp+48h]; this
0x18000cad2  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cad9  mov     ebx, 8007000Eh
0x18000cade  mov     edx, 1DDh; void *
0x18000cae3  mov     r9d, ebx; char *
0x18000cae6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000caeb  mov     eax, ebx
0x18000caed  jmp     short loc_18000CB4A
0x18000caef  mov     r8, rdi
0x18000caf2  mov     rdx, rbp
0x18000caf5  mov     rcx, rbx
0x18000caf8  call    ?Create@SRCacheContext@@QEAAJAEAUSRCacheManager@@PEBGW4SRCacheFlags@@@Z; SRCacheContext::Create(SRCacheManager &,ushort const *,SRCacheFlags)
0x18000cafd  mov     edi, eax
0x18000caff  test    eax, eax
0x18000cb01  jns     short loc_18000CB2D
0x18000cb03  mov     rcx, [rsp+48h]; this
0x18000cb08  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cb0f  mov     r9d, eax; char *
0x18000cb12  mov     edx, 1DFh; void *
0x18000cb17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb1c  test    rbx, rbx
0x18000cb1f  jz      short loc_18000CB29
0x18000cb21  mov     rcx, rbx; this
0x18000cb24  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000cb29  mov     eax, edi
0x18000cb2b  jmp     short loc_18000CB4A
0x18000cb2d  cmp     qword ptr [rbx], 0
0x18000cb31  jz      short loc_18000CB3B
0x18000cb33  mov     rax, rbx
0x18000cb36  xor     ebx, ebx
0x18000cb38  mov     [rsi], rax
0x18000cb3b  test    rbx, rbx
0x18000cb3e  jz      short loc_18000CB48
0x18000cb40  mov     rcx, rbx; this
0x18000cb43  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000cb48  xor     eax, eax
0x18000cb4a  add     rsp, 28h
0x18000cb4e  pop     rdi
0x18000cb4f  pop     rsi
0x18000cb50  pop     rbp
0x18000cb51  pop     rbx
0x18000cb52  retn
```
