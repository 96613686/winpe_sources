# COutOfProcFactory::`vector deleting destructor'(uint)

- ea: `0x140002e80`
- end: `0x140002ec1`
- name: `??_ECOutOfProcFactory@@UEAAPEAXI@Z`
- size: `65`
- prototype: `COutOfProcFactory *__fastcall(COutOfProcFactory *this, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002e60`

## callees

- `0x140002e80`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140002eb2`
- `msvcrt!??3@YAXPEAX@Z` at `0x140002eb2`

## pseudocode

```c
COutOfProcFactory *__fastcall COutOfProcFactory::`vector deleting destructor'(COutOfProcFactory *this, char a2)
{
  *((_DWORD *)this + 7) |= 8u;
  *((_QWORD *)this + 6) = &COutOfProcFactory::`vftable';
  *(_QWORD *)this = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &CTSObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140002e80  push    rbx
0x140002e82  sub     rsp, 20h
0x140002e86  or      dword ptr [rcx+1Ch], 8
0x140002e8a  lea     rax, ??_7COutOfProcFactory@@6B@; const COutOfProcFactory::`vftable'
0x140002e91  mov     [rcx+30h], rax
0x140002e95  lea     rax, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x140002e9c  mov     [rcx], rax
0x140002e9f  lea     rax, ??_7CTSObject@@6B@; const CTSObject::`vftable'
0x140002ea6  mov     [rcx+8], rax
0x140002eaa  mov     rbx, rcx
0x140002ead  test    dl, 1
0x140002eb0  jz      short loc_140002EB8
0x140002eb2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140002eb8  mov     rax, rbx
0x140002ebb  add     rsp, 20h
0x140002ebf  pop     rbx
0x140002ec0  retn
```
