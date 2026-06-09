# XPerf::Internal::CvDbgInfoFromImage2(ushort const *,void *,ulong,ulong,bool,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,ulong *,ulong *,ushort *,ulong,bool &,bool,EMBEDDED_PDB_INFORMATION &,bool &,XPerfCore::IErrorMessage *)

- ea: `0x180033ad8`
- end: `0x180033fa9`
- name: `?CvDbgInfoFromImage2@Internal@XPerf@@YAJPEBGPEAXKK_NPEAKPEAT_CVDD@@3PEAUCODEVIEW_INFORMATION_1@@33PEAGKAEA_N2AEAUEMBEDDED_PDB_INFORMATION@@7PEAVIErrorMessage@XPerfCore@@@Z`
- size: `1233`
- prototype: `__int64 __fastcall(XPerf::Internal *this, unsigned __int16 *, void *, __int64, unsigned int, unsigned int *, union _CVDD *, union _CVDD *, struct CODEVIEW_INFORMATION_1 *, struct CODEVIEW_INFORMATION_1 *, unsigned int *, unsigned __int16 *, unsigned __int16 *, _BYTE *, BOOLEAN MappedAsImage, struct EMBEDDED_PDB_INFORMATION *, struct EMBEDDED_PDB_INFORMATION *, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180020204`
- `0x1800347ec`

## callees

