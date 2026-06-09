# COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)

- ea: `0x180005ba8`
- end: `0x180005c88`
- name: `?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z`
- size: `224`
- prototype: `__int64 __fastcall(COMMAND_OBJECT *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `18`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006b6c`
- `0x180010850`
- `0x1800122a8`
- `0x180013d88`
- `0x180014ff0`
- `0x180015844`
- `0x180016cd0`
- `0x1800172ec`
- `0x180018540`
- `0x180018b78`
- `0x180018d80`
- `0x18001e418`
- `0x18001ed98`
- `0x18001f120`
- `0x18001fe54`
- `0x180023110`
- `0x1800267d4`
- `0x180026aec`

## callees

- `0x180001044`
- `0x180005ba8`
- `0x180005d74`
- `0x180006784`
- `0x180007f44`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall COMMAND_OBJECT::AddAttribute(
        COMMAND_OBJECT *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  ATTRIBUTE_ENTRY *Attribute; // rax
  struct IArrayListEntry *v7; // rax
  struct IArrayListEntry *v8; // rbx
  int v9; // edi

  Attribute = COMMAND_OBJECT::FindAttribute(this, a2);
  if ( Attribute )
  {
    return (unsigned int)ATTRIBUTE_ENTRY::Create(Attribute, a2, a3);
  }
  else
  {
    v7 = (struct IArrayListEntry *)operator new(0x78u);
    v8 = v7;
    if ( v7 )
    {
      *(_QWORD *)v7 = &PARAMETER_ENTRY::`vftable';
      *((_DWORD *)v7 + 12) = 32;
      *((_QWORD *)v7 + 1) = 0;
      *((_QWORD *)v7 + 5) = (char *)v7 + 8;
      *((_WORD *)v7 + 26) = 256;
      *((_DWORD *)v7 + 14) = 0;
      *((_DWORD *)v7 + 26) = 32;
      *((_QWORD *)v7 + 8) = 0;
      *((_QWORD *)v7 + 12) = (char *)v7 + 64;
      *((_WORD *)v7 + 54) = 256;
      *((_DWORD *)v7 + 28) = 0;
      v9 = ATTRIBUTE_ENTRY::Create(v7, a2, a3);
      if ( v9 < 0 || (v9 = ARRAY_LIST::AddEntry((COMMAND_OBJECT *)((char *)this + 200), v8, 0xFFFFFFFF), v9 < 0) )
        (**(void (__fastcall ***)(struct IArrayListEntry *))v8)(v8);
    }
    else
    {
      return (unsigned int)-2147024888;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180005ba8  push    rbx
0x180005baa  push    rbp
0x180005bab  push    rsi
0x180005bac  push    rdi
0x180005bad  sub     rsp, 28h
0x180005bb1  mov     rbp, r8
0x180005bb4  mov     rdi, rdx
0x180005bb7  mov     rsi, rcx
0x180005bba  call    ?FindAttribute@COMMAND_OBJECT@@AEAAPEAVATTRIBUTE_ENTRY@@PEBG@Z; COMMAND_OBJECT::FindAttribute(ushort const *)
0x180005bbf  test    rax, rax
0x180005bc2  jnz     loc_180005C6D
0x180005bc8  lea     ecx, [rax+78h]; Size
0x180005bcb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005bd0  mov     rbx, rax
0x180005bd3  test    rax, rax
0x180005bd6  jz      loc_180005C66
0x180005bdc  mov     ecx, 20h ; ' '
0x180005be1  lea     rax, ??_7PARAMETER_ENTRY@@6B@; const PARAMETER_ENTRY::`vftable'
0x180005be8  mov     [rbx], rax
0x180005beb  mov     r8, rbp; unsigned __int16 *
0x180005bee  lea     rax, [rbx+8]
0x180005bf2  mov     rdx, rdi; unsigned __int16 *
0x180005bf5  mov     [rax+28h], ecx
0x180005bf8  mov     qword ptr [rax], 0
0x180005bff  mov     [rax+20h], rax
0x180005c03  mov     word ptr [rax+2Ch], 100h
0x180005c09  mov     dword ptr [rax+30h], 0
0x180005c10  lea     rax, [rbx+40h]
0x180005c14  mov     [rax+28h], ecx
0x180005c17  mov     rcx, rbx; this
0x180005c1a  mov     qword ptr [rax], 0
0x180005c21  mov     [rax+20h], rax
0x180005c25  mov     word ptr [rax+2Ch], 100h
0x180005c2b  mov     dword ptr [rax+30h], 0
0x180005c32  call    ?Create@ATTRIBUTE_ENTRY@@QEAAJPEBG0@Z; ATTRIBUTE_ENTRY::Create(ushort const *,ushort const *)
0x180005c37  mov     edi, eax
0x180005c39  test    eax, eax
0x180005c3b  js      short loc_180005C56
0x180005c3d  lea     rcx, [rsi+0C8h]; this
0x180005c44  or      r8d, 0FFFFFFFFh; unsigned int
0x180005c48  mov     rdx, rbx; struct IArrayListEntry *
0x180005c4b  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x180005c50  mov     edi, eax
0x180005c52  test    eax, eax
0x180005c54  jns     short loc_180005C7D
0x180005c56  mov     rax, [rbx]
0x180005c59  mov     rcx, rbx
0x180005c5c  mov     rax, [rax]
0x180005c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c64  jmp     short loc_180005C7D
0x180005c66  mov     edi, 80070008h
0x180005c6b  jmp     short loc_180005C7D
0x180005c6d  mov     r8, rbp; unsigned __int16 *
0x180005c70  mov     rdx, rdi; unsigned __int16 *
0x180005c73  mov     rcx, rax; this
0x180005c76  call    ?Create@ATTRIBUTE_ENTRY@@QEAAJPEBG0@Z; ATTRIBUTE_ENTRY::Create(ushort const *,ushort const *)
0x180005c7b  mov     edi, eax
0x180005c7d  mov     eax, edi
0x180005c7f  add     rsp, 28h
0x180005c83  pop     rdi
0x180005c84  pop     rsi
0x180005c85  pop     rbp
0x180005c86  pop     rbx
0x180005c87  retn
```
