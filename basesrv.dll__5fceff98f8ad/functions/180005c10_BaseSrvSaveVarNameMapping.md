# BaseSrvSaveVarNameMapping

- ea: `0x180005c10`
- end: `0x180005ebf`
- name: `BaseSrvSaveVarNameMapping`
- size: `687`
- prototype: `__int64 __fastcall(__int64, __int64, const UNICODE_STRING *, const wchar_t *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004d70`

## callees

- `0x180005c10`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180005c67`
- `ntdll!RtlAllocateHeap` at `0x180005db1`
- `ntdll!RtlAllocateHeap` at `0x180005c67`
- `ntdll!RtlAllocateHeap` at `0x180005db1`
- `ntdll!RtlFreeHeap` at `0x180005dd6`
- `ntdll!RtlFreeHeap` at `0x180005dd6`
- `ntdll!_wcsnicmp` at `0x180005d0c`
- `ntdll!_wcsnicmp` at `0x180005e83`
- `ntdll!_wcsnicmp` at `0x180005d0c`
- `ntdll!_wcsnicmp` at `0x180005e83`
- `ntdll!RtlCopyUnicodeString` at `0x180005e10`
- `ntdll!RtlCopyUnicodeString` at `0x180005e41`
- `ntdll!RtlCopyUnicodeString` at `0x180005e10`
- `ntdll!RtlCopyUnicodeString` at `0x180005e41`
- `ntdll!RtlEqualUnicodeString` at `0x180005d78`
- `ntdll!RtlEqualUnicodeString` at `0x180005d78`
- `ntdll!RtlInitUnicodeString` at `0x180005d51`
- `ntdll!RtlInitUnicodeString` at `0x180005d51`

## pseudocode

```c
__int64 __fastcall BaseSrvSaveVarNameMapping(
        __int64 a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        const wchar_t *a4,
        _QWORD *a5)
{
  _QWORD *v7; // rax
  _QWORD *i; // r14
  char *Heap; // rbp
  int v11; // r15d
  unsigned __int64 v12; // rax
  const WCHAR *v13; // rdx
  wchar_t v14; // cx
  int v15; // ecx
  __int64 *j; // rdi
  char *v17; // rbx
  char *v18; // rax
  unsigned int v19; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF

  if ( a3->Length )
  {
    v7 = *(_QWORD **)(a2 + 24);
    for ( i = (_QWORD *)(a2 + 24); v7; v7 = (_QWORD *)*v7 )
      i = v7;
  }
  else
  {
    i = (_QWORD *)(a2 + 32);
  }
  Heap = (char *)RtlAllocateHeap(BaseSrvSharedHeap, (BaseSrvSharedTag + 0x40000) | 8, a3->MaximumLength + 40LL);
  if ( !Heap )
    return 3221225495LL;
  DestinationString = 0;
  v11 = 0;
  v12 = -1;
  do
    ++v12;
  while ( a4[v12] );
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v12 )
        goto LABEL_11;
      v14 = *a4;
      if ( *a4 != 33 )
        break;
      ++a4;
      --v12;
      v11 |= 1u;
    }
    if ( v14 == 35 )
    {
      v15 = 2;
      goto LABEL_23;
    }
    if ( v14 != 64 )
      break;
    v15 = 4;
LABEL_23:
    ++a4;
    --v12;
    v11 |= v15;
  }
  if ( v12 < 4 )
    goto LABEL_11;
  if ( !_wcsnicmp(a4, L"USR:", 4u) )
  {
    v11 |= 0x80000000;
LABEL_21:
    a4 += 4;
    goto LABEL_11;
  }
  if ( !_wcsnicmp(a4, L"SYS:", 4u) )
  {
    v11 |= 0x40000000u;
    goto LABEL_21;
  }
LABEL_11:
  if ( (v11 & 0xC0000000) != 0 )
  {
    if ( *a4 == 92 )
    {
LABEL_42:
      v19 = -1073741773;
LABEL_32:
      RtlFreeHeap(BaseSrvSharedHeap, 0, Heap);
      return v19;
    }
LABEL_25:
    v13 = a4;
    goto LABEL_26;
  }
  if ( *a4 == 92 )
    goto LABEL_25;
  if ( *a4 )
    goto LABEL_42;
  v13 = 0;
LABEL_26:
  RtlInitUnicodeString(&DestinationString, v13);
  for ( j = &BaseSrvMappingTargetHead; ; j = (__int64 *)v17 )
  {
    v17 = (char *)*j;
    if ( !*j )
      break;
    if ( RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)(v17 + 8), 1u) )
      goto LABEL_35;
  }
  v18 = (char *)RtlAllocateHeap(
                  BaseSrvSharedHeap,
                  (BaseSrvSharedTag + 0x40000) | 8,
                  DestinationString.MaximumLength + 24LL);
  v17 = v18;
  if ( !v18 )
  {
    v19 = -1073741801;
    goto LABEL_32;
  }
  *j = (__int64)v18;
  if ( DestinationString.Length )
  {
    *((_QWORD *)v18 + 2) = v18 + 24;
    *((_WORD *)v18 + 4) = 0;
    *((_WORD *)v18 + 5) = DestinationString.MaximumLength;
    RtlCopyUnicodeString((PUNICODE_STRING)(v18 + 8), &DestinationString);
  }
