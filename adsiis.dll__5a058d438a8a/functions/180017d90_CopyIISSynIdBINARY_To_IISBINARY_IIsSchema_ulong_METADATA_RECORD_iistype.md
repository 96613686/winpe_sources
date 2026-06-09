# CopyIISSynIdBINARY_To_IISBINARY(IIsSchema *,ulong,_METADATA_RECORD *,_iistype *)

- ea: `0x180017d90`
- end: `0x180017e26`
- name: `?CopyIISSynIdBINARY_To_IISBINARY@@YAPEAU_METADATA_RECORD@@PEAVIIsSchema@@KPEAU1@PEAU_iistype@@@Z`
- size: `150`
- prototype: `struct _METADATA_RECORD *__fastcall(struct IIsSchema *, unsigned int, struct _METADATA_RECORD *, struct _iistype *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017f6c`

## callees

- `0x180017d90`
- `0x18001b444`
- `0x18001d652`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x180017deb`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017deb`

## pseudocode

```c
struct _METADATA_RECORD *__fastcall CopyIISSynIdBINARY_To_IISBINARY(
        struct IIsSchema *a1,
        unsigned int a2,
        struct _METADATA_RECORD *a3,
        struct _iistype *a4)
{
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rbx
  DWORD v10; // [rsp+38h] [rbp+10h] BYREF
  DWORD v11; // [rsp+40h] [rbp+18h] BYREF

  v10 = 0;
  v11 = 0;
  IIsSchema::LookupMDFlags(a1, a2, &v10, &v11);
  a3->dwMDAttributes = v10;
  a3->dwMDUserType = v11;
  a3->dwMDIdentifier = a2;
  *(_QWORD *)&a3->dwMDDataType = 3;
  a3->pbMDData = 0;
  if ( a4 )
  {
    v7 = (unsigned __int8 *)AllocADsMem(*((_DWORD *)a4 + 2));
    v8 = v7;
    if ( v7 )
    {
      memcpy_0(v7, *((const void **)a4 + 2), *((unsigned int *)a4 + 2));
      a3->pbMDData = v8;
      a3->dwMDDataLen = *((_DWORD *)a4 + 2);
    }
  }
  return a3;
}

```

## disassembly

```asm
0x180017d90  mov     rax, rsp
0x180017d93  mov     [rax+8], rbx
0x180017d97  mov     [rax+20h], rsi
0x180017d9b  push    rdi
0x180017d9c  sub     rsp, 20h
0x180017da0  mov     rsi, r9
0x180017da3  mov     dword ptr [rax+10h], 0
0x180017daa  mov     rdi, r8
0x180017dad  mov     dword ptr [rax+18h], 0
0x180017db4  lea     r9, [rax+18h]; unsigned int *
0x180017db8  mov     ebx, edx
0x180017dba  lea     r8, [rax+10h]; unsigned int *
0x180017dbe  call    ?LookupMDFlags@IIsSchema@@QEAAJKPEAK0@Z; IIsSchema::LookupMDFlags(ulong,ulong *,ulong *)
0x180017dc3  mov     eax, [rsp+28h+arg_8]
0x180017dc7  mov     [rdi+4], eax
0x180017dca  mov     eax, [rsp+28h+arg_10]
0x180017dce  mov     [rdi+8], eax
0x180017dd1  mov     [rdi], ebx
0x180017dd3  mov     qword ptr [rdi+0Ch], 3
0x180017ddb  mov     qword ptr [rdi+18h], 0
0x180017de3  test    rsi, rsi
0x180017de6  jz      short loc_180017E13
0x180017de8  mov     ecx, [rsi+8]; cb
0x180017deb  call    cs:__imp_AllocADsMem
0x180017df1  mov     rbx, rax
0x180017df4  test    rax, rax
0x180017df7  jz      short loc_180017E13
0x180017df9  mov     r8d, [rsi+8]; Size
0x180017dfd  mov     rcx, rax; void *
0x180017e00  mov     rdx, [rsi+10h]; Src
0x180017e04  call    memcpy_0
0x180017e09  mov     [rdi+18h], rbx
0x180017e0d  mov     eax, [rsi+8]
0x180017e10  mov     [rdi+10h], eax
0x180017e13  mov     rbx, [rsp+28h+arg_0]
0x180017e18  mov     rax, rdi
0x180017e1b  mov     rsi, [rsp+28h+arg_18]
0x180017e20  add     rsp, 20h
0x180017e24  pop     rdi
0x180017e25  retn
```
