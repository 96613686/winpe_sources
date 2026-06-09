# CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateCchBufferN(ushort,ulong,ushort * *)

- ea: `0x18000b57c`
- end: `0x18000b684`
- name: `?CreateCchBufferN@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJGKPEAPEAG@Z`
- size: `264`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b984`
- `0x1800133e0`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000b57c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b66f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b66f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b5fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b5fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b661`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b661`

## pseudocode

```c
__int64 __fastcall CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateCchBufferN(
        __int64 a1,
        int a2,
        _QWORD *a3)
{
  _DWORD *v3; // rbx
  unsigned int v6; // esi
  int v7; // edi
  HANDLE ProcessHeap; // rax
  __int64 v9; // rcx
  _DWORD *v10; // rdx
  HANDLE v11; // rax

  v3 = 0;
  if ( a2 )
  {
    v6 = 2 * a2;
    if ( (unsigned int)(2 * a2) >> 1 == a2 )
    {
      v7 = 0;
    }
    else
    {
      v6 = 0;
      v7 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
    }
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
    v3 = HeapAlloc(ProcessHeap, 0, v6);
    if ( !v3 )
    {
      v7 = -2147024882;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024882);
      goto LABEL_20;
    }
    if ( a2 )
    {
      *v3 = a2 - 1;
      v7 = 0;
    }
    else
    {
      v7 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
    {
LABEL_6:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
      goto LABEL_20;
    }
    v9 = (unsigned int)*v3;
    v10 = v3 + 1;
    v3 = 0;
    *((_WORD *)v10 + v9) = 0;
    *a3 = v10;
  }
  else
  {
    *a3 = 0;
  }
  v7 = 0;
LABEL_20:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v3 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v3);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b57c  push    rbx
0x18000b57e  push    rbp
0x18000b57f  push    rsi
0x18000b580  push    rdi
0x18000b581  push    r14
0x18000b583  push    r15
0x18000b585  sub     rsp, 28h
0x18000b589  xor     ebx, ebx
0x18000b58b  mov     r15, r8
0x18000b58e  mov     r14d, edx
0x18000b591  test    edx, edx
0x18000b593  jz      loc_18000B650
0x18000b599  lea     esi, [rdx+rdx]
0x18000b59c  mov     ebp, 80070216h
0x18000b5a1  mov     eax, esi
0x18000b5a3  shr     eax, 1
0x18000b5a5  cmp     eax, edx
0x18000b5a7  jz      short loc_18000B5B6
0x18000b5a9  xor     esi, esi
0x18000b5ab  mov     ecx, ebp
0x18000b5ad  mov     edi, ebp
0x18000b5af  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b5b4  jmp     short loc_18000B5B8
0x18000b5b6  xor     edi, edi
0x18000b5b8  mov     ecx, edi
0x18000b5ba  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b5bf  test    edi, edi
0x18000b5c1  jns     short loc_18000B5CF
0x18000b5c3  mov     ecx, edi
0x18000b5c5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b5ca  jmp     loc_18000B655
0x18000b5cf  lea     eax, [rsi+4]
0x18000b5d2  cmp     eax, esi
0x18000b5d4  jb      short loc_18000B5DC
0x18000b5d6  mov     esi, eax
0x18000b5d8  xor     edi, edi
0x18000b5da  jmp     short loc_18000B5E5
0x18000b5dc  mov     ecx, ebp
0x18000b5de  mov     edi, ebp
0x18000b5e0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b5e5  mov     ecx, edi
0x18000b5e7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b5ec  test    edi, edi
0x18000b5ee  js      short loc_18000B5C3
0x18000b5f0  call    cs:__imp_GetProcessHeap
0x18000b5f6  mov     r8d, esi; dwBytes
0x18000b5f9  xor     edx, edx; dwFlags
0x18000b5fb  mov     rcx, rax; hHeap
0x18000b5fe  call    cs:__imp_HeapAlloc
0x18000b604  mov     rbx, rax
0x18000b607  test    rax, rax
0x18000b60a  jnz     short loc_18000B61A
0x18000b60c  mov     edi, 8007000Eh
0x18000b611  mov     ecx, edi
0x18000b613  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b618  jmp     short loc_18000B655
0x18000b61a  lea     eax, [r14-1]
0x18000b61e  cmp     eax, r14d
0x18000b621  ja      short loc_18000B629
0x18000b623  mov     [rbx], eax
0x18000b625  xor     edi, edi
0x18000b627  jmp     short loc_18000B632
0x18000b629  mov     ecx, ebp
0x18000b62b  mov     edi, ebp
0x18000b62d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b632  mov     ecx, edi
0x18000b634  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b639  test    edi, edi
0x18000b63b  js      short loc_18000B5C3
0x18000b63d  mov     ecx, [rbx]
0x18000b63f  lea     rdx, [rbx+4]
0x18000b643  xor     eax, eax
0x18000b645  xor     ebx, ebx
0x18000b647  mov     [rdx+rcx*2], ax
0x18000b64b  mov     [r15], rdx
0x18000b64e  jmp     short loc_18000B653
0x18000b650  mov     [r8], rbx
0x18000b653  xor     edi, edi
0x18000b655  mov     ecx, edi
0x18000b657  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b65c  test    rbx, rbx
0x18000b65f  jz      short loc_18000B675
0x18000b661  call    cs:__imp_GetProcessHeap
0x18000b667  mov     r8, rbx; lpMem
0x18000b66a  xor     edx, edx; dwFlags
0x18000b66c  mov     rcx, rax; hHeap
0x18000b66f  call    cs:__imp_HeapFree
0x18000b675  mov     eax, edi
0x18000b677  add     rsp, 28h
0x18000b67b  pop     r15
0x18000b67d  pop     r14
0x18000b67f  pop     rdi
0x18000b680  pop     rsi
0x18000b681  pop     rbp
0x18000b682  pop     rbx
0x18000b683  retn
```