LABEL_35:
  *((_DWORD *)Heap + 6) = v11;
  *((_QWORD *)Heap + 4) = v17;
  if ( a3->Length )
  {
    *((_QWORD *)Heap + 2) = Heap + 40;
    *((_WORD *)Heap + 5) = a3->MaximumLength;
    RtlCopyUnicodeString((PUNICODE_STRING)(Heap + 8), a3);
  }
  *i = Heap;
  *a5 = Heap;
  return 0;
}

```

## disassembly

```asm
0x180005c10  mov     [rsp+arg_10], rbx
0x180005c15  push    rbp
0x180005c16  push    rsi
0x180005c17  push    r14
0x180005c19  sub     rsp, 30h
0x180005c1d  cmp     word ptr [r8], 0
0x180005c22  mov     rbx, r9
0x180005c25  mov     rsi, r8
0x180005c28  jz      short loc_180005C44
0x180005c2a  mov     rax, [rdx+18h]
0x180005c2e  lea     r14, [rdx+18h]
0x180005c32  test    rax, rax
0x180005c35  jz      short loc_180005C48
0x180005c37  mov     r14, rax
0x180005c3a  mov     rax, [rax]
0x180005c3d  test    rax, rax
0x180005c40  jnz     short loc_180005C37
0x180005c42  jmp     short loc_180005C48
0x180005c44  lea     r14, [rdx+20h]
0x180005c48  mov     edx, cs:BaseSrvSharedTag
0x180005c4e  movzx   r8d, word ptr [r8+2]
0x180005c53  add     edx, 40000h
0x180005c59  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180005c60  or      edx, 8; Flags
0x180005c63  add     r8, 28h ; '('; Size
0x180005c67  call    cs:__imp_RtlAllocateHeap
0x180005c6e  nop     dword ptr [rax+rax+00h]
0x180005c73  mov     rbp, rax
0x180005c76  test    rax, rax
0x180005c79  jnz     short loc_180005C8F
0x180005c7b  mov     eax, 0C0000017h
0x180005c80  mov     rbx, [rsp+48h+arg_10]
0x180005c85  add     rsp, 30h
0x180005c89  pop     r14
0x180005c8b  pop     rsi
0x180005c8c  pop     rbp
0x180005c8d  retn
0x180005c8f  xorps   xmm0, xmm0
0x180005c92  mov     [rsp+48h+arg_8], r15
0x180005c97  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x180005c9c  xor     r15d, r15d
0x180005c9f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005ca6  inc     rax
0x180005ca9  cmp     [rbx+rax*2], r15w
0x180005cae  jnz     short loc_180005CA6
0x180005cb0  test    rax, rax
0x180005cb3  jnz     short loc_180005CD9
0x180005cb5  mov     [rsp+48h+arg_0], rdi
0x180005cba  test    r15d, 0C0000000h
0x180005cc1  jnz     short loc_180005D3F
0x180005cc3  movzx   eax, word ptr [rbx]
0x180005cc6  cmp     ax, 5Ch ; '\'
0x180005cca  jz      short loc_180005D49
0x180005ccc  test    ax, ax
0x180005ccf  jnz     loc_180005EB5
0x180005cd5  xor     edx, edx
0x180005cd7  jmp     short loc_180005D4C
0x180005cd9  movzx   ecx, word ptr [rbx]
0x180005cdc  cmp     cx, 21h ; '!'
0x180005ce0  jz      loc_180005EA1
0x180005ce6  cmp     cx, 23h ; '#'
0x180005cea  jz      short loc_180005D2B
0x180005cec  cmp     cx, 40h ; '@'
0x180005cf0  jz      loc_180005E69
0x180005cf6  cmp     rax, 4
0x180005cfa  jb      short loc_180005CB5
0x180005cfc  mov     r8d, 4; MaxCount
0x180005d02  lea     rdx, aUsr; "USR:"
0x180005d09  mov     rcx, rbx; String1
0x180005d0c  call    cs:__imp__wcsnicmp
0x180005d13  nop     dword ptr [rax+rax+00h]
0x180005d18  test    eax, eax
0x180005d1a  jnz     loc_180005E73
0x180005d20  bts     r15d, 1Fh
0x180005d25  add     rbx, 8
0x180005d29  jmp     short loc_180005CB5
0x180005d2b  mov     ecx, 2
0x180005d30  add     rbx, 2
0x180005d34  dec     rax
0x180005d37  or      r15d, ecx
0x180005d3a  jmp     loc_180005CB0
0x180005d3f  cmp     word ptr [rbx], 5Ch ; '\'
0x180005d43  jz      loc_180005EB5
0x180005d49  mov     rdx, rbx; SourceString
0x180005d4c  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180005d51  call    cs:__imp_RtlInitUnicodeString
0x180005d58  nop     dword ptr [rax+rax+00h]
0x180005d5d  lea     rdi, BaseSrvMappingTargetHead
0x180005d64  mov     rbx, [rdi]
0x180005d67  test    rbx, rbx
0x180005d6a  jz      short loc_180005D91
0x180005d6c  lea     rdx, [rbx+8]; String2
0x180005d70  mov     r8b, 1; CaseInsensitive
0x180005d73  lea     rcx, [rsp+48h+DestinationString]; String1
0x180005d78  call    cs:__imp_RtlEqualUnicodeString
0x180005d7f  nop     dword ptr [rax+rax+00h]
0x180005d84  test    al, al
0x180005d86  jnz     loc_180005E1C
0x180005d8c  mov     rdi, rbx
0x180005d8f  jmp     short loc_180005D64
0x180005d91  mov     edx, cs:BaseSrvSharedTag
0x180005d97  movzx   r8d, [rsp+48h+DestinationString.MaximumLength]
0x180005d9d  add     edx, 40000h
0x180005da3  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180005daa  or      edx, 8; Flags
0x180005dad  add     r8, 18h; Size
0x180005db1  call    cs:__imp_RtlAllocateHeap
0x180005db8  nop     dword ptr [rax+rax+00h]
0x180005dbd  mov     rbx, rax
0x180005dc0  test    rax, rax
0x180005dc3  jnz     short loc_180005DE6
0x180005dc5  mov     ebx, 0C0000017h
0x180005dca  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180005dd1  mov     r8, rbp; P
0x180005dd4  xor     edx, edx; Flags
0x180005dd6  call    cs:__imp_RtlFreeHeap
0x180005ddd  nop     dword ptr [rax+rax+00h]
0x180005de2  mov     eax, ebx
0x180005de4  jmp     short loc_180005E5A
0x180005de6  mov     [rdi], rbx
0x180005de9  cmp     [rsp+48h+DestinationString.Length], 0
0x180005def  jz      short loc_180005E1C
0x180005df1  add     rax, 18h
0x180005df5  lea     rcx, [rbx+8]; DestinationString
0x180005df9  mov     [rbx+10h], rax
0x180005dfd  lea     rdx, [rsp+48h+DestinationString]; SourceString
0x180005e02  xor     eax, eax
0x180005e04  mov     [rcx], ax
0x180005e07  movzx   eax, [rsp+48h+DestinationString.MaximumLength]
0x180005e0c  mov     [rbx+0Ah], ax
0x180005e10  call    cs:__imp_RtlCopyUnicodeString
0x180005e17  nop     dword ptr [rax+rax+00h]
0x180005e1c  mov     [rbp+18h], r15d
0x180005e20  mov     [rbp+20h], rbx
0x180005e24  cmp     word ptr [rsi], 0
0x180005e28  jz      short loc_180005E4D
0x180005e2a  lea     rax, [rbp+28h]
0x180005e2e  mov     rdx, rsi; SourceString
0x180005e31  mov     [rbp+10h], rax
0x180005e35  lea     rcx, [rbp+8]; DestinationString
0x180005e39  movzx   eax, word ptr [rsi+2]
0x180005e3d  mov     [rbp+0Ah], ax
0x180005e41  call    cs:__imp_RtlCopyUnicodeString
0x180005e48  nop     dword ptr [rax+rax+00h]
0x180005e4d  mov     rax, [rsp+48h+arg_20]
0x180005e52  mov     [r14], rbp
0x180005e55  mov     [rax], rbp
0x180005e58  xor     eax, eax
0x180005e5a  mov     rdi, [rsp+48h+arg_0]
0x180005e5f  mov     r15, [rsp+48h+arg_8]
0x180005e64  jmp     loc_180005C80
0x180005e69  mov     ecx, 4
0x180005e6e  jmp     loc_180005D30
0x180005e73  mov     r8d, 4; MaxCount
0x180005e79  lea     rdx, aSys; "SYS:"
0x180005e80  mov     rcx, rbx; String1
0x180005e83  call    cs:__imp__wcsnicmp
0x180005e8a  nop     dword ptr [rax+rax+00h]
0x180005e8f  test    eax, eax
0x180005e91  jnz     loc_180005CB5
0x180005e97  bts     r15d, 1Eh
0x180005e9c  jmp     loc_180005D25
0x180005ea1  mov     ecx, 1
0x180005ea6  add     rbx, 2
0x180005eaa  dec     rax
0x180005ead  or      r15d, ecx
0x180005eb0  jmp     loc_180005CB0
0x180005eb5  mov     ebx, 0C0000033h
0x180005eba  jmp     loc_180005DCA
```
