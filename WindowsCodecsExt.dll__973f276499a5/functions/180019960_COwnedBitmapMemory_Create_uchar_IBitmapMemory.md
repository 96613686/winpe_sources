# COwnedBitmapMemory::Create(uchar *,IBitmapMemory * *)

- ea: `0x180019960`
- end: `0x1800199d1`
- name: `?Create@COwnedBitmapMemory@@SAJPEAEPEAPEAUIBitmapMemory@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(unsigned __int8 *, struct IBitmapMemory **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180019600`
- `0x18001a190`

## callees

- `0x180019960`
- `0x18001a160`
- `0x1800215e8`

## pseudocode

```c
__int64 __fastcall COwnedBitmapMemory::Create(unsigned __int8 *a1, struct IBitmapMemory **a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // r8
  struct IBitmapMemory *v6; // rcx

  v4 = operator new(0x20u);
  v5 = v4;
  if ( v4 )
  {
    v4[3] = a1;
    *v4 = &CMILRefCountBase::`vftable';
    *v4 = &COwnedBitmapMemory::`vftable'{for `CMILRefCountBase'};
    v4[2] = &COwnedBitmapMemory::`vftable'{for `IBitmapMemory'};
    *((_DWORD *)v4 + 2) = 0;
  }
  else
  {
    v5 = 0;
  }
  v6 = (struct IBitmapMemory *)((unsigned __int64)(v5 + 2) & -(__int64)(v5 != 0));
  *a2 = v6;
  return CBitmapMemory::NullCheckAndAddRef(v6);
}

```

## disassembly

```asm
0x180019960  mov     [rsp+arg_0], rbx
0x180019965  push    rdi
0x180019966  sub     rsp, 20h
0x18001996a  mov     rbx, rcx
0x18001996d  mov     rdi, rdx
0x180019970  mov     ecx, 20h ; ' '; Size
0x180019975  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001997a  mov     r8, rax
0x18001997d  test    rax, rax
0x180019980  jz      short loc_1800199AF
0x180019982  lea     rax, ??_7CMILRefCountBase@@6B@; const CMILRefCountBase::`vftable'
0x180019989  mov     [r8+18h], rbx
0x18001998d  mov     [r8], rax
0x180019990  lea     rax, ??_7COwnedBitmapMemory@@6BCMILRefCountBase@@@; const COwnedBitmapMemory::`vftable'{for `CMILRefCountBase'}
0x180019997  mov     [r8], rax
0x18001999a  lea     rax, ??_7COwnedBitmapMemory@@6BIBitmapMemory@@@; const COwnedBitmapMemory::`vftable'{for `IBitmapMemory'}
0x1800199a1  mov     [r8+10h], rax
0x1800199a5  mov     dword ptr [r8+8], 0
0x1800199ad  jmp     short loc_1800199B2
0x1800199af  xor     r8d, r8d
0x1800199b2  lea     rax, [r8+10h]
0x1800199b6  neg     r8
0x1800199b9  sbb     rcx, rcx
0x1800199bc  and     rcx, rax; struct IBitmapMemory *
0x1800199bf  mov     [rdi], rcx
0x1800199c2  mov     rbx, [rsp+28h+arg_0]
0x1800199c7  add     rsp, 20h
0x1800199cb  pop     rdi
0x1800199cc  jmp     ?NullCheckAndAddRef@CBitmapMemory@@KAJPEAUIBitmapMemory@@@Z; CBitmapMemory::NullCheckAndAddRef(IBitmapMemory *)
```
