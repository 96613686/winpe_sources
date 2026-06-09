# RtlpImageNtHeader

- ea: `0x140001f3c`
- end: `0x140001f8d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001f94`

## callees

- `0x140001f3c`

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
0x140001f3c  sub     rsp, 18h
0x140001f40  xor     edx, edx
0x140001f42  lea     rax, [rcx-1]
0x140001f46  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001f4a  ja      short loc_140001F85
0x140001f4c  mov     eax, 5A4Dh
0x140001f51  cmp     [rcx], ax
0x140001f54  jnz     short loc_140001F7D
0x140001f56  movsxd  rax, dword ptr [rcx+3Ch]
0x140001f5a  test    eax, eax
0x140001f5c  js      short loc_140001F7D
0x140001f5e  cmp     eax, 10000000h
0x140001f63  jnb     short loc_140001F7D
0x140001f65  lea     rdx, [rcx+rax]
0x140001f69  mov     [rsp+18h+var_18], rdx
0x140001f6d  xor     eax, eax
0x140001f6f  cmp     dword ptr [rdx], 4550h
0x140001f75  cmovnz  rdx, rax
0x140001f79  mov     [rsp+18h+var_18], rdx
0x140001f7d  jmp     short loc_140001F85
0x140001f7f  xor     edx, edx
0x140001f81  mov     [rsp+18h+var_18], rdx
0x140001f85  mov     rax, rdx
0x140001f88  add     rsp, 18h
0x140001f8c  retn
```
