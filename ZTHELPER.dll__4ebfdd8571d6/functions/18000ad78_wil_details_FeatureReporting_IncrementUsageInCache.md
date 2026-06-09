# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18000ad78`
- end: `0x18000ae4d`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ae54`

## callees

- `0x18000ad78`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementUsageInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  _DWORD *v5; // r10
  BOOL v8; // edi
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 4;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 14) & 1) != v8 )
    {
      if ( ((v9 >> 5) & 0x1FF) != 0 )
      {
        a4[1] = (v9 >> 5) & 0x1FF;
        v5 = a4 + 2;
        a4[2] = a2 == 0 ? 4 : 0;
        v9 = v4 & 0xFFFFC01E | 1;
      }
      v10 = 0;
      if ( a2 == 4 )
        v10 = 0x4000;
      v9 = v9 & 0xFFFFBFFF | v10;
    }
    v11 = (v9 >> 5) & 0x1FF;
    v12 = v11 + 1;
    if ( v11 + 1 > 0x1FF || v12 < v11 )
    {
      LOWORD(v12) = 1;
      *v5 = a2;
      a4[1] = v11;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(
                             a1,
                             v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)(32 * v12)) & 0x3FE0,
                             v4);
    if ( v4 == (_DWORD)result )
      break;
    v4 = result;
  }
  a4[4] = 0;
  *a4 = (v4 & 1) == 0;
  return result;
}

```

## disassembly

```asm
0x18000ad78  push    rbx
0x18000ad7a  push    rsi
0x18000ad7b  push    rdi
0x18000ad7c  mov     r8d, [rcx]
0x18000ad7f  lea     r10, [r9+8]
0x18000ad83  xor     edi, edi
0x18000ad85  mov     ebx, edx
0x18000ad87  cmp     edx, 4
0x18000ad8a  mov     rsi, rcx
0x18000ad8d  setz    dil
0x18000ad91  mov     eax, r8d
0x18000ad94  mov     dword ptr [r9+4], 0
0x18000ad9c  or      eax, 1
0x18000ad9f  mov     ecx, eax
0x18000ada1  shr     ecx, 0Eh
0x18000ada4  and     ecx, 1
0x18000ada7  cmp     ecx, edi
0x18000ada9  jz      short loc_18000ADED
0x18000adab  mov     r11d, eax
0x18000adae  shr     r11d, 5
0x18000adb2  and     r11d, 1FFh
0x18000adb9  jbe     short loc_18000ADD6
0x18000adbb  mov     ecx, ebx
0x18000adbd  mov     [r9+4], r11d
0x18000adc1  neg     ecx
0x18000adc3  lea     r10, [r9+8]
0x18000adc7  sbb     edx, edx
0x18000adc9  not     edx
0x18000adcb  and     edx, 4
0x18000adce  mov     [r10], edx
0x18000add1  and     eax, 0FFFFC01Fh
0x18000add6  xor     edx, edx
0x18000add8  mov     ecx, 4000h
0x18000addd  cmp     ebx, 4
0x18000ade0  cmovz   edx, ecx
0x18000ade3  mov     ecx, eax
0x18000ade5  btr     ecx, 0Eh
0x18000ade9  mov     eax, edx
0x18000adeb  or      eax, ecx
0x18000aded  mov     ecx, eax
0x18000adef  shr     ecx, 5
0x18000adf2  and     ecx, 1FFh
0x18000adf8  lea     edx, [rcx+1]
0x18000adfb  cmp     edx, 1FFh
0x18000ae01  ja      short loc_18000AE0D
0x18000ae03  cmp     edx, ecx
0x18000ae05  jb      short loc_18000AE0D
0x18000ae07  lea     r10, [r9+8]
0x18000ae0b  jmp     short loc_18000AE19
0x18000ae0d  mov     edx, 1
0x18000ae12  mov     [r10], ebx
0x18000ae15  mov     [r9+4], ecx
0x18000ae19  shl     edx, 5
0x18000ae1c  xor     edx, eax
0x18000ae1e  and     edx, 3FE0h
0x18000ae24  xor     edx, eax
0x18000ae26  mov     eax, r8d
0x18000ae29  lock cmpxchg [rsi], edx
0x18000ae2d  jz      short loc_18000AE37
0x18000ae2f  mov     r8d, eax
0x18000ae32  jmp     loc_18000AD91
0x18000ae37  not     r8d
0x18000ae3a  mov     dword ptr [r9+10h], 0
0x18000ae42  and     r8d, 1
0x18000ae46  mov     [r9], r8d
0x18000ae49  pop     rdi
0x18000ae4a  pop     rsi
0x18000ae4b  pop     rbx
0x18000ae4c  retn
```
