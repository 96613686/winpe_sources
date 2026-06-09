# CspHandleLineRead

- ea: `0x14001ded4`
- end: `0x14001e204`
- name: `CspHandleLineRead`
- size: `816`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001e628`

## callees

- `0x14001d9ec`
- `0x14001ded4`
- `0x14001e374`
- `0x14001e448`
- `0x14001e5f4`
- `0x14001f07c`
- `0x14002074c`
- `0x140021cf0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001e09d`
- `ntdll!RtlAllocateHeap` at `0x14001e09d`
- `ntdll!RtlFreeHeap` at `0x14001e0ec`
- `ntdll!RtlFreeHeap` at `0x14001e0f7`
- `ntdll!RtlFreeHeap` at `0x14001e16f`
- `ntdll!RtlFreeHeap` at `0x14001e1ae`
- `ntdll!RtlFreeHeap` at `0x14001e0ec`
- `ntdll!RtlFreeHeap` at `0x14001e0f7`
- `ntdll!RtlFreeHeap` at `0x14001e16f`
- `ntdll!RtlFreeHeap` at `0x14001e1ae`
- `ntdll!RtlUnicodeToUTF8N` at `0x14001e079`
- `ntdll!RtlUnicodeToUTF8N` at `0x14001e0ce`
- `ntdll!RtlUnicodeToUTF8N` at `0x14001e079`
- `ntdll!RtlUnicodeToUTF8N` at `0x14001e0ce`

## pseudocode

```c
char __fastcall CspHandleLineRead(__int64 a1, __int64 a2, char a3, __int64 a4)
{
  PVOID *v4; // rdi
  unsigned int v6; // edx
  __int64 v9; // rdx
  int v10; // ebp
  unsigned int v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // r10
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rbp
  __int64 v17; // rdx
  PVOID Heap; // r14
  PVOID ProcessHeap; // rcx
  int v20; // eax
  unsigned int v21; // ecx
  PVOID v22; // r8
  unsigned int v24; // ecx
  bool v25; // zf
  SIZE_T Size; // [rsp+60h] [rbp+8h] BYREF

  v4 = (PVOID *)(a1 + 152);
  LODWORD(Size) = 0;
  v6 = *(_DWORD *)(a1 + 168);
  if ( !v6 )
  {
    if ( !*v4 )
    {
      v10 = CspInitializeLineBuffer(a1, a2);
      if ( v10 < 0 )
        goto LABEL_32;
    }
    v11 = *(_DWORD *)(a1 + 164);
    LOBYTE(a4) = 0;
    v12 = *(unsigned int *)(a1 + 160);
    if ( v11 >= (unsigned int)v12 )
    {
      v15 = (unsigned int)v12;
      v14 = *(_DWORD *)(a1 + 164);
    }
    else
    {
      do
      {
        v13 = *(unsigned int *)(a1 + 144);
        v14 = v11;
        v15 = (unsigned int)v12;
        if ( *(_DWORD *)(a1 + 140) == (_DWORD)v13 || (_BYTE)a4 )
          break;
        if ( *(_WORD *)(a1 + 20 * v13 + 456) == 1 )
        {
          v16 = a1 + 20 * (v13 + 23);
          if ( *(_DWORD *)v16 )
          {
            LOBYTE(a4) = CspProcessKey(a1, a2, a1 + 20 * (v13 + 23));
            if ( *(_WORD *)(v16 + 4) )
              continue;
          }
        }
        v17 = ((unsigned int)(*(_DWORD *)(a1 + 144) + 1) * (unsigned __int128)0x47AE147AE147AE15uLL) >> 64;
        *(_DWORD *)(a1 + 144) = *(_DWORD *)(a1 + 144)
                              + 1
                              - 100
                              * ((v17 + (((unsigned __int64)(unsigned int)(*(_DWORD *)(a1 + 144) + 1) - v17) >> 1)) >> 6);
        v11 = *(_DWORD *)(a1 + 164);
        v14 = v11;
        v12 = *(unsigned int *)(a1 + 160);
        v15 = (unsigned int)v12;
      }
      while ( v11 < (unsigned int)v12 );
    }
    if ( !v14 || !(_BYTE)a4 && v14 < (unsigned int)v15 )
    {
      CspResetInputEventIfEmpty(a1, v12, v15, a4);
      return 0;
    }
    if ( *((_WORD *)*v4 + ((unsigned __int64)v14 >> 1) - 1) == 13 )
    {
      CspAddHistoryEntry(a1, v12, v15);
      if ( (*(_BYTE *)(a1 + 132) & 1) != 0 )
      {
        *((_WORD *)*v4 + ((unsigned __int64)*(unsigned int *)(a1 + 164) >> 1)) = 10;
        *(_DWORD *)(a1 + 164) += 2;
        if ( (*(_BYTE *)(a1 + 132) & 4) != 0 )
          CspEchoInputString(a1, L"\n", 1);
      }
    }
    if ( !a3 )
    {
      v10 = RtlUnicodeToUTF8N(0, 0, &Size, *v4, *(_DWORD *)(a1 + 164));
      if ( v10 < 0 )
        goto LABEL_32;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
      if ( !Heap )
      {
        v10 = -1073741670;
        goto LABEL_32;
      }
      v10 = RtlUnicodeToUTF8N(Heap, (unsigned int)Size, &Size, *v4, *(_DWORD *)(a1 + 164));
      ProcessHeap = NtCurrentPeb()->ProcessHeap;
      if ( v10 < 0 )
      {
        RtlFreeHeap(ProcessHeap, 0, Heap);
        goto LABEL_32;
      }
      RtlFreeHeap(ProcessHeap, 0, *v4);
      v20 = Size;
      *(_DWORD *)(a1 + 164) = Size;
      *(_DWORD *)(a1 + 160) = v20;
      *v4 = Heap;
    }
    v6 = *(_DWORD *)(a1 + 164);
    *(_DWORD *)(a1 + 168) = v6;
  }
  v21 = *(_DWORD *)(a2 + 128) - *(_DWORD *)(a2 + 40);
  LODWORD(Size) = v21;
  if ( v21 > v6 )
  {
    v21 = v6;
    LODWORD(Size) = v6;
  }
  v10 = WriteMessageOutput(a1, a2, 0, *(_DWORD *)v4 + *(_DWORD *)(a1 + 164) - v6, v21);
  if ( v10 >= 0 )
  {
    v24 = Size;
    v25 = *(_DWORD *)(a1 + 168) == (_DWORD)Size;
    *(_DWORD *)(a1 + 168) -= Size;
    if ( v25 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v4);
      v24 = Size;
      *v4 = 0;
    }
    *(_QWORD *)(a2 + 16) = v24;
    *(_DWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 156) = *(_DWORD *)(a1 + 128);
    *(_DWORD *)(a2 + 160) = v24;
    goto LABEL_39;
  }
