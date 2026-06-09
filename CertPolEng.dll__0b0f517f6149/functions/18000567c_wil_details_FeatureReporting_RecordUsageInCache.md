# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000567c`
- end: `0x1800058cd`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `593`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005500`

## callees

- `0x18000567c`
- `0x180018b8c`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v3; // r10d
  int v6; // r8d
  unsigned __int32 v7; // eax
  BOOL v8; // edx
  unsigned __int32 v9; // ett
  int v10; // ecx
  signed __int32 i; // edx
  signed __int32 v12; // r9d
  signed __int32 v13; // eax
  signed __int32 v14; // edx
  BOOL v15; // esi
  unsigned int v16; // eax
  int v17; // r9d
  unsigned int v18; // r8d
  unsigned int v19; // r9d
  signed __int32 v20; // eax

  v3 = a3;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  if ( (_DWORD)a3 )
  {
    if ( (_DWORD)a3 == 1 )
      goto LABEL_31;
    if ( (_DWORD)a3 == 2 || (_DWORD)a3 == 3 )
    {
LABEL_17:
      v10 = 0;
      switch ( (_DWORD)a3 )
      {
        case 2:
          v10 = 2;
          break;
        case 3:
          v10 = 8;
          break;
        case 6:
          v10 = 4;
          break;
        case 7:
          v10 = 16;
          break;
      }
      for ( i = *a2; ; i = v13 )
      {
        v12 = i | v10 | 1;
        *(_DWORD *)(a1 + 16) = (i | v10) == i;
        if ( (i | v10) == i )
          v12 = i | v10;
        v13 = _InterlockedCompareExchange(a2, v12, i);
        if ( i == v13 )
          break;
      }
      *(_DWORD *)a1 = (v12 & 1) != 0 && (i & 1) == 0;
      return a1;
    }
    if ( (_DWORD)a3 != 4 )
    {
      if ( (_DWORD)a3 != 5 )
      {
        if ( (unsigned int)(a3 - 6) >= 2 )
        {
          v6 = a3 - 320;
          if ( v6 >= 64 )
            goto LABEL_16;
          v7 = *((_DWORD *)a2 + 1);
          do
          {
            v8 = (v7 & 0x10) != 0 && ((v7 >> 5) & 0x3F) == v6;
            *(_DWORD *)(a1 + 16) = v8;
            v9 = v7;
            v7 = _InterlockedCompareExchange(
                   a2 + 1,
                   v7 ^ ((unsigned __int16)v7 ^ (unsigned __int16)(32 * v6)) & 0x7E0 | 0x10,
                   v7);
          }
          while ( v9 != v7 );
          if ( !*(_DWORD *)(a1 + 16) )
          {
LABEL_16:
            *(_DWORD *)(a1 + 8) = v3;
            *(_DWORD *)(a1 + 4) = 1;
            *(_DWORD *)(a1 + 12) = 0;
          }
          return a1;
        }
        goto LABEL_17;
      }
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3, a3, (_DWORD *)a1);
      return a1;
    }
  }
  v14 = *a2;
  v15 = a3 == 4;
  while ( 1 )
  {
    *(_DWORD *)(a1 + 4) = 0;
    v16 = v14 | 1;
    if ( (((v14 | 1u) >> 14) & 1) != v15 )
    {
      if ( ((v16 >> 5) & 0x1FF) != 0 )
      {
        *(_DWORD *)(a1 + 4) = (v16 >> 5) & 0x1FF;
        *(_DWORD *)(a1 + 8) = v3 == 0 ? 4 : 0;
        v16 = v14 & 0xFFFFC01E | 1;
      }
      v17 = 0;
      if ( v3 == 4 )
        v17 = 0x4000;
      v16 = v16 & 0xFFFFBFFF | v17;
    }
    v18 = (v16 >> 5) & 0x1FF;
    v19 = v18 + 1;
    if ( v18 + 1 > 0x1FF || v19 < v18 )
    {
      LOWORD(v19) = 1;
      *(_DWORD *)(a1 + 8) = v3;
      *(_DWORD *)(a1 + 4) = v18;
    }
    v20 = _InterlockedCompareExchange(a2, v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)(32 * v19)) & 0x3FE0, v14);
    if ( v14 == v20 )
      break;
    v14 = v20;
  }
  *(_DWORD *)(a1 + 16) = 0;
  *(_DWORD *)a1 = (v14 & 1) == 0;
  return a1;
}

```

