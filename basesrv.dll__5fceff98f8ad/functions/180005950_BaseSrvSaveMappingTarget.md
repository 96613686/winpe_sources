# BaseSrvSaveMappingTarget

- ea: `0x180005950`
- end: `0x180005b4b`
- name: `BaseSrvSaveMappingTarget`
- size: `507`
- prototype: `__int64 __fastcall(wchar_t *String1, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005200`

## callees

- `0x180005950`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180005a79`
- `ntdll!RtlAllocateHeap` at `0x180005a79`
- `ntdll!_wcsnicmp` at `0x1800059d4`
- `ntdll!_wcsnicmp` at `0x180005b11`
- `ntdll!_wcsnicmp` at `0x1800059d4`
- `ntdll!_wcsnicmp` at `0x180005b11`
- `ntdll!RtlCopyUnicodeString` at `0x180005ae9`
- `ntdll!RtlCopyUnicodeString` at `0x180005ae9`
- `ntdll!RtlEqualUnicodeString` at `0x180005a44`
- `ntdll!RtlEqualUnicodeString` at `0x180005a44`
- `ntdll!RtlInitUnicodeString` at `0x180005a17`
- `ntdll!RtlInitUnicodeString` at `0x180005a17`

## pseudocode

```c
__int64 __fastcall BaseSrvSaveMappingTarget(wchar_t *String1, _QWORD *a2, _DWORD *a3)
{
  wchar_t *v5; // rbx
  int v6; // esi
  unsigned __int64 v7; // rax
  const WCHAR *v8; // rdx
  wchar_t v9; // cx
  int v10; // ecx
  __int64 *i; // rdi
  char *v12; // rbx
  char *Heap; // rax
  __int64 result; // rax
  bool v15; // zf
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF

  DestinationString = 0;
  v5 = String1;
  v6 = 0;
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
      v9 = *v5;
      if ( *v5 != 33 )
        break;
      --v7;
      ++v5;
      v6 |= 1u;
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
    ++v5;
    v6 |= v10;
  }
  if ( v7 < 4 )
    goto LABEL_4;
  if ( !_wcsnicmp(v5, L"USR:", 4u) )
  {
    v6 |= 0x80000000;
LABEL_14:
    v5 += 4;
    goto LABEL_4;
  }
  if ( !_wcsnicmp(v5, L"SYS:", 4u) )
  {
    v6 |= 0x40000000u;
    goto LABEL_14;
  }
LABEL_4:
  if ( (v6 & 0xC0000000) != 0 )
  {
    if ( *v5 == 92 )
      return 3221225523LL;
LABEL_18:
    v8 = v5;
    goto LABEL_19;
  }
  if ( *v5 == 92 )
    goto LABEL_18;
  if ( *v5 )
    return 3221225523LL;
  v8 = 0;
LABEL_19:
  RtlInitUnicodeString(&DestinationString, v8);
  for ( i = &BaseSrvMappingTargetHead; ; i = (__int64 *)v12 )
  {
    v12 = (char *)*i;
    if ( !*i )
      break;
    if ( RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)(v12 + 8), 1u) )
    {
      *a3 = v6;
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
  v15 = DestinationString.Length == 0;
  *a3 = v6;
  if ( !v15 )
  {
    *((_QWORD *)Heap + 2) = Heap + 24;
    *((_WORD *)Heap + 4) = 0;
    *((_WORD *)Heap + 5) = DestinationString.MaximumLength;
    RtlCopyUnicodeString((PUNICODE_STRING)(Heap + 8), &DestinationString);
  }
LABEL_26:
  result = 0;
  *a2 = v12;
  return result;
}

