# RtlpImageNtHeader

- ea: `0x14000205c`
- end: `0x1400020ad`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400020b4`

## callees

- `0x14000205c`

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
0x14000205c  sub     rsp, 18h
0x140002060  xor     edx, edx
0x140002062  lea     rax, [rcx-1]
0x140002066  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000206a  ja      short loc_1400020A5
0x14000206c  mov     eax, 5A4Dh
0x140002071  cmp     [rcx], ax
0x140002074  jnz     short loc_14000209D
0x140002076  movsxd  rax, dword ptr [rcx+3Ch]
0x14000207a  test    eax, eax
0x14000207c  js      short loc_14000209D
0x14000207e  cmp     eax, 10000000h
0x140002083  jnb     short loc_14000209D
0x140002085  lea     rdx, [rcx+rax]
0x140002089  mov     [rsp+18h+var_18], rdx
0x14000208d  xor     eax, eax
0x14000208f  cmp     dword ptr [rdx], 4550h
0x140002095  cmovnz  rdx, rax
0x140002099  mov     [rsp+18h+var_18], rdx
0x14000209d  jmp     short loc_1400020A5
0x14000209f  xor     edx, edx
0x1400020a1  mov     [rsp+18h+var_18], rdx
0x1400020a5  mov     rax, rdx
0x1400020a8  add     rsp, 18h
0x1400020ac  retn
```
