# AslPathToNetworkPathNt

- ea: `0x140046840`
- end: `0x140046901`
- name: `AslPathToNetworkPathNt`
- size: `193`
- prototype: `__int64 __fastcall(wchar_t **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x140026e80`

## callees

- `0x14003e364`
- `0x140045d44`
- `0x140046840`
- `0x140046e00`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!wcscpy_s` at `0x1400468d5`
- `ntoskrnl!wcscpy_s` at `0x1400468d5`
- `ntoskrnl!wcscat_s` at `0x1400468eb`
- `ntoskrnl!wcscat_s` at `0x1400468eb`

## string_xrefs

- `0x1400468b2`: `AslPathToNetworkPathNt`

## pseudocode

```c
__int64 __fastcall AslPathToNetworkPathNt(wchar_t **a1, __int64 a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v7; // rax
  rsize_t v8; // rsi
  wchar_t *v9; // rax
  wchar_t *v10; // rdi

  *a1 = 0;
  if ( (unsigned int)AslpDetermineDosPathNameType(a2) == 1 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(a2 + 2 * v7) );
    v8 = v7 + 9;
    v9 = (wchar_t *)AslAlloc(v4, 2 * (v7 + 9), 1);
    v10 = v9;
    if ( v9 )
    {
      wcscpy_s(v9, v8, L"\\??\\UNC\\");
      wcscat_s(v10, v8, (const wchar_t *)(a2 + 4));
      v5 = 0;
      *a1 = v10;
    }
    else
    {
      v5 = -1073741801;
      AslLogCallPrintf(1, "AslPathToNetworkPathNt", 348, "Out of memory");
    }
  }
  else
  {
    v5 = -1073741811;
  }
  AslFree(v4, 0);
  return v5;
}

```

## disassembly

```asm
0x140046840  push    rbx
0x140046842  push    rbp
0x140046843  push    rsi
0x140046844  push    rdi
0x140046845  push    r14
0x140046847  sub     rsp, 20h
0x14004684b  mov     r14, rcx
0x14004684e  xor     ebp, ebp
0x140046850  mov     [rcx], rbp
0x140046853  mov     rbx, rdx
0x140046856  mov     rcx, rdx
0x140046859  call    AslpDetermineDosPathNameType
0x14004685e  cmp     eax, 1
0x140046861  jz      short loc_14004687D
0x140046863  mov     ebx, 0C000000Dh
0x140046868  xor     edx, edx
0x14004686a  call    AslFree
0x14004686f  mov     eax, ebx
0x140046871  add     rsp, 20h
0x140046875  pop     r14
0x140046877  pop     rdi
0x140046878  pop     rsi
0x140046879  pop     rbp
0x14004687a  pop     rbx
0x14004687b  retn
0x14004687d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140046881  inc     rax
0x140046884  cmp     [rbx+rax*2], bp
0x140046888  jnz     short loc_140046881
0x14004688a  lea     rsi, [rax+9]
0x14004688e  mov     r8d, 1
0x140046894  lea     rdx, [rsi+rsi]
0x140046898  call    AslAlloc
0x14004689d  mov     rdi, rax
0x1400468a0  test    rax, rax
0x1400468a3  jnz     short loc_1400468C8
0x1400468a5  lea     r9, aOutOfMemory; "Out of memory"
0x1400468ac  mov     r8d, 15Ch
0x1400468b2  lea     rdx, aAslpathtonetwo; "AslPathToNetworkPathNt"
0x1400468b9  mov     ebx, 0C0000017h
0x1400468be  lea     ecx, [rax+1]
0x1400468c1  call    AslLogCallPrintf
0x1400468c6  jmp     short loc_140046868
0x1400468c8  lea     r8, aUnc; "\\??\\UNC\\"
0x1400468cf  mov     rdx, rsi; SizeInWords
0x1400468d2  mov     rcx, rdi; Dst
0x1400468d5  call    cs:__imp_wcscpy_s
0x1400468dc  nop     dword ptr [rax+rax+00h]
0x1400468e1  lea     r8, [rbx+4]; Src
0x1400468e5  mov     rdx, rsi; SizeInWords
0x1400468e8  mov     rcx, rdi; Dst
0x1400468eb  call    cs:__imp_wcscat_s
0x1400468f2  nop     dword ptr [rax+rax+00h]
0x1400468f7  mov     ebx, ebp
0x1400468f9  mov     [r14], rdi
0x1400468fc  jmp     loc_140046868
```
