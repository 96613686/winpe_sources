# RtlpImageNtHeader

- ea: `0x1400030cc`
- end: `0x14000311d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140003124`

## callees

- `0x1400030cc`

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
0x1400030cc  sub     rsp, 18h
0x1400030d0  xor     edx, edx
0x1400030d2  lea     rax, [rcx-1]
0x1400030d6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400030da  ja      short loc_140003115
0x1400030dc  mov     eax, 5A4Dh
0x1400030e1  cmp     [rcx], ax
0x1400030e4  jnz     short loc_14000310D
0x1400030e6  movsxd  rax, dword ptr [rcx+3Ch]
0x1400030ea  test    eax, eax
0x1400030ec  js      short loc_14000310D
0x1400030ee  cmp     eax, 10000000h
0x1400030f3  jnb     short loc_14000310D
0x1400030f5  lea     rdx, [rcx+rax]
0x1400030f9  mov     [rsp+18h+var_18], rdx
0x1400030fd  xor     eax, eax
0x1400030ff  cmp     dword ptr [rdx], 4550h
0x140003105  cmovnz  rdx, rax
0x140003109  mov     [rsp+18h+var_18], rdx
0x14000310d  jmp     short loc_140003115
0x14000310f  xor     edx, edx
0x140003111  mov     [rsp+18h+var_18], rdx
0x140003115  mov     rax, rdx
0x140003118  add     rsp, 18h
0x14000311c  retn
```
