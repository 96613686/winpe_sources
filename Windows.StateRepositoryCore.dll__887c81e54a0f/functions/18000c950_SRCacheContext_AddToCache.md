# SRCacheContext_AddToCache

- ea: `0x18000c950`
- end: `0x18000c9fa`
- name: `SRCacheContext_AddToCache`
- size: `170`
- prototype: `__int64 __fastcall(struct SRCacheContext *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000940c`
- `0x18000bf44`
- `0x18000bf7c`
- `0x18000bfac`
- `0x18000c950`

## string_xrefs

- `0x18000c983`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000c9b6`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_AddToCache(struct SRCacheContext *a1, unsigned __int16 *a2)
{
  RTL_SRWLOCK *v4; // rcx
  HKEY *v5; // rbx
  int v7; // eax
  unsigned int v8; // edi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  SRCacheContext *v10; // [rsp+30h] [rbp+8h] BYREF

  if ( !a1 )
    return 0;
  wil::make_unique_nothrow<SRCacheContext,>(&v10);
  v5 = (HKEY *)v10;
  if ( !v10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CD,
      (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)0x8007000ELL);
    return 2147942414LL;
  }
  v7 = SRCacheContext::AddToCache(v4, a1, a2);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( v5 )
      SRCacheContext::`scalar deleting destructor'(v5);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1CF,
    (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)(unsigned int)v7);
  if ( v5 )
    SRCacheContext::`scalar deleting destructor'(v5);
  return v8;
}

```

## disassembly

```asm
0x18000c950  mov     [rsp+arg_8], rbx
0x18000c955  mov     [rsp+arg_10], rsi
0x18000c95a  push    rdi; int
0x18000c95b  sub     rsp, 20h
0x18000c95f  mov     rsi, rdx
0x18000c962  mov     rdi, rcx
0x18000c965  test    rcx, rcx
0x18000c968  jz      short loc_18000C9E8
0x18000c96a  lea     rcx, [rsp+28h+arg_0]
0x18000c96f  call    ??$make_unique_nothrow@USRCacheContext@@$$V@wil@@YA?AV?$unique_ptr@USRCacheContext@@U?$default_delete@USRCacheContext@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<SRCacheContext,>(void)
0x18000c974  mov     rbx, [rsp+28h+arg_0]
0x18000c979  test    rbx, rbx
0x18000c97c  jnz     short loc_18000C9A0
0x18000c97e  mov     rcx, [rsp+28h]; this
0x18000c983  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c98a  mov     ebx, 8007000Eh
0x18000c98f  mov     edx, 1CDh; void *
0x18000c994  mov     r9d, ebx; char *
0x18000c997  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c99c  mov     eax, ebx
0x18000c99e  jmp     short loc_18000C9EA
0x18000c9a0  mov     r8, rsi; unsigned __int16 *
0x18000c9a3  mov     rdx, rdi; struct SRCacheContext *
0x18000c9a6  call    ?AddToCache@SRCacheContext@@QEAAJAEAU1@PEBG@Z; SRCacheContext::AddToCache(SRCacheContext &,ushort const *)
0x18000c9ab  mov     edi, eax
0x18000c9ad  test    eax, eax
0x18000c9af  jns     short loc_18000C9DB
0x18000c9b1  mov     rcx, [rsp+28h]; this
0x18000c9b6  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c9bd  mov     r9d, eax; char *
0x18000c9c0  mov     edx, 1CFh; void *
0x18000c9c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9ca  test    rbx, rbx
0x18000c9cd  jz      short loc_18000C9D7
0x18000c9cf  mov     rcx, rbx; this
0x18000c9d2  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000c9d7  mov     eax, edi
0x18000c9d9  jmp     short loc_18000C9EA
0x18000c9db  test    rbx, rbx
0x18000c9de  jz      short loc_18000C9E8
0x18000c9e0  mov     rcx, rbx; this
0x18000c9e3  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000c9e8  xor     eax, eax
0x18000c9ea  mov     rbx, [rsp+28h+arg_8]
0x18000c9ef  mov     rsi, [rsp+28h+arg_10]
0x18000c9f4  add     rsp, 20h
0x18000c9f8  pop     rdi
0x18000c9f9  retn
```
