# CMtfPredictionCandidate::CreateCandidatePrimitive(IMtfSuggestionCandidatePrimitive * *)

- ea: `0x180026300`
- end: `0x1800263b4`
- name: `?CreateCandidatePrimitive@CMtfPredictionCandidate@@UEAAJPEAPEAUIMtfSuggestionCandidatePrimitive@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(CMtfPredictionCandidate *__hidden this, struct IMtfSuggestionCandidatePrimitive **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001fc4`
- `0x180026300`

## pseudocode

```c
__int64 __fastcall CMtfPredictionCandidate::CreateCandidatePrimitive(
        CMtfPredictionCandidate *this,
        struct IMtfSuggestionCandidatePrimitive **a2)
{
  __int64 result; // rax
  _QWORD *v4; // rax

  if ( !a2 )
    return 2147500035LL;
  try
  {
    v4 = operator new(0x50u);
    if ( v4 )
    {
      *v4 = &MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionListElement'};
      v4[1] = &MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionCandidatePrimitive'};
      v4[2] = &MtfPrimitiveImpl::`vftable'{for `IMtfPrimitive'};
      v4[3] = &MtfPrimitiveImpl::`vftable'{for `IMtfSerializable'};
      v4[4] = 0;
      v4[5] = 0;
      v4[6] = 0;
      v4[7] = 1;
      v4[8] = 0;
      *((_DWORD *)v4 + 18) = -65536;
      *((_WORD *)v4 + 38) = -1;
      _InterlockedIncrement(&g_cRefDll);
    }
    *a2 = (struct IMtfSuggestionCandidatePrimitive *)((unsigned __int64)(v4 + 1) & -(__int64)(v4 != 0));
    result = 0;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180026300  push    rbx
0x180026302  sub     rsp, 20h
0x180026306  mov     rbx, rdx
0x180026309  test    rdx, rdx
0x18002630c  jnz     short loc_180026318
0x18002630e  mov     eax, 80004003h
0x180026313  jmp     loc_1800263AD
0x180026318  mov     ecx, 50h ; 'P'; Size
0x18002631d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026322  mov     rdx, rax
0x180026325  test    rdx, rdx
0x180026328  jz      short loc_180026394
0x18002632a  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfSuggestionListElement@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionListElement'}
0x180026331  mov     [rdx], rax
0x180026334  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfSuggestionCandidatePrimitive@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionCandidatePrimitive'}
0x18002633b  mov     [rdx+8], rax
0x18002633f  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfPrimitive@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfPrimitive'}
0x180026346  mov     [rdx+10h], rax
0x18002634a  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfSerializable@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfSerializable'}
0x180026351  mov     [rdx+18h], rax
0x180026355  mov     qword ptr [rdx+20h], 0
0x18002635d  mov     qword ptr [rdx+28h], 0
0x180026365  mov     qword ptr [rdx+30h], 0
0x18002636d  mov     qword ptr [rdx+38h], 1
0x180026375  mov     qword ptr [rdx+40h], 0
0x18002637d  mov     dword ptr [rdx+48h], 0FFFF0000h
0x180026384  mov     eax, 0FFFFh
0x180026389  mov     [rdx+4Ch], ax
0x18002638d  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x180026394  lea     rcx, [rdx+8]
0x180026398  neg     rdx
0x18002639b  sbb     rax, rax
0x18002639e  and     rax, rcx
0x1800263a1  mov     [rbx], rax
0x1800263a4  xor     eax, eax
0x1800263a6  jmp     short loc_1800263AD
0x1800263a8  mov     eax, 80004005h
0x1800263ad  add     rsp, 20h
0x1800263b1  pop     rbx
0x1800263b2  retn
```
