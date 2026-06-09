# BaseSrvSaveMappingTarget

- ea: `0x1800059b0`
- end: `0x180005bb3`
- name: `BaseSrvSaveMappingTarget`
- size: `515`
- prototype: `__int64 __fastcall(wchar_t *String1, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005210`

## callees

- `0x1800059b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180005ae9`
- `ntdll!RtlAllocateHeap` at `0x180005ae9`
- `ntdll!_wcsnicmp` at `0x180005a3f`
- `ntdll!_wcsnicmp` at `0x180005b79`
- `ntdll!_wcsnicmp` at `0x180005a3f`
- `ntdll!_wcsnicmp` at `0x180005b79`
- `ntdll!RtlCopyUnicodeString` at `0x180005b51`
- `ntdll!RtlCopyUnicodeString` at `0x180005b51`
- `ntdll!RtlEqualUnicodeString` at `0x180005ab4`
- `ntdll!RtlEqualUnicodeString` at `0x180005ab4`
- `ntdll!RtlInitUnicodeString` at `0x180005a82`
- `ntdll!RtlInitUnicodeString` at `0x180005a82`

## pseudocode

```c
__int64 __fastcall BaseSrvSaveMappingTarget(wchar_t *String1, _QWORD *a2, _DWORD *a3)
{
  int v3; // esi
  wchar_t *v6; // rbx
  unsigned __int64 v7; // rax
  const WCHAR *v8; // rdx
  wchar_t v9; // cx
  int v10; // ecx
  __int64 *i; // rdi
  char *v12; // rbx
  char *Heap; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF

  DestinationString = 0;
  v3 = 0;
  v6 = String1;
  v7 = -1;
  do
    ++v7;
  while ( String1[v7] );
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v7 )
        goto LABEL_4;
      v9 = *v6;
      if ( *v6 != 33 )
        break;
      --v7;
      ++v6;
      v3 |= 1u;
    }
    if ( v9 == 35 )
    {
      v10 = 2;
      goto LABEL_16;
    }
    if ( v9 != 64 )
      break;
    v10 = 4;
LABEL_16:
    --v7;
    ++v6;
    v3 |= v10;
  }
  if ( v7 < 4 )
    goto LABEL_4;
  if ( !_wcsnicmp(v6, L"USR:", 4u) )
  {
    v3 |= 0x80000000;
LABEL_14:
    v6 += 4;
    goto LABEL_4;
  }
  if ( !_wcsnicmp(v6, L"SYS:", 4u) )
  {
    v3 |= 0x40000000u;
    goto LABEL_14;
  }
LABEL_4:
  if ( (v3 & 0xC0000000) != 0 )
  {
    if ( *v6 == 92 )
      return 3221225523LL;
LABEL_18:
    v8 = v6;
    goto LABEL_19;
  }
  if ( *v6 == 92 )
    goto LABEL_18;
  if ( *v6 )
    return 3221225523LL;
  v8 = 0;
LABEL_19:
  RtlInitUnicodeString(&DestinationString, v8);
  for ( i = BaseSrvMappingTargetHead; ; i = (__int64 *)v12 )
  {
    v12 = (char *)*i;
    if ( !*i )
      break;
    if ( RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)(v12 + 8), 1u) )
    {
      *a3 = v3;
      goto LABEL_26;
    }
  }
  Heap = (char *)RtlAllocateHeap(
                   BaseSrvSharedHeap,
                   (BaseSrvSharedTag + 0x40000) | 8,
                   DestinationString.MaximumLength + 24LL);
  v12 = Heap;
  if ( !Heap )
    return 3221225495LL;
  *i = (__int64)Heap;
  *a3 = v3;
  if ( DestinationString.Length )
  {
    *((_WORD *)Heap + 4) = 0;
    *((_QWORD *)Heap + 2) = Heap + 24;
    *((_WORD *)Heap + 5) = DestinationString.MaximumLength;
    RtlCopyUnicodeString((PUNICODE_STRING)(Heap + 8), &DestinationString);
  }
LABEL_26:
  *a2 = v12;
  return 0;
}

```

## disassembly

