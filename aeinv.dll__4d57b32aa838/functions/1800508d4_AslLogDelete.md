# AslLogDelete

- ea: `0x1800508d4`
- end: `0x18005097e`
- name: `AslLogDelete`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180028028`
- `0x1800506d0`
- `0x1800508a4`

## callees

- `0x18001cce4`
- `0x1800508d4`
- `0x18005a8bc`
- `0x18005ab60`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x18005095d`
- `ntdll!EtwEventUnregister` at `0x18005095d`
- `ntdll!RtlFreeHeap` at `0x180050916`
- `ntdll!RtlFreeHeap` at `0x180050916`
- `ntdll!RtlDeleteCriticalSection` at `0x180050938`
- `ntdll!RtlDeleteCriticalSection` at `0x180050938`

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
      FreeLibrary_0(v2);
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
0x1800508d4  test    rcx, rcx
0x1800508d7  jz      locret_18005097D
0x1800508dd  push    rbx
0x1800508de  sub     rsp, 20h
0x1800508e2  mov     rbx, rcx
0x1800508e5  mov     rcx, [rcx+2D0h]; hLibModule
0x1800508ec  test    rcx, rcx
0x1800508ef  jz      short loc_180050901
0x1800508f1  call    FreeLibrary_0
0x1800508f6  mov     qword ptr [rbx+2D0h], 0
0x180050901  mov     r8, [rbx+0B8h]; P
0x180050908  test    r8, r8
0x18005090b  jz      short loc_18005091C
0x18005090d  mov     rcx, [rbx+90h]; HeapHandle
0x180050914  xor     edx, edx; Flags
0x180050916  call    cs:__imp_RtlFreeHeap
0x18005091c  xorps   xmm0, xmm0
0x18005091f  lea     rcx, [rbx+68h]; CriticalSection
0x180050923  movups  xmmword ptr [rbx+90h], xmm0
0x18005092a  movups  xmmword ptr [rbx+0A0h], xmm0
0x180050931  movups  xmmword ptr [rbx+0B0h], xmm0
0x180050938  call    cs:__imp_RtlDeleteCriticalSection
0x18005093e  mov     rcx, [rbx]; void *
0x180050941  test    rcx, rcx
0x180050944  jz      short loc_180050951
0x180050946  xor     edx, edx; Val
0x180050948  lea     r8d, [rdx+5Ch]; Size
0x18005094c  call    memset_0
0x180050951  mov     rcx, [rbx+2C8h]
0x180050958  test    rcx, rcx
0x18005095b  jz      short loc_180050963
0x18005095d  call    cs:__imp_EtwEventUnregister
0x180050963  mov     rcx, gs:60h
0x18005096c  mov     rdx, rbx
0x18005096f  mov     rcx, [rcx+30h]
0x180050973  call    AslFree
0x180050978  add     rsp, 20h
0x18005097c  pop     rbx
0x18005097d  retn
```
