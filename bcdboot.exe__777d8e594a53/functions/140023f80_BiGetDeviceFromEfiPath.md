# BiGetDeviceFromEfiPath

- ea: `0x140023f80`
- end: `0x140024159`
- name: `BiGetDeviceFromEfiPath`
- size: `473`
- prototype: `__int64 __fastcall(char *Src, _QWORD *, _DWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140022e8c`
- `0x140024cf0`

## callees

- `0x1400133e4`
- `0x140023f80`
- `0x140024b30`
- `0x1400265e2`
- `0x1400265fa`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140024015`
- `ntdll!RtlAllocateHeap` at `0x140024090`
- `ntdll!RtlAllocateHeap` at `0x140024015`
- `ntdll!RtlAllocateHeap` at `0x140024090`
- `ntdll!RtlFreeHeap` at `0x140024102`
- `ntdll!RtlFreeHeap` at `0x14002411f`
- `ntdll!RtlFreeHeap` at `0x14002413c`
- `ntdll!RtlFreeHeap` at `0x140024102`
- `ntdll!RtlFreeHeap` at `0x14002411f`
- `ntdll!RtlFreeHeap` at `0x14002413c`

## string_xrefs

- `0x1400240da`: `BiGetDeviceFromEfiPath failed: %x`

## pseudocode

```c
__int64 __fastcall BiGetDeviceFromEfiPath(char *Src, _QWORD *a2, _DWORD *a3)
{
  char *v3; // rdi
  char v4; // al
  _DWORD *v5; // r14
  char *v8; // rsi
  unsigned int v9; // ebx
  char *i; // rbx
  size_t v11; // rbx
  char *Heap; // rax
  int v13; // eax
  unsigned int v14; // ebp
  _DWORD *v15; // rax
  _QWORD *v16; // rax
  PVOID P; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v19; // [rsp+68h] [rbp+10h]

  v19 = a2;
  v3 = 0;
  v4 = *Src & 0x7F;
  v5 = 0;
  P = 0;
  if ( v4 == 127 )
  {
    v8 = 0;
    v9 = -1073741766;
  }
  else
  {
    for ( i = &Src[*((unsigned __int16 *)Src + 1)];
          (*i & 0x7F) != 0x7F && (*i != 4 || i[1] != 4);
          i += *((unsigned __int16 *)i + 1) )
    {
      ;
    }
    v11 = (unsigned int)((_DWORD)i - (_DWORD)Src);
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v11 + 16));
    v8 = Heap;
    if ( Heap )
    {
      *(_DWORD *)Heap = 1;
      *((_DWORD *)Heap + 1) = v11 + 16;
      *((_DWORD *)Heap + 2) = 4;
      memcpy_0(Heap + 12, Src, v11);
      *(_DWORD *)&v8[v11 + 12] = 327551;
      v13 = BiTranslateFilePath(v8, 3, &P);
      v3 = (char *)P;
      v9 = v13;
      if ( v13 < 0 )
      {
        if ( v13 == -1073741811 )
          goto LABEL_16;
        goto LABEL_14;
      }
      v14 = *((_DWORD *)P + 1) - 12;
      v15 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v14 + 20);
      v5 = v15;
      if ( v15 )
      {
        memset_0(v15, 0, v14 + 20);
        *v5 = 2;
        memcpy_0(v5 + 5, v3 + 12, v14);
        v16 = v19;
        *a3 = v14 + 20;
        *v16 = v5;
        goto LABEL_16;
      }
    }
    v9 = -1073741670;
  }
LABEL_14:
  BiLogMessage(4, L"BiGetDeviceFromEfiPath failed: %x", v9);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
LABEL_16:
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return v9;
}

