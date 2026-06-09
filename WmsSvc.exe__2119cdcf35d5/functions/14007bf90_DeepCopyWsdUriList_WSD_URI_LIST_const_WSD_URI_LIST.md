# DeepCopyWsdUriList(_WSD_URI_LIST const *,_WSD_URI_LIST * *)

- ea: `0x14007bf90`
- end: `0x14007c225`
- name: `?DeepCopyWsdUriList@@YAJPEBU_WSD_URI_LIST@@PEAPEAU1@@Z`
- size: `661`
- prototype: `__int64 __fastcall(const struct _WSD_URI_LIST *, struct _WSD_URI_LIST **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140079428`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007bf90`
- `0x14007c7c0`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14007bff1`
- `KERNEL32!IsDebuggerPresent` at `0x14007c0d1`
- `KERNEL32!IsDebuggerPresent` at `0x14007c1ae`
- `KERNEL32!IsDebuggerPresent` at `0x14007bff1`
- `KERNEL32!IsDebuggerPresent` at `0x14007c0d1`
- `KERNEL32!IsDebuggerPresent` at `0x14007c1ae`
- `wsdapi!WSDAllocateLinkedMemory` at `0x14007c07f`
- `wsdapi!WSDAllocateLinkedMemory` at `0x14007c0f5`
- `wsdapi!WSDAllocateLinkedMemory` at `0x14007c07f`
- `wsdapi!WSDAllocateLinkedMemory` at `0x14007c0f5`
- `wsdapi!WSDFreeLinkedMemory` at `0x14007c20c`
- `wsdapi!WSDFreeLinkedMemory` at `0x14007c20c`

## string_xrefs

- `0x14007bfd9`: `termsrv\wms\src\middletier\discovery\common\common.cpp`
- `0x14007c0ab`: `termsrv\wms\src\middletier\discovery\common\common.cpp`
- `0x14007c187`: `termsrv\wms\src\middletier\discovery\common\common.cpp`
- `0x14007bfcd`: `DeepCopyWsdUriList`
- `0x14007c09a`: `DeepCopyWsdUriList`
- `0x14007c175`: `DeepCopyWsdUriList`
- `0x14007c18e`: `pTempList->Next`

## pseudocode

```c
__int64 __fastcall DeepCopyWsdUriList(const struct _WSD_URI_LIST *a1, struct _WSD_URI_LIST **a2)
{
  const struct _WSD_URI_LIST *v3; // r14
  unsigned int v4; // edi
  const unsigned __int16 *v5; // r15
  unsigned int v6; // r14d
  struct _WSD_URI_LIST *v7; // rbx
  struct _WSD_URI_LIST *v8; // rsi
  struct _WSD_URI_LIST *v9; // rax

  v3 = a1;
  if ( !a1 )
  {
    v4 = -2147024809;
    v5 = L"pSrcList";
    v6 = 209;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = L"ppDestList";
    v6 = 210;
LABEL_3:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
      v6,
      L"DeepCopyWsdUriList",
      L"CBRAEx",
      v5,
      v4);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
        v6,
        L"DeepCopyWsdUriList",
        L"CBRAEx",
        v5,
        v4);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
        v6,
        L"DeepCopyWsdUriList",
        L"CBRAEx",
        v5,
        v4);
    return v4;
  }
  v7 = 0;
  v8 = 0;
  while ( v7 )
  {
    v9 = (struct _WSD_URI_LIST *)WSDAllocateLinkedMemory(v8, 0x10u);
    v8->Next = v9;
    if ( !v9 )
    {
      v4 = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
        0xE3u,
        L"DeepCopyWsdUriList",
        L"CPR",
        L"pTempList->Next",
        -2147024882);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
          227,
          L"DeepCopyWsdUriList",
          L"CPR",
          L"pTempList->Next",
          -2147024882);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
          227,
          L"DeepCopyWsdUriList",
          L"CPR",
          L"pTempList->Next",
          -2147024882);
LABEL_25:
      WSDFreeLinkedMemory(v7);
      return v4;
    }
LABEL_16:
    v9->Next = 0;
    v9->Element = 0;
    v8 = v9;
    v4 = s_DeepCopyStringHelper(1, v3->Element, v9, &v9->Element);
    if ( (v4 & 0x80000000) != 0 )
    {
      if ( !v7 )
        return v4;
      goto LABEL_25;
    }
    v3 = v3->Next;
    if ( !v3 )
    {
      *a2 = v7;
      return v4;
    }
  }
  v9 = (struct _WSD_URI_LIST *)WSDAllocateLinkedMemory(0, 0x10u);
  v7 = v9;
  if ( v9 )
    goto LABEL_16;
  v4 = -2147024882;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
    0xDAu,
    L"DeepCopyWsdUriList",
    L"CPR",
    L"pDuplicatedList",
    -2147024882);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
      218,
      L"DeepCopyWsdUriList",
      L"CPR",
      L"pDuplicatedList",
      -2147024882);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
      218,
      L"DeepCopyWsdUriList",
      L"CPR",
      L"pDuplicatedList",
      -2147024882);
  return v4;
}

```

