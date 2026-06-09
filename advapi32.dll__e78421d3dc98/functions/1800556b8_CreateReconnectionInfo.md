# CreateReconnectionInfo

- ea: `0x1800556b8`
- end: `0x18005587f`
- name: `CreateReconnectionInfo`
- size: `455`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180037d78`
- `0x180055bd4`
- `0x180055cec`
- `0x180055e6c`
- `0x180056378`

## callees

- `0x1800556b8`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180055813`
- `ntdll!RtlCopyUnicodeString` at `0x180055854`
- `ntdll!RtlCopyUnicodeString` at `0x180055813`
- `ntdll!RtlCopyUnicodeString` at `0x180055854`
- `ntdll!RtlCopyString` at `0x18005579a`
- `ntdll!RtlCopyString` at `0x1800557e3`
- `ntdll!RtlCopyString` at `0x18005579a`
- `ntdll!RtlCopyString` at `0x1800557e3`
- `KERNEL32!HeapAlloc` at `0x18005570b`
- `KERNEL32!HeapAlloc` at `0x18005570b`
- `KERNEL32!GetProcessHeap` at `0x1800556fa`
- `KERNEL32!GetProcessHeap` at `0x18005575c`
- `KERNEL32!GetProcessHeap` at `0x1800556fa`
- `KERNEL32!GetProcessHeap` at `0x18005575c`
- `KERNEL32!HeapFree` at `0x18005576a`
- `KERNEL32!HeapFree` at `0x18005576a`

## pseudocode

```c
struct _STRING *__fastcall CreateReconnectionInfo(int a1, const STRING *a2, const STRING *a3, char a4, CHAR *a5)
{
  int v6; // ecx
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  struct _STRING *v12; // rax
  struct _STRING *v13; // rbx
  struct _STRING *result; // rax
  int v15; // edi
  int v16; // edi
  int v17; // edi
  HANDLE v18; // rax

  v6 = 56;
  if ( a2 && a2->Buffer )
    v6 = a2->MaximumLength + 56;
  if ( a3 && a3->Buffer )
    v6 += a3->MaximumLength;
  v10 = v6;
  ProcessHeap = GetProcessHeap();
  v12 = (struct _STRING *)HeapAlloc(ProcessHeap, 8u, v10);
  v13 = v12;
  if ( !v12 )
    return 0;
  *(_DWORD *)(&v12->MaximumLength + 1) = a1;
  LOBYTE(v12[3].Length) = NtCurrentTeb()->IsImpersonating != 0;
  if ( a1 && (v15 = a1 - 1) != 0 && (v16 = v15 - 1) != 0 )
  {
    v17 = v16 - 1;
    if ( v17 && (unsigned int)(v17 - 1) >= 2 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v13);
      return 0;
    }
    if ( a2 && a2->Buffer )
    {
      v12[1].Buffer = (PCHAR)&v12[3].Buffer;
      v12[1].MaximumLength = a2->MaximumLength;
      v12[1].Length = 0;
      RtlCopyString(v12 + 1, a2);
      v13[2].Buffer = &v13[1].Buffer[a2->MaximumLength];
    }
    if ( a3 && a3->Buffer )
    {
      if ( !v13[2].Buffer )
        v13[2].Buffer = (PCHAR)&v13[3].Buffer;
      v13[2].MaximumLength = a3->MaximumLength;
      v13[2].Length = 0;
      RtlCopyString(v13 + 2, a3);
    }
  }
  else
  {
    if ( a2 && a2->Buffer )
    {
      v12[1].Buffer = (PCHAR)&v12[3].Buffer;
      v12[1].MaximumLength = a2->MaximumLength;
      v12[1].Length = 0;
      RtlCopyUnicodeString((PUNICODE_STRING)&v12[1], (PCUNICODE_STRING)a2);
      v13[2].Buffer = &v13[1].Buffer[a2->MaximumLength];
    }
    if ( a3 && a3->Buffer )
    {
      if ( !v13[2].Buffer )
        v13[2].Buffer = (PCHAR)&v13[3].Buffer;
      v13[2].MaximumLength = a3->MaximumLength;
      v13[2].Length = 0;
      RtlCopyUnicodeString((PUNICODE_STRING)&v13[2], (PCUNICODE_STRING)a3);
    }
  }
  v13->Buffer = a5;
  result = v13;
  HIBYTE(v13[3].Length) = a4;
  LOBYTE(v13[3].MaximumLength) = 0;
  *(_DWORD *)&v13->Length = 1164731971;
  return result;
}

```

## disassembly

