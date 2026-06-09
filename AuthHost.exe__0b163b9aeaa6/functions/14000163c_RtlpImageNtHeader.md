# RtlpImageNtHeader

- ea: `0x14000163c`
- end: `0x14000168d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001694`

## callees

- `0x14000163c`

## pseudocode

```c
__int64 __fastcall RtlpImageNtHeader(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rax

  v1 = 0;
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && *(_WORD *)a1 == 23117 )
  {
    v2 = *(int *)(a1 + 60);
    if ( (unsigned int)v2 < 0x10000000 )
    {
      v1 = a1 + v2;
      if ( *(_DWORD *)(a1 + v2) != 17744 )
        return 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x14000163c  sub     rsp, 18h
0x140001640  xor     edx, edx
0x140001642  lea     rax, [rcx-1]
0x140001646  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000164a  ja      short loc_140001685
0x14000164c  mov     eax, 5A4Dh
0x140001651  cmp     [rcx], ax
0x140001654  jnz     short loc_14000167D
0x140001656  movsxd  rax, dword ptr [rcx+3Ch]
0x14000165a  test    eax, eax
0x14000165c  js      short loc_14000167D
0x14000165e  cmp     eax, 10000000h
0x140001663  jnb     short loc_14000167D
0x140001665  lea     rdx, [rcx+rax]
0x140001669  mov     [rsp+18h+var_18], rdx
0x14000166d  xor     eax, eax
0x14000166f  cmp     dword ptr [rdx], 4550h
0x140001675  cmovnz  rdx, rax
0x140001679  mov     [rsp+18h+var_18], rdx
0x14000167d  jmp     short loc_140001685
0x14000167f  xor     edx, edx
0x140001681  mov     [rsp+18h+var_18], rdx
0x140001685  mov     rax, rdx
0x140001688  add     rsp, 18h
0x14000168c  retn
```