```

## disassembly

```asm
0x180005950  push    rbx
0x180005952  push    rsi
0x180005953  push    r14
0x180005955  push    r15
0x180005957  sub     rsp, 38h
0x18000595b  xorps   xmm0, xmm0
0x18000595e  mov     r15, r8
0x180005961  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x180005966  mov     r14, rdx
0x180005969  mov     rbx, rcx
0x18000596c  xor     esi, esi
0x18000596e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005975  inc     rax
0x180005978  cmp     [rcx+rax*2], si
0x18000597c  jnz     short loc_180005975
0x18000597e  test    rax, rax
0x180005981  jnz     short loc_1800059A1
0x180005983  test    esi, 0C0000000h
0x180005989  jnz     short loc_180005A05
0x18000598b  movzx   eax, word ptr [rbx]
0x18000598e  cmp     ax, 5Ch ; '\'
0x180005992  jz      short loc_180005A0F
0x180005994  test    ax, ax
0x180005997  jnz     loc_180005B41
0x18000599d  xor     edx, edx
0x18000599f  jmp     short loc_180005A12
0x1800059a1  movzx   ecx, word ptr [rbx]
0x1800059a4  cmp     cx, 21h ; '!'
0x1800059a8  jz      loc_180005B2E
0x1800059ae  cmp     cx, 23h ; '#'
0x1800059b2  jz      short loc_1800059F2
0x1800059b4  cmp     cx, 40h ; '@'
0x1800059b8  jz      loc_180005AF7
0x1800059be  cmp     rax, 4
0x1800059c2  jb      short loc_180005983
0x1800059c4  mov     r8d, 4; MaxCount
0x1800059ca  lea     rdx, aUsr; "USR:"
0x1800059d1  mov     rcx, rbx; String1
0x1800059d4  call    cs:__imp__wcsnicmp
0x1800059db  nop     dword ptr [rax+rax+00h]
0x1800059e0  test    eax, eax
0x1800059e2  jnz     loc_180005B01
0x1800059e8  bts     esi, 1Fh
0x1800059ec  add     rbx, 8
0x1800059f0  jmp     short loc_180005983
0x1800059f2  mov     ecx, 2
0x1800059f7  dec     rax
0x1800059fa  add     rbx, 2
0x1800059fe  or      esi, ecx
0x180005a00  jmp     loc_18000597E
0x180005a05  cmp     word ptr [rbx], 5Ch ; '\'
0x180005a09  jz      loc_180005B41
0x180005a0f  mov     rdx, rbx; SourceString
0x180005a12  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x180005a17  call    cs:__imp_RtlInitUnicodeString
0x180005a1e  nop     dword ptr [rax+rax+00h]
0x180005a23  mov     [rsp+58h+arg_0], rdi
0x180005a28  lea     rdi, BaseSrvMappingTargetHead
0x180005a2f  nop
0x180005a30  mov     rbx, [rdi]
0x180005a33  test    rbx, rbx
0x180005a36  jz      short loc_180005A59
0x180005a38  lea     rdx, [rbx+8]; String2
0x180005a3c  mov     r8b, 1; CaseInsensitive
0x180005a3f  lea     rcx, [rsp+58h+DestinationString]; String1
0x180005a44  call    cs:__imp_RtlEqualUnicodeString
0x180005a4b  nop     dword ptr [rax+rax+00h]
0x180005a50  test    al, al
0x180005a52  jnz     short loc_180005AA3
0x180005a54  mov     rdi, rbx
0x180005a57  jmp     short loc_180005A30
0x180005a59  mov     edx, cs:BaseSrvSharedTag
0x180005a5f  movzx   r8d, [rsp+58h+DestinationString.MaximumLength]
0x180005a65  add     edx, 40000h
0x180005a6b  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180005a72  or      edx, 8; Flags
0x180005a75  add     r8, 18h; Size
0x180005a79  call    cs:__imp_RtlAllocateHeap
0x180005a80  nop     dword ptr [rax+rax+00h]
0x180005a85  mov     rbx, rax
0x180005a88  test    rax, rax
0x180005a8b  jnz     short loc_180005ABC
0x180005a8d  mov     rdi, [rsp+58h+arg_0]
0x180005a92  mov     eax, 0C0000017h
0x180005a97  add     rsp, 38h
0x180005a9b  pop     r15
0x180005a9d  pop     r14
0x180005a9f  pop     rsi
0x180005aa0  pop     rbx
0x180005aa1  retn
0x180005aa3  mov     [r15], esi
0x180005aa6  mov     rdi, [rsp+58h+arg_0]
0x180005aab  xor     eax, eax
0x180005aad  mov     [r14], rbx
0x180005ab0  add     rsp, 38h
0x180005ab4  pop     r15
0x180005ab6  pop     r14
0x180005ab8  pop     rsi
0x180005ab9  pop     rbx
0x180005aba  retn
0x180005abc  mov     [rdi], rbx
0x180005abf  cmp     [rsp+58h+DestinationString.Length], 0
0x180005ac5  mov     [r15], esi
0x180005ac8  jz      short loc_180005AA6
0x180005aca  add     rax, 18h
0x180005ace  lea     rcx, [rbx+8]; DestinationString
0x180005ad2  mov     [rbx+10h], rax
0x180005ad6  lea     rdx, [rsp+58h+DestinationString]; SourceString
0x180005adb  xor     eax, eax
0x180005add  mov     [rcx], ax
0x180005ae0  movzx   eax, [rsp+58h+DestinationString.MaximumLength]
0x180005ae5  mov     [rbx+0Ah], ax
0x180005ae9  call    cs:__imp_RtlCopyUnicodeString
0x180005af0  nop     dword ptr [rax+rax+00h]
0x180005af5  jmp     short loc_180005AA6
0x180005af7  mov     ecx, 4
0x180005afc  jmp     loc_1800059F7
0x180005b01  mov     r8d, 4; MaxCount
0x180005b07  lea     rdx, aSys; "SYS:"
0x180005b0e  mov     rcx, rbx; String1
0x180005b11  call    cs:__imp__wcsnicmp
0x180005b18  nop     dword ptr [rax+rax+00h]
0x180005b1d  test    eax, eax
0x180005b1f  jnz     loc_180005983
0x180005b25  bts     esi, 1Eh
0x180005b29  jmp     loc_1800059EC
0x180005b2e  mov     ecx, 1
0x180005b33  dec     rax
0x180005b36  add     rbx, 2
0x180005b3a  or      esi, ecx
0x180005b3c  jmp     loc_18000597E
0x180005b41  mov     eax, 0C0000033h
0x180005b46  jmp     loc_180005AB0
```
