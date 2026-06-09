# RtlpImageNtHeader

- ea: `0x1400018dc`
- end: `0x14000192d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001934`

## callees

- `0x1400018dc`

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
0x1400018dc  sub     rsp, 18h
0x1400018e0  xor     edx, edx
0x1400018e2  lea     rax, [rcx-1]
0x1400018e6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400018ea  ja      short loc_140001925
0x1400018ec  mov     eax, 5A4Dh
0x1400018f1  cmp     [rcx], ax
0x1400018f4  jnz     short loc_14000191D
0x1400018f6  movsxd  rax, dword ptr [rcx+3Ch]
0x1400018fa  test    eax, eax
0x1400018fc  js      short loc_14000191D
0x1400018fe  cmp     eax, 10000000h
0x140001903  jnb     short loc_14000191D
0x140001905  lea     rdx, [rcx+rax]
0x140001909  mov     [rsp+18h+var_18], rdx
0x14000190d  xor     eax, eax
0x14000190f  cmp     dword ptr [rdx], 4550h
0x140001915  cmovnz  rdx, rax
0x140001919  mov     [rsp+18h+var_18], rdx
0x14000191d  jmp     short loc_140001925
0x14000191f  xor     edx, edx
0x140001921  mov     [rsp+18h+var_18], rdx
0x140001925  mov     rax, rdx
0x140001928  add     rsp, 18h
0x14000192c  retn
```
