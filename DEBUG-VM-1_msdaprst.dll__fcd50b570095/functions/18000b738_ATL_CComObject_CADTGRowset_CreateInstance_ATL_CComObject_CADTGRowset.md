# ATL::CComObject<CADTGRowset>::CreateInstance(ATL::CComObject<CADTGRowset> * *)

- ea: `0x18000b738`
- end: `0x18000b7dd`
- name: `?CreateInstance@?$CComObject@VCADTGRowset@@@ATL@@SAJPEAPEAV12@@Z`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e5ec`
- `0x1800146d0`

## callees

- `0x180001d94`
- `0x18000a210`
- `0x18000b738`
- `0x180020344`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CADTGRowset>::CreateInstance(CRowset **a1, unsigned int a2)
{
  unsigned int v4; // esi
  CADTGRowset *v5; // rax
  CRowset *v6; // rbx
  unsigned int v7; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v4 = -2147024882;
  v5 = (CADTGRowset *)MMMAlloc(0x2C8u, a2);
  v6 = v5;
  if ( v5 )
  {
    try
    {
      CADTGRowset::CADTGRowset(v5);
      *(_QWORD *)v6 = &ATL::CComObject<CADTGRowset>::`vftable';
      _InterlockedIncrement(&dword_1800454E8);
    }
    catch ( long v7 )
    {
      return v7;
    }
  }
  else
  {
    v6 = 0;
  }
  if ( v6 )
  {
    v4 = CRowset::FinalConstruct(v6);
    if ( v4 )
    {
      (*(void (__fastcall **)(CRowset *, __int64))(*(_QWORD *)v6 + 128LL))(v6, 1);
      v6 = 0;
    }
  }
  *a1 = v6;
  return v4;
}

```

## disassembly

```asm
0x18000b738  mov     [rsp+arg_8], rbx
0x18000b73d  mov     [rsp+arg_10], rsi
0x18000b742  push    rdi
0x18000b743  sub     rsp, 30h
0x18000b747  mov     rdi, rcx
0x18000b74a  test    rcx, rcx
0x18000b74d  jnz     short loc_18000B756
0x18000b74f  mov     eax, 80004003h
0x18000b754  jmp     short loc_18000B7CD
0x18000b756  mov     qword ptr [rcx], 0
0x18000b75d  mov     esi, 8007000Eh
0x18000b762  mov     ecx, 2C8h; unsigned int
0x18000b767  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b76c  mov     rbx, rax
0x18000b76f  mov     [rsp+38h+arg_0], rax
0x18000b774  test    rax, rax
0x18000b777  jz      short loc_18000B794
0x18000b779  mov     rcx, rax; this
0x18000b77c  call    ??0CADTGRowset@@QEAA@XZ; CADTGRowset::CADTGRowset(void)
0x18000b781  lea     rax, ??_7?$CComObject@VCADTGRowset@@@ATL@@6B@; const ATL::CComObject<CADTGRowset>::`vftable'
0x18000b788  mov     [rbx], rax
0x18000b78b  lock inc cs:dword_1800454E8
0x18000b792  jmp     short loc_18000B796
0x18000b794  xor     ebx, ebx
0x18000b796  test    rbx, rbx
0x18000b799  jz      short loc_18000B7C2
0x18000b79b  mov     rcx, rbx; this
0x18000b79e  call    ?FinalConstruct@CRowset@@QEAAJXZ; CRowset::FinalConstruct(void)
0x18000b7a3  mov     esi, eax
0x18000b7a5  test    eax, eax
0x18000b7a7  jz      short loc_18000B7C2
0x18000b7a9  mov     r8, [rbx]
0x18000b7ac  mov     edx, 1
0x18000b7b1  mov     rcx, rbx
0x18000b7b4  mov     rax, [r8+80h]
0x18000b7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7c0  xor     ebx, ebx
0x18000b7c2  mov     [rdi], rbx
0x18000b7c5  mov     eax, esi
0x18000b7c7  jmp     short loc_18000B7CD
0x18000b7c9  mov     eax, [rsp+38h+var_18]
0x18000b7cd  mov     rbx, [rsp+38h+arg_8]
0x18000b7d2  mov     rsi, [rsp+38h+arg_10]
0x18000b7d7  add     rsp, 30h
0x18000b7db  pop     rdi
0x18000b7dc  retn
```
