# AslRegistryGetStringExpand

- ea: `0x18004c6c8`
- end: `0x18004c8e5`
- name: `AslRegistryGetStringExpand`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180049234`

## callees

- `0x18004a7a8`
- `0x18004a9c0`
- `0x18004c020`
- `0x18004c4fc`
- `0x18004c6c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004c712`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004c712`
- `ntdll!RtlAllocateHeap` at `0x18004c782`
- `ntdll!RtlAllocateHeap` at `0x18004c823`
- `ntdll!RtlAllocateHeap` at `0x18004c782`
- `ntdll!RtlAllocateHeap` at `0x18004c823`
- `ntdll!RtlFreeHeap` at `0x18004c803`
- `ntdll!RtlFreeHeap` at `0x18004c8af`
- `ntdll!RtlFreeHeap` at `0x18004c8cc`
- `ntdll!RtlFreeHeap` at `0x18004c803`
- `ntdll!RtlFreeHeap` at `0x18004c8af`
- `ntdll!RtlFreeHeap` at `0x18004c8cc`

## string_xrefs

- `0x18004c74b`: `AslRegistryGetStringExpand`
- `0x18004c7a2`: `AslRegistryGetStringExpand`
- `0x18004c87e`: `AslRegistryGetStringExpand`

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
0x18004c6c8  push    rbp
0x18004c6ca  push    rbx
0x18004c6cb  push    rsi
0x18004c6cc  push    rdi
0x18004c6cd  push    r12
0x18004c6cf  push    r13
0x18004c6d1  push    r14
0x18004c6d3  push    r15
0x18004c6d5  mov     rbp, rsp
0x18004c6d8  sub     rsp, 58h
0x18004c6dc  mov     eax, 0FFFFh
0x18004c6e1  mov     r14, rcx
0x18004c6e4  xor     edi, edi
0x18004c6e6  mov     [rbp+var_18], ax
0x18004c6ea  lea     rcx, [rbp+Str]
0x18004c6ee  mov     [rbp+Str], rdi
0x18004c6f2  mov     [rbp+var_14], ax
0x18004c6f6  mov     r13, r9
0x18004c6f9  call    AslRegistryGetString
0x18004c6fe  mov     rsi, [rbp+Str]
0x18004c702  mov     ebx, eax
0x18004c704  test    eax, eax
0x18004c706  js      loc_18004C898
0x18004c70c  lea     edx, [rdi+25h]; Ch
0x18004c70f  mov     rcx, rsi; Str
0x18004c712  call    cs:__imp_wcschr
0x18004c718  test    rax, rax
0x18004c71b  jnz     short loc_18004C727
0x18004c71d  mov     [r14], rsi
0x18004c720  xor     ebx, ebx
0x18004c722  jmp     loc_18004C8D2
0x18004c727  lea     rdx, [rbp+var_18]
0x18004c72b  lea     rcx, [rbp+var_14]
0x18004c72f  call    AslEnvGetProcessWowInfo
0x18004c734  mov     ebx, eax
0x18004c736  test    eax, eax
0x18004c738  jns     short loc_18004C761
0x18004c73a  lea     r9, aAslenvgetproce_0; "AslEnvGetProcessWowInfo failed [%x]"
0x18004c741  mov     dword ptr [rsp+58h+var_38], eax
0x18004c745  mov     r8d, 5B8h
0x18004c74b  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x18004c752  mov     ecx, 1
0x18004c757  call    AslLogCallPrintf
0x18004c75c  jmp     loc_18004C898
0x18004c761  mov     rcx, gs:60h
0x18004c76a  mov     ebx, 104h
0x18004c76f  mov     edx, 8; Flags
0x18004c774  mov     [rbp+Str], rbx
0x18004c778  mov     r8d, 208h; Size
0x18004c77e  mov     rcx, [rcx+30h]; HeapHandle
0x18004c782  call    cs:__imp_RtlAllocateHeap
0x18004c788  mov     rdi, rax
0x18004c78b  test    rax, rax
0x18004c78e  jnz     short loc_18004C7B8
0x18004c790  mov     r8d, 5C4h
0x18004c796  lea     r9, aOutOfMemory_0; "Out of memory"
0x18004c79d  mov     ecx, 1
0x18004c7a2  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x18004c7a9  call    AslLogCallPrintf
0x18004c7ae  mov     ebx, 0C0000017h
0x18004c7b3  jmp     loc_18004C898
0x18004c7b8  movzx   r15d, [rbp+var_18]
0x18004c7bd  lea     rax, [rbp+Str]
0x18004c7c1  movzx   r12d, [rbp+var_14]
0x18004c7c6  mov     r9, rbx
0x18004c7c9  mov     [rsp+58h+var_28], r15w
0x18004c7cf  mov     r8, rdi
0x18004c7d2  mov     word ptr [rsp+58h+var_30], r12w
0x18004c7d8  mov     rdx, rsi
0x18004c7db  mov     rcx, r13
0x18004c7de  mov     [rsp+58h+var_38], rax
0x18004c7e3  call    AslEnvExpandStrings2
0x18004c7e8  mov     ebx, eax
0x18004c7ea  cmp     eax, 0C0000023h
0x18004c7ef  jnz     short loc_18004C864
0x18004c7f1  mov     rcx, gs:60h
0x18004c7fa  mov     r8, rdi; P
0x18004c7fd  xor     edx, edx; Flags
0x18004c7ff  mov     rcx, [rcx+30h]; HeapHandle
0x18004c803  call    cs:__imp_RtlFreeHeap
0x18004c809  mov     rcx, gs:60h
0x18004c812  mov     edx, 8; Flags
0x18004c817  mov     rbx, [rbp+Str]
0x18004c81b  mov     rcx, [rcx+30h]; HeapHandle
0x18004c81f  lea     r8, [rbx+rbx]; Size
0x18004c823  call    cs:__imp_RtlAllocateHeap
0x18004c829  mov     rdi, rax
0x18004c82c  test    rax, rax
0x18004c82f  jnz     short loc_18004C83C
0x18004c831  mov     r8d, 5D6h
0x18004c837  jmp     loc_18004C796
0x18004c83c  mov     [rsp+58h+var_28], r15w
0x18004c842  lea     rax, [rbp+Str]
0x18004c846  mov     word ptr [rsp+58h+var_30], r12w
0x18004c84c  mov     r9, rbx
0x18004c84f  mov     r8, rdi
0x18004c852  mov     [rsp+58h+var_38], rax
0x18004c857  mov     rdx, rsi
0x18004c85a  mov     rcx, r13
0x18004c85d  call    AslEnvExpandStrings2
0x18004c862  mov     ebx, eax
0x18004c864  test    ebx, ebx
0x18004c866  jns     short loc_18004C891
0x18004c868  mov     dword ptr [rsp+58h+var_30], ebx
0x18004c86c  lea     r9, aAslenvexpandst_0; "AslEnvExpandStrings2 failed to expand s"...
0x18004c873  mov     r8d, 5E5h
0x18004c879  mov     [rsp+58h+var_38], rsi
0x18004c87e  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x18004c885  mov     ecx, 1
0x18004c88a  call    AslLogCallPrintf
0x18004c88f  jmp     short loc_18004C898
0x18004c891  mov     [r14], rdi
0x18004c894  xor     edi, edi
0x18004c896  xor     ebx, ebx
0x18004c898  test    rsi, rsi
0x18004c89b  jz      short loc_18004C8B5
0x18004c89d  mov     rcx, gs:60h
0x18004c8a6  mov     r8, rsi; P
0x18004c8a9  xor     edx, edx; Flags
0x18004c8ab  mov     rcx, [rcx+30h]; HeapHandle
0x18004c8af  call    cs:__imp_RtlFreeHeap
0x18004c8b5  test    rdi, rdi
0x18004c8b8  jz      short loc_18004C8D2
0x18004c8ba  mov     rcx, gs:60h
0x18004c8c3  mov     r8, rdi; P
0x18004c8c6  xor     edx, edx; Flags
0x18004c8c8  mov     rcx, [rcx+30h]; HeapHandle
0x18004c8cc  call    cs:__imp_RtlFreeHeap
0x18004c8d2  mov     eax, ebx
0x18004c8d4  add     rsp, 58h
0x18004c8d8  pop     r15
0x18004c8da  pop     r14
0x18004c8dc  pop     r13
0x18004c8de  pop     r12
0x18004c8e0  pop     rdi
0x18004c8e1  pop     rsi
0x18004c8e2  pop     rbx
0x18004c8e3  pop     rbp
0x18004c8e4  retn
```