## disassembly

```asm
0x14007bf90  push    rbx
0x14007bf92  push    rbp
0x14007bf93  push    rsi
0x14007bf94  push    rdi
0x14007bf95  push    r12
0x14007bf97  push    r13
0x14007bf99  push    r14
0x14007bf9b  push    r15
0x14007bf9d  sub     rsp, 48h
0x14007bfa1  mov     r15, rdx
0x14007bfa4  mov     r14, rcx
0x14007bfa7  test    rcx, rcx
0x14007bfaa  jnz     loc_14007C052
0x14007bfb0  mov     edi, 80070057h
0x14007bfb5  lea     r15, aPsrclist; "pSrcList"
0x14007bfbc  mov     r14d, 0D1h
0x14007bfc2  lea     rbx, aCbraex; "CBRAEx"
0x14007bfc9  mov     [rsp+88h+var_60], edi; int
0x14007bfcd  lea     rbp, aDeepcopywsduri; "DeepCopyWsdUriList"
0x14007bfd4  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x14007bfd9  lea     rsi, aTermsrvWmsSrcM; "termsrv\\wms\\src\\middletier\\discover"...
0x14007bfe0  mov     r9, rbx; unsigned __int16 *
0x14007bfe3  mov     r8, rbp; unsigned __int16 *
0x14007bfe6  mov     rcx, rsi; unsigned __int16 *
0x14007bfe9  mov     edx, r14d; unsigned int
0x14007bfec  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007bff1  call    cs:__imp_IsDebuggerPresent
0x14007bff7  test    eax, eax
0x14007bff9  jz      short loc_14007C02A
0x14007bffb  mov     [rsp+88h+var_50], edi
0x14007bfff  mov     r9d, r14d
0x14007c002  mov     [rsp+88h+var_58], r15
0x14007c007  mov     qword ptr [rsp+88h+var_60], rbx
0x14007c00c  mov     r8, rsi
0x14007c00f  mov     [rsp+88h+var_68], rbp
0x14007c014  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14007c01b  mov     ecx, 2; unsigned __int8
0x14007c020  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007c025  jmp     loc_14007C212
0x14007c02a  mov     dword ptr [rsp+88h+var_58], edi
0x14007c02e  mov     r8d, r14d
0x14007c031  mov     qword ptr [rsp+88h+var_60], r15
0x14007c036  mov     [rsp+88h+var_68], rbx
0x14007c03b  mov     r9, rbp
0x14007c03e  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14007c045  mov     rdx, rsi
0x14007c048  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007c04d  jmp     loc_14007C212
0x14007c052  test    r15, r15
0x14007c055  jnz     short loc_14007C06E
0x14007c057  mov     edi, 80004003h
0x14007c05c  lea     r15, aPpdestlist; "ppDestList"
0x14007c063  mov     r14d, 0D2h
0x14007c069  jmp     loc_14007BFC2
0x14007c06e  xor     ebx, ebx
0x14007c070  xor     esi, esi
0x14007c072  lea     ebp, [rbx+10h]
0x14007c075  mov     rdx, rbp; cbSize
0x14007c078  test    rbx, rbx
0x14007c07b  jnz     short loc_14007C0F2
0x14007c07d  xor     ecx, ecx; pParent
0x14007c07f  call    cs:__imp_WSDAllocateLinkedMemory
0x14007c085  mov     rbx, rax
0x14007c088  test    rax, rax
0x14007c08b  jnz     short loc_14007C103
0x14007c08d  mov     r14d, 8007000Eh
0x14007c093  lea     r15, aCpr; "CPR"
0x14007c09a  lea     rbp, aDeepcopywsduri; "DeepCopyWsdUriList"
0x14007c0a1  mov     [rsp+88h+var_60], r14d; int
0x14007c0a6  mov     ebx, 0DAh
0x14007c0ab  lea     rsi, aTermsrvWmsSrcM; "termsrv\\wms\\src\\middletier\\discover"...
0x14007c0b2  lea     r12, aPduplicatedlis; "pDuplicatedList"
0x14007c0b9  mov     r9, r15; unsigned __int16 *
0x14007c0bc  mov     r8, rbp; unsigned __int16 *
0x14007c0bf  mov     [rsp+88h+var_68], r12; unsigned __int16 *
0x14007c0c4  mov     edx, ebx; unsigned int
0x14007c0c6  mov     rcx, rsi; unsigned __int16 *
0x14007c0c9  mov     edi, r14d
0x14007c0cc  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007c0d1  call    cs:__imp_IsDebuggerPresent
0x14007c0d7  test    eax, eax
0x14007c0d9  jz      short loc_14007C143
0x14007c0db  mov     [rsp+88h+var_50], r14d
0x14007c0e0  mov     r9d, ebx
0x14007c0e3  mov     [rsp+88h+var_58], r12
0x14007c0e8  mov     qword ptr [rsp+88h+var_60], r15
0x14007c0ed  jmp     loc_14007C00C
0x14007c0f2  mov     rcx, rsi; pParent
0x14007c0f5  call    cs:__imp_WSDAllocateLinkedMemory
0x14007c0fb  mov     [rsi], rax
0x14007c0fe  test    rax, rax
0x14007c101  jz      short loc_14007C168
0x14007c103  lea     r9, [rax+8]
0x14007c107  mov     qword ptr [rax], 0
0x14007c10e  mov     qword ptr [r9], 0
0x14007c115  mov     r8, rax
0x14007c118  mov     rdx, [r14+8]
0x14007c11c  mov     ecx, 1
0x14007c121  mov     rsi, rax
0x14007c124  call    s_DeepCopyStringHelper
0x14007c129  mov     edi, eax
0x14007c12b  test    eax, eax
0x14007c12d  js      short loc_14007C15A
0x14007c12f  mov     r14, [r14]
0x14007c132  test    r14, r14
0x14007c135  jnz     loc_14007C075
0x14007c13b  mov     [r15], rbx
0x14007c13e  jmp     loc_14007C212
0x14007c143  mov     dword ptr [rsp+88h+var_58], r14d
0x14007c148  mov     r8d, ebx
0x14007c14b  mov     qword ptr [rsp+88h+var_60], r12
0x14007c150  mov     [rsp+88h+var_68], r15
0x14007c155  jmp     loc_14007C03B
0x14007c15a  test    rbx, rbx
0x14007c15d  jz      loc_14007C212
0x14007c163  jmp     loc_14007C209
0x14007c168  mov     r14d, 8007000Eh
0x14007c16e  lea     r15, aCpr; "CPR"
0x14007c175  lea     rbp, aDeepcopywsduri; "DeepCopyWsdUriList"
0x14007c17c  mov     [rsp+88h+var_60], r14d; int
0x14007c181  mov     r12d, 0E3h
0x14007c187  lea     rsi, aTermsrvWmsSrcM; "termsrv\\wms\\src\\middletier\\discover"...
0x14007c18e  lea     r13, aPtemplistNext; "pTempList->Next"
0x14007c195  mov     r9, r15; unsigned __int16 *
0x14007c198  mov     r8, rbp; unsigned __int16 *
0x14007c19b  mov     [rsp+88h+var_68], r13; unsigned __int16 *
0x14007c1a0  mov     edx, r12d; unsigned int
0x14007c1a3  mov     rcx, rsi; unsigned __int16 *
0x14007c1a6  mov     edi, r14d
0x14007c1a9  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007c1ae  call    cs:__imp_IsDebuggerPresent
0x14007c1b4  test    eax, eax
0x14007c1b6  jz      short loc_14007C1E5
0x14007c1b8  mov     [rsp+88h+var_50], r14d
0x14007c1bd  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14007c1c4  mov     [rsp+88h+var_58], r13
0x14007c1c9  mov     r9d, r12d
0x14007c1cc  mov     qword ptr [rsp+88h+var_60], r15
0x14007c1d1  mov     r8, rsi
0x14007c1d4  mov     ecx, 2; unsigned __int8
0x14007c1d9  mov     [rsp+88h+var_68], rbp
0x14007c1de  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007c1e3  jmp     short loc_14007C209
0x14007c1e5  mov     dword ptr [rsp+88h+var_58], r14d
0x14007c1ea  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14007c1f1  mov     qword ptr [rsp+88h+var_60], r13
0x14007c1f6  mov     r9, rbp
0x14007c1f9  mov     r8d, r12d
0x14007c1fc  mov     [rsp+88h+var_68], r15
0x14007c201  mov     rdx, rsi
0x14007c204  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007c209  mov     rcx, rbx; pVoid
0x14007c20c  call    cs:__imp_WSDFreeLinkedMemory
0x14007c212  mov     eax, edi
0x14007c214  add     rsp, 48h
0x14007c218  pop     r15
0x14007c21a  pop     r14
0x14007c21c  pop     r13
0x14007c21e  pop     r12
0x14007c220  pop     rdi
0x14007c221  pop     rsi
0x14007c222  pop     rbp
0x14007c223  pop     rbx
0x14007c224  retn
```
