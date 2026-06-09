# AslRegistryGetStringExpand

- ea: `0x180029b64`
- end: `0x180029d78`
- name: `AslRegistryGetStringExpand`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18002e270`

## callees

- `0x1800295dc`
- `0x18002979c`
- `0x18002999c`
- `0x180029b64`
- `0x18002f968`
- `0x18002fb68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180029bae`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180029bae`
- `ntdll!RtlAllocateHeap` at `0x180029c1e`
- `ntdll!RtlAllocateHeap` at `0x180029cbc`
- `ntdll!RtlAllocateHeap` at `0x180029c1e`
- `ntdll!RtlAllocateHeap` at `0x180029cbc`

## string_xrefs

- `0x180029be7`: `AslRegistryGetStringExpand`
- `0x180029c3e`: `AslRegistryGetStringExpand`
- `0x180029d17`: `AslRegistryGetStringExpand`

## pseudocode

```c
__int64 __fastcall AslRegistryGetStringExpand(wchar_t **a1, void *a2, const WCHAR *a3, int a4)
{
  wchar_t *Heap; // rdi
  int String; // eax
  wchar_t *v8; // rsi
  int v9; // ebx
  int ProcessWowInfo; // eax
  __int64 v11; // r8
  __int16 v12; // r15
  __int16 v13; // r12
  wchar_t *v14; // rbx
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
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
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
    v9 = AslEnvExpandStrings2(a4, v8, Heap, 260, Str, v18, v17[0]);
    if ( v9 == -1073741789 )
    {
      AslFree(NtCurrentPeb()->ProcessHeap, Heap);
      v14 = Str[0];
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (__int64)Str[0]);
      if ( !Heap )
      {
        v11 = 1494;
        goto LABEL_8;
      }
      v9 = AslEnvExpandStrings2(a4, v8, Heap, (__int64)v14, Str, v13, v12);
    }
    if ( v9 >= 0 )
    {
      *a1 = Heap;
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
0x180029b64  push    rbp
0x180029b66  push    rbx
0x180029b67  push    rsi
0x180029b68  push    rdi
0x180029b69  push    r12
0x180029b6b  push    r13
0x180029b6d  push    r14
0x180029b6f  push    r15
0x180029b71  mov     rbp, rsp
0x180029b74  sub     rsp, 58h
0x180029b78  mov     eax, 0FFFFh
0x180029b7d  mov     r14, rcx
0x180029b80  xor     edi, edi
0x180029b82  mov     [rbp+var_18], ax
0x180029b86  lea     rcx, [rbp+Str]
0x180029b8a  mov     [rbp+Str], rdi
0x180029b8e  mov     [rbp+var_14], ax
0x180029b92  mov     r13, r9
0x180029b95  call    AslRegistryGetString
0x180029b9a  mov     rsi, [rbp+Str]
0x180029b9e  mov     ebx, eax
0x180029ba0  test    eax, eax
0x180029ba2  js      loc_180029D31
0x180029ba8  lea     edx, [rdi+25h]; Ch
0x180029bab  mov     rcx, rsi; Str
0x180029bae  call    cs:__imp_wcschr
0x180029bb4  test    rax, rax
0x180029bb7  jnz     short loc_180029BC3
0x180029bb9  mov     [r14], rsi
0x180029bbc  xor     ebx, ebx
0x180029bbe  jmp     loc_180029D65
0x180029bc3  lea     rdx, [rbp+var_18]
0x180029bc7  lea     rcx, [rbp+var_14]
0x180029bcb  call    AslEnvGetProcessWowInfo
0x180029bd0  mov     ebx, eax
0x180029bd2  test    eax, eax
0x180029bd4  jns     short loc_180029BFD
0x180029bd6  lea     r9, aAslenvgetproce_0; "AslEnvGetProcessWowInfo failed [%x]"
0x180029bdd  mov     dword ptr [rsp+58h+var_38], eax
0x180029be1  mov     r8d, 5B8h
0x180029be7  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x180029bee  mov     ecx, 1
0x180029bf3  call    AslLogCallPrintf
0x180029bf8  jmp     loc_180029D31
0x180029bfd  mov     rcx, gs:60h
0x180029c06  mov     ebx, 104h
0x180029c0b  mov     edx, 8; Flags
0x180029c10  mov     [rbp+Str], rbx
0x180029c14  mov     r8d, 208h; Size
0x180029c1a  mov     rcx, [rcx+30h]; HeapHandle
0x180029c1e  call    cs:__imp_RtlAllocateHeap
0x180029c24  mov     rdi, rax
0x180029c27  test    rax, rax
0x180029c2a  jnz     short loc_180029C54
0x180029c2c  mov     r8d, 5C4h
0x180029c32  lea     r9, aOutOfMemory_0; "Out of memory"
0x180029c39  mov     ecx, 1
0x180029c3e  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x180029c45  call    AslLogCallPrintf
0x180029c4a  mov     ebx, 0C0000017h
0x180029c4f  jmp     loc_180029D31
0x180029c54  movzx   r15d, [rbp+var_18]
0x180029c59  lea     rax, [rbp+Str]
0x180029c5d  movzx   r12d, [rbp+var_14]
0x180029c62  mov     r9, rbx
0x180029c65  mov     [rsp+58h+var_28], r15w
0x180029c6b  mov     r8, rdi
0x180029c6e  mov     word ptr [rsp+58h+var_30], r12w
0x180029c74  mov     rdx, rsi
0x180029c77  mov     rcx, r13
0x180029c7a  mov     [rsp+58h+var_38], rax
0x180029c7f  call    AslEnvExpandStrings2
0x180029c84  mov     ebx, eax
0x180029c86  cmp     eax, 0C0000023h
0x180029c8b  jnz     short loc_180029CFD
0x180029c8d  mov     rcx, gs:60h
0x180029c96  mov     rdx, rdi
0x180029c99  mov     rcx, [rcx+30h]
0x180029c9d  call    AslFree
0x180029ca2  mov     rcx, gs:60h
0x180029cab  mov     edx, 8; Flags
0x180029cb0  mov     rbx, [rbp+Str]
0x180029cb4  mov     rcx, [rcx+30h]; HeapHandle
0x180029cb8  lea     r8, [rbx+rbx]; Size
0x180029cbc  call    cs:__imp_RtlAllocateHeap
0x180029cc2  mov     rdi, rax
0x180029cc5  test    rax, rax
0x180029cc8  jnz     short loc_180029CD5
0x180029cca  mov     r8d, 5D6h
0x180029cd0  jmp     loc_180029C32
0x180029cd5  mov     [rsp+58h+var_28], r15w
0x180029cdb  lea     rax, [rbp+Str]
0x180029cdf  mov     word ptr [rsp+58h+var_30], r12w
0x180029ce5  mov     r9, rbx
0x180029ce8  mov     r8, rdi
0x180029ceb  mov     [rsp+58h+var_38], rax
0x180029cf0  mov     rdx, rsi
0x180029cf3  mov     rcx, r13
0x180029cf6  call    AslEnvExpandStrings2
0x180029cfb  mov     ebx, eax
0x180029cfd  test    ebx, ebx
0x180029cff  jns     short loc_180029D2A
0x180029d01  mov     dword ptr [rsp+58h+var_30], ebx
0x180029d05  lea     r9, aAslenvexpandst_0; "AslEnvExpandStrings2 failed to expand s"...
0x180029d0c  mov     r8d, 5E5h
0x180029d12  mov     [rsp+58h+var_38], rsi
0x180029d17  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x180029d1e  mov     ecx, 1
0x180029d23  call    AslLogCallPrintf
0x180029d28  jmp     short loc_180029D31
0x180029d2a  mov     [r14], rdi
0x180029d2d  xor     edi, edi
0x180029d2f  xor     ebx, ebx
0x180029d31  test    rsi, rsi
0x180029d34  jz      short loc_180029D4B
0x180029d36  mov     rcx, gs:60h
0x180029d3f  mov     rdx, rsi
0x180029d42  mov     rcx, [rcx+30h]
0x180029d46  call    AslFree
0x180029d4b  test    rdi, rdi
0x180029d4e  jz      short loc_180029D65
0x180029d50  mov     rcx, gs:60h
0x180029d59  mov     rdx, rdi
0x180029d5c  mov     rcx, [rcx+30h]
0x180029d60  call    AslFree
0x180029d65  mov     eax, ebx
0x180029d67  add     rsp, 58h
0x180029d6b  pop     r15
0x180029d6d  pop     r14
0x180029d6f  pop     r13
0x180029d71  pop     r12
0x180029d73  pop     rdi
0x180029d74  pop     rsi
0x180029d75  pop     rbx
0x180029d76  pop     rbp
0x180029d77  retn
```
