# _fcloseall

- ea: `0x18021de74`
- end: `0x18021df26`
- name: `_fcloseall`
- size: `178`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1802131f0`

## callees

- `0x1802132c8`
- `0x180213328`
- `0x180219680`
- `0x18021de74`
- `0x180225b70`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18021dee7`
- `KERNEL32!DeleteCriticalSection` at `0x18021dee7`

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
0x18021de74  mov     [rsp+arg_8], rbx
0x18021de79  push    rdi
0x18021de7a  sub     rsp, 30h
0x18021de7e  and     [rsp+38h+var_18], 0
0x18021de83  mov     ecx, 8
0x18021de88  call    __acrt_lock
0x18021de8d  nop
0x18021de8e  mov     ebx, 3
0x18021de93  mov     [rsp+38h+var_14], ebx
0x18021de97  cmp     ebx, cs:_nstream
0x18021de9d  jz      short loc_18021DF0D
0x18021de9f  movsxd  rdi, ebx
0x18021dea2  mov     rax, cs:__piob
0x18021dea9  mov     rax, [rax+rdi*8]
0x18021dead  test    rax, rax
0x18021deb0  jnz     short loc_18021DEB4
0x18021deb2  jmp     short loc_18021DF09
0x18021deb4  mov     eax, [rax+14h]
0x18021deb7  nop
0x18021deb8  shr     eax, 0Dh
0x18021debb  test    al, 1
0x18021debd  jz      short loc_18021DED8
0x18021debf  mov     rcx, cs:__piob
0x18021dec6  mov     rcx, [rcx+rdi*8]; Stream
0x18021deca  call    fclose
0x18021decf  cmp     eax, 0FFFFFFFFh
0x18021ded2  jz      short loc_18021DED8
0x18021ded4  inc     [rsp+38h+var_18]
0x18021ded8  mov     rax, cs:__piob
0x18021dedf  mov     rcx, [rax+rdi*8]
0x18021dee3  add     rcx, 30h ; '0'; lpCriticalSection
0x18021dee7  call    cs:__imp_DeleteCriticalSection
0x18021deed  mov     rcx, cs:__piob
0x18021def4  mov     rcx, [rcx+rdi*8]; Block
0x18021def8  call    _free_base
0x18021defd  mov     rax, cs:__piob
0x18021df04  and     qword ptr [rax+rdi*8], 0
0x18021df09  inc     ebx
0x18021df0b  jmp     short loc_18021DE93
0x18021df0d  mov     ecx, 8
0x18021df12  call    __acrt_unlock
0x18021df17  mov     eax, [rsp+38h+var_18]
0x18021df1b  mov     rbx, [rsp+38h+arg_8]
0x18021df20  add     rsp, 30h
0x18021df24  pop     rdi
0x18021df25  retn
0x180257d1a  push    rbp
0x180257d1c  sub     rsp, 20h
0x180257d20  mov     rbp, rdx
0x180257d23  mov     ecx, 8
0x180257d28  add     rsp, 20h
0x180257d2c  pop     rbp
0x180257d2d  jmp     __acrt_unlock
```
