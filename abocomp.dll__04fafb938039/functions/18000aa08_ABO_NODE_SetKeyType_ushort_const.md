# ABO_NODE::SetKeyType(ushort const *)

- ea: `0x18000aa08`
- end: `0x18000aaa1`
- name: `?SetKeyType@ABO_NODE@@QEAAJPEBG@Z`
- size: `153`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004f98`
- `0x180006e28`
- `0x180008050`
- `0x1800259c0`

## callees

- `0x18000aa08`
- `0x18001015c`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000aa8b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000aa8b`

## pseudocode

```c
int __fastcall ABO_NODE::SetKeyType(ABO_NODE *this, unsigned __int8 *a2)
{
  int result; // eax
  __int64 v5; // rax
  struct _METADATA_RECORD v6; // [rsp+20h] [rbp-38h] BYREF

  *(&v6.dwMDDataLen + 1) = 0;
  *(_QWORD *)&v6.dwMDDataTag = 0;
  if ( !a2 )
    return -2147024809;
  *(_QWORD *)&v6.dwMDIdentifier = 1002;
  v6.dwMDUserType = 1;
  v5 = -1;
  v6.dwMDDataType = 2;
  do
    ++v5;
  while ( *(_WORD *)&a2[2 * v5] );
  v6.pbMDData = a2;
  v6.dwMDDataLen = 2 * v5 + 2;
  result = PROPERTY_BAG::SetData((ABO_NODE *)((char *)this + 184), &v6, 1, 0);
  if ( result >= 0 )
    return STRU::Copy((ABO_NODE *)((char *)this + 120), (const unsigned __int16 *)a2);
  return result;
}

```

## disassembly

```asm
0x18000aa08  mov     rax, rsp
0x18000aa0b  mov     [rax+8], rbx
0x18000aa0f  mov     [rax+10h], rsi
0x18000aa13  push    rdi
0x18000aa14  sub     rsp, 50h
0x18000aa18  xor     esi, esi
0x18000aa1a  mov     rbx, rdx
0x18000aa1d  mov     [rax-24h], esi
0x18000aa20  mov     rdi, rcx
0x18000aa23  mov     [rax-18h], rsi
0x18000aa27  test    rdx, rdx
0x18000aa2a  jnz     short loc_18000AA33
0x18000aa2c  mov     eax, 80070057h
0x18000aa31  jmp     short loc_18000AA91
0x18000aa33  mov     r8d, 1; int
0x18000aa39  mov     qword ptr [rsp+58h+var_38.dwMDIdentifier], 3EAh
0x18000aa42  mov     [rsp+58h+var_38.dwMDUserType], r8d
0x18000aa47  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000aa4b  mov     [rsp+58h+var_38.dwMDDataType], 2
0x18000aa53  inc     rax
0x18000aa56  cmp     [rdx+rax*2], si
0x18000aa5a  jnz     short loc_18000AA53
0x18000aa5c  lea     eax, ds:2[rax*2]
0x18000aa63  mov     [rsp+58h+var_38.pbMDData], rbx
0x18000aa68  add     rcx, 0B8h; this
0x18000aa6f  mov     [rsp+58h+var_38.dwMDDataLen], eax
0x18000aa73  xor     r9d, r9d; struct PROPERTY_ENTRY **
0x18000aa76  lea     rdx, [rsp+58h+var_38]; struct _METADATA_RECORD *
0x18000aa7b  call    ?SetData@PROPERTY_BAG@@QEAAJPEAU_METADATA_RECORD@@HPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::SetData(_METADATA_RECORD *,int,PROPERTY_ENTRY * *)
0x18000aa80  test    eax, eax
0x18000aa82  js      short loc_18000AA91
0x18000aa84  lea     rcx, [rdi+78h]
0x18000aa88  mov     rdx, rbx
0x18000aa8b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000aa91  mov     rbx, [rsp+58h+arg_0]
0x18000aa96  mov     rsi, [rsp+58h+arg_8]
0x18000aa9b  add     rsp, 50h
0x18000aa9f  pop     rdi
0x18000aaa0  retn
```
