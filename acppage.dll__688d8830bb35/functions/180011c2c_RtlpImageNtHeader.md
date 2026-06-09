# RtlpImageNtHeader

- ea: `0x180011c2c`
- end: `0x180011c7d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800119a0`

## callees

- `0x180011c2c`

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
0x180011c2c  sub     rsp, 18h
0x180011c30  xor     edx, edx
0x180011c32  lea     rax, [rcx-1]
0x180011c36  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011c3a  ja      short loc_180011C75
0x180011c3c  mov     eax, 5A4Dh
0x180011c41  cmp     [rcx], ax
0x180011c44  jnz     short loc_180011C6D
0x180011c46  movsxd  rax, dword ptr [rcx+3Ch]
0x180011c4a  test    eax, eax
0x180011c4c  js      short loc_180011C6D
0x180011c4e  cmp     eax, 10000000h
0x180011c53  jnb     short loc_180011C6D
0x180011c55  lea     rdx, [rcx+rax]
0x180011c59  mov     [rsp+18h+var_18], rdx
0x180011c5d  xor     eax, eax
0x180011c5f  cmp     dword ptr [rdx], 4550h
0x180011c65  cmovnz  rdx, rax
0x180011c69  mov     [rsp+18h+var_18], rdx
0x180011c6d  jmp     short loc_180011C75
0x180011c6f  xor     edx, edx
0x180011c71  mov     [rsp+18h+var_18], rdx
0x180011c75  mov     rax, rdx
0x180011c78  add     rsp, 18h
0x180011c7c  retn
```
