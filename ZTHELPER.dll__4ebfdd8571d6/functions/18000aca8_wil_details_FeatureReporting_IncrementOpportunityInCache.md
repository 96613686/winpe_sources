# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18000aca8`
- end: `0x18000ad71`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ae54`

## callees

- `0x18000aca8`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementOpportunityInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  int *v5; // r10
  BOOL v8; // ebx
  unsigned int v9; // eax
  int v10; // ecx
  int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 5;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 22) & 1) != v8 )
    {
      if ( ((v9 >> 15) & 0x7F) != 0 )
      {
        a4[1] = (v9 >> 15) & 0x7F;
        v10 = 5;
        v5 = a4 + 2;
        if ( a2 != 1 )
          v10 = 1;
        v9 = v4 & 0xFFC07FFE | 1;
        *v5 = v10;
      }
      v11 = 0;
      if ( a2 == 5 )
        v11 = 0x400000;
      v9 = v9 & 0xFFBFFFFF | v11;
    }
    v12 = (v9 >> 15) & 0x7F;
    v13 = v12 + 1;
    if ( v12 + 1 > 0x7F || v13 < v12 )
    {
      v13 = 1;
      *v5 = a2;
      a4[1] = v12;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(a1, v9 ^ (v9 ^ (v13 << 15)) & 0x3F8000, v4);
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
0x18000aca8  push    rbx
0x18000acaa  push    rsi
0x18000acab  push    rdi
0x18000acac  mov     r8d, [rcx]
0x18000acaf  lea     r10, [r9+8]
0x18000acb3  xor     ebx, ebx
0x18000acb5  mov     r11d, edx
0x18000acb8  cmp     edx, 5
0x18000acbb  mov     rdi, rcx
0x18000acbe  mov     esi, 1
0x18000acc3  setz    bl
0x18000acc6  mov     eax, r8d
0x18000acc9  mov     dword ptr [r9+4], 0
0x18000acd1  or      eax, esi
0x18000acd3  mov     ecx, eax
0x18000acd5  shr     ecx, 16h
0x18000acd8  and     ecx, esi
0x18000acda  cmp     ecx, ebx
0x18000acdc  jz      short loc_18000AD1B
0x18000acde  mov     edx, eax
0x18000ace0  shr     edx, 0Fh
0x18000ace3  and     edx, 7Fh
0x18000ace6  jbe     short loc_18000AD03
0x18000ace8  cmp     r11d, esi
0x18000aceb  mov     [r9+4], edx
0x18000acef  mov     ecx, 5
0x18000acf4  lea     r10, [r9+8]
0x18000acf8  cmovnz  ecx, esi
0x18000acfb  and     eax, 0FFC07FFFh
0x18000ad00  mov     [r10], ecx
0x18000ad03  xor     edx, edx
0x18000ad05  mov     ecx, 400000h
0x18000ad0a  cmp     r11d, 5
0x18000ad0e  cmovz   edx, ecx
0x18000ad11  mov     ecx, eax
0x18000ad13  btr     ecx, 16h
0x18000ad17  mov     eax, edx
0x18000ad19  or      eax, ecx
0x18000ad1b  mov     ecx, eax
0x18000ad1d  shr     ecx, 0Fh
0x18000ad20  and     ecx, 7Fh
0x18000ad23  lea     edx, [rcx+1]
0x18000ad26  cmp     edx, 7Fh
0x18000ad29  ja      short loc_18000AD35
0x18000ad2b  cmp     edx, ecx
0x18000ad2d  jb      short loc_18000AD35
0x18000ad2f  lea     r10, [r9+8]
0x18000ad33  jmp     short loc_18000AD3E
0x18000ad35  mov     edx, esi
0x18000ad37  mov     [r10], r11d
0x18000ad3a  mov     [r9+4], ecx
0x18000ad3e  shl     edx, 0Fh
0x18000ad41  xor     edx, eax
0x18000ad43  and     edx, 3F8000h
0x18000ad49  xor     edx, eax
0x18000ad4b  mov     eax, r8d
0x18000ad4e  lock cmpxchg [rdi], edx
0x18000ad52  jz      short loc_18000AD5C
0x18000ad54  mov     r8d, eax
0x18000ad57  jmp     loc_18000ACC6
0x18000ad5c  not     r8d
0x18000ad5f  mov     dword ptr [r9+10h], 0
0x18000ad67  and     r8d, esi
0x18000ad6a  mov     [r9], r8d
0x18000ad6d  pop     rdi
0x18000ad6e  pop     rsi
0x18000ad6f  pop     rbx
0x18000ad70  retn
```
