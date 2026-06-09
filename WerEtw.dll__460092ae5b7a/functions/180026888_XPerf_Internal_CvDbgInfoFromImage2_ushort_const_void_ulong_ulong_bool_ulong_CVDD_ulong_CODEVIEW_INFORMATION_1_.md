# XPerf::Internal::CvDbgInfoFromImage2(ushort const *,void *,ulong,ulong,bool,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,ulong *,ulong *,ushort *,ulong,bool &,bool,EMBEDDED_PDB_INFORMATION &,bool &,XPerfCore::IErrorMessage *)

- ea: `0x180026888`
- end: `0x180026db6`
- name: `?CvDbgInfoFromImage2@Internal@XPerf@@YAJPEBGPEAXKK_NPEAKPEAT_CVDD@@3PEAUCODEVIEW_INFORMATION_1@@33PEAGKAEA_N2AEAUEMBEDDED_PDB_INFORMATION@@7PEAVIErrorMessage@XPerfCore@@@Z`
- size: `1326`
- prototype: `__int64 __fastcall(wchar_t *this, unsigned __int16 *, void *, __int64, unsigned int, unsigned int *, union _CVDD *, union _CVDD *, struct CODEVIEW_INFORMATION_1 *, struct CODEVIEW_INFORMATION_1 *, unsigned int *, unsigned int *, unsigned __int16 *, _BYTE *, BOOLEAN MappedAsImage, struct EMBEDDED_PDB_INFORMATION *, struct EMBEDDED_PDB_INFORMATION *, bool *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f5dc`
- `0x1800275f8`

## callees

