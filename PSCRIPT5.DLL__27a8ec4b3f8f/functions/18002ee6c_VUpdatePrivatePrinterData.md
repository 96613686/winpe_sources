# VUpdatePrivatePrinterData

- ea: `0x18002ee6c`
- end: `0x18002ef31`
- name: `VUpdatePrivatePrinterData`
- size: `197`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800300e8`

## callees

- `0x18002ee6c`
- `0x180030098`

## string_xrefs

- `0x18002eef2`: `Protocol`

## pseudocode

```c
__int64 __fastcall VUpdatePrivatePrinterData(void *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // r8d
  __int64 result; // rax
  int v9; // ecx
  int v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = 0;
  if ( BGetPrinterDataDWord(a1, L"FreeMem", (BYTE *)&v10) )
  {
    v7 = *(_DWORD *)(a4 + 80) < 2u ? 176128 : 254976;
    if ( v10 << 10 > v7 )
      v7 = v10 << 10;
    *(_DWORD *)(a2 + 8) = v7;
  }
  if ( BGetPrinterDataDWord(a1, L"JobTimeOut", (BYTE *)&v10) )
    *(_DWORD *)(a2 + 12) = v10;
  result = BGetPrinterDataDWord(a1, L"Protocol", (BYTE *)&v10);
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
0x18002ee6c  mov     rax, rsp
0x18002ee6f  mov     [rax+8], rbx
0x18002ee73  mov     [rax+10h], rsi
0x18002ee77  mov     [rax+18h], r8d
0x18002ee7b  push    rdi
0x18002ee7c  sub     rsp, 20h
0x18002ee80  mov     rbx, rdx
0x18002ee83  mov     dword ptr [rax+18h], 0
0x18002ee8a  lea     rdx, aFreemem; "FreeMem"
0x18002ee91  mov     rsi, r9
0x18002ee94  lea     r8, [rax+18h]
0x18002ee98  mov     rdi, rcx
0x18002ee9b  call    BGetPrinterDataDWord
0x18002eea0  test    eax, eax
0x18002eea2  jz      short loc_18002EECB
0x18002eea4  cmp     dword ptr [rsi+50h], 2
0x18002eea8  mov     eax, [rsp+28h+arg_10]
0x18002eeac  sbb     r8d, r8d
0x18002eeaf  shl     eax, 0Ah
0x18002eeb2  and     r8d, 0FFFECC00h
0x18002eeb9  add     r8d, 3E400h
0x18002eec0  cmp     eax, r8d
0x18002eec3  cmova   r8d, eax
0x18002eec7  mov     [rbx+8], r8d
0x18002eecb  lea     r8, [rsp+28h+arg_10]
0x18002eed0  mov     rcx, rdi
0x18002eed3  lea     rdx, aJobtimeout; "JobTimeOut"
0x18002eeda  call    BGetPrinterDataDWord
0x18002eedf  test    eax, eax
0x18002eee1  jz      short loc_18002EEEA
0x18002eee3  mov     eax, [rsp+28h+arg_10]
0x18002eee7  mov     [rbx+0Ch], eax
0x18002eeea  lea     r8, [rsp+28h+arg_10]
0x18002eeef  mov     rcx, rdi
0x18002eef2  lea     rdx, aProtocol; "Protocol"
0x18002eef9  call    BGetPrinterDataDWord
0x18002eefe  test    eax, eax
0x18002ef00  jz      short loc_18002EF20
0x18002ef02  movzx   eax, word ptr [rsp+28h+arg_10]
0x18002ef07  mov     [rbx+26h], ax
0x18002ef0b  cmp     eax, 10h
0x18002ef0e  ja      short loc_18002EF1A
0x18002ef10  mov     ecx, 10015h
0x18002ef15  bt      ecx, eax
0x18002ef18  jb      short loc_18002EF20
0x18002ef1a  xor     eax, eax
0x18002ef1c  mov     [rbx+26h], ax
0x18002ef20  mov     rbx, [rsp+28h+arg_0]
0x18002ef25  mov     rsi, [rsp+28h+arg_8]
0x18002ef2a  add     rsp, 20h
0x18002ef2e  pop     rdi
0x18002ef2f  retn
```
