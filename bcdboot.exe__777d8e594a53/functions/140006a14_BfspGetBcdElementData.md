# BfspGetBcdElementData

- ea: `0x140006a14`
- end: `0x140006aff`
- name: `BfspGetBcdElementData`
- size: `235`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *, _DWORD *)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x140004828`
- `0x140005100`
- `0x1400052bc`
- `0x14000619c`
- `0x140006b08`
- `0x1400074f4`
- `0x1400078f4`
- `0x140008400`
- `0x140008c74`
- `0x140008e68`
- `0x140009094`
- `0x140009170`
- `0x140009528`
- `0x140009658`

## callees

- `0x140006a14`
- `0x14000e628`
- `0x140018890`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140006acc`
- `KERNEL32!HeapFree` at `0x140006acc`
- `KERNEL32!HeapAlloc` at `0x140006a71`
- `KERNEL32!HeapAlloc` at `0x140006a71`
- `KERNEL32!GetProcessHeap` at `0x140006a60`
- `KERNEL32!GetProcessHeap` at `0x140006abe`
- `KERNEL32!GetProcessHeap` at `0x140006a60`
- `KERNEL32!GetProcessHeap` at `0x140006abe`

## pseudocode

```c
__int64 __fastcall BfspGetBcdElementData(__int64 a1, unsigned int a2, _QWORD *a3, _DWORD *a4)
{
  int ElementDataWithFlags; // ebx
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  void *v11; // rdi
  __int64 v12; // r8
  int v13; // esi
  int v14; // eax
  HANDLE v15; // rax
  __int64 result; // rax
  SIZE_T dwBytes; // [rsp+80h] [rbp+18h] BYREF

  LODWORD(dwBytes) = 0;
  ElementDataWithFlags = BcdGetElementDataWithFlags(a1, a2, (__int64)a3, 0, &dwBytes);
  if ( ElementDataWithFlags != -1073741789 || !(_DWORD)dwBytes )
  {
    v13 = 0;
    if ( ElementDataWithFlags >= 0 )
      ElementDataWithFlags = -1073741823;
    goto LABEL_10;
  }
  v9 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, v9);
  if ( v11 )
  {
    v14 = BcdGetElementDataWithFlags(a1, a2, v12, (__int64)v11, &dwBytes);
    ElementDataWithFlags = v14;
    if ( v14 >= 0 )
    {
      v13 = dwBytes;
      goto LABEL_11;
    }
    BfspLogMessage(4, L"Failed to get element data. Status = [%x]", (unsigned int)v14);
    v13 = 0;
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v11);
LABEL_10:
    v11 = 0;
    goto LABEL_11;
  }
  ElementDataWithFlags = -1073741801;
  v13 = 0;
LABEL_11:
  *a3 = v11;
  result = (unsigned int)ElementDataWithFlags;
  *a4 = v13;
  return result;
}

```

## disassembly

```asm
0x140006a14  mov     rax, rsp
0x140006a17  push    rbx
0x140006a18  push    rbp
0x140006a19  push    rsi
0x140006a1a  push    rdi
0x140006a1b  push    r14
0x140006a1d  push    r15
0x140006a1f  sub     rsp, 38h
0x140006a23  mov     dword ptr [rax+18h], 0
0x140006a2a  lea     rax, [rax+18h]
0x140006a2e  mov     r14, r9
0x140006a31  mov     [rsp+68h+var_48], rax
0x140006a36  xor     r9d, r9d
0x140006a39  mov     r15, r8
0x140006a3c  mov     esi, edx
0x140006a3e  mov     rbp, rcx
0x140006a41  call    BcdGetElementDataWithFlags
0x140006a46  mov     ebx, eax
0x140006a48  cmp     eax, 0C0000023h
0x140006a4d  jnz     loc_140006ADD
0x140006a53  mov     eax, dword ptr [rsp+68h+dwBytes]
0x140006a5a  test    eax, eax
0x140006a5c  jz      short loc_140006ADD
0x140006a5e  mov     ebx, eax
0x140006a60  call    cs:__imp_GetProcessHeap
0x140006a66  mov     r8d, ebx; dwBytes
0x140006a69  mov     edx, 8; dwFlags
0x140006a6e  mov     rcx, rax; hHeap
0x140006a71  call    cs:__imp_HeapAlloc
0x140006a77  mov     rdi, rax
0x140006a7a  test    rax, rax
0x140006a7d  jnz     short loc_140006A88
0x140006a7f  mov     ebx, 0C0000017h
0x140006a84  xor     esi, esi
0x140006a86  jmp     short loc_140006AEA
0x140006a88  lea     rax, [rsp+68h+dwBytes]
0x140006a90  mov     r9, rdi
0x140006a93  mov     edx, esi
0x140006a95  mov     [rsp+68h+var_48], rax
0x140006a9a  mov     rcx, rbp
0x140006a9d  call    BcdGetElementDataWithFlags
0x140006aa2  mov     ebx, eax
0x140006aa4  test    eax, eax
0x140006aa6  jns     short loc_140006AD4
0x140006aa8  mov     r8d, eax
0x140006aab  lea     rdx, aFailedToGetEle_2; "Failed to get element data. Status = [%"...
0x140006ab2  mov     ecx, 4
0x140006ab7  call    BfspLogMessage
0x140006abc  xor     esi, esi
0x140006abe  call    cs:__imp_GetProcessHeap
0x140006ac4  mov     r8, rdi; lpMem
0x140006ac7  xor     edx, edx; dwFlags
0x140006ac9  mov     rcx, rax; hHeap
0x140006acc  call    cs:__imp_HeapFree
0x140006ad2  jmp     short loc_140006AE8
0x140006ad4  mov     esi, dword ptr [rsp+68h+dwBytes]
0x140006adb  jmp     short loc_140006AEA
0x140006add  xor     esi, esi
0x140006adf  test    ebx, ebx
0x140006ae1  js      short loc_140006AE8
0x140006ae3  mov     ebx, 0C0000001h
0x140006ae8  xor     edi, edi
0x140006aea  mov     [r15], rdi
0x140006aed  mov     eax, ebx
0x140006aef  mov     [r14], esi
0x140006af2  add     rsp, 38h
0x140006af6  pop     r15
0x140006af8  pop     r14
0x140006afa  pop     rdi
0x140006afb  pop     rsi
0x140006afc  pop     rbp
0x140006afd  pop     rbx
0x140006afe  retn
```
