# AslLogDelete

- ea: `0x180054224`
- end: `0x1800542d1`
- name: `AslLogDelete`
- size: `173`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000aa10`
- `0x18005377c`
- `0x180069110`

## callees

- `0x180002874`
- `0x180002b63`
- `0x180054224`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180054266`
- `KERNEL32!HeapFree` at `0x180054266`
- `ntdll!RtlDeleteCriticalSection` at `0x180054288`
- `ntdll!RtlDeleteCriticalSection` at `0x180054288`
- `ntdll!RtlFreeHeap` at `0x1800542c5`
- `ntdll!RtlFreeHeap` at `0x1800542c5`
- `ntdll!EtwEventUnregister` at `0x1800542ad`
- `ntdll!EtwEventUnregister` at `0x1800542ad`

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
      WINRT_IMPL_FreeLibrary(v2);
      *((_QWORD *)P + 90) = 0;
    }
    v3 = (void *)*((_QWORD *)P + 23);
    if ( v3 )
      HeapFree(*((HANDLE *)P + 18), 0, v3);
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
0x180054224  test    rcx, rcx
0x180054227  jz      locret_1800542D0
0x18005422d  push    rbx
0x18005422e  sub     rsp, 20h
0x180054232  mov     rbx, rcx
0x180054235  mov     rcx, [rcx+2D0h]; hLibModule
0x18005423c  test    rcx, rcx
0x18005423f  jz      short loc_180054251
0x180054241  call    WINRT_IMPL_FreeLibrary
0x180054246  mov     qword ptr [rbx+2D0h], 0
0x180054251  mov     r8, [rbx+0B8h]; lpMem
0x180054258  test    r8, r8
0x18005425b  jz      short loc_18005426C
0x18005425d  mov     rcx, [rbx+90h]; hHeap
0x180054264  xor     edx, edx; dwFlags
0x180054266  call    cs:__imp_HeapFree
0x18005426c  xorps   xmm0, xmm0
0x18005426f  lea     rcx, [rbx+68h]; CriticalSection
0x180054273  movups  xmmword ptr [rbx+90h], xmm0
0x18005427a  movups  xmmword ptr [rbx+0A0h], xmm0
0x180054281  movups  xmmword ptr [rbx+0B0h], xmm0
0x180054288  call    cs:__imp_RtlDeleteCriticalSection
0x18005428e  mov     rcx, [rbx]; void *
0x180054291  test    rcx, rcx
0x180054294  jz      short loc_1800542A1
0x180054296  xor     edx, edx; Val
0x180054298  lea     r8d, [rdx+5Ch]; Size
0x18005429c  call    memset_0
0x1800542a1  mov     rcx, [rbx+2C8h]
0x1800542a8  test    rcx, rcx
0x1800542ab  jz      short loc_1800542B3
0x1800542ad  call    cs:__imp_EtwEventUnregister
0x1800542b3  mov     rcx, gs:60h
0x1800542bc  mov     r8, rbx; P
0x1800542bf  xor     edx, edx; Flags
0x1800542c1  mov     rcx, [rcx+30h]; HeapHandle
0x1800542c5  call    cs:__imp_RtlFreeHeap
0x1800542cb  add     rsp, 20h
0x1800542cf  pop     rbx
0x1800542d0  retn
```
