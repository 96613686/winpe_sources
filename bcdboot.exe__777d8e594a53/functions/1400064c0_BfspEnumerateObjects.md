# BfspEnumerateObjects

- ea: `0x1400064c0`
- end: `0x140006598`
- name: `BfspEnumerateObjects`
- size: `216`
- prototype: `__int64 __fastcall(int, int, _DWORD *, _QWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140003d30`
- `0x140004828`
- `0x1400078f4`
- `0x140007e20`
- `0x140008104`

## callees

- `0x1400064c0`
- `0x14000e628`
- `0x140013c1c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000651c`
- `KERNEL32!HeapFree` at `0x140006577`
- `KERNEL32!HeapFree` at `0x14000651c`
- `KERNEL32!HeapFree` at `0x140006577`
- `KERNEL32!HeapAlloc` at `0x140006537`
- `KERNEL32!HeapAlloc` at `0x140006537`
- `KERNEL32!GetProcessHeap` at `0x14000650e`
- `KERNEL32!GetProcessHeap` at `0x140006526`
- `KERNEL32!GetProcessHeap` at `0x140006569`
- `KERNEL32!GetProcessHeap` at `0x14000650e`
- `KERNEL32!GetProcessHeap` at `0x140006526`
- `KERNEL32!GetProcessHeap` at `0x140006569`

## pseudocode

```c
__int64 __fastcall BfspEnumerateObjects(int a1, int a2, _DWORD *a3, _QWORD *a4)
{
  void *v4; // rbx
  int v9; // eax
  unsigned int v10; // edi
  HANDLE ProcessHeap; // rax
  unsigned int v12; // ebx
  HANDLE v13; // rax
  HANDLE v14; // rax
  SIZE_T dwBytes[9]; // [rsp+30h] [rbp-48h] BYREF

  v4 = 0;
  dwBytes[0] = 0;
  while ( 1 )
  {
    v9 = BcdEnumerateObjects(a1, a2, (_DWORD)v4, (unsigned int)dwBytes, (__int64)dwBytes + 4);
    v10 = v9;
    if ( v9 != -1073741789 )
      break;
    if ( v4 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    v12 = dwBytes[0];
    v13 = GetProcessHeap();
    v4 = HeapAlloc(v13, 8u, v12);
    if ( !v4 )
      return (unsigned int)-1073741801;
  }
  if ( v9 >= 0 )
  {
    *a3 = HIDWORD(dwBytes[0]);
    *a4 = v4;
  }
  else
  {
    BfspLogMessage(4, L"Failed to enumerate BCD objects. Status = [%x]", (unsigned int)v9);
    if ( v4 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v4);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1400064c0  push    rbx
0x1400064c2  push    rbp
0x1400064c3  push    rsi
0x1400064c4  push    rdi
0x1400064c5  push    r14
0x1400064c7  push    r15
0x1400064c9  sub     rsp, 48h
0x1400064cd  xor     ebx, ebx
0x1400064cf  mov     rsi, r9
0x1400064d2  mov     dword ptr [rsp+78h+dwBytes+4], ebx
0x1400064d6  mov     r14, r8
0x1400064d9  mov     dword ptr [rsp+78h+dwBytes], ebx
0x1400064dd  mov     rbp, rdx
0x1400064e0  mov     r15, rcx
0x1400064e3  lea     rax, [rsp+78h+dwBytes+4]
0x1400064e8  mov     r8, rbx
0x1400064eb  lea     r9, [rsp+78h+dwBytes]
0x1400064f0  mov     [rsp+78h+var_58], rax
0x1400064f5  mov     rdx, rbp
0x1400064f8  mov     rcx, r15
0x1400064fb  call    BcdEnumerateObjects
0x140006500  mov     edi, eax
0x140006502  cmp     eax, 0C0000023h
0x140006507  jnz     short loc_14000654C
0x140006509  test    rbx, rbx
0x14000650c  jz      short loc_140006522
0x14000650e  call    cs:__imp_GetProcessHeap
0x140006514  mov     r8, rbx; lpMem
0x140006517  xor     edx, edx; dwFlags
0x140006519  mov     rcx, rax; hHeap
0x14000651c  call    cs:__imp_HeapFree
0x140006522  mov     ebx, dword ptr [rsp+78h+dwBytes]
0x140006526  call    cs:__imp_GetProcessHeap
0x14000652c  mov     r8d, ebx; dwBytes
0x14000652f  mov     edx, 8; dwFlags
0x140006534  mov     rcx, rax; hHeap
0x140006537  call    cs:__imp_HeapAlloc
0x14000653d  mov     rbx, rax
0x140006540  test    rax, rax
0x140006543  jnz     short loc_1400064E3
0x140006545  mov     edi, 0C0000017h
0x14000654a  jmp     short loc_140006589
0x14000654c  test    eax, eax
0x14000654e  jns     short loc_14000657F
0x140006550  mov     r8d, eax
0x140006553  lea     rdx, aFailedToEnumer_4; "Failed to enumerate BCD objects. Status"...
0x14000655a  mov     ecx, 4
0x14000655f  call    BfspLogMessage
0x140006564  test    rbx, rbx
0x140006567  jz      short loc_140006589
0x140006569  call    cs:__imp_GetProcessHeap
0x14000656f  mov     r8, rbx; lpMem
0x140006572  xor     edx, edx; dwFlags
0x140006574  mov     rcx, rax; hHeap
0x140006577  call    cs:__imp_HeapFree
0x14000657d  jmp     short loc_140006589
0x14000657f  mov     eax, dword ptr [rsp+78h+dwBytes+4]
0x140006583  mov     [r14], eax
0x140006586  mov     [rsi], rbx
0x140006589  mov     eax, edi
0x14000658b  add     rsp, 48h
0x14000658f  pop     r15
0x140006591  pop     r14
0x140006593  pop     rdi
0x140006594  pop     rsi
0x140006595  pop     rbp
0x140006596  pop     rbx
0x140006597  retn
```