## disassembly

```asm
0x18000567c  mov     [rsp+arg_0], rbx
0x180005681  mov     [rsp+arg_8], rsi
0x180005686  push    rdi
0x180005687  sub     rsp, 20h
0x18000568b  xor     eax, eax
0x18000568d  xorps   xmm0, xmm0
0x180005690  mov     r10d, r8d
0x180005693  mov     r11, rdx
0x180005696  mov     rbx, rcx
0x180005699  mov     r9d, r8d
0x18000569c  movups  xmmword ptr [rcx], xmm0
0x18000569f  mov     [rcx+10h], rax
0x1800056a3  test    r8d, r8d
0x1800056a6  jz      loc_1800057ED
0x1800056ac  sub     r9d, 1
0x1800056b0  jz      loc_1800057DA
0x1800056b6  sub     r9d, 1
0x1800056ba  jz      loc_18000575B
0x1800056c0  sub     r9d, 1
0x1800056c4  jz      loc_18000575B
0x1800056ca  sub     r9d, 1
0x1800056ce  jz      loc_1800057ED
0x1800056d4  sub     r9d, 1
0x1800056d8  jz      loc_1800057DA
0x1800056de  sub     r9d, 1
0x1800056e2  jz      short loc_18000575B
0x1800056e4  cmp     r9d, 1
0x1800056e8  jz      short loc_18000575B
0x1800056ea  add     r8d, 0FFFFFEC0h
0x1800056f1  cmp     r8d, 40h ; '@'
0x1800056f5  jge     short loc_180005744
0x1800056f7  mov     eax, [rdx+4]
0x1800056fa  mov     r9d, r8d
0x1800056fd  shl     r9d, 5
0x180005701  mov     ecx, 10h
0x180005706  test    cl, al
0x180005708  jz      short loc_18000571E
0x18000570a  mov     edx, eax
0x18000570c  shr     edx, 5
0x18000570f  and     edx, 3Fh
0x180005712  cmp     edx, r8d
0x180005715  jnz     short loc_18000571E
0x180005717  mov     edx, 1
0x18000571c  jmp     short loc_180005720
0x18000571e  xor     edx, edx
0x180005720  mov     [rbx+10h], edx
0x180005723  mov     edx, r9d
0x180005726  xor     edx, eax
0x180005728  and     edx, 7E0h
0x18000572e  xor     edx, eax
0x180005730  or      edx, ecx
0x180005732  lock cmpxchg [r11+4], edx
0x180005738  jnz     short loc_180005706
0x18000573a  cmp     dword ptr [rbx+10h], 0
0x18000573e  jnz     loc_1800058BA
0x180005744  mov     [rbx+8], r10d
0x180005748  mov     dword ptr [rbx+4], 1
0x18000574f  mov     dword ptr [rbx+0Ch], 0
0x180005756  jmp     loc_1800058BA
0x18000575b  xor     ecx, ecx
0x18000575d  sub     r10d, 2
0x180005761  jz      short loc_180005789
0x180005763  sub     r10d, 1
0x180005767  jz      short loc_180005782
0x180005769  sub     r10d, 3
0x18000576d  jz      short loc_18000577B
0x18000576f  cmp     r10d, 1
0x180005773  jnz     short loc_18000578E
0x180005775  lea     ecx, [r10+0Fh]
0x180005779  jmp     short loc_18000578E
0x18000577b  mov     ecx, 4
0x180005780  jmp     short loc_18000578E
0x180005782  mov     ecx, 8
0x180005787  jmp     short loc_18000578E
0x180005789  mov     ecx, 2
0x18000578e  mov     edx, [rdx]
0x180005790  xor     eax, eax
0x180005792  mov     r8d, ecx
0x180005795  or      r8d, edx
0x180005798  cmp     r8d, edx
0x18000579b  mov     r9d, r8d
0x18000579e  setz    al
0x1800057a1  or      r9d, 1
0x1800057a5  cmp     r8d, edx
0x1800057a8  mov     [rbx+10h], eax
0x1800057ab  mov     eax, edx
0x1800057ad  cmovz   r9d, r8d
0x1800057b1  lock cmpxchg [r11], r9d
0x1800057b6  jz      short loc_1800057BC
0x1800057b8  mov     edx, eax
0x1800057ba  jmp     short loc_180005790
0x1800057bc  test    r9b, 1
0x1800057c0  setnz   cl
0x1800057c3  test    dl, 1
0x1800057c6  setz    al
0x1800057c9  test    al, cl
0x1800057cb  mov     eax, 0
0x1800057d0  setnz   al
0x1800057d3  mov     [rbx], eax
0x1800057d5  jmp     loc_1800058BA
0x1800057da  mov     r9, rbx
0x1800057dd  mov     edx, r10d
0x1800057e0  mov     rcx, r11
0x1800057e3  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1800057e8  jmp     loc_1800058BA
0x1800057ed  mov     edx, [rdx]
0x1800057ef  xor     esi, esi
0x1800057f1  lea     ecx, [rsi+4]
0x1800057f4  cmp     r10d, ecx
0x1800057f7  setz    sil
0x1800057fb  mov     eax, edx
0x1800057fd  mov     dword ptr [rbx+4], 0
0x180005804  or      eax, 1
0x180005807  mov     r8d, eax
0x18000580a  shr     r8d, 0Eh
0x18000580e  and     r8d, 1
0x180005812  cmp     r8d, esi
0x180005815  jz      short loc_18000585D
0x180005817  mov     edi, eax
0x180005819  shr     edi, 5
0x18000581c  and     edi, 1FFh
0x180005822  jbe     short loc_18000583F
0x180005824  mov     r8d, r10d
0x180005827  mov     [rbx+4], edi
0x18000582a  neg     r8d
0x18000582d  sbb     r9d, r9d
0x180005830  not     r9d
0x180005833  and     r9d, ecx
0x180005836  mov     [rbx+8], r9d
0x18000583a  and     eax, 0FFFFC01Fh
0x18000583f  xor     r9d, r9d
0x180005842  mov     r8d, 4000h
0x180005848  cmp     r10d, ecx
0x18000584b  cmovz   r9d, r8d
0x18000584f  mov     r8d, eax
0x180005852  btr     r8d, 0Eh
0x180005857  mov     eax, r9d
0x18000585a  or      eax, r8d
0x18000585d  mov     r8d, eax
0x180005860  shr     r8d, 5
0x180005864  and     r8d, 1FFh
0x18000586b  lea     r9d, [r8+1]
0x18000586f  cmp     r9d, 1FFh
0x180005876  ja      short loc_18000587D
0x180005878  cmp     r9d, r8d
0x18000587b  jnb     short loc_18000588B
0x18000587d  mov     r9d, 1
0x180005883  mov     [rbx+8], r10d
0x180005887  mov     [rbx+4], r8d
0x18000588b  shl     r9d, 5
0x18000588f  xor     r9d, eax
0x180005892  and     r9d, 3FE0h
0x180005899  xor     r9d, eax
0x18000589c  mov     eax, edx
0x18000589e  lock cmpxchg [r11], r9d
0x1800058a3  jz      short loc_1800058AC
0x1800058a5  mov     edx, eax
0x1800058a7  jmp     loc_1800057FB
0x1800058ac  not     edx
0x1800058ae  mov     dword ptr [rbx+10h], 0
0x1800058b5  and     edx, 1
0x1800058b8  mov     [rbx], edx
0x1800058ba  mov     rsi, [rsp+28h+arg_8]
0x1800058bf  mov     rax, rbx
0x1800058c2  mov     rbx, [rsp+28h+arg_0]
0x1800058c7  add     rsp, 20h
0x1800058cb  pop     rdi
0x1800058cc  retn
```
