# GetLayerInfo(ushort const *,ulong,int *,int *,int *,int *,int *,int *,ulong *,_COLOR_SHIM_FLAGS *,ushort * *)

- ea: `0x18000bc0c`
- end: `0x18000bfdf`
- name: `?GetLayerInfo@@YAHPEBGKPEAH11111PEAKPEAU_COLOR_SHIM_FLAGS@@PEAPEAG@Z`
- size: `979`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, int *, int *, int *, int *, int *, int *, unsigned int *, struct _COLOR_SHIM_FLAGS *, SIZE_T dwBytes)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d6e8`
- `0x18000f4ac`

## callees

- `0x18000bc0c`
- `0x18000d058`
- `0x180017010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18000bd0b`
- `msvcrt!_wcsupr` at `0x18000bd0b`
- `KERNEL32!HeapFree` at `0x18000bfbb`
- `KERNEL32!HeapFree` at `0x18000bfbb`
- `KERNEL32!HeapAlloc` at `0x18000bcd3`
- `KERNEL32!HeapAlloc` at `0x18000bcd3`
- `KERNEL32!GetProcessHeap` at `0x18000bcc2`
- `KERNEL32!GetProcessHeap` at `0x18000bfad`
- `KERNEL32!GetProcessHeap` at `0x18000bcc2`
- `KERNEL32!GetProcessHeap` at `0x18000bfad`
- `KERNEL32!DecodePointer` at `0x18000bc8e`
- `KERNEL32!DecodePointer` at `0x18000bc8e`

## pseudocode

```c
__int64 __fastcall GetLayerInfo(
        const unsigned __int16 *a1,
        unsigned int a2,
        int *a3,
        int *a4,
        int *a5,
        int *a6,
        int *a7,
        int *a8,
        unsigned int *a9,
        struct _COLOR_SHIM_FLAGS *a10,
        SIZE_T dwBytes)
{
  int *v14; // rax
  struct _COLOR_SHIM_FLAGS *v15; // r13
  int *v16; // rax
  unsigned int (__fastcall *v17)(const unsigned __int16 *, wchar_t *, SIZE_T *, _QWORD); // rax
  unsigned int (__fastcall *v18)(const unsigned __int16 *, wchar_t *, SIZE_T *, _QWORD); // rdi
  unsigned int v19; // ebx
  HANDLE ProcessHeap; // rax
  wchar_t *v21; // rax
  wchar_t *v22; // r14
  int v23; // edi
  int v24; // edi
  unsigned int v25; // edi
  unsigned int v26; // edi
  unsigned int i; // ebx
  unsigned int v28; // r10d
  __int64 *v29; // r8
  int v30; // edx
  int v31; // r9d
  unsigned int j; // ecx
  int *v33; // r11
  int v34; // edx
  __int64 v35; // rcx
  int v36; // r8d
  int v37; // edi
  unsigned int *v38; // rdi
  __int64 k; // rbx
  bool v40; // zf
  int v41; // ecx
  HANDLE v42; // rax
  unsigned int v44; // [rsp+80h] [rbp+50h] BYREF
  int *v45; // [rsp+88h] [rbp+58h]

  v45 = a4;
  LODWORD(dwBytes) = 0;
  if ( !a3 || !a9 )
    return 0;
  v14 = a5;
  v15 = a10;
  *a9 = 0;
  *a3 = -1;
  *v14 = -1;
  v16 = a6;
  *(_DWORD *)v15 &= 0xFFFFFFFC;
  *a4 = -1;
  *v16 = -1;
  *a7 = -1;
  *a8 = -1;
  v17 = (unsigned int (__fastcall *)(const unsigned __int16 *, wchar_t *, SIZE_T *, _QWORD))DecodePointer(g_pfnGetPermLayers);
  v18 = v17;
  if ( v17 )
  {
    if ( v17(a1, 0, &dwBytes, a2) )
    {
      v19 = dwBytes;
      ProcessHeap = GetProcessHeap();
      v21 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v19);
      v22 = v21;
      if ( v21 )
      {
        if ( v18(a1, v21, &dwBytes, a2) )
        {
          _wcsupr(v22);
          v23 = 0;
          while ( 1 )
          {
            v44 = 0;
            MatchLayer(v22, &v44, &aWin95[38 * v23], 1 << v23);
            if ( v44 == 1 << v23 )
              break;
            if ( (unsigned int)++v23 >= 0xA )
              goto LABEL_12;
          }
          *a3 = v23;
LABEL_12:
          v24 = 0;
          while ( 1 )
          {
            v44 = 0;
            MatchLayer(v22, &v44, &a256color[38 * v24], 1 << v24);
            if ( v44 == 1 << v24 )
              break;
            if ( (unsigned int)++v24 >= 2 )
              goto LABEL_17;
          }
          *v45 = v24;
LABEL_17:
          v25 = 0;
          while ( 1 )
          {
            v44 = 0;
            MatchLayer(v22, &v44, (const unsigned __int16 *)qword_18001A930 + 38 * v25, 1 << v25);
            if ( v44 == 1 << v25 )
              break;
            if ( ++v25 >= 4 )
              goto LABEL_22;
          }
          *a7 = v25;
LABEL_22:
          v26 = 0;
          while ( 1 )
          {
            v44 = 0;
            MatchLayer(v22, &v44, (const unsigned __int16 *)qword_18001A6B0 + 38 * v26, 1 << v26);
            if ( v44 == 1 << v26 )
              break;
            if ( ++v26 >= 4 )
              goto LABEL_27;
          }
          *a8 = v26;
LABEL_27:
          v44 = 0;
          for ( i = 0; i < 3; ++i )
            MatchLayer(v22, &v44, &aHighdpiaware[54 * i], 1 << i);
          v28 = v44;
          v29 = qword_18001AA60;
          v30 = 0;
          do
          {
            v31 = 0;
            for ( j = 0; j < 3; ++j )
            {
              if ( !*((_DWORD *)v29 + j) )
                break;
              if ( (v44 & *((_DWORD *)v29 + j)) != 0 )
              {
                if ( v31 )
                  goto LABEL_43;
                v31 = 1;
              }
            }
            v29 = (__int64 *)((char *)v29 + 12);
            ++v30;
          }
          while ( !v30 );
          v33 = a5;
          v34 = 0;
          v35 = 0;
          *a5 = -1;
          do
          {
            v36 = dword_18001AA80[3 * v35];
            if ( (v28 & v36) == v36 && (!v34 || (v34 & v36) == v34) )
            {
              v34 = dword_18001AA80[3 * v35];
              *v33 = dword_18001AA84[3 * v35];
            }
            ++v35;
          }
          while ( v35 != 3 );
LABEL_43:
          v37 = 0;
          while ( 1 )
          {
            v44 = 0;
            MatchLayer(v22, &v44, &aPerprocesssyst[38 * v37], 1 << v37);
            if ( v44 == 1 << v37 )
              break;
            if ( (unsigned int)++v37 >= 2 )
              goto LABEL_48;
          }
          *a6 = v37;
LABEL_48:
          v38 = a9;
          for ( k = 0; k != 13; ++k )
            MatchLayer(v22, v38, &a640x480[54 * k], *((_DWORD *)qword_18001A190 + 27 * k));
          v44 = 0;
          MatchLayer(v22, &v44, L"TRANSFORMLEGACYCOLORMANAGED", 1u);
          v40 = v44 == 0;
          v44 = 0;
          *(_DWORD *)v15 &= ~1u;
          *(_DWORD *)v15 |= !v40;
          MatchLayer(v22, &v44, L"DISABLETRANSFORMLEGACYCOLORMANAGED", 1u);
          v41 = -(v44 != 0);
          *(_DWORD *)v15 &= ~2u;
          *(_DWORD *)v15 |= v41 & 2;
        }
        v42 = GetProcessHeap();
        HeapFree(v42, 0, v22);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000bc0c  mov     [rsp-38h+arg_0], rbx
0x18000bc11  mov     [rsp-38h+arg_18], r9
0x18000bc16  push    rbp
0x18000bc17  push    rsi
0x18000bc18  push    rdi
0x18000bc19  push    r12
0x18000bc1b  push    r13
0x18000bc1d  push    r14
0x18000bc1f  push    r15
0x18000bc21  mov     rbp, rsp
0x18000bc24  sub     rsp, 30h
0x18000bc28  mov     dword ptr [rbp+dwBytes], 0
0x18000bc32  mov     rsi, r8
0x18000bc35  mov     r15d, edx
0x18000bc38  mov     r12, rcx
0x18000bc3b  test    r8, r8
0x18000bc3e  jz      loc_18000BFC8
0x18000bc44  mov     rcx, [rbp+arg_40]
0x18000bc4b  test    rcx, rcx
0x18000bc4e  jz      loc_18000BFC8
0x18000bc54  mov     rax, [rbp+arg_20]
0x18000bc58  mov     r13, [rbp+arg_48]
0x18000bc5f  mov     dword ptr [rcx], 0
0x18000bc65  or      ecx, 0FFFFFFFFh
0x18000bc68  mov     [r8], ecx
0x18000bc6b  mov     [rax], ecx
0x18000bc6d  mov     rax, [rbp+arg_28]
0x18000bc71  and     dword ptr [r13+0], 0FFFFFFFCh
0x18000bc76  mov     [r9], ecx
0x18000bc79  mov     [rax], ecx
0x18000bc7b  mov     rax, [rbp+arg_30]
0x18000bc7f  mov     [rax], ecx
0x18000bc81  mov     rax, [rbp+arg_38]
0x18000bc85  mov     [rax], ecx
0x18000bc87  mov     rcx, cs:?g_pfnGetPermLayers@@3P6AHPEBGPEAGPEAKK@ZEA; Ptr
0x18000bc8e  call    cs:__imp_DecodePointer
0x18000bc94  mov     rdi, rax
0x18000bc97  test    rax, rax
0x18000bc9a  jz      loc_18000BFC1
0x18000bca0  mov     r9d, r15d
0x18000bca3  lea     r8, [rbp+dwBytes]
0x18000bcaa  xor     edx, edx
0x18000bcac  mov     rcx, r12
0x18000bcaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcb4  test    eax, eax
0x18000bcb6  jz      loc_18000BFC1
0x18000bcbc  mov     ebx, dword ptr [rbp+dwBytes]
0x18000bcc2  call    cs:__imp_GetProcessHeap
0x18000bcc8  mov     r8d, ebx; dwBytes
0x18000bccb  mov     edx, 8; dwFlags
0x18000bcd0  mov     rcx, rax; hHeap
0x18000bcd3  call    cs:__imp_HeapAlloc
0x18000bcd9  mov     r14, rax
0x18000bcdc  test    rax, rax
0x18000bcdf  jz      loc_18000BFC1
0x18000bce5  mov     rdx, rax
0x18000bce8  lea     r8, [rbp+dwBytes]
0x18000bcef  mov     rax, rdi
0x18000bcf2  mov     r9d, r15d
0x18000bcf5  mov     rcx, r12
0x18000bcf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcfd  xor     r15d, r15d
0x18000bd00  test    eax, eax
0x18000bd02  jz      loc_18000BFAD
0x18000bd08  mov     rcx, r14; String
0x18000bd0b  call    cs:__imp__wcsupr
0x18000bd11  mov     edi, r15d
0x18000bd14  lea     r12d, [r15+1]
0x18000bd18  mov     eax, edi
0x18000bd1a  lea     rdx, [rbp+arg_10]; unsigned int *
0x18000bd1e  imul    r8, rax, 4Ch ; 'L'
0x18000bd22  mov     ecx, edi
0x18000bd24  mov     [rbp+arg_10], r15d
0x18000bd28  lea     rax, aWin95; "WIN95"
0x18000bd2f  mov     ebx, r12d
0x18000bd32  shl     ebx, cl
0x18000bd34  add     r8, rax; unsigned __int16 *
0x18000bd37  mov     r9d, ebx; unsigned int
0x18000bd3a  mov     rcx, r14; unsigned __int16 *
0x18000bd3d  call    ?MatchLayer@@YAXPEBGPEAK0K@Z; MatchLayer(ushort const *,ulong *,ushort const *,ulong)
0x18000bd42  cmp     [rbp+arg_10], ebx
0x18000bd45  jz      short loc_18000BD51
0x18000bd47  add     edi, r12d
0x18000bd4a  cmp     edi, 0Ah
0x18000bd4d  jb      short loc_18000BD18
0x18000bd4f  jmp     short loc_18000BD53
0x18000bd51  mov     [rsi], edi
0x18000bd53  mov     edi, r15d
0x18000bd56  mov     eax, edi
0x18000bd58  lea     rdx, [rbp+arg_10]; unsigned int *
0x18000bd5c  imul    r8, rax, 4Ch ; 'L'
0x18000bd60  mov     ecx, edi
0x18000bd62  mov     [rbp+arg_10], r15d
0x18000bd66  lea     rax, a256color; "256COLOR"
0x18000bd6d  mov     ebx, r12d
0x18000bd70  shl     ebx, cl
0x18000bd72  add     r8, rax; unsigned __int16 *
0x18000bd75  mov     r9d, ebx; unsigned int
0x18000bd78  mov     rcx, r14; unsigned __int16 *
0x18000bd7b  call    ?MatchLayer@@YAXPEBGPEAK0K@Z; MatchLayer(ushort const *,ulong *,ushort const *,ulong)
0x18000bd80  cmp     [rbp+arg_10], ebx
0x18000bd83  jz      short loc_18000BD8F
0x18000bd85  add     edi, r12d
0x18000bd88  cmp     edi, 2
0x18000bd8b  jb      short loc_18000BD56
0x18000bd8d  jmp     short loc_18000BD95
0x18000bd8f  mov     rax, [rbp+arg_18]
0x18000bd93  mov     [rax], edi
0x18000bd95  mov     edi, r15d
0x18000bd98  mov     eax, edi
0x18000bd9a  lea     rdx, [rbp+arg_10]; unsigned int *
0x18000bd9e  imul    r8, rax, 4Ch ; 'L'
0x18000bda2  mov     ecx, edi
0x18000bda4  mov     [rbp+arg_10], r15d
0x18000bda8  lea     rax, qword_18001A930
0x18000bdaf  mov     ebx, r12d
0x18000bdb2  shl     ebx, cl
0x18000bdb4  add     r8, rax; unsigned __int16 *
0x18000bdb7  mov     r9d, ebx; unsigned int
0x18000bdba  mov     rcx, r14; unsigned __int16 *
0x18000bdbd  call    ?MatchLayer@@YAXPEBGPEAK0K@Z; MatchLayer(ushort const *,ulong *,ushort const *,ulong)
0x18000bdc2  cmp     [rbp+arg_10], ebx
0x18000bdc5  jz      short loc_18000BDD1
0x18000bdc7  add     edi, r12d
0x18000bdca  cmp     edi, 4
0x18000bdcd  jb      short loc_18000BD98
0x18000bdcf  jmp     short loc_18000BDD7
0x18000bdd1  mov     rax, [rbp+arg_30]
0x18000bdd5  mov     [rax], edi
0x18000bdd7  mov     edi, r15d
0x18000bdda  mov     eax, edi
0x18000bddc  lea     rdx, [rbp+arg_10]; unsigned int *
0x18000bde0  imul    r8, rax, 4Ch ; 'L'
0x18000bde4  mov     ecx, edi
0x18000bde6  mov     [rbp+arg_10], r15d
0x18000bdea  lea     rax, qword_18001A6B0
0x18000bdf1  mov     ebx, r12d
0x18000bdf4  shl     ebx, cl
0x18000bdf6  add     r8, rax; unsigned __int16 *
0x18000bdf9  mov     r9d, ebx; unsigned int
0x18000bdfc  mov     rcx, r14; unsigned __int16 *
0x18000bdff  call    ?MatchLayer@@YAXPEBGPEAK0K@Z; MatchLayer(ushort const *,ulong *,ushort const *,ulong)
0x18000be04  cmp     [rbp+arg_10], ebx
0x18000be07  jz      short loc_18000BE13
0x18000be09  add     edi, r12d
0x18000be0c  cmp     edi, 4
0x18000be0f  jb      short loc_18000BDDA
0x18000be11  jmp     short loc_18000BE19
0x18000be13  mov     rax, [rbp+arg_38]
0x18000be17  mov     [rax], edi
0x18000be19  mov     [rbp+arg_10], r15d
0x18000be1d  mov     ebx, r15d
0x18000be20  mov     eax, ebx
0x18000be22  lea     rdx, [rbp+arg_10]; unsigned int *
0x18000be26  imul    r8, rax, 6Ch ; 'l'
0x18000be2a  mov     ecx, ebx
0x18000be2c  lea     rax, aHighdpiaware; "HIGHDPIAWARE"
0x18000be33  mov     r9d, r12d
0x18000be36  add     r8, rax; unsigned __int16 *
0x18000be39  shl     r9d, cl; unsigned int
0x18000be3c  mov     rcx, r14; unsigned __int16 *
0x18000be3f  call    ?MatchLayer@@YAXPEBGPEAK0K@Z; MatchLayer(ushort const *,ulong *,ushort const *,ulong)
0x18000be44  add     ebx, r12d
0x18000be47  cmp     ebx, 3
0x18000be4a  jb      short loc_18000BE20
0x18000be4c  mov     r10d, [rbp+arg_10]
0x18000be50  lea     r8, qword_18001AA60
0x18000be57  mov     edx, r15d
0x18000be5a  mov     r9d, r15d
0x18000be5d  mov     ecx, r15d
0x18000be60  mov     eax, ecx
0x18000be62  lea     rsi, __ImageBase
0x18000be69  cmp     [r8+rax*4], r15d
0x18000be6d  jz      short loc_18000BE85
0x18000be6f  test    [r8+rax*4], r10d
0x18000be73  jz      short loc_18000BE7D
0x18000be75  test    r9d, r9d
0x18000be78  jnz     short loc_18000BEDD
0x18000be7a  mov     r9d, r12d
0x18000be7d  add     ecx, r12d
0x18000be80  cmp     ecx, 3
0x18000be83  jb      short loc_18000BE60
0x18000be85  add     r8, 0Ch
0x18000be89  add     edx, r12d
0x18000be8c  cmp     edx, r12d
0x18000be8f  jb      short loc_18000BE5A
0x18000be91  mov     r11, [rbp+arg_20]
0x18000be95  mov     edx, r15d
0x18000be98  mov     rcx, r15
0x18000be9b  mov     dword ptr [r11], 0FFFFFFFFh
0x18000bea2  lea     r9, [rcx+rcx*2]
0x18000bea6  mov     r8d, ds:rva dword_18001AA80[rsi+r9*4]
0x18000beae  mov     eax, r8d
0x18000beb1  and     eax, r10d
0x18000beb4  cmp     eax, r8d
0x18000beb7  jnz     short loc_18000BED4
0x18000beb9  test    edx, edx
0x18000bebb  jz      short loc_18000BEC6
0x18000bebd  mov     eax, r8d
0x18000bec0  and     eax, edx
0x18000bec2  cmp     eax, edx
0x18000bec4  jnz     short loc_18000BED4
0x18000bec6  mov     eax, ds:rva dword_18001AA84[rsi+r9*4]
0x18000bece  mov     edx, r8d
0x18000bed1  mov     [r11], eax
0x18000bed4  add     rcx, r12
0x18000bed7  cmp     rcx, 3
0x18000bedb  jnz     short loc_18000BEA2
0x18000bedd  mov     edi, r15d
0x18000bee0  mov     eax, edi
0x18000bee2  lea     rdx, [rbp+arg_10]; unsigned int *
0x18000bee6  imul    r8, rax, 4Ch ; 'L'
0x18000beea  mov     ecx, edi
0x18000beec  mov     [rbp+arg_10], r15d
0x18000bef0  lea     rax, aPerprocesssyst; "PERPROCESSSYSTEMDPIFORCEOFF"
0x18000bef7  mov     ebx, r12d
0x18000befa  shl     ebx, cl
0x18000befc  add     r8, rax; unsigned __int16 *
0x18000beff  mov     r9d, ebx; unsigned int
0x18000bf02  mov     rcx, r14; unsigned __int16 *
0x18000bf05  call    ?MatchLayer@@YAXPEBGPEAK0K@Z; MatchLayer(ushort const *,ulong *,ushort const *,ulong)
0x18000bf0a  cmp     [rbp+arg_10], ebx
0x18000bf0d  jz      short loc_18000BF19
0x18000bf0f  add     edi, r12d
0x18000bf12  cmp     edi, 2
0x18000bf15  jb      short loc_18000BEE0
0x18000bf17  jmp     short loc_18000BF1F
0x18000bf19  mov     rax, [rbp+arg_28]
0x18000bf1d  mov     [rax], edi
0x18000bf1f  mov     rdi, [rbp+arg_40]
0x18000bf26  mov     rbx, r15
0x18000bf29  imul    r9, rbx, 6Ch ; 'l'
0x18000bf2d  lea     r8, rva a640x480[rsi]; "640X480" ...
0x18000bf34  mov     rdx, rdi; unsigned int *
0x18000bf37  add     r8, r9; unsigned __int16 *
0x18000bf3a  mov     rcx, r14; unsigned __int16 *
0x18000bf3d  mov     r9d, [r9+rsi+1A190h]; unsigned int
0x18000bf45  call    ?MatchLayer@@YAXPEBGPEAK0K@Z; MatchLayer(ushort const *,ulong *,ushort const *,ulong)
0x18000bf4a  add     rbx, r12
0x18000bf4d  cmp     rbx, 0Dh
0x18000bf51  jnz     short loc_18000BF29
0x18000bf53  mov     r9d, r12d; unsigned int
0x18000bf56  mov     [rbp+arg_10], r15d
0x18000bf5a  lea     r8, aTransformlegac; "TRANSFORMLEGACYCOLORMANAGED"
0x18000bf61  mov     rcx, r14; unsigned __int16 *
0x18000bf64  lea     rdx, [rbp+arg_10]; unsigned int *
0x18000bf68  call    ?MatchLayer@@YAXPEBGPEAK0K@Z; MatchLayer(ushort const *,ulong *,ushort const *,ulong)
0x18000bf6d  cmp     [rbp+arg_10], r15d
0x18000bf71  lea     r8, aDisabletransfo; "DISABLETRANSFORMLEGACYCOLORMANAGED"
0x18000bf78  mov     eax, r15d
0x18000bf7b  mov     [rbp+arg_10], r15d
0x18000bf7f  setnz   al
0x18000bf82  lea     rdx, [rbp+arg_10]; unsigned int *
0x18000bf86  and     dword ptr [r13+0], 0FFFFFFFEh
0x18000bf8b  mov     r9d, r12d; unsigned int
0x18000bf8e  or      [r13+0], eax
0x18000bf92  mov     rcx, r14; unsigned __int16 *
0x18000bf95  call    ?MatchLayer@@YAXPEBGPEAK0K@Z; MatchLayer(ushort const *,ulong *,ushort const *,ulong)
0x18000bf9a  mov     eax, [rbp+arg_10]
0x18000bf9d  neg     eax
0x18000bf9f  sbb     ecx, ecx
0x18000bfa1  and     dword ptr [r13+0], 0FFFFFFFDh
0x18000bfa6  and     ecx, 2
0x18000bfa9  or      [r13+0], ecx
0x18000bfad  call    cs:__imp_GetProcessHeap
0x18000bfb3  mov     r8, r14; lpMem
0x18000bfb6  xor     edx, edx; dwFlags
0x18000bfb8  mov     rcx, rax; hHeap
0x18000bfbb  call    cs:__imp_HeapFree
0x18000bfc1  mov     eax, 1
0x18000bfc6  jmp     short loc_18000BFCA
0x18000bfc8  xor     eax, eax
0x18000bfca  mov     rbx, [rsp+30h+arg_0]
0x18000bfcf  add     rsp, 30h
0x18000bfd3  pop     r15
0x18000bfd5  pop     r14
0x18000bfd7  pop     r13
0x18000bfd9  pop     r12
0x18000bfdb  pop     rdi
0x18000bfdc  pop     rsi
0x18000bfdd  pop     rbp
0x18000bfde  retn
```
