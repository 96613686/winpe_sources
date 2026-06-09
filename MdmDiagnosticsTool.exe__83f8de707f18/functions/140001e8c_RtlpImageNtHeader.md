# RtlpImageNtHeader

- ea: `0x140001e8c`
- end: `0x140001edd`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001ee4`

## callees

- `0x140001e8c`

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
0x140001e8c  sub     rsp, 18h
0x140001e90  xor     edx, edx
0x140001e92  lea     rax, [rcx-1]
0x140001e96  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001e9a  ja      short loc_140001ED5
0x140001e9c  mov     eax, 5A4Dh
0x140001ea1  cmp     [rcx], ax
0x140001ea4  jnz     short loc_140001ECD
0x140001ea6  movsxd  rax, dword ptr [rcx+3Ch]
0x140001eaa  test    eax, eax
0x140001eac  js      short loc_140001ECD
0x140001eae  cmp     eax, 10000000h
0x140001eb3  jnb     short loc_140001ECD
0x140001eb5  lea     rdx, [rcx+rax]
0x140001eb9  mov     [rsp+18h+var_18], rdx
0x140001ebd  xor     eax, eax
0x140001ebf  cmp     dword ptr [rdx], 4550h
0x140001ec5  cmovnz  rdx, rax
0x140001ec9  mov     [rsp+18h+var_18], rdx
0x140001ecd  jmp     short loc_140001ED5
0x140001ecf  xor     edx, edx
0x140001ed1  mov     [rsp+18h+var_18], rdx
0x140001ed5  mov     rax, rdx
0x140001ed8  add     rsp, 18h
0x140001edc  retn
```
