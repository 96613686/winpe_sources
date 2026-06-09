# s_DeepCopyStringHelper

- ea: `0x14007c7c0`
- end: `0x14007ca3f`
- name: `s_DeepCopyStringHelper`
- size: `639`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140078d04`
- `0x140079d40`
- `0x14007a2a8`
- `0x14007b398`
- `0x14007be28`
- `0x14007bf90`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140005518`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007c7c0`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14007c825`
- `KERNEL32!IsDebuggerPresent` at `0x14007c92b`
- `KERNEL32!IsDebuggerPresent` at `0x14007c9b2`
- `KERNEL32!IsDebuggerPresent` at `0x14007c825`
- `KERNEL32!IsDebuggerPresent` at `0x14007c92b`
- `KERNEL32!IsDebuggerPresent` at `0x14007c9b2`
- `wsdapi!WSDAllocateLinkedMemory` at `0x14007c8c8`
- `wsdapi!WSDAllocateLinkedMemory` at `0x14007c8c8`
- `wsdapi!WSDFreeLinkedMemory` at `0x14007ca1a`
- `wsdapi!WSDFreeLinkedMemory` at `0x14007ca1a`

## string_xrefs

- `0x14007c80d`: `termsrv\wms\src\middletier\discovery\common\common.cpp`
- `0x14007c908`: `termsrv\wms\src\middletier\discovery\common\common.cpp`
- `0x14007c98a`: `termsrv\wms\src\middletier\discovery\common\common.cpp`
- `0x14007c801`: `s_DeepCopyStringHelper`
- `0x14007c8f8`: `s_DeepCopyStringHelper`
- `0x14007c97d`: `s_DeepCopyStringHelper`
- `0x14007c90f`: `pszTempDest`

## pseudocode

```c
__int64 __fastcall s_DeepCopyStringHelper(int a1, const unsigned __int16 *a2, void *a3, unsigned __int16 **a4)
{
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // r12
  unsigned int v9; // r14d
  __int64 v10; // rdx
  unsigned __int64 v11; // rsi
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rbp
  int v14; // eax

  if ( !a2 )
  {
    v7 = -2147024809;
    v8 = L"pszSource";
    v9 = 110;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v7 = -2147467261;
    v8 = L"ppszDest";
    v9 = 111;
LABEL_3:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
      v9,
      L"s_DeepCopyStringHelper",
      L"CBRAEx",
      v8,
      v7);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
        v9,
        L"s_DeepCopyStringHelper",
        L"CBRAEx",
        v8,
        v7);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
        v9,
        L"s_DeepCopyStringHelper",
        L"CBRAEx",
        v8,
        v7);
    return v7;
  }
  *a4 = 0;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  v11 = v10 + 1;
  if ( a1 )
    v12 = (unsigned __int16 *)WSDAllocateLinkedMemory(a3, 2 * v10 + 2);
  else
    v12 = (unsigned __int16 *)operator new(saturated_mul(v11, 2u));
  v13 = v12;
  if ( v12 )
  {
    v14 = StringCchCopyW(v12, v11, a2);
    v7 = v14;
    if ( v14 >= 0 )
    {
      *a4 = v13;
    }
    else
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
        0x84u,
        L"s_DeepCopyStringHelper",
        L"CHRA",
        L"hr",
        v14);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
          132,
          L"s_DeepCopyStringHelper",
          L"CHRA",
          L"hr",
          v7);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
          132,
          L"s_DeepCopyStringHelper",
          L"CHRA",
          L"hr",
          v7);
      if ( a1 )
        WSDFreeLinkedMemory(v13);
      else
        operator delete(v13);
    }
  }
  else
  {
    v7 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
      0x80u,
      L"s_DeepCopyStringHelper",
      L"CPR",
      L"pszTempDest",
      -2147024882);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
        128,
        L"s_DeepCopyStringHelper",
        L"CPR",
        L"pszTempDest",
        -2147024882);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
        128,
        L"s_DeepCopyStringHelper",
        L"CPR",
        L"pszTempDest",
        -2147024882);
  }
  return v7;
}

```

## disassembly

