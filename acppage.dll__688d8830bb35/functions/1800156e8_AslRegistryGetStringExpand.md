# AslRegistryGetStringExpand

- ea: `0x1800156e8`
- end: `0x180015905`
- name: `AslRegistryGetStringExpand`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800137e0`

## callees

- `0x180014d54`
- `0x180014f6c`
- `0x180015220`
- `0x18001551c`
- `0x1800156e8`

## import_xrefs

- `msvcrt!wcschr` at `0x180015732`
- `msvcrt!wcschr` at `0x180015732`
- `ntdll!RtlFreeHeap` at `0x180015823`
- `ntdll!RtlFreeHeap` at `0x1800158cf`
- `ntdll!RtlFreeHeap` at `0x1800158ec`
- `ntdll!RtlFreeHeap` at `0x180015823`
- `ntdll!RtlFreeHeap` at `0x1800158cf`
- `ntdll!RtlFreeHeap` at `0x1800158ec`
- `ntdll!RtlAllocateHeap` at `0x1800157a2`
- `ntdll!RtlAllocateHeap` at `0x180015843`
- `ntdll!RtlAllocateHeap` at `0x1800157a2`
- `ntdll!RtlAllocateHeap` at `0x180015843`

## string_xrefs

- `0x18001576b`: `AslRegistryGetStringExpand`
- `0x1800157c2`: `AslRegistryGetStringExpand`
- `0x18001589e`: `AslRegistryGetStringExpand`

## pseudocode

```c
__int64 __fastcall AslRegistryGetStringExpand(wchar_t **a1, void *a2, const WCHAR *a3, int a4)
{
  PVOID Heap; // rdi
  int String; // eax
  wchar_t *v8; // rsi
  int ProcessWowInfo; // ebx
  __int64 v10; // r8
  __int16 v11; // r15
  __int16 v12; // r12
  int v13; // ebx
  __int16 v15[2]; // [rsp+40h] [rbp-18h] BYREF
  __int16 v16; // [rsp+44h] [rbp-14h] BYREF
  wchar_t *Str[2]; // [rsp+48h] [rbp-10h] BYREF

  Heap = 0;
  v15[0] = -1;
  Str[0] = 0;
  v16 = -1;
  String = AslRegistryGetString(Str, a2, a3);
  v8 = Str[0];
  ProcessWowInfo = String;
  if ( String < 0 )
    goto LABEL_16;
  if ( !wcschr(Str[0], 0x25u) )
  {
    *a1 = v8;
    return 0;
  }
  ProcessWowInfo = AslEnvGetProcessWowInfo(&v16, v15);
  if ( ProcessWowInfo >= 0 )
  {
    Str[0] = (wchar_t *)260;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
    if ( !Heap )
    {
      v10 = 1476;
LABEL_8:
      AslLogCallPrintf(1, "AslRegistryGetStringExpand", v10, "Out of memory");
      ProcessWowInfo = -1073741801;
      goto LABEL_16;
    }
    v11 = v15[0];
    v12 = v16;
    ProcessWowInfo = AslEnvExpandStrings2(a4, (_DWORD)v8, (_DWORD)Heap, 260, (__int64)Str, v16, v15[0]);
    if ( ProcessWowInfo == -1073741789 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v13 = (int)Str[0];
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (__int64)Str[0]);
      if ( !Heap )
      {
        v10 = 1494;
        goto LABEL_8;
      }
      ProcessWowInfo = AslEnvExpandStrings2(a4, (_DWORD)v8, (_DWORD)Heap, v13, (__int64)Str, v12, v11);
    }
    if ( ProcessWowInfo >= 0 )
    {
      *a1 = (wchar_t *)Heap;
      Heap = 0;
      ProcessWowInfo = 0;
    }
    else
    {
      AslLogCallPrintf(
        1,
        "AslRegistryGetStringExpand",
        1509,
        "AslEnvExpandStrings2 failed to expand strings for %ws [%x]");
    }
    goto LABEL_16;
  }
  AslLogCallPrintf(1, "AslRegistryGetStringExpand", 1464, "AslEnvGetProcessWowInfo failed [%x]");
LABEL_16:
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)ProcessWowInfo;
}

