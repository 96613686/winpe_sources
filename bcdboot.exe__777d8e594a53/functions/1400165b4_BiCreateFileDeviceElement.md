# BiCreateFileDeviceElement

- ea: `0x1400165b4`
- end: `0x14001677c`
- name: `BiCreateFileDeviceElement`
- size: `456`
- prototype: `__int64 __fastcall(const wchar_t *Src, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x140016784`

## callees

- `0x1400165b4`
- `0x1400265e2`
- `0x1400265fa`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1400166e9`
- `msvcrt!wcscpy_s` at `0x14001670f`
- `msvcrt!wcscpy_s` at `0x1400166e9`
- `msvcrt!wcscpy_s` at `0x14001670f`
- `msvcrt!_wcsnicmp` at `0x1400165e2`
- `msvcrt!_wcsnicmp` at `0x1400165e2`
- `msvcrt!wcschr` at `0x1400165fa`
- `msvcrt!wcschr` at `0x1400165fa`
- `ntdll!RtlAllocateHeap` at `0x14001662b`
- `ntdll!RtlAllocateHeap` at `0x14001669e`
- `ntdll!RtlAllocateHeap` at `0x14001662b`
- `ntdll!RtlAllocateHeap` at `0x14001669e`
- `ntdll!RtlFreeHeap` at `0x140016737`
- `ntdll!RtlFreeHeap` at `0x140016758`
- `ntdll!RtlFreeHeap` at `0x140016737`
- `ntdll!RtlFreeHeap` at `0x140016758`

## pseudocode

```c
__int64 __fastcall BiCreateFileDeviceElement(const wchar_t *Src, _QWORD *a2, unsigned int *a3)
{
  wchar_t *v4; // rax
  const wchar_t *v5; // r14
  __int64 v6; // rbx
  char *Heap; // rsi
  int v8; // ebx
  size_t v9; // rbx
  __int64 v10; // rbp
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // r15d
  unsigned int v14; // r13d
  char *v15; // rax
  char *v16; // rdi
  __int64 v17; // rdx

  if ( _wcsnicmp(Src, L"\\Device\\HarddiskVolume", 0x16u) )
    return (unsigned int)-1073741811;
  v4 = wcschr(Src + 22, 0x5Cu);
  if ( (v5 = v4) == 0 )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    v6 = v4 - Src;
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * (unsigned int)(v6 + 1));
    if ( Heap )
    {
      v9 = 2LL * (unsigned int)v6;
      memcpy_0(Heap, Src, v9);
      v10 = -1;
      *(_WORD *)&Heap[v9] = 0;
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&Heap[2 * v11] );
      v12 = -1;
      do
        ++v12;
      while ( v5[v12] );
      v13 = 2 * v12 + 46;
      v14 = v13 + 2 * (v11 + 11);
      v15 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
      v16 = v15;
      if ( v15 )
      {
        v8 = 0;
        memset_0(v15, 0, v14);
        v17 = -1;
        *((_DWORD *)v16 + 5) = v13;
        *(_DWORD *)v16 = 3;
        do
          ++v17;
        while ( v5[v17] );
        wcscpy_s((wchar_t *)v16 + 12, v17 + 1, v5);
        *(_DWORD *)&v16[v13] = 2;
        do
          ++v10;
        while ( *(_WORD *)&Heap[2 * v10] );
        wcscpy_s((wchar_t *)&v16[v13 + 20], v10 + 1, (const wchar_t *)Heap);
        *a2 = v16;
        *a3 = v14;
      }
      else
      {
        v8 = -1073741670;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      if ( v8 < 0 && v16 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400165b4  mov     [rsp+arg_0], rbx
0x1400165b9  mov     [rsp+arg_10], r8
0x1400165be  mov     [rsp+arg_8], rdx
0x1400165c3  push    rbp
0x1400165c4  push    rsi
0x1400165c5  push    rdi
0x1400165c6  push    r12
0x1400165c8  push    r13
0x1400165ca  push    r14
0x1400165cc  push    r15
0x1400165ce  sub     rsp, 20h
0x1400165d2  mov     r8d, 16h; MaxCount
0x1400165d8  lea     rdx, aDeviceHarddisk_1; "\\Device\\HarddiskVolume"
0x1400165df  mov     rdi, rcx
0x1400165e2  call    cs:__imp__wcsnicmp
0x1400165e8  xor     r15d, r15d
0x1400165eb  test    eax, eax
0x1400165ed  jnz     loc_140016760
0x1400165f3  lea     edx, [rax+5Ch]; Ch
0x1400165f6  lea     rcx, [rdi+2Ch]; Str
0x1400165fa  call    cs:__imp_wcschr
0x140016600  mov     r14, rax
0x140016603  test    rax, rax
0x140016606  jz      loc_140016760
0x14001660c  mov     rcx, gs:60h
0x140016615  mov     rbx, rax
0x140016618  sub     rbx, rdi
0x14001661b  xor     edx, edx; Flags
0x14001661d  sar     rbx, 1
0x140016620  mov     rcx, [rcx+30h]; HeapHandle
0x140016624  lea     r8d, [rbx+1]
0x140016628  add     r8, r8; Size
0x14001662b  call    cs:__imp_RtlAllocateHeap
0x140016631  mov     rsi, rax
0x140016634  test    rax, rax
0x140016637  jnz     short loc_140016643
0x140016639  mov     ebx, 0C000009Ah
0x14001663e  jmp     loc_140016765
0x140016643  mov     eax, ebx
0x140016645  mov     rdx, rdi; Src
0x140016648  mov     rcx, rsi; void *
0x14001664b  lea     rbx, [rax+rax]
0x14001664f  mov     r8, rbx; Size
0x140016652  call    memcpy_0
0x140016657  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14001665b  mov     [rbx+rsi], r15w
0x140016660  mov     rcx, rbp
0x140016663  inc     rcx
0x140016666  cmp     [rsi+rcx*2], r15w
0x14001666b  jnz     short loc_140016663
0x14001666d  mov     rax, rbp
0x140016670  inc     rax
0x140016673  cmp     [r14+rax*2], r15w
0x140016678  jnz     short loc_140016670
0x14001667a  lea     ecx, [rcx+0Bh]
0x14001667d  xor     edx, edx; Flags
0x14001667f  lea     r15d, ds:2Eh[rax*2]
0x140016687  lea     r13d, [r15+rcx*2]
0x14001668b  mov     rcx, gs:60h
0x140016694  mov     r8d, r13d; Size
0x140016697  mov     r12d, r13d
0x14001669a  mov     rcx, [rcx+30h]; HeapHandle
0x14001669e  call    cs:__imp_RtlAllocateHeap
0x1400166a4  mov     rdi, rax
0x1400166a7  test    rax, rax
0x1400166aa  jnz     short loc_1400166B3
0x1400166ac  mov     ebx, 0C000009Ah
0x1400166b1  jmp     short loc_140016725
0x1400166b3  mov     r8, r12; Size
0x1400166b6  xor     edx, edx; Val
0x1400166b8  mov     rcx, rdi; void *
0x1400166bb  xor     ebx, ebx
0x1400166bd  call    memset_0
0x1400166c2  mov     r12d, r15d
0x1400166c5  mov     rdx, rbp
0x1400166c8  mov     [rdi+14h], r15d
0x1400166cc  xor     r15d, r15d
0x1400166cf  mov     dword ptr [rdi], 3
0x1400166d5  inc     rdx
0x1400166d8  cmp     [r14+rdx*2], r15w
0x1400166dd  jnz     short loc_1400166D5
0x1400166df  inc     rdx; SizeInWords
0x1400166e2  lea     rcx, [rdi+18h]; Destination
0x1400166e6  mov     r8, r14; Source
0x1400166e9  call    cs:__imp_wcscpy_s
0x1400166ef  mov     dword ptr [r12+rdi], 2
0x1400166f7  inc     rbp
0x1400166fa  cmp     [rsi+rbp*2], r15w
0x1400166ff  jnz     short loc_1400166F7
0x140016701  lea     rcx, [rdi+14h]
0x140016705  mov     r8, rsi; Source
0x140016708  add     rcx, r12; Destination
0x14001670b  lea     rdx, [rbp+1]; SizeInWords
0x14001670f  call    cs:__imp_wcscpy_s
0x140016715  mov     rax, [rsp+58h+arg_8]
0x14001671a  mov     [rax], rdi
0x14001671d  mov     rax, [rsp+58h+arg_10]
0x140016722  mov     [rax], r13d
0x140016725  mov     rcx, gs:60h
0x14001672e  mov     r8, rsi; P
0x140016731  xor     edx, edx; Flags
0x140016733  mov     rcx, [rcx+30h]; HeapHandle
0x140016737  call    cs:__imp_RtlFreeHeap
0x14001673d  test    ebx, ebx
0x14001673f  jns     short loc_140016765
0x140016741  test    rdi, rdi
0x140016744  jz      short loc_140016765
0x140016746  mov     rcx, gs:60h
0x14001674f  mov     r8, rdi; P
0x140016752  xor     edx, edx; Flags
0x140016754  mov     rcx, [rcx+30h]; HeapHandle
0x140016758  call    cs:__imp_RtlFreeHeap
0x14001675e  jmp     short loc_140016765
0x140016760  mov     ebx, 0C000000Dh
0x140016765  mov     eax, ebx
0x140016767  mov     rbx, [rsp+58h+arg_0]
0x14001676c  add     rsp, 20h
0x140016770  pop     r15
0x140016772  pop     r14
0x140016774  pop     r13
0x140016776  pop     r12
0x140016778  pop     rdi
0x140016779  pop     rsi
0x14001677a  pop     rbp
0x14001677b  retn
```
