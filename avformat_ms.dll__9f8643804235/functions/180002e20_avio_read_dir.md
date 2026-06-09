# avio_read_dir

- ea: `0x180002e20`
- end: `0x180002e70`
- name: `avio_read_dir`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002bf0`
- `0x180002e20`
- `0x18001d6e0`

## pseudocode

```c
__int64 __fastcall avio_read_dir(__int64 *a1, _QWORD *a2)
{
  __int64 v3; // rcx
  int v4; // edi

  if ( !a1 )
    return 4294967274LL;
  v3 = *a1;
  if ( !v3 )
    return 4294967274LL;
  v4 = (*(__int64 (**)(void))(*(_QWORD *)(v3 + 8) + 152LL))();
  if ( v4 < 0 )
  {
    _mm_lfence();
    avio_free_directory_entry(a2);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002e20  mov     [rsp+arg_0], rbx
0x180002e25  push    rdi
0x180002e26  sub     rsp, 20h
0x180002e2a  mov     rbx, rdx
0x180002e2d  test    rcx, rcx
0x180002e30  jz      short loc_180002E60
0x180002e32  mov     rcx, [rcx]
0x180002e35  test    rcx, rcx
0x180002e38  jz      short loc_180002E60
0x180002e3a  mov     rax, [rcx+8]
0x180002e3e  mov     rax, [rax+98h]
0x180002e45  call    cs:__guard_dispatch_icall_fptr
0x180002e4b  mov     edi, eax
0x180002e4d  test    eax, eax
0x180002e4f  jns     short loc_180002E5C
0x180002e51  lfence
0x180002e54  mov     rcx, rbx
0x180002e57  call    avio_free_directory_entry
0x180002e5c  mov     eax, edi
0x180002e5e  jmp     short loc_180002E65
0x180002e60  mov     eax, 0FFFFFFEAh
0x180002e65  mov     rbx, [rsp+28h+arg_0]
0x180002e6a  add     rsp, 20h
0x180002e6e  pop     rdi
0x180002e6f  retn
```
