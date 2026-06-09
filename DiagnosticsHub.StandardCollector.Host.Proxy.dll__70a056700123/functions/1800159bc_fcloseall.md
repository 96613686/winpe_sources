# _fcloseall

- ea: `0x1800159bc`
- end: `0x180015a6e`
- name: `_fcloseall`
- size: `178`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f530`

## callees

- `0x1800069b8`
- `0x180006a18`
- `0x1800078e0`
- `0x1800159bc`
- `0x18001d028`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180015a2f`
- `KERNEL32!DeleteCriticalSection` at `0x180015a2f`

## pseudocode

```c
int __cdecl fcloseall()
{
  int i; // ebx
  __int64 v1; // rax
  int v3; // [rsp+20h] [rbp-18h]

  v3 = 0;
  _acrt_lock(8);
  for ( i = 3; i != nstream; ++i )
  {
    v1 = *((_QWORD *)_piob + i);
    if ( v1 )
    {
      if ( (*(_DWORD *)(v1 + 20) & 0x2000) != 0 && fclose(*((FILE **)_piob + i)) != -1 )
        ++v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)_piob + i) + 48LL));
      free_base(*((void **)_piob + i));
      *((_QWORD *)_piob + i) = 0;
    }
  }
  _acrt_unlock(8);
  return v3;
}

```

## disassembly

```asm
0x1800159bc  mov     [rsp+arg_8], rbx
0x1800159c1  push    rdi
0x1800159c2  sub     rsp, 30h
0x1800159c6  and     [rsp+38h+var_18], 0
0x1800159cb  mov     ecx, 8
0x1800159d0  call    __acrt_lock
0x1800159d5  nop
0x1800159d6  mov     ebx, 3
0x1800159db  mov     [rsp+38h+var_14], ebx
0x1800159df  cmp     ebx, cs:_nstream
0x1800159e5  jz      short loc_180015A55
0x1800159e7  movsxd  rdi, ebx
0x1800159ea  mov     rax, cs:__piob
0x1800159f1  mov     rax, [rax+rdi*8]
0x1800159f5  test    rax, rax
0x1800159f8  jnz     short loc_1800159FC
0x1800159fa  jmp     short loc_180015A51
0x1800159fc  mov     eax, [rax+14h]
0x1800159ff  nop
0x180015a00  shr     eax, 0Dh
0x180015a03  test    al, 1
0x180015a05  jz      short loc_180015A20
0x180015a07  mov     rcx, cs:__piob
0x180015a0e  mov     rcx, [rcx+rdi*8]; Stream
0x180015a12  call    fclose
0x180015a17  cmp     eax, 0FFFFFFFFh
0x180015a1a  jz      short loc_180015A20
0x180015a1c  inc     [rsp+38h+var_18]
0x180015a20  mov     rax, cs:__piob
0x180015a27  mov     rcx, [rax+rdi*8]
0x180015a2b  add     rcx, 30h ; '0'; lpCriticalSection
0x180015a2f  call    cs:__imp_DeleteCriticalSection
0x180015a35  mov     rcx, cs:__piob
0x180015a3c  mov     rcx, [rcx+rdi*8]; Block
0x180015a40  call    _free_base
0x180015a45  mov     rax, cs:__piob
0x180015a4c  and     qword ptr [rax+rdi*8], 0
0x180015a51  inc     ebx
0x180015a53  jmp     short loc_1800159DB
0x180015a55  mov     ecx, 8
0x180015a5a  call    __acrt_unlock
0x180015a5f  mov     eax, [rsp+38h+var_18]
0x180015a63  mov     rbx, [rsp+38h+arg_8]
0x180015a68  add     rsp, 30h
0x180015a6c  pop     rdi
0x180015a6d  retn
0x1800612ea  push    rbp
0x1800612ec  sub     rsp, 20h
0x1800612f0  mov     rbp, rdx
0x1800612f3  mov     ecx, 8
0x1800612f8  add     rsp, 20h
0x1800612fc  pop     rbp
0x1800612fd  jmp     __acrt_unlock
```
