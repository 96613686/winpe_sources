# ConvertLegacyDhPrivateBlob

- ea: `0x1800180d8`
- end: `0x18001826a`
- name: `ConvertLegacyDhPrivateBlob`
- size: `402`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008890`

## callees

- `0x180005060`
- `0x18000e0c0`
- `0x1800180d8`
- `0x18001b3c4`
- `0x18001b7a9`

## string_xrefs

- `0x180018245`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertLegacyDhPrivateBlob(__int64 *a1, __int64 a2, _DWORD *a3, unsigned int a4, unsigned int *a5)
{
  size_t v5; // r12
  unsigned int v8; // ebx
  unsigned int v9; // r11d
  __int64 v10; // r9
  unsigned int v11; // ebp
  unsigned int v12; // ecx
  int v13; // ebx
  int v14; // edi
  int v15; // esi
  __int64 v16; // rcx
  __int64 v17; // r9
  __int64 v18; // r11
  __int64 v19; // r9
  __int64 v20; // r11
  __int64 v21; // r10
  __int64 v22; // rcx
  __int64 v24; // [rsp+88h] [rbp+30h]

  v5 = a4;
  v8 = VerifyLegacyDhPrivateBlob();
  if ( v8 )
  {
    v10 = 2257;
LABEL_17:
    v22 = v8;
    goto LABEL_18;
  }
  if ( !a1 || v9 < 0x34 )
  {
    v10 = 2265;
    v8 = -2146893785;
    goto LABEL_17;
  }
  v24 = *a1;
  if ( (unsigned __int8)*a1 != 7 )
  {
    v10 = 2279;
LABEL_15:
    v22 = 2148073475LL;
    v8 = -2146893821;
LABEL_18:
    DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c", v10);
    return v8;
  }
  if ( BYTE1(v24) != 3 || (unsigned int)(HIDWORD(v24) - 43521) > 1 )
  {
    v10 = 2287;
    goto LABEL_15;
  }
  v11 = *((_DWORD *)a1 + 3) >> 3;
  v12 = 4 * v11 + 8;
  *a5 = v12;
  if ( a3 )
  {
    if ( (unsigned int)v5 < v12 )
      return (unsigned int)-2146893784;
    v13 = *((_DWORD *)a1 + 4);
    v14 = *((_DWORD *)a1 + 5);
    v15 = *((_DWORD *)a1 + 6);
    memset_0(a3, 0, v5);
    *a3 = 1448101956;
    a3[1] = v11;
    ReverseMemCopy(a3 + 2, (char *)a1 + 52, v11);
    ReverseMemCopy(
      (unsigned int)a3[1] + v16,
      (unsigned int)a3[1] + ((unsigned __int64)(unsigned int)(v13 + 7) >> 3) + v17,
      (unsigned int)a3[1]);
    ReverseMemCopy((unsigned int)a3[1] + v18, v19 + a3[1] + ((unsigned int)(v14 + 7) >> 3), (unsigned int)a3[1]);
    ReverseMemCopy(
      (unsigned int)a3[1] + v20 + a3[1] - ((unsigned int)(v15 + 7) >> 3),
      v21 + (unsigned int)a3[1],
      (unsigned int)(v15 + 7) >> 3);
  }
  return 0;
}

```

## disassembly

