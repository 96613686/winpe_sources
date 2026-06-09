# RtlpImageNtHeader

- ea: `0x1400016dc`
- end: `0x14000172d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001734`

## callees

- `0x1400016dc`

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
0x1400016dc  sub     rsp, 18h
0x1400016e0  xor     edx, edx
0x1400016e2  lea     rax, [rcx-1]
0x1400016e6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400016ea  ja      short loc_140001725
0x1400016ec  mov     eax, 5A4Dh
0x1400016f1  cmp     [rcx], ax
0x1400016f4  jnz     short loc_14000171D
0x1400016f6  movsxd  rax, dword ptr [rcx+3Ch]
0x1400016fa  test    eax, eax
0x1400016fc  js      short loc_14000171D
0x1400016fe  cmp     eax, 10000000h
0x140001703  jnb     short loc_14000171D
0x140001705  lea     rdx, [rcx+rax]
0x140001709  mov     [rsp+18h+var_18], rdx
0x14000170d  xor     eax, eax
0x14000170f  cmp     dword ptr [rdx], 4550h
0x140001715  cmovnz  rdx, rax
0x140001719  mov     [rsp+18h+var_18], rdx
0x14000171d  jmp     short loc_140001725
0x14000171f  xor     edx, edx
0x140001721  mov     [rsp+18h+var_18], rdx
0x140001725  mov     rax, rdx
0x140001728  add     rsp, 18h
0x14000172c  retn
```
