# _fcloseall

- ea: `0x18001611c`
- end: `0x1800161ce`
- name: `_fcloseall`
- size: `178`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fc90`

## callees

- `0x180007118`
- `0x180007178`
- `0x180008040`
- `0x18001611c`
- `0x18001d788`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001618f`
- `KERNEL32!DeleteCriticalSection` at `0x18001618f`

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
0x18001611c  mov     [rsp+arg_8], rbx
0x180016121  push    rdi
0x180016122  sub     rsp, 30h
0x180016126  and     [rsp+38h+var_18], 0
0x18001612b  mov     ecx, 8
0x180016130  call    __acrt_lock
0x180016135  nop
0x180016136  mov     ebx, 3
0x18001613b  mov     [rsp+38h+var_14], ebx
0x18001613f  cmp     ebx, cs:_nstream
0x180016145  jz      short loc_1800161B5
0x180016147  movsxd  rdi, ebx
0x18001614a  mov     rax, cs:__piob
0x180016151  mov     rax, [rax+rdi*8]
0x180016155  test    rax, rax
0x180016158  jnz     short loc_18001615C
0x18001615a  jmp     short loc_1800161B1
0x18001615c  mov     eax, [rax+14h]
0x18001615f  nop
0x180016160  shr     eax, 0Dh
0x180016163  test    al, 1
0x180016165  jz      short loc_180016180
0x180016167  mov     rcx, cs:__piob
0x18001616e  mov     rcx, [rcx+rdi*8]; Stream
0x180016172  call    fclose
0x180016177  cmp     eax, 0FFFFFFFFh
0x18001617a  jz      short loc_180016180
0x18001617c  inc     [rsp+38h+var_18]
0x180016180  mov     rax, cs:__piob
0x180016187  mov     rcx, [rax+rdi*8]
0x18001618b  add     rcx, 30h ; '0'; lpCriticalSection
0x18001618f  call    cs:__imp_DeleteCriticalSection
0x180016195  mov     rcx, cs:__piob
0x18001619c  mov     rcx, [rcx+rdi*8]; Block
0x1800161a0  call    _free_base
0x1800161a5  mov     rax, cs:__piob
0x1800161ac  and     qword ptr [rax+rdi*8], 0
0x1800161b1  inc     ebx
0x1800161b3  jmp     short loc_18001613B
0x1800161b5  mov     ecx, 8
0x1800161ba  call    __acrt_unlock
0x1800161bf  mov     eax, [rsp+38h+var_18]
0x1800161c3  mov     rbx, [rsp+38h+arg_8]
0x1800161c8  add     rsp, 30h
0x1800161cc  pop     rdi
0x1800161cd  retn
0x1800615ca  push    rbp
0x1800615cc  sub     rsp, 20h
0x1800615d0  mov     rbp, rdx
0x1800615d3  mov     ecx, 8
0x1800615d8  add     rsp, 20h
0x1800615dc  pop     rbp
0x1800615dd  jmp     __acrt_unlock
```
