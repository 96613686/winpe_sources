# _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)

- ea: `0x180019530`
- end: `0x1800197cb`
- name: `?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z`
- size: `667`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, int, __int64)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180014130`
- `0x18001902c`
- `0x18001b280`
- `0x1800235e0`
- `0x180023d80`
- `0x180055100`
- `0x1801173a0`

## callees

- `0x180019530`
- `0x1800197d4`
- `0x18001cce4`
- `0x18005a8a4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800196b7`
- `ntdll!RtlAllocateHeap` at `0x1800196b7`

## string_xrefs

- `0x1800195fe`: `_SetFileAttributeValue`
- `0x180019710`: `_SetFileAttributeValue`
- `0x18001974c`: `_SetFileAttributeValue`
- `0x1800195f1`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x18001973a`: `Failed to copy attribute value (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _SetFileAttributeValue(const wchar_t *a1, unsigned int a2, int a3, __int64 a4)
{
  __int64 v4; // r12
  const wchar_t *v6; // rbx
  unsigned int v7; // edi
  unsigned int v8; // r13d
  rsize_t v9; // rsi
  __int64 v10; // r14
  unsigned __int64 v11; // rax
  __int64 v12; // r8
  _WORD *v13; // rdx
  const char *v14; // r9
  int v15; // r8d
  wchar_t *Heap; // rcx
  errno_t v18; // eax
  __int64 v19; // rdx

  v4 = a3;
  v6 = a1;
  v7 = -2147024809;
  if ( a4 )
  {
    if ( !a1 )
      return 0;
    v8 = dword_180180864[6 * a3];
    if ( v8 != 4 )
    {
      if ( v8 <= 2 )
      {
        v10 = a4 + 544LL * a3;
        *(_DWORD *)v10 = *(_DWORD *)a1;
      }
      else
      {
        if ( v8 != 3 )
          return v7;
        v10 = a4 + 544LL * a3;
        *(_QWORD *)v10 = *(_QWORD *)a1;
      }
      goto LABEL_14;
    }
    v9 = a2 >> 1;
    if ( (unsigned int)v9 <= 0x103 )
    {
      v10 = a4 + 544LL * a3;
      v11 = (unsigned __int64)a2 >> 1;
      if ( v11 <= 0x7FFFFFFE )
      {
        v12 = 260;
        v13 = (_WORD *)v10;
        while ( v11 && *v6 )
        {
          *v13++ = *v6++;
          --v11;
          if ( !--v12 )
          {
            *(v13 - 1) = 0;
            v7 = -2147024774;
            goto LABEL_11;
          }
        }
        *v13 = 0;
        goto LABEL_14;
      }
      *(_WORD *)v10 = 0;
LABEL_11:
      v14 = "StringCbCopy failed to copy string attribute (index %d) [%x]";
      v15 = 3178;
      goto LABEL_12;
    }
    if ( (unsigned int)v9 > 0x1000 )
    {
      v7 = -2147024774;
      v14 = "Attribute (index %d) was too large. Size was %x bytes";
      v15 = 3132;
LABEL_12:
      AslLogCallPrintf(1, (unsigned int)"_SetFileAttributeValue", v15, (_DWORD)v14);
      return v7;
    }
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v9 + 1));
    v10 = a4 + 544 * v4;
    *(_QWORD *)(v10 + 536) = Heap;
    if ( !Heap )
    {
      v7 = -2147024882;
      AslLogCallPrintf(
        1,
        (unsigned int)"_SetFileAttributeValue",
        3144,
        (unsigned int)"Failed to alloc memory for string value (index %d)");
      return v7;
    }
    v18 = o_wmemcpy_s_0(Heap, (unsigned int)(v9 + 1), v6, v9);
    v7 = v18;
    if ( !v18 )
    {
      *(_WORD *)(*(_QWORD *)(v10 + 536) + 2 * v9) = 0;
      *(_WORD *)v10 = 0;
LABEL_14:
      *(_DWORD *)(v10 + 520) = v4;
      v7 = 0;
      *(_DWORD *)(v10 + 524) = v8;
      *(_DWORD *)(v10 + 528) = 1;
      return v7;
    }
    if ( v18 > 0 )
      v7 = (unsigned __int16)v18 | 0x80070000;
    AslLogCallPrintf(
      1,
      (unsigned int)"_SetFileAttributeValue",
      3156,
      (unsigned int)"Failed to copy attribute value (index %d) [%x]");
    v19 = *(_QWORD *)(v10 + 536);
    if ( v19 )
    {
      AslFree(NtCurrentPeb()->ProcessHeap, v19);
      *(_QWORD *)(v10 + 536) = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180019530  push    rbx
0x180019532  push    rbp
0x180019533  push    rdi
0x180019534  push    r12
0x180019536  sub     rsp, 38h
0x18001953a  movsxd  r12, r8d
0x18001953d  mov     rbp, r9
0x180019540  mov     rbx, rcx
0x180019543  mov     edi, 80070057h
0x180019548  test    r9, r9
0x18001954b  jz      loc_18001964F
0x180019551  mov     [rsp+58h+var_28], r15
0x180019556  xor     r15d, r15d
0x180019559  test    rcx, rcx
0x18001955c  jz      loc_18001978B
0x180019562  mov     [rsp+58h+arg_0], rsi
0x180019567  lea     rax, [r12+r12*2]
0x18001956b  mov     [rsp+58h+arg_8], r13
0x180019570  lea     r13, dword_180180864
0x180019577  mov     r13d, [r13+rax*8+0]
0x18001957c  mov     [rsp+58h+arg_10], r14
0x180019581  mov     r14, r12
0x180019584  cmp     r13d, 4
0x180019588  jnz     loc_18001965B
0x18001958e  mov     esi, edx
0x180019590  shr     esi, 1
0x180019592  cmp     esi, 103h
0x180019598  ja      loc_180019690
0x18001959e  imul    r14, 220h
0x1800195a5  mov     eax, edx
0x1800195a7  add     r14, r9
0x1800195aa  shr     rax, 1
0x1800195ad  cmp     rax, 7FFFFFFEh
0x1800195b3  ja      loc_1800197C2
0x1800195b9  mov     r8d, 104h
0x1800195bf  mov     rdx, r14
0x1800195c2  test    rax, rax
0x1800195c5  jz      short loc_18001961B
0x1800195c7  movzx   ecx, word ptr [rbx]
0x1800195ca  test    cx, cx
0x1800195cd  jz      short loc_180019616
0x1800195cf  mov     [rdx], cx
0x1800195d2  add     rbx, 2
0x1800195d6  add     rdx, 2
0x1800195da  dec     rax
0x1800195dd  sub     r8, 1
0x1800195e1  jnz     short loc_1800195C2
0x1800195e3  mov     [rdx-2], r15w
0x1800195e8  mov     edi, 8007007Ah
0x1800195ed  mov     [rsp+58h+var_30], edi
0x1800195f1  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800195f8  mov     r8d, 0C6Ah
0x1800195fe  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180019605  mov     [rsp+58h+var_38], r12d
0x18001960a  mov     ecx, 1
0x18001960f  call    AslLogCallPrintf
0x180019614  jmp     short loc_18001963B
0x180019616  test    r8, r8
0x180019619  jz      short loc_1800195E3
0x18001961b  mov     [rdx], r15w
0x18001961f  mov     [r14+208h], r12d
0x180019626  mov     edi, r15d
0x180019629  mov     [r14+20Ch], r13d
0x180019630  mov     dword ptr [r14+210h], 1
0x18001963b  mov     r14, [rsp+58h+arg_10]
0x180019640  mov     r13, [rsp+58h+arg_8]
0x180019645  mov     rsi, [rsp+58h+arg_0]
0x18001964a  mov     r15, [rsp+58h+var_28]
0x18001964f  mov     eax, edi
0x180019651  add     rsp, 38h
0x180019655  pop     r12
0x180019657  pop     rdi
0x180019658  pop     rbp
0x180019659  pop     rbx
0x18001965a  retn
0x18001965b  mov     ecx, r13d
0x18001965e  test    r13d, r13d
0x180019661  jz      loc_180019793
0x180019667  sub     ecx, 1
0x18001966a  jz      loc_180019793
0x180019670  sub     ecx, 1
0x180019673  jz      loc_180019793
0x180019679  cmp     ecx, 1
0x18001967c  jnz     short loc_18001963B
0x18001967e  mov     rax, [rbx]
0x180019681  imul    r14, 220h
0x180019688  add     r14, rbp
0x18001968b  mov     [r14], rax
0x18001968e  jmp     short loc_18001961F
0x180019690  cmp     esi, 1000h
0x180019696  ja      loc_1800197A7
0x18001969c  mov     rcx, gs:60h
0x1800196a5  lea     eax, [rsi+1]
0x1800196a8  lea     r8, [rax+rax]; Size
0x1800196ac  mov     edi, eax
0x1800196ae  mov     edx, 8; Flags
0x1800196b3  mov     rcx, [rcx+30h]; HeapHandle
0x1800196b7  call    cs:__imp_RtlAllocateHeap
0x1800196bd  imul    r14, 220h
0x1800196c4  mov     rcx, rax; S1
0x1800196c7  add     r14, rbp
0x1800196ca  mov     [r14+218h], rax
0x1800196d1  test    rax, rax
0x1800196d4  jz      short loc_1800196FE
0x1800196d6  mov     r9, rsi; N
0x1800196d9  mov     r8, rbx; S2
0x1800196dc  mov     edx, edi; N1
0x1800196de  call    _o_wmemcpy_s_0
0x1800196e3  mov     edi, eax
0x1800196e5  test    eax, eax
0x1800196e7  jnz     short loc_18001972B
0x1800196e9  mov     rax, [r14+218h]
0x1800196f0  mov     [rax+rsi*2], r15w
0x1800196f5  mov     [r14], r15w
0x1800196f9  jmp     loc_18001961F
0x1800196fe  lea     r9, aFailedToAllocM_0; "Failed to alloc memory for string value"...
0x180019705  mov     [rsp+58h+var_38], r12d
0x18001970a  mov     r8d, 0C48h
0x180019710  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180019717  mov     ecx, 1
0x18001971c  mov     edi, 8007000Eh
0x180019721  call    AslLogCallPrintf
0x180019726  jmp     loc_18001963B
0x18001972b  jle     short loc_180019736
0x18001972d  movzx   edi, ax
0x180019730  or      edi, 80070000h
0x180019736  mov     [rsp+58h+var_30], edi
0x18001973a  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x180019741  mov     r8d, 0C54h
0x180019747  mov     [rsp+58h+var_38], r12d
0x18001974c  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180019753  mov     ecx, 1
0x180019758  call    AslLogCallPrintf
0x18001975d  mov     rdx, [r14+218h]
0x180019764  test    rdx, rdx
0x180019767  jz      loc_18001963B
0x18001976d  mov     rcx, gs:60h
0x180019776  mov     rcx, [rcx+30h]
0x18001977a  call    AslFree
0x18001977f  mov     [r14+218h], r15
0x180019786  jmp     loc_18001963B
0x18001978b  mov     edi, r15d
0x18001978e  jmp     loc_18001964A
0x180019793  mov     eax, [rbx]
0x180019795  imul    r14, 220h
0x18001979c  add     r14, rbp
0x18001979f  mov     [r14], eax
0x1800197a2  jmp     loc_18001961F
0x1800197a7  mov     edi, 8007007Ah
0x1800197ac  mov     [rsp+58h+var_30], edx
0x1800197b0  lea     r9, aAttributeIndex; "Attribute (index %d) was too large. Siz"...
0x1800197b7  mov     r8d, 0C3Ch
0x1800197bd  jmp     loc_1800195FE
0x1800197c2  mov     [r14], r15w
0x1800197c6  jmp     loc_1800195ED
```