```asm
0x1800180d8  push    rbx
0x1800180da  push    rbp
0x1800180db  push    rsi
0x1800180dc  push    rdi
0x1800180dd  push    r12
0x1800180df  push    r14
0x1800180e1  push    r15
0x1800180e3  sub     rsp, 20h
0x1800180e7  mov     r12d, r9d
0x1800180ea  mov     r15, r8
0x1800180ed  mov     r11d, edx
0x1800180f0  mov     r14, rcx
0x1800180f3  call    VerifyLegacyDhPrivateBlob
0x1800180f8  mov     ebx, eax
0x1800180fa  test    eax, eax
0x1800180fc  jz      short loc_180018109
0x1800180fe  mov     r9d, 8D1h
0x180018104  jmp     loc_180018243
0x180018109  test    r14, r14
0x18001810c  jz      loc_180018238
0x180018112  cmp     r11d, 34h ; '4'
0x180018116  jb      loc_180018238
0x18001811c  mov     rax, [r14]
0x18001811f  mov     [rsp+58h+arg_28], rax
0x180018127  cmp     al, 7
0x180018129  jz      short loc_180018136
0x18001812b  mov     r9d, 8E7h
0x180018131  jmp     loc_18001822F
0x180018136  cmp     byte ptr [rsp+58h+arg_28+1], 3
0x18001813e  jnz     loc_180018229
0x180018144  mov     eax, dword ptr [rsp+58h+arg_28+4]
0x18001814b  add     eax, 0FFFF55FFh
0x180018150  cmp     eax, 1
0x180018153  ja      loc_180018229
0x180018159  mov     ebp, [r14+0Ch]
0x18001815d  mov     rax, [rsp+58h+arg_20]
0x180018165  shr     ebp, 3
0x180018168  lea     ecx, ds:8[rbp*4]
0x18001816f  mov     [rax], ecx
0x180018171  test    r15, r15
0x180018174  jnz     short loc_18001817D
0x180018176  xor     ebx, ebx
0x180018178  jmp     loc_180018258
0x18001817d  cmp     r12d, ecx
0x180018180  jnb     short loc_18001818C
0x180018182  mov     ebx, 80090028h
0x180018187  jmp     loc_180018258
0x18001818c  mov     ebx, [r14+10h]
0x180018190  mov     r8, r12; Size
0x180018193  mov     edi, [r14+14h]
0x180018197  xor     edx, edx; Val
0x180018199  mov     esi, [r14+18h]
0x18001819d  mov     rcx, r15; void *
0x1800181a0  call    memset_0
0x1800181a5  lea     r9, [r14+34h]
0x1800181a9  mov     dword ptr [r15], 56504844h
0x1800181b0  mov     rdx, r9
0x1800181b3  mov     [r15+4], ebp
0x1800181b7  lea     rcx, [r15+8]
0x1800181bb  mov     r8d, ebp
0x1800181be  call    ReverseMemCopy
0x1800181c3  mov     r8d, [r15+4]
0x1800181c7  lea     r11, [r8+rcx]
0x1800181cb  lea     ecx, [rbx+7]
0x1800181ce  shr     rcx, 3
0x1800181d2  add     rcx, r8
0x1800181d5  add     r9, rcx
0x1800181d8  mov     rcx, r11
0x1800181db  mov     rdx, r9
0x1800181de  call    ReverseMemCopy
0x1800181e3  mov     r8d, [r15+4]
0x1800181e7  lea     r10d, [rdi+7]
0x1800181eb  shr     r10d, 3
0x1800181ef  add     r11, r8
0x1800181f2  add     r10d, r8d
0x1800181f5  mov     rcx, r11
0x1800181f8  add     r10, r9
0x1800181fb  mov     rdx, r10
0x1800181fe  call    ReverseMemCopy
0x180018203  mov     r9d, [r15+4]
0x180018207  lea     r8d, [rsi+7]
0x18001820b  shr     r8d, 3
0x18001820f  mov     ecx, r9d
0x180018212  sub     ecx, r8d
0x180018215  add     rcx, r11
0x180018218  add     rcx, r9
0x18001821b  lea     rdx, [r10+r9]
0x18001821f  call    ReverseMemCopy
0x180018224  jmp     loc_180018176
0x180018229  mov     r9d, 8EFh
0x18001822f  mov     ecx, 80090003h
0x180018234  mov     ebx, ecx
0x180018236  jmp     short loc_180018245
0x180018238  mov     r9d, 8D9h
0x18001823e  mov     ebx, 80090027h
0x180018243  mov     ecx, ebx
0x180018245  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001824c  lea     rdx, aStatus; "Status"
0x180018253  call    DebugTraceError
0x180018258  mov     eax, ebx
0x18001825a  add     rsp, 20h
0x18001825e  pop     r15
0x180018260  pop     r14
0x180018262  pop     r12
0x180018264  pop     rdi
0x180018265  pop     rsi
0x180018266  pop     rbp
0x180018267  pop     rbx
0x180018268  retn
```
