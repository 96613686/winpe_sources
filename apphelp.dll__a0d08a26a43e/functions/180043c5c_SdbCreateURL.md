# SdbCreateURL

- ea: `0x180043c5c`
- end: `0x180043dd4`
- name: `SdbCreateURL`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800446e0`

## callees

- `0x18000ecc0`
- `0x18000f114`
- `0x180043730`
- `0x180043c5c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180043d39`
- `ntdll!RtlAllocateHeap` at `0x180043d39`

## string_xrefs

- `0x180043ccc`: `Failed to retrieve size for create help center URL`
- `0x180043d11`: `Failed to retrieve size for create help center URL`
- `0x180043d58`: `SdbCreateURL`
- `0x180043d9e`: `SdbCreateURL`

## pseudocode

```c
__int64 __fastcall SdbCreateURL(__int64 a1, __int64 a2, _QWORD *a3)
{
  int FirstTag; // eax
  _OWORD *v7; // r9
  unsigned int v8; // r8d
  int v9; // edx
  BOOL v10; // ebp
  PVOID Heap; // rdi
  int v12; // esi
  __int64 result; // rax
  SIZE_T Size; // [rsp+50h] [rbp+8h] BYREF

  LODWORD(Size) = 0;
  FirstTag = SdbFindFirstTag(*(_QWORD *)(a1 + 8), *(unsigned int *)(a1 + 72), 4101);
  v7 = *(_OWORD **)(a1 + 128);
  v8 = *(_DWORD *)(a1 + 76);
  v9 = *(_DWORD *)(a1 + 24);
  v10 = FirstTag != 0;
  *a3 = 0;
  if ( !(unsigned int)SdbCreateHelpCenterURL(v10, v9, v8, v7, 0, (unsigned int *)&Size) )
  {
    AslLogCallPrintf(1, "SdbCreateURL", 1922, "Failed to retrieve size for create help center URL");
    return 0;
  }
  Heap = 0;
  if ( a2 )
  {
    if ( !(unsigned int)SdbCreateHelpCenterURL(
                          v10,
                          *(_DWORD *)(a1 + 24),
                          *(_DWORD *)(a1 + 76),
                          *(_OWORD **)(a1 + 128),
                          0,
                          (unsigned int *)&Size) )
    {
      AslLogCallPrintf(1, "SdbCreateURL", 1938, "Failed to retrieve size for create help center URL");
      return 0;
    }
    v12 = Size;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)Size);
    if ( !Heap )
    {
      AslLogCallPrintf(1, "SdbCreateURL", 1945, "Failed to allocate '%ld' bytes for help center URL", v12);
      return 0;
    }
    if ( !(unsigned int)SdbCreateHelpCenterURL(
                          v10,
                          *(_DWORD *)(a1 + 24),
                          *(_DWORD *)(a1 + 76),
                          *(_OWORD **)(a1 + 128),
                          (__int64)Heap,
                          (unsigned int *)&Size) )
    {
      AslLogCallPrintf(1, "SdbCreateURL", 1959, "Failed to retrieve help center URL");
      return 0;
    }
  }
  result = (unsigned int)Size;
  *(_QWORD *)(a1 + 168) = Heap;
  *a3 = Heap;
  return result;
}