```asm
0x1800059b0  mov     [rsp+arg_8], rbx
0x1800059b5  mov     [rsp+arg_10], rbp
0x1800059ba  push    rsi
0x1800059bb  push    r14
0x1800059bd  push    r15
0x1800059bf  sub     rsp, 30h
0x1800059c3  xorps   xmm0, xmm0
0x1800059c6  xor     ebp, ebp
0x1800059c8  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1800059cd  mov     esi, ebp
0x1800059cf  mov     r15, r8
0x1800059d2  mov     r14, rdx
0x1800059d5  mov     rbx, rcx
0x1800059d8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800059df  nop
0x1800059e0  inc     rax
0x1800059e3  cmp     [rcx+rax*2], si
0x1800059e7  jnz     short loc_1800059E0
0x1800059e9  test    rax, rax
0x1800059ec  jnz     short loc_180005A0C
0x1800059ee  test    esi, 0C0000000h
0x1800059f4  jnz     short loc_180005A70
0x1800059f6  movzx   eax, word ptr [rbx]
0x1800059f9  cmp     ax, 5Ch ; '\'
0x1800059fd  jz      short loc_180005A7A
0x1800059ff  test    ax, ax
0x180005a02  jnz     loc_180005BA9
0x180005a08  xor     edx, edx
0x180005a0a  jmp     short loc_180005A7D
0x180005a0c  movzx   ecx, word ptr [rbx]
0x180005a0f  cmp     cx, 21h ; '!'
0x180005a13  jz      loc_180005B96
0x180005a19  cmp     cx, 23h ; '#'
0x180005a1d  jz      short loc_180005A5D
0x180005a1f  cmp     cx, 40h ; '@'
0x180005a23  jz      loc_180005B5F
0x180005a29  cmp     rax, 4
0x180005a2d  jb      short loc_1800059EE
0x180005a2f  mov     r8d, 4; MaxCount
0x180005a35  lea     rdx, aUsr; "USR:"
0x180005a3c  mov     rcx, rbx; String1
0x180005a3f  call    cs:__imp__wcsnicmp
0x180005a46  nop     dword ptr [rax+rax+00h]
0x180005a4b  test    eax, eax
0x180005a4d  jnz     loc_180005B69
0x180005a53  bts     esi, 1Fh
0x180005a57  add     rbx, 8
0x180005a5b  jmp     short loc_1800059EE
0x180005a5d  mov     ecx, 2
0x180005a62  dec     rax
0x180005a65  add     rbx, 2
0x180005a69  or      esi, ecx
0x180005a6b  jmp     loc_1800059E9
0x180005a70  cmp     word ptr [rbx], 5Ch ; '\'
0x180005a74  jz      loc_180005BA9
0x180005a7a  mov     rdx, rbx; SourceString
0x180005a7d  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180005a82  call    cs:__imp_RtlInitUnicodeString
0x180005a89  nop     dword ptr [rax+rax+00h]
0x180005a8e  mov     [rsp+48h+arg_0], rdi
0x180005a93  lea     rdi, BaseSrvMappingTargetHead
0x180005a9a  nop     word ptr [rax+rax+00h]
0x180005aa0  mov     rbx, [rdi]
0x180005aa3  test    rbx, rbx
0x180005aa6  jz      short loc_180005AC9
0x180005aa8  lea     rdx, [rbx+8]; String2
0x180005aac  mov     r8b, 1; CaseInsensitive
0x180005aaf  lea     rcx, [rsp+48h+DestinationString]; String1
0x180005ab4  call    cs:__imp_RtlEqualUnicodeString
0x180005abb  nop     dword ptr [rax+rax+00h]
0x180005ac0  test    al, al
0x180005ac2  jnz     short loc_180005B04
0x180005ac4  mov     rdi, rbx
0x180005ac7  jmp     short loc_180005AA0
0x180005ac9  mov     edx, cs:BaseSrvSharedTag
0x180005acf  movzx   r8d, [rsp+48h+DestinationString.MaximumLength]
0x180005ad5  add     edx, 40000h
0x180005adb  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180005ae2  or      edx, 8; Flags
0x180005ae5  add     r8, 18h; Size
0x180005ae9  call    cs:__imp_RtlAllocateHeap
0x180005af0  nop     dword ptr [rax+rax+00h]
0x180005af5  mov     rbx, rax
0x180005af8  test    rax, rax
0x180005afb  jnz     short loc_180005B26
0x180005afd  mov     eax, 0C0000017h
0x180005b02  jmp     short loc_180005B0C
0x180005b04  mov     [r15], esi
0x180005b07  mov     [r14], rbx
0x180005b0a  xor     eax, eax
0x180005b0c  mov     rdi, [rsp+48h+arg_0]
0x180005b11  mov     rbx, [rsp+48h+arg_8]
0x180005b16  mov     rbp, [rsp+48h+arg_10]
0x180005b1b  add     rsp, 30h
0x180005b1f  pop     r15
0x180005b21  pop     r14
0x180005b23  pop     rsi
0x180005b24  retn
0x180005b26  mov     [rdi], rbx
0x180005b29  mov     [r15], esi
0x180005b2c  cmp     [rsp+48h+DestinationString.Length], bp
0x180005b31  jz      short loc_180005B07
0x180005b33  add     rax, 18h
0x180005b37  mov     [rbx+8], bp
0x180005b3b  lea     rcx, [rbx+8]; DestinationString
0x180005b3f  mov     [rbx+10h], rax
0x180005b43  movzx   eax, [rsp+48h+DestinationString.MaximumLength]
0x180005b48  lea     rdx, [rsp+48h+DestinationString]; SourceString
0x180005b4d  mov     [rbx+0Ah], ax
0x180005b51  call    cs:__imp_RtlCopyUnicodeString
0x180005b58  nop     dword ptr [rax+rax+00h]
0x180005b5d  jmp     short loc_180005B07
0x180005b5f  mov     ecx, 4
0x180005b64  jmp     loc_180005A62
0x180005b69  mov     r8d, 4; MaxCount
0x180005b6f  lea     rdx, aSys; "SYS:"
0x180005b76  mov     rcx, rbx; String1
0x180005b79  call    cs:__imp__wcsnicmp
0x180005b80  nop     dword ptr [rax+rax+00h]
0x180005b85  test    eax, eax
0x180005b87  jnz     loc_1800059EE
0x180005b8d  bts     esi, 1Eh
0x180005b91  jmp     loc_180005A57
0x180005b96  mov     ecx, 1
0x180005b9b  dec     rax
0x180005b9e  add     rbx, 2
0x180005ba2  or      esi, ecx
0x180005ba4  jmp     loc_1800059E9
0x180005ba9  mov     eax, 0C0000033h
0x180005bae  jmp     loc_180005B11
```
