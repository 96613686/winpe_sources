# aacDecoder_ConfigCallback

- ea: `0x180008320`
- end: `0x1800083d9`
- name: `aacDecoder_ConfigCallback`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180006958`
- `0x1800069ec`
- `0x180008320`
- `0x1800095c0`
- `0x18002f280`
- `0x18002f3c0`

## pseudocode

```c
__int64 __fastcall aacDecoder_ConfigCallback(__int64 a1, __int64 a2, char a3, _BYTE *a4)
{
  int v5; // edi
  __int64 result; // rax

  v5 = CAacDecoder_Init((int *)a1, a2, a3, a4);
  if ( !(unsigned int)CDK_chMapDescr_isValid(a1 + 864) )
    return 1026;
  if ( !v5 )
  {
    if ( (*(_BYTE *)(a1 + 68) & 0x30) != 0
      && *(_DWORD *)(a1 + 2404) == -1
      && CConcealment_GetDelay((struct CConcealParams_fl *)(a1 + 2128))
      || (*(_DWORD *)(a1 + 68) & 0x4300) != 0 && CConcealment_GetDelay((struct CConcealParams_fl *)(a1 + 2128)) )
    {
      setConcealMethod(a1, 1);
    }
    aacDecoder_setMetadataExpiry(a1, *(unsigned int *)(a1 + 4344));
    return 0;
  }
  if ( v5 == 8203 )
    return 515;
  result = 513;
  if ( (unsigned int)(v5 - 0x2000) <= 0xFFF )
    return 1026;
  return result;
}

```

## disassembly

```asm
0x180008320  mov     [rsp+arg_0], rbx
0x180008325  push    rdi
0x180008326  sub     rsp, 20h
0x18000832a  mov     rbx, rcx
0x18000832d  call    ?CAacDecoder_Init@@YA?AW4AAC_DECODER_ERROR@@PEAUAAC_DECODER_INSTANCE@@PEBUCSAudioSpecificConfig@@EPEAE@Z; CAacDecoder_Init(AAC_DECODER_INSTANCE *,CSAudioSpecificConfig const *,uchar,uchar *)
0x180008332  lea     rcx, [rbx+360h]
0x180008339  mov     edi, eax
0x18000833b  call    CDK_chMapDescr_isValid
0x180008340  test    eax, eax
0x180008342  jz      loc_1800083D2
0x180008348  test    edi, edi
0x18000834a  jnz     short loc_180008377
0x18000834c  test    byte ptr [rbx+44h], 30h
0x180008350  jnz     short loc_180008386
0x180008352  test    dword ptr [rbx+44h], 4300h
0x180008359  jnz     short loc_1800083A1
0x18000835b  mov     edx, [rbx+10F8h]
0x180008361  mov     rcx, rbx
0x180008364  call    aacDecoder_setMetadataExpiry
0x180008369  xor     eax, eax
0x18000836b  mov     rbx, [rsp+28h+arg_0]
0x180008370  add     rsp, 20h
0x180008374  pop     rdi
0x180008375  retn
0x180008377  cmp     edi, 200Bh
0x18000837d  jnz     short loc_1800083C0
0x18000837f  mov     eax, 203h
0x180008384  jmp     short loc_18000836B
0x180008386  cmp     dword ptr [rbx+964h], 0FFFFFFFFh
0x18000838d  jnz     short loc_180008352
0x18000838f  lea     rcx, [rbx+850h]; struct CConcealParams_fl *
0x180008396  call    ?CConcealment_GetDelay@@YAIPEAUCConcealParams_fl@@@Z; CConcealment_GetDelay(CConcealParams_fl *)
0x18000839b  test    eax, eax
0x18000839d  jnz     short loc_1800083B1
0x18000839f  jmp     short loc_180008352
0x1800083a1  lea     rcx, [rbx+850h]; struct CConcealParams_fl *
0x1800083a8  call    ?CConcealment_GetDelay@@YAIPEAUCConcealParams_fl@@@Z; CConcealment_GetDelay(CConcealParams_fl *)
0x1800083ad  test    eax, eax
0x1800083af  jz      short loc_18000835B
0x1800083b1  mov     edx, 1
0x1800083b6  mov     rcx, rbx
0x1800083b9  call    setConcealMethod
0x1800083be  jmp     short loc_18000835B
0x1800083c0  lea     eax, [rdi-2000h]
0x1800083c6  cmp     eax, 0FFFh
0x1800083cb  mov     eax, 201h
0x1800083d0  ja      short loc_18000836B
0x1800083d2  mov     eax, 402h
0x1800083d7  jmp     short loc_18000836B
```
