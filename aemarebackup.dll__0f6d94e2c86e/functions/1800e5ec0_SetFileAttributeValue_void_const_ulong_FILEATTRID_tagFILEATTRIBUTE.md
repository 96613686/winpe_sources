# _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)

- ea: `0x1800e5ec0`
- end: `0x1800e613d`
- name: `?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z`
- size: `637`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, int, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800e2500`
- `0x1800e49c0`
- `0x1800e5dec`

## callees

- `0x1800058fc`
- `0x18004c020`
- `0x1800e5ec0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800e5f9a`
- `ntdll!RtlAllocateHeap` at `0x1800e5f9a`
- `ntdll!RtlFreeHeap` at `0x1800e6049`
- `ntdll!RtlFreeHeap` at `0x1800e6049`

## string_xrefs

- `0x1800e5f64`: `_SetFileAttributeValue`
- `0x1800e5fcb`: `_SetFileAttributeValue`
- `0x1800e6019`: `_SetFileAttributeValue`
- `0x1800e60dd`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800e6007`: `Failed to copy attribute value (index %d) [%x]`

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
  void *v15; // r8
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
  v8 = dword_1801197A4[6 * a3];
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
  v15 = *(void **)(v13 + 536);
  if ( v15 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
    *(_QWORD *)(v13 + 536) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1800e5ec0  push    rbx
0x1800e5ec2  push    rbp
0x1800e5ec3  push    rsi
0x1800e5ec4  push    rdi
0x1800e5ec5  push    r12
0x1800e5ec7  push    r13
0x1800e5ec9  push    r14
0x1800e5ecb  push    r15
0x1800e5ecd  sub     rsp, 38h
0x1800e5ed1  xor     r13d, r13d
0x1800e5ed4  movsxd  r15, r8d
0x1800e5ed7  mov     r14, r9
0x1800e5eda  mov     rsi, rcx
0x1800e5edd  mov     ebx, 80070057h
0x1800e5ee2  test    r9, r9
0x1800e5ee5  jz      loc_1800E612A
0x1800e5eeb  test    rcx, rcx
0x1800e5eee  jz      loc_1800E6127
0x1800e5ef4  lea     rax, [r15+r15*2]
0x1800e5ef8  mov     rdi, r15
0x1800e5efb  lea     r12, dword_1801197A4
0x1800e5f02  mov     r12d, [r12+rax*8]
0x1800e5f06  mov     ecx, r12d
0x1800e5f09  test    r12d, r12d
0x1800e5f0c  jz      loc_1800E6101
0x1800e5f12  sub     ecx, 1
0x1800e5f15  jz      loc_1800E6101
0x1800e5f1b  sub     ecx, 1
0x1800e5f1e  jz      loc_1800E6101
0x1800e5f24  sub     ecx, 1
0x1800e5f27  jz      loc_1800E60EF
0x1800e5f2d  cmp     ecx, 1
0x1800e5f30  jnz     loc_1800E612A
0x1800e5f36  mov     ebp, edx
0x1800e5f38  shr     ebp, 1
0x1800e5f3a  cmp     ebp, 103h
0x1800e5f40  jbe     loc_1800E6070
0x1800e5f46  cmp     ebp, 1000h
0x1800e5f4c  jbe     short loc_1800E5F7F
0x1800e5f4e  mov     ebx, 8007007Ah
0x1800e5f53  mov     [rsp+78h+var_50], edx
0x1800e5f57  lea     r9, aAttributeIndex; "Attribute (index %d) was too large. Siz"...
0x1800e5f5e  mov     r8d, 0C3Ch
0x1800e5f64  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e5f6b  mov     [rsp+78h+var_58], r15d
0x1800e5f70  mov     ecx, 1
0x1800e5f75  call    AslLogCallPrintf
0x1800e5f7a  jmp     loc_1800E612A
0x1800e5f7f  mov     rcx, gs:60h
0x1800e5f88  lea     eax, [rbp+1]
0x1800e5f8b  lea     r8, [rax+rax]; Size
0x1800e5f8f  mov     ebx, eax
0x1800e5f91  mov     edx, 8; Flags
0x1800e5f96  mov     rcx, [rcx+30h]; HeapHandle
0x1800e5f9a  call    cs:__imp_RtlAllocateHeap
0x1800e5fa0  imul    rdi, 220h
0x1800e5fa7  mov     rcx, rax; S1
0x1800e5faa  add     rdi, r14
0x1800e5fad  mov     [rdi+218h], rax
0x1800e5fb4  test    rax, rax
0x1800e5fb7  jnz     short loc_1800E5FE4
0x1800e5fb9  lea     r9, aFailedToAllocM_0; "Failed to alloc memory for string value"...
0x1800e5fc0  mov     [rsp+78h+var_58], r15d
0x1800e5fc5  mov     r8d, 0C48h
0x1800e5fcb  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e5fd2  lea     ecx, [rax+1]
0x1800e5fd5  mov     ebx, 8007000Eh
0x1800e5fda  call    AslLogCallPrintf
0x1800e5fdf  jmp     loc_1800E612A
0x1800e5fe4  mov     r9, rbp; N
0x1800e5fe7  mov     r8, rsi; S2
0x1800e5fea  mov     rdx, rbx; N1
0x1800e5fed  call    _o_wmemcpy_s_0
0x1800e5ff2  mov     ebx, eax
0x1800e5ff4  test    eax, eax
0x1800e5ff6  jz      short loc_1800E605B
0x1800e5ff8  jle     short loc_1800E6003
0x1800e5ffa  movzx   ebx, ax
0x1800e5ffd  or      ebx, 80070000h
0x1800e6003  mov     [rsp+78h+var_50], ebx
0x1800e6007  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x1800e600e  mov     r8d, 0C54h
0x1800e6014  mov     [rsp+78h+var_58], r15d
0x1800e6019  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e6020  mov     ecx, 1
0x1800e6025  call    AslLogCallPrintf
0x1800e602a  mov     r8, [rdi+218h]; P
0x1800e6031  test    r8, r8
0x1800e6034  jz      loc_1800E612A
0x1800e603a  mov     rcx, gs:60h
0x1800e6043  xor     edx, edx; Flags
0x1800e6045  mov     rcx, [rcx+30h]; HeapHandle
0x1800e6049  call    cs:__imp_RtlFreeHeap
0x1800e604f  mov     [rdi+218h], r13
0x1800e6056  jmp     loc_1800E612A
0x1800e605b  mov     rcx, [rdi+218h]
0x1800e6062  mov     [rcx+rbp*2], r13w
0x1800e6067  mov     [rdi], r13w
0x1800e606b  jmp     loc_1800E610F
0x1800e6070  imul    rdi, 220h
0x1800e6077  mov     eax, edx
0x1800e6079  add     rdi, r14
0x1800e607c  shr     rax, 1
0x1800e607f  cmp     rax, 7FFFFFFEh
0x1800e6085  jbe     short loc_1800E608D
0x1800e6087  mov     [rdi], r13w
0x1800e608b  jmp     short loc_1800E60D9
0x1800e608d  mov     edx, 104h
0x1800e6092  mov     r8, rdi
0x1800e6095  test    rax, rax
0x1800e6098  jz      short loc_1800E60B7
0x1800e609a  movzx   ecx, word ptr [rsi]
0x1800e609d  test    cx, cx
0x1800e60a0  jz      short loc_1800E60B7
0x1800e60a2  mov     [r8], cx
0x1800e60a6  add     rsi, 2
0x1800e60aa  add     r8, 2
0x1800e60ae  dec     rax
0x1800e60b1  sub     rdx, 1
0x1800e60b5  jnz     short loc_1800E6095
0x1800e60b7  mov     rax, rdx
0x1800e60ba  mov     ebx, 8007007Ah
0x1800e60bf  neg     rax
0x1800e60c2  sbb     ecx, ecx
0x1800e60c4  not     ecx
0x1800e60c6  and     ebx, ecx
0x1800e60c8  lea     rcx, [r8-2]
0x1800e60cc  test    rdx, rdx
0x1800e60cf  cmovnz  rcx, r8
0x1800e60d3  mov     [rcx], r13w
0x1800e60d7  jnz     short loc_1800E610F
0x1800e60d9  mov     [rsp+78h+var_50], ebx
0x1800e60dd  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800e60e4  mov     r8d, 0C6Ah
0x1800e60ea  jmp     loc_1800E5F64
0x1800e60ef  mov     rax, [rsi]
0x1800e60f2  imul    rdi, 220h
0x1800e60f9  add     rdi, r14
0x1800e60fc  mov     [rdi], rax
0x1800e60ff  jmp     short loc_1800E610F
0x1800e6101  mov     eax, [rsi]
0x1800e6103  imul    rdi, 220h
0x1800e610a  add     rdi, r14
0x1800e610d  mov     [rdi], eax
0x1800e610f  mov     [rdi+208h], r15d
0x1800e6116  mov     [rdi+20Ch], r12d
0x1800e611d  mov     dword ptr [rdi+210h], 1
0x1800e6127  mov     ebx, r13d
0x1800e612a  mov     eax, ebx
0x1800e612c  add     rsp, 38h
0x1800e6130  pop     r15
0x1800e6132  pop     r14
0x1800e6134  pop     r13
0x1800e6136  pop     r12
0x1800e6138  pop     rdi
0x1800e6139  pop     rsi
0x1800e613a  pop     rbp
0x1800e613b  pop     rbx
0x1800e613c  retn
```
