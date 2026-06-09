# std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>::~vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>(void)

- ea: `0x1800031a4`
- end: `0x18000325b`
- name: `??1?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(__int64)`
- caller_count: `18`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004690`
- `0x18001fb24`
- `0x18001ff74`
- `0x180022204`
- `0x180023660`
- `0x180024d00`
- `0x180024fa8`
- `0x180025cac`
- `0x1800264a8`
- `0x1800269a4`
- `0x180027df8`
- `0x180028534`
- `0x180029310`
- `0x180029f30`
- `0x180033ad5`
- `0x180033b76`
- `0x180033c72`
- `0x180033cb9`

## callees

- `0x180001900`
- `0x1800031a4`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800031cb`
- `OLEAUT32!__imp_VariantClear` at `0x1800031cb`

## pseudocode

```c
void __fastcall std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(__int64 a1)
{
  VARIANTARG *v1; // rbx
  VARIANTARG *v3; // rsi
  VARIANTARG *v4; // rcx
  VARIANTARG *pRecInfo; // rax

  v1 = *(VARIANTARG **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(VARIANTARG **)(a1 + 8);
    while ( v1 != v3 )
      VariantClear(v1++);
    v4 = *(VARIANTARG **)a1;
    if ( (unsigned __int64)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3)) < 0x1000 )
    {
      pRecInfo = *(VARIANTARG **)a1;
    }
    else
    {
      pRecInfo = (VARIANTARG *)v4[-1].pRecInfo;
      if ( (unsigned __int64)((char *)v4 - (char *)pRecInfo - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(pRecInfo);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x1800031a4  mov     [rsp+arg_0], rbx
0x1800031a9  mov     [rsp+arg_8], rsi
0x1800031ae  push    rdi
0x1800031af  sub     rsp, 20h
0x1800031b3  mov     rbx, [rcx]
0x1800031b6  mov     rdi, rcx
0x1800031b9  test    rbx, rbx
0x1800031bc  jz      loc_18000324B
0x1800031c2  mov     rsi, [rcx+8]
0x1800031c6  jmp     short loc_1800031D5
0x1800031c8  mov     rcx, rbx; pvarg
0x1800031cb  call    cs:__imp_VariantClear
0x1800031d1  add     rbx, 18h
0x1800031d5  cmp     rbx, rsi
0x1800031d8  jnz     short loc_1800031C8
0x1800031da  mov     rcx, [rdi]
0x1800031dd  mov     rdx, 0AAAAAAAAAAAAAAABh
0x1800031e7  mov     rax, [rdi+10h]
0x1800031eb  sub     rax, rcx
0x1800031ee  sar     rax, 3
0x1800031f2  imul    rax, rdx
0x1800031f6  lea     rax, [rax+rax*2]
0x1800031fa  lea     rdx, ds:0[rax*8]
0x180003202  cmp     rdx, 1000h
0x180003209  jb      short loc_180003229
0x18000320b  mov     rax, [rcx-8]
0x18000320f  sub     rcx, rax
0x180003212  sub     rcx, 8
0x180003216  cmp     rcx, 1Fh
0x18000321a  ja      short loc_180003222
0x18000321c  add     rdx, 27h ; '''
0x180003220  jmp     short loc_18000322C
0x180003222  mov     ecx, 5
0x180003227  int     29h; Win8: RtlFailFast(ecx)
0x180003229  mov     rax, rcx
0x18000322c  mov     rcx, rax; Block
0x18000322f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003234  mov     qword ptr [rdi], 0
0x18000323b  mov     qword ptr [rdi+8], 0
0x180003243  mov     qword ptr [rdi+10h], 0
0x18000324b  mov     rbx, [rsp+28h+arg_0]
0x180003250  mov     rsi, [rsp+28h+arg_8]
0x180003255  add     rsp, 20h
0x180003259  pop     rdi
0x18000325a  retn
```
