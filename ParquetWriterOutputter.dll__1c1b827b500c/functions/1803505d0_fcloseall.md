# _fcloseall

- ea: `0x1803505d0`
- end: `0x180350682`
- name: `_fcloseall`
- size: `178`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1803463b0`

## callees

- `0x1803457c8`
- `0x180345828`
- `0x1803464f0`
- `0x18034962c`
- `0x1803505d0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180350643`
- `KERNEL32!DeleteCriticalSection` at `0x180350643`

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
0x1803505d0  mov     [rsp+arg_0], rbx
0x1803505d5  push    rdi
0x1803505d6  sub     rsp, 30h
0x1803505da  and     [rsp+38h+var_18], 0
0x1803505df  mov     ecx, 8
0x1803505e4  call    __acrt_lock
0x1803505e9  nop
0x1803505ea  mov     ebx, 3
0x1803505ef  mov     [rsp+38h+var_14], ebx
0x1803505f3  cmp     ebx, cs:_nstream
0x1803505f9  jz      short loc_180350669
0x1803505fb  movsxd  rdi, ebx
0x1803505fe  mov     rax, cs:__piob
0x180350605  mov     rax, [rax+rdi*8]
0x180350609  test    rax, rax
0x18035060c  jnz     short loc_180350610
0x18035060e  jmp     short loc_180350665
0x180350610  mov     ecx, [rax+14h]
0x180350613  shr     ecx, 0Dh
0x180350616  test    cl, 1
0x180350619  jz      short loc_180350634
0x18035061b  mov     rcx, cs:__piob
0x180350622  mov     rcx, [rcx+rdi*8]; Stream
0x180350626  call    fclose
0x18035062b  cmp     eax, 0FFFFFFFFh
0x18035062e  jz      short loc_180350634
0x180350630  inc     [rsp+38h+var_18]
0x180350634  mov     rax, cs:__piob
0x18035063b  mov     rcx, [rax+rdi*8]
0x18035063f  add     rcx, 30h ; '0'; lpCriticalSection
0x180350643  call    cs:__imp_DeleteCriticalSection
0x180350649  mov     rcx, cs:__piob
0x180350650  mov     rcx, [rcx+rdi*8]; Block
0x180350654  call    _free_base
0x180350659  mov     rax, cs:__piob
0x180350660  and     qword ptr [rax+rdi*8], 0
0x180350665  inc     ebx
0x180350667  jmp     short loc_1803505EF
0x180350669  mov     ecx, 8
0x18035066e  call    __acrt_unlock
0x180350673  mov     eax, [rsp+38h+var_18]
0x180350677  mov     rbx, [rsp+38h+arg_0]
0x18035067c  add     rsp, 30h
0x180350680  pop     rdi
0x180350681  retn
0x18036ad4f  push    rbp
0x18036ad51  sub     rsp, 20h
0x18036ad55  mov     rbp, rdx
0x18036ad58  mov     ecx, 8
0x18036ad5d  add     rsp, 20h
0x18036ad61  pop     rbp
0x18036ad62  jmp     __acrt_unlock
```
