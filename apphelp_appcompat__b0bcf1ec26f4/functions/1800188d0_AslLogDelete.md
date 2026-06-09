# AslLogDelete

- ea: `0x1800188d0`
- end: `0x180018982`
- name: `AslLogDelete`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180017794`
- `0x18002ac10`

## callees

- `0x1800188d0`
- `0x180018f20`
- `0x180059235`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180018915`
- `ntdll!RtlDeleteCriticalSection` at `0x180018915`
- `ntdll!RtlFreeHeap` at `0x180018964`
- `ntdll!RtlFreeHeap` at `0x180018964`
- `ntdll!EtwEventUnregister` at `0x18001893a`
- `ntdll!EtwEventUnregister` at `0x18001893a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001896c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001896c`

## pseudocode

```c
__int64 __fastcall AslLogDelete(__int64 a1)
{
  HMODULE v2; // rcx
  void *v3; // r8
  __int64 result; // rax

  if ( a1 )
  {
    v2 = *(HMODULE *)(a1 + 720);
    if ( v2 )
    {
      FreeLibrary(v2);
      *(_QWORD *)(a1 + 720) = 0;
    }
    v3 = *(void **)(a1 + 184);
    if ( v3 )
      RtlFreeHeap(*(HANDLE *)(a1 + 144), 0, v3);
    *(_OWORD *)(a1 + 144) = 0;
    *(_OWORD *)(a1 + 160) = 0;
    *(_OWORD *)(a1 + 176) = 0;
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
    if ( *(_QWORD *)a1 )
      memset_0(*(void **)a1, 0, 0x5Cu);
    if ( *(_QWORD *)(a1 + 712) )
      EtwEventUnregister();
    return AslFree(NtCurrentPeb()->ProcessHeap, a1);
  }
  return result;
}

```

## disassembly

```asm
0x1800188d0  test    rcx, rcx
0x1800188d3  jz      locret_18001895A
0x1800188d9  push    rbx
0x1800188da  sub     rsp, 20h
0x1800188de  mov     rbx, rcx
0x1800188e1  mov     rcx, [rcx+2D0h]; hLibModule
0x1800188e8  test    rcx, rcx
0x1800188eb  jnz     short loc_18001896C
0x1800188ed  mov     r8, [rbx+0B8h]; P
0x1800188f4  test    r8, r8
0x1800188f7  jnz     short loc_18001895B
0x1800188f9  xorps   xmm0, xmm0
0x1800188fc  lea     rcx, [rbx+68h]; CriticalSection
0x180018900  movups  xmmword ptr [rbx+90h], xmm0
0x180018907  movups  xmmword ptr [rbx+0A0h], xmm0
0x18001890e  movups  xmmword ptr [rbx+0B0h], xmm0
0x180018915  call    cs:__imp_RtlDeleteCriticalSection
0x18001891b  mov     rcx, [rbx]; void *
0x18001891e  test    rcx, rcx
0x180018921  jz      short loc_18001892E
0x180018923  xor     edx, edx; Val
0x180018925  lea     r8d, [rdx+5Ch]; Size
0x180018929  call    memset_0
0x18001892e  mov     rcx, [rbx+2C8h]
0x180018935  test    rcx, rcx
0x180018938  jz      short loc_180018940
0x18001893a  call    cs:__imp_EtwEventUnregister
0x180018940  mov     rcx, gs:60h
0x180018949  mov     rdx, rbx
0x18001894c  mov     rcx, [rcx+30h]
0x180018950  call    AslFree
0x180018955  add     rsp, 20h
0x180018959  pop     rbx
0x18001895a  retn
0x18001895b  mov     rcx, [rbx+90h]; HeapHandle
0x180018962  xor     edx, edx; Flags
0x180018964  call    cs:__imp_RtlFreeHeap
0x18001896a  jmp     short loc_1800188F9
0x18001896c  call    cs:__imp_FreeLibrary
0x180018972  mov     qword ptr [rbx+2D0h], 0
0x18001897d  jmp     loc_1800188ED
```
