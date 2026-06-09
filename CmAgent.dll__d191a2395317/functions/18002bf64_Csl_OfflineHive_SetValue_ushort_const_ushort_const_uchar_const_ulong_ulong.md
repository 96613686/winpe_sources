# Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)

- ea: `0x18002bf64`
- end: `0x18002c061`
- name: `?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z`
- size: `253`
- prototype: `__int64 __fastcall(Csl::OfflineHive *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180029928`
- `0x180029ef8`
- `0x18002bca8`

## callees

- `0x180007b4c`
- `0x18002bf64`
- `0x18002c6e0`
- `0x18002d190`
- `0x18002dee0`

## string_xrefs

- `0x18002bfbc`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002c018`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::SetValue(
        Csl::OfflineHive *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 v9; // rbx
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // edi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v18; // [rsp+58h] [rbp+10h] BYREF

  v9 = 0;
  v18 = 0;
  if ( !a2 )
    goto LABEL_10;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  if ( !v10 )
    goto LABEL_10;
  v11 = OROpenKey(*((_QWORD *)this + 1), a2, &v18);
  if ( v11 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1FB,
            (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)v11);
    if ( v18 )
      ORCloseKey(v18);
    return v12;
  }
  v9 = v18;
  v14 = v18;
  if ( !v18 )
LABEL_10:
    v14 = *((_QWORD *)this + 1);
  v15 = ORSetValueInternal(v14, a3, a6, a4, a5);
  if ( v15 )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x203,
            (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)v15);
    if ( v9 )
      ORCloseKey(v9);
    return v16;
  }
  else
  {
    if ( v9 )
      ORCloseKey(v9);
    return 0;
  }
}

```

## disassembly

```asm
0x18002bf64  mov     [rsp+arg_0], rbx
0x18002bf69  mov     [rsp+arg_10], rbp
0x18002bf6e  push    rsi
0x18002bf6f  push    rdi
0x18002bf70  push    r14
0x18002bf72  sub     rsp, 30h
0x18002bf76  mov     rsi, r9
0x18002bf79  mov     rbp, r8
0x18002bf7c  mov     rdi, rcx
0x18002bf7f  xor     r14d, r14d
0x18002bf82  mov     ebx, r14d
0x18002bf85  mov     [rsp+48h+arg_8], rbx
0x18002bf8a  test    rdx, rdx
0x18002bf8d  jz      short loc_18002BFF0
0x18002bf8f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002bf93  inc     rax
0x18002bf96  cmp     [rdx+rax*2], r14w
0x18002bf9b  jnz     short loc_18002BF93
0x18002bf9d  test    rax, rax
0x18002bfa0  jz      short loc_18002BFF0
0x18002bfa2  lea     r8, [rsp+48h+arg_8]
0x18002bfa7  mov     rcx, [rcx+8]
0x18002bfab  call    OROpenKey
0x18002bfb0  test    eax, eax
0x18002bfb2  jz      short loc_18002BFE3
0x18002bfb4  mov     rcx, [rsp+48h]; this
0x18002bfb9  mov     r9d, eax; char *
0x18002bfbc  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002bfc3  mov     edx, 1FBh; void *
0x18002bfc8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002bfcd  mov     ebx, eax
0x18002bfcf  mov     rcx, [rsp+48h+arg_8]
0x18002bfd4  test    rcx, rcx
0x18002bfd7  jz      short loc_18002BFDF
0x18002bfd9  call    ORCloseKey
0x18002bfde  nop
0x18002bfdf  mov     eax, ebx
0x18002bfe1  jmp     short loc_18002C04D
0x18002bfe3  mov     rbx, [rsp+48h+arg_8]
0x18002bfe8  test    rbx, rbx
0x18002bfeb  mov     rcx, rbx
0x18002bfee  jnz     short loc_18002BFF4
0x18002bff0  mov     rcx, [rdi+8]
0x18002bff4  mov     eax, [rsp+48h+arg_20]
0x18002bff8  mov     [rsp+48h+var_28], eax; unsigned int
0x18002bffc  mov     r9, rsi
0x18002bfff  mov     r8d, [rsp+48h+arg_28]
0x18002c004  mov     rdx, rbp
0x18002c007  call    ORSetValueInternal
0x18002c00c  test    eax, eax
0x18002c00e  jz      short loc_18002C03D
0x18002c010  mov     rcx, [rsp+48h]; this
0x18002c015  mov     r9d, eax; char *
0x18002c018  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002c01f  mov     edx, 203h; void *
0x18002c024  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c029  mov     edi, eax
0x18002c02b  test    rbx, rbx
0x18002c02e  jz      short loc_18002C039
0x18002c030  mov     rcx, rbx
0x18002c033  call    ORCloseKey
0x18002c038  nop
0x18002c039  mov     eax, edi
0x18002c03b  jmp     short loc_18002C04D
0x18002c03d  test    rbx, rbx
0x18002c040  jz      short loc_18002C04B
0x18002c042  mov     rcx, rbx
0x18002c045  call    ORCloseKey
0x18002c04a  nop
0x18002c04b  xor     eax, eax
0x18002c04d  mov     rbx, [rsp+48h+arg_0]
0x18002c052  mov     rbp, [rsp+48h+arg_10]
0x18002c057  add     rsp, 30h
0x18002c05b  pop     r14
0x18002c05d  pop     rdi
0x18002c05e  pop     rsi
0x18002c05f  retn
```
