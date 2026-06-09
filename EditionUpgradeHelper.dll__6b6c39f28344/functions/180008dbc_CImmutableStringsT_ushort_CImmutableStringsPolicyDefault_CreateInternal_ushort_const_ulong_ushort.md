# CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)

- ea: `0x180008dbc`
- end: `0x180008ee4`
- name: `?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z`
- size: `296`
- prototype: `__int64 __fastcall(void *Src, unsigned int, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008740`
- `0x18000a240`

## callees

- `0x180008c60`
- `0x180008dbc`
- `0x180009978`
- `0x18002664c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ebf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ebf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ecd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ecd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e73`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e73`

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
0x180008dbc  push    rbx
0x180008dbe  push    rbp
0x180008dbf  push    rsi
0x180008dc0  push    rdi
0x180008dc1  push    r12
0x180008dc3  push    r14
0x180008dc5  push    r15
0x180008dc7  sub     rsp, 20h
0x180008dcb  xor     ebx, ebx
0x180008dcd  mov     ebp, edx
0x180008dcf  mov     r14, r8
0x180008dd2  mov     r15, rcx
0x180008dd5  test    rcx, rcx
0x180008dd8  jz      loc_180008EAE
0x180008dde  lea     esi, [rbp+1]
0x180008de1  mov     r12d, 80070216h
0x180008de7  cmp     esi, ebp
0x180008de9  jb      short loc_180008DEF
0x180008deb  xor     edi, edi
0x180008ded  jmp     short loc_180008DFC
0x180008def  xor     esi, esi
0x180008df1  mov     ecx, r12d
0x180008df4  mov     edi, r12d
0x180008df7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180008dfc  mov     ecx, edi
0x180008dfe  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008e03  test    edi, edi
0x180008e05  jns     short loc_180008E13
0x180008e07  mov     ecx, edi
0x180008e09  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180008e0e  jmp     loc_180008EB3
0x180008e13  test    esi, esi
0x180008e15  jz      short loc_180008E33
0x180008e17  lea     ecx, [rsi+rsi]
0x180008e1a  mov     eax, ecx
0x180008e1c  shr     eax, 1
0x180008e1e  cmp     eax, esi
0x180008e20  jz      short loc_180008E2F
0x180008e22  mov     ecx, r12d
0x180008e25  mov     edi, r12d
0x180008e28  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180008e2d  jmp     short loc_180008E37
0x180008e2f  mov     esi, ecx
0x180008e31  jmp     short loc_180008E35
0x180008e33  xor     esi, esi
0x180008e35  xor     edi, edi
0x180008e37  mov     ecx, edi
0x180008e39  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008e3e  test    edi, edi
0x180008e40  js      short loc_180008E07
0x180008e42  lea     eax, [rsi+4]
0x180008e45  cmp     eax, esi
0x180008e47  jb      short loc_180008E4F
0x180008e49  mov     esi, eax
0x180008e4b  xor     edi, edi
0x180008e4d  jmp     short loc_180008E5A
0x180008e4f  mov     ecx, r12d
0x180008e52  mov     edi, r12d
0x180008e55  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180008e5a  mov     ecx, edi
0x180008e5c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008e61  test    edi, edi
0x180008e63  js      short loc_180008E07
0x180008e65  call    cs:__imp_GetProcessHeap
0x180008e6b  mov     r8d, esi; dwBytes
0x180008e6e  xor     edx, edx; dwFlags
0x180008e70  mov     rcx, rax; hHeap
0x180008e73  call    cs:__imp_HeapAlloc
0x180008e79  test    rax, rax
0x180008e7c  jnz     short loc_180008E85
0x180008e7e  mov     edi, 8007000Eh
0x180008e83  jmp     short loc_180008E07
0x180008e85  lea     rdi, [rax+4]
0x180008e89  mov     [rax], ebp
0x180008e8b  lea     rbx, ds:0[rbp*2]
0x180008e93  mov     rcx, rdi; void *
0x180008e96  mov     r8, rbx; Size
0x180008e99  mov     rdx, r15; Src
0x180008e9c  call    memcpy_0
0x180008ea1  xor     eax, eax
0x180008ea3  mov     [rbx+rdi], ax
0x180008ea7  xor     ebx, ebx
0x180008ea9  mov     [r14], rdi
0x180008eac  jmp     short loc_180008EB1
0x180008eae  mov     [r8], rbx
0x180008eb1  xor     edi, edi
0x180008eb3  mov     ecx, edi
0x180008eb5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008eba  test    rbx, rbx
0x180008ebd  jz      short loc_180008ED3
0x180008ebf  call    cs:__imp_GetProcessHeap
0x180008ec5  mov     r8, rbx; lpMem
0x180008ec8  xor     edx, edx; dwFlags
0x180008eca  mov     rcx, rax; hHeap
0x180008ecd  call    cs:__imp_HeapFree
0x180008ed3  mov     eax, edi
0x180008ed5  add     rsp, 20h
0x180008ed9  pop     r15
0x180008edb  pop     r14
0x180008edd  pop     r12
0x180008edf  pop     rdi
0x180008ee0  pop     rsi
0x180008ee1  pop     rbp
0x180008ee2  pop     rbx
0x180008ee3  retn
```
