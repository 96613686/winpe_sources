# AslRegistryGetStringExpand

- ea: `0x18003d3ac`
- end: `0x18003d5c0`
- name: `AslRegistryGetStringExpand`
- size: `532`
- prototype: `__int64 __fastcall(wchar_t **, void *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180030810`

## callees

- `0x1800015d0`
- `0x18000f114`
- `0x180018f20`
- `0x18002b438`
- `0x18003c53c`
- `0x18003d3ac`

## import_xrefs

- `ntdll!wcschr` at `0x18003d3f6`
- `ntdll!wcschr` at `0x18003d3f6`
- `ntdll!RtlAllocateHeap` at `0x18003d466`
- `ntdll!RtlAllocateHeap` at `0x18003d504`
- `ntdll!RtlAllocateHeap` at `0x18003d466`
- `ntdll!RtlAllocateHeap` at `0x18003d504`

## string_xrefs

- `0x18003d42f`: `AslRegistryGetStringExpand`
- `0x18003d486`: `AslRegistryGetStringExpand`
- `0x18003d55f`: `AslRegistryGetStringExpand`

## pseudocode

```c
__int64 __fastcall AslRegistryGetStringExpand(wchar_t **a1, void *a2, const WCHAR *a3, __int64 a4)
{
  PVOID Heap; // rdi
  int String; // eax
  wchar_t *v8; // rsi
  int v9; // ebx
  int ProcessWowInfo; // eax
  __int64 v11; // r8
  __int16 v12; // r15
  __int16 v13; // r12
  wchar_t *v14; // rbx
  __int64 v16; // [rsp+28h] [rbp-30h]
  int v17; // [rsp+30h] [rbp-28h]
  __int16 v18[2]; // [rsp+40h] [rbp-18h] BYREF
  __int16 v19; // [rsp+44h] [rbp-14h] BYREF
  wchar_t *Str[2]; // [rsp+48h] [rbp-10h] BYREF

  Heap = 0;
  v18[0] = -1;
  Str[0] = 0;
  v19 = -1;
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
  ProcessWowInfo = AslEnvGetProcessWowInfo(&v19, v18);
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
    v12 = v18[0];
    v13 = v19;
    v9 = AslEnvExpandStrings2(a4, v8, Heap, 260, Str, v19, v18[0]);
    if ( v9 == -1073741789 )
    {
      AslFree(NtCurrentPeb()->ProcessHeap, Heap);
      v14 = Str[0];
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (__int64)Str[0]);
      if ( !Heap )
      {
        v11 = 1494;
        goto LABEL_8;
      }
      LOWORD(v17) = v12;
      LOWORD(v16) = v13;
      v9 = AslEnvExpandStrings2(a4, v8, Heap, v14, Str, v16, v17);
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
    AslFree(NtCurrentPeb()->ProcessHeap, v8);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003d3ac  push    rbp
0x18003d3ae  push    rbx
0x18003d3af  push    rsi
0x18003d3b0  push    rdi
0x18003d3b1  push    r12
0x18003d3b3  push    r13
0x18003d3b5  push    r14
0x18003d3b7  push    r15
0x18003d3b9  mov     rbp, rsp
0x18003d3bc  sub     rsp, 58h
0x18003d3c0  mov     eax, 0FFFFh
0x18003d3c5  mov     r14, rcx
0x18003d3c8  xor     edi, edi
0x18003d3ca  mov     [rbp+var_18], ax
0x18003d3ce  lea     rcx, [rbp+Str]
0x18003d3d2  mov     [rbp+Str], rdi
0x18003d3d6  mov     [rbp+var_14], ax
0x18003d3da  mov     r13, r9
0x18003d3dd  call    AslRegistryGetString
0x18003d3e2  mov     rsi, [rbp+Str]
0x18003d3e6  mov     ebx, eax
0x18003d3e8  test    eax, eax
0x18003d3ea  js      loc_18003D579
0x18003d3f0  lea     edx, [rdi+25h]; Ch
0x18003d3f3  mov     rcx, rsi; Str
0x18003d3f6  call    cs:__imp_wcschr
0x18003d3fc  test    rax, rax
0x18003d3ff  jnz     short loc_18003D40B
0x18003d401  mov     [r14], rsi
0x18003d404  xor     ebx, ebx
0x18003d406  jmp     loc_18003D5AD
0x18003d40b  lea     rdx, [rbp+var_18]
0x18003d40f  lea     rcx, [rbp+var_14]
0x18003d413  call    AslEnvGetProcessWowInfo
0x18003d418  mov     ebx, eax
0x18003d41a  test    eax, eax
0x18003d41c  jns     short loc_18003D445
0x18003d41e  lea     r9, aAslenvgetproce_1; "AslEnvGetProcessWowInfo failed [%x]"
0x18003d425  mov     dword ptr [rsp+58h+var_38], eax
0x18003d429  mov     r8d, 5B8h
0x18003d42f  lea     rdx, aAslregistryget_6; "AslRegistryGetStringExpand"
0x18003d436  mov     ecx, 1
0x18003d43b  call    AslLogCallPrintf
0x18003d440  jmp     loc_18003D579
0x18003d445  mov     rcx, gs:60h
0x18003d44e  mov     ebx, 104h
0x18003d453  mov     edx, 8; Flags
0x18003d458  mov     [rbp+Str], rbx
0x18003d45c  mov     r8d, 208h; Size
0x18003d462  mov     rcx, [rcx+30h]; HeapHandle
0x18003d466  call    cs:__imp_RtlAllocateHeap
0x18003d46c  mov     rdi, rax
0x18003d46f  test    rax, rax
0x18003d472  jnz     short loc_18003D49C
0x18003d474  mov     r8d, 5C4h
0x18003d47a  lea     r9, aOutOfMemory; "Out of memory"
0x18003d481  mov     ecx, 1
0x18003d486  lea     rdx, aAslregistryget_6; "AslRegistryGetStringExpand"
0x18003d48d  call    AslLogCallPrintf
0x18003d492  mov     ebx, 0C0000017h
0x18003d497  jmp     loc_18003D579
0x18003d49c  movzx   r15d, [rbp+var_18]
0x18003d4a1  lea     rax, [rbp+Str]
0x18003d4a5  movzx   r12d, [rbp+var_14]
0x18003d4aa  mov     r9, rbx
0x18003d4ad  mov     word ptr [rsp+58h+var_28], r15w
0x18003d4b3  mov     r8, rdi
0x18003d4b6  mov     word ptr [rsp+58h+var_30], r12w
0x18003d4bc  mov     rdx, rsi
0x18003d4bf  mov     rcx, r13
0x18003d4c2  mov     [rsp+58h+var_38], rax
0x18003d4c7  call    AslEnvExpandStrings2
0x18003d4cc  mov     ebx, eax
0x18003d4ce  cmp     eax, 0C0000023h
0x18003d4d3  jnz     short loc_18003D545
0x18003d4d5  mov     rcx, gs:60h
0x18003d4de  mov     rdx, rdi
0x18003d4e1  mov     rcx, [rcx+30h]
0x18003d4e5  call    AslFree
0x18003d4ea  mov     rcx, gs:60h
0x18003d4f3  mov     edx, 8; Flags
0x18003d4f8  mov     rbx, [rbp+Str]
0x18003d4fc  mov     rcx, [rcx+30h]; HeapHandle
0x18003d500  lea     r8, [rbx+rbx]; Size
0x18003d504  call    cs:__imp_RtlAllocateHeap
0x18003d50a  mov     rdi, rax
0x18003d50d  test    rax, rax
0x18003d510  jnz     short loc_18003D51D
0x18003d512  mov     r8d, 5D6h
0x18003d518  jmp     loc_18003D47A
0x18003d51d  mov     word ptr [rsp+58h+var_28], r15w
0x18003d523  lea     rax, [rbp+Str]
0x18003d527  mov     word ptr [rsp+58h+var_30], r12w
0x18003d52d  mov     r9, rbx
0x18003d530  mov     r8, rdi
0x18003d533  mov     [rsp+58h+var_38], rax
0x18003d538  mov     rdx, rsi
0x18003d53b  mov     rcx, r13
0x18003d53e  call    AslEnvExpandStrings2
0x18003d543  mov     ebx, eax
0x18003d545  test    ebx, ebx
0x18003d547  jns     short loc_18003D572
0x18003d549  mov     dword ptr [rsp+58h+var_30], ebx
0x18003d54d  lea     r9, aAslenvexpandst_1; "AslEnvExpandStrings2 failed to expand s"...
0x18003d554  mov     r8d, 5E5h
0x18003d55a  mov     [rsp+58h+var_38], rsi
0x18003d55f  lea     rdx, aAslregistryget_6; "AslRegistryGetStringExpand"
0x18003d566  mov     ecx, 1
0x18003d56b  call    AslLogCallPrintf
0x18003d570  jmp     short loc_18003D579
0x18003d572  mov     [r14], rdi
0x18003d575  xor     edi, edi
0x18003d577  xor     ebx, ebx
0x18003d579  test    rsi, rsi
0x18003d57c  jz      short loc_18003D593
0x18003d57e  mov     rcx, gs:60h
0x18003d587  mov     rdx, rsi
0x18003d58a  mov     rcx, [rcx+30h]
0x18003d58e  call    AslFree
0x18003d593  test    rdi, rdi
0x18003d596  jz      short loc_18003D5AD
0x18003d598  mov     rcx, gs:60h
0x18003d5a1  mov     rdx, rdi
0x18003d5a4  mov     rcx, [rcx+30h]
0x18003d5a8  call    AslFree
0x18003d5ad  mov     eax, ebx
0x18003d5af  add     rsp, 58h
0x18003d5b3  pop     r15
0x18003d5b5  pop     r14
0x18003d5b7  pop     r13
0x18003d5b9  pop     r12
0x18003d5bb  pop     rdi
0x18003d5bc  pop     rsi
0x18003d5bd  pop     rbx
0x18003d5be  pop     rbp
0x18003d5bf  retn
```
