# RtlpImageNtHeader

- ea: `0x1400020ac`
- end: `0x1400020fd`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140002104`

## callees

- `0x1400020ac`

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
0x1400020ac  sub     rsp, 18h
0x1400020b0  xor     edx, edx
0x1400020b2  lea     rax, [rcx-1]
0x1400020b6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400020ba  ja      short loc_1400020F5
0x1400020bc  mov     eax, 5A4Dh
0x1400020c1  cmp     [rcx], ax
0x1400020c4  jnz     short loc_1400020ED
0x1400020c6  movsxd  rax, dword ptr [rcx+3Ch]
0x1400020ca  test    eax, eax
0x1400020cc  js      short loc_1400020ED
0x1400020ce  cmp     eax, 10000000h
0x1400020d3  jnb     short loc_1400020ED
0x1400020d5  lea     rdx, [rcx+rax]
0x1400020d9  mov     [rsp+18h+var_18], rdx
0x1400020dd  xor     eax, eax
0x1400020df  cmp     dword ptr [rdx], 4550h
0x1400020e5  cmovnz  rdx, rax
0x1400020e9  mov     [rsp+18h+var_18], rdx
0x1400020ed  jmp     short loc_1400020F5
0x1400020ef  xor     edx, edx
0x1400020f1  mov     [rsp+18h+var_18], rdx
0x1400020f5  mov     rax, rdx
0x1400020f8  add     rsp, 18h
0x1400020fc  retn
```
