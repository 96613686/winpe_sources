# RtlpImageNtHeader

- ea: `0x140001c2c`
- end: `0x140001c7d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001c84`

## callees

- `0x140001c2c`

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
0x140001c2c  sub     rsp, 18h
0x140001c30  xor     edx, edx
0x140001c32  lea     rax, [rcx-1]
0x140001c36  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001c3a  ja      short loc_140001C75
0x140001c3c  mov     eax, 5A4Dh
0x140001c41  cmp     [rcx], ax
0x140001c44  jnz     short loc_140001C6D
0x140001c46  movsxd  rax, dword ptr [rcx+3Ch]
0x140001c4a  test    eax, eax
0x140001c4c  js      short loc_140001C6D
0x140001c4e  cmp     eax, 10000000h
0x140001c53  jnb     short loc_140001C6D
0x140001c55  lea     rdx, [rcx+rax]
0x140001c59  mov     [rsp+18h+var_18], rdx
0x140001c5d  xor     eax, eax
0x140001c5f  cmp     dword ptr [rdx], 4550h
0x140001c65  cmovnz  rdx, rax
0x140001c69  mov     [rsp+18h+var_18], rdx
0x140001c6d  jmp     short loc_140001C75
0x140001c6f  xor     edx, edx
0x140001c71  mov     [rsp+18h+var_18], rdx
0x140001c75  mov     rax, rdx
0x140001c78  add     rsp, 18h
0x140001c7c  retn
```
