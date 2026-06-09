# AllocateObjectBuffer

- ea: `0x180005f50`
- end: `0x180006017`
- name: `AllocateObjectBuffer`
- size: `199`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000acc0`
- `0x18000b1d0`

## callees

- `0x180005060`
- `0x180005f50`
- `0x1800066f0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180005faa`
- `ntdll!RtlAllocateHeap` at `0x180005faa`

## string_xrefs

- `0x180005fd9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180005ff8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall AllocateObjectBuffer(void *a1, _QWORD *a2, _DWORD *a3)
{
  NTSTATUS Property; // eax
  unsigned int v6; // esi
  PVOID Heap; // rax
  ULONG v9[14]; // [rsp+30h] [rbp-38h] BYREF
  SIZE_T Size; // [rsp+88h] [rbp+20h] BYREF

  LODWORD(Size) = 0;
  v9[0] = 0;
  Property = BCryptGetProperty(a1, L"ObjectLength", (PUCHAR)&Size, 4u, v9, 0);
  v6 = Property;
  if ( Property < 0 )
  {
    DebugTraceError((unsigned int)Property, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    return v6;
  }
  else
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
    if ( Heap )
    {
      *a2 = Heap;
      *a3 = Size;
      return 0;
    }
    else
    {
      DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
      return 3221225495LL;
    }
  }
}

```

## disassembly

```asm
0x180005f50  mov     r11, rsp
0x180005f53  push    rbx
0x180005f54  push    rbp
0x180005f55  push    rsi
0x180005f56  push    rdi
0x180005f57  sub     rsp, 48h
0x180005f5b  xor     ebp, ebp
0x180005f5d  lea     rax, [r11-38h]
0x180005f61  mov     rbx, r8
0x180005f64  mov     [rsp+68h+dwFlags], ebp; dwFlags
0x180005f68  mov     rdi, rdx
0x180005f6b  mov     [r11-48h], rax
0x180005f6f  mov     r9d, 4; cbOutput
0x180005f75  mov     [r11+20h], ebp
0x180005f79  lea     r8, [r11+20h]; pbOutput
0x180005f7d  mov     [rsp+68h+var_38], ebp
0x180005f81  lea     rdx, aObjectlength; "ObjectLength"
0x180005f88  call    BCryptGetProperty
0x180005f8d  mov     esi, eax
0x180005f8f  test    eax, eax
0x180005f91  js      short loc_180005FD3
0x180005f93  mov     rcx, gs:60h
0x180005f9c  xor     edx, edx; Flags
0x180005f9e  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x180005fa6  mov     rcx, [rcx+30h]; HeapHandle
0x180005faa  call    cs:__imp_RtlAllocateHeap
0x180005fb1  nop     dword ptr [rax+rax+00h]
0x180005fb6  test    rax, rax
0x180005fb9  jz      short loc_180005FF2
0x180005fbb  mov     [rdi], rax
0x180005fbe  mov     eax, dword ptr [rsp+68h+Size]
0x180005fc5  mov     [rbx], eax
0x180005fc7  mov     eax, ebp
0x180005fc9  add     rsp, 48h
0x180005fcd  pop     rdi
0x180005fce  pop     rsi
0x180005fcf  pop     rbp
0x180005fd0  pop     rbx
0x180005fd1  retn
0x180005fd3  mov     r9d, 3E3h
0x180005fd9  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005fe0  lea     rdx, aStatus; "Status"
0x180005fe7  mov     ecx, esi
0x180005fe9  call    DebugTraceError
0x180005fee  mov     eax, esi
0x180005ff0  jmp     short loc_180005FC9
0x180005ff2  mov     r9d, 3EBh
0x180005ff8  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005fff  lea     rdx, aStatus; "Status"
0x180006006  mov     ecx, 0C0000017h
0x18000600b  call    DebugTraceError
0x180006010  mov     eax, 0C0000017h
0x180006015  jmp     short loc_180005FC9
```
