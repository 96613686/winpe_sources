# AiAddImagePathWithMacro

- ea: `0x180005b70`
- end: `0x180005cf3`
- name: `AiAddImagePathWithMacro`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000423c`

## callees

- `0x180003fd4`
- `0x180005b70`
- `0x180009562`
- `0x18000956e`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180005c95`
- `ntdll!RtlEqualUnicodeString` at `0x180005c95`
- `ntdll!RtlFreeHeap` at `0x180005c0a`
- `ntdll!RtlFreeHeap` at `0x180005cbe`
- `ntdll!RtlFreeHeap` at `0x180005c0a`
- `ntdll!RtlFreeHeap` at `0x180005cbe`
- `ntdll!RtlUpcaseUnicodeString` at `0x180005b9c`
- `ntdll!RtlUpcaseUnicodeString` at `0x180005b9c`

## pseudocode

```c
__int64 __fastcall AiAddImagePathWithMacro(__int64 a1, UNICODE_STRING *a2)
{
  __int64 v5; // rax
  unsigned __int64 v6; // rax
  int v7; // esi
  void *v8; // rax
  void *v9; // rdi
  void *v10; // r8
  unsigned int v11; // ecx
  PVOID *p_Buffer; // rdi
  unsigned int v13; // ebp
  __int64 v14; // rdx
  __int64 v15; // r8
  _WORD *v16; // r9
  __int64 v17; // rsi
  __int64 v18; // rsi
  const UNICODE_STRING *v19; // rdx

  if ( !a2->Length )
    return 3221225485LL;
  RtlUpcaseUnicodeString(a2, a2, 0);
  v5 = *(unsigned int *)(a1 + 96);
  if ( *(_DWORD *)(a1 + 92) == (_DWORD)v5 )
  {
    v6 = 2 * v5;
    if ( v6 > 0xFFFFFFFF )
      return 3221225621LL;
    v7 = v6;
    v8 = (void *)AiAlloc(16LL * (unsigned int)v6);
    v9 = v8;
    if ( !v8 )
      return 3221225495LL;
    memcpy_0(v8, *(const void **)(a1 + 104), 16LL * *(unsigned int *)(a1 + 92));
    v10 = *(void **)(a1 + 104);
    if ( v10 != (void *)(a1 + 112) )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    *(_DWORD *)(a1 + 96) = v7;
    *(_QWORD *)(a1 + 104) = v9;
  }
  v11 = *(_DWORD *)(a1 + 92);
  p_Buffer = (PVOID *)&a2->Buffer;
  if ( !v11 )
  {
    v17 = 0;
LABEL_24:
    v18 = 16 * v17;
    goto LABEL_25;
  }
  v13 = 0;
  while ( 1 )
  {
    v14 = *(_QWORD *)(a1 + 104);
    v15 = 16LL * v13;
    v16 = *(_WORD **)(v15 + v14 + 8);
    if ( *(_WORD *)*p_Buffer == 37 )
    {
      if ( *v16 != 37 )
        break;
    }
    else if ( *v16 == 37 )
    {
      goto LABEL_20;
    }
    v19 = (const UNICODE_STRING *)(v15 + v14);
    if ( v19->Length > a2->Length )
      break;
    if ( RtlEqualUnicodeString(a2, v19, 0) )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *p_Buffer);
      *p_Buffer = 0;
      return 0;
    }
LABEL_20:
    v11 = *(_DWORD *)(a1 + 92);
    if ( ++v13 >= v11 )
    {
      v17 = v13;
      goto LABEL_24;
    }
  }
  v17 = v13;
  if ( v13 >= v11 )
    goto LABEL_24;
  v18 = 16LL * v13;
  memmove_0(
    (void *)(*(_QWORD *)(a1 + 104) + 16LL * (v13 + 1)),
    (const void *)(*(_QWORD *)(a1 + 104) + v18),
    16LL * (v11 - v13));
LABEL_25:
  *(UNICODE_STRING *)(*(_QWORD *)(a1 + 104) + v18) = *a2;
  *p_Buffer = 0;
  ++*(_DWORD *)(a1 + 92);
  return 0;
}

```

## disassembly

