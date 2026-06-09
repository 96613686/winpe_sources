# FormLongPathName

- ea: `0x18001320c`
- end: `0x180013316`
- name: `FormLongPathName`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800128a0`

## callees

- `0x18001320c`
- `0x18001331c`

## import_xrefs

- `KERNEL32!GetLongPathNameW` at `0x180013246`
- `KERNEL32!GetLongPathNameW` at `0x180013282`
- `KERNEL32!GetLongPathNameW` at `0x180013246`
- `KERNEL32!GetLongPathNameW` at `0x180013282`
- `KERNEL32!GetLastError` at `0x18001328c`
- `KERNEL32!GetLastError` at `0x1800132aa`
- `KERNEL32!GetLastError` at `0x1800132e9`
- `KERNEL32!GetLastError` at `0x18001328c`
- `KERNEL32!GetLastError` at `0x1800132aa`
- `KERNEL32!GetLastError` at `0x1800132e9`
- `KERNEL32!GetProcessHeap` at `0x180013257`
- `KERNEL32!GetProcessHeap` at `0x1800132d1`
- `KERNEL32!GetProcessHeap` at `0x180013257`
- `KERNEL32!GetProcessHeap` at `0x1800132d1`
- `KERNEL32!HeapAlloc` at `0x180013268`
- `KERNEL32!HeapAlloc` at `0x180013268`
- `KERNEL32!HeapFree` at `0x1800132df`
- `KERNEL32!HeapFree` at `0x1800132df`
- `KERNEL32!SetLastError` at `0x1800132f3`
- `KERNEL32!SetLastError` at `0x180013303`
- `KERNEL32!SetLastError` at `0x1800132f3`
- `KERNEL32!SetLastError` at `0x180013303`

## pseudocode

```c
const WCHAR *__fastcall FormLongPathName(const wchar_t *a1)
{
  const WCHAR *v1; // rax
  const WCHAR *v2; // rbp
  DWORD LongPathNameW; // edi
  HANDLE ProcessHeap; // rax
  WCHAR *v5; // rax
  WCHAR *v6; // rsi
  DWORD v7; // r14d
  WCHAR *v8; // rax
  const WCHAR *v9; // rbx
  DWORD LastError; // edi
  WCHAR *v11; // rsi
  HANDLE v12; // rax

  if ( a1 && *a1 )
  {
    v1 = (const WCHAR *)PrepareUnicodePathEx(a1);
    v2 = v1;
    if ( !v1 )
    {
      v9 = 0;
      LastError = GetLastError();
LABEL_20:
      SetLastError(LastError);
      return v9;
    }
    LongPathNameW = GetLongPathNameW(v1, 0, 0);
    if ( LongPathNameW )
    {
      ProcessHeap = GetProcessHeap();
      v5 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * LongPathNameW);
      v6 = v5;
      if ( v5 )
      {
        v7 = 0;
        if ( !GetLongPathNameW(v2, v5, LongPathNameW) )
          v7 = GetLastError();
      }
      else
      {
        v7 = 14;
      }
      v8 = v6;
      if ( v6 )
      {
        v9 = v6;
LABEL_13:
        LastError = 0;
        if ( v6 )
          LastError = v7;
        v11 = 0;
        if ( v8 )
          v11 = (WCHAR *)v2;
        if ( v11 )
        {
          v12 = GetProcessHeap();
          HeapFree(v12, 0, v11);
        }
        goto LABEL_20;
      }
    }
    else
    {
      v6 = 0;
      v7 = GetLastError();
      v8 = 0;
    }
    v9 = v2;
    goto LABEL_13;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x18001320c  push    rbx
0x18001320e  push    rbp
0x18001320f  push    rsi
0x180013210  push    rdi
0x180013211  push    r14
0x180013213  sub     rsp, 20h
0x180013217  test    rcx, rcx
0x18001321a  jz      loc_1800132FE
0x180013220  xor     eax, eax
0x180013222  cmp     ax, [rcx]
0x180013225  jz      loc_1800132FE
0x18001322b  xor     edx, edx
0x18001322d  call    PrepareUnicodePathEx
0x180013232  mov     rbp, rax
0x180013235  test    rax, rax
0x180013238  jz      loc_1800132E7
0x18001323e  xor     r8d, r8d; cchBuffer
0x180013241  xor     edx, edx; lpszLongPath
0x180013243  mov     rcx, rax; lpszShortPath
0x180013246  call    cs:__imp_GetLongPathNameW
0x18001324c  mov     edi, eax
0x18001324e  test    eax, eax
0x180013250  jz      short loc_1800132AA
0x180013252  mov     ebx, edi
0x180013254  add     rbx, rbx
0x180013257  call    cs:__imp_GetProcessHeap
0x18001325d  mov     r8, rbx; dwBytes
0x180013260  mov     edx, 8; dwFlags
0x180013265  mov     rcx, rax; hHeap
0x180013268  call    cs:__imp_HeapAlloc
0x18001326e  mov     rsi, rax
0x180013271  test    rax, rax
0x180013274  jz      short loc_180013297
0x180013276  mov     r8d, edi; cchBuffer
0x180013279  mov     rdx, rax; lpszLongPath
0x18001327c  mov     rcx, rbp; lpszShortPath
0x18001327f  xor     r14d, r14d
0x180013282  call    cs:__imp_GetLongPathNameW
0x180013288  test    eax, eax
0x18001328a  jnz     short loc_18001329D
0x18001328c  call    cs:__imp_GetLastError
0x180013292  mov     r14d, eax
0x180013295  jmp     short loc_18001329D
0x180013297  mov     r14d, 0Eh
0x18001329d  mov     rax, rsi
0x1800132a0  test    rsi, rsi
0x1800132a3  jz      short loc_1800132B7
0x1800132a5  mov     rbx, rsi
0x1800132a8  jmp     short loc_1800132BA
0x1800132aa  call    cs:__imp_GetLastError
0x1800132b0  xor     esi, esi
0x1800132b2  mov     r14d, eax
0x1800132b5  xor     eax, eax
0x1800132b7  mov     rbx, rbp
0x1800132ba  xor     edi, edi
0x1800132bc  test    rsi, rsi
0x1800132bf  cmovnz  edi, r14d
0x1800132c3  xor     esi, esi
0x1800132c5  test    rax, rax
0x1800132c8  cmovnz  rsi, rbp
0x1800132cc  test    rsi, rsi
0x1800132cf  jz      short loc_1800132F1
0x1800132d1  call    cs:__imp_GetProcessHeap
0x1800132d7  mov     r8, rsi; lpMem
0x1800132da  xor     edx, edx; dwFlags
0x1800132dc  mov     rcx, rax; hHeap
0x1800132df  call    cs:__imp_HeapFree
0x1800132e5  jmp     short loc_1800132F1
0x1800132e7  xor     ebx, ebx
0x1800132e9  call    cs:__imp_GetLastError
0x1800132ef  mov     edi, eax
0x1800132f1  mov     ecx, edi; dwErrCode
0x1800132f3  call    cs:__imp_SetLastError
0x1800132f9  mov     rax, rbx
0x1800132fc  jmp     short loc_18001330B
0x1800132fe  mov     ecx, 57h ; 'W'; dwErrCode
0x180013303  call    cs:__imp_SetLastError
0x180013309  xor     eax, eax
0x18001330b  add     rsp, 20h
0x18001330f  pop     r14
0x180013311  pop     rdi
0x180013312  pop     rsi
0x180013313  pop     rbp
0x180013314  pop     rbx
0x180013315  retn
```