```asm
0x14007c7c0  push    rbx
0x14007c7c2  push    rbp
0x14007c7c3  push    rsi
0x14007c7c4  push    rdi
0x14007c7c5  push    r12
0x14007c7c7  push    r13
0x14007c7c9  push    r14
0x14007c7cb  push    r15
0x14007c7cd  sub     rsp, 48h
0x14007c7d1  xor     r15d, r15d
0x14007c7d4  mov     rdi, r9
0x14007c7d7  mov     rbx, rdx
0x14007c7da  mov     r14d, ecx
0x14007c7dd  test    rdx, rdx
0x14007c7e0  jnz     loc_14007C886
0x14007c7e6  mov     ebx, 80070057h
0x14007c7eb  lea     r12, aPszsource; "pszSource"
0x14007c7f2  lea     r14d, [rdx+6Eh]
0x14007c7f6  lea     rbp, aCbraex; "CBRAEx"
0x14007c7fd  mov     [rsp+88h+var_60], ebx; int
0x14007c801  lea     rsi, aSDeepcopystrin; "s_DeepCopyStringHelper"
0x14007c808  mov     [rsp+88h+var_68], r12; unsigned __int16 *
0x14007c80d  lea     rdi, aTermsrvWmsSrcM; "termsrv\\wms\\src\\middletier\\discover"...
0x14007c814  mov     r9, rbp; unsigned __int16 *
0x14007c817  mov     r8, rsi; unsigned __int16 *
0x14007c81a  mov     rcx, rdi; unsigned __int16 *
0x14007c81d  mov     edx, r14d; unsigned int
0x14007c820  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007c825  call    cs:__imp_IsDebuggerPresent
0x14007c82b  test    eax, eax
0x14007c82d  jz      short loc_14007C85E
0x14007c82f  mov     [rsp+88h+var_50], ebx
0x14007c833  mov     r9d, r14d
0x14007c836  mov     [rsp+88h+var_58], r12
0x14007c83b  mov     qword ptr [rsp+88h+var_60], rbp
0x14007c840  mov     r8, rdi
0x14007c843  mov     [rsp+88h+var_68], rsi
0x14007c848  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14007c84f  mov     ecx, 2; unsigned __int8
0x14007c854  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007c859  jmp     loc_14007CA2C
0x14007c85e  mov     dword ptr [rsp+88h+var_58], ebx
0x14007c862  mov     r8d, r14d
0x14007c865  mov     qword ptr [rsp+88h+var_60], r12
0x14007c86a  mov     [rsp+88h+var_68], rbp
0x14007c86f  mov     r9, rsi
0x14007c872  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14007c879  mov     rdx, rdi
0x14007c87c  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007c881  jmp     loc_14007CA2C
0x14007c886  test    rdi, rdi
0x14007c889  jnz     short loc_14007C8A0
0x14007c88b  mov     ebx, 80004003h
0x14007c890  lea     r12, aPpszdest_0; "ppszDest"
0x14007c897  lea     r14d, [rdi+6Fh]
0x14007c89b  jmp     loc_14007C7F6
0x14007c8a0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14007c8a4  mov     [r9], r15
0x14007c8a7  mov     rdx, rcx
0x14007c8aa  inc     rdx
0x14007c8ad  cmp     [rbx+rdx*2], r15w
0x14007c8b2  jnz     short loc_14007C8AA
0x14007c8b4  lea     rsi, [rdx+1]
0x14007c8b8  test    r14d, r14d
0x14007c8bb  jz      short loc_14007C8D0
0x14007c8bd  lea     rdx, ds:2[rdx*2]; cbSize
0x14007c8c5  mov     rcx, r8; pParent
0x14007c8c8  call    cs:__imp_WSDAllocateLinkedMemory
0x14007c8ce  jmp     short loc_14007C8E4
0x14007c8d0  mov     eax, 2
0x14007c8d5  mul     rsi
0x14007c8d8  cmovb   rax, rcx
0x14007c8dc  mov     rcx, rax; Size
0x14007c8df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007c8e4  mov     rbp, rax
0x14007c8e7  test    rax, rax
0x14007c8ea  jnz     short loc_14007C961
0x14007c8ec  mov     ebx, 8007000Eh
0x14007c8f1  lea     r12, aCpr; "CPR"
0x14007c8f8  lea     rsi, aSDeepcopystrin; "s_DeepCopyStringHelper"
0x14007c8ff  mov     [rsp+88h+var_60], ebx; int
0x14007c903  mov     ebp, 80h
0x14007c908  lea     rdi, aTermsrvWmsSrcM; "termsrv\\wms\\src\\middletier\\discover"...
0x14007c90f  lea     r14, aPsztempdest; "pszTempDest"
0x14007c916  mov     r9, r12; unsigned __int16 *
0x14007c919  mov     r8, rsi; unsigned __int16 *
0x14007c91c  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x14007c921  mov     edx, ebp; unsigned int
0x14007c923  mov     rcx, rdi; unsigned __int16 *
0x14007c926  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007c92b  call    cs:__imp_IsDebuggerPresent
0x14007c931  test    eax, eax
0x14007c933  jz      short loc_14007C94B
0x14007c935  mov     [rsp+88h+var_50], ebx
0x14007c939  mov     r9d, ebp
0x14007c93c  mov     [rsp+88h+var_58], r14
0x14007c941  mov     qword ptr [rsp+88h+var_60], r12
0x14007c946  jmp     loc_14007C840
0x14007c94b  mov     dword ptr [rsp+88h+var_58], ebx
0x14007c94f  mov     r8d, ebp
0x14007c952  mov     qword ptr [rsp+88h+var_60], r14
0x14007c957  mov     [rsp+88h+var_68], r12
0x14007c95c  jmp     loc_14007C86F
0x14007c961  mov     r8, rbx; unsigned __int16 *
0x14007c964  mov     rdx, rsi; unsigned __int64
0x14007c967  mov     rcx, rbp; unsigned __int16 *
0x14007c96a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14007c96f  mov     ebx, eax
0x14007c971  test    eax, eax
0x14007c973  jns     loc_14007CA29
0x14007c979  mov     [rsp+88h+var_60], eax; int
0x14007c97d  lea     rsi, aSDeepcopystrin; "s_DeepCopyStringHelper"
0x14007c984  mov     r12d, 84h
0x14007c98a  lea     rdi, aTermsrvWmsSrcM; "termsrv\\wms\\src\\middletier\\discover"...
0x14007c991  lea     r13, aHr; "hr"
0x14007c998  mov     r8, rsi; unsigned __int16 *
0x14007c99b  mov     edx, r12d; unsigned int
0x14007c99e  mov     [rsp+88h+var_68], r13; unsigned __int16 *
0x14007c9a3  mov     rcx, rdi; unsigned __int16 *
0x14007c9a6  lea     r9, aChra; "CHRA"
0x14007c9ad  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007c9b2  call    cs:__imp_IsDebuggerPresent
0x14007c9b8  test    eax, eax
0x14007c9ba  lea     rax, aChra; "CHRA"
0x14007c9c1  jz      short loc_14007C9EF
0x14007c9c3  mov     [rsp+88h+var_50], ebx
0x14007c9c7  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14007c9ce  mov     [rsp+88h+var_58], r13
0x14007c9d3  mov     r9d, r12d
0x14007c9d6  mov     qword ptr [rsp+88h+var_60], rax
0x14007c9db  mov     r8, rdi
0x14007c9de  mov     ecx, 2; unsigned __int8
0x14007c9e3  mov     [rsp+88h+var_68], rsi
0x14007c9e8  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007c9ed  jmp     short loc_14007CA12
0x14007c9ef  mov     dword ptr [rsp+88h+var_58], ebx
0x14007c9f3  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14007c9fa  mov     qword ptr [rsp+88h+var_60], r13
0x14007c9ff  mov     r9, rsi
0x14007ca02  mov     r8d, r12d
0x14007ca05  mov     [rsp+88h+var_68], rax
0x14007ca0a  mov     rdx, rdi
0x14007ca0d  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007ca12  mov     rcx, rbp; Block
0x14007ca15  test    r14d, r14d
0x14007ca18  jz      short loc_14007CA22
0x14007ca1a  call    cs:__imp_WSDFreeLinkedMemory
0x14007ca20  jmp     short loc_14007CA2C
0x14007ca22  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14007ca27  jmp     short loc_14007CA2C
0x14007ca29  mov     [rdi], rbp
0x14007ca2c  mov     eax, ebx
0x14007ca2e  add     rsp, 48h
0x14007ca32  pop     r15
0x14007ca34  pop     r14
0x14007ca36  pop     r13
0x14007ca38  pop     r12
0x14007ca3a  pop     rdi
0x14007ca3b  pop     rsi
0x14007ca3c  pop     rbp
0x14007ca3d  pop     rbx
0x14007ca3e  retn
```