- `0x1800063e0`
- `0x1800064a4`
- `0x180015734`
- `0x180033ad8`
- `0x180033fb0`
- `0x1800344a0`
- `0x18003459c`
- `0x180034780`
- `0x180034990`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180033ec3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180033ec3`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180033caa`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180033caa`

## pseudocode

```c
__int64 __fastcall XPerf::Internal::CvDbgInfoFromImage2(
        XPerf::Internal *this,
        unsigned __int16 *a2,
        void *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6,
        union _CVDD *a7,
        union _CVDD *a8,
        struct CODEVIEW_INFORMATION_1 *a9,
        struct CODEVIEW_INFORMATION_1 *a10,
        unsigned int *a11,
        unsigned __int16 *a12,
        unsigned __int16 *a13,
        _BYTE *a14,
        BOOLEAN MappedAsImage,
        struct EMBEDDED_PDB_INFORMATION *a16,
        struct EMBEDDED_PDB_INFORMATION *a17,
        bool *a18)
{
  unsigned int *v18; // r12
  union _CVDD *v19; // rbx
  struct EMBEDDED_PDB_INFORMATION *v20; // r13
  unsigned __int16 *v21; // r14
  __int64 v22; // rax
  int v23; // r9d
  void *v24; // r10
  struct _IMAGE_NT_HEADERS64 *v25; // rsi
  __int64 result; // rax
  int v27; // eax
  DWORD TimeDateStamp; // edx
  unsigned int SizeOfImage; // ecx
  BOOLEAN v30; // r15
  _BYTE *v31; // rax
  int v32; // eax
  union _CVDD *v33; // rsi
  unsigned int v34; // ecx
  int v35; // r9d
  unsigned int i; // edx
  __int64 v37; // r8
  wchar_t *v38; // rax
  __int64 v39; // rax
  bool v40; // [rsp+20h] [rbp-B8h]
  ULONG Size; // [rsp+70h] [rbp-68h] BYREF
  int v42; // [rsp+74h] [rbp-64h]
  int v43; // [rsp+78h] [rbp-60h]
  unsigned int v44; // [rsp+7Ch] [rbp-5Ch]
  int v45; // [rsp+80h] [rbp-58h]
  DWORD v46; // [rsp+84h] [rbp-54h]
  unsigned int v47; // [rsp+88h] [rbp-50h]
  int v48; // [rsp+8Ch] [rbp-4Ch]
  DWORD v49; // [rsp+90h] [rbp-48h]
  unsigned int v50; // [rsp+94h] [rbp-44h]
  signed __int64 v51; // [rsp+98h] [rbp-40h]
  unsigned int v54; // [rsp+F0h] [rbp+18h]

  v54 = (unsigned int)a3;
  v18 = a6;
  v19 = a7;
  v20 = a16;
  *(_OWORD *)a16 = 0;
  *((_QWORD *)v20 + 2) = 0;
  *(_BYTE *)a17 = 0;
  v21 = a12;
  if ( a12 )
    *a12 = 0;
  v22 = XPerfCore::_SafeImageNtHeader(a2, (unsigned int)a3);
  v25 = (struct _IMAGE_NT_HEADERS64 *)v22;
  if ( !v22 )
  {
    if ( a18 )
      (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(a18, L"Invalid executable format.");
    return ATL::AtlHresultFromWin32(193);
  }
  v27 = *(_DWORD *)(v22 + 88);
  v45 = v27;
  v48 = v27;
  TimeDateStamp = v25->FileHeader.TimeDateStamp;
  v46 = TimeDateStamp;
  v49 = TimeDateStamp;
  SizeOfImage = v25->OptionalHeader.SizeOfImage;
  v47 = SizeOfImage;
  v50 = SizeOfImage;
  if ( v23 && v27 != v23 )
  {
    if ( a18 )
      (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(a18, L"Invalid image header checksum.");
    return ATL::AtlHresultFromWin32(13);
  }
  if ( a10 )
    *(_DWORD *)a10 = TimeDateStamp;
  if ( a11 )
    *a11 = SizeOfImage;
  if ( v25->OptionalHeader.Magic == 267 )
  {
    *a14 = 0;
  }
  else
  {
    if ( v25->OptionalHeader.Magic != 523 )
      return 2147549183LL;
    *a14 = 1;
  }
  v30 = MappedAsImage;
  if ( (unsigned int)SymCommonNativeResourceOnlyDll(v24) )
    goto LABEL_24;
  v43 = v25->FileHeader.Characteristics & 0x200;
  v42 = SymCommonTlbImpManagedDll(a2, v25, v30);
  Size = 0;
  v31 = RtlImageDirectoryEntryToData(a2, v30, 6u, &Size);
  if ( v31 )
  {
    v51 = v31 - (_BYTE *)a2;
    a5 = -1;
    v33 = a8;
    result = CvInfoFromDbgDir(
               a2,
               v54,
               Size,
               (int)v31 - (int)a2,
               v40,
               &a5,
               v18,
               v19,
               (unsigned int *)a8,
               a9,
               v30,
               v20,
               (bool *)a17);
    if ( (int)result < 0 )
      return result;
    v34 = *v18;
    v35 = v42;
    if ( *v18 > 1 )
    {
      if ( v42 == 1 )
      {
        if ( a18 )
          (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(
            a18,
            L"Multiple CvDbg entries in IL-only image.");
        return ATL::AtlHresultFromWin32(193);
      }
      for ( i = 0; ; ++i )
      {
        v44 = i;
        if ( i >= v34 )
          break;
        v37 = 1576LL * i;
        if ( *(_DWORD *)((char *)v19 + v37) == 1396986706 && a5 != -1 && i != a5 )
        {
          *(_DWORD *)((char *)v19 + v37) = 3;
          v34 = *v18;
        }
      }
    }
    v32 = *(_DWORD *)v19;
    if ( *(_DWORD *)v19 == 1 )
    {
      v32 = 1;
    }
    else if ( v32 || !v43 )
    {
      if ( v35 == 1 )
      {
        *(_DWORD *)v19 = 3;
        v32 = 3;
      }
    }
    else
    {
      *(_DWORD *)v19 = 2;
      v32 = 2;
    }
  }
  else
  {
    if ( !v43 )
    {
LABEL_24:
      *v18 = 1;
      *(_DWORD *)v19 = 0;
      v32 = 0;
      v33 = a8;
      goto LABEL_47;
    }
    *v18 = 1;
    *(_DWORD *)v19 = 2;
    v32 = 2;
    v33 = a8;
  }
LABEL_47:
  if ( !v32 )
  {
    if ( v33 )
      *(_DWORD *)v33 = 4;
LABEL_62:
    if ( !v21 || !(_DWORD)a13 || (unsigned int)SymGetEstimatedOriginalFilename((unsigned __int16 *)this) )
      return 0;
    goto LABEL_66;
  }
  if ( (unsigned int)(v32 - 1) > 1 )
    goto LABEL_62;
  *((_DWORD *)v19 + 1) = v45;
  *((_DWORD *)v19 + 2) = v46;
  *((_DWORD *)v19 + 3) = v47;
  if ( !(unsigned int)SymGetEstimatedOriginalFilename((unsigned __int16 *)this) )
  {
LABEL_66:
    if ( a18 )
      (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(
        a18,
        L"Failed to obtain the original file name.");
    return 2147500037LL;
  }
  if ( !v21 || (result = StringCchCopyW(v21, (unsigned int)a13, (const unsigned __int16 *)v19 + 8), (int)result >= 0) )
  {
    if ( *(_DWORD *)v19 != 2 )
      goto LABEL_56;
    v38 = wcsrchr((const wchar_t *)v19 + 8, 0x2Eu);
    if ( v38 )
      *v38 = 0;
    result = StringCchCatW((unsigned __int16 *)v19 + 8, 0x30Cu, L".dbg");
    if ( (int)result >= 0 )
    {
LABEL_56:
      if ( v33 )
      {
        v39 = -1;
        do
          ++v39;
        while ( *((_WORD *)v19 + v39 + 8) );
        *(_DWORD *)v33 = 2 * v39 + 18;
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180033ad8  mov     [rsp+arg_10], r8d
0x180033add  mov     [rsp+BaseAddress], rdx
0x180033ae2  mov     [rsp+arg_0], rcx
0x180033ae7  push    rbx
0x180033ae8  push    rsi
0x180033ae9  push    rdi
0x180033aea  push    r12
0x180033aec  push    r13
0x180033aee  push    r14
0x180033af0  push    r15
0x180033af2  sub     rsp, 0A0h
0x180033af9  mov     r10, rdx
0x180033afc  mov     r12, [rsp+0D8h+arg_28]
0x180033b04  mov     rbx, [rsp+0D8h+arg_30]
0x180033b0c  xorps   xmm0, xmm0
0x180033b0f  xor     eax, eax
0x180033b11  mov     r13, [rsp+0D8h+arg_78]
0x180033b19  movups  xmmword ptr [r13+0], xmm0
0x180033b1e  mov     [r13+10h], rax
0x180033b22  mov     rax, [rsp+0D8h+arg_80]
0x180033b2a  mov     byte ptr [rax], 0
0x180033b2d  mov     r14, [rsp+0D8h+arg_58]
0x180033b35  test    r14, r14
0x180033b38  jz      short loc_180033B40
0x180033b3a  xor     eax, eax
0x180033b3c  mov     [r14], ax
0x180033b40  mov     edx, r8d
0x180033b43  mov     rcx, r10
0x180033b46  call    XPerfCore___SafeImageNtHeader
0x180033b4b  mov     rsi, rax
0x180033b4e  test    rax, rax
0x180033b51  jnz     short loc_180033B82
0x180033b53  mov     rcx, [rsp+0D8h+arg_88]
0x180033b5b  test    rcx, rcx
0x180033b5e  jz      short loc_180033B73
0x180033b60  mov     rax, [rcx]
0x180033b63  lea     rdx, aInvalidExecuta; "Invalid executable format."
0x180033b6a  mov     rax, [rax+8]
0x180033b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b73  mov     ecx, 0C1h; unsigned int
0x180033b78  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180033b7d  jmp     loc_180033F96
0x180033b82  mov     eax, [rax+58h]
0x180033b85  mov     [rsp+0D8h+var_58], eax
0x180033b8c  mov     [rsp+0D8h+var_4C], eax
0x180033b93  mov     edx, [rsi+8]
0x180033b96  mov     [rsp+0D8h+var_54], edx
0x180033b9d  mov     [rsp+0D8h+var_48], edx
0x180033ba4  mov     ecx, [rsi+50h]
0x180033ba7  mov     [rsp+0D8h+var_50], ecx
0x180033bae  mov     [rsp+0D8h+var_44], ecx
0x180033bb5  test    r9d, r9d
0x180033bb8  jz      short loc_180033BEE
0x180033bba  cmp     eax, r9d
0x180033bbd  jz      short loc_180033BEE
0x180033bbf  mov     rcx, [rsp+0D8h+arg_88]
0x180033bc7  test    rcx, rcx
0x180033bca  jz      short loc_180033BDF
0x180033bcc  mov     rax, [rcx]
0x180033bcf  lea     rdx, aInvalidImageHe; "Invalid image header checksum."
0x180033bd6  mov     rax, [rax+8]
0x180033bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bdf  mov     ecx, 0Dh; unsigned int
0x180033be4  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180033be9  jmp     loc_180033F96
0x180033bee  mov     rax, [rsp+0D8h+arg_48]
0x180033bf6  test    rax, rax
0x180033bf9  jz      short loc_180033BFD
0x180033bfb  mov     [rax], edx
0x180033bfd  mov     rax, [rsp+0D8h+arg_50]
0x180033c05  test    rax, rax
0x180033c08  jz      short loc_180033C0C
0x180033c0a  mov     [rax], ecx
0x180033c0c  mov     eax, 10Bh
0x180033c11  cmp     [rsi+18h], ax
0x180033c15  jz      short loc_180033C3E
0x180033c17  mov     eax, 20Bh
0x180033c1c  cmp     [rsi+18h], ax
0x180033c20  jz      short loc_180033C2C
0x180033c22  mov     eax, 8000FFFFh
0x180033c27  jmp     loc_180033F96
0x180033c2c  mov     edi, 1
0x180033c31  mov     rax, [rsp+0D8h+arg_68]
0x180033c39  mov     [rax], dil
0x180033c3c  jmp     short loc_180033C4E
0x180033c3e  mov     rax, [rsp+0D8h+arg_68]
0x180033c46  mov     byte ptr [rax], 0
0x180033c49  mov     edi, 1
0x180033c4e  mov     r15b, [rsp+0D8h+MappedAsImage]
0x180033c56  mov     dl, r15b
0x180033c59  mov     rcx, r10; BaseAddress
0x180033c5c  call    SymCommonNativeResourceOnlyDll
0x180033c61  test    eax, eax
0x180033c63  jz      short loc_180033C6A
0x180033c65  xor     r13d, r13d
0x180033c68  jmp     short loc_180033CC2
0x180033c6a  movzx   eax, word ptr [rsi+16h]
0x180033c6e  and     eax, 200h
0x180033c73  mov     [rsp+0D8h+var_60], eax
0x180033c77  mov     r8b, r15b; MappedAsImage
0x180033c7a  mov     rdx, rsi; NtHeader
0x180033c7d  mov     rsi, [rsp+0D8h+BaseAddress]
0x180033c85  mov     rcx, rsi; BaseAddress
0x180033c88  call    SymCommonTlbImpManagedDll
0x180033c8d  mov     [rsp+0D8h+var_64], eax
0x180033c91  mov     [rsp+0D8h+Size], 0
0x180033c99  mov     r8d, 6; Directory
0x180033c9f  lea     r9, [rsp+0D8h+Size]; Size
0x180033ca4  mov     dl, r15b; MappedAsImage
0x180033ca7  mov     rcx, rsi; BaseAddress
0x180033caa  call    cs:__imp_RtlImageDirectoryEntryToData
0x180033cb0  mov     r9, rax
0x180033cb3  test    rax, rax
0x180033cb6  jnz     short loc_180033D05
0x180033cb8  xor     r13d, r13d
0x180033cbb  cmp     [rsp+0D8h+var_60], r13d
0x180033cc0  jnz     short loc_180033CE1
0x180033cc2  mov     [r12], edi
0x180033cc6  mov     [rbx], r13d
0x180033cc9  mov     eax, r13d
0x180033ccc  mov     rsi, [rsp+0D8h+arg_38]
0x180033cd4  mov     r15, [rsp+0D8h+BaseAddress]
0x180033cdc  jmp     loc_180033E3E
0x180033ce1  mov     [r12], edi
0x180033ce5  mov     dword ptr [rbx], 2
0x180033ceb  mov     eax, 2
0x180033cf0  mov     rsi, [rsp+0D8h+arg_38]
0x180033cf8  mov     r15, [rsp+0D8h+BaseAddress]
0x180033d00  jmp     loc_180033E3E
0x180033d05  sub     r9, rsi; unsigned int
0x180033d08  mov     [rsp+0D8h+var_40], r9
0x180033d10  mov     [rsp+0D8h+arg_20], 0FFFFFFFFh
0x180033d1b  mov     rax, [rsp+0D8h+arg_80]
0x180033d23  mov     [rsp+0D8h+var_78], rax; bool *
0x180033d28  mov     [rsp+0D8h+var_80], r13; struct EMBEDDED_PDB_INFORMATION *
0x180033d2d  mov     [rsp+0D8h+var_88], r15b; bool
0x180033d32  mov     rax, [rsp+0D8h+arg_40]
0x180033d3a  mov     [rsp+0D8h+var_90], rax; struct CODEVIEW_INFORMATION_1 *
0x180033d3f  mov     rsi, [rsp+0D8h+arg_38]
0x180033d47  mov     [rsp+0D8h+var_98], rsi; unsigned int *
0x180033d4c  mov     [rsp+0D8h+var_A0], rbx; union _CVDD *
0x180033d51  mov     [rsp+0D8h+var_A8], r12; unsigned int *
0x180033d56  lea     rax, [rsp+0D8h+arg_20]
0x180033d5e  mov     [rsp+0D8h+var_B0], rax; unsigned int *
0x180033d63  mov     r8d, [rsp+0D8h+Size]; unsigned int
0x180033d68  mov     edx, [rsp+0D8h+arg_10]; unsigned int
0x180033d6f  mov     r15, [rsp+0D8h+BaseAddress]
0x180033d77  mov     rcx, r15; void *
0x180033d7a  call    ?CvInfoFromDbgDir@@YAJPEAXKKK_NPEAK2PEAT_CVDD@@2PEAUCODEVIEW_INFORMATION_1@@1AEAUEMBEDDED_PDB_INFORMATION@@AEA_N@Z; CvInfoFromDbgDir(void *,ulong,ulong,ulong,bool,ulong *,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,bool,EMBEDDED_PDB_INFORMATION &,bool &)
0x180033d7f  xor     r13d, r13d
0x180033d82  test    eax, eax
0x180033d84  js      loc_180033F96
0x180033d8a  mov     ecx, [r12]
0x180033d8e  mov     r9d, [rsp+0D8h+var_64]
0x180033d93  cmp     ecx, edi
0x180033d95  jbe     short loc_180033E0C
0x180033d97  cmp     r9d, edi
0x180033d9a  jnz     short loc_180033DCB
0x180033d9c  mov     rcx, [rsp+0D8h+arg_88]
0x180033da4  test    rcx, rcx
0x180033da7  jz      short loc_180033DBC
0x180033da9  mov     rax, [rcx]
0x180033dac  lea     rdx, aMultipleCvdbgE; "Multiple CvDbg entries in IL-only image"...
0x180033db3  mov     rax, [rax+8]
0x180033db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033dbc  mov     ecx, 0C1h; unsigned int
0x180033dc1  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180033dc6  jmp     loc_180033F96
0x180033dcb  mov     edx, r13d
0x180033dce  mov     [rsp+0D8h+var_5C], edx
0x180033dd2  cmp     edx, ecx
0x180033dd4  jnb     short loc_180033E0C
0x180033dd6  mov     eax, edx
0x180033dd8  imul    r8, rax, 628h
0x180033ddf  cmp     dword ptr [r8+rbx], 53445352h
0x180033de7  jnz     short loc_180033E08
0x180033de9  cmp     [rsp+0D8h+arg_20], 0FFFFFFFFh
0x180033df1  jz      short loc_180033E08
0x180033df3  cmp     edx, [rsp+0D8h+arg_20]
0x180033dfa  jz      short loc_180033E08
0x180033dfc  mov     dword ptr [r8+rbx], 3
0x180033e04  mov     ecx, [r12]
0x180033e08  add     edx, edi
0x180033e0a  jmp     short loc_180033DCE
0x180033e0c  mov     eax, [rbx]
0x180033e0e  cmp     eax, edi
0x180033e10  jz      short loc_180033E3C
0x180033e12  test    eax, eax
0x180033e14  jnz     short loc_180033E2A
0x180033e16  cmp     [rsp+0D8h+var_60], r13d
0x180033e1b  jz      short loc_180033E2A
0x180033e1d  mov     dword ptr [rbx], 2
0x180033e23  mov     eax, 2
0x180033e28  jmp     short loc_180033E3E
0x180033e2a  cmp     r9d, edi
0x180033e2d  jnz     short loc_180033E3A
0x180033e2f  mov     dword ptr [rbx], 3
0x180033e35  mov     eax, 3
0x180033e3a  jmp     short loc_180033E3E
0x180033e3c  mov     eax, edi
0x180033e3e  test    eax, eax
0x180033e40  jz      loc_180033F0C
0x180033e46  sub     eax, 1
0x180033e49  jz      short loc_180033E54
0x180033e4b  cmp     eax, 1
0x180033e4e  jnz     loc_180033F17
0x180033e54  mov     eax, [rsp+0D8h+var_58]
0x180033e5b  mov     [rbx+4], eax
0x180033e5e  mov     eax, [rsp+0D8h+var_54]
0x180033e65  mov     [rbx+8], eax
0x180033e68  mov     eax, [rsp+0D8h+var_50]
0x180033e6f  mov     [rbx+0Ch], eax
0x180033e72  lea     rdi, [rbx+10h]
0x180033e76  mov     r9, rdi
0x180033e79  mov     r8d, 307h
0x180033e7f  mov     rdx, r15
0x180033e82  mov     rcx, [rsp+0D8h+arg_0]; unsigned __int16 *
0x180033e8a  call    SymGetEstimatedOriginalFilename
0x180033e8f  test    eax, eax
0x180033e91  jz      loc_180033F44
0x180033e97  test    r14, r14
0x180033e9a  jz      short loc_180033EB6
0x180033e9c  mov     edx, dword ptr [rsp+0D8h+arg_60]; unsigned __int64
0x180033ea3  mov     r8, rdi; unsigned __int16 *
0x180033ea6  mov     rcx, r14; unsigned __int16 *
0x180033ea9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033eae  test    eax, eax
0x180033eb0  js      loc_180033F96
0x180033eb6  cmp     dword ptr [rbx], 2
0x180033eb9  jnz     short loc_180033EEE
0x180033ebb  mov     edx, 2Eh ; '.'; Ch
0x180033ec0  mov     rcx, rdi; Str
0x180033ec3  call    cs:__imp_wcsrchr
0x180033ec9  test    rax, rax
0x180033ecc  jz      short loc_180033ED2
0x180033ece  mov     [rax], r13w
0x180033ed2  lea     r8, aDbg; ".dbg"
0x180033ed9  mov     edx, 30Ch; unsigned __int64
0x180033ede  mov     rcx, rdi; unsigned __int16 *
0x180033ee1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180033ee6  test    eax, eax
0x180033ee8  js      loc_180033F96
0x180033eee  test    rsi, rsi
0x180033ef1  jz      short loc_180033F40
0x180033ef3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033ef7  inc     rax
0x180033efa  cmp     [rdi+rax*2], r13w
0x180033eff  jnz     short loc_180033EF7
0x180033f01  lea     eax, ds:12h[rax*2]
0x180033f08  mov     [rsi], eax
0x180033f0a  jmp     short loc_180033F40
0x180033f0c  test    rsi, rsi
0x180033f0f  jz      short loc_180033F17
0x180033f11  mov     dword ptr [rsi], 4
0x180033f17  test    r14, r14
0x180033f1a  jz      short loc_180033F40
0x180033f1c  mov     r8d, dword ptr [rsp+0D8h+arg_60]
0x180033f24  test    r8d, r8d
0x180033f27  jz      short loc_180033F40
0x180033f29  mov     r9, r14
0x180033f2c  mov     rdx, r15
0x180033f2f  mov     rcx, [rsp+0D8h+arg_0]; unsigned __int16 *
0x180033f37  call    SymGetEstimatedOriginalFilename
0x180033f3c  test    eax, eax
0x180033f3e  jz      short loc_180033F44
0x180033f40  xor     eax, eax
0x180033f42  jmp     short loc_180033F96
0x180033f44  mov     rcx, [rsp+0D8h+arg_88]
0x180033f4c  test    rcx, rcx
0x180033f4f  jz      short loc_180033F64
0x180033f51  mov     rax, [rcx]
0x180033f54  lea     rdx, aFailedToObtain; "Failed to obtain the original file name"...
0x180033f5b  mov     rax, [rax+8]
0x180033f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f64  mov     eax, 80004005h
0x180033f69  jmp     short loc_180033F96
0x180033f6b  mov     rcx, [rsp+0D8h+arg_88]
0x180033f73  test    rcx, rcx
0x180033f76  jz      short loc_180033F8B
0x180033f78  mov     rax, [rcx]
0x180033f7b  lea     rdx, aPagingExceptio; "Paging exception occurred while process"...
0x180033f82  mov     rax, [rax+8]
0x180033f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f8b  mov     ecx, 3E7h; unsigned int
0x180033f90  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180033f95  nop
0x180033f96  add     rsp, 0A0h
0x180033f9d  pop     r15
0x180033f9f  pop     r14
0x180033fa1  pop     r13
0x180033fa3  pop     r12
0x180033fa5  pop     rdi
0x180033fa6  pop     rsi
0x180033fa7  pop     rbx
0x180033fa8  retn
0x180036d21  push    rbp
0x180036d23  sub     rsp, 70h
0x180036d27  mov     rbp, rdx
0x180036d2a  mov     rax, [rcx]
0x180036d2d  xor     ecx, ecx
  ... truncated ...
```
