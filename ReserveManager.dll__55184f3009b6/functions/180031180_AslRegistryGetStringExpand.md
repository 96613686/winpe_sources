# AslRegistryGetStringExpand

- ea: `0x180031180`
- end: `0x18003139d`
- name: `AslRegistryGetStringExpand`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002f0f4`

## callees

- `0x180030668`
- `0x180030880`
- `0x180030fb4`
- `0x180031180`
- `0x180031a3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800311ca`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800311ca`
- `ntdll!RtlAllocateHeap` at `0x18003123a`
- `ntdll!RtlAllocateHeap` at `0x1800312db`
- `ntdll!RtlAllocateHeap` at `0x18003123a`
- `ntdll!RtlAllocateHeap` at `0x1800312db`
- `ntdll!RtlFreeHeap` at `0x1800312bb`
- `ntdll!RtlFreeHeap` at `0x180031367`
- `ntdll!RtlFreeHeap` at `0x180031384`
- `ntdll!RtlFreeHeap` at `0x1800312bb`
- `ntdll!RtlFreeHeap` at `0x180031367`
- `ntdll!RtlFreeHeap` at `0x180031384`

## string_xrefs

- `0x180031203`: `AslRegistryGetStringExpand`
- `0x18003125a`: `AslRegistryGetStringExpand`
- `0x180031336`: `AslRegistryGetStringExpand`

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
0x180031180  push    rbp
0x180031182  push    rbx
0x180031183  push    rsi
0x180031184  push    rdi
0x180031185  push    r12
0x180031187  push    r13
0x180031189  push    r14
0x18003118b  push    r15
0x18003118d  mov     rbp, rsp
0x180031190  sub     rsp, 58h
0x180031194  mov     eax, 0FFFFh
0x180031199  mov     r14, rcx
0x18003119c  xor     edi, edi
0x18003119e  mov     [rbp+var_18], ax
0x1800311a2  lea     rcx, [rbp+Str]
0x1800311a6  mov     [rbp+Str], rdi
0x1800311aa  mov     [rbp+var_14], ax
0x1800311ae  mov     r13, r9
0x1800311b1  call    AslRegistryGetString
0x1800311b6  mov     rsi, [rbp+Str]
0x1800311ba  mov     ebx, eax
0x1800311bc  test    eax, eax
0x1800311be  js      loc_180031350
0x1800311c4  lea     edx, [rdi+25h]; Ch
0x1800311c7  mov     rcx, rsi; Str
0x1800311ca  call    cs:__imp_wcschr
0x1800311d0  test    rax, rax
0x1800311d3  jnz     short loc_1800311DF
0x1800311d5  mov     [r14], rsi
0x1800311d8  xor     ebx, ebx
0x1800311da  jmp     loc_18003138A
0x1800311df  lea     rdx, [rbp+var_18]
0x1800311e3  lea     rcx, [rbp+var_14]
0x1800311e7  call    AslEnvGetProcessWowInfo
0x1800311ec  mov     ebx, eax
0x1800311ee  test    eax, eax
0x1800311f0  jns     short loc_180031219
0x1800311f2  lea     r9, aAslenvgetproce_0; "AslEnvGetProcessWowInfo failed [%x]"
0x1800311f9  mov     dword ptr [rsp+58h+var_38], eax
0x1800311fd  mov     r8d, 5B8h
0x180031203  lea     rdx, aAslregistryget_0; "AslRegistryGetStringExpand"
0x18003120a  mov     ecx, 1
0x18003120f  call    AslLogCallPrintf
0x180031214  jmp     loc_180031350
0x180031219  mov     rcx, gs:60h
0x180031222  mov     ebx, 104h
0x180031227  mov     edx, 8; Flags
0x18003122c  mov     [rbp+Str], rbx
0x180031230  mov     r8d, 208h; Size
0x180031236  mov     rcx, [rcx+30h]; HeapHandle
0x18003123a  call    cs:__imp_RtlAllocateHeap
0x180031240  mov     rdi, rax
0x180031243  test    rax, rax
0x180031246  jnz     short loc_180031270
0x180031248  mov     r8d, 5C4h
0x18003124e  lea     r9, aOutOfMemory; "Out of memory"
0x180031255  mov     ecx, 1
0x18003125a  lea     rdx, aAslregistryget_0; "AslRegistryGetStringExpand"
0x180031261  call    AslLogCallPrintf
0x180031266  mov     ebx, 0C0000017h
0x18003126b  jmp     loc_180031350
0x180031270  movzx   r15d, [rbp+var_18]
0x180031275  lea     rax, [rbp+Str]
0x180031279  movzx   r12d, [rbp+var_14]
0x18003127e  mov     r9, rbx
0x180031281  mov     [rsp+58h+var_28], r15w
0x180031287  mov     r8, rdi
0x18003128a  mov     word ptr [rsp+58h+var_30], r12w
0x180031290  mov     rdx, rsi
0x180031293  mov     rcx, r13
0x180031296  mov     [rsp+58h+var_38], rax
0x18003129b  call    AslEnvExpandStrings2
0x1800312a0  mov     ebx, eax
0x1800312a2  cmp     eax, 0C0000023h
0x1800312a7  jnz     short loc_18003131C
0x1800312a9  mov     rcx, gs:60h
0x1800312b2  mov     r8, rdi; P
0x1800312b5  xor     edx, edx; Flags
0x1800312b7  mov     rcx, [rcx+30h]; HeapHandle
0x1800312bb  call    cs:__imp_RtlFreeHeap
0x1800312c1  mov     rcx, gs:60h
0x1800312ca  mov     edx, 8; Flags
0x1800312cf  mov     rbx, [rbp+Str]
0x1800312d3  mov     rcx, [rcx+30h]; HeapHandle
0x1800312d7  lea     r8, [rbx+rbx]; Size
0x1800312db  call    cs:__imp_RtlAllocateHeap
0x1800312e1  mov     rdi, rax
0x1800312e4  test    rax, rax
0x1800312e7  jnz     short loc_1800312F4
0x1800312e9  mov     r8d, 5D6h
0x1800312ef  jmp     loc_18003124E
0x1800312f4  mov     [rsp+58h+var_28], r15w
0x1800312fa  lea     rax, [rbp+Str]
0x1800312fe  mov     word ptr [rsp+58h+var_30], r12w
0x180031304  mov     r9, rbx
0x180031307  mov     r8, rdi
0x18003130a  mov     [rsp+58h+var_38], rax
0x18003130f  mov     rdx, rsi
0x180031312  mov     rcx, r13
0x180031315  call    AslEnvExpandStrings2
0x18003131a  mov     ebx, eax
0x18003131c  test    ebx, ebx
0x18003131e  jns     short loc_180031349
0x180031320  mov     dword ptr [rsp+58h+var_30], ebx
0x180031324  lea     r9, aAslenvexpandst_0; "AslEnvExpandStrings2 failed to expand s"...
0x18003132b  mov     r8d, 5E5h
0x180031331  mov     [rsp+58h+var_38], rsi
0x180031336  lea     rdx, aAslregistryget_0; "AslRegistryGetStringExpand"
0x18003133d  mov     ecx, 1
0x180031342  call    AslLogCallPrintf
0x180031347  jmp     short loc_180031350
0x180031349  mov     [r14], rdi
0x18003134c  xor     edi, edi
0x18003134e  xor     ebx, ebx
0x180031350  test    rsi, rsi
0x180031353  jz      short loc_18003136D
0x180031355  mov     rcx, gs:60h
0x18003135e  mov     r8, rsi; P
0x180031361  xor     edx, edx; Flags
0x180031363  mov     rcx, [rcx+30h]; HeapHandle
0x180031367  call    cs:__imp_RtlFreeHeap
0x18003136d  test    rdi, rdi
0x180031370  jz      short loc_18003138A
0x180031372  mov     rcx, gs:60h
0x18003137b  mov     r8, rdi; P
0x18003137e  xor     edx, edx; Flags
0x180031380  mov     rcx, [rcx+30h]; HeapHandle
0x180031384  call    cs:__imp_RtlFreeHeap
0x18003138a  mov     eax, ebx
0x18003138c  add     rsp, 58h
0x180031390  pop     r15
0x180031392  pop     r14
0x180031394  pop     r13
0x180031396  pop     r12
0x180031398  pop     rdi
0x180031399  pop     rsi
0x18003139a  pop     rbx
0x18003139b  pop     rbp
0x18003139c  retn
```
