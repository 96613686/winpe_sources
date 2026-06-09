# VfsCowQueryFileForUserAndPackage

- ea: `0x1400034a0`
- end: `0x1400037a4`
- name: `VfsCowQueryFileForUserAndPackage`
- size: `772`
- prototype: `__int64 __fastcall(__int64, void *, int, void *, unsigned __int16 *, __int16 *, const UNICODE_STRING *SourceString, _QWORD *, _QWORD *, __int64, _DWORD *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004484`

## callees

- `0x1400031bc`
- `0x1400034a0`
- `0x140007bac`
- `0x140008c04`
- `0x140009298`
- `0x140009368`
- `0x140012acc`
- `0x14001322c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003777`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014775`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003777`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014775`
- `FLTMGR!FltObjectDereference` at `0x14000375c`
- `FLTMGR!FltObjectDereference` at `0x14001475b`
- `FLTMGR!FltObjectDereference` at `0x14000375c`
- `FLTMGR!FltObjectDereference` at `0x14001475b`

## string_xrefs

- `0x1400036f9`: `VfsCowCheckExcludedExtension() - FileNameExtension: - %wZ\n desiredAccess:     - 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCowQueryFileForUserAndPackage(
        __int64 a1,
        void *a2,
        int a3,
        void *a4,
        unsigned __int16 *a5,
        __int16 *a6,
        const UNICODE_STRING *SourceString,
        _QWORD *a8,
        _QWORD *a9,
        __int64 a10,
        _DWORD *a11,
        int *a12)
{
  __int64 v15; // rdx
  __int16 v16; // cx
  __int64 result; // rax
  _QWORD *v18; // rdi
  int MappedTarget; // eax
  int File; // r15d
  PVOID v21; // rbx
  int v22; // ecx
  int v23; // eax
  int v24; // r12d
  __int64 v25; // [rsp+20h] [rbp-A8h]
  PFLT_INSTANCE Instance; // [rsp+28h] [rbp-A0h]
  PVOID FltObject; // [rsp+58h] [rbp-70h] BYREF
  __int64 v28; // [rsp+60h] [rbp-68h]
  _DWORD v29[2]; // [rsp+70h] [rbp-58h] BYREF
  __int64 v30; // [rsp+78h] [rbp-50h]
  __int128 v31; // [rsp+80h] [rbp-48h] BYREF
  PVOID P[2]; // [rsp+90h] [rbp-38h] BYREF
  int v34; // [rsp+E8h] [rbp+20h]

  v34 = (int)a4;
  FltObject = 0;
  *(_OWORD *)P = 0;
  v31 = 0;
  *a8 = 0;
  *a9 = 0;
  *a11 = 0;
  *(_QWORD *)(a10 + 8) = 0;
  *(_DWORD *)a10 = 0;
  v15 = *a5;
  v29[1] = 0;
  v16 = *a6;
  if ( (unsigned __int16)v15 < (unsigned __int16)*a6 )
  {
    v30 = *((_QWORD *)a6 + 1) + v15;
    LOWORD(v29[0]) = v16 - v15;
    HIWORD(v29[0]) = v16 - v15;
  }
  else
  {
    v30 = 0;
    v29[0] = 0;
  }
  result = VfsLookupMappingForUserAndPackage(a2, (__int64)&v31);
  v18 = (_QWORD *)result;
  v28 = result;
  if ( result )
  {
    *a12 |= 1u;
    if ( !(_WORD)v31 || (_WORD)v31 == 2 && **((_WORD **)&v31 + 1) == 92 )
      *a12 |= 2u;
    *a11 = (unsigned __int16)GetNumberComponents(v29) - *(unsigned __int16 *)(*(_QWORD *)(result + 40) + 16LL);
    MappedTarget = VfsGetMappedTarget(a4, (__int64)P, (__int64)&FltObject);
    File = MappedTarget;
    if ( MappedTarget >= 0 )
    {
      v21 = FltObject;
      File = VfsCowQueryFile(v34, 0, (int)a6, a3, (__int64)a2, (PFLT_INSTANCE)FltObject, 0, (__int64)P, (__int64)a12);
      if ( File >= 0 )
      {
        if ( SourceString )
        {
          if ( SourceString->Length )
          {
            v22 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 35LL);
            *a12 &= ~4u;
            v23 = *a12;
            if ( (*a12 & 0x20) == 0
              && (v23 & 0x18) != 0
              && (v23 & 0x2100) == 0
              && ((v23 & 0xC0) != 0 || v22 != 1 && v22 != 4) )
            {
              v24 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) + 16LL);
              if ( (v24 & 0x20) != 0 || (unsigned __int8)VfsIsExcludedExtension(SourceString) )
              {
                LODWORD(v25) = v24;
                LogWrite(
                  3,
                  0,
                  L"VfsCowCheckExcludedExtension() - FileNameExtension: - %wZ\n desiredAccess:     - 0x%08X",
                  SourceString,
                  v25);
                *a12 |= 4u;
              }
            }
          }
        }
        *a8 = v18;
        *a9 = v21;
        *(_OWORD *)a10 = *(_OWORD *)P;
        v18 = 0;
        v28 = 0;
        v21 = 0;
        FltObject = 0;
      }
    }
    else
    {
      LODWORD(Instance) = MappedTarget;
      LogWrite(
        1,
        0,
        L"VfsCowQueryFileForUserAndPackage() - Failed to map filename: %wZ\n for mapping: %wZ\n Status: 0x%08X",
        &v31,
        v18[5],
        Instance);
      v21 = FltObject;
    }
    if ( v18 )
      VfsReleaseMappingEntry(v18);
    if ( v21 )
    {
      FltObjectDereference(v21);
      if ( P[1] )
        ExFreePoolWithTag(P[1], 0);
    }
    return (unsigned int)File;
  }
  return result;
}

