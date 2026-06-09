# RtlpImageNtHeader

- ea: `0x14000217c`
- end: `0x1400021cd`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400021d4`

## callees

- `0x14000217c`

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
0x14000217c  sub     rsp, 18h
0x140002180  xor     edx, edx
0x140002182  lea     rax, [rcx-1]
0x140002186  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000218a  ja      short loc_1400021C5
0x14000218c  mov     eax, 5A4Dh
0x140002191  cmp     [rcx], ax
0x140002194  jnz     short loc_1400021BD
0x140002196  movsxd  rax, dword ptr [rcx+3Ch]
0x14000219a  test    eax, eax
0x14000219c  js      short loc_1400021BD
0x14000219e  cmp     eax, 10000000h
0x1400021a3  jnb     short loc_1400021BD
0x1400021a5  lea     rdx, [rcx+rax]
0x1400021a9  mov     [rsp+18h+var_18], rdx
0x1400021ad  xor     eax, eax
0x1400021af  cmp     dword ptr [rdx], 4550h
0x1400021b5  cmovnz  rdx, rax
0x1400021b9  mov     [rsp+18h+var_18], rdx
0x1400021bd  jmp     short loc_1400021C5
0x1400021bf  xor     edx, edx
0x1400021c1  mov     [rsp+18h+var_18], rdx
0x1400021c5  mov     rax, rdx
0x1400021c8  add     rsp, 18h
0x1400021cc  retn
```
