# SRCacheContext_CreateSubContext

- ea: `0x18000cb60`
- end: `0x18000cc4a`
- name: `SRCacheContext_CreateSubContext`
- size: `234`
- prototype: `__int64 __fastcall(HKEY *this, unsigned __int16 *, __int64, HKEY **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000bf44`
- `0x18000bf7c`
- `0x18000cb60`
- `0x18000f95c`

## string_xrefs

- `0x18000cb96`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000cbee`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000cc02`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_CreateSubContext(HKEY *this, unsigned __int16 *a2, __int64 a3, HKEY **a4)
{
  __int64 v7; // r9
  HKEY *v8; // rbx
  unsigned int SubKey; // edi
  __int64 v11; // rdx
  struct _SECURITY_ATTRIBUTES *v12; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  SRCacheContext *v14; // [rsp+88h] [rbp+20h] BYREF

  *a4 = 0;
  wil::make_unique_nothrow<SRCacheContext,>(&v14);
  v8 = (HKEY *)v14;
  if ( !v14 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F1,
      (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)0x8007000ELL);
    return 2147942414LL;
  }
  if ( !*this )
  {
    SubKey = -2147024809;
    v11 = 81;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)SubKey);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F3,
      (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)SubKey);
    if ( v8 )
      SRCacheContext::`scalar deleting destructor'(v8);
    return SubKey;
  }
  SubKey = Common::RegistryKey::CreateSubKey(this, a2, 0x2011Fu, v7, v12, (HKEY *)v14);
  if ( (SubKey & 0x80000000) != 0 )
  {
    v11 = 84;
    goto LABEL_7;
  }
  if ( *v8 )
  {
    *a4 = v8;
  }
  else if ( v8 )
  {
    SRCacheContext::`scalar deleting destructor'(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18000cb60  mov     rax, rsp
0x18000cb63  push    rbx
0x18000cb64  push    rbp
0x18000cb65  push    rsi
0x18000cb66  push    rdi
0x18000cb67  sub     rsp, 48h
0x18000cb6b  mov     rdi, rcx
0x18000cb6e  mov     qword ptr [r9], 0
0x18000cb75  lea     rcx, [rax+20h]
0x18000cb79  mov     rsi, r9
0x18000cb7c  mov     rbp, rdx
0x18000cb7f  call    ??$make_unique_nothrow@USRCacheContext@@$$V@wil@@YA?AV?$unique_ptr@USRCacheContext@@U?$default_delete@USRCacheContext@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<SRCacheContext,>(void)
0x18000cb84  mov     rbx, [rsp+68h+arg_18]
0x18000cb8c  test    rbx, rbx
0x18000cb8f  jnz     short loc_18000CBB6
0x18000cb91  mov     rcx, [rsp+68h]; this
0x18000cb96  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cb9d  mov     ebx, 8007000Eh
0x18000cba2  mov     edx, 1F1h; void *
0x18000cba7  mov     r9d, ebx; char *
0x18000cbaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cbaf  mov     eax, ebx
0x18000cbb1  jmp     loc_18000CC41
0x18000cbb6  cmp     qword ptr [rdi], 0
0x18000cbba  jnz     short loc_18000CBC8
0x18000cbbc  mov     edi, 80070057h
0x18000cbc1  mov     edx, 51h ; 'Q'
0x18000cbc6  jmp     short loc_18000CBE9
0x18000cbc8  mov     r8d, 2011Fh; unsigned int
0x18000cbce  mov     [rsp+68h+var_40], rbx; struct Common::AutoHandleHKEY *
0x18000cbd3  mov     rdx, rbp; unsigned __int16 *
0x18000cbd6  mov     rcx, rdi; this
0x18000cbd9  call    ?CreateSubKey@RegistryKey@Common@@QEAAJPEBGKKQEAU_SECURITY_ATTRIBUTES@@AEAVAutoHandleHKEY@2@PEAK@Z; Common::RegistryKey::CreateSubKey(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,Common::AutoHandleHKEY &,ulong *)
0x18000cbde  mov     edi, eax
0x18000cbe0  test    eax, eax
0x18000cbe2  jns     short loc_18000CC27
0x18000cbe4  mov     edx, 54h ; 'T'; void *
0x18000cbe9  mov     rcx, [rsp+68h]; this
0x18000cbee  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cbf5  mov     r9d, edi; char *
0x18000cbf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cbfd  mov     rcx, [rsp+68h]; this
0x18000cc02  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cc09  mov     r9d, edi; char *
0x18000cc0c  mov     edx, 1F3h; void *
0x18000cc11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc16  test    rbx, rbx
0x18000cc19  jz      short loc_18000CC23
0x18000cc1b  mov     rcx, rbx; this
0x18000cc1e  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000cc23  mov     eax, edi
0x18000cc25  jmp     short loc_18000CC41
0x18000cc27  cmp     qword ptr [rbx], 0
0x18000cc2b  jz      short loc_18000CC32
0x18000cc2d  mov     [rsi], rbx
0x18000cc30  jmp     short loc_18000CC3F
0x18000cc32  test    rbx, rbx
0x18000cc35  jz      short loc_18000CC3F
0x18000cc37  mov     rcx, rbx; this
0x18000cc3a  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000cc3f  xor     eax, eax
0x18000cc41  add     rsp, 48h
0x18000cc45  pop     rdi
0x18000cc46  pop     rsi
0x18000cc47  pop     rbp
0x18000cc48  pop     rbx
0x18000cc49  retn
```
