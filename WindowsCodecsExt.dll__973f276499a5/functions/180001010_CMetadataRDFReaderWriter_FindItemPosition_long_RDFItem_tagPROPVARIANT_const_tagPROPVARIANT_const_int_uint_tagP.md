# CMetadataRDFReaderWriter::FindItemPosition(long (*)(RDFItem *,tagPROPVARIANT const *,tagPROPVARIANT const *,int *),uint,tagPROPVARIANT const *,tagPROPVARIANT const *,int *,uint *)

- ea: `0x180001010`
- end: `0x180001139`
- name: `?FindItemPosition@CMetadataRDFReaderWriter@@IEAAJP6AJPEAVRDFItem@@PEBUtagPROPVARIANT@@1PEAH@ZI112PEAI@Z`
- size: `297`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, int (*)(struct RDFItem *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, int *), unsigned int, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, int *, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000285c`
- `0x18001e950`
- `0x18001ea50`
- `0x1800214e0`

## callees

- `0x180001010`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::FindItemPosition(
        CMetadataRDFReaderWriter *this,
        __int64 (__fastcall *a2)(__int64, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, unsigned int **),
        int a3,
        const struct tagPROPVARIANT *a4,
        const struct tagPROPVARIANT *a5,
        int *a6,
        unsigned int *a7)
{
  __int64 v7; // rbx
  unsigned int *v8; // r13
  unsigned int v10; // ebp
  int v11; // r9d
  int v13; // r8d
  unsigned int v15; // edi
  int v16; // edx
  __int64 v17; // rcx
  __int64 result; // rax
  int v19; // [rsp+70h] [rbp+8h]

  v7 = 0;
  v8 = a7;
  v10 = *((_DWORD *)this + 58);
  v11 = a3;
  v13 = g_doStackCaptures;
  *a6 = 0;
  v15 = 0;
  *v8 = 0;
  v16 = 0;
  v19 = 0;
  while ( (unsigned int)v7 < v10 )
  {
    v17 = *(_QWORD *)(*((_QWORD *)this + 26) + 8 * v7);
    if ( (*(_BYTE *)(v17 + 8) & 2) == 0 )
    {
      if ( !a2 )
        goto LABEL_15;
      LODWORD(a7) = 1;
      result = a2(v17, a4, a5, &a7);
      v13 = g_doStackCaptures;
      v15 = result;
      if ( (int)result < 0 && g_doStackCaptures )
        goto LABEL_10;
      if ( (int)result < 0 )
        return result;
      v16 = v19;
      v11 = a3;
      if ( (_DWORD)a7 )
      {
LABEL_15:
        if ( v11 == v16 )
        {
          *v8 = v7;
          return v15;
        }
        v19 = ++v16;
      }
    }
    v7 = (unsigned int)(v7 + 1);
  }
  *v8 = v7;
  if ( v11 == v16 )
  {
    *a6 = 1;
  }
  else
  {
    v15 = -2003292352;
    if ( v13 )
LABEL_10:
      DoStackCapture(v15);
  }
  return v15;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_8], rbx
0x180001015  mov     [rsp+arg_10], r8d
0x18000101a  push    rbp
0x18000101b  push    rsi
0x18000101c  push    rdi
0x18000101d  push    r12
0x18000101f  push    r13
0x180001021  push    r14
0x180001023  push    r15
0x180001025  sub     rsp, 30h
0x180001029  mov     rax, [rsp+68h+arg_28]
0x180001031  xor     ebx, ebx
0x180001033  mov     r13, [rsp+68h+arg_30]
0x18000103b  mov     r15, r9
0x18000103e  mov     ebp, [rcx+0E8h]
0x180001044  mov     r9d, r8d
0x180001047  mov     r12, [rsp+68h+arg_20]
0x18000104f  mov     rsi, rdx
0x180001052  mov     r8d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180001059  mov     r14, rcx
0x18000105c  mov     [rax], ebx
0x18000105e  mov     edi, ebx
0x180001060  mov     [r13+0], ebx
0x180001064  mov     edx, ebx
0x180001066  mov     [rsp+68h+arg_0], ebx
0x18000106a  nop     word ptr [rax+rax+00h]
0x180001070  cmp     ebx, ebp
0x180001072  jnb     loc_180001101
0x180001078  mov     rax, [r14+0D0h]
0x18000107f  mov     rcx, [rax+rbx*8]
0x180001083  test    byte ptr [rcx+8], 2
0x180001087  jnz     short loc_1800010DF
0x180001089  test    rsi, rsi
0x18000108c  jz      loc_18000111A
0x180001092  lea     r9, [rsp+68h+arg_30]
0x18000109a  mov     dword ptr [rsp+68h+arg_30], 1
0x1800010a5  mov     r8, r12
0x1800010a8  mov     rdx, r15
0x1800010ab  mov     rax, rsi
0x1800010ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010b3  mov     r8d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800010ba  mov     edi, eax
0x1800010bc  test    eax, eax
0x1800010be  jns     short loc_1800010C5
0x1800010c0  test    r8d, r8d
0x1800010c3  jnz     short loc_1800010E3
0x1800010c5  test    edi, edi
0x1800010c7  js      short loc_1800010EC
0x1800010c9  cmp     dword ptr [rsp+68h+arg_30], 0
0x1800010d1  mov     edx, [rsp+68h+arg_0]
0x1800010d5  mov     r9d, [rsp+68h+arg_10]
0x1800010dd  jnz     short loc_18000111A
0x1800010df  inc     ebx
0x1800010e1  jmp     short loc_180001070
0x1800010e3  mov     ecx, edi; int
0x1800010e5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800010ea  mov     eax, edi
0x1800010ec  mov     rbx, [rsp+68h+arg_8]
0x1800010f1  add     rsp, 30h
0x1800010f5  pop     r15
0x1800010f7  pop     r14
0x1800010f9  pop     r13
0x1800010fb  pop     r12
0x1800010fd  pop     rdi
0x1800010fe  pop     rsi
0x1800010ff  pop     rbp
0x180001100  retn
0x180001101  mov     [r13+0], ebx
0x180001105  cmp     r9d, edx
0x180001108  jnz     short loc_18000112D
0x18000110a  mov     rax, [rsp+68h+arg_28]
0x180001112  mov     dword ptr [rax], 1
0x180001118  jmp     short loc_1800010EA
0x18000111a  cmp     r9d, edx
0x18000111d  jnz     short loc_180001125
0x18000111f  mov     [r13+0], ebx
0x180001123  jmp     short loc_1800010EA
0x180001125  inc     edx
0x180001127  mov     [rsp+68h+arg_0], edx
0x18000112b  jmp     short loc_1800010DF
0x18000112d  mov     edi, 88982F40h
0x180001132  test    r8d, r8d
0x180001135  jz      short loc_1800010EA
0x180001137  jmp     short loc_1800010E3
```
