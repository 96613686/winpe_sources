# _tlgCreate1Sz_wchar_t

- ea: `0x180001178`
- end: `0x1800011ae`
- name: `_tlgCreate1Sz_wchar_t`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180016d74`
- `0x180017f9c`
- `0x180019d6c`
- `0x18001a260`

## callees

- `0x180001178`

## pseudocode

```c
__int64 __fastcall tlgCreate1Sz_wchar_t(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  if ( a2 )
  {
    v2 = -1;
    do
      ++v2;
    while ( *((_WORD *)a2 + v2) );
    result = (unsigned int)(2 * v2 + 2);
  }
  else
  {
    a2 = &qword_180024730;
    result = 2;
  }
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 8) = result;
  *(_DWORD *)(a1 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x180001178  xor     r8d, r8d
0x18000117b  test    rdx, rdx
0x18000117e  jz      short loc_180001197
0x180001180  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001184  inc     rax
0x180001187  cmp     [rdx+rax*2], r8w
0x18000118c  jnz     short loc_180001184
0x18000118e  lea     eax, ds:2[rax*2]
0x180001195  jmp     short loc_1800011A3
0x180001197  lea     rdx, qword_180024730
0x18000119e  mov     eax, 2
0x1800011a3  mov     [rcx], rdx
0x1800011a6  mov     [rcx+8], eax
0x1800011a9  mov     [rcx+0Ch], r8d
0x1800011ad  retn
```
