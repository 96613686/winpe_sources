# VUpdatePrivatePrinterData

- ea: `0x18002da4c`
- end: `0x18002db10`
- name: `VUpdatePrivatePrinterData`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002ea84`

## callees

- `0x18002da4c`
- `0x18002ea3c`

## string_xrefs

- `0x18002dad2`: `Protocol`

## pseudocode

```c
__int64 __fastcall VUpdatePrivatePrinterData(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // r8d
  __int64 result; // rax
  int v9; // ecx
  int v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = 0;
  if ( (unsigned int)BGetPrinterDataDWord(a1, L"FreeMem", &v10) )
  {
    v7 = *(_DWORD *)(a4 + 80) < 2u ? 176128 : 254976;
    if ( v10 << 10 > v7 )
      v7 = v10 << 10;
    *(_DWORD *)(a2 + 8) = v7;
  }
  if ( (unsigned int)BGetPrinterDataDWord(a1, L"JobTimeOut", &v10) )
    *(_DWORD *)(a2 + 12) = v10;
  result = BGetPrinterDataDWord(a1, L"Protocol", &v10);
  if ( (_DWORD)result )
  {
    result = (unsigned __int16)v10;
    *(_WORD *)(a2 + 38) = v10;
    if ( (unsigned int)result > 0x10 || (v9 = 65557, !_bittest(&v9, result)) )
    {
      result = 0;
      *(_WORD *)(a2 + 38) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002da4c  mov     rax, rsp
0x18002da4f  mov     [rax+8], rbx
0x18002da53  mov     [rax+10h], rsi
0x18002da57  mov     [rax+18h], r8d
0x18002da5b  push    rdi
0x18002da5c  sub     rsp, 20h
0x18002da60  mov     rbx, rdx
0x18002da63  mov     dword ptr [rax+18h], 0
0x18002da6a  lea     rdx, aFreemem; "FreeMem"
0x18002da71  mov     rsi, r9
0x18002da74  lea     r8, [rax+18h]
0x18002da78  mov     rdi, rcx
0x18002da7b  call    BGetPrinterDataDWord
0x18002da80  test    eax, eax
0x18002da82  jz      short loc_18002DAAB
0x18002da84  cmp     dword ptr [rsi+50h], 2
0x18002da88  mov     eax, [rsp+28h+arg_10]
0x18002da8c  sbb     r8d, r8d
0x18002da8f  shl     eax, 0Ah
0x18002da92  and     r8d, 0FFFECC00h
0x18002da99  add     r8d, 3E400h
0x18002daa0  cmp     eax, r8d
0x18002daa3  cmova   r8d, eax
0x18002daa7  mov     [rbx+8], r8d
0x18002daab  lea     r8, [rsp+28h+arg_10]
0x18002dab0  mov     rcx, rdi
0x18002dab3  lea     rdx, aJobtimeout; "JobTimeOut"
0x18002daba  call    BGetPrinterDataDWord
0x18002dabf  test    eax, eax
0x18002dac1  jz      short loc_18002DACA
0x18002dac3  mov     eax, [rsp+28h+arg_10]
0x18002dac7  mov     [rbx+0Ch], eax
0x18002daca  lea     r8, [rsp+28h+arg_10]
0x18002dacf  mov     rcx, rdi
0x18002dad2  lea     rdx, aProtocol; "Protocol"
0x18002dad9  call    BGetPrinterDataDWord
0x18002dade  test    eax, eax
0x18002dae0  jz      short loc_18002DB00
0x18002dae2  movzx   eax, word ptr [rsp+28h+arg_10]
0x18002dae7  mov     [rbx+26h], ax
0x18002daeb  cmp     eax, 10h
0x18002daee  ja      short loc_18002DAFA
0x18002daf0  mov     ecx, 10015h
0x18002daf5  bt      ecx, eax
0x18002daf8  jb      short loc_18002DB00
0x18002dafa  xor     eax, eax
0x18002dafc  mov     [rbx+26h], ax
0x18002db00  mov     rbx, [rsp+28h+arg_0]
0x18002db05  mov     rsi, [rsp+28h+arg_8]
0x18002db0a  add     rsp, 20h
0x18002db0e  pop     rdi
0x18002db0f  retn
```
