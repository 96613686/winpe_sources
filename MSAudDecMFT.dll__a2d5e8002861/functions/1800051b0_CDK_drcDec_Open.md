# CDK_drcDec_Open

- ea: `0x1800051b0`
- end: `0x180005280`
- name: `CDK_drcDec_Open`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005288`

## callees

- `0x1800051b0`
- `0x18000543c`
- `0x180005bb4`
- `0x1800413ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800051d3`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800051f5`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180005221`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800051d3`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800051f5`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180005221`

## pseudocode

```c
__int64 __fastcall CDK_drcDec_Open(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  void *v4; // rax
  _DWORD *v5; // rax
  __int64 result; // rax
  bool v7; // zf

  CDKinit_check();
  v2 = calloc(1u, 0x6500u);
  *a1 = v2;
  v3 = v2;
  if ( !v2 )
    return 4294957297LL;
  v4 = calloc(1u, 0x784u);
  v3[2641] = v4;
  if ( !v4 )
    return 4294957297LL;
  *(_QWORD *)((char *)v3 + 4) = 3;
  *(_DWORD *)v3 = -1;
  v5 = calloc(1u, 0x5D8u);
  if ( !v5 )
    return 4294957297LL;
  *v5 = -1;
  v3[3] = v5;
  result = drcDec_SelectionProcess_Init(v5);
  if ( (_DWORD)result )
    return 4294957296LL;
  v7 = (*((_BYTE *)v3 + 4) & 2) == 0;
  *((_DWORD *)v3 + 8) = 1;
  if ( !v7 )
    return (unsigned int)drcDec_GainDecoder_Open(v3 + 2) != 0 ? 0xFFFFD8F1 : 0;
  return result;
}

```

## disassembly

```asm
0x1800051b0  mov     [rsp+arg_0], rbx
0x1800051b5  mov     [rsp+arg_8], rsi
0x1800051ba  push    rdi
0x1800051bb  sub     rsp, 20h
0x1800051bf  mov     rbx, rcx
0x1800051c2  call    CDKinit_check
0x1800051c7  mov     esi, 1
0x1800051cc  mov     edx, 6500h; Size
0x1800051d1  mov     ecx, esi; Count
0x1800051d3  call    cs:__imp_calloc
0x1800051da  nop     dword ptr [rax+rax+00h]
0x1800051df  mov     [rbx], rax
0x1800051e2  mov     rdi, rax
0x1800051e5  test    rax, rax
0x1800051e8  jz      loc_180005279
0x1800051ee  mov     edx, 784h; Size
0x1800051f3  mov     ecx, esi; Count
0x1800051f5  call    cs:__imp_calloc
0x1800051fc  nop     dword ptr [rax+rax+00h]
0x180005201  mov     [rdi+5288h], rax
0x180005208  test    rax, rax
0x18000520b  jz      short loc_180005279
0x18000520d  or      ebx, 0FFFFFFFFh
0x180005210  mov     qword ptr [rdi+4], 3
0x180005218  mov     edx, 5D8h; Size
0x18000521d  mov     [rdi], ebx
0x18000521f  mov     ecx, esi; Count
0x180005221  call    cs:__imp_calloc
0x180005228  nop     dword ptr [rax+rax+00h]
0x18000522d  test    rax, rax
0x180005230  jz      short loc_180005279
0x180005232  mov     [rax], ebx
0x180005234  mov     rcx, rax
0x180005237  mov     [rdi+18h], rax
0x18000523b  call    ?drcDec_SelectionProcess_Init@@YA?AW4DRCDEC_SELECTION_PROCESS_RETURN@@PEAUs_drcdec_selection_process@@@Z; drcDec_SelectionProcess_Init(s_drcdec_selection_process *)
0x180005240  test    eax, eax
0x180005242  jnz     short loc_180005272
0x180005244  test    byte ptr [rdi+4], 2
0x180005248  mov     [rdi+20h], esi
0x18000524b  jnz     short loc_18000525E
0x18000524d  mov     rbx, [rsp+28h+arg_0]
0x180005252  mov     rsi, [rsp+28h+arg_8]
0x180005257  add     rsp, 20h
0x18000525b  pop     rdi
0x18000525c  retn
0x18000525e  lea     rcx, [rdi+10h]
0x180005262  call    ?drcDec_GainDecoder_Open@@YA?AW4DRC_ERROR@@PEAPEAUDRC_GAIN_DECODER@@@Z; drcDec_GainDecoder_Open(DRC_GAIN_DECODER * *)
0x180005267  neg     eax
0x180005269  sbb     eax, eax
0x18000526b  and     eax, 0FFFFD8F1h
0x180005270  jmp     short loc_18000524D
0x180005272  mov     eax, 0FFFFD8F0h
0x180005277  jmp     short loc_18000524D
0x180005279  mov     eax, 0FFFFD8F1h
0x18000527e  jmp     short loc_18000524D
```
