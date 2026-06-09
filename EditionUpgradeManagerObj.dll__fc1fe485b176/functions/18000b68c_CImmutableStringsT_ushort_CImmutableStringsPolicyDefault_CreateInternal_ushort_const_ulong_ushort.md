# CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)

- ea: `0x18000b68c`
- end: `0x18000b7b4`
- name: `?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z`
- size: `296`
- prototype: `__int64 __fastcall(void *Src, unsigned int, _QWORD *)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b884`
- `0x18000bb10`
- `0x180011fac`
- `0x1800133e0`
- `0x180013780`
- `0x1800142f8`
- `0x180018388`
- `0x1800188f8`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000b68c`
- `0x18002295c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b79d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b79d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b743`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b743`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b735`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b78f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b735`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b78f`

## pseudocode

```c
__int64 __fastcall CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
        void *Src,
        unsigned int a2,
        _QWORD *a3)
{
  __int64 v3; // rbp
  unsigned int v6; // esi
  int v7; // edi
  HANDLE ProcessHeap; // rax
  _DWORD *v9; // rax
  _DWORD *v10; // rdi

  v3 = a2;
  if ( !Src )
  {
    *a3 = 0;
    goto LABEL_22;
  }
  v6 = a2 + 1;
  if ( a2 + 1 < a2 )
  {
    v6 = 0;
    v7 = -2147024362;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
  }
  else
  {
    v7 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v7 < 0 )
    goto LABEL_6;
  if ( !v6 )
  {
    v6 = 0;
    goto LABEL_12;
  }
  if ( (2 * v6) >> 1 == v6 )
  {
    v6 *= 2;
LABEL_12:
    v7 = 0;
    goto LABEL_13;
  }
  v7 = -2147024362;
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
LABEL_13:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v7 < 0 )
    goto LABEL_6;
  if ( v6 + 4 < v6 )
  {
    v7 = -2147024362;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
  }
  else
  {
    v6 += 4;
    v7 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v7 < 0 )
    goto LABEL_6;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, v6);
  if ( v9 )
  {
    v10 = v9 + 1;
    *v9 = v3;
    memcpy_0(v9 + 1, Src, 2 * v3);
    *((_WORD *)v10 + v3) = 0;
    *a3 = v10;
LABEL_22:
    v7 = 0;
    goto LABEL_23;
  }
  v7 = -2147024882;
LABEL_6:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_23:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b68c  push    rbx
0x18000b68e  push    rbp
0x18000b68f  push    rsi
0x18000b690  push    rdi
0x18000b691  push    r12
0x18000b693  push    r14
0x18000b695  push    r15
0x18000b697  sub     rsp, 20h
0x18000b69b  xor     ebx, ebx
0x18000b69d  mov     ebp, edx
0x18000b69f  mov     r14, r8
0x18000b6a2  mov     r15, rcx
0x18000b6a5  test    rcx, rcx
0x18000b6a8  jz      loc_18000B77E
0x18000b6ae  lea     esi, [rbp+1]
0x18000b6b1  mov     r12d, 80070216h
0x18000b6b7  cmp     esi, ebp
0x18000b6b9  jb      short loc_18000B6BF
0x18000b6bb  xor     edi, edi
0x18000b6bd  jmp     short loc_18000B6CC
0x18000b6bf  xor     esi, esi
0x18000b6c1  mov     ecx, r12d
0x18000b6c4  mov     edi, r12d
0x18000b6c7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b6cc  mov     ecx, edi
0x18000b6ce  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b6d3  test    edi, edi
0x18000b6d5  jns     short loc_18000B6E3
0x18000b6d7  mov     ecx, edi
0x18000b6d9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b6de  jmp     loc_18000B783
0x18000b6e3  test    esi, esi
0x18000b6e5  jz      short loc_18000B703
0x18000b6e7  lea     ecx, [rsi+rsi]
0x18000b6ea  mov     eax, ecx
0x18000b6ec  shr     eax, 1
0x18000b6ee  cmp     eax, esi
0x18000b6f0  jz      short loc_18000B6FF
0x18000b6f2  mov     ecx, r12d
0x18000b6f5  mov     edi, r12d
0x18000b6f8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b6fd  jmp     short loc_18000B707
0x18000b6ff  mov     esi, ecx
0x18000b701  jmp     short loc_18000B705
0x18000b703  xor     esi, esi
0x18000b705  xor     edi, edi
0x18000b707  mov     ecx, edi
0x18000b709  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b70e  test    edi, edi
0x18000b710  js      short loc_18000B6D7
0x18000b712  lea     eax, [rsi+4]
0x18000b715  cmp     eax, esi
0x18000b717  jb      short loc_18000B71F
0x18000b719  mov     esi, eax
0x18000b71b  xor     edi, edi
0x18000b71d  jmp     short loc_18000B72A
0x18000b71f  mov     ecx, r12d
0x18000b722  mov     edi, r12d
0x18000b725  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b72a  mov     ecx, edi
0x18000b72c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b731  test    edi, edi
0x18000b733  js      short loc_18000B6D7
0x18000b735  call    cs:__imp_GetProcessHeap
0x18000b73b  mov     r8d, esi; dwBytes
0x18000b73e  xor     edx, edx; dwFlags
0x18000b740  mov     rcx, rax; hHeap
0x18000b743  call    cs:__imp_HeapAlloc
0x18000b749  test    rax, rax
0x18000b74c  jnz     short loc_18000B755
0x18000b74e  mov     edi, 8007000Eh
0x18000b753  jmp     short loc_18000B6D7
0x18000b755  lea     rdi, [rax+4]
0x18000b759  mov     [rax], ebp
0x18000b75b  lea     rbx, ds:0[rbp*2]
0x18000b763  mov     rcx, rdi; void *
0x18000b766  mov     r8, rbx; Size
0x18000b769  mov     rdx, r15; Src
0x18000b76c  call    memcpy_0
0x18000b771  xor     eax, eax
0x18000b773  mov     [rbx+rdi], ax
0x18000b777  xor     ebx, ebx
0x18000b779  mov     [r14], rdi
0x18000b77c  jmp     short loc_18000B781
0x18000b77e  mov     [r8], rbx
0x18000b781  xor     edi, edi
0x18000b783  mov     ecx, edi
0x18000b785  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b78a  test    rbx, rbx
0x18000b78d  jz      short loc_18000B7A3
0x18000b78f  call    cs:__imp_GetProcessHeap
0x18000b795  mov     r8, rbx; lpMem
0x18000b798  xor     edx, edx; dwFlags
0x18000b79a  mov     rcx, rax; hHeap
0x18000b79d  call    cs:__imp_HeapFree
0x18000b7a3  mov     eax, edi
0x18000b7a5  add     rsp, 20h
0x18000b7a9  pop     r15
0x18000b7ab  pop     r14
0x18000b7ad  pop     r12
0x18000b7af  pop     rdi
0x18000b7b0  pop     rsi
0x18000b7b1  pop     rbp
0x18000b7b2  pop     rbx
0x18000b7b3  retn
```
