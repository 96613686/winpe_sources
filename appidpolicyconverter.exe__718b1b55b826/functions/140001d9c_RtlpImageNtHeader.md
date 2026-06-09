# RtlpImageNtHeader

- ea: `0x140001d9c`
- end: `0x140001ded`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001df4`

## callees

- `0x140001d9c`

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
0x140001d9c  sub     rsp, 18h
0x140001da0  xor     edx, edx
0x140001da2  lea     rax, [rcx-1]
0x140001da6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001daa  ja      short loc_140001DE5
0x140001dac  mov     eax, 5A4Dh
0x140001db1  cmp     [rcx], ax
0x140001db4  jnz     short loc_140001DDD
0x140001db6  movsxd  rax, dword ptr [rcx+3Ch]
0x140001dba  test    eax, eax
0x140001dbc  js      short loc_140001DDD
0x140001dbe  cmp     eax, 10000000h
0x140001dc3  jnb     short loc_140001DDD
0x140001dc5  lea     rdx, [rcx+rax]
0x140001dc9  mov     [rsp+18h+var_18], rdx
0x140001dcd  xor     eax, eax
0x140001dcf  cmp     dword ptr [rdx], 4550h
0x140001dd5  cmovnz  rdx, rax
0x140001dd9  mov     [rsp+18h+var_18], rdx
0x140001ddd  jmp     short loc_140001DE5
0x140001ddf  xor     edx, edx
0x140001de1  mov     [rsp+18h+var_18], rdx
0x140001de5  mov     rax, rdx
0x140001de8  add     rsp, 18h
0x140001dec  retn
```