```

## disassembly

```asm
0x180043c5c  mov     [rsp+arg_8], rbx
0x180043c61  mov     [rsp+arg_10], rbp
0x180043c66  push    rsi
0x180043c67  push    rdi
0x180043c68  push    r14
0x180043c6a  sub     rsp, 30h
0x180043c6e  mov     rsi, rdx
0x180043c71  mov     dword ptr [rsp+48h+Size], 0
0x180043c79  mov     edx, [rcx+48h]
0x180043c7c  mov     r14, r8
0x180043c7f  mov     rbx, rcx
0x180043c82  mov     r8d, 1005h
0x180043c88  mov     rcx, [rcx+8]
0x180043c8c  call    SdbFindFirstTag
0x180043c91  mov     r9, [rbx+80h]
0x180043c98  xor     ebp, ebp
0x180043c9a  mov     r8d, [rbx+4Ch]
0x180043c9e  test    eax, eax
0x180043ca0  mov     edx, [rbx+18h]
0x180043ca3  lea     rax, [rsp+48h+Size]
0x180043ca8  setnz   bpl
0x180043cac  mov     [rsp+48h+var_20], rax
0x180043cb1  mov     ecx, ebp
0x180043cb3  mov     qword ptr [r14], 0
0x180043cba  mov     [rsp+48h+var_28], 0
0x180043cc3  call    SdbCreateHelpCenterURL
0x180043cc8  test    eax, eax
0x180043cca  jnz     short loc_180043CDE
0x180043ccc  lea     r9, aFailedToRetrie_3; "Failed to retrieve size for create help"...
0x180043cd3  mov     r8d, 782h
0x180043cd9  jmp     loc_180043D9E
0x180043cde  xor     edi, edi
0x180043ce0  test    rsi, rsi
0x180043ce3  jz      loc_180043DB3
0x180043ce9  mov     r9, [rbx+80h]
0x180043cf0  lea     rax, [rsp+48h+Size]
0x180043cf5  mov     r8d, [rbx+4Ch]
0x180043cf9  mov     ecx, ebp
0x180043cfb  mov     edx, [rbx+18h]
0x180043cfe  mov     [rsp+48h+var_20], rax
0x180043d03  mov     [rsp+48h+var_28], rdi
0x180043d08  call    SdbCreateHelpCenterURL
0x180043d0d  test    eax, eax
0x180043d0f  jnz     short loc_180043D20
0x180043d11  lea     r9, aFailedToRetrie_3; "Failed to retrieve size for create help"...
0x180043d18  mov     r8d, 792h
0x180043d1e  jmp     short loc_180043D9E
0x180043d20  mov     rcx, gs:60h
0x180043d29  mov     edx, 8; Flags
0x180043d2e  mov     esi, dword ptr [rsp+48h+Size]
0x180043d32  mov     r8d, esi; Size
0x180043d35  mov     rcx, [rcx+30h]; HeapHandle
0x180043d39  call    cs:__imp_RtlAllocateHeap
0x180043d3f  mov     rdi, rax
0x180043d42  test    rax, rax
0x180043d45  jnz     short loc_180043D69
0x180043d47  lea     r9, aFailedToAlloca_2; "Failed to allocate '%ld' bytes for help"...
0x180043d4e  mov     dword ptr [rsp+48h+var_28], esi
0x180043d52  mov     r8d, 799h
0x180043d58  lea     rdx, aSdbcreateurl; "SdbCreateURL"
0x180043d5f  lea     ecx, [rax+1]
0x180043d62  call    AslLogCallPrintf
0x180043d67  jmp     short loc_180043DAF
0x180043d69  mov     r9, [rbx+80h]
0x180043d70  lea     rax, [rsp+48h+Size]
0x180043d75  mov     r8d, [rbx+4Ch]
0x180043d79  mov     ecx, ebp
0x180043d7b  mov     edx, [rbx+18h]
0x180043d7e  mov     [rsp+48h+var_20], rax
0x180043d83  mov     [rsp+48h+var_28], rdi
0x180043d88  call    SdbCreateHelpCenterURL
0x180043d8d  test    eax, eax
0x180043d8f  jnz     short loc_180043DB3
0x180043d91  lea     r9, aFailedToRetrie_5; "Failed to retrieve help center URL"
0x180043d98  mov     r8d, 7A7h
0x180043d9e  lea     rdx, aSdbcreateurl; "SdbCreateURL"
0x180043da5  mov     ecx, 1
0x180043daa  call    AslLogCallPrintf
0x180043daf  xor     eax, eax
0x180043db1  jmp     short loc_180043DC1
0x180043db3  mov     eax, dword ptr [rsp+48h+Size]
0x180043db7  mov     [rbx+0A8h], rdi
0x180043dbe  mov     [r14], rdi
0x180043dc1  mov     rbx, [rsp+48h+arg_8]
0x180043dc6  mov     rbp, [rsp+48h+arg_10]
0x180043dcb  add     rsp, 30h
0x180043dcf  pop     r14
0x180043dd1  pop     rdi
0x180043dd2  pop     rsi
0x180043dd3  retn
```
