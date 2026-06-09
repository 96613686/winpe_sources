# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x1400046b0`
- end: `0x140004786`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000478c`

## callees

- `0x1400046b0`

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
0x1400046b0  push    rbx
0x1400046b2  push    rsi
0x1400046b3  push    rdi
0x1400046b4  mov     r8d, [rcx]
0x1400046b7  lea     r10, [r9+8]
0x1400046bb  xor     edi, edi
0x1400046bd  mov     ebx, edx
0x1400046bf  cmp     edx, 4
0x1400046c2  mov     rsi, rcx
0x1400046c5  setz    dil
0x1400046c9  mov     eax, r8d
0x1400046cc  mov     dword ptr [r9+4], 0
0x1400046d4  or      eax, 1
0x1400046d7  mov     ecx, eax
0x1400046d9  shr     ecx, 0Eh
0x1400046dc  and     ecx, 1
0x1400046df  cmp     ecx, edi
0x1400046e1  jz      short loc_140004725
0x1400046e3  mov     r11d, eax
0x1400046e6  shr     r11d, 5
0x1400046ea  and     r11d, 1FFh
0x1400046f1  jbe     short loc_14000470E
0x1400046f3  mov     ecx, ebx
0x1400046f5  mov     [r9+4], r11d
0x1400046f9  neg     ecx
0x1400046fb  lea     r10, [r9+8]
0x1400046ff  sbb     edx, edx
0x140004701  not     edx
0x140004703  and     edx, 4
0x140004706  mov     [r10], edx
0x140004709  and     eax, 0FFFFC01Fh
0x14000470e  xor     edx, edx
0x140004710  mov     ecx, 4000h
0x140004715  cmp     ebx, 4
0x140004718  cmovz   edx, ecx
0x14000471b  mov     ecx, eax
0x14000471d  btr     ecx, 0Eh
0x140004721  mov     eax, edx
0x140004723  or      eax, ecx
0x140004725  mov     ecx, eax
0x140004727  shr     ecx, 5
0x14000472a  and     ecx, 1FFh
0x140004730  lea     edx, [rcx+1]
0x140004733  cmp     edx, 1FFh
0x140004739  ja      short loc_140004745
0x14000473b  cmp     edx, ecx
0x14000473d  jb      short loc_140004745
0x14000473f  lea     r10, [r9+8]
0x140004743  jmp     short loc_140004751
0x140004745  mov     edx, 1
0x14000474a  mov     [r10], ebx
0x14000474d  mov     [r9+4], ecx
0x140004751  shl     edx, 5
0x140004754  xor     edx, eax
0x140004756  and     edx, 3FE0h
0x14000475c  xor     edx, eax
0x14000475e  mov     eax, r8d
0x140004761  lock cmpxchg [rsi], edx
0x140004765  jz      short loc_14000476F
0x140004767  mov     r8d, eax
0x14000476a  jmp     loc_1400046C9
0x14000476f  not     r8d
0x140004772  mov     dword ptr [r9+10h], 0
0x14000477a  and     r8d, 1
0x14000477e  mov     [r9], r8d
0x140004781  pop     rdi
0x140004782  pop     rsi
0x140004783  pop     rbx
0x140004784  retn
```
