# RtlpImageNtHeader

- ea: `0x14000139c`
- end: `0x1400013ed`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400013f4`

## callees

- `0x14000139c`

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
0x14000139c  sub     rsp, 18h
0x1400013a0  xor     edx, edx
0x1400013a2  lea     rax, [rcx-1]
0x1400013a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400013aa  ja      short loc_1400013E5
0x1400013ac  mov     eax, 5A4Dh
0x1400013b1  cmp     [rcx], ax
0x1400013b4  jnz     short loc_1400013DD
0x1400013b6  movsxd  rax, dword ptr [rcx+3Ch]
0x1400013ba  test    eax, eax
0x1400013bc  js      short loc_1400013DD
0x1400013be  cmp     eax, 10000000h
0x1400013c3  jnb     short loc_1400013DD
0x1400013c5  lea     rdx, [rcx+rax]
0x1400013c9  mov     [rsp+18h+var_18], rdx
0x1400013cd  xor     eax, eax
0x1400013cf  cmp     dword ptr [rdx], 4550h
0x1400013d5  cmovnz  rdx, rax
0x1400013d9  mov     [rsp+18h+var_18], rdx
0x1400013dd  jmp     short loc_1400013E5
0x1400013df  xor     edx, edx
0x1400013e1  mov     [rsp+18h+var_18], rdx
0x1400013e5  mov     rax, rdx
0x1400013e8  add     rsp, 18h
0x1400013ec  retn
```
