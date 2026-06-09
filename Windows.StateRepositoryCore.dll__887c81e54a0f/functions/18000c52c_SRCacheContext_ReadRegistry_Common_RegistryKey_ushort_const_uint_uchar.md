# SRCacheContext::ReadRegistry(Common::RegistryKey &,ushort const *,uint &,uchar * *)

- ea: `0x18000c52c`
- end: `0x18000c691`
- name: `?ReadRegistry@SRCacheContext@@CAJAEAVRegistryKey@Common@@PEBGAEAIPEAPEAE@Z`
- size: `357`
- prototype: `__int64 __fastcall(struct Common::RegistryKey *this, const unsigned __int16 *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000cde0`

## callees

- `0x1800022a0`
- `0x18000940c`
- `0x18000be7c`
- `0x18000c52c`
- `0x18000c7d0`
- `0x18000fc70`

## string_xrefs

- `0x18000c5ec`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000c66f`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext::ReadRegistry(
        struct Common::RegistryKey *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  unsigned int v8; // edi
  void *v9; // rbx
  int Value; // eax
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  const char *v13; // r9
  unsigned int v14; // edi
  unsigned __int64 v15; // rdx
  unsigned __int8 *v17; // rax
  unsigned int v18; // ebx
  __int64 v19; // rdx
  unsigned int v20; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int i; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v23; // [rsp+70h] [rbp+18h] BYREF
  void *v24; // [rsp+78h] [rbp+20h] BYREF

  *a3 = 0;
  *a4 = 0;
  if ( (unsigned __int64)(*(_QWORD *)this - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v18 = -2147019873;
    v19 = 230;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v18,
      v20);
    return v18;
  }
  else
  {
    v8 = 1024;
    for ( i = 1024; ; v8 = i )
    {
      wil::make_unique_nothrow<unsigned char [0]>(&v24, v8);
      v9 = v24;
      if ( !v24 )
      {
        v18 = -2147024882;
        v19 = 235;
        goto LABEL_23;
      }
      v23 = 4;
      Value = Common::RegistryKey::GetValue(this, a2, v8, &i, v24, &v23);
      v14 = Value;
      if ( Value >= 0 )
        break;
      if ( (unsigned int)(Value + 2147024894) <= 1 )
      {
        v14 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xFE, v12, v13, v20);
        goto LABEL_11;
      }
      if ( Value != -2147024662 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x103,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
          (const char *)(unsigned int)Value,
          v20);
LABEL_11:
        if ( v9 )
          operator delete(v9, v15);
        return v14;
      }
      v24 = 0;
      if ( v9 )
        operator delete(v9, v11);
    }
    if ( v23 )
    {
      *a3 = i;
      v17 = (unsigned __int8 *)v9;
      v9 = 0;
    }
    else
    {
      *a3 = 0;
      v17 = 0;
    }
    *a4 = v17;
    if ( v9 )
      operator delete(v9, v11);
    return 0;
  }
}

```

## disassembly