LABEL_32:
  v22 = *v4;
  if ( *v4 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
    *v4 = 0;
  }
  *(_DWORD *)(a1 + 168) = 0;
  *(_DWORD *)(a2 + 8) = v10;
LABEL_39:
  CspResetInputEventIfEmpty(a1, v9, v22, a4);
  CspCompleteConsoleIo(a1, a2);
  return 1;
}

```

## disassembly

```asm
0x14001ded4  mov     [rsp+arg_8], rbx
0x14001ded9  mov     [rsp+arg_10], rbp
0x14001dede  push    rsi
0x14001dedf  push    rdi
0x14001dee0  push    r12
0x14001dee2  push    r14
0x14001dee4  push    r15
0x14001dee6  sub     rsp, 30h
0x14001deea  xor     r15d, r15d
0x14001deed  lea     rdi, [rcx+98h]
0x14001def4  mov     rsi, rdx
0x14001def7  mov     dword ptr [rsp+58h+Size], r15d
0x14001defc  mov     edx, [rcx+0A8h]
0x14001df02  mov     r14b, r8b
0x14001df05  mov     rbx, rcx
0x14001df08  lea     r12d, [r15+1]
0x14001df0c  test    edx, edx
0x14001df0e  jnz     loc_14001E11C
0x14001df14  cmp     [rdi], r15
0x14001df17  jnz     short loc_14001DF2B
0x14001df19  mov     rdx, rsi
0x14001df1c  call    CspInitializeLineBuffer
0x14001df21  mov     ebp, eax
0x14001df23  test    eax, eax
0x14001df25  js      loc_14001E158
0x14001df2b  mov     ecx, [rbx+0A4h]
0x14001df31  mov     r9b, r15b
0x14001df34  mov     edx, [rbx+0A0h]
0x14001df3a  cmp     ecx, edx
0x14001df3c  jnb     loc_14001DFEA
0x14001df42  mov     r10d, [rbx+90h]
0x14001df49  mov     eax, ecx
0x14001df4b  mov     r8d, edx
0x14001df4e  cmp     [rbx+8Ch], r10d
0x14001df55  jz      loc_14001DFEF
0x14001df5b  test    r9b, r9b
0x14001df5e  jnz     loc_14001DFEF
0x14001df64  lea     rax, [r10+r10*4]
0x14001df68  cmp     [rbx+rax*4+1C8h], r12w
0x14001df71  jnz     short loc_14001DF9D
0x14001df73  lea     rax, [r10+17h]
0x14001df77  lea     rax, [rax+rax*4]
0x14001df7b  lea     rbp, [rbx+rax*4]
0x14001df7f  cmp     [rbp+0], r15d
0x14001df83  jz      short loc_14001DF9D
0x14001df85  mov     r8, rbp
0x14001df88  mov     rdx, rsi
0x14001df8b  mov     rcx, rbx
0x14001df8e  call    CspProcessKey
0x14001df93  mov     r9b, al
0x14001df96  cmp     [rbp+4], r15w
0x14001df9b  jnz     short loc_14001DFCF
0x14001df9d  mov     ecx, [rbx+90h]
0x14001dfa3  mov     rax, 47AE147AE147AE15h
0x14001dfad  add     ecx, r12d
0x14001dfb0  mul     rcx
0x14001dfb3  mov     eax, ecx
0x14001dfb5  sub     rax, rdx
0x14001dfb8  shr     rax, 1
0x14001dfbb  add     rax, rdx
0x14001dfbe  shr     rax, 6
0x14001dfc2  imul    rax, 64h ; 'd'
0x14001dfc6  sub     rcx, rax
0x14001dfc9  mov     [rbx+90h], ecx
0x14001dfcf  mov     ecx, [rbx+0A4h]
0x14001dfd5  mov     eax, ecx
0x14001dfd7  mov     edx, [rbx+0A0h]
0x14001dfdd  mov     r8d, edx
0x14001dfe0  cmp     ecx, edx
0x14001dfe2  jb      loc_14001DF42
0x14001dfe8  jmp     short loc_14001DFEF
0x14001dfea  mov     r8d, edx
0x14001dfed  mov     eax, ecx
0x14001dfef  test    eax, eax
0x14001dff1  jz      loc_14001E184
0x14001dff7  test    r9b, r9b
0x14001dffa  jnz     short loc_14001E005
0x14001dffc  cmp     eax, r8d
0x14001dfff  jb      loc_14001E184
0x14001e005  mov     ecx, eax
0x14001e007  mov     rax, [rdi]
0x14001e00a  shr     rcx, 1
0x14001e00d  cmp     word ptr [rax+rcx*2-2], 0Dh
0x14001e013  jnz     short loc_14001E05A
0x14001e015  mov     rcx, rbx
0x14001e018  call    CspAddHistoryEntry
0x14001e01d  test    [rbx+84h], r12b
0x14001e024  jz      short loc_14001E05A
0x14001e026  mov     ecx, [rbx+0A4h]
0x14001e02c  mov     rax, [rdi]
0x14001e02f  shr     rcx, 1
0x14001e032  mov     word ptr [rax+rcx*2], 0Ah
0x14001e038  add     dword ptr [rbx+0A4h], 2
0x14001e03f  test    byte ptr [rbx+84h], 4
0x14001e046  jz      short loc_14001E05A
0x14001e048  mov     r8d, r12d
0x14001e04b  lea     rdx, asc_140027580; "\n"
0x14001e052  mov     rcx, rbx
0x14001e055  call    CspEchoInputString
0x14001e05a  test    r14b, r14b
0x14001e05d  jnz     loc_14001E110
0x14001e063  mov     eax, [rbx+0A4h]
0x14001e069  lea     r8, [rsp+58h+Size]
0x14001e06e  mov     r9, [rdi]
0x14001e071  xor     edx, edx
0x14001e073  xor     ecx, ecx
0x14001e075  mov     [rsp+58h+var_38], eax
0x14001e079  call    cs:__imp_RtlUnicodeToUTF8N
0x14001e07f  mov     ebp, eax
0x14001e081  test    eax, eax
0x14001e083  js      loc_14001E158
0x14001e089  mov     rcx, gs:60h
0x14001e092  xor     edx, edx; Flags
0x14001e094  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x14001e099  mov     rcx, [rcx+30h]; HeapHandle
0x14001e09d  call    cs:__imp_RtlAllocateHeap
0x14001e0a3  mov     r14, rax
0x14001e0a6  test    rax, rax
0x14001e0a9  jnz     short loc_14001E0B5
0x14001e0ab  mov     ebp, 0C000009Ah
0x14001e0b0  jmp     loc_14001E158
0x14001e0b5  mov     eax, [rbx+0A4h]
0x14001e0bb  lea     r8, [rsp+58h+Size]
0x14001e0c0  mov     r9, [rdi]
0x14001e0c3  mov     rcx, r14
0x14001e0c6  mov     edx, dword ptr [rsp+58h+Size]
0x14001e0ca  mov     [rsp+58h+var_38], eax
0x14001e0ce  call    cs:__imp_RtlUnicodeToUTF8N
0x14001e0d4  mov     rcx, gs:60h
0x14001e0dd  xor     edx, edx; Flags
0x14001e0df  mov     ebp, eax
0x14001e0e1  mov     rcx, [rcx+30h]; HeapHandle
0x14001e0e5  test    eax, eax
0x14001e0e7  jns     short loc_14001E0F4
0x14001e0e9  mov     r8, r14; P
0x14001e0ec  call    cs:__imp_RtlFreeHeap
0x14001e0f2  jmp     short loc_14001E158
0x14001e0f4  mov     r8, [rdi]; P
0x14001e0f7  call    cs:__imp_RtlFreeHeap
0x14001e0fd  mov     eax, dword ptr [rsp+58h+Size]
0x14001e101  mov     [rbx+0A4h], eax
0x14001e107  mov     [rbx+0A0h], eax
0x14001e10d  mov     [rdi], r14
0x14001e110  mov     edx, [rbx+0A4h]
0x14001e116  mov     [rbx+0A8h], edx
0x14001e11c  mov     ecx, [rsi+80h]
0x14001e122  sub     ecx, [rsi+28h]
0x14001e125  mov     dword ptr [rsp+58h+Size], ecx
0x14001e129  cmp     ecx, edx
0x14001e12b  jbe     short loc_14001E133
0x14001e12d  mov     ecx, edx
0x14001e12f  mov     dword ptr [rsp+58h+Size], edx
0x14001e133  mov     r9d, [rbx+0A4h]
0x14001e13a  xor     r8d, r8d
0x14001e13d  sub     r9d, edx
0x14001e140  mov     [rsp+58h+var_38], ecx
0x14001e144  add     r9, [rdi]
0x14001e147  mov     rdx, rsi
0x14001e14a  mov     rcx, rbx
0x14001e14d  call    WriteMessageOutput
0x14001e152  mov     ebp, eax
0x14001e154  test    eax, eax
0x14001e156  jns     short loc_14001E190
0x14001e158  mov     r8, [rdi]; P
0x14001e15b  test    r8, r8
0x14001e15e  jz      short loc_14001E178
0x14001e160  mov     rcx, gs:60h
0x14001e169  xor     edx, edx; Flags
0x14001e16b  mov     rcx, [rcx+30h]; HeapHandle
0x14001e16f  call    cs:__imp_RtlFreeHeap
0x14001e175  mov     [rdi], r15
0x14001e178  mov     [rbx+0A8h], r15d
0x14001e17f  mov     [rsi+8], ebp
0x14001e182  jmp     short loc_14001E1D7
0x14001e184  mov     rcx, rbx
0x14001e187  call    CspResetInputEventIfEmpty
0x14001e18c  xor     al, al
0x14001e18e  jmp     short loc_14001E1ED
0x14001e190  mov     ecx, dword ptr [rsp+58h+Size]
0x14001e194  sub     [rbx+0A8h], ecx
0x14001e19a  jnz     short loc_14001E1BB
0x14001e19c  mov     rcx, gs:60h
0x14001e1a5  xor     edx, edx; Flags
0x14001e1a7  mov     r8, [rdi]; P
0x14001e1aa  mov     rcx, [rcx+30h]; HeapHandle
0x14001e1ae  call    cs:__imp_RtlFreeHeap
0x14001e1b4  mov     ecx, dword ptr [rsp+58h+Size]
0x14001e1b8  mov     [rdi], r15
0x14001e1bb  mov     eax, ecx
0x14001e1bd  mov     [rsi+10h], rax
0x14001e1c1  mov     [rsi+8], r15d
0x14001e1c5  mov     eax, [rbx+80h]
0x14001e1cb  mov     [rsi+9Ch], eax
0x14001e1d1  mov     [rsi+0A0h], ecx
0x14001e1d7  mov     rcx, rbx
0x14001e1da  call    CspResetInputEventIfEmpty
0x14001e1df  mov     rdx, rsi
0x14001e1e2  mov     rcx, rbx
0x14001e1e5  call    CspCompleteConsoleIo
0x14001e1ea  mov     al, r12b
0x14001e1ed  mov     rbx, [rsp+58h+arg_8]
0x14001e1f2  mov     rbp, [rsp+58h+arg_10]
0x14001e1f7  add     rsp, 30h
0x14001e1fb  pop     r15
0x14001e1fd  pop     r14
0x14001e1ff  pop     r12
0x14001e201  pop     rdi
0x14001e202  pop     rsi
0x14001e203  retn
```
