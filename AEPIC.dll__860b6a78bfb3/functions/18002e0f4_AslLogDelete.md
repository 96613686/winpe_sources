# AslLogDelete

- ea: `0x18002e0f4`
- end: `0x18002e19f`
- name: `AslLogDelete`
- size: `171`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800228b0`
- `0x1800228d4`
- `0x18002d860`

## callees

- `0x180006938`
- `0x18002979c`
- `0x18002e0f4`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18002e159`
- `ntdll!RtlDeleteCriticalSection` at `0x18002e159`
- `ntdll!EtwEventUnregister` at `0x18002e17e`
- `ntdll!EtwEventUnregister` at `0x18002e17e`
- `ntdll!RtlFreeHeap` at `0x18002e137`
- `ntdll!RtlFreeHeap` at `0x18002e137`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e111`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e111`

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
0x18002e0f4  test    rcx, rcx
0x18002e0f7  jz      locret_18002E19E
0x18002e0fd  push    rbx
0x18002e0fe  sub     rsp, 20h
0x18002e102  mov     rbx, rcx
0x18002e105  mov     rcx, [rcx+2D0h]; hLibModule
0x18002e10c  test    rcx, rcx
0x18002e10f  jz      short loc_18002E122
0x18002e111  call    cs:__imp_FreeLibrary
0x18002e117  mov     qword ptr [rbx+2D0h], 0
0x18002e122  mov     r8, [rbx+0B8h]; P
0x18002e129  test    r8, r8
0x18002e12c  jz      short loc_18002E13D
0x18002e12e  mov     rcx, [rbx+90h]; HeapHandle
0x18002e135  xor     edx, edx; Flags
0x18002e137  call    cs:__imp_RtlFreeHeap
0x18002e13d  xorps   xmm0, xmm0
0x18002e140  lea     rcx, [rbx+68h]; CriticalSection
0x18002e144  movups  xmmword ptr [rbx+90h], xmm0
0x18002e14b  movups  xmmword ptr [rbx+0A0h], xmm0
0x18002e152  movups  xmmword ptr [rbx+0B0h], xmm0
0x18002e159  call    cs:__imp_RtlDeleteCriticalSection
0x18002e15f  mov     rcx, [rbx]; void *
0x18002e162  test    rcx, rcx
0x18002e165  jz      short loc_18002E172
0x18002e167  xor     edx, edx; Val
0x18002e169  lea     r8d, [rdx+5Ch]; Size
0x18002e16d  call    memset_0
0x18002e172  mov     rcx, [rbx+2C8h]
0x18002e179  test    rcx, rcx
0x18002e17c  jz      short loc_18002E184
0x18002e17e  call    cs:__imp_EtwEventUnregister
0x18002e184  mov     rcx, gs:60h
0x18002e18d  mov     rdx, rbx
0x18002e190  mov     rcx, [rcx+30h]
0x18002e194  call    AslFree
0x18002e199  add     rsp, 20h
0x18002e19d  pop     rbx
0x18002e19e  retn
```
