# AiConvertToTokenAttributes

- ea: `0x180006d90`
- end: `0x180006f02`
- name: `AiConvertToTokenAttributes`
- size: `370`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002a80`
- `0x180006a70`

## callees

- `0x180003fd4`
- `0x180006d90`
- `0x180009562`
- `0x18000957a`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006e1b`
- `ntdll!RtlFreeHeap` at `0x180006e33`
- `ntdll!RtlFreeHeap` at `0x180006e1b`
- `ntdll!RtlFreeHeap` at `0x180006e33`
- `ntdll!RtlUpcaseUnicodeString` at `0x180006e9f`
- `ntdll!RtlUpcaseUnicodeString` at `0x180006e9f`
- `ntdll!RtlAllocateHeap` at `0x180006dbf`
- `ntdll!RtlAllocateHeap` at `0x180006dbf`

## pseudocode

```c
__int64 __fastcall AiConvertToTokenAttributes(const void **a1, const void **a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  char *Heap; // rax
  char *v9; // rdi
  unsigned int v10; // esi
  unsigned int v11; // ebx
  char *v12; // rax
  char *v13; // rbp
  __int64 v14; // rax
  char *v15; // rbx
  __int64 v16; // rcx

  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x50u);
  v9 = Heap;
  if ( !Heap )
  {
LABEL_5:
    v11 = -1073741801;
    goto LABEL_6;
  }
  memset_0(Heap, 0, 0x50u);
  v10 = *(unsigned __int16 *)a1 + *(unsigned __int16 *)a2 + 12;
  if ( v10 <= 0xFFFF )
  {
    v12 = (char *)AiAlloc(v10);
    v13 = v12;
    if ( v12 )
    {
      memcpy_0(v12, a1[1], *(unsigned __int16 *)a1);
      v14 = *(unsigned __int16 *)a1;
      *(_WORD *)&v13[v14] = 92;
      v15 = &v13[v14];
      memcpy_0(&v13[v14 + 2], a2[1], *(unsigned __int16 *)a2);
      v16 = *(unsigned __int16 *)a2;
      *(_WORD *)&v15[v16 + 2] = 92;
      *(_QWORD *)&v15[v16 + 4] = 0x58005000500041LL;
      *((_WORD *)v9 + 4) = v10;
      *((_WORD *)v9 + 5) = v10;
      *((_QWORD *)v9 + 2) = v13;
      *(_QWORD *)v9 = a4;
      RtlUpcaseUnicodeString((PUNICODE_STRING)(v9 + 8), (PCUNICODE_STRING)(v9 + 8), 0);
      *((_WORD *)v9 + 20) = 4;
      *(_OWORD *)(v9 + 24) = *(_OWORD *)&qword_18000B0C8;
      *((_DWORD *)v9 + 12) = 1;
      *((_QWORD *)v9 + 7) = v9;
      v11 = 0;
      *((_DWORD *)v9 + 11) = 2;
      *((_WORD *)v9 + 33) = 0;
      *((_WORD *)v9 + 32) = 1;
      *((_DWORD *)v9 + 17) = 1;
      *((_QWORD *)v9 + 9) = v9 + 24;
      *a5 = v9 + 64;
      return v11;
    }
    goto LABEL_5;
  }
  v11 = -1073741675;
LABEL_6:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, 0);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  return v11;
}

```

## disassembly

