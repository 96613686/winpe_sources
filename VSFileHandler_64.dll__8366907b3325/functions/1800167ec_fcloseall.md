# _fcloseall

- ea: `0x1800167ec`
- end: `0x18001689d`
- name: `_fcloseall`
- size: `177`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011bf0`

## callees

- `0x18000fe3c`
- `0x180011ff8`
- `0x180012058`
- `0x1800167ec`
- `0x180019a04`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001685e`
- `KERNEL32!DeleteCriticalSection` at `0x18001685e`

## pseudocode

```c
int __cdecl fcloseall()
{
  int i; // ebx
  __int64 v1; // rcx
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
0x1800167ec  mov     [rsp+arg_0], rbx
0x1800167f1  push    rdi
0x1800167f2  sub     rsp, 30h
0x1800167f6  and     [rsp+38h+var_18], 0
0x1800167fb  mov     ecx, 8
0x180016800  call    __acrt_lock
0x180016805  nop
0x180016806  mov     ebx, 3
0x18001680b  mov     [rsp+38h+var_14], ebx
0x18001680f  cmp     ebx, cs:_nstream
0x180016815  jz      short loc_180016884
0x180016817  movsxd  rdi, ebx
0x18001681a  mov     rax, cs:__piob
0x180016821  mov     rcx, [rax+rdi*8]
0x180016825  test    rcx, rcx
0x180016828  jnz     short loc_18001682C
0x18001682a  jmp     short loc_180016880
0x18001682c  mov     eax, [rcx+14h]
0x18001682f  shr     eax, 0Dh
0x180016832  test    al, 1
0x180016834  jz      short loc_18001684F
0x180016836  mov     rcx, cs:__piob
0x18001683d  mov     rcx, [rcx+rdi*8]; Stream
0x180016841  call    fclose
0x180016846  cmp     eax, 0FFFFFFFFh
0x180016849  jz      short loc_18001684F
0x18001684b  inc     [rsp+38h+var_18]
0x18001684f  mov     rax, cs:__piob
0x180016856  mov     rcx, [rax+rdi*8]
0x18001685a  add     rcx, 30h ; '0'; lpCriticalSection
0x18001685e  call    cs:__imp_DeleteCriticalSection
0x180016864  mov     rcx, cs:__piob
0x18001686b  mov     rcx, [rcx+rdi*8]; Block
0x18001686f  call    _free_base
0x180016874  mov     rax, cs:__piob
0x18001687b  and     qword ptr [rax+rdi*8], 0
0x180016880  inc     ebx
0x180016882  jmp     short loc_18001680B
0x180016884  mov     ecx, 8
0x180016889  call    __acrt_unlock
0x18001688e  mov     eax, [rsp+38h+var_18]
0x180016892  mov     rbx, [rsp+38h+arg_0]
0x180016897  add     rsp, 30h
0x18001689b  pop     rdi
0x18001689c  retn
0x180025294  push    rbp
0x180025296  sub     rsp, 20h
0x18002529a  mov     rbp, rdx
0x18002529d  mov     ecx, 8
0x1800252a2  add     rsp, 20h
0x1800252a6  pop     rbp
0x1800252a7  jmp     __acrt_unlock
```
