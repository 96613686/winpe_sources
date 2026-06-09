# RtlpImageNtHeader

- ea: `0x140001e5c`
- end: `0x140001ead`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001eb4`

## callees

- `0x140001e5c`

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
0x140001e5c  sub     rsp, 18h
0x140001e60  xor     edx, edx
0x140001e62  lea     rax, [rcx-1]
0x140001e66  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001e6a  ja      short loc_140001EA5
0x140001e6c  mov     eax, 5A4Dh
0x140001e71  cmp     [rcx], ax
0x140001e74  jnz     short loc_140001E9D
0x140001e76  movsxd  rax, dword ptr [rcx+3Ch]
0x140001e7a  test    eax, eax
0x140001e7c  js      short loc_140001E9D
0x140001e7e  cmp     eax, 10000000h
0x140001e83  jnb     short loc_140001E9D
0x140001e85  lea     rdx, [rcx+rax]
0x140001e89  mov     [rsp+18h+var_18], rdx
0x140001e8d  xor     eax, eax
0x140001e8f  cmp     dword ptr [rdx], 4550h
0x140001e95  cmovnz  rdx, rax
0x140001e99  mov     [rsp+18h+var_18], rdx
0x140001e9d  jmp     short loc_140001EA5
0x140001e9f  xor     edx, edx
0x140001ea1  mov     [rsp+18h+var_18], rdx
0x140001ea5  mov     rax, rdx
0x140001ea8  add     rsp, 18h
0x140001eac  retn
```