```asm
0x180005b70  push    rbx
0x180005b72  push    rbp
0x180005b73  push    rsi
0x180005b74  push    rdi
0x180005b75  push    r14
0x180005b77  push    r15
0x180005b79  sub     rsp, 28h
0x180005b7d  xor     r15d, r15d
0x180005b80  mov     r14, rdx
0x180005b83  mov     rbx, rcx
0x180005b86  cmp     [rdx], r15w
0x180005b8a  jnz     short loc_180005B96
0x180005b8c  mov     eax, 0C000000Dh
0x180005b91  jmp     loc_180005CE6
0x180005b96  xor     r8d, r8d; AllocateDestinationString
0x180005b99  mov     rcx, r14; DestinationString
0x180005b9c  call    cs:__imp_RtlUpcaseUnicodeString
0x180005ba2  mov     eax, [rbx+60h]
0x180005ba5  cmp     [rbx+5Ch], eax
0x180005ba8  jnz     short loc_180005C17
0x180005baa  add     rax, rax
0x180005bad  mov     ecx, 0FFFFFFFFh
0x180005bb2  cmp     rax, rcx
0x180005bb5  ja      loc_180005C75
0x180005bbb  mov     ecx, eax
0x180005bbd  shl     rcx, 4
0x180005bc1  mov     esi, eax
0x180005bc3  call    AiAlloc
0x180005bc8  mov     rdi, rax
0x180005bcb  test    rax, rax
0x180005bce  jnz     short loc_180005BDA
0x180005bd0  mov     eax, 0C0000017h
0x180005bd5  jmp     loc_180005CE6
0x180005bda  mov     r8d, [rbx+5Ch]
0x180005bde  mov     rcx, rdi; void *
0x180005be1  mov     rdx, [rbx+68h]; Src
0x180005be5  shl     r8, 4; Size
0x180005be9  call    memcpy_0
0x180005bee  mov     r8, [rbx+68h]; P
0x180005bf2  lea     rax, [rbx+70h]
0x180005bf6  cmp     r8, rax
0x180005bf9  jz      short loc_180005C10
0x180005bfb  mov     rcx, gs:60h
0x180005c04  xor     edx, edx; Flags
0x180005c06  mov     rcx, [rcx+30h]; HeapHandle
0x180005c0a  call    cs:__imp_RtlFreeHeap
0x180005c10  mov     [rbx+60h], esi
0x180005c13  mov     [rbx+68h], rdi
0x180005c17  mov     ecx, [rbx+5Ch]
0x180005c1a  lea     rdi, [r14+8]
0x180005c1e  test    ecx, ecx
0x180005c20  jz      loc_180005CC9
0x180005c26  mov     ebp, r15d
0x180005c29  mov     rax, [rdi]
0x180005c2c  mov     rdx, [rbx+68h]
0x180005c30  mov     r8d, ebp
0x180005c33  shl     r8, 4
0x180005c37  cmp     word ptr [rax], 25h ; '%'
0x180005c3b  mov     r9, [r8+rdx+8]
0x180005c40  jnz     short loc_180005C7C
0x180005c42  cmp     word ptr [r9], 25h ; '%'
0x180005c47  jz      short loc_180005C83
0x180005c49  mov     esi, ebp
0x180005c4b  cmp     ebp, ecx
0x180005c4d  jnb     short loc_180005CCC
0x180005c4f  mov     r9, [rbx+68h]
0x180005c53  sub     ecx, ebp
0x180005c55  mov     r8d, ecx
0x180005c58  lea     ecx, [rbp+1]
0x180005c5b  shl     rsi, 4
0x180005c5f  shl     rcx, 4
0x180005c63  add     rcx, r9; void *
0x180005c66  shl     r8, 4; Size
0x180005c6a  lea     rdx, [r9+rsi]; Src
0x180005c6e  call    memmove_0
0x180005c73  jmp     short loc_180005CD0
0x180005c75  mov     eax, 0C0000095h
0x180005c7a  jmp     short loc_180005CE6
0x180005c7c  cmp     word ptr [r9], 25h ; '%'
0x180005c81  jz      short loc_180005C9F
0x180005c83  movzx   eax, word ptr [r14]
0x180005c87  add     rdx, r8; String2
0x180005c8a  cmp     [rdx], ax
0x180005c8d  ja      short loc_180005C49
0x180005c8f  xor     r8d, r8d; CaseInsensitive
0x180005c92  mov     rcx, r14; String1
0x180005c95  call    cs:__imp_RtlEqualUnicodeString
0x180005c9b  test    al, al
0x180005c9d  jnz     short loc_180005CAC
0x180005c9f  mov     ecx, [rbx+5Ch]
0x180005ca2  inc     ebp
0x180005ca4  cmp     ebp, ecx
0x180005ca6  jb      short loc_180005C29
0x180005ca8  mov     esi, ebp
0x180005caa  jmp     short loc_180005CCC
0x180005cac  mov     rcx, gs:60h
0x180005cb5  xor     edx, edx; Flags
0x180005cb7  mov     r8, [rdi]; P
0x180005cba  mov     rcx, [rcx+30h]; HeapHandle
0x180005cbe  call    cs:__imp_RtlFreeHeap
0x180005cc4  mov     [rdi], r15
0x180005cc7  jmp     short loc_180005CE3
0x180005cc9  mov     rsi, r15
0x180005ccc  shl     rsi, 4
0x180005cd0  movups  xmm0, xmmword ptr [r14]
0x180005cd4  mov     rax, [rbx+68h]
0x180005cd8  movdqu  xmmword ptr [rax+rsi], xmm0
0x180005cdd  mov     [rdi], r15
0x180005ce0  inc     dword ptr [rbx+5Ch]
0x180005ce3  mov     eax, r15d
0x180005ce6  add     rsp, 28h
0x180005cea  pop     r15
0x180005cec  pop     r14
0x180005cee  pop     rdi
0x180005cef  pop     rsi
0x180005cf0  pop     rbp
0x180005cf1  pop     rbx
0x180005cf2  retn
```
