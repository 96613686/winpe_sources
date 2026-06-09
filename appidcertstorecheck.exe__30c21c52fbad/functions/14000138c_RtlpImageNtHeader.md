# RtlpImageNtHeader

- ea: `0x14000138c`
- end: `0x1400013dd`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400013e4`

## callees

- `0x14000138c`

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
0x14000138c  sub     rsp, 18h
0x140001390  xor     edx, edx
0x140001392  lea     rax, [rcx-1]
0x140001396  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000139a  ja      short loc_1400013D5
0x14000139c  mov     eax, 5A4Dh
0x1400013a1  cmp     [rcx], ax
0x1400013a4  jnz     short loc_1400013CD
0x1400013a6  movsxd  rax, dword ptr [rcx+3Ch]
0x1400013aa  test    eax, eax
0x1400013ac  js      short loc_1400013CD
0x1400013ae  cmp     eax, 10000000h
0x1400013b3  jnb     short loc_1400013CD
0x1400013b5  lea     rdx, [rcx+rax]
0x1400013b9  mov     [rsp+18h+var_18], rdx
0x1400013bd  xor     eax, eax
0x1400013bf  cmp     dword ptr [rdx], 4550h
0x1400013c5  cmovnz  rdx, rax
0x1400013c9  mov     [rsp+18h+var_18], rdx
0x1400013cd  jmp     short loc_1400013D5
0x1400013cf  xor     edx, edx
0x1400013d1  mov     [rsp+18h+var_18], rdx
0x1400013d5  mov     rax, rdx
0x1400013d8  add     rsp, 18h
0x1400013dc  retn
```