```asm
0x1800556b8  push    rbx
0x1800556ba  push    rbp
0x1800556bb  push    rsi
0x1800556bc  push    rdi
0x1800556bd  push    r14
0x1800556bf  sub     rsp, 20h
0x1800556c3  mov     edi, ecx
0x1800556c5  mov     ecx, 38h ; '8'
0x1800556ca  mov     r14b, r9b
0x1800556cd  mov     rsi, r8
0x1800556d0  mov     rbp, rdx
0x1800556d3  test    rdx, rdx
0x1800556d6  jz      short loc_1800556E5
0x1800556d8  cmp     qword ptr [rdx+8], 0
0x1800556dd  jz      short loc_1800556E5
0x1800556df  movzx   eax, word ptr [rdx+2]
0x1800556e3  add     ecx, eax
0x1800556e5  test    rsi, rsi
0x1800556e8  jz      short loc_1800556F8
0x1800556ea  cmp     qword ptr [r8+8], 0
0x1800556ef  jz      short loc_1800556F8
0x1800556f1  movzx   eax, word ptr [r8+2]
0x1800556f6  add     ecx, eax
0x1800556f8  mov     ebx, ecx
0x1800556fa  call    cs:__imp_GetProcessHeap
0x180055700  mov     r8d, ebx; dwBytes
0x180055703  mov     edx, 8; dwFlags
0x180055708  mov     rcx, rax; hHeap
0x18005570b  call    cs:__imp_HeapAlloc
0x180055711  mov     rbx, rax
0x180055714  test    rax, rax
0x180055717  jnz     short loc_180055720
0x180055719  xor     eax, eax
0x18005571b  jmp     loc_180055874
0x180055720  mov     [rax+4], edi
0x180055723  mov     eax, gs:179Ch
0x18005572b  test    eax, eax
0x18005572d  setnz   al
0x180055730  mov     [rbx+30h], al
0x180055733  test    edi, edi
0x180055735  jz      loc_1800557EB
0x18005573b  sub     edi, 1
0x18005573e  jz      loc_1800557EB
0x180055744  sub     edi, 1
0x180055747  jz      loc_1800557EB
0x18005574d  sub     edi, 1
0x180055750  jz      short loc_180055772
0x180055752  sub     edi, 1
0x180055755  jz      short loc_180055772
0x180055757  cmp     edi, 1
0x18005575a  jz      short loc_180055772
0x18005575c  call    cs:__imp_GetProcessHeap
0x180055762  mov     r8, rbx; lpMem
0x180055765  xor     edx, edx; dwFlags
0x180055767  mov     rcx, rax; hHeap
0x18005576a  call    cs:__imp_HeapFree
0x180055770  jmp     short loc_180055719
0x180055772  test    rbp, rbp
0x180055775  jz      short loc_1800557AC
0x180055777  cmp     qword ptr [rbp+8], 0
0x18005577c  jz      short loc_1800557AC
0x18005577e  lea     rax, [rbx+38h]
0x180055782  mov     rdx, rbp; SourceString
0x180055785  mov     [rbx+18h], rax
0x180055789  lea     rcx, [rbx+10h]; DestinationString
0x18005578d  movzx   eax, word ptr [rbp+2]
0x180055791  mov     [rbx+12h], ax
0x180055795  xor     eax, eax
0x180055797  mov     [rcx], ax
0x18005579a  call    cs:__imp_RtlCopyString
0x1800557a0  movzx   eax, word ptr [rbp+2]
0x1800557a4  add     rax, [rbx+18h]
0x1800557a8  mov     [rbx+28h], rax
0x1800557ac  test    rsi, rsi
0x1800557af  jz      loc_18005585A
0x1800557b5  cmp     qword ptr [rsi+8], 0
0x1800557ba  jz      loc_18005585A
0x1800557c0  cmp     qword ptr [rbx+28h], 0
0x1800557c5  jnz     short loc_1800557CF
0x1800557c7  lea     rax, [rbx+38h]
0x1800557cb  mov     [rbx+28h], rax
0x1800557cf  movzx   eax, word ptr [rsi+2]
0x1800557d3  lea     rcx, [rbx+20h]; DestinationString
0x1800557d7  mov     [rbx+22h], ax
0x1800557db  mov     rdx, rsi; SourceString
0x1800557de  xor     eax, eax
0x1800557e0  mov     [rcx], ax
0x1800557e3  call    cs:__imp_RtlCopyString
0x1800557e9  jmp     short loc_18005585A
0x1800557eb  test    rbp, rbp
0x1800557ee  jz      short loc_180055825
0x1800557f0  cmp     qword ptr [rbp+8], 0
0x1800557f5  jz      short loc_180055825
0x1800557f7  lea     rax, [rbx+38h]
0x1800557fb  mov     rdx, rbp; SourceString
0x1800557fe  mov     [rbx+18h], rax
0x180055802  lea     rcx, [rbx+10h]; DestinationString
0x180055806  movzx   eax, word ptr [rbp+2]
0x18005580a  mov     [rbx+12h], ax
0x18005580e  xor     eax, eax
0x180055810  mov     [rcx], ax
0x180055813  call    cs:__imp_RtlCopyUnicodeString
0x180055819  movzx   eax, word ptr [rbp+2]
0x18005581d  add     rax, [rbx+18h]
0x180055821  mov     [rbx+28h], rax
0x180055825  test    rsi, rsi
0x180055828  jz      short loc_18005585A
0x18005582a  cmp     qword ptr [rsi+8], 0
0x18005582f  jz      short loc_18005585A
0x180055831  cmp     qword ptr [rbx+28h], 0
0x180055836  jnz     short loc_180055840
0x180055838  lea     rax, [rbx+38h]
0x18005583c  mov     [rbx+28h], rax
0x180055840  movzx   eax, word ptr [rsi+2]
0x180055844  lea     rcx, [rbx+20h]; DestinationString
0x180055848  mov     [rbx+22h], ax
0x18005584c  mov     rdx, rsi; SourceString
0x18005584f  xor     eax, eax
0x180055851  mov     [rcx], ax
0x180055854  call    cs:__imp_RtlCopyUnicodeString
0x18005585a  mov     rax, [rsp+48h+arg_20]
0x18005585f  mov     [rbx+8], rax
0x180055863  mov     rax, rbx
0x180055866  mov     [rbx+31h], r14b
0x18005586a  mov     byte ptr [rbx+32h], 0
0x18005586e  mov     dword ptr [rbx], 456C6643h
0x180055874  add     rsp, 20h
0x180055878  pop     r14
0x18005587a  pop     rdi
0x18005587b  pop     rsi
0x18005587c  pop     rbp
0x18005587d  pop     rbx
0x18005587e  retn
```
