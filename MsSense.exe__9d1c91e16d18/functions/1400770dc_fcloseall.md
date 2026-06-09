# _fcloseall

- ea: `0x1400770dc`
- end: `0x14007718e`
- name: `_fcloseall`
- size: `178`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14006ce60`

## callees

- `0x14006c958`
- `0x14006fd48`
- `0x14006fda8`
- `0x140072280`
- `0x1400770dc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14007714f`
- `KERNEL32!DeleteCriticalSection` at `0x14007714f`

## pseudocode

```c
int __cdecl fcloseall()
{
  int i; // ebx
  __int64 v1; // rax
  int v3; // [rsp+20h] [rbp-18h]

  v3 = 0;
  _vcrt_lock_0(8);
  for ( i = 3; i != dword_1400C43B8; ++i )
  {
    v1 = *((_QWORD *)qword_1400C43C0 + i);
    if ( v1 )
    {
      if ( (*(_DWORD *)(v1 + 20) & 0x2000) != 0 && fclose(*((FILE **)qword_1400C43C0 + i)) != -1 )
        ++v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)qword_1400C43C0 + i) + 48LL));
      free_base(*((void **)qword_1400C43C0 + i));
      *((_QWORD *)qword_1400C43C0 + i) = 0;
    }
  }
  _vcrt_unlock_0(8);
  return v3;
}

```

## disassembly

```asm
0x1400770dc  mov     [rsp+arg_8], rbx
0x1400770e1  push    rdi
0x1400770e2  sub     rsp, 30h
0x1400770e6  and     [rsp+38h+var_18], 0
0x1400770eb  mov     ecx, 8
0x1400770f0  call    __vcrt_lock_0
0x1400770f5  nop
0x1400770f6  mov     ebx, 3
0x1400770fb  mov     [rsp+38h+var_14], ebx
0x1400770ff  cmp     ebx, cs:dword_1400C43B8
0x140077105  jz      short loc_140077175
0x140077107  movsxd  rdi, ebx
0x14007710a  mov     rax, cs:qword_1400C43C0
0x140077111  mov     rax, [rax+rdi*8]
0x140077115  test    rax, rax
0x140077118  jnz     short loc_14007711C
0x14007711a  jmp     short loc_140077171
0x14007711c  mov     eax, [rax+14h]
0x14007711f  nop
0x140077120  shr     eax, 0Dh
0x140077123  test    al, 1
0x140077125  jz      short loc_140077140
0x140077127  mov     rcx, cs:qword_1400C43C0
0x14007712e  mov     rcx, [rcx+rdi*8]; File
0x140077132  call    fclose
0x140077137  cmp     eax, 0FFFFFFFFh
0x14007713a  jz      short loc_140077140
0x14007713c  inc     [rsp+38h+var_18]
0x140077140  mov     rax, cs:qword_1400C43C0
0x140077147  mov     rcx, [rax+rdi*8]
0x14007714b  add     rcx, 30h ; '0'; lpCriticalSection
0x14007714f  call    cs:__imp_DeleteCriticalSection
0x140077155  mov     rcx, cs:qword_1400C43C0
0x14007715c  mov     rcx, [rcx+rdi*8]; Block
0x140077160  call    _free_base
0x140077165  mov     rax, cs:qword_1400C43C0
0x14007716c  and     qword ptr [rax+rdi*8], 0
0x140077171  inc     ebx
0x140077173  jmp     short loc_1400770FB
0x140077175  mov     ecx, 8
0x14007717a  call    __vcrt_unlock_0
0x14007717f  mov     eax, [rsp+38h+var_18]
0x140077183  mov     rbx, [rsp+38h+arg_8]
0x140077188  add     rsp, 30h
0x14007718c  pop     rdi
0x14007718d  retn
0x14008588e  push    rbp; Microsoft VisualC 64bit universal runtime
0x140085890  sub     rsp, 20h
0x140085894  mov     rbp, rdx
0x140085897  mov     ecx, 8
0x14008589c  add     rsp, 20h
0x1400858a0  pop     rbp
0x1400858a1  jmp     __vcrt_unlock_0
```
