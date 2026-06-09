# AslLogDelete

- ea: `0x18004795c`
- end: `0x180047a0a`
- name: `AslLogDelete`
- size: `174`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008424`
- `0x180046ed4`
- `0x1800e9ee0`

## callees

- `0x180005914`
- `0x18004795c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047979`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047979`
- `ntdll!RtlDeleteCriticalSection` at `0x1800479c1`
- `ntdll!RtlDeleteCriticalSection` at `0x1800479c1`
- `ntdll!EtwEventUnregister` at `0x1800479e6`
- `ntdll!EtwEventUnregister` at `0x1800479e6`
- `ntdll!RtlFreeHeap` at `0x18004799f`
- `ntdll!RtlFreeHeap` at `0x1800479fe`
- `ntdll!RtlFreeHeap` at `0x18004799f`
- `ntdll!RtlFreeHeap` at `0x1800479fe`

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
0x18004795c  test    rcx, rcx
0x18004795f  jz      locret_180047A09
0x180047965  push    rbx
0x180047966  sub     rsp, 20h
0x18004796a  mov     rbx, rcx
0x18004796d  mov     rcx, [rcx+2D0h]; hLibModule
0x180047974  test    rcx, rcx
0x180047977  jz      short loc_18004798A
0x180047979  call    cs:__imp_FreeLibrary
0x18004797f  mov     qword ptr [rbx+2D0h], 0
0x18004798a  mov     r8, [rbx+0B8h]; P
0x180047991  test    r8, r8
0x180047994  jz      short loc_1800479A5
0x180047996  mov     rcx, [rbx+90h]; HeapHandle
0x18004799d  xor     edx, edx; Flags
0x18004799f  call    cs:__imp_RtlFreeHeap
0x1800479a5  xorps   xmm0, xmm0
0x1800479a8  lea     rcx, [rbx+68h]; CriticalSection
0x1800479ac  movups  xmmword ptr [rbx+90h], xmm0
0x1800479b3  movups  xmmword ptr [rbx+0A0h], xmm0
0x1800479ba  movups  xmmword ptr [rbx+0B0h], xmm0
0x1800479c1  call    cs:__imp_RtlDeleteCriticalSection
0x1800479c7  mov     rcx, [rbx]; void *
0x1800479ca  test    rcx, rcx
0x1800479cd  jz      short loc_1800479DA
0x1800479cf  xor     edx, edx; Val
0x1800479d1  lea     r8d, [rdx+5Ch]; Size
0x1800479d5  call    memset_0
0x1800479da  mov     rcx, [rbx+2C8h]
0x1800479e1  test    rcx, rcx
0x1800479e4  jz      short loc_1800479EC
0x1800479e6  call    cs:__imp_EtwEventUnregister
0x1800479ec  mov     rcx, gs:60h
0x1800479f5  mov     r8, rbx; P
0x1800479f8  xor     edx, edx; Flags
0x1800479fa  mov     rcx, [rcx+30h]; HeapHandle
0x1800479fe  call    cs:__imp_RtlFreeHeap
0x180047a04  add     rsp, 20h
0x180047a08  pop     rbx
0x180047a09  retn
```
