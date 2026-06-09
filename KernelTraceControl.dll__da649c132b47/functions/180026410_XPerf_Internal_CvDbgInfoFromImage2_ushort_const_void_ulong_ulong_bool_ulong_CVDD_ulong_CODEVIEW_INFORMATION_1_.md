# XPerf::Internal::CvDbgInfoFromImage2(ushort const *,void *,ulong,ulong,bool,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,ulong *,ulong *,ushort *,ulong,bool &,bool,EMBEDDED_PDB_INFORMATION &,bool &)

- ea: `0x180026410`
- end: `0x18002684b`
- name: `?CvDbgInfoFromImage2@Internal@XPerf@@YAJPEBGPEAXKK_NPEAKPEAT_CVDD@@3PEAUCODEVIEW_INFORMATION_1@@33PEAGKAEA_N2AEAUEMBEDDED_PDB_INFORMATION@@7@Z`
- size: `1083`
- prototype: `__int64 __fastcall(wchar_t *this, unsigned __int16 *, void *, __int64, char, unsigned int *, unsigned int *, union _CVDD *, unsigned int *, struct CODEVIEW_INFORMATION_1 *, unsigned int *, unsigned __int16 *, unsigned __int16 *, _BYTE *, BOOLEAN MappedAsImage, _QWORD *, struct EMBEDDED_PDB_INFORMATION *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000a30c`
- `0x1800262c4`

## callees

- `0x180006960`
- `0x1800136c4`
- `0x18001dd1c`
- `0x1800257c8`
- `0x180025a5c`
- `0x180025b40`
- `0x180025c20`
- `0x180025e04`
- `0x180026410`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800267a2`
- `msvcrt!wcsrchr` at `0x1800267a2`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180026587`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180026587`

## pseudocode

```c
__int64 __fastcall XPerf::Internal::CvDbgInfoFromImage2(
        wchar_t *this,
        unsigned __int16 *a2,
        void *a3,
        __int64 a4,
        char a5,
        unsigned int *a6,
        unsigned int *a7,
        union _CVDD *a8,
        unsigned int *a9,
        struct CODEVIEW_INFORMATION_1 *a10,
        unsigned int *a11,
        unsigned __int16 *a12,
        unsigned __int16 *a13,
        _BYTE *a14,
        BOOLEAN MappedAsImage,
        _QWORD *a16,
        struct EMBEDDED_PDB_INFORMATION *a17)
{
  struct EMBEDDED_PDB_INFORMATION *v17; // r13
  __int64 v18; // rax
  void *v19; // r8
  int v20; // r9d
  char v21; // r10
  struct _IMAGE_NT_HEADERS64 *v22; // rbx
  __int64 result; // rax
  unsigned int v24; // eax
  DWORD TimeDateStamp; // ecx
  unsigned int SizeOfImage; // edx
  int Magic; // eax
  _BYTE *v28; // rax
  unsigned int *v29; // rbx
  union _CVDD *v30; // rsi
  unsigned int *v31; // rax
  unsigned int i; // ecx
  __int64 v33; // rdx
  wchar_t *v34; // rax
  __int64 v35; // rax
  struct CODEVIEW_INFORMATION_1 *v36; // [rsp+48h] [rbp-80h]
  ULONG Size; // [rsp+60h] [rbp-68h] BYREF
  BOOL v38; // [rsp+64h] [rbp-64h]
  unsigned int v39; // [rsp+68h] [rbp-60h]
  unsigned int v40; // [rsp+6Ch] [rbp-5Ch]
  unsigned int v41; // [rsp+70h] [rbp-58h]
  unsigned int v42; // [rsp+74h] [rbp-54h]
  unsigned int v43; // [rsp+78h] [rbp-50h]
  DWORD v44; // [rsp+7Ch] [rbp-4Ch]
  unsigned int v45; // [rsp+80h] [rbp-48h]
  signed __int64 v46; // [rsp+88h] [rbp-40h]
  unsigned int v49; // [rsp+E0h] [rbp+18h]
  char v50; // [rsp+F0h] [rbp+28h]