```

## disassembly

```asm
0x1800156e8  push    rbp
0x1800156ea  push    rbx
0x1800156eb  push    rsi
0x1800156ec  push    rdi
0x1800156ed  push    r12
0x1800156ef  push    r13
0x1800156f1  push    r14
0x1800156f3  push    r15
0x1800156f5  mov     rbp, rsp
0x1800156f8  sub     rsp, 58h
0x1800156fc  mov     eax, 0FFFFh
0x180015701  mov     r14, rcx
0x180015704  xor     edi, edi
0x180015706  mov     [rbp+var_18], ax
0x18001570a  lea     rcx, [rbp+Str]
0x18001570e  mov     [rbp+Str], rdi
0x180015712  mov     [rbp+var_14], ax
0x180015716  mov     r13, r9
0x180015719  call    AslRegistryGetString
0x18001571e  mov     rsi, [rbp+Str]
0x180015722  mov     ebx, eax
0x180015724  test    eax, eax
0x180015726  js      loc_1800158B8
0x18001572c  lea     edx, [rdi+25h]; Ch
0x18001572f  mov     rcx, rsi; Str
0x180015732  call    cs:__imp_wcschr
0x180015738  test    rax, rax
0x18001573b  jnz     short loc_180015747
0x18001573d  mov     [r14], rsi
0x180015740  xor     ebx, ebx
0x180015742  jmp     loc_1800158F2
0x180015747  lea     rdx, [rbp+var_18]
0x18001574b  lea     rcx, [rbp+var_14]
0x18001574f  call    AslEnvGetProcessWowInfo
0x180015754  mov     ebx, eax
0x180015756  test    eax, eax
0x180015758  jns     short loc_180015781
0x18001575a  lea     r9, aAslenvgetproce_0; "AslEnvGetProcessWowInfo failed [%x]"
0x180015761  mov     dword ptr [rsp+58h+var_38], eax
0x180015765  mov     r8d, 5B8h
0x18001576b  lea     rdx, aAslregistryget_0; "AslRegistryGetStringExpand"
0x180015772  mov     ecx, 1
0x180015777  call    AslLogCallPrintf
0x18001577c  jmp     loc_1800158B8
0x180015781  mov     rcx, gs:60h
0x18001578a  mov     ebx, 104h
0x18001578f  mov     edx, 8; Flags
0x180015794  mov     [rbp+Str], rbx
0x180015798  mov     r8d, 208h; Size
0x18001579e  mov     rcx, [rcx+30h]; HeapHandle
0x1800157a2  call    cs:__imp_RtlAllocateHeap
0x1800157a8  mov     rdi, rax
0x1800157ab  test    rax, rax
0x1800157ae  jnz     short loc_1800157D8
0x1800157b0  mov     r8d, 5C4h
0x1800157b6  lea     r9, aOutOfMemory; "Out of memory"
0x1800157bd  mov     ecx, 1
0x1800157c2  lea     rdx, aAslregistryget_0; "AslRegistryGetStringExpand"
0x1800157c9  call    AslLogCallPrintf
0x1800157ce  mov     ebx, 0C0000017h
0x1800157d3  jmp     loc_1800158B8
0x1800157d8  movzx   r15d, [rbp+var_18]
0x1800157dd  lea     rax, [rbp+Str]
0x1800157e1  movzx   r12d, [rbp+var_14]
0x1800157e6  mov     r9, rbx
0x1800157e9  mov     [rsp+58h+var_28], r15w
0x1800157ef  mov     r8, rdi
0x1800157f2  mov     word ptr [rsp+58h+var_30], r12w
0x1800157f8  mov     rdx, rsi
0x1800157fb  mov     rcx, r13
0x1800157fe  mov     [rsp+58h+var_38], rax
0x180015803  call    AslEnvExpandStrings2
0x180015808  mov     ebx, eax
0x18001580a  cmp     eax, 0C0000023h
0x18001580f  jnz     short loc_180015884
0x180015811  mov     rcx, gs:60h
0x18001581a  mov     r8, rdi; P
0x18001581d  xor     edx, edx; Flags
0x18001581f  mov     rcx, [rcx+30h]; HeapHandle
0x180015823  call    cs:__imp_RtlFreeHeap
0x180015829  mov     rcx, gs:60h
0x180015832  mov     edx, 8; Flags
0x180015837  mov     rbx, [rbp+Str]
0x18001583b  mov     rcx, [rcx+30h]; HeapHandle
0x18001583f  lea     r8, [rbx+rbx]; Size
0x180015843  call    cs:__imp_RtlAllocateHeap
0x180015849  mov     rdi, rax
0x18001584c  test    rax, rax
0x18001584f  jnz     short loc_18001585C
0x180015851  mov     r8d, 5D6h
0x180015857  jmp     loc_1800157B6
0x18001585c  mov     [rsp+58h+var_28], r15w
0x180015862  lea     rax, [rbp+Str]
0x180015866  mov     word ptr [rsp+58h+var_30], r12w
0x18001586c  mov     r9, rbx
0x18001586f  mov     r8, rdi
0x180015872  mov     [rsp+58h+var_38], rax
0x180015877  mov     rdx, rsi
0x18001587a  mov     rcx, r13
0x18001587d  call    AslEnvExpandStrings2
0x180015882  mov     ebx, eax
0x180015884  test    ebx, ebx
0x180015886  jns     short loc_1800158B1
0x180015888  mov     [rsp+58h+var_30], ebx
0x18001588c  lea     r9, aAslenvexpandst_0; "AslEnvExpandStrings2 failed to expand s"...
0x180015893  mov     r8d, 5E5h
0x180015899  mov     [rsp+58h+var_38], rsi
0x18001589e  lea     rdx, aAslregistryget_0; "AslRegistryGetStringExpand"
0x1800158a5  mov     ecx, 1
0x1800158aa  call    AslLogCallPrintf
0x1800158af  jmp     short loc_1800158B8
0x1800158b1  mov     [r14], rdi
0x1800158b4  xor     edi, edi
0x1800158b6  xor     ebx, ebx
0x1800158b8  test    rsi, rsi
0x1800158bb  jz      short loc_1800158D5
0x1800158bd  mov     rcx, gs:60h
0x1800158c6  mov     r8, rsi; P
0x1800158c9  xor     edx, edx; Flags
0x1800158cb  mov     rcx, [rcx+30h]; HeapHandle
0x1800158cf  call    cs:__imp_RtlFreeHeap
0x1800158d5  test    rdi, rdi
0x1800158d8  jz      short loc_1800158F2
0x1800158da  mov     rcx, gs:60h
0x1800158e3  mov     r8, rdi; P
0x1800158e6  xor     edx, edx; Flags
0x1800158e8  mov     rcx, [rcx+30h]; HeapHandle
0x1800158ec  call    cs:__imp_RtlFreeHeap
0x1800158f2  mov     eax, ebx
0x1800158f4  add     rsp, 58h
0x1800158f8  pop     r15
0x1800158fa  pop     r14
0x1800158fc  pop     r13
0x1800158fe  pop     r12
0x180015900  pop     rdi
0x180015901  pop     rsi
0x180015902  pop     rbx
0x180015903  pop     rbp
0x180015904  retn
```
