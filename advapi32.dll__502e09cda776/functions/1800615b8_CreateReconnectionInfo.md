# CreateReconnectionInfo

- ea: `0x1800615b8`
- end: `0x1800617b0`
- name: `CreateReconnectionInfo`
- size: `504`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003bf7c`
- `0x180061b38`
- `0x180061c5c`
- `0x180061df0`
- `0x180062340`

## callees

- `0x1800615b8`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180061737`
- `ntdll!RtlCopyUnicodeString` at `0x18006177e`
- `ntdll!RtlCopyUnicodeString` at `0x180061737`
- `ntdll!RtlCopyUnicodeString` at `0x18006177e`
- `ntdll!RtlCopyString` at `0x1800616b2`
- `ntdll!RtlCopyString` at `0x180061701`
- `ntdll!RtlCopyString` at `0x1800616b2`
- `ntdll!RtlCopyString` at `0x180061701`
- `KERNEL32!HeapAlloc` at `0x180061611`
- `KERNEL32!HeapAlloc` at `0x180061611`
- `KERNEL32!GetProcessHeap` at `0x1800615fa`
- `KERNEL32!GetProcessHeap` at `0x180061668`
- `KERNEL32!GetProcessHeap` at `0x1800615fa`
- `KERNEL32!GetProcessHeap` at `0x180061668`
- `KERNEL32!HeapFree` at `0x18006167c`
- `KERNEL32!HeapFree` at `0x18006167c`

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
0x1800615b8  push    rbx
0x1800615ba  push    rbp
0x1800615bb  push    rsi
0x1800615bc  push    rdi
0x1800615bd  push    r14
0x1800615bf  sub     rsp, 20h
0x1800615c3  mov     edi, ecx
0x1800615c5  mov     ecx, 38h ; '8'
0x1800615ca  mov     r14b, r9b
0x1800615cd  mov     rsi, r8
0x1800615d0  mov     rbp, rdx
0x1800615d3  test    rdx, rdx
0x1800615d6  jz      short loc_1800615E5
0x1800615d8  cmp     qword ptr [rdx+8], 0
0x1800615dd  jz      short loc_1800615E5
0x1800615df  movzx   eax, word ptr [rdx+2]
0x1800615e3  add     ecx, eax
0x1800615e5  test    rsi, rsi
0x1800615e8  jz      short loc_1800615F8
0x1800615ea  cmp     qword ptr [r8+8], 0
0x1800615ef  jz      short loc_1800615F8
0x1800615f1  movzx   eax, word ptr [r8+2]
0x1800615f6  add     ecx, eax
0x1800615f8  mov     ebx, ecx
0x1800615fa  call    cs:__imp_GetProcessHeap
0x180061601  nop     dword ptr [rax+rax+00h]
0x180061606  mov     r8d, ebx; dwBytes
0x180061609  mov     edx, 8; dwFlags
0x18006160e  mov     rcx, rax; hHeap
0x180061611  call    cs:__imp_HeapAlloc
0x180061618  nop     dword ptr [rax+rax+00h]
0x18006161d  mov     rbx, rax
0x180061620  test    rax, rax
0x180061623  jnz     short loc_18006162C
0x180061625  xor     eax, eax
0x180061627  jmp     loc_1800617A4
0x18006162c  mov     [rax+4], edi
0x18006162f  mov     eax, gs:179Ch
0x180061637  test    eax, eax
0x180061639  setnz   al
0x18006163c  mov     [rbx+30h], al
0x18006163f  test    edi, edi
0x180061641  jz      loc_18006170F
0x180061647  sub     edi, 1
0x18006164a  jz      loc_18006170F
0x180061650  sub     edi, 1
0x180061653  jz      loc_18006170F
0x180061659  sub     edi, 1
0x18006165c  jz      short loc_18006168A
0x18006165e  sub     edi, 1
0x180061661  jz      short loc_18006168A
0x180061663  cmp     edi, 1
0x180061666  jz      short loc_18006168A
0x180061668  call    cs:__imp_GetProcessHeap
0x18006166f  nop     dword ptr [rax+rax+00h]
0x180061674  mov     r8, rbx; lpMem
0x180061677  xor     edx, edx; dwFlags
0x180061679  mov     rcx, rax; hHeap
0x18006167c  call    cs:__imp_HeapFree
0x180061683  nop     dword ptr [rax+rax+00h]
0x180061688  jmp     short loc_180061625
0x18006168a  test    rbp, rbp
0x18006168d  jz      short loc_1800616CA
0x18006168f  cmp     qword ptr [rbp+8], 0
0x180061694  jz      short loc_1800616CA
0x180061696  lea     rax, [rbx+38h]
0x18006169a  mov     rdx, rbp; SourceString
0x18006169d  mov     [rbx+18h], rax
0x1800616a1  lea     rcx, [rbx+10h]; DestinationString
0x1800616a5  movzx   eax, word ptr [rbp+2]
0x1800616a9  mov     [rbx+12h], ax
0x1800616ad  xor     eax, eax
0x1800616af  mov     [rcx], ax
0x1800616b2  call    cs:__imp_RtlCopyString
0x1800616b9  nop     dword ptr [rax+rax+00h]
0x1800616be  movzx   eax, word ptr [rbp+2]
0x1800616c2  add     rax, [rbx+18h]
0x1800616c6  mov     [rbx+28h], rax
0x1800616ca  test    rsi, rsi
0x1800616cd  jz      loc_18006178A
0x1800616d3  cmp     qword ptr [rsi+8], 0
0x1800616d8  jz      loc_18006178A
0x1800616de  cmp     qword ptr [rbx+28h], 0
0x1800616e3  jnz     short loc_1800616ED
0x1800616e5  lea     rax, [rbx+38h]
0x1800616e9  mov     [rbx+28h], rax
0x1800616ed  movzx   eax, word ptr [rsi+2]
0x1800616f1  lea     rcx, [rbx+20h]; DestinationString
0x1800616f5  mov     [rbx+22h], ax
0x1800616f9  mov     rdx, rsi; SourceString
0x1800616fc  xor     eax, eax
0x1800616fe  mov     [rcx], ax
0x180061701  call    cs:__imp_RtlCopyString
0x180061708  nop     dword ptr [rax+rax+00h]
0x18006170d  jmp     short loc_18006178A
0x18006170f  test    rbp, rbp
0x180061712  jz      short loc_18006174F
0x180061714  cmp     qword ptr [rbp+8], 0
0x180061719  jz      short loc_18006174F
0x18006171b  lea     rax, [rbx+38h]
0x18006171f  mov     rdx, rbp; SourceString
0x180061722  mov     [rbx+18h], rax
0x180061726  lea     rcx, [rbx+10h]; DestinationString
0x18006172a  movzx   eax, word ptr [rbp+2]
0x18006172e  mov     [rbx+12h], ax
0x180061732  xor     eax, eax
0x180061734  mov     [rcx], ax
0x180061737  call    cs:__imp_RtlCopyUnicodeString
0x18006173e  nop     dword ptr [rax+rax+00h]
0x180061743  movzx   eax, word ptr [rbp+2]
0x180061747  add     rax, [rbx+18h]
0x18006174b  mov     [rbx+28h], rax
0x18006174f  test    rsi, rsi
0x180061752  jz      short loc_18006178A
0x180061754  cmp     qword ptr [rsi+8], 0
0x180061759  jz      short loc_18006178A
0x18006175b  cmp     qword ptr [rbx+28h], 0
0x180061760  jnz     short loc_18006176A
0x180061762  lea     rax, [rbx+38h]
0x180061766  mov     [rbx+28h], rax
0x18006176a  movzx   eax, word ptr [rsi+2]
0x18006176e  lea     rcx, [rbx+20h]; DestinationString
0x180061772  mov     [rbx+22h], ax
0x180061776  mov     rdx, rsi; SourceString
0x180061779  xor     eax, eax
0x18006177b  mov     [rcx], ax
0x18006177e  call    cs:__imp_RtlCopyUnicodeString
0x180061785  nop     dword ptr [rax+rax+00h]
0x18006178a  mov     rax, [rsp+48h+arg_20]
0x18006178f  mov     [rbx+8], rax
0x180061793  mov     rax, rbx
0x180061796  mov     [rbx+31h], r14b
0x18006179a  mov     byte ptr [rbx+32h], 0
0x18006179e  mov     dword ptr [rbx], 456C6643h
0x1800617a4  add     rsp, 20h
0x1800617a8  pop     r14
0x1800617aa  pop     rdi
0x1800617ab  pop     rsi
0x1800617ac  pop     rbp
0x1800617ad  pop     rbx
0x1800617ae  retn
```
