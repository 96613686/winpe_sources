# BaseSrvSaveVarNameMapping

- ea: `0x1800056e0`
- end: `0x1800059a0`
- name: `BaseSrvSaveVarNameMapping`
- size: `704`
- prototype: `__int64 __fastcall(__int64, __int64, const UNICODE_STRING *, const wchar_t *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004d80`
- `0x180005210`

## callees

- `0x1800056e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180005737`
- `ntdll!RtlAllocateHeap` at `0x18000588d`
- `ntdll!RtlAllocateHeap` at `0x180005737`
- `ntdll!RtlAllocateHeap` at `0x18000588d`
- `ntdll!RtlFreeHeap` at `0x1800058b2`
- `ntdll!RtlFreeHeap` at `0x1800058b2`
- `ntdll!_wcsnicmp` at `0x1800057e6`
- `ntdll!_wcsnicmp` at `0x180005964`
- `ntdll!_wcsnicmp` at `0x1800057e6`
- `ntdll!_wcsnicmp` at `0x180005964`
- `ntdll!RtlCopyUnicodeString` at `0x1800058ec`
- `ntdll!RtlCopyUnicodeString` at `0x18000591d`
- `ntdll!RtlCopyUnicodeString` at `0x1800058ec`
- `ntdll!RtlCopyUnicodeString` at `0x18000591d`
- `ntdll!RtlEqualUnicodeString` at `0x180005854`
- `ntdll!RtlEqualUnicodeString` at `0x180005854`
- `ntdll!RtlInitUnicodeString` at `0x18000582b`
- `ntdll!RtlInitUnicodeString` at `0x18000582b`

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
  v11 = 0;
  v12 = -1;
  DestinationString = 0;
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
  for ( j = BaseSrvMappingTargetHead; ; j = (__int64 *)v17 )
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
    *((_WORD *)v18 + 4) = 0;
    *((_QWORD *)v18 + 2) = v18 + 24;
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
0x1800056e0  mov     [rsp+arg_18], rbx
0x1800056e5  push    rbp
0x1800056e6  push    rsi
0x1800056e7  push    r14
0x1800056e9  sub     rsp, 30h
0x1800056ed  cmp     word ptr [r8], 0
0x1800056f2  mov     rbx, r9
0x1800056f5  mov     rsi, r8
0x1800056f8  jz      short loc_180005714
0x1800056fa  mov     rax, [rdx+18h]
0x1800056fe  lea     r14, [rdx+18h]
0x180005702  test    rax, rax
0x180005705  jz      short loc_180005718
0x180005707  mov     r14, rax
0x18000570a  mov     rax, [rax]
0x18000570d  test    rax, rax
0x180005710  jnz     short loc_180005707
0x180005712  jmp     short loc_180005718
0x180005714  lea     r14, [rdx+20h]
0x180005718  mov     edx, cs:BaseSrvSharedTag
0x18000571e  movzx   r8d, word ptr [r8+2]
0x180005723  add     edx, 40000h
0x180005729  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180005730  or      edx, 8; Flags
0x180005733  add     r8, 28h ; '('; Size
0x180005737  call    cs:__imp_RtlAllocateHeap
0x18000573e  nop     dword ptr [rax+rax+00h]
0x180005743  mov     rbp, rax
0x180005746  test    rax, rax
0x180005749  jnz     short loc_18000575F
0x18000574b  mov     eax, 0C0000017h
0x180005750  mov     rbx, [rsp+48h+arg_18]
0x180005755  add     rsp, 30h
0x180005759  pop     r14
0x18000575b  pop     rsi
0x18000575c  pop     rbp
0x18000575d  retn
0x18000575f  mov     [rsp+48h+arg_8], r12
0x180005764  xorps   xmm0, xmm0
0x180005767  xor     r12d, r12d
0x18000576a  mov     [rsp+48h+arg_10], r15
0x18000576f  mov     r15d, r12d
0x180005772  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005779  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18000577e  xchg    ax, ax
0x180005780  inc     rax
0x180005783  cmp     [rbx+rax*2], r12w
0x180005788  jnz     short loc_180005780
0x18000578a  test    rax, rax
0x18000578d  jnz     short loc_1800057B3
0x18000578f  mov     [rsp+48h+arg_0], rdi
0x180005794  test    r15d, 0C0000000h
0x18000579b  jnz     short loc_180005819
0x18000579d  movzx   eax, word ptr [rbx]
0x1800057a0  cmp     ax, 5Ch ; '\'
0x1800057a4  jz      short loc_180005823
0x1800057a6  test    ax, ax
0x1800057a9  jnz     loc_180005996
0x1800057af  xor     edx, edx
0x1800057b1  jmp     short loc_180005826
0x1800057b3  movzx   ecx, word ptr [rbx]
0x1800057b6  cmp     cx, 21h ; '!'
0x1800057ba  jz      loc_180005982
0x1800057c0  cmp     cx, 23h ; '#'
0x1800057c4  jz      short loc_180005805
0x1800057c6  cmp     cx, 40h ; '@'
0x1800057ca  jz      loc_18000594A
0x1800057d0  cmp     rax, 4
0x1800057d4  jb      short loc_18000578F
0x1800057d6  mov     r8d, 4; MaxCount
0x1800057dc  lea     rdx, aUsr; "USR:"
0x1800057e3  mov     rcx, rbx; String1
0x1800057e6  call    cs:__imp__wcsnicmp
0x1800057ed  nop     dword ptr [rax+rax+00h]
0x1800057f2  test    eax, eax
0x1800057f4  jnz     loc_180005954
0x1800057fa  bts     r15d, 1Fh
0x1800057ff  add     rbx, 8
0x180005803  jmp     short loc_18000578F
0x180005805  mov     ecx, 2
0x18000580a  add     rbx, 2
0x18000580e  dec     rax
0x180005811  or      r15d, ecx
0x180005814  jmp     loc_18000578A
0x180005819  cmp     word ptr [rbx], 5Ch ; '\'
0x18000581d  jz      loc_180005996
0x180005823  mov     rdx, rbx; SourceString
0x180005826  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18000582b  call    cs:__imp_RtlInitUnicodeString
0x180005832  nop     dword ptr [rax+rax+00h]
0x180005837  lea     rdi, BaseSrvMappingTargetHead
0x18000583e  xchg    ax, ax
0x180005840  mov     rbx, [rdi]
0x180005843  test    rbx, rbx
0x180005846  jz      short loc_18000586D
0x180005848  lea     rdx, [rbx+8]; String2
0x18000584c  mov     r8b, 1; CaseInsensitive
0x18000584f  lea     rcx, [rsp+48h+DestinationString]; String1
0x180005854  call    cs:__imp_RtlEqualUnicodeString
0x18000585b  nop     dword ptr [rax+rax+00h]
0x180005860  test    al, al
0x180005862  jnz     loc_1800058F8
0x180005868  mov     rdi, rbx
0x18000586b  jmp     short loc_180005840
0x18000586d  mov     edx, cs:BaseSrvSharedTag
0x180005873  movzx   r8d, [rsp+48h+DestinationString.MaximumLength]
0x180005879  add     edx, 40000h
0x18000587f  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180005886  or      edx, 8; Flags
0x180005889  add     r8, 18h; Size
0x18000588d  call    cs:__imp_RtlAllocateHeap
0x180005894  nop     dword ptr [rax+rax+00h]
0x180005899  mov     rbx, rax
0x18000589c  test    rax, rax
0x18000589f  jnz     short loc_1800058C2
0x1800058a1  mov     ebx, 0C0000017h
0x1800058a6  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x1800058ad  mov     r8, rbp; P
0x1800058b0  xor     edx, edx; Flags
0x1800058b2  call    cs:__imp_RtlFreeHeap
0x1800058b9  nop     dword ptr [rax+rax+00h]
0x1800058be  mov     eax, ebx
0x1800058c0  jmp     short loc_180005936
0x1800058c2  mov     [rdi], rbx
0x1800058c5  cmp     [rsp+48h+DestinationString.Length], r12w
0x1800058cb  jz      short loc_1800058F8
0x1800058cd  add     rax, 18h
0x1800058d1  mov     [rbx+8], r12w
0x1800058d6  lea     rcx, [rbx+8]; DestinationString
0x1800058da  mov     [rbx+10h], rax
0x1800058de  movzx   eax, [rsp+48h+DestinationString.MaximumLength]
0x1800058e3  lea     rdx, [rsp+48h+DestinationString]; SourceString
0x1800058e8  mov     [rbx+0Ah], ax
0x1800058ec  call    cs:__imp_RtlCopyUnicodeString
0x1800058f3  nop     dword ptr [rax+rax+00h]
0x1800058f8  mov     [rbp+18h], r15d
0x1800058fc  mov     [rbp+20h], rbx
0x180005900  cmp     [rsi], r12w
0x180005904  jz      short loc_180005929
0x180005906  lea     rax, [rbp+28h]
0x18000590a  mov     rdx, rsi; SourceString
0x18000590d  mov     [rbp+10h], rax
0x180005911  lea     rcx, [rbp+8]; DestinationString
0x180005915  movzx   eax, word ptr [rsi+2]
0x180005919  mov     [rbp+0Ah], ax
0x18000591d  call    cs:__imp_RtlCopyUnicodeString
0x180005924  nop     dword ptr [rax+rax+00h]
0x180005929  mov     rax, [rsp+48h+arg_20]
0x18000592e  mov     [r14], rbp
0x180005931  mov     [rax], rbp
0x180005934  xor     eax, eax
0x180005936  mov     rdi, [rsp+48h+arg_0]
0x18000593b  mov     r12, [rsp+48h+arg_8]
0x180005940  mov     r15, [rsp+48h+arg_10]
0x180005945  jmp     loc_180005750
0x18000594a  mov     ecx, 4
0x18000594f  jmp     loc_18000580A
0x180005954  mov     r8d, 4; MaxCount
0x18000595a  lea     rdx, aSys; "SYS:"
0x180005961  mov     rcx, rbx; String1
0x180005964  call    cs:__imp__wcsnicmp
0x18000596b  nop     dword ptr [rax+rax+00h]
0x180005970  test    eax, eax
0x180005972  jnz     loc_18000578F
0x180005978  bts     r15d, 1Eh
0x18000597d  jmp     loc_1800057FF
0x180005982  mov     ecx, 1
0x180005987  add     rbx, 2
0x18000598b  dec     rax
0x18000598e  or      r15d, ecx
0x180005991  jmp     loc_18000578A
0x180005996  mov     ebx, 0C0000033h
0x18000599b  jmp     loc_1800058A6
```
