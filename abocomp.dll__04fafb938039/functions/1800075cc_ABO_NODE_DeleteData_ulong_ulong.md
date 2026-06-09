# ABO_NODE::DeleteData(ulong,ulong)

- ea: `0x1800075cc`
- end: `0x18000766a`
- name: `?DeleteData@ABO_NODE@@QEAAJKK@Z`
- size: `158`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180007724`
- `0x18000cd68`

## callees

- `0x1800075cc`
- `0x1800077dc`
- `0x180009b84`
- `0x18000fde4`
- `0x18000fec4`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000761a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000761a`

## pseudocode

```c
__int64 __fastcall ABO_NODE::DeleteData(ABO_NODE *this, unsigned int a2, int a3)
{
  PROPERTY_BAG *v3; // r14
  int Entry; // eax
  PROPERTY_MAPPING *v8; // rdi
  int v9; // ebx
  PROPERTY_MAPPING *v11; // [rsp+40h] [rbp+8h] BYREF

  v3 = (ABO_NODE *)((char *)this + 184);
  v11 = 0;
  Entry = PROPERTY_BAG::FindEntry((ABO_NODE *)((char *)this + 184), a2, &v11);
  v8 = v11;
  if ( Entry < 0 || a3 && *((_DWORD *)BUFFER::QueryPtr((PROPERTY_MAPPING *)((char *)v11 + 16)) + 3) != a3 )
  {
    v9 = -2146646015;
  }
  else
  {
    v9 = PROPERTY_BAG::DeleteEntry(v3, a2);
    if ( v9 >= 0 && *((_DWORD *)v8 + 16) )
      v9 = ABO_NODE::MapDeleteData(this, v8);
  }
  if ( v8 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800075cc  mov     rax, rsp
0x1800075cf  mov     [rax+10h], rbx
0x1800075d3  mov     [rax+18h], rbp
0x1800075d7  push    rsi
0x1800075d8  push    rdi
0x1800075d9  push    r14
0x1800075db  sub     rsp, 20h
0x1800075df  lea     r14, [rcx+0B8h]
0x1800075e6  mov     qword ptr [rax+8], 0
0x1800075ee  mov     ebx, r8d
0x1800075f1  mov     rsi, rcx
0x1800075f4  mov     rcx, r14; this
0x1800075f7  lea     r8, [rax+8]; struct PROPERTY_ENTRY **
0x1800075fb  mov     ebp, edx
0x1800075fd  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x180007602  mov     rdi, [rsp+38h+arg_0]
0x180007607  test    eax, eax
0x180007609  jns     short loc_180007612
0x18000760b  mov     ebx, 800CC801h
0x180007610  jmp     short loc_180007648
0x180007612  test    ebx, ebx
0x180007614  jz      short loc_180007625
0x180007616  lea     rcx, [rdi+10h]
0x18000761a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180007620  cmp     [rax+0Ch], ebx
0x180007623  jnz     short loc_18000760B
0x180007625  mov     edx, ebp; unsigned int
0x180007627  mov     rcx, r14; this
0x18000762a  call    ?DeleteEntry@PROPERTY_BAG@@QEAAJK@Z; PROPERTY_BAG::DeleteEntry(ulong)
0x18000762f  mov     ebx, eax
0x180007631  test    eax, eax
0x180007633  js      short loc_180007648
0x180007635  cmp     dword ptr [rdi+40h], 0
0x180007639  jz      short loc_180007648
0x18000763b  mov     rdx, rdi; struct PROPERTY_ENTRY *
0x18000763e  mov     rcx, rsi; this
0x180007641  call    ?MapDeleteData@ABO_NODE@@AEAAJPEAVPROPERTY_ENTRY@@@Z; ABO_NODE::MapDeleteData(PROPERTY_ENTRY *)
0x180007646  mov     ebx, eax
0x180007648  test    rdi, rdi
0x18000764b  jz      short loc_180007655
0x18000764d  mov     rcx, rdi; this
0x180007650  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180007655  mov     rbp, [rsp+38h+arg_10]
0x18000765a  mov     eax, ebx
0x18000765c  mov     rbx, [rsp+38h+arg_8]
0x180007661  add     rsp, 20h
0x180007665  pop     r14
0x180007667  pop     rdi
0x180007668  pop     rsi
0x180007669  retn
```
