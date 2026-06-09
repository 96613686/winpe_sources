# sub_18002CABC

- ea: `0x18002cabc`
- end: `0x18002cb6e`
- name: `sub_18002CABC`
- size: `178`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180024e80`

## callees

- `0x1800211b8`
- `0x180021218`
- `0x180023610`
- `0x18002cabc`
- `0x18002f5e0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002cb2f`
- `KERNEL32!DeleteCriticalSection` at `0x18002cb2f`

## pseudocode

```c
__int64 sub_18002CABC()
{
  int i; // ebx
  __int64 v1; // rax
  unsigned int v3; // [rsp+20h] [rbp-18h]

  v3 = 0;
  sub_1800211B8(8);
  for ( i = 3; i != dword_18009A228; ++i )
  {
    v1 = *((_QWORD *)qword_18009A230 + i);
    if ( v1 )
    {
      if ( (*(_DWORD *)(v1 + 20) & 0x2000) != 0 && (unsigned int)sub_18002F5E0(*((_QWORD *)qword_18009A230 + i)) != -1 )
        ++v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)qword_18009A230 + i) + 48LL));
      sub_180023610(*((LPVOID *)qword_18009A230 + i));
      *((_QWORD *)qword_18009A230 + i) = 0;
    }
  }
  sub_180021218(8);
  return v3;
}

```

## disassembly

```asm
0x18002cabc  mov     [rsp+arg_8], rbx
0x18002cac1  push    rdi
0x18002cac2  sub     rsp, 30h
0x18002cac6  and     [rsp+38h+var_18], 0
0x18002cacb  mov     ecx, 8
0x18002cad0  call    sub_1800211B8
0x18002cad5  nop
0x18002cad6  mov     ebx, 3
0x18002cadb  mov     [rsp+38h+var_14], ebx
0x18002cadf  cmp     ebx, cs:dword_18009A228
0x18002cae5  jz      short loc_18002CB55
0x18002cae7  movsxd  rdi, ebx
0x18002caea  mov     rax, cs:qword_18009A230
0x18002caf1  mov     rax, [rax+rdi*8]
0x18002caf5  test    rax, rax
0x18002caf8  jnz     short loc_18002CAFC
0x18002cafa  jmp     short loc_18002CB51
0x18002cafc  mov     eax, [rax+14h]
0x18002caff  nop
0x18002cb00  shr     eax, 0Dh
0x18002cb03  test    al, 1
0x18002cb05  jz      short loc_18002CB20
0x18002cb07  mov     rcx, cs:qword_18009A230
0x18002cb0e  mov     rcx, [rcx+rdi*8]
0x18002cb12  call    sub_18002F5E0
0x18002cb17  cmp     eax, 0FFFFFFFFh
0x18002cb1a  jz      short loc_18002CB20
0x18002cb1c  inc     [rsp+38h+var_18]
0x18002cb20  mov     rax, cs:qword_18009A230
0x18002cb27  mov     rcx, [rax+rdi*8]
0x18002cb2b  add     rcx, 30h ; '0'; lpCriticalSection
0x18002cb2f  call    cs:__imp_DeleteCriticalSection
0x18002cb35  mov     rcx, cs:qword_18009A230
0x18002cb3c  mov     rcx, [rcx+rdi*8]; lpMem
0x18002cb40  call    sub_180023610
0x18002cb45  mov     rax, cs:qword_18009A230
0x18002cb4c  and     qword ptr [rax+rdi*8], 0
0x18002cb51  inc     ebx
0x18002cb53  jmp     short loc_18002CADB
0x18002cb55  mov     ecx, 8
0x18002cb5a  call    sub_180021218
0x18002cb5f  mov     eax, [rsp+38h+var_18]
0x18002cb63  mov     rbx, [rsp+38h+arg_8]
0x18002cb68  add     rsp, 30h
0x18002cb6c  pop     rdi
0x18002cb6d  retn
0x180069a45  push    rbp
0x180069a47  sub     rsp, 20h
0x180069a4b  mov     rbp, rdx
0x180069a4e  mov     ecx, 8
0x180069a53  add     rsp, 20h
0x180069a57  pop     rbp
0x180069a58  jmp     sub_180021218
```
