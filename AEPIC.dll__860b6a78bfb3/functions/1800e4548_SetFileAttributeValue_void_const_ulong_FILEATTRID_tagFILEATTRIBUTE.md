# _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)

- ea: `0x1800e4548`
- end: `0x1800e47c2`
- name: `?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z`
- size: `634`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, int, __int64)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800e2b80`
- `0x1800e3330`
- `0x1800e34b0`
- `0x1800e37c0`
- `0x1800e3910`
- `0x1800e3b70`
- `0x1800e4474`

## callees

- `0x180006908`
- `0x1800295dc`
- `0x18002979c`
- `0x1800e4548`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800e4622`
- `ntdll!RtlAllocateHeap` at `0x1800e4622`

## string_xrefs

- `0x1800e45ec`: `_SetFileAttributeValue`
- `0x1800e4653`: `_SetFileAttributeValue`
- `0x1800e46a1`: `_SetFileAttributeValue`
- `0x1800e468f`: `Failed to copy attribute value (index %d) [%x]`
- `0x1800e4762`: `StringCbCopy failed to copy string attribute (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _SetFileAttributeValue(const wchar_t *a1, unsigned int a2, int a3, __int64 a4)
{
  __int64 v4; // r15
  const wchar_t *v6; // rsi
  unsigned int v7; // ebx
  unsigned int v8; // r12d
  rsize_t v9; // rbp
  const char *v10; // r9
  __int64 v11; // r8
  wchar_t *Heap; // rcx
  __int64 v13; // rdi
  errno_t v14; // eax
  __int64 v15; // rdx
  unsigned __int64 v16; // rax
  __int64 v17; // rdx
  _WORD *v18; // r8
  _WORD *v19; // rcx
  unsigned int v21; // [rsp+28h] [rbp-50h]

  v4 = a3;
  v6 = a1;
  v7 = -2147024809;
  if ( !a4 )
    return v7;
  if ( !a1 )
    return 0;
  v8 = dword_180120344[6 * a3];
  if ( v8 <= 2 )
  {
    v13 = a4 + 544LL * a3;
    *(_DWORD *)v13 = *(_DWORD *)a1;
    goto LABEL_30;
  }
  if ( v8 == 3 )
  {
    v13 = a4 + 544LL * a3;
    *(_QWORD *)v13 = *(_QWORD *)a1;
    goto LABEL_30;
  }
  if ( v8 != 4 )
    return v7;
  v9 = a2 >> 1;
  if ( (unsigned int)v9 <= 0x103 )
  {
    v13 = a4 + 544LL * a3;
    v16 = (unsigned __int64)a2 >> 1;
    if ( v16 <= 0x7FFFFFFE )
    {
      v17 = 260;
      v18 = (_WORD *)(a4 + 544LL * a3);
      do
      {
        if ( !v16 )
          break;
        if ( !*v6 )
          break;
        *v18++ = *v6++;
        --v16;
        --v17;
      }
      while ( v17 );
      v7 = v17 == 0 ? 0x8007007A : 0;
      v19 = v18 - 1;
      if ( v17 )
        v19 = v18;
      *v19 = 0;
      if ( v17 )
        goto LABEL_30;
    }
    else
    {
      *(_WORD *)v13 = 0;
    }
    v21 = v7;
    v10 = "StringCbCopy failed to copy string attribute (index %d) [%x]";
    v11 = 3178;
    goto LABEL_9;
  }
  if ( (unsigned int)v9 > 0x1000 )
  {
    v7 = -2147024774;
    v21 = a2;
    v10 = "Attribute (index %d) was too large. Size was %x bytes";
    v11 = 3132;
LABEL_9:
    AslLogCallPrintf(1, "_SetFileAttributeValue", v11, v10, v4, v21);
    return v7;
  }
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v9 + 1));
  v13 = a4 + 544 * v4;
  *(_QWORD *)(v13 + 536) = Heap;
  if ( !Heap )
  {
    v7 = -2147024882;
    AslLogCallPrintf(1, "_SetFileAttributeValue", 3144, "Failed to alloc memory for string value (index %d)", v4);
    return v7;
  }
  v14 = o_wmemcpy_s_0(Heap, (unsigned int)(v9 + 1), v6, v9);
  v7 = v14;
  if ( !v14 )
  {
    *(_WORD *)(*(_QWORD *)(v13 + 536) + 2 * v9) = 0;
    *(_WORD *)v13 = 0;
LABEL_30:
    *(_DWORD *)(v13 + 520) = v4;
    *(_DWORD *)(v13 + 524) = v8;
    *(_DWORD *)(v13 + 528) = 1;
    return 0;
  }
  if ( v14 > 0 )
    v7 = (unsigned __int16)v14 | 0x80070000;
  AslLogCallPrintf(1, "_SetFileAttributeValue", 3156, "Failed to copy attribute value (index %d) [%x]", v4, v7);
  v15 = *(_QWORD *)(v13 + 536);
  if ( v15 )
  {
    AslFree(NtCurrentPeb()->ProcessHeap, v15);
    *(_QWORD *)(v13 + 536) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1800e4548  push    rbx
0x1800e454a  push    rbp
0x1800e454b  push    rsi
0x1800e454c  push    rdi
0x1800e454d  push    r12
0x1800e454f  push    r13
0x1800e4551  push    r14
0x1800e4553  push    r15
0x1800e4555  sub     rsp, 38h
0x1800e4559  xor     r13d, r13d
0x1800e455c  movsxd  r15, r8d
0x1800e455f  mov     r14, r9
0x1800e4562  mov     rsi, rcx
0x1800e4565  mov     ebx, 80070057h
0x1800e456a  test    r9, r9
0x1800e456d  jz      loc_1800E47AF
0x1800e4573  test    rcx, rcx
0x1800e4576  jz      loc_1800E47AC
0x1800e457c  lea     rax, [r15+r15*2]
0x1800e4580  mov     rdi, r15
0x1800e4583  lea     r12, dword_180120344
0x1800e458a  mov     r12d, [r12+rax*8]
0x1800e458e  mov     ecx, r12d
0x1800e4591  test    r12d, r12d
0x1800e4594  jz      loc_1800E4786
0x1800e459a  sub     ecx, 1
0x1800e459d  jz      loc_1800E4786
0x1800e45a3  sub     ecx, 1
0x1800e45a6  jz      loc_1800E4786
0x1800e45ac  sub     ecx, 1
0x1800e45af  jz      loc_1800E4774
0x1800e45b5  cmp     ecx, 1
0x1800e45b8  jnz     loc_1800E47AF
0x1800e45be  mov     ebp, edx
0x1800e45c0  shr     ebp, 1
0x1800e45c2  cmp     ebp, 103h
0x1800e45c8  jbe     loc_1800E46F5
0x1800e45ce  cmp     ebp, 1000h
0x1800e45d4  jbe     short loc_1800E4607
0x1800e45d6  mov     ebx, 8007007Ah
0x1800e45db  mov     [rsp+78h+var_50], edx
0x1800e45df  lea     r9, aAttributeIndex; "Attribute (index %d) was too large. Siz"...
0x1800e45e6  mov     r8d, 0C3Ch
0x1800e45ec  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e45f3  mov     [rsp+78h+var_58], r15d
0x1800e45f8  mov     ecx, 1
0x1800e45fd  call    AslLogCallPrintf
0x1800e4602  jmp     loc_1800E47AF
0x1800e4607  mov     rcx, gs:60h
0x1800e4610  lea     eax, [rbp+1]
0x1800e4613  lea     r8, [rax+rax]; Size
0x1800e4617  mov     ebx, eax
0x1800e4619  mov     edx, 8; Flags
0x1800e461e  mov     rcx, [rcx+30h]; HeapHandle
0x1800e4622  call    cs:__imp_RtlAllocateHeap
0x1800e4628  imul    rdi, 220h
0x1800e462f  mov     rcx, rax; S1
0x1800e4632  add     rdi, r14
0x1800e4635  mov     [rdi+218h], rax
0x1800e463c  test    rax, rax
0x1800e463f  jnz     short loc_1800E466C
0x1800e4641  lea     r9, aFailedToAllocM_0; "Failed to alloc memory for string value"...
0x1800e4648  mov     [rsp+78h+var_58], r15d
0x1800e464d  mov     r8d, 0C48h
0x1800e4653  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e465a  lea     ecx, [rax+1]
0x1800e465d  mov     ebx, 8007000Eh
0x1800e4662  call    AslLogCallPrintf
0x1800e4667  jmp     loc_1800E47AF
0x1800e466c  mov     r9, rbp; N
0x1800e466f  mov     r8, rsi; S2
0x1800e4672  mov     rdx, rbx; N1
0x1800e4675  call    _o_wmemcpy_s_0
0x1800e467a  mov     ebx, eax
0x1800e467c  test    eax, eax
0x1800e467e  jz      short loc_1800E46E0
0x1800e4680  jle     short loc_1800E468B
0x1800e4682  movzx   ebx, ax
0x1800e4685  or      ebx, 80070000h
0x1800e468b  mov     [rsp+78h+var_50], ebx
0x1800e468f  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x1800e4696  mov     r8d, 0C54h
0x1800e469c  mov     [rsp+78h+var_58], r15d
0x1800e46a1  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e46a8  mov     ecx, 1
0x1800e46ad  call    AslLogCallPrintf
0x1800e46b2  mov     rdx, [rdi+218h]
0x1800e46b9  test    rdx, rdx
0x1800e46bc  jz      loc_1800E47AF
0x1800e46c2  mov     rcx, gs:60h
0x1800e46cb  mov     rcx, [rcx+30h]
0x1800e46cf  call    AslFree
0x1800e46d4  mov     [rdi+218h], r13
0x1800e46db  jmp     loc_1800E47AF
0x1800e46e0  mov     rcx, [rdi+218h]
0x1800e46e7  mov     [rcx+rbp*2], r13w
0x1800e46ec  mov     [rdi], r13w
0x1800e46f0  jmp     loc_1800E4794
0x1800e46f5  imul    rdi, 220h
0x1800e46fc  mov     eax, edx
0x1800e46fe  add     rdi, r14
0x1800e4701  shr     rax, 1
0x1800e4704  cmp     rax, 7FFFFFFEh
0x1800e470a  jbe     short loc_1800E4712
0x1800e470c  mov     [rdi], r13w
0x1800e4710  jmp     short loc_1800E475E
0x1800e4712  mov     edx, 104h
0x1800e4717  mov     r8, rdi
0x1800e471a  test    rax, rax
0x1800e471d  jz      short loc_1800E473C
0x1800e471f  movzx   ecx, word ptr [rsi]
0x1800e4722  test    cx, cx
0x1800e4725  jz      short loc_1800E473C
0x1800e4727  mov     [r8], cx
0x1800e472b  add     rsi, 2
0x1800e472f  add     r8, 2
0x1800e4733  dec     rax
0x1800e4736  sub     rdx, 1
0x1800e473a  jnz     short loc_1800E471A
0x1800e473c  mov     rax, rdx
0x1800e473f  mov     ebx, 8007007Ah
0x1800e4744  neg     rax
0x1800e4747  sbb     ecx, ecx
0x1800e4749  not     ecx
0x1800e474b  and     ebx, ecx
0x1800e474d  lea     rcx, [r8-2]
0x1800e4751  test    rdx, rdx
0x1800e4754  cmovnz  rcx, r8
0x1800e4758  mov     [rcx], r13w
0x1800e475c  jnz     short loc_1800E4794
0x1800e475e  mov     [rsp+78h+var_50], ebx
0x1800e4762  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800e4769  mov     r8d, 0C6Ah
0x1800e476f  jmp     loc_1800E45EC
0x1800e4774  mov     rax, [rsi]
0x1800e4777  imul    rdi, 220h
0x1800e477e  add     rdi, r14
0x1800e4781  mov     [rdi], rax
0x1800e4784  jmp     short loc_1800E4794
0x1800e4786  mov     eax, [rsi]
0x1800e4788  imul    rdi, 220h
0x1800e478f  add     rdi, r14
0x1800e4792  mov     [rdi], eax
0x1800e4794  mov     [rdi+208h], r15d
0x1800e479b  mov     [rdi+20Ch], r12d
0x1800e47a2  mov     dword ptr [rdi+210h], 1
0x1800e47ac  mov     ebx, r13d
0x1800e47af  mov     eax, ebx
0x1800e47b1  add     rsp, 38h
0x1800e47b5  pop     r15
0x1800e47b7  pop     r14
0x1800e47b9  pop     r13
0x1800e47bb  pop     r12
0x1800e47bd  pop     rdi
0x1800e47be  pop     rsi
0x1800e47bf  pop     rbp
0x1800e47c0  pop     rbx
0x1800e47c1  retn
```