```asm
0x180006d90  push    rbx
0x180006d92  push    rbp
0x180006d93  push    rsi
0x180006d94  push    rdi
0x180006d95  push    r12
0x180006d97  push    r14
0x180006d99  push    r15
0x180006d9b  sub     rsp, 20h
0x180006d9f  mov     rbx, rcx
0x180006da2  mov     r14, rdx
0x180006da5  mov     rcx, gs:60h
0x180006dae  mov     esi, 50h ; 'P'
0x180006db3  mov     r8d, esi; Size
0x180006db6  xor     edx, edx; Flags
0x180006db8  mov     r15, r9
0x180006dbb  mov     rcx, [rcx+30h]; HeapHandle
0x180006dbf  call    cs:__imp_RtlAllocateHeap
0x180006dc5  mov     rdi, rax
0x180006dc8  test    rax, rax
0x180006dcb  jz      short loc_180006E04
0x180006dcd  mov     r8d, esi; Size
0x180006dd0  xor     edx, edx; Val
0x180006dd2  mov     rcx, rax; void *
0x180006dd5  call    memset_0
0x180006dda  movzx   esi, word ptr [r14]
0x180006dde  movzx   ecx, word ptr [rbx]
0x180006de1  add     esi, 0Ch
0x180006de4  add     esi, ecx
0x180006de6  cmp     esi, 0FFFFh
0x180006dec  jbe     short loc_180006DF5
0x180006dee  mov     ebx, 0C0000095h
0x180006df3  jmp     short loc_180006E09
0x180006df5  mov     ecx, esi
0x180006df7  call    AiAlloc
0x180006dfc  mov     rbp, rax
0x180006dff  test    rax, rax
0x180006e02  jnz     short loc_180006E3E
0x180006e04  mov     ebx, 0C0000017h
0x180006e09  mov     rcx, gs:60h
0x180006e12  xor     r8d, r8d; P
0x180006e15  xor     edx, edx; Flags
0x180006e17  mov     rcx, [rcx+30h]; HeapHandle
0x180006e1b  call    cs:__imp_RtlFreeHeap
0x180006e21  mov     rcx, gs:60h
0x180006e2a  mov     r8, rdi; P
0x180006e2d  xor     edx, edx; Flags
0x180006e2f  mov     rcx, [rcx+30h]; HeapHandle
0x180006e33  call    cs:__imp_RtlFreeHeap
0x180006e39  jmp     loc_180006EF1
0x180006e3e  movzx   r8d, word ptr [rbx]; Size
0x180006e42  mov     rcx, rbp; void *
0x180006e45  mov     rdx, [rbx+8]; Src
0x180006e49  call    memcpy_0
0x180006e4e  movzx   eax, word ptr [rbx]
0x180006e51  mov     r12d, 5Ch ; '\'
0x180006e57  mov     [rax+rbp], r12w
0x180006e5c  lea     rbx, [rax+rbp]
0x180006e60  movzx   r8d, word ptr [r14]; Size
0x180006e64  lea     rcx, [rbx+2]; void *
0x180006e68  mov     rdx, [r14+8]; Src
0x180006e6c  call    memcpy_0
0x180006e71  movzx   ecx, word ptr [r14]
0x180006e75  xor     r8d, r8d; AllocateDestinationString
0x180006e78  mov     [rcx+rbx+2], r12w
0x180006e7e  mov     rax, cs:qword_18000C238
0x180006e85  mov     [rcx+rbx+4], rax
0x180006e8a  lea     rcx, [rdi+8]; DestinationString
0x180006e8e  mov     rdx, rcx; SourceString
0x180006e91  mov     [rcx], si
0x180006e94  mov     [rdi+0Ah], si
0x180006e98  mov     [rdi+10h], rbp
0x180006e9c  mov     [rdi], r15
0x180006e9f  call    cs:__imp_RtlUpcaseUnicodeString
0x180006ea5  movups  xmm0, xmmword ptr cs:qword_18000B0C8
0x180006eac  lea     rdx, [rdi+18h]
0x180006eb0  xor     eax, eax
0x180006eb2  mov     word ptr [rdx+10h], 4
0x180006eb8  lea     r8d, [r12-5Bh]
0x180006ebd  movdqu  xmmword ptr [rdx], xmm0
0x180006ec1  mov     [rdx+18h], r8d
0x180006ec5  lea     rcx, [rdi+40h]
0x180006ec9  mov     [rdx+20h], rdi
0x180006ecd  xor     ebx, ebx
0x180006ecf  mov     dword ptr [rdx+14h], 2
0x180006ed6  mov     [rdi+42h], ax
0x180006eda  mov     rax, [rsp+58h+arg_20]
0x180006ee2  mov     [rcx], r8w
0x180006ee6  mov     [rdi+44h], r8d
0x180006eea  mov     [rdi+48h], rdx
0x180006eee  mov     [rax], rcx
0x180006ef1  mov     eax, ebx
0x180006ef3  add     rsp, 20h
0x180006ef7  pop     r15
0x180006ef9  pop     r14
0x180006efb  pop     r12
0x180006efd  pop     rdi
0x180006efe  pop     rsi
0x180006eff  pop     rbp
0x180006f00  pop     rbx
0x180006f01  retn
```