```

## disassembly

```asm
0x140023f80  mov     [rsp+arg_10], rbx
0x140023f85  mov     [rsp+arg_8], rdx
0x140023f8a  push    rbp
0x140023f8b  push    rsi
0x140023f8c  push    rdi
0x140023f8d  push    r12
0x140023f8f  push    r13
0x140023f91  push    r14
0x140023f93  push    r15
0x140023f95  sub     rsp, 20h
0x140023f99  mov     al, [rcx]
0x140023f9b  mov     r12b, 7Fh
0x140023f9e  xor     edi, edi
0x140023fa0  and     al, r12b
0x140023fa3  xor     r14d, r14d
0x140023fa6  mov     [rsp+58h+P], rdi
0x140023fab  mov     r13, r8
0x140023fae  mov     r15, rcx
0x140023fb1  cmp     al, r12b
0x140023fb4  jnz     short loc_140023FC2
0x140023fb6  xor     esi, esi
0x140023fb8  mov     ebx, 0C000003Ah
0x140023fbd  jmp     loc_1400240D7
0x140023fc2  movzx   ebx, byte ptr [rcx+3]
0x140023fc6  movzx   eax, byte ptr [rcx+2]
0x140023fca  shl     rbx, 8
0x140023fce  or      rbx, rax
0x140023fd1  add     rbx, r15
0x140023fd4  mov     al, [rbx]
0x140023fd6  and     al, r12b
0x140023fd9  cmp     al, r12b
0x140023fdc  jz      short loc_140023FFD
0x140023fde  cmp     byte ptr [rbx], 4
0x140023fe1  jnz     short loc_140023FE9
0x140023fe3  cmp     byte ptr [rbx+1], 4
0x140023fe7  jz      short loc_140023FFD
0x140023fe9  movzx   ecx, byte ptr [rbx+3]
0x140023fed  movzx   eax, byte ptr [rbx+2]
0x140023ff1  shl     rcx, 8
0x140023ff5  or      rcx, rax
0x140023ff8  add     rbx, rcx
0x140023ffb  jmp     short loc_140023FD4
0x140023ffd  mov     rcx, gs:60h
0x140024006  sub     ebx, r15d
0x140024009  xor     edx, edx; Flags
0x14002400b  mov     rcx, [rcx+30h]; HeapHandle
0x14002400f  lea     ebp, [rbx+10h]
0x140024012  mov     r8d, ebp; Size
0x140024015  call    cs:__imp_RtlAllocateHeap
0x14002401b  mov     rsi, rax
0x14002401e  test    rax, rax
0x140024021  jnz     short loc_14002402D
0x140024023  mov     ebx, 0C000009Ah
0x140024028  jmp     loc_1400240D7
0x14002402d  lea     rcx, [rax+0Ch]; void *
0x140024031  mov     dword ptr [rax], 1
0x140024037  mov     r8, rbx; Size
0x14002403a  mov     [rax+4], ebp
0x14002403d  mov     rdx, r15; Src
0x140024040  mov     dword ptr [rax+8], 4
0x140024047  call    memcpy_0
0x14002404c  lea     r8, [rsp+58h+P]
0x140024051  mov     dword ptr [rbx+rsi+0Ch], 4FF7Fh
0x140024059  mov     edx, 3
0x14002405e  mov     rcx, rsi
0x140024061  call    BiTranslateFilePath
0x140024066  mov     rdi, [rsp+58h+P]
0x14002406b  mov     ebx, eax
0x14002406d  test    eax, eax
0x14002406f  js      short loc_1400240D0
0x140024071  mov     ebp, [rdi+4]
0x140024074  xor     edx, edx; Flags
0x140024076  mov     rcx, gs:60h
0x14002407f  add     ebp, 0FFFFFFF4h
0x140024082  mov     rcx, [rcx+30h]; HeapHandle
0x140024086  lea     r15d, [rbp+14h]
0x14002408a  mov     r8d, r15d; Size
0x14002408d  mov     r12d, r15d
0x140024090  call    cs:__imp_RtlAllocateHeap
0x140024096  mov     r14, rax
0x140024099  test    rax, rax
0x14002409c  jz      short loc_140024023
0x14002409e  mov     r8d, r12d; Size
0x1400240a1  xor     edx, edx; Val
0x1400240a3  mov     rcx, rax; void *
0x1400240a6  call    memset_0
0x1400240ab  mov     r8d, ebp; Size
0x1400240ae  lea     rdx, [rdi+0Ch]; Src
0x1400240b2  lea     rcx, [r14+14h]; void *
0x1400240b6  mov     dword ptr [r14], 2
0x1400240bd  call    memcpy_0
0x1400240c2  mov     rax, [rsp+58h+arg_8]
0x1400240c7  mov     [r13+0], r15d
0x1400240cb  mov     [rax], r14
0x1400240ce  jmp     short loc_140024108
0x1400240d0  cmp     eax, 0C000000Dh
0x1400240d5  jz      short loc_140024108
0x1400240d7  mov     r8d, ebx
0x1400240da  lea     rdx, aBigetdevicefro; "BiGetDeviceFromEfiPath failed: %x"
0x1400240e1  mov     ecx, 4
0x1400240e6  call    BiLogMessage
0x1400240eb  test    r14, r14
0x1400240ee  jz      short loc_140024108
0x1400240f0  mov     rcx, gs:60h
0x1400240f9  mov     r8, r14; P
0x1400240fc  xor     edx, edx; Flags
0x1400240fe  mov     rcx, [rcx+30h]; HeapHandle
0x140024102  call    cs:__imp_RtlFreeHeap
0x140024108  test    rdi, rdi
0x14002410b  jz      short loc_140024125
0x14002410d  mov     rcx, gs:60h
0x140024116  mov     r8, rdi; P
0x140024119  xor     edx, edx; Flags
0x14002411b  mov     rcx, [rcx+30h]; HeapHandle
0x14002411f  call    cs:__imp_RtlFreeHeap
0x140024125  test    rsi, rsi
0x140024128  jz      short loc_140024142
0x14002412a  mov     rcx, gs:60h
0x140024133  mov     r8, rsi; P
0x140024136  xor     edx, edx; Flags
0x140024138  mov     rcx, [rcx+30h]; HeapHandle
0x14002413c  call    cs:__imp_RtlFreeHeap
0x140024142  mov     eax, ebx
0x140024144  mov     rbx, [rsp+58h+arg_10]
0x140024149  add     rsp, 20h
0x14002414d  pop     r15
0x14002414f  pop     r14
0x140024151  pop     r13
0x140024153  pop     r12
0x140024155  pop     rdi
0x140024156  pop     rsi
0x140024157  pop     rbp
0x140024158  retn
```
