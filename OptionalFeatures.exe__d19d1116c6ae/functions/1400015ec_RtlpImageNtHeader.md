# RtlpImageNtHeader

- ea: `0x1400015ec`
- end: `0x14000163d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001644`

## callees

- `0x1400015ec`

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
0x1400015ec  sub     rsp, 18h
0x1400015f0  xor     edx, edx
0x1400015f2  lea     rax, [rcx-1]
0x1400015f6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400015fa  ja      short loc_140001635
0x1400015fc  mov     eax, 5A4Dh
0x140001601  cmp     [rcx], ax
0x140001604  jnz     short loc_14000162D
0x140001606  movsxd  rax, dword ptr [rcx+3Ch]
0x14000160a  test    eax, eax
0x14000160c  js      short loc_14000162D
0x14000160e  cmp     eax, 10000000h
0x140001613  jnb     short loc_14000162D
0x140001615  lea     rdx, [rcx+rax]
0x140001619  mov     [rsp+18h+var_18], rdx
0x14000161d  xor     eax, eax
0x14000161f  cmp     dword ptr [rdx], 4550h
0x140001625  cmovnz  rdx, rax
0x140001629  mov     [rsp+18h+var_18], rdx
0x14000162d  jmp     short loc_140001635
0x14000162f  xor     edx, edx
0x140001631  mov     [rsp+18h+var_18], rdx
0x140001635  mov     rax, rdx
0x140001638  add     rsp, 18h
0x14000163c  retn
```
