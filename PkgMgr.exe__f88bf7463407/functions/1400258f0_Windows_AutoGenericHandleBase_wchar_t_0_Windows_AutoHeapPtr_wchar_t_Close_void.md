# Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)

- ea: `0x1400258f0`
- end: `0x14002592c`
- name: `?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140024c30`
- `0x140024de0`
- `0x140024ed0`
- `0x140024fe0`
- `0x1400251e4`
- `0x1400253b0`
- `0x140025660`
- `0x140025880`
- `0x1400259d0`
- `0x140025b30`

## callees

- `0x1400258f0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140025910`
- `ntdll!RtlFreeHeap` at `0x140025910`

## pseudocode

```c
void __fastcall Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(PVOID *a1)
{
  int v2; // eax

  if ( *a1 )
  {
    LOBYTE(v2) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a1);
    if ( !v2 )
      __fastfail(7u);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x1400258f0  push    rbx
0x1400258f2  sub     rsp, 20h
0x1400258f6  mov     r8, [rcx]; P
0x1400258f9  mov     rbx, rcx
0x1400258fc  test    r8, r8
0x1400258ff  jz      short loc_140025926
0x140025901  mov     rcx, gs:60h
0x14002590a  xor     edx, edx; Flags
0x14002590c  mov     rcx, [rcx+30h]; HeapHandle
0x140025910  call    cs:__imp_RtlFreeHeap
0x140025916  test    eax, eax
0x140025918  jnz     short loc_14002591F
0x14002591a  lea     ecx, [rax+7]
0x14002591d  int     29h; Win8: RtlFailFast(ecx)
0x14002591f  mov     qword ptr [rbx], 0
0x140025926  add     rsp, 20h
0x14002592a  pop     rbx
0x14002592b  retn
```