```asm
0x18000c52c  mov     [rsp+arg_8], rbx
0x18000c531  push    rbp
0x18000c532  push    rsi
0x18000c533  push    rdi
0x18000c534  push    r14
0x18000c536  push    r15
0x18000c538  sub     rsp, 30h
0x18000c53c  mov     dword ptr [r8], 0
0x18000c543  mov     r14, r9
0x18000c546  mov     qword ptr [r9], 0
0x18000c54d  mov     rsi, r8
0x18000c550  mov     rax, [rcx]
0x18000c553  mov     rbp, rdx
0x18000c556  dec     rax
0x18000c559  mov     r15, rcx
0x18000c55c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c560  ja      loc_18000C660
0x18000c566  mov     edi, 400h
0x18000c56b  mov     [rsp+58h+arg_0], edi
0x18000c56f  mov     edx, edi
0x18000c571  lea     rcx, [rsp+58h+arg_18]
0x18000c576  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18000c57b  mov     rbx, [rsp+58h+arg_18]
0x18000c580  test    rbx, rbx
0x18000c583  jz      loc_18000C654
0x18000c589  lea     rax, [rsp+58h+arg_10]
0x18000c58e  mov     [rsp+58h+arg_10], 4
0x18000c596  mov     [rsp+58h+var_30], rax; unsigned int *
0x18000c59b  lea     r9, [rsp+58h+arg_0]; unsigned int *
0x18000c5a0  mov     r8d, edi; unsigned int
0x18000c5a3  mov     [rsp+58h+var_38], rbx; unsigned int
0x18000c5a8  mov     rdx, rbp; unsigned __int16 *
0x18000c5ab  mov     rcx, r15; this
0x18000c5ae  call    ?GetValue@RegistryKey@Common@@QEAAJPEBGKPEAKPEAX1@Z; Common::RegistryKey::GetValue(ushort const *,ulong,ulong *,void *,ulong *)
0x18000c5b3  mov     edi, eax
0x18000c5b5  test    eax, eax
0x18000c5b7  jns     short loc_18000C624
0x18000c5b9  lea     ecx, [rax+7FF8FFFEh]
0x18000c5bf  cmp     ecx, 1
0x18000c5c2  jbe     short loc_18000C611
0x18000c5c4  cmp     eax, 800700EAh
0x18000c5c9  jnz     short loc_18000C5E7
0x18000c5cb  mov     [rsp+58h+arg_18], 0
0x18000c5d4  test    rbx, rbx
0x18000c5d7  jz      short loc_18000C5E1
0x18000c5d9  mov     rcx, rbx; void *
0x18000c5dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c5e1  mov     edi, [rsp+58h+arg_0]
0x18000c5e5  jmp     short loc_18000C56F
0x18000c5e7  mov     rcx, [rsp+58h]; this
0x18000c5ec  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c5f3  mov     r9d, edi; char *
0x18000c5f6  mov     edx, 103h; void *
0x18000c5fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c600  test    rbx, rbx
0x18000c603  jz      short loc_18000C60D
0x18000c605  mov     rcx, rbx; void *
0x18000c608  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c60d  mov     eax, edi
0x18000c60f  jmp     short loc_18000C680
0x18000c611  mov     rcx, [rsp+58h]; this
0x18000c616  mov     edx, 0FEh; void *
0x18000c61b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000c620  mov     edi, eax
0x18000c622  jmp     short loc_18000C600
0x18000c624  cmp     [rsp+58h+arg_10], 0
0x18000c629  jnz     short loc_18000C635
0x18000c62b  mov     dword ptr [rsi], 0
0x18000c631  xor     eax, eax
0x18000c633  jmp     short loc_18000C640
0x18000c635  mov     eax, [rsp+58h+arg_0]
0x18000c639  mov     [rsi], eax
0x18000c63b  mov     rax, rbx
0x18000c63e  xor     ebx, ebx
0x18000c640  mov     [r14], rax
0x18000c643  test    rbx, rbx
0x18000c646  jz      short loc_18000C650
0x18000c648  mov     rcx, rbx; void *
0x18000c64b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c650  xor     eax, eax
0x18000c652  jmp     short loc_18000C680
0x18000c654  mov     ebx, 8007000Eh
0x18000c659  mov     edx, 0EBh
0x18000c65e  jmp     short loc_18000C66A
0x18000c660  mov     ebx, 8007139Fh
0x18000c665  mov     edx, 0E6h; void *
0x18000c66a  mov     rcx, [rsp+58h]; this
0x18000c66f  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c676  mov     r9d, ebx; char *
0x18000c679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c67e  mov     eax, ebx
0x18000c680  mov     rbx, [rsp+58h+arg_8]
0x18000c685  add     rsp, 30h
0x18000c689  pop     r15
0x18000c68b  pop     r14
0x18000c68d  pop     rdi
0x18000c68e  pop     rsi
0x18000c68f  pop     rbp
0x18000c690  retn
```
