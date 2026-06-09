# WaveStreamReadFormat

- ea: `0x180006460`
- end: `0x1800064c1`
- name: `WaveStreamReadFormat`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006460`
- `0x180017365`

## pseudocode

```c
__int64 __fastcall WaveStreamReadFormat(__int64 a1, __int64 a2, void *a3, int *a4)
{
  int v6; // edx
  int v7; // eax

  if ( a3 && (v6 = *a4) != 0 )
  {
    if ( v6 >= *(_DWORD *)(a1 + 288) )
      v6 = *(_DWORD *)(a1 + 288);
    memmove_0(a3, *(const void **)(a1 + 280), v6);
    v7 = *(_DWORD *)(a1 + 288);
    if ( *a4 < v7 )
      return 2147762292LL;
  }
  else
  {
    v7 = *(_DWORD *)(a1 + 288);
  }
  *a4 = v7;
  return 0;
}

```

## disassembly

```asm
0x180006460  mov     [rsp+arg_0], rbx
0x180006465  push    rdi
0x180006466  sub     rsp, 20h
0x18000646a  mov     rbx, r9
0x18000646d  mov     r9, r8
0x180006470  mov     rdi, rcx
0x180006473  test    r8, r8
0x180006476  jz      short loc_1800064AC
0x180006478  mov     edx, [rbx]
0x18000647a  test    edx, edx
0x18000647c  jz      short loc_1800064AC
0x18000647e  mov     eax, [rcx+120h]
0x180006484  cmp     edx, eax
0x180006486  cmovge  edx, eax
0x180006489  movsxd  r8, edx; Size
0x18000648c  mov     rdx, [rcx+118h]; Src
0x180006493  mov     rcx, r9; void *
0x180006496  call    memmove_0
0x18000649b  mov     eax, [rdi+120h]
0x1800064a1  cmp     [rbx], eax
0x1800064a3  jge     short loc_1800064B2
0x1800064a5  mov     eax, 80044074h
0x1800064aa  jmp     short loc_1800064B6
0x1800064ac  mov     eax, [rcx+120h]
0x1800064b2  mov     [rbx], eax
0x1800064b4  xor     eax, eax
0x1800064b6  mov     rbx, [rsp+28h+arg_0]
0x1800064bb  add     rsp, 20h
0x1800064bf  pop     rdi
0x1800064c0  retn
```
