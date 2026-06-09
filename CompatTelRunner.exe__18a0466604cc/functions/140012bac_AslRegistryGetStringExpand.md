# AslRegistryGetStringExpand

- ea: `0x140012bac`
- end: `0x140012dc9`
- name: `AslRegistryGetStringExpand`
- size: `541`
- prototype: `__int64 __fastcall(wchar_t **, void *, const WCHAR *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140016744`

## callees

- `0x1400129e0`
- `0x140012bac`
- `0x1400151b0`
- `0x140017cb8`
- `0x140017ed0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140012bf6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140012bf6`
- `ntdll!RtlFreeHeap` at `0x140012ce7`
- `ntdll!RtlFreeHeap` at `0x140012d93`
- `ntdll!RtlFreeHeap` at `0x140012db0`
- `ntdll!RtlFreeHeap` at `0x140012ce7`
- `ntdll!RtlFreeHeap` at `0x140012d93`
- `ntdll!RtlFreeHeap` at `0x140012db0`
- `ntdll!RtlAllocateHeap` at `0x140012c66`
- `ntdll!RtlAllocateHeap` at `0x140012d07`
- `ntdll!RtlAllocateHeap` at `0x140012c66`
- `ntdll!RtlAllocateHeap` at `0x140012d07`

## string_xrefs

- `0x140012c2f`: `AslRegistryGetStringExpand`
- `0x140012c86`: `AslRegistryGetStringExpand`
- `0x140012d62`: `AslRegistryGetStringExpand`

## pseudocode

