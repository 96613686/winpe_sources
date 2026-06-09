# AslRegistryGetStringExpand

- ea: `0x180051d64`
- end: `0x180051f81`
- name: `AslRegistryGetStringExpand`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18005b258`

## callees

- `0x180051b98`
- `0x180051d64`
- `0x1800543c0`
- `0x18005c7c4`
- `0x18005c9dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180051dae`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180051dae`
- `ntdll!RtlAllocateHeap` at `0x180051e1e`
- `ntdll!RtlAllocateHeap` at `0x180051ebf`
- `ntdll!RtlAllocateHeap` at `0x180051e1e`
- `ntdll!RtlAllocateHeap` at `0x180051ebf`
- `ntdll!RtlFreeHeap` at `0x180051e9f`
- `ntdll!RtlFreeHeap` at `0x180051f4b`
- `ntdll!RtlFreeHeap` at `0x180051f68`
- `ntdll!RtlFreeHeap` at `0x180051e9f`
- `ntdll!RtlFreeHeap` at `0x180051f4b`
- `ntdll!RtlFreeHeap` at `0x180051f68`

## string_xrefs

- `0x180051de7`: `AslRegistryGetStringExpand`
- `0x180051e3e`: `AslRegistryGetStringExpand`
- `0x180051f1a`: `AslRegistryGetStringExpand`

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
0x180051d64  push    rbp
0x180051d66  push    rbx
0x180051d67  push    rsi
0x180051d68  push    rdi
0x180051d69  push    r12
0x180051d6b  push    r13
0x180051d6d  push    r14
0x180051d6f  push    r15
0x180051d71  mov     rbp, rsp
0x180051d74  sub     rsp, 58h
0x180051d78  mov     eax, 0FFFFh
0x180051d7d  mov     r14, rcx
0x180051d80  xor     edi, edi
0x180051d82  mov     [rbp+var_18], ax
0x180051d86  lea     rcx, [rbp+Str]
0x180051d8a  mov     [rbp+Str], rdi
0x180051d8e  mov     [rbp+var_14], ax
0x180051d92  mov     r13, r9
0x180051d95  call    AslRegistryGetString
0x180051d9a  mov     rsi, [rbp+Str]
0x180051d9e  mov     ebx, eax
0x180051da0  test    eax, eax
0x180051da2  js      loc_180051F34
0x180051da8  lea     edx, [rdi+25h]; Ch
0x180051dab  mov     rcx, rsi; Str
0x180051dae  call    cs:__imp_wcschr
0x180051db4  test    rax, rax
0x180051db7  jnz     short loc_180051DC3
0x180051db9  mov     [r14], rsi
0x180051dbc  xor     ebx, ebx
0x180051dbe  jmp     loc_180051F6E
0x180051dc3  lea     rdx, [rbp+var_18]
0x180051dc7  lea     rcx, [rbp+var_14]
0x180051dcb  call    AslEnvGetProcessWowInfo
0x180051dd0  mov     ebx, eax
0x180051dd2  test    eax, eax
0x180051dd4  jns     short loc_180051DFD
0x180051dd6  lea     r9, aAslenvgetproce_1; "AslEnvGetProcessWowInfo failed [%x]"
0x180051ddd  mov     dword ptr [rsp+58h+var_38], eax
0x180051de1  mov     r8d, 5B8h
0x180051de7  lea     rdx, aAslregistryget_5; "AslRegistryGetStringExpand"
0x180051dee  mov     ecx, 1
0x180051df3  call    AslLogCallPrintf
0x180051df8  jmp     loc_180051F34
0x180051dfd  mov     rcx, gs:60h
0x180051e06  mov     ebx, 104h
0x180051e0b  mov     edx, 8; Flags
0x180051e10  mov     [rbp+Str], rbx
0x180051e14  mov     r8d, 208h; Size
0x180051e1a  mov     rcx, [rcx+30h]; HeapHandle
0x180051e1e  call    cs:__imp_RtlAllocateHeap
0x180051e24  mov     rdi, rax
0x180051e27  test    rax, rax
0x180051e2a  jnz     short loc_180051E54
0x180051e2c  mov     r8d, 5C4h
0x180051e32  lea     r9, aOutOfMemory; "Out of memory"
0x180051e39  mov     ecx, 1
0x180051e3e  lea     rdx, aAslregistryget_5; "AslRegistryGetStringExpand"
0x180051e45  call    AslLogCallPrintf
0x180051e4a  mov     ebx, 0C0000017h
0x180051e4f  jmp     loc_180051F34
0x180051e54  movzx   r15d, [rbp+var_18]
0x180051e59  lea     rax, [rbp+Str]
0x180051e5d  movzx   r12d, [rbp+var_14]
0x180051e62  mov     r9, rbx
0x180051e65  mov     [rsp+58h+var_28], r15w
0x180051e6b  mov     r8, rdi
0x180051e6e  mov     word ptr [rsp+58h+var_30], r12w
0x180051e74  mov     rdx, rsi
0x180051e77  mov     rcx, r13
0x180051e7a  mov     [rsp+58h+var_38], rax
0x180051e7f  call    AslEnvExpandStrings2
0x180051e84  mov     ebx, eax
0x180051e86  cmp     eax, 0C0000023h
0x180051e8b  jnz     short loc_180051F00
0x180051e8d  mov     rcx, gs:60h
0x180051e96  mov     r8, rdi; P
0x180051e99  xor     edx, edx; Flags
0x180051e9b  mov     rcx, [rcx+30h]; HeapHandle
0x180051e9f  call    cs:__imp_RtlFreeHeap
0x180051ea5  mov     rcx, gs:60h
0x180051eae  mov     edx, 8; Flags
0x180051eb3  mov     rbx, [rbp+Str]
0x180051eb7  mov     rcx, [rcx+30h]; HeapHandle
0x180051ebb  lea     r8, [rbx+rbx]; Size
0x180051ebf  call    cs:__imp_RtlAllocateHeap
0x180051ec5  mov     rdi, rax
0x180051ec8  test    rax, rax
0x180051ecb  jnz     short loc_180051ED8
0x180051ecd  mov     r8d, 5D6h
0x180051ed3  jmp     loc_180051E32
0x180051ed8  mov     [rsp+58h+var_28], r15w
0x180051ede  lea     rax, [rbp+Str]
0x180051ee2  mov     word ptr [rsp+58h+var_30], r12w
0x180051ee8  mov     r9, rbx
0x180051eeb  mov     r8, rdi
0x180051eee  mov     [rsp+58h+var_38], rax
0x180051ef3  mov     rdx, rsi
0x180051ef6  mov     rcx, r13
0x180051ef9  call    AslEnvExpandStrings2
0x180051efe  mov     ebx, eax
0x180051f00  test    ebx, ebx
0x180051f02  jns     short loc_180051F2D
0x180051f04  mov     dword ptr [rsp+58h+var_30], ebx
0x180051f08  lea     r9, aAslenvexpandst_0; "AslEnvExpandStrings2 failed to expand s"...
0x180051f0f  mov     r8d, 5E5h
0x180051f15  mov     [rsp+58h+var_38], rsi
0x180051f1a  lea     rdx, aAslregistryget_5; "AslRegistryGetStringExpand"
0x180051f21  mov     ecx, 1
0x180051f26  call    AslLogCallPrintf
0x180051f2b  jmp     short loc_180051F34
0x180051f2d  mov     [r14], rdi
0x180051f30  xor     edi, edi
0x180051f32  xor     ebx, ebx
0x180051f34  test    rsi, rsi
0x180051f37  jz      short loc_180051F51
0x180051f39  mov     rcx, gs:60h
0x180051f42  mov     r8, rsi; P
0x180051f45  xor     edx, edx; Flags
0x180051f47  mov     rcx, [rcx+30h]; HeapHandle
0x180051f4b  call    cs:__imp_RtlFreeHeap
0x180051f51  test    rdi, rdi
0x180051f54  jz      short loc_180051F6E
0x180051f56  mov     rcx, gs:60h
0x180051f5f  mov     r8, rdi; P
0x180051f62  xor     edx, edx; Flags
0x180051f64  mov     rcx, [rcx+30h]; HeapHandle
0x180051f68  call    cs:__imp_RtlFreeHeap
0x180051f6e  mov     eax, ebx
0x180051f70  add     rsp, 58h
0x180051f74  pop     r15
0x180051f76  pop     r14
0x180051f78  pop     r13
0x180051f7a  pop     r12
0x180051f7c  pop     rdi
0x180051f7d  pop     rsi
0x180051f7e  pop     rbx
0x180051f7f  pop     rbp
0x180051f80  retn
```