```

## disassembly

```asm
0x1400034a0  mov     rax, rsp
0x1400034a3  mov     [rax+10h], rbx
0x1400034a7  mov     [rax+18h], rsi
0x1400034ab  mov     [rax+20h], r9
0x1400034af  mov     [rax+8], rcx
0x1400034b3  push    rdi
0x1400034b4  push    r12
0x1400034b6  push    r13
0x1400034b8  push    r14
0x1400034ba  push    r15
0x1400034bc  sub     rsp, 0A0h
0x1400034c3  mov     r15, r9
0x1400034c6  mov     r12, r8
0x1400034c9  mov     r13, rdx
0x1400034cc  xor     esi, esi
0x1400034ce  mov     [rax-70h], rsi
0x1400034d2  xorps   xmm0, xmm0
0x1400034d5  movups  xmmword ptr [rax-38h], xmm0
0x1400034d9  xorps   xmm1, xmm1
0x1400034dc  movups  xmmword ptr [rax-48h], xmm1
0x1400034e0  mov     rax, [rsp+0C8h+arg_38]
0x1400034e8  mov     [rax], rsi
0x1400034eb  mov     rax, [rsp+0C8h+arg_40]
0x1400034f3  mov     [rax], rsi
0x1400034f6  mov     rbx, [rsp+0C8h+arg_50]
0x1400034fe  mov     [rbx], esi
0x140003500  mov     rcx, [rsp+0C8h+arg_48]
0x140003508  mov     [rcx+8], rsi
0x14000350c  mov     [rcx], esi
0x14000350e  mov     r8, [rsp+0C8h+arg_20]
0x140003516  movzx   edx, word ptr [r8]
0x14000351a  mov     dword ptr [rsp+0C8h+var_58+4], esi
0x14000351e  mov     r14, [rsp+0C8h+arg_28]
0x140003526  movzx   ecx, word ptr [r14]
0x14000352a  cmp     dx, cx
0x14000352d  jb      short loc_14000353A
0x14000352f  mov     qword ptr [rsp+0C8h+var_58+8], rsi
0x140003534  mov     dword ptr [rsp+0C8h+var_58], esi
0x140003538  jmp     short loc_140003553
0x14000353a  mov     rax, rdx
0x14000353d  add     rax, [r14+8]
0x140003541  mov     qword ptr [rsp+0C8h+var_58+8], rax
0x140003546  sub     cx, dx
0x140003549  mov     word ptr [rsp+0C8h+var_58], cx
0x14000354e  mov     word ptr [rsp+0C8h+var_58+2], cx
0x140003553  movaps  xmm0, [rsp+0C8h+var_58]
0x140003558  movdqa  [rsp+0C8h+var_58], xmm0
0x14000355e  lea     rax, [rsp+0C8h+var_48]
0x140003566  mov     [rsp+0C8h+var_A8], rax; __int64
0x14000356b  lea     r9, [rsp+0C8h+var_58]
0x140003570  mov     rdx, r12
0x140003573  mov     rcx, r13; Buffer
0x140003576  call    VfsLookupMappingForUserAndPackage
0x14000357b  mov     rdi, rax
0x14000357e  mov     [rsp+0C8h+var_68], rax
0x140003583  test    rax, rax
0x140003586  jz      loc_140003786
0x14000358c  mov     rsi, [rsp+0C8h+arg_58]
0x140003594  or      dword ptr [rsi], 1
0x140003597  movzx   eax, word ptr [rsp+0C8h+var_48]
0x14000359f  mov     ecx, 2
0x1400035a4  test    ax, ax
0x1400035a7  jz      short loc_1400035BC
0x1400035a9  cmp     ax, cx
0x1400035ac  jnz     short loc_1400035BE
0x1400035ae  mov     rax, [rsp+0C8h+var_40]
0x1400035b6  cmp     word ptr [rax], 5Ch ; '\'
0x1400035ba  jnz     short loc_1400035BE
0x1400035bc  or      [rsi], ecx
0x1400035be  lea     rcx, [rsp+0C8h+var_58]
0x1400035c3  call    GetNumberComponents
0x1400035c8  movzx   edx, ax
0x1400035cb  mov     rax, [rdi+28h]
0x1400035cf  movzx   ecx, word ptr [rax+10h]
0x1400035d3  sub     edx, ecx
0x1400035d5  mov     [rbx], edx
0x1400035d7  lea     rax, [rsp+0C8h+FltObject]
0x1400035dc  mov     [rsp+0C8h+Instance], rax; __int64
0x1400035e1  lea     rax, [rsp+0C8h+P]
0x1400035e9  mov     [rsp+0C8h+var_A8], rax; __int64
0x1400035ee  mov     r9, rdi
0x1400035f1  mov     r8b, 1
0x1400035f4  lea     rdx, [rsp+0C8h+var_48]
0x1400035fc  mov     rcx, r15; FltObject
0x1400035ff  call    VfsGetMappedTarget
0x140003604  mov     r15d, eax
0x140003607  mov     [rsp+0C8h+var_78], eax
0x14000360b  xor     ecx, ecx
0x14000360d  test    eax, eax
0x14000360f  jns     short loc_140003641
0x140003611  mov     dword ptr [rsp+0C8h+Instance], eax
0x140003615  mov     rdx, [rdi+28h]
0x140003619  mov     [rsp+0C8h+var_A8], rdx
0x14000361e  lea     r9, [rsp+0C8h+var_48]
0x140003626  lea     r8, aVfscowqueryfil; "VfsCowQueryFileForUserAndPackage() - Fa"...
0x14000362d  xor     edx, edx
0x14000362f  lea     ecx, [rdx+1]
0x140003632  call    LogWrite
0x140003637  mov     rbx, [rsp+0C8h+FltObject]
0x14000363c  jmp     loc_140003747
0x140003641  mov     [rsp+0C8h+var_88], rsi; __int64
0x140003646  lea     rax, [rsp+0C8h+P]
0x14000364e  mov     [rsp+0C8h+var_90], rax; __int64
0x140003653  mov     [rsp+0C8h+var_98], rcx; __int64
0x140003658  mov     rbx, [rsp+0C8h+FltObject]
0x14000365d  mov     [rsp+0C8h+Instance], rbx; Instance
0x140003662  mov     [rsp+0C8h+var_A8], r13; __int64
0x140003667  mov     r9, r12; int
0x14000366a  mov     r8, r14; int
0x14000366d  xor     edx, edx; int
0x14000366f  mov     rcx, qword ptr [rsp+0C8h+arg_18]; int
0x140003677  call    VfsCowQueryFile
0x14000367c  mov     r15d, eax
0x14000367f  mov     [rsp+0C8h+var_78], eax
0x140003683  xor     r13d, r13d
0x140003686  test    eax, eax
0x140003688  js      loc_140003747
0x14000368e  mov     r14, [rsp+0C8h+SourceString]
0x140003696  test    r14, r14
0x140003699  jz      short loc_14000370D
0x14000369b  cmp     [r14], r13w
0x14000369f  jz      short loc_14000370D
0x1400036a1  mov     rdx, [rsp+0C8h+arg_0]
0x1400036a9  mov     rax, [rdx+10h]
0x1400036ad  movzx   ecx, byte ptr [rax+23h]
0x1400036b1  and     dword ptr [rsi], 0FFFFFFFBh
0x1400036b4  mov     eax, [rsi]
0x1400036b6  test    al, 20h
0x1400036b8  jnz     short loc_14000370D
0x1400036ba  test    al, 18h
0x1400036bc  jz      short loc_14000370D
0x1400036be  test    eax, 2100h
0x1400036c3  jnz     short loc_14000370D
0x1400036c5  test    al, 0C0h
0x1400036c7  jnz     short loc_1400036D3
0x1400036c9  cmp     ecx, 1
0x1400036cc  jz      short loc_14000370D
0x1400036ce  cmp     ecx, 4
0x1400036d1  jz      short loc_14000370D
0x1400036d3  mov     rax, [rdx+10h]
0x1400036d7  mov     rcx, [rax+18h]
0x1400036db  mov     r12d, [rcx+10h]
0x1400036df  test    r12b, 20h
0x1400036e3  jnz     short loc_1400036F1
0x1400036e5  mov     rcx, r14; SourceString
0x1400036e8  call    VfsIsExcludedExtension
0x1400036ed  test    al, al
0x1400036ef  jz      short loc_14000370D
0x1400036f1  mov     dword ptr [rsp+0C8h+var_A8], r12d
0x1400036f6  mov     r9, r14
0x1400036f9  lea     r8, aVfscowcheckexc; "VfsCowCheckExcludedExtension() - FileNa"...
0x140003700  xor     edx, edx
0x140003702  lea     ecx, [rdx+3]
0x140003705  call    LogWrite
0x14000370a  or      dword ptr [rsi], 4
0x14000370d  mov     rax, [rsp+0C8h+arg_38]
0x140003715  mov     [rax], rdi
0x140003718  mov     rax, [rsp+0C8h+arg_40]
0x140003720  mov     [rax], rbx
0x140003723  movups  xmm0, xmmword ptr [rsp+0C8h+P]
0x14000372b  mov     rax, [rsp+0C8h+arg_48]
0x140003733  movdqu  xmmword ptr [rax], xmm0
0x140003737  mov     rdi, r13
0x14000373a  mov     [rsp+0C8h+var_68], r13
0x14000373f  mov     rbx, r13
0x140003742  mov     [rsp+0C8h+FltObject], rbx
0x140003747  test    rdi, rdi
0x14000374a  jz      short loc_140003754
0x14000374c  mov     rcx, rdi; P
0x14000374f  call    VfsReleaseMappingEntry
0x140003754  test    rbx, rbx
0x140003757  jz      short loc_140003783
0x140003759  mov     rcx, rbx; FltObject
0x14000375c  call    cs:__imp_FltObjectDereference
0x140003763  nop     dword ptr [rax+rax+00h]
0x140003768  mov     rcx, [rsp+0C8h+P+8]; P
0x140003770  test    rcx, rcx
0x140003773  jz      short loc_140003783
0x140003775  xor     edx, edx; Tag
0x140003777  call    cs:__imp_ExFreePoolWithTag
0x14000377e  nop     dword ptr [rax+rax+00h]
0x140003783  mov     eax, r15d
0x140003786  lea     r11, [rsp+0C8h+var_28]
0x14000378e  mov     rbx, [r11+38h]
0x140003792  mov     rsi, [r11+40h]
0x140003796  mov     rsp, r11
0x140003799  pop     r15
0x14000379b  pop     r14
0x14000379d  pop     r13
0x14000379f  pop     r12
0x1400037a1  pop     rdi
0x1400037a2  retn
0x14001473a  push    rbp
0x14001473c  sub     rsp, 50h
0x140014740  mov     rbp, rdx
0x140014743  mov     rcx, [rbp+60h]; P
0x140014747  test    rcx, rcx
0x14001474a  jz      short loc_140014752
0x14001474c  call    VfsReleaseMappingEntry
0x140014751  nop
0x140014752  mov     rcx, [rbp+58h]; FltObject
0x140014756  test    rcx, rcx
0x140014759  jz      short loc_140014782
0x14001475b  call    cs:__imp_FltObjectDereference
0x140014762  nop     dword ptr [rax+rax+00h]
0x140014767  mov     rcx, [rbp+98h]; P
0x14001476e  test    rcx, rcx
0x140014771  jz      short loc_140014782
0x140014773  xor     edx, edx; Tag
0x140014775  call    cs:__imp_ExFreePoolWithTag
0x14001477c  nop     dword ptr [rax+rax+00h]
0x140014781  nop
0x140014782  add     rsp, 50h
0x140014786  pop     rbp
0x140014787  retn
```
