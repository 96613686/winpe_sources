# SRCacheContext_OpenSubContext

- ea: `0x18000d170`
- end: `0x18000d27a`
- name: `SRCacheContext_OpenSubContext`
- size: `266`
- prototype: `__int64 __fastcall(Common::RegistryKey *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000bf44`
- `0x18000bf7c`
- `0x18000d170`
- `0x18000fda8`

## string_xrefs

- `0x18000d1ae`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000d214`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000d228`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_OpenSubContext(
        Common::RegistryKey *this,
        unsigned __int16 *a2,
        char a3,
        SRCacheContext **a4)
{
  SRCacheContext *v8; // rbx
  unsigned int v10; // edi
  __int64 v11; // rdx
  unsigned int v12; // edx
  unsigned int v13; // edx
  int v14; // [rsp+20h] [rbp-18h]
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SRCacheContext *v17; // [rsp+58h] [rbp+20h] BYREF

  *a4 = 0;
  wil::make_unique_nothrow<SRCacheContext,>(&v17);
  v8 = v17;
  if ( !v17 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)0x8007000ELL,
      v14);
    return 2147942414LL;
  }
  if ( !*(_QWORD *)this )
  {
    v10 = -2147024809;
    v11 = 38;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v10,
      v14);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v10,
      v15);
    if ( v8 )
      SRCacheContext::`scalar deleting destructor'(v8, v13);
    return v10;
  }
  v10 = Common::RegistryKey::OpenSubKeyIfExists(this, a2, (a3 & 1) != 0 ? 131359 : 131353, v17);
  if ( (v10 & 0x80000000) != 0 )
  {
    v11 = 41;
    goto LABEL_7;
  }
  if ( *(_QWORD *)v8 )
  {
    *a4 = v8;
  }
  else if ( v8 )
  {
    SRCacheContext::`scalar deleting destructor'(v8, v12);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d170  mov     [rsp+arg_0], rbx
0x18000d175  mov     [rsp+arg_8], rbp
0x18000d17a  push    rsi
0x18000d17b  push    rdi
0x18000d17c  push    r14; int
0x18000d17e  sub     rsp, 20h
0x18000d182  mov     rbp, rcx
0x18000d185  mov     qword ptr [r9], 0
0x18000d18c  lea     rcx, [rsp+38h+arg_18]
0x18000d191  mov     rsi, r9
0x18000d194  mov     edi, r8d
0x18000d197  mov     r14, rdx
0x18000d19a  call    ??$make_unique_nothrow@USRCacheContext@@$$V@wil@@YA?AV?$unique_ptr@USRCacheContext@@U?$default_delete@USRCacheContext@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<SRCacheContext,>(void)
0x18000d19f  mov     rbx, [rsp+38h+arg_18]
0x18000d1a4  test    rbx, rbx
0x18000d1a7  jnz     short loc_18000D1CE
0x18000d1a9  mov     rcx, [rsp+38h]; this
0x18000d1ae  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d1b5  mov     ebx, 8007000Eh
0x18000d1ba  mov     edx, 1A9h; void *
0x18000d1bf  mov     r9d, ebx; char *
0x18000d1c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d1c7  mov     eax, ebx
0x18000d1c9  jmp     loc_18000D267
0x18000d1ce  cmp     qword ptr [rbp+0], 0
0x18000d1d3  jnz     short loc_18000D1E1
0x18000d1d5  mov     edi, 80070057h
0x18000d1da  mov     edx, 26h ; '&'
0x18000d1df  jmp     short loc_18000D20F
0x18000d1e1  and     dil, 1
0x18000d1e5  mov     r9, rbx; struct Common::AutoHandleHKEY *
0x18000d1e8  neg     dil
0x18000d1eb  mov     rdx, r14; unsigned __int16 *
0x18000d1ee  mov     rcx, rbp; this
0x18000d1f1  sbb     r8d, r8d
0x18000d1f4  and     r8d, 6
0x18000d1f8  add     r8d, 20119h; unsigned int
0x18000d1ff  call    ?OpenSubKeyIfExists@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKeyIfExists(ushort const *,ulong,Common::AutoHandleHKEY &)
0x18000d204  mov     edi, eax
0x18000d206  test    eax, eax
0x18000d208  jns     short loc_18000D24D
0x18000d20a  mov     edx, 29h ; ')'; void *
0x18000d20f  mov     rcx, [rsp+38h]; this
0x18000d214  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d21b  mov     r9d, edi; char *
0x18000d21e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d223  mov     rcx, [rsp+38h]; this
0x18000d228  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d22f  mov     r9d, edi; char *
0x18000d232  mov     edx, 1ABh; void *
0x18000d237  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d23c  test    rbx, rbx
0x18000d23f  jz      short loc_18000D249
0x18000d241  mov     rcx, rbx; this
0x18000d244  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000d249  mov     eax, edi
0x18000d24b  jmp     short loc_18000D267
0x18000d24d  cmp     qword ptr [rbx], 0
0x18000d251  jz      short loc_18000D258
0x18000d253  mov     [rsi], rbx
0x18000d256  jmp     short loc_18000D265
0x18000d258  test    rbx, rbx
0x18000d25b  jz      short loc_18000D265
0x18000d25d  mov     rcx, rbx; this
0x18000d260  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000d265  xor     eax, eax
0x18000d267  mov     rbx, [rsp+38h+arg_0]
0x18000d26c  mov     rbp, [rsp+38h+arg_8]
0x18000d271  add     rsp, 20h
0x18000d275  pop     r14
0x18000d277  pop     rdi
0x18000d278  pop     rsi
0x18000d279  retn
```