- `0x180004694`
- `0x18001f020`
- `0x180026888`
- `0x180026dbc`
- `0x1800272ac`
- `0x1800273a8`
- `0x18002758c`
- `0x18002779c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180026cce`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180026cce`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180026a45`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180026a45`

## pseudocode

```c
__int64 __fastcall XPerf::Internal::CvDbgInfoFromImage2(
        wchar_t *this,
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
        unsigned int *a12,
        unsigned __int16 *a13,
        _BYTE *a14,
        BOOLEAN MappedAsImage,
        struct EMBEDDED_PDB_INFORMATION *a16,
        struct EMBEDDED_PDB_INFORMATION *a17,
        bool *a18)
{
  unsigned int *v18; // r15
  union _CVDD *v19; // rdi
  struct EMBEDDED_PDB_INFORMATION *v20; // r13
  unsigned int *v21; // rbx
  __int64 v22; // rax
  int v23; // r9d
  void *v24; // r10
  struct _IMAGE_NT_HEADERS64 *v25; // rsi
  __int64 result; // rax
  int v27; // eax
  DWORD TimeDateStamp; // edx
  unsigned int SizeOfImage; // ecx
  BOOLEAN v30; // r14
  int v31; // r12d
  int v32; // esi
  _BYTE *v33; // rax
  int v34; // eax
  union _CVDD *v35; // r14
  unsigned int v36; // ecx
  ULONG i; // edx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // rax
  __int16 *v41; // rcx
  __int16 v42; // r8
  unsigned int *v43; // rcx
  wchar_t *v44; // rax
  __int64 v45; // rax
  bool v46; // [rsp+20h] [rbp-B8h]
  bool v47; // [rsp+50h] [rbp-88h]
  ULONG Size[2]; // [rsp+70h] [rbp-68h] BYREF
  int v49; // [rsp+78h] [rbp-60h]
  DWORD v50; // [rsp+7Ch] [rbp-5Ch]
  unsigned int v51; // [rsp+80h] [rbp-58h]
  int v52; // [rsp+84h] [rbp-54h]
  DWORD v53; // [rsp+88h] [rbp-50h]
  unsigned int v54; // [rsp+8Ch] [rbp-4Ch]
  signed __int64 v55; // [rsp+90h] [rbp-48h]
  unsigned int v58; // [rsp+F0h] [rbp+18h]

  v58 = (unsigned int)a3;
  v18 = a6;
  v19 = a7;
  v20 = a16;
  *(_OWORD *)a16 = 0;
  *((_QWORD *)v20 + 2) = 0;
  *(_BYTE *)a17 = 0;
  v21 = a12;
  if ( a12 )
    *(_WORD *)a12 = 0;
  v22 = XPerfCore::_SafeImageNtHeader(a2, (unsigned int)a3);
  v25 = (struct _IMAGE_NT_HEADERS64 *)v22;
  if ( !v22 )
  {
    if ( a18 )
      (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(a18, L"Invalid executable format.");
    return ATL::AtlHresultFromWin32(0xC1u);
  }
  v27 = *(_DWORD *)(v22 + 88);
  v49 = v27;
  v52 = v27;
  TimeDateStamp = v25->FileHeader.TimeDateStamp;
  v50 = TimeDateStamp;
  v53 = TimeDateStamp;
  SizeOfImage = v25->OptionalHeader.SizeOfImage;
  v51 = SizeOfImage;
  v54 = SizeOfImage;
  if ( v23 && v27 != v23 )
  {
    if ( a18 )
      (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(a18, L"Invalid image header checksum.");
    return ATL::AtlHresultFromWin32(0xDu);
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
  v31 = v25->FileHeader.Characteristics & 0x200;
  v32 = SymCommonTlbImpManagedDll(a2, v25, v30);
  Size[0] = 0;
  v33 = RtlImageDirectoryEntryToData(a2, v30, 6u, Size);
  if ( v33 )
  {
    v55 = v33 - (_BYTE *)a2;
    a5 = -1;
    v47 = v30;
    v35 = a8;
    result = CvInfoFromDbgDir(
               a2,
               v58,
               Size[0],
               (int)v33 - (int)a2,
               v46,
               &a5,
               v18,
               v19,
               (unsigned int *)a8,
               a9,
               v47,
               v20,
               (bool *)a17);
    if ( (int)result < 0 )
      return result;
    v36 = *v18;
    if ( *v18 > 1 )
    {
      if ( v32 == 1 )
      {
        if ( a18 )
          (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(
            a18,
            L"Multiple CvDbg entries in IL-only image.");
        return ATL::AtlHresultFromWin32(0xC1u);
      }
      for ( i = 0; ; ++i )
      {
        Size[1] = i;
        if ( i >= v36 )
          break;
        v38 = 1576LL * i;
        if ( *(_DWORD *)((char *)v19 + v38) == 1396986706 && a5 != -1 && i != a5 )
        {
          *(_DWORD *)((char *)v19 + v38) = 3;
          v36 = *v18;
        }
      }
    }
    v34 = *(_DWORD *)v19;
    if ( *(_DWORD *)v19 == 1 )
    {
      v34 = 1;
    }
    else if ( v34 || !v31 )
    {
      if ( v32 == 1 )
      {
        *(_DWORD *)v19 = 3;
        v34 = 3;
      }
    }
    else
    {
      *(_DWORD *)v19 = 2;
      v34 = 2;
    }
  }
  else
  {
    if ( !v31 )
    {
LABEL_24:
      *v18 = 1;
      *(_DWORD *)v19 = 0;
      v34 = 0;
      v35 = a8;
      goto LABEL_47;
    }
    *v18 = 1;
    *(_DWORD *)v19 = 2;
    v34 = 2;
    v35 = a8;
  }
LABEL_47:
  if ( !v34 )
  {
    if ( v35 )
      *(_DWORD *)v35 = 4;
LABEL_75:
    if ( !v21 || !(_DWORD)a13 || (unsigned int)SymGetEstimatedOriginalFilename(this) )
      return 0;
    goto LABEL_79;
  }
  if ( (unsigned int)(v34 - 1) > 1 )
    goto LABEL_75;
  *((_DWORD *)v19 + 1) = v49;
  *((_DWORD *)v19 + 2) = v50;
  *((_DWORD *)v19 + 3) = v51;
  if ( !(unsigned int)SymGetEstimatedOriginalFilename(this) )
  {
LABEL_79:
    if ( a18 )
      (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(
        a18,
        L"Failed to obtain the original file name.");
    return 2147500037LL;
  }
  if ( !v21 )
    goto LABEL_84;
  v39 = (unsigned int)a13;
  if ( !(_DWORD)a13 || (result = 0, (unsigned int)a13 > 0x7FFFFFFFuLL) )
    result = 2147942487LL;
  if ( (int)result < 0 )
  {
    if ( (_DWORD)a13 )
      *(_WORD *)v21 = 0;
  }
  else
  {
    v40 = 2147483646;
    v41 = (__int16 *)((char *)v19 + 16);
    if ( (_DWORD)a13 )
    {
      do
      {
        if ( !v40 )
          break;
        v42 = *v41;
        if ( !*v41 )
          break;
        ++v41;
        *(_WORD *)v21 = v42;
        v21 = (unsigned int *)((char *)v21 + 2);
        --v40;
        --v39;
      }
      while ( v39 );
    }
    v43 = (unsigned int *)((char *)v21 - 2);
    if ( v39 )
      v43 = v21;
    *(_WORD *)v43 = 0;
    result = v39 == 0 ? 0x8007007A : 0;
  }
  if ( (int)result >= 0 )
  {
LABEL_84:
    if ( *(_DWORD *)v19 != 2 )
      goto LABEL_69;
    v44 = wcsrchr((const wchar_t *)v19 + 8, 0x2Eu);
    if ( v44 )
      *v44 = 0;
    result = StringCchCatW((unsigned __int16 *)v19 + 8, 0x30Cu, L".dbg");
    if ( (int)result >= 0 )
    {
LABEL_69:
      if ( v35 )
      {
        v45 = -1;
        do
          ++v45;
        while ( *((_WORD *)v19 + v45 + 8) );
        *(_DWORD *)v35 = 2 * v45 + 18;
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180026888  mov     [rsp+arg_10], r8d
0x18002688d  mov     [rsp+BaseAddress], rdx
0x180026892  mov     [rsp+Str], rcx
0x180026897  push    rbx
0x180026898  push    rsi
0x180026899  push    rdi
0x18002689a  push    r12
0x18002689c  push    r13
0x18002689e  push    r14
0x1800268a0  push    r15
0x1800268a2  sub     rsp, 0A0h
0x1800268a9  mov     r10, rdx
0x1800268ac  mov     r15, [rsp+0D8h+arg_28]
0x1800268b4  mov     rdi, [rsp+0D8h+arg_30]
0x1800268bc  xorps   xmm0, xmm0
0x1800268bf  xor     eax, eax
0x1800268c1  mov     r13, [rsp+0D8h+arg_78]
0x1800268c9  movups  xmmword ptr [r13+0], xmm0
0x1800268ce  mov     [r13+10h], rax
0x1800268d2  xor     r12d, r12d
0x1800268d5  mov     rax, [rsp+0D8h+arg_80]
0x1800268dd  mov     [rax], r12b
0x1800268e0  mov     rbx, [rsp+0D8h+arg_58]
0x1800268e8  test    rbx, rbx
0x1800268eb  jz      short loc_1800268F1
0x1800268ed  mov     [rbx], r12w
0x1800268f1  mov     edx, r8d
0x1800268f4  mov     rcx, r10
0x1800268f7  call    XPerfCore___SafeImageNtHeader
0x1800268fc  mov     rsi, rax
0x1800268ff  test    rax, rax
0x180026902  jnz     short loc_180026933
0x180026904  mov     rcx, [rsp+0D8h+arg_88]
0x18002690c  test    rcx, rcx
0x18002690f  jz      short loc_180026924
0x180026911  mov     rax, [rcx]
0x180026914  lea     rdx, aInvalidExecuta; "Invalid executable format."
0x18002691b  mov     rax, [rax+8]
0x18002691f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026924  mov     ecx, 0C1h; unsigned int
0x180026929  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002692e  jmp     loc_180026DA3
0x180026933  mov     eax, [rax+58h]
0x180026936  mov     [rsp+0D8h+var_60], eax
0x18002693a  mov     [rsp+0D8h+var_54], eax
0x180026941  mov     edx, [rsi+8]
0x180026944  mov     [rsp+0D8h+var_5C], edx
0x180026948  mov     [rsp+0D8h+var_50], edx
0x18002694f  mov     ecx, [rsi+50h]
0x180026952  mov     [rsp+0D8h+var_58], ecx
0x180026959  mov     [rsp+0D8h+var_4C], ecx
0x180026960  test    r9d, r9d
0x180026963  jz      short loc_180026999
0x180026965  cmp     eax, r9d
0x180026968  jz      short loc_180026999
0x18002696a  mov     rcx, [rsp+0D8h+arg_88]
0x180026972  test    rcx, rcx
0x180026975  jz      short loc_18002698A
0x180026977  mov     rax, [rcx]
0x18002697a  lea     rdx, aInvalidImageHe; "Invalid image header checksum."
0x180026981  mov     rax, [rax+8]
0x180026985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002698a  mov     ecx, 0Dh; unsigned int
0x18002698f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180026994  jmp     loc_180026DA3
0x180026999  mov     rax, [rsp+0D8h+arg_48]
0x1800269a1  test    rax, rax
0x1800269a4  jz      short loc_1800269A8
0x1800269a6  mov     [rax], edx
0x1800269a8  mov     rax, [rsp+0D8h+arg_50]
0x1800269b0  test    rax, rax
0x1800269b3  jz      short loc_1800269B7
0x1800269b5  mov     [rax], ecx
0x1800269b7  mov     eax, 10Bh
0x1800269bc  cmp     [rsi+18h], ax
0x1800269c0  jz      short loc_1800269E4
0x1800269c2  mov     eax, 20Bh
0x1800269c7  cmp     [rsi+18h], ax
0x1800269cb  jz      short loc_1800269D7
0x1800269cd  mov     eax, 8000FFFFh
0x1800269d2  jmp     loc_180026DA3
0x1800269d7  mov     rax, [rsp+0D8h+arg_68]
0x1800269df  mov     byte ptr [rax], 1
0x1800269e2  jmp     short loc_1800269EF
0x1800269e4  mov     rax, [rsp+0D8h+arg_68]
0x1800269ec  mov     [rax], r12b
0x1800269ef  mov     r14b, [rsp+0D8h+MappedAsImage]
0x1800269f7  mov     dl, r14b
0x1800269fa  mov     rcx, r10; BaseAddress
0x1800269fd  call    SymCommonNativeResourceOnlyDll
0x180026a02  test    eax, eax
0x180026a04  jnz     short loc_180026A5B
0x180026a06  movzx   r12d, word ptr [rsi+16h]
0x180026a0b  and     r12d, 200h
0x180026a12  mov     r8b, r14b; MappedAsImage
0x180026a15  mov     rdx, rsi; NtHeader
0x180026a18  mov     rcx, [rsp+0D8h+BaseAddress]; BaseAddress
0x180026a20  call    SymCommonTlbImpManagedDll
0x180026a25  mov     esi, eax
0x180026a27  mov     [rsp+0D8h+Size], 0
0x180026a2f  mov     r8d, 6; Directory
0x180026a35  lea     r9, [rsp+0D8h+Size]; Size
0x180026a3a  mov     dl, r14b; MappedAsImage
0x180026a3d  mov     rcx, [rsp+0D8h+BaseAddress]; BaseAddress
0x180026a45  call    cs:__imp_RtlImageDirectoryEntryToData
0x180026a4b  mov     r9, rax
0x180026a4e  test    rax, rax
0x180026a51  jnz     short loc_180026AA7
0x180026a53  test    r12d, r12d
0x180026a56  jnz     short loc_180026A7D
0x180026a58  xor     r12d, r12d
0x180026a5b  mov     dword ptr [r15], 1
0x180026a62  mov     [rdi], r12d
0x180026a65  mov     eax, r12d
0x180026a68  mov     r14, [rsp+0D8h+arg_38]
0x180026a70  mov     r13, [rsp+0D8h+BaseAddress]
0x180026a78  jmp     loc_180026BE4
0x180026a7d  mov     dword ptr [r15], 1
0x180026a84  mov     dword ptr [rdi], 2
0x180026a8a  mov     eax, 2
0x180026a8f  mov     r14, [rsp+0D8h+arg_38]
0x180026a97  mov     r13, [rsp+0D8h+BaseAddress]
0x180026a9f  xor     r12d, r12d
0x180026aa2  jmp     loc_180026BE4
0x180026aa7  sub     r9, [rsp+0D8h+BaseAddress]; unsigned int
0x180026aaf  mov     [rsp+0D8h+var_48], r9
0x180026ab7  mov     [rsp+0D8h+arg_20], 0FFFFFFFFh
0x180026ac2  mov     rax, [rsp+0D8h+arg_80]
0x180026aca  mov     [rsp+0D8h+var_78], rax; bool *
0x180026acf  mov     [rsp+0D8h+var_80], r13; struct EMBEDDED_PDB_INFORMATION *
0x180026ad4  mov     [rsp+0D8h+var_88], r14b; bool
0x180026ad9  mov     rax, [rsp+0D8h+arg_40]
0x180026ae1  mov     [rsp+0D8h+var_90], rax; struct CODEVIEW_INFORMATION_1 *
0x180026ae6  mov     r14, [rsp+0D8h+arg_38]
0x180026aee  mov     [rsp+0D8h+var_98], r14; unsigned int *
0x180026af3  mov     [rsp+0D8h+var_A0], rdi; union _CVDD *
0x180026af8  mov     [rsp+0D8h+var_A8], r15; unsigned int *
0x180026afd  lea     rax, [rsp+0D8h+arg_20]
0x180026b05  mov     [rsp+0D8h+var_B0], rax; unsigned int *
0x180026b0a  mov     r8d, [rsp+0D8h+Size]; unsigned int
0x180026b0f  mov     edx, [rsp+0D8h+arg_10]; unsigned int
0x180026b16  mov     r13, [rsp+0D8h+BaseAddress]
0x180026b1e  mov     rcx, r13; void *
0x180026b21  call    ?CvInfoFromDbgDir@@YAJPEAXKKK_NPEAK2PEAT_CVDD@@2PEAUCODEVIEW_INFORMATION_1@@1AEAUEMBEDDED_PDB_INFORMATION@@AEA_N@Z; CvInfoFromDbgDir(void *,ulong,ulong,ulong,bool,ulong *,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,bool,EMBEDDED_PDB_INFORMATION &,bool &)
0x180026b26  test    eax, eax
0x180026b28  js      loc_180026DA3
0x180026b2e  mov     ecx, [r15]
0x180026b31  cmp     ecx, 1
0x180026b34  jbe     short loc_180026BA9
0x180026b36  cmp     esi, 1
0x180026b39  jnz     short loc_180026B6A
0x180026b3b  mov     rcx, [rsp+0D8h+arg_88]
0x180026b43  test    rcx, rcx
0x180026b46  jz      short loc_180026B5B
0x180026b48  mov     rax, [rcx]
0x180026b4b  lea     rdx, aMultipleCvdbgE; "Multiple CvDbg entries in IL-only image"...
0x180026b52  mov     rax, [rax+8]
0x180026b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b5b  mov     ecx, 0C1h; unsigned int
0x180026b60  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180026b65  jmp     loc_180026DA3
0x180026b6a  xor     edx, edx
0x180026b6c  mov     [rsp+0D8h+var_64], edx
0x180026b70  cmp     edx, ecx
0x180026b72  jnb     short loc_180026BA9
0x180026b74  mov     eax, edx
0x180026b76  imul    r8, rax, 628h
0x180026b7d  cmp     dword ptr [r8+rdi], 53445352h
0x180026b85  jnz     short loc_180026BA5
0x180026b87  cmp     [rsp+0D8h+arg_20], 0FFFFFFFFh
0x180026b8f  jz      short loc_180026BA5
0x180026b91  cmp     edx, [rsp+0D8h+arg_20]
0x180026b98  jz      short loc_180026BA5
0x180026b9a  mov     dword ptr [r8+rdi], 3
0x180026ba2  mov     ecx, [r15]
0x180026ba5  inc     edx
0x180026ba7  jmp     short loc_180026B6C
0x180026ba9  mov     eax, [rdi]
0x180026bab  cmp     eax, 1
0x180026bae  jz      short loc_180026BDC
0x180026bb0  test    eax, eax
0x180026bb2  jnz     short loc_180026BC9
0x180026bb4  test    r12d, r12d
0x180026bb7  jz      short loc_180026BC9
0x180026bb9  mov     dword ptr [rdi], 2
0x180026bbf  mov     eax, 2
0x180026bc4  xor     r12d, r12d
0x180026bc7  jmp     short loc_180026BE4
0x180026bc9  cmp     esi, 1
0x180026bcc  jnz     short loc_180026BD7
0x180026bce  mov     dword ptr [rdi], 3
0x180026bd4  lea     eax, [rsi+2]
0x180026bd7  xor     r12d, r12d
0x180026bda  jmp     short loc_180026BE4
0x180026bdc  mov     eax, 1
0x180026be1  xor     r12d, r12d
0x180026be4  test    eax, eax
0x180026be6  jz      loc_180026D18
0x180026bec  sub     eax, 1
0x180026bef  jz      short loc_180026BFA
0x180026bf1  cmp     eax, 1
0x180026bf4  jnz     loc_180026D24
0x180026bfa  mov     eax, [rsp+0D8h+var_60]
0x180026bfe  mov     [rdi+4], eax
0x180026c01  mov     eax, [rsp+0D8h+var_5C]
0x180026c05  mov     [rdi+8], eax
0x180026c08  mov     eax, [rsp+0D8h+var_58]
0x180026c0f  mov     [rdi+0Ch], eax
0x180026c12  lea     rsi, [rdi+10h]
0x180026c16  mov     r9, rsi
0x180026c19  mov     r8d, 307h
0x180026c1f  mov     rdx, r13
0x180026c22  mov     rcx, [rsp+0D8h+Str]; Str
0x180026c2a  call    SymGetEstimatedOriginalFilename
0x180026c2f  test    eax, eax
0x180026c31  jz      loc_180026D51
0x180026c37  test    rbx, rbx
0x180026c3a  jz      loc_180026CC1
0x180026c40  mov     eax, dword ptr [rsp+0D8h+arg_60]
0x180026c47  mov     edx, eax
0x180026c49  test    eax, eax
0x180026c4b  jz      short loc_180026C59
0x180026c4d  mov     eax, r12d
0x180026c50  cmp     rdx, 7FFFFFFFh
0x180026c57  jbe     short loc_180026C5E
0x180026c59  mov     eax, 80070057h
0x180026c5e  test    eax, eax
0x180026c60  js      short loc_180026CB0
0x180026c62  mov     eax, 7FFFFFFEh
0x180026c67  mov     rcx, rsi
0x180026c6a  test    rdx, rdx
0x180026c6d  jz      short loc_180026C93
0x180026c6f  test    rax, rax
0x180026c72  jz      short loc_180026C93
0x180026c74  movzx   r8d, word ptr [rcx]
0x180026c78  test    r8w, r8w
0x180026c7c  jz      short loc_180026C93
0x180026c7e  add     rcx, 2
0x180026c82  mov     [rbx], r8w
0x180026c86  add     rbx, 2
0x180026c8a  dec     rax
0x180026c8d  sub     rdx, 1
0x180026c91  jnz     short loc_180026C6F
0x180026c93  lea     rcx, [rbx-2]
0x180026c97  test    rdx, rdx
0x180026c9a  cmovnz  rcx, rbx
0x180026c9e  mov     [rcx], r12w
0x180026ca2  neg     rdx
0x180026ca5  sbb     eax, eax
0x180026ca7  not     eax
0x180026ca9  and     eax, 8007007Ah
0x180026cae  jmp     short loc_180026CB9
0x180026cb0  test    rdx, rdx
0x180026cb3  jz      short loc_180026CB9
0x180026cb5  mov     [rbx], r12w
0x180026cb9  test    eax, eax
0x180026cbb  js      loc_180026DA3
0x180026cc1  cmp     dword ptr [rdi], 2
0x180026cc4  jnz     short loc_180026CF9
0x180026cc6  mov     edx, 2Eh ; '.'; Ch
0x180026ccb  mov     rcx, rsi; Str
0x180026cce  call    cs:__imp_wcsrchr
0x180026cd4  test    rax, rax
0x180026cd7  jz      short loc_180026CDD
0x180026cd9  mov     [rax], r12w
0x180026cdd  lea     r8, aDbg; ".dbg"
0x180026ce4  mov     edx, 30Ch; unsigned __int64
0x180026ce9  mov     rcx, rsi; unsigned __int16 *
0x180026cec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026cf1  test    eax, eax
0x180026cf3  js      loc_180026DA3
0x180026cf9  test    r14, r14
0x180026cfc  jz      short loc_180026D4D
0x180026cfe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026d02  inc     rax
0x180026d05  cmp     [rsi+rax*2], r12w
0x180026d0a  jnz     short loc_180026D02
0x180026d0c  lea     eax, ds:12h[rax*2]
0x180026d13  mov     [r14], eax
0x180026d16  jmp     short loc_180026D4D
0x180026d18  test    r14, r14
0x180026d1b  jz      short loc_180026D24
0x180026d1d  mov     dword ptr [r14], 4
0x180026d24  test    rbx, rbx
0x180026d27  jz      short loc_180026D4D
0x180026d29  mov     r8d, dword ptr [rsp+0D8h+arg_60]
0x180026d31  test    r8d, r8d
0x180026d34  jz      short loc_180026D4D
0x180026d36  mov     r9, rbx
0x180026d39  mov     rdx, r13
0x180026d3c  mov     rcx, [rsp+0D8h+Str]; Str
0x180026d44  call    SymGetEstimatedOriginalFilename
0x180026d49  test    eax, eax
0x180026d4b  jz      short loc_180026D51
0x180026d4d  xor     eax, eax
0x180026d4f  jmp     short loc_180026DA3
0x180026d51  mov     rcx, [rsp+0D8h+arg_88]
0x180026d59  test    rcx, rcx
0x180026d5c  jz      short loc_180026D71
0x180026d5e  mov     rax, [rcx]
  ... truncated ...
```
