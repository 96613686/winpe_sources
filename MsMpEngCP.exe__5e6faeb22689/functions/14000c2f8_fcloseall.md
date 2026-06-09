# _fcloseall

- ea: `0x14000c2f8`
- end: `0x14000c3aa`
- name: `_fcloseall`
- size: `178`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a360`

## callees

- `0x140006940`
- `0x1400081e8`
- `0x140008248`
- `0x14000c2f8`
- `0x14000c784`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000c36b`
- `KERNEL32!DeleteCriticalSection` at `0x14000c36b`

## pseudocode

```c
int __cdecl fcloseall()
{
  int i; // ebx
  __int64 v1; // rax
  int v3; // [rsp+20h] [rbp-18h]

  v3 = 0;
  sub_1400081E8(8);
  for ( i = 3; i != dword_14001AC50; ++i )
  {
    v1 = *((_QWORD *)qword_14001AC58 + i);
    if ( v1 )
    {
      if ( (*(_DWORD *)(v1 + 20) & 0x2000) != 0 && fclose(*((FILE **)qword_14001AC58 + i)) != -1 )
        ++v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)qword_14001AC58 + i) + 48LL));
      free_base(*((void **)qword_14001AC58 + i));
      *((_QWORD *)qword_14001AC58 + i) = 0;
    }
  }
  sub_140008248(8);
  return v3;
}

```

## disassembly

```asm
0x14000c2f8  mov     [rsp+arg_8], rbx
0x14000c2fd  push    rdi
0x14000c2fe  sub     rsp, 30h
0x14000c302  and     [rsp+38h+var_18], 0
0x14000c307  mov     ecx, 8
0x14000c30c  call    sub_1400081E8
0x14000c311  nop
0x14000c312  mov     ebx, 3
0x14000c317  mov     [rsp+38h+var_14], ebx
0x14000c31b  cmp     ebx, cs:dword_14001AC50
0x14000c321  jz      short loc_14000C391
0x14000c323  movsxd  rdi, ebx
0x14000c326  mov     rax, cs:qword_14001AC58
0x14000c32d  mov     rax, [rax+rdi*8]
0x14000c331  test    rax, rax
0x14000c334  jnz     short loc_14000C338
0x14000c336  jmp     short loc_14000C38D
0x14000c338  mov     eax, [rax+14h]
0x14000c33b  nop
0x14000c33c  shr     eax, 0Dh
0x14000c33f  test    al, 1
0x14000c341  jz      short loc_14000C35C
0x14000c343  mov     rcx, cs:qword_14001AC58
0x14000c34a  mov     rcx, [rcx+rdi*8]; Stream
0x14000c34e  call    fclose
0x14000c353  cmp     eax, 0FFFFFFFFh
0x14000c356  jz      short loc_14000C35C
0x14000c358  inc     [rsp+38h+var_18]
0x14000c35c  mov     rax, cs:qword_14001AC58
0x14000c363  mov     rcx, [rax+rdi*8]
0x14000c367  add     rcx, 30h ; '0'; lpCriticalSection
0x14000c36b  call    cs:DeleteCriticalSection
0x14000c371  mov     rcx, cs:qword_14001AC58
0x14000c378  mov     rcx, [rcx+rdi*8]; Block
0x14000c37c  call    _free_base
0x14000c381  mov     rax, cs:qword_14001AC58
0x14000c388  and     qword ptr [rax+rdi*8], 0
0x14000c38d  inc     ebx
0x14000c38f  jmp     short loc_14000C317
0x14000c391  mov     ecx, 8
0x14000c396  call    sub_140008248
0x14000c39b  mov     eax, [rsp+38h+var_18]
0x14000c39f  mov     rbx, [rsp+38h+arg_8]
0x14000c3a4  add     rsp, 30h
0x14000c3a8  pop     rdi
0x14000c3a9  retn
0x14000e036  push    rbp; Microsoft VisualC 64bit universal runtime
0x14000e038  sub     rsp, 20h
0x14000e03c  mov     rbp, rdx
0x14000e03f  mov     ecx, 8
0x14000e044  add     rsp, 20h
0x14000e048  pop     rbp
0x14000e049  jmp     sub_140008248
```
