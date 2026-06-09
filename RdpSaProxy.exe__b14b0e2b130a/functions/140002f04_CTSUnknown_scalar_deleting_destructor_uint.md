# CTSUnknown::`scalar deleting destructor'(uint)

- ea: `0x140002f04`
- end: `0x140002f3a`
- name: `??_GCTSUnknown@@UEAAPEAXI@Z`
- size: `54`
- prototype: `CTSUnknown *__fastcall(CTSUnknown *this, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002e70`

## callees

- `0x140002f04`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140002f2b`
- `msvcrt!??3@YAXPEAX@Z` at `0x140002f2b`

## pseudocode

```c
CTSUnknown *__fastcall CTSUnknown::`scalar deleting destructor'(CTSUnknown *this, char a2)
{
  *(_QWORD *)this = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
  *((_DWORD *)this + 7) |= 8u;
  *((_QWORD *)this + 1) = &CTSObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140002f04  push    rbx
0x140002f06  sub     rsp, 20h
0x140002f0a  lea     rax, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x140002f11  mov     rbx, rcx
0x140002f14  mov     [rcx], rax
0x140002f17  lea     rax, ??_7CTSObject@@6B@; const CTSObject::`vftable'
0x140002f1e  or      dword ptr [rcx+1Ch], 8
0x140002f22  mov     [rcx+8], rax
0x140002f26  test    dl, 1
0x140002f29  jz      short loc_140002F31
0x140002f2b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140002f31  mov     rax, rbx
0x140002f34  add     rsp, 20h
0x140002f38  pop     rbx
0x140002f39  retn
```
