# AslRegistryGetStringExpand

- ea: `0x180015870`
- end: `0x180015a8d`
- name: `AslRegistryGetStringExpand`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180017f84`

## callees

- `0x1800152d0`
- `0x1800156a4`
- `0x180015870`
- `0x1800194f8`
- `0x180019710`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800158ba`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800158ba`
- `ntdll!RtlFreeHeap` at `0x1800159ab`
- `ntdll!RtlFreeHeap` at `0x180015a57`
- `ntdll!RtlFreeHeap` at `0x180015a74`
- `ntdll!RtlFreeHeap` at `0x1800159ab`
- `ntdll!RtlFreeHeap` at `0x180015a57`
- `ntdll!RtlFreeHeap` at `0x180015a74`
- `ntdll!RtlAllocateHeap` at `0x18001592a`
- `ntdll!RtlAllocateHeap` at `0x1800159cb`
- `ntdll!RtlAllocateHeap` at `0x18001592a`
- `ntdll!RtlAllocateHeap` at `0x1800159cb`

## string_xrefs

- `0x1800158f3`: `AslRegistryGetStringExpand`
- `0x18001594a`: `AslRegistryGetStringExpand`
- `0x180015a26`: `AslRegistryGetStringExpand`

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
0x180015870  push    rbp
0x180015872  push    rbx
0x180015873  push    rsi
0x180015874  push    rdi
0x180015875  push    r12
0x180015877  push    r13
0x180015879  push    r14
0x18001587b  push    r15
0x18001587d  mov     rbp, rsp
0x180015880  sub     rsp, 58h
0x180015884  mov     eax, 0FFFFh
0x180015889  mov     r14, rcx
0x18001588c  xor     edi, edi
0x18001588e  mov     [rbp+var_18], ax
0x180015892  lea     rcx, [rbp+Str]
0x180015896  mov     [rbp+Str], rdi
0x18001589a  mov     [rbp+var_14], ax
0x18001589e  mov     r13, r9
0x1800158a1  call    AslRegistryGetString
0x1800158a6  mov     rsi, [rbp+Str]
0x1800158aa  mov     ebx, eax
0x1800158ac  test    eax, eax
0x1800158ae  js      loc_180015A40
0x1800158b4  lea     edx, [rdi+25h]; Ch
0x1800158b7  mov     rcx, rsi; Str
0x1800158ba  call    cs:__imp_wcschr
0x1800158c0  test    rax, rax
0x1800158c3  jnz     short loc_1800158CF
0x1800158c5  mov     [r14], rsi
0x1800158c8  xor     ebx, ebx
0x1800158ca  jmp     loc_180015A7A
0x1800158cf  lea     rdx, [rbp+var_18]
0x1800158d3  lea     rcx, [rbp+var_14]
0x1800158d7  call    AslEnvGetProcessWowInfo
0x1800158dc  mov     ebx, eax
0x1800158de  test    eax, eax
0x1800158e0  jns     short loc_180015909
0x1800158e2  lea     r9, aAslenvgetproce_0; "AslEnvGetProcessWowInfo failed [%x]"
0x1800158e9  mov     dword ptr [rsp+58h+var_38], eax
0x1800158ed  mov     r8d, 5B8h
0x1800158f3  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x1800158fa  mov     ecx, 1
0x1800158ff  call    AslLogCallPrintf
0x180015904  jmp     loc_180015A40
0x180015909  mov     rcx, gs:60h
0x180015912  mov     ebx, 104h
0x180015917  mov     edx, 8; Flags
0x18001591c  mov     [rbp+Str], rbx
0x180015920  mov     r8d, 208h; Size
0x180015926  mov     rcx, [rcx+30h]; HeapHandle
0x18001592a  call    cs:__imp_RtlAllocateHeap
0x180015930  mov     rdi, rax
0x180015933  test    rax, rax
0x180015936  jnz     short loc_180015960
0x180015938  mov     r8d, 5C4h
0x18001593e  lea     r9, aOutOfMemory_0; "Out of memory"
0x180015945  mov     ecx, 1
0x18001594a  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x180015951  call    AslLogCallPrintf
0x180015956  mov     ebx, 0C0000017h
0x18001595b  jmp     loc_180015A40
0x180015960  movzx   r15d, [rbp+var_18]
0x180015965  lea     rax, [rbp+Str]
0x180015969  movzx   r12d, [rbp+var_14]
0x18001596e  mov     r9, rbx
0x180015971  mov     [rsp+58h+var_28], r15w
0x180015977  mov     r8, rdi
0x18001597a  mov     word ptr [rsp+58h+var_30], r12w
0x180015980  mov     rdx, rsi
0x180015983  mov     rcx, r13
0x180015986  mov     [rsp+58h+var_38], rax
0x18001598b  call    AslEnvExpandStrings2
0x180015990  mov     ebx, eax
0x180015992  cmp     eax, 0C0000023h
0x180015997  jnz     short loc_180015A0C
0x180015999  mov     rcx, gs:60h
0x1800159a2  mov     r8, rdi; P
0x1800159a5  xor     edx, edx; Flags
0x1800159a7  mov     rcx, [rcx+30h]; HeapHandle
0x1800159ab  call    cs:__imp_RtlFreeHeap
0x1800159b1  mov     rcx, gs:60h
0x1800159ba  mov     edx, 8; Flags
0x1800159bf  mov     rbx, [rbp+Str]
0x1800159c3  mov     rcx, [rcx+30h]; HeapHandle
0x1800159c7  lea     r8, [rbx+rbx]; Size
0x1800159cb  call    cs:__imp_RtlAllocateHeap
0x1800159d1  mov     rdi, rax
0x1800159d4  test    rax, rax
0x1800159d7  jnz     short loc_1800159E4
0x1800159d9  mov     r8d, 5D6h
0x1800159df  jmp     loc_18001593E
0x1800159e4  mov     [rsp+58h+var_28], r15w
0x1800159ea  lea     rax, [rbp+Str]
0x1800159ee  mov     word ptr [rsp+58h+var_30], r12w
0x1800159f4  mov     r9, rbx
0x1800159f7  mov     r8, rdi
0x1800159fa  mov     [rsp+58h+var_38], rax
0x1800159ff  mov     rdx, rsi
0x180015a02  mov     rcx, r13
0x180015a05  call    AslEnvExpandStrings2
0x180015a0a  mov     ebx, eax
0x180015a0c  test    ebx, ebx
0x180015a0e  jns     short loc_180015A39
0x180015a10  mov     dword ptr [rsp+58h+var_30], ebx
0x180015a14  lea     r9, aAslenvexpandst_0; "AslEnvExpandStrings2 failed to expand s"...
0x180015a1b  mov     r8d, 5E5h
0x180015a21  mov     [rsp+58h+var_38], rsi
0x180015a26  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x180015a2d  mov     ecx, 1
0x180015a32  call    AslLogCallPrintf
0x180015a37  jmp     short loc_180015A40
0x180015a39  mov     [r14], rdi
0x180015a3c  xor     edi, edi
0x180015a3e  xor     ebx, ebx
0x180015a40  test    rsi, rsi
0x180015a43  jz      short loc_180015A5D
0x180015a45  mov     rcx, gs:60h
0x180015a4e  mov     r8, rsi; P
0x180015a51  xor     edx, edx; Flags
0x180015a53  mov     rcx, [rcx+30h]; HeapHandle
0x180015a57  call    cs:__imp_RtlFreeHeap
0x180015a5d  test    rdi, rdi
0x180015a60  jz      short loc_180015A7A
0x180015a62  mov     rcx, gs:60h
0x180015a6b  mov     r8, rdi; P
0x180015a6e  xor     edx, edx; Flags
0x180015a70  mov     rcx, [rcx+30h]; HeapHandle
0x180015a74  call    cs:__imp_RtlFreeHeap
0x180015a7a  mov     eax, ebx
0x180015a7c  add     rsp, 58h
0x180015a80  pop     r15
0x180015a82  pop     r14
0x180015a84  pop     r13
0x180015a86  pop     r12
0x180015a88  pop     rdi
0x180015a89  pop     rsi
0x180015a8a  pop     rbx
0x180015a8b  pop     rbp
0x180015a8c  retn
```