```c
__int64 __fastcall AslRegistryGetStringExpand(wchar_t **a1, void *a2, const WCHAR *a3, int a4)
{
  PVOID Heap; // rdi
  int String; // eax
  wchar_t *v8; // rsi
  int v9; // ebx
  int ProcessWowInfo; // eax
  __int64 v11; // r8
  __int16 v12; // r15
  __int16 v13; // r12
  int v14; // ebx
  __int64 v16; // [rsp+28h] [rbp-30h]
  __int16 v17[2]; // [rsp+40h] [rbp-18h] BYREF
  __int16 v18; // [rsp+44h] [rbp-14h] BYREF
  wchar_t *Str[2]; // [rsp+48h] [rbp-10h] BYREF

  Heap = 0;
  v17[0] = -1;
  Str[0] = 0;
  v18 = -1;
  String = AslRegistryGetString(Str, a2, a3);
  v8 = Str[0];
  v9 = String;
  if ( String < 0 )
    goto LABEL_16;
  if ( !wcschr(Str[0], 0x25u) )
  {
    *a1 = v8;
    return 0;
  }
  ProcessWowInfo = AslEnvGetProcessWowInfo(&v18, v17);
  v9 = ProcessWowInfo;
  if ( ProcessWowInfo >= 0 )
  {
    Str[0] = (wchar_t *)260;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
    if ( !Heap )
    {
      v11 = 1476;
LABEL_8:
      AslLogCallPrintf(1, "AslRegistryGetStringExpand", v11, "Out of memory");
      v9 = -1073741801;
      goto LABEL_16;
    }
    v12 = v17[0];
    v13 = v18;
    v9 = AslEnvExpandStrings2(a4, (_DWORD)v8, (_DWORD)Heap, 260, (__int64)Str, v18, v17[0]);
    if ( v9 == -1073741789 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v14 = (int)Str[0];
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (__int64)Str[0]);
      if ( !Heap )
      {
        v11 = 1494;
        goto LABEL_8;
      }
      v9 = AslEnvExpandStrings2(a4, (_DWORD)v8, (_DWORD)Heap, v14, (__int64)Str, v13, v12);
    }
    if ( v9 >= 0 )
    {
      *a1 = (wchar_t *)Heap;
      Heap = 0;
      v9 = 0;
    }
    else
    {
      LODWORD(v16) = v9;
      AslLogCallPrintf(
        1,
        "AslRegistryGetStringExpand",
        1509,
        "AslEnvExpandStrings2 failed to expand strings for %ws [%x]",
        v8,
        v16);
    }
    goto LABEL_16;
  }
  AslLogCallPrintf(1, "AslRegistryGetStringExpand", 1464, "AslEnvGetProcessWowInfo failed [%x]", ProcessWowInfo);
LABEL_16:
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140012bac  push    rbp
0x140012bae  push    rbx
0x140012baf  push    rsi
0x140012bb0  push    rdi
0x140012bb1  push    r12
0x140012bb3  push    r13
0x140012bb5  push    r14
0x140012bb7  push    r15
0x140012bb9  mov     rbp, rsp
0x140012bbc  sub     rsp, 58h
0x140012bc0  mov     eax, 0FFFFh
0x140012bc5  mov     r14, rcx
0x140012bc8  xor     edi, edi
0x140012bca  mov     [rbp+var_18], ax
0x140012bce  lea     rcx, [rbp+Str]
0x140012bd2  mov     [rbp+Str], rdi
0x140012bd6  mov     [rbp+var_14], ax
0x140012bda  mov     r13, r9
0x140012bdd  call    AslRegistryGetString
0x140012be2  mov     rsi, [rbp+Str]
0x140012be6  mov     ebx, eax
0x140012be8  test    eax, eax
0x140012bea  js      loc_140012D7C
0x140012bf0  lea     edx, [rdi+25h]; Ch
0x140012bf3  mov     rcx, rsi; Str
0x140012bf6  call    cs:__imp_wcschr
0x140012bfc  test    rax, rax
0x140012bff  jnz     short loc_140012C0B
0x140012c01  mov     [r14], rsi
0x140012c04  xor     ebx, ebx
0x140012c06  jmp     loc_140012DB6
0x140012c0b  lea     rdx, [rbp+var_18]
0x140012c0f  lea     rcx, [rbp+var_14]
0x140012c13  call    AslEnvGetProcessWowInfo
0x140012c18  mov     ebx, eax
0x140012c1a  test    eax, eax
0x140012c1c  jns     short loc_140012C45
0x140012c1e  lea     r9, aAslenvgetproce_0; "AslEnvGetProcessWowInfo failed [%x]"
0x140012c25  mov     dword ptr [rsp+58h+var_38], eax
0x140012c29  mov     r8d, 5B8h
0x140012c2f  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x140012c36  mov     ecx, 1
0x140012c3b  call    AslLogCallPrintf
0x140012c40  jmp     loc_140012D7C
0x140012c45  mov     rcx, gs:60h
0x140012c4e  mov     ebx, 104h
0x140012c53  mov     edx, 8; Flags
0x140012c58  mov     [rbp+Str], rbx
0x140012c5c  mov     r8d, 208h; Size
0x140012c62  mov     rcx, [rcx+30h]; HeapHandle
0x140012c66  call    cs:__imp_RtlAllocateHeap
0x140012c6c  mov     rdi, rax
0x140012c6f  test    rax, rax
0x140012c72  jnz     short loc_140012C9C
0x140012c74  mov     r8d, 5C4h
0x140012c7a  lea     r9, aOutOfMemory_0; "Out of memory"
0x140012c81  mov     ecx, 1
0x140012c86  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x140012c8d  call    AslLogCallPrintf
0x140012c92  mov     ebx, 0C0000017h
0x140012c97  jmp     loc_140012D7C
0x140012c9c  movzx   r15d, [rbp+var_18]
0x140012ca1  lea     rax, [rbp+Str]
0x140012ca5  movzx   r12d, [rbp+var_14]
0x140012caa  mov     r9, rbx
0x140012cad  mov     [rsp+58h+var_28], r15w
0x140012cb3  mov     r8, rdi
0x140012cb6  mov     word ptr [rsp+58h+var_30], r12w
0x140012cbc  mov     rdx, rsi
0x140012cbf  mov     rcx, r13
0x140012cc2  mov     [rsp+58h+var_38], rax
0x140012cc7  call    AslEnvExpandStrings2
0x140012ccc  mov     ebx, eax
0x140012cce  cmp     eax, 0C0000023h
0x140012cd3  jnz     short loc_140012D48
0x140012cd5  mov     rcx, gs:60h
0x140012cde  mov     r8, rdi; P
0x140012ce1  xor     edx, edx; Flags
0x140012ce3  mov     rcx, [rcx+30h]; HeapHandle
0x140012ce7  call    cs:__imp_RtlFreeHeap
0x140012ced  mov     rcx, gs:60h
0x140012cf6  mov     edx, 8; Flags
0x140012cfb  mov     rbx, [rbp+Str]
0x140012cff  mov     rcx, [rcx+30h]; HeapHandle
0x140012d03  lea     r8, [rbx+rbx]; Size
0x140012d07  call    cs:__imp_RtlAllocateHeap
0x140012d0d  mov     rdi, rax
0x140012d10  test    rax, rax
0x140012d13  jnz     short loc_140012D20
0x140012d15  mov     r8d, 5D6h
0x140012d1b  jmp     loc_140012C7A
0x140012d20  mov     [rsp+58h+var_28], r15w
0x140012d26  lea     rax, [rbp+Str]
0x140012d2a  mov     word ptr [rsp+58h+var_30], r12w
0x140012d30  mov     r9, rbx
0x140012d33  mov     r8, rdi
0x140012d36  mov     [rsp+58h+var_38], rax
0x140012d3b  mov     rdx, rsi
0x140012d3e  mov     rcx, r13
0x140012d41  call    AslEnvExpandStrings2
0x140012d46  mov     ebx, eax
0x140012d48  test    ebx, ebx
0x140012d4a  jns     short loc_140012D75
0x140012d4c  mov     dword ptr [rsp+58h+var_30], ebx
0x140012d50  lea     r9, aAslenvexpandst_0; "AslEnvExpandStrings2 failed to expand s"...
0x140012d57  mov     r8d, 5E5h
0x140012d5d  mov     [rsp+58h+var_38], rsi
0x140012d62  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x140012d69  mov     ecx, 1
0x140012d6e  call    AslLogCallPrintf
0x140012d73  jmp     short loc_140012D7C
0x140012d75  mov     [r14], rdi
0x140012d78  xor     edi, edi
0x140012d7a  xor     ebx, ebx
0x140012d7c  test    rsi, rsi
0x140012d7f  jz      short loc_140012D99
0x140012d81  mov     rcx, gs:60h
0x140012d8a  mov     r8, rsi; P
0x140012d8d  xor     edx, edx; Flags
0x140012d8f  mov     rcx, [rcx+30h]; HeapHandle
0x140012d93  call    cs:__imp_RtlFreeHeap
0x140012d99  test    rdi, rdi
0x140012d9c  jz      short loc_140012DB6
0x140012d9e  mov     rcx, gs:60h
0x140012da7  mov     r8, rdi; P
0x140012daa  xor     edx, edx; Flags
0x140012dac  mov     rcx, [rcx+30h]; HeapHandle
0x140012db0  call    cs:__imp_RtlFreeHeap
0x140012db6  mov     eax, ebx
0x140012db8  add     rsp, 58h
0x140012dbc  pop     r15
0x140012dbe  pop     r14
0x140012dc0  pop     r13
0x140012dc2  pop     r12
0x140012dc4  pop     rdi
0x140012dc5  pop     rsi
0x140012dc6  pop     rbx
0x140012dc7  pop     rbp
0x140012dc8  retn
```
