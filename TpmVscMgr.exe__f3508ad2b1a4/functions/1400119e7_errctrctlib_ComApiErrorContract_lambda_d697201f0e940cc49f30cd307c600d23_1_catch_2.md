# _errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch$2

- ea: `0x1400119e7`
- end: `0x140011a35`
- name: `_errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch$2`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400119e7`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140011a06`
- `ntdll!RtlNtStatusToDosError` at `0x140011a06`

## pseudocode

```c
__int64 __fastcall errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch_2(
        __int64 a1,
        __int64 a2)
{
  NTSTATUS v3; // ebx
  signed int v4; // eax

  v3 = *(_DWORD *)(*(_QWORD *)(a2 + 40) + 24LL);
  if ( v3 < 0 )
  {
    v4 = RtlNtStatusToDosError(v3);
    if ( v4 == 317 )
      v4 = v3;
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v4 = 0;
  }
  *(_DWORD *)(a2 + 80) = v4;
  return 0;
}

```

## disassembly

```asm
0x1400119e7  mov     [rsp+arg_8], rdx
0x1400119ec  push    rbx
0x1400119ed  push    rbp
0x1400119ee  sub     rsp, 28h
0x1400119f2  mov     rbp, rdx
0x1400119f5  mov     rax, [rbp+28h]
0x1400119f9  mov     ebx, [rax+18h]
0x1400119fc  test    ebx, ebx
0x1400119fe  js      short loc_140011A04
0x140011a00  xor     eax, eax
0x140011a02  jmp     short loc_140011A20
0x140011a04  mov     ecx, ebx; Status
0x140011a06  call    cs:__imp_RtlNtStatusToDosError
0x140011a0c  cmp     eax, 13Dh
0x140011a11  cmovz   eax, ebx
0x140011a14  test    eax, eax
0x140011a16  jle     short loc_140011A20
0x140011a18  movzx   eax, ax
0x140011a1b  or      eax, 80070000h
0x140011a20  mov     [rbp+50h], eax
0x140011a23  mov     rax, 0
0x140011a2d  add     rsp, 28h
0x140011a31  pop     rbp
0x140011a32  pop     rbx
0x140011a33  retn
```
