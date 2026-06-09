# RtlpImageNtHeader

- ea: `0x1400015bc`
- end: `0x14000160d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001614`

## callees

- `0x1400015bc`

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
0x1400015bc  sub     rsp, 18h
0x1400015c0  xor     edx, edx
0x1400015c2  lea     rax, [rcx-1]
0x1400015c6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400015ca  ja      short loc_140001605
0x1400015cc  mov     eax, 5A4Dh
0x1400015d1  cmp     [rcx], ax
0x1400015d4  jnz     short loc_1400015FD
0x1400015d6  movsxd  rax, dword ptr [rcx+3Ch]
0x1400015da  test    eax, eax
0x1400015dc  js      short loc_1400015FD
0x1400015de  cmp     eax, 10000000h
0x1400015e3  jnb     short loc_1400015FD
0x1400015e5  lea     rdx, [rcx+rax]
0x1400015e9  mov     [rsp+18h+var_18], rdx
0x1400015ed  xor     eax, eax
0x1400015ef  cmp     dword ptr [rdx], 4550h
0x1400015f5  cmovnz  rdx, rax
0x1400015f9  mov     [rsp+18h+var_18], rdx
0x1400015fd  jmp     short loc_140001605
0x1400015ff  xor     edx, edx
0x140001601  mov     [rsp+18h+var_18], rdx
0x140001605  mov     rax, rdx
0x140001608  add     rsp, 18h
0x14000160c  retn
```
