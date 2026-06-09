# AslLogDelete

- ea: `0x140015034`
- end: `0x1400150e2`
- name: `AslLogDelete`
- size: `174`
- prototype: `BOOLEAN __fastcall(char *P)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000b2d8`
- `0x1400145a4`
- `0x1400a7ca0`

## callees

- `0x1400026c0`
- `0x140015034`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x1400150be`
- `ntdll!EtwEventUnregister` at `0x1400150be`
- `ntdll!RtlFreeHeap` at `0x140015077`
- `ntdll!RtlFreeHeap` at `0x1400150d6`
- `ntdll!RtlFreeHeap` at `0x140015077`
- `ntdll!RtlFreeHeap` at `0x1400150d6`
- `ntdll!RtlDeleteCriticalSection` at `0x140015099`
- `ntdll!RtlDeleteCriticalSection` at `0x140015099`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140015051`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140015051`

## pseudocode

```c
BOOLEAN __fastcall AslLogDelete(char *P)
{
  HMODULE v2; // rcx
  void *v3; // r8
  BOOLEAN result; // al

  if ( P )
  {
    v2 = (HMODULE)*((_QWORD *)P + 90);
    if ( v2 )
    {
      FreeLibrary(v2);
      *((_QWORD *)P + 90) = 0;
    }
    v3 = (void *)*((_QWORD *)P + 23);
    if ( v3 )
      RtlFreeHeap(*((HANDLE *)P + 18), 0, v3);
    *((_OWORD *)P + 9) = 0;
    *((_OWORD *)P + 10) = 0;
    *((_OWORD *)P + 11) = 0;
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(P + 104));
    if ( *(_QWORD *)P )
      memset_0(*(void **)P, 0, 0x5Cu);
    if ( *((_QWORD *)P + 89) )
      EtwEventUnregister();
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x140015034  test    rcx, rcx
0x140015037  jz      locret_1400150E1
0x14001503d  push    rbx
0x14001503e  sub     rsp, 20h
0x140015042  mov     rbx, rcx
0x140015045  mov     rcx, [rcx+2D0h]; hLibModule
0x14001504c  test    rcx, rcx
0x14001504f  jz      short loc_140015062
0x140015051  call    cs:__imp_FreeLibrary
0x140015057  mov     qword ptr [rbx+2D0h], 0
0x140015062  mov     r8, [rbx+0B8h]; P
0x140015069  test    r8, r8
0x14001506c  jz      short loc_14001507D
0x14001506e  mov     rcx, [rbx+90h]; HeapHandle
0x140015075  xor     edx, edx; Flags
0x140015077  call    cs:__imp_RtlFreeHeap
0x14001507d  xorps   xmm0, xmm0
0x140015080  lea     rcx, [rbx+68h]; CriticalSection
0x140015084  movups  xmmword ptr [rbx+90h], xmm0
0x14001508b  movups  xmmword ptr [rbx+0A0h], xmm0
0x140015092  movups  xmmword ptr [rbx+0B0h], xmm0
0x140015099  call    cs:__imp_RtlDeleteCriticalSection
0x14001509f  mov     rcx, [rbx]; void *
0x1400150a2  test    rcx, rcx
0x1400150a5  jz      short loc_1400150B2
0x1400150a7  xor     edx, edx; Val
0x1400150a9  lea     r8d, [rdx+5Ch]; Size
0x1400150ad  call    memset_0
0x1400150b2  mov     rcx, [rbx+2C8h]
0x1400150b9  test    rcx, rcx
0x1400150bc  jz      short loc_1400150C4
0x1400150be  call    cs:__imp_EtwEventUnregister
0x1400150c4  mov     rcx, gs:60h
0x1400150cd  mov     r8, rbx; P
0x1400150d0  xor     edx, edx; Flags
0x1400150d2  mov     rcx, [rcx+30h]; HeapHandle
0x1400150d6  call    cs:__imp_RtlFreeHeap
0x1400150dc  add     rsp, 20h
0x1400150e0  pop     rbx
0x1400150e1  retn
```