  v49 = (unsigned int)a3;
  *a16 = 0;
  a16[1] = 0;
  a16[2] = 0;
  v17 = a17;
  *(_BYTE *)a17 = 0;
  if ( a12 )
    *a12 = 0;
  v18 = sub_1800257C8(a2, (unsigned int)a3);
  v22 = (struct _IMAGE_NT_HEADERS64 *)v18;
  if ( !v18 )
    return ATL::AtlHresultFromWin32(0xC1u);
  v24 = *(_DWORD *)(v18 + 88);
  v40 = v24;
  v43 = v24;
  TimeDateStamp = v22->FileHeader.TimeDateStamp;
  v41 = TimeDateStamp;
  v44 = TimeDateStamp;
  SizeOfImage = v22->OptionalHeader.SizeOfImage;
  v42 = SizeOfImage;
  v45 = SizeOfImage;
  if ( v20 && v24 != v20 )
    return ATL::AtlHresultFromWin32(0xDu);
  if ( a10 )
    *(_DWORD *)a10 = TimeDateStamp;
  if ( a11 )
    *a11 = SizeOfImage;
  Magic = v22->OptionalHeader.Magic;
  if ( Magic == 267 )
  {
    *a14 = v21;
  }
  else
  {
    if ( Magic != 523 )
      return 2147549183LL;
    *a14 = 1;
  }
  if ( (unsigned int)sub_180025B40(v19) )
    goto LABEL_20;
  v38 = (v22->FileHeader.Characteristics & 0x200) != 0;
  v50 = (unsigned int)sub_180025C20(a2, v22, MappedAsImage) == 1;
  Size = 0;
  v28 = RtlImageDirectoryEntryToData(a2, MappedAsImage, 6u, &Size);
  if ( v28 )
  {
    v46 = v28 - (_BYTE *)a2;
    LODWORD(a17) = -1;
    *(_BYTE *)v17 = 0;
    LOBYTE(v36) = MappedAsImage;
    v30 = a8;
    v29 = a7;
    result = CvInfoFromDbgDir(
               (char *)a2,
               v49,
               Size,
               (int)v28 - (int)a2,
               (unsigned int *)&a17,
               a6,
               a7,
               a8,
               a9,
               v36,
               (__int64)a16,
               v17);
    if ( (int)result < 0 )
      return result;
    if ( *(_BYTE *)v17 && a10 )
      *(_DWORD *)a10 = 0;
    v31 = a6;
    if ( *a6 > 1 )
    {
      if ( v50 )
        return ATL::AtlHresultFromWin32(0xC1u);
      for ( i = 0; ; ++i )
      {
        v39 = i;
        if ( i >= *v31 )
          break;
        v33 = 394LL * i;
        if ( a7[v33] == 1396986706 && (_DWORD)a17 != -1 && i != (_DWORD)a17 )
          a7[v33] = 3;
        v31 = a6;
      }
    }
    if ( *a7 != 1 )
    {
      if ( *a7 || !v38 )
      {
        if ( v50 )
          *a7 = 3;
      }
      else
      {
        *a7 = 2;
      }
    }
  }
  else
  {
    if ( !v38 )
    {
LABEL_20:
      *a6 = 1;
      v29 = a7;
      *a7 = 0;
      v30 = a8;
      goto LABEL_42;
    }
    *a6 = 1;
    v29 = a7;
    *a7 = 2;
    v30 = a8;
  }
LABEL_42:
  if ( *v29 )
  {
    if ( *v29 - 1 <= 1 )
    {
      v29[1] = v40;
      v29[2] = v41;
      v29[3] = v42;
      if ( !(unsigned int)SymGetEstimatedOriginalFilename(this) )
        return 2147500037LL;
      if ( !a12
        || (result = StringCchCopyW(a12, (unsigned int)a13, (const unsigned __int16 *)v29 + 8), (int)result >= 0) )
      {
        if ( *v29 != 2 )
          goto LABEL_51;
        v34 = wcsrchr((const wchar_t *)v29 + 8, 0x2Eu);
        if ( v34 )
          *v34 = 0;
        result = StringCchCatW((unsigned __int16 *)v29 + 8, 0x30Cu, L".dbg");
        if ( (int)result >= 0 )
        {
LABEL_51:
          if ( v30 )
          {
            v35 = -1;
            do
              ++v35;
            while ( *((_WORD *)v29 + v35 + 8) );
            *(_DWORD *)v30 = 2 * v35 + 18;
          }
          return 0;
        }
      }
      return result;
    }
  }
  else if ( v30 )
  {
    *(_DWORD *)v30 = 4;
  }
  if ( !a12 || !(_DWORD)a13 )
    return 0;
  return (unsigned int)SymGetEstimatedOriginalFilename(this) == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180026410  mov     [rsp+arg_10], r8d
0x180026415  mov     [rsp+BaseAddress], rdx
0x18002641a  mov     [rsp+Str], rcx
0x18002641f  push    rbx
0x180026420  push    rsi
0x180026421  push    rdi
0x180026422  push    r12
0x180026424  push    r13
0x180026426  push    r14
0x180026428  push    r15
0x18002642a  sub     rsp, 90h
0x180026431  mov     eax, r8d
0x180026434  mov     r8, rdx
0x180026437  xor     ecx, ecx
0x180026439  mov     rsi, [rsp+0C8h+arg_78]
0x180026441  mov     [rsi], rcx
0x180026444  mov     [rsi+8], rcx
0x180026448  mov     [rsi+10h], rcx
0x18002644c  xor     r10d, r10d
0x18002644f  mov     r13, [rsp+0C8h+arg_80]
0x180026457  mov     [r13+0], r10b
0x18002645b  mov     r15, [rsp+0C8h+arg_58]
0x180026463  test    r15, r15
0x180026466  jz      short loc_18002646C
0x180026468  mov     [r15], r10w
0x18002646c  mov     edx, eax
0x18002646e  mov     rcx, r8
0x180026471  call    sub_1800257C8
0x180026476  mov     rbx, rax
0x180026479  test    rax, rax
0x18002647c  jnz     short loc_18002648D
0x18002647e  mov     ecx, 0C1h; unsigned int
0x180026483  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180026488  jmp     loc_180026838
0x18002648d  mov     eax, [rax+58h]
0x180026490  mov     [rsp+0C8h+var_5C], eax
0x180026494  mov     [rsp+0C8h+var_50], eax
0x180026498  mov     ecx, [rbx+8]
0x18002649b  mov     [rsp+0C8h+var_58], ecx
0x18002649f  mov     [rsp+0C8h+var_4C], ecx
0x1800264a3  mov     edx, [rbx+50h]
0x1800264a6  mov     [rsp+0C8h+var_54], edx
0x1800264aa  mov     [rsp+0C8h+var_48], edx
0x1800264b1  test    r9d, r9d
0x1800264b4  jz      short loc_1800264CA
0x1800264b6  cmp     eax, r9d
0x1800264b9  jz      short loc_1800264CA
0x1800264bb  mov     ecx, 0Dh; unsigned int
0x1800264c0  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800264c5  jmp     loc_180026838
0x1800264ca  mov     r14, [rsp+0C8h+arg_48]
0x1800264d2  test    r14, r14
0x1800264d5  jz      short loc_1800264DA
0x1800264d7  mov     [r14], ecx
0x1800264da  mov     rax, [rsp+0C8h+arg_50]
0x1800264e2  test    rax, rax
0x1800264e5  jz      short loc_1800264E9
0x1800264e7  mov     [rax], edx
0x1800264e9  movzx   eax, word ptr [rbx+18h]
0x1800264ed  cmp     eax, 10Bh
0x1800264f2  jz      short loc_180026517
0x1800264f4  cmp     eax, 20Bh
0x1800264f9  jz      short loc_180026505
0x1800264fb  mov     eax, 8000FFFFh
0x180026500  jmp     loc_180026838
0x180026505  mov     edi, 1
0x18002650a  mov     rax, [rsp+0C8h+arg_68]
0x180026512  mov     [rax], dil
0x180026515  jmp     short loc_180026527
0x180026517  mov     rax, [rsp+0C8h+arg_68]
0x18002651f  mov     [rax], r10b
0x180026522  mov     edi, 1
0x180026527  mov     r12b, [rsp+0C8h+MappedAsImage]
0x18002652f  mov     dl, r12b
0x180026532  mov     rcx, r8; BaseAddress
0x180026535  call    sub_180025B40
0x18002653a  test    eax, eax
0x18002653c  jz      short loc_180026543
0x18002653e  xor     r13d, r13d
0x180026541  jmp     short loc_18002659F
0x180026543  movzx   eax, word ptr [rbx+16h]
0x180026547  shr     eax, 9
0x18002654a  and     al, dil
0x18002654d  mov     [rsp+0C8h+var_64], eax
0x180026551  mov     r8b, r12b; MappedAsImage
0x180026554  mov     rdx, rbx; NtHeader
0x180026557  mov     rbx, [rsp+0C8h+BaseAddress]
0x18002655f  mov     rcx, rbx; BaseAddress
0x180026562  call    sub_180025C20
0x180026567  cmp     eax, edi
0x180026569  setz    [rsp+0C8h+arg_20]
0x180026571  and     [rsp+0C8h+Size], 0
0x180026576  mov     r8d, 6; Directory
0x18002657c  lea     r9, [rsp+0C8h+Size]; Size
0x180026581  mov     dl, r12b; MappedAsImage
0x180026584  mov     rcx, rbx; BaseAddress
0x180026587  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002658d  mov     rcx, rax
0x180026590  test    rax, rax
0x180026593  jnz     short loc_1800265F6
0x180026595  xor     r13d, r13d
0x180026598  cmp     byte ptr [rsp+0C8h+var_64], r13b
0x18002659d  jnz     short loc_1800265C9
0x18002659f  mov     rax, [rsp+0C8h+arg_28]
0x1800265a7  mov     [rax], edi
0x1800265a9  mov     rbx, [rsp+0C8h+arg_30]
0x1800265b1  mov     [rbx], r13d
0x1800265b4  mov     rsi, [rsp+0C8h+arg_38]
0x1800265bc  mov     r12, [rsp+0C8h+BaseAddress]
0x1800265c4  jmp     loc_18002672C
0x1800265c9  mov     rax, [rsp+0C8h+arg_28]
0x1800265d1  mov     [rax], edi
0x1800265d3  mov     rbx, [rsp+0C8h+arg_30]
0x1800265db  mov     dword ptr [rbx], 2
0x1800265e1  mov     rsi, [rsp+0C8h+arg_38]
0x1800265e9  mov     r12, [rsp+0C8h+BaseAddress]
0x1800265f1  jmp     loc_18002672C
0x1800265f6  sub     rcx, rbx
0x1800265f9  mov     [rsp+0C8h+var_40], rcx
0x180026601  or      dword ptr [rsp+0C8h+arg_80], 0FFFFFFFFh
0x180026609  mov     byte ptr [r13+0], 0
0x18002660e  mov     [rsp+0C8h+var_70], r13; struct EMBEDDED_PDB_INFORMATION *
0x180026613  mov     qword ptr [rsp+0C8h+var_78], rsi; bool
0x180026618  mov     byte ptr [rsp+0C8h+var_80], r12b; struct CODEVIEW_INFORMATION_1 *
0x18002661d  mov     rax, [rsp+0C8h+arg_40]
0x180026625  mov     [rsp+0C8h+var_88], rax; unsigned int *
0x18002662a  mov     rsi, [rsp+0C8h+arg_38]
0x180026632  mov     [rsp+0C8h+var_90], rsi; union _CVDD *
0x180026637  mov     rbx, [rsp+0C8h+arg_30]
0x18002663f  mov     [rsp+0C8h+var_98], rbx; unsigned int *
0x180026644  mov     rax, [rsp+0C8h+arg_28]
0x18002664c  mov     [rsp+0C8h+var_A0], rax; unsigned int *
0x180026651  lea     rax, [rsp+0C8h+arg_80]
0x180026659  mov     qword ptr [rsp+0C8h+var_A8], rax; bool
0x18002665e  mov     r9d, ecx; unsigned int
0x180026661  mov     r8d, [rsp+0C8h+Size]; unsigned int
0x180026666  mov     edx, [rsp+0C8h+arg_10]; unsigned int
0x18002666d  mov     r12, [rsp+0C8h+BaseAddress]
0x180026675  mov     rcx, r12; void *
0x180026678  call    ?CvInfoFromDbgDir@@YAJPEAXKKK_NPEAK2PEAT_CVDD@@2PEAUCODEVIEW_INFORMATION_1@@1AEAUEMBEDDED_PDB_INFORMATION@@AEA_N@Z; CvInfoFromDbgDir(void *,ulong,ulong,ulong,bool,ulong *,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,bool,EMBEDDED_PDB_INFORMATION &,bool &)
0x18002667d  test    eax, eax
0x18002667f  js      loc_180026838
0x180026685  cmp     byte ptr [r13+0], 0
0x18002668a  jz      short loc_180026699
0x18002668c  xor     r13d, r13d
0x18002668f  test    r14, r14
0x180026692  jz      short loc_18002669C
0x180026694  mov     [r14], r13d
0x180026697  jmp     short loc_18002669C
0x180026699  xor     r13d, r13d
0x18002669c  mov     rax, [rsp+0C8h+arg_28]
0x1800266a4  mov     r8b, [rsp+0C8h+arg_20]
0x1800266ac  cmp     [rax], edi
0x1800266ae  jbe     short loc_180026707
0x1800266b0  test    r8b, r8b
0x1800266b3  jz      short loc_1800266C4
0x1800266b5  mov     ecx, 0C1h; unsigned int
0x1800266ba  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800266bf  jmp     loc_180026838
0x1800266c4  mov     ecx, r13d
0x1800266c7  mov     [rsp+0C8h+var_60], ecx
0x1800266cb  cmp     ecx, [rax]
0x1800266cd  jnb     short loc_180026707
0x1800266cf  mov     eax, ecx
0x1800266d1  imul    rdx, rax, 628h
0x1800266d8  cmp     dword ptr [rdx+rbx], 53445352h
0x1800266df  jnz     short loc_1800266FB
0x1800266e1  cmp     dword ptr [rsp+0C8h+arg_80], 0FFFFFFFFh
0x1800266e9  jz      short loc_1800266FB
0x1800266eb  cmp     ecx, dword ptr [rsp+0C8h+arg_80]
0x1800266f2  jz      short loc_1800266FB
0x1800266f4  mov     dword ptr [rdx+rbx], 3
0x1800266fb  add     ecx, edi
0x1800266fd  mov     rax, [rsp+0C8h+arg_28]
0x180026705  jmp     short loc_1800266C7
0x180026707  cmp     [rbx], edi
0x180026709  jz      short loc_18002672C
0x18002670b  cmp     [rbx], r13d
0x18002670e  jnz     short loc_18002671F
0x180026710  cmp     byte ptr [rsp+0C8h+var_64], r13b
0x180026715  jz      short loc_18002671F
0x180026717  mov     dword ptr [rbx], 2
0x18002671d  jmp     short loc_18002672C
0x18002671f  test    r8b, r8b
0x180026722  jz      short loc_18002672A
0x180026724  mov     dword ptr [rbx], 3
0x18002672a  jmp     short $+2
0x18002672c  mov     eax, [rbx]
0x18002672e  test    eax, eax
0x180026730  jz      loc_1800267F0
0x180026736  dec     eax
0x180026738  cmp     eax, edi
0x18002673a  ja      loc_1800267FB
0x180026740  mov     eax, [rsp+0C8h+var_5C]
0x180026744  mov     [rbx+4], eax
0x180026747  mov     eax, [rsp+0C8h+var_58]
0x18002674b  mov     [rbx+8], eax
0x18002674e  mov     eax, [rsp+0C8h+var_54]
0x180026752  mov     [rbx+0Ch], eax
0x180026755  lea     rdi, [rbx+10h]
0x180026759  mov     r9, rdi
0x18002675c  mov     r8d, 307h
0x180026762  mov     rdx, r12
0x180026765  mov     rcx, [rsp+0C8h+Str]; Str
0x18002676d  call    SymGetEstimatedOriginalFilename
0x180026772  test    eax, eax
0x180026774  jz      short loc_1800267E9
0x180026776  test    r15, r15
0x180026779  jz      short loc_180026795
0x18002677b  mov     edx, dword ptr [rsp+0C8h+arg_60]; unsigned __int64
0x180026782  mov     r8, rdi; unsigned __int16 *
0x180026785  mov     rcx, r15; unsigned __int16 *
0x180026788  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002678d  test    eax, eax
0x18002678f  js      loc_180026838
0x180026795  cmp     dword ptr [rbx], 2
0x180026798  jnz     short loc_1800267C9
0x18002679a  mov     edx, 2Eh ; '.'; Ch
0x18002679f  mov     rcx, rdi; Str
0x1800267a2  call    cs:__imp_wcsrchr
0x1800267a8  test    rax, rax
0x1800267ab  jz      short loc_1800267B1
0x1800267ad  mov     [rax], r13w
0x1800267b1  lea     r8, aDbg; ".dbg"
0x1800267b8  mov     edx, 30Ch; unsigned __int64
0x1800267bd  mov     rcx, rdi; unsigned __int16 *
0x1800267c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800267c5  test    eax, eax
0x1800267c7  js      short loc_180026838
0x1800267c9  test    rsi, rsi
0x1800267cc  jz      short loc_1800267E5
0x1800267ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800267d2  inc     rax
0x1800267d5  cmp     [rdi+rax*2], r13w
0x1800267da  jnz     short loc_1800267D2
0x1800267dc  lea     eax, ds:12h[rax*2]
0x1800267e3  mov     [rsi], eax
0x1800267e5  xor     eax, eax
0x1800267e7  jmp     short loc_180026838
0x1800267e9  mov     eax, 80004005h
0x1800267ee  jmp     short loc_180026838
0x1800267f0  test    rsi, rsi
0x1800267f3  jz      short loc_1800267FB
0x1800267f5  mov     dword ptr [rsi], 4
0x1800267fb  test    r15, r15
0x1800267fe  jz      short loc_1800267E5
0x180026800  mov     r8d, dword ptr [rsp+0C8h+arg_60]
0x180026808  test    r8d, r8d
0x18002680b  jz      short loc_1800267E5
0x18002680d  mov     r9, r15
0x180026810  mov     rdx, r12
0x180026813  mov     rcx, [rsp+0C8h+Str]; Str
0x18002681b  call    SymGetEstimatedOriginalFilename
0x180026820  neg     eax
0x180026822  sbb     eax, eax
0x180026824  not     eax
0x180026826  and     eax, 80004005h
0x18002682b  jmp     short loc_180026838
0x18002682d  mov     ecx, 3E7h; unsigned int
0x180026832  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180026837  nop
0x180026838  add     rsp, 90h
0x18002683f  pop     r15
0x180026841  pop     r14
0x180026843  pop     r13
0x180026845  pop     r12
0x180026847  pop     rdi
0x180026848  pop     rsi
0x180026849  pop     rbx
0x18002684a  retn
0x18002984c  push    rbp
0x18002984e  sub     rsp, 60h
0x180029852  mov     rbp, rdx
0x180029855  mov     rax, [rcx]
0x180029858  xor     ecx, ecx
0x18002985a  cmp     dword ptr [rax], 0C0000006h
0x180029860  setz    cl
0x180029863  mov     eax, ecx
0x180029865  add     rsp, 60h
0x180029869  pop     rbp
0x18002986a  retn
```
