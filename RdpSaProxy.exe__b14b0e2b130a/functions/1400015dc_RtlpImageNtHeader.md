# RtlpImageNtHeader

- ea: `0x1400015dc`
- end: `0x14000162d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001634`

## callees

- `0x1400015dc`

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
0x1400015dc  sub     rsp, 18h
0x1400015e0  xor     edx, edx
0x1400015e2  lea     rax, [rcx-1]
0x1400015e6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400015ea  ja      short loc_140001625
0x1400015ec  mov     eax, 5A4Dh
0x1400015f1  cmp     [rcx], ax
0x1400015f4  jnz     short loc_14000161D
0x1400015f6  movsxd  rax, dword ptr [rcx+3Ch]
0x1400015fa  test    eax, eax
0x1400015fc  js      short loc_14000161D
0x1400015fe  cmp     eax, 10000000h
0x140001603  jnb     short loc_14000161D
0x140001605  lea     rdx, [rcx+rax]
0x140001609  mov     [rsp+18h+var_18], rdx
0x14000160d  xor     eax, eax
0x14000160f  cmp     dword ptr [rdx], 4550h
0x140001615  cmovnz  rdx, rax
0x140001619  mov     [rsp+18h+var_18], rdx
0x14000161d  jmp     short loc_140001625
0x14000161f  xor     edx, edx
0x140001621  mov     [rsp+18h+var_18], rdx
0x140001625  mov     rax, rdx
0x140001628  add     rsp, 18h
0x14000162c  retn
```
