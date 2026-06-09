# XPerf::Internal::CvDbgInfoFromImage2(ushort const *,void *,ulong,ulong,bool,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,ulong *,ulong *,ushort *,ulong,bool &,bool,EMBEDDED_PDB_INFORMATION &,bool &,XPerfCore::IErrorMessage *)

- ea: `0x18002a840`
- end: `0x18002b1af`
- name: `?CvDbgInfoFromImage2@Internal@XPerf@@YAJPEBGPEAXKK_NPEAKPEAT_CVDD@@3PEAUCODEVIEW_INFORMATION_1@@33PEAGKAEA_N2AEAUEMBEDDED_PDB_INFORMATION@@7PEAVIErrorMessage@XPerfCore@@@Z`
- size: `2415`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned __int16 *, void *, int, ULONG, unsigned int *, union _CVDD *, union _CVDD *, struct CODEVIEW_INFORMATION_1 *, struct CODEVIEW_INFORMATION_1 *, unsigned int *, wchar_t *Str, unsigned __int16 *, _BYTE *, bool *, struct EMBEDDED_PDB_INFORMATION *, struct EMBEDDED_PDB_INFORMATION *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027e60`
- `0x180082a38`

## callees

- `0x18000829c`
- `0x18002a840`
- `0x18002b1b8`
- `0x18002b460`
- `0x18002b9a0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18002adf7`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18002af58`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18002adf7`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18002af58`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002adc1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002af29`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002adc1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002af29`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002ad65`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002ad76`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002aed1`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002aee2`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002b081`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002ad65`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002ad76`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002aed1`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002aee2`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002b081`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002adde`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002af43`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002adde`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002af43`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002aa1f`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002aa40`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002aa65`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002aad6`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002ab58`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002aa1f`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002aa40`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002aa65`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002aad6`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002ab58`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall XPerf::Internal::CvDbgInfoFromImage2(
        LPCWSTR lpwstrFilename,
        unsigned __int16 *a2,
        void *a3,
        int a4,
        ULONG a5,
        unsigned int *a6,
        union _CVDD *a7,
        union _CVDD *a8,
        struct CODEVIEW_INFORMATION_1 *a9,
        struct CODEVIEW_INFORMATION_1 *a10,
        unsigned int *a11,
        wchar_t *Str,
        unsigned __int16 *a13,
        _BYTE *a14,
        bool *a15,
        struct EMBEDDED_PDB_INFORMATION *a16,
        struct EMBEDDED_PDB_INFORMATION *a17,
        bool *a18)
{
  struct EMBEDDED_PDB_INFORMATION *v20; // r13
  wchar_t *v21; // rbx
  __int64 v22; // rax
  unsigned int v23; // ecx
  struct _IMAGE_NT_HEADERS64 *v24; // r14
  WORD Magic; // ax
  DWORD CheckSum; // eax
  DWORD TimeDateStamp; // r10d
  unsigned int SizeOfImage; // ecx
  __int64 result; // rax
  WORD v30; // ax
  PVOID v31; // r12
  int v32; // r15d
  __int64 v33; // rcx
  BOOL v34; // eax
  _DWORD *v35; // rax
  bool v36; // r12
  char v37; // r14
  _BYTE *v38; // rax
  union _CVDD *v39; // r9
  unsigned int *v40; // r14
  ULONG v41; // r8d
  ULONG v42; // edx
  __int64 v43; // rcx
  const wchar_t *v44; // r12
  __int64 v45; // r15
  int OriginalFilename; // r13d
  wchar_t *v47; // rdi
  wchar_t *v48; // rax
  __int64 v49; // r14
  __int64 v50; // rdi
  __int64 v51; // rdi
  __int64 v52; // rcx
  __int64 v53; // rax
  const wchar_t *v54; // rdx
  wchar_t v55; // r8
  wchar_t *v56; // rax
  int v57; // ebx
  unsigned __int64 v58; // r15
  int v59; // r12d
  wchar_t *v60; // rdi
  wchar_t *v61; // rax
  __int64 v62; // r14
  unsigned __int64 v63; // rcx
  int v64; // esi
  __int64 v65; // rdi
  WCHAR v66; // ax
  wchar_t *v67; // rax
  bool *v68; // rcx
  __int64 v69; // rax
  wchar_t *v70; // rcx
  WCHAR v71; // dx
  wchar_t *v72; // rax
  wchar_t *v73; // rax
  __int64 v74; // rax
  const wchar_t *v75; // rdx
  const wchar_t *v76; // rdx
  __int64 v77; // rcx
  wchar_t *v78; // r9
  wchar_t v79; // ax
  wchar_t *v80; // rax
  bool v81; // [rsp+20h] [rbp-B8h]
  bool v82; // [rsp+50h] [rbp-88h]
  unsigned int v83[2]; // [rsp+70h] [rbp-68h] BYREF
  ULONG v84; // [rsp+78h] [rbp-60h] BYREF
  ULONG Size; // [rsp+7Ch] [rbp-5Ch] BYREF
  ULONG v86[2]; // [rsp+80h] [rbp-58h] BYREF
  DWORD v87; // [rsp+88h] [rbp-50h]
  DWORD v88; // [rsp+8Ch] [rbp-4Ch]
  unsigned int v89; // [rsp+90h] [rbp-48h]
  DWORD v90; // [rsp+94h] [rbp-44h]
  DWORD v91; // [rsp+98h] [rbp-40h]
  unsigned int v92; // [rsp+9Ch] [rbp-3Ch]
  signed __int64 v93; // [rsp+A0h] [rbp-38h]
  unsigned int v94; // [rsp+F0h] [rbp+18h]

  v94 = (unsigned int)a3;
  v20 = a16;
  *(_OWORD *)a16 = 0;
  *((_QWORD *)v20 + 2) = 0;
  *(_BYTE *)a17 = 0;
  v21 = Str;
  if ( Str )
    *Str = 0;
  if ( !a2 )
    goto LABEL_163;
  if ( (unsigned int)a3 <= 0x40 )
    goto LABEL_163;
  if ( *a2 != 23117 )
    goto LABEL_163;
  v22 = *((unsigned int *)a2 + 15);
  if ( (v22 & 3) != 0 )
    goto LABEL_163;
  if ( (unsigned int)v22 >= (unsigned int)a3 )
    goto LABEL_163;
  v23 = (_DWORD)a3 - v22;
  if ( (unsigned int)((_DWORD)a3 - v22) < 0x1B )
    goto LABEL_163;
  v24 = (struct _IMAGE_NT_HEADERS64 *)((char *)a2 + v22);
  if ( *(_DWORD *)((char *)a2 + v22) != 17744 )
    goto LABEL_163;
  Magic = v24->OptionalHeader.Magic;
  if ( Magic == 267 )
  {
    if ( v23 <= 0xF8 )
      goto LABEL_163;
  }
  else if ( Magic != 523 || v23 <= 0x108 )
  {
    goto LABEL_163;
  }
  if ( v24 )
  {
    CheckSum = v24->OptionalHeader.CheckSum;
    v87 = CheckSum;
    v90 = CheckSum;
    TimeDateStamp = v24->FileHeader.TimeDateStamp;
    v88 = TimeDateStamp;
    v91 = TimeDateStamp;
    SizeOfImage = v24->OptionalHeader.SizeOfImage;
    v89 = SizeOfImage;
    v92 = SizeOfImage;
    if ( a4 && CheckSum != a4 )
    {
      if ( a18 )
        (*(void (__fastcall **)(bool *, const wchar_t *, _QWORD))(*(_QWORD *)a18 + 8LL))(
          a18,
          L"Invalid image header checksum.",
          0);
      return ATL::AtlHresultFromWin32(0xDu);
    }
    if ( a10 )
      *(_DWORD *)a10 = TimeDateStamp;
    if ( a11 )
      *a11 = SizeOfImage;
    v30 = v24->OptionalHeader.Magic;
    if ( v30 == 267 )
    {
      *a14 = 0;
    }
    else
    {
      if ( v30 != 523 )
        return 2147549183LL;
      *a14 = 1;
    }
    Size = 0;
    v84 = 0;
    a5 = 0;
    *(_QWORD *)v83 = RtlImageDirectoryEntryToData(a2, (BOOLEAN)a15, 0, &Size);
    v31 = RtlImageDirectoryEntryToData(a2, (BOOLEAN)a15, 1u, &v84);
    v32 = 2;
    if ( RtlImageDirectoryEntryToData(a2, (BOOLEAN)a15, 2u, &a5) && a5 && !v31 && !v84 && !*(_QWORD *)v83 && !Size )
    {
      v33 = *((unsigned int *)a2 + 15);
      if ( ((*(unsigned __int16 *)((char *)a2 + v33 + 24) - 267) & 0xFEFF) != 0 )
      {
        v34 = 0;
      }
      else
      {
        if ( *(_DWORD *)((char *)a2 + v33 + 40) )
          goto LABEL_44;
        v35 = RtlImageDirectoryEntryToData(a2, (BOOLEAN)a15, 0xEu, &a5);
        if ( a5 != 72 || !v35 )
          goto LABEL_46;
        v34 = *v35 != 72;
      }
      if ( v34 )
        goto LABEL_46;
    }
LABEL_44:
    a5 = v24->FileHeader.Characteristics & 0x200;
    v36 = (unsigned int)SymCommonTlbImpManagedDll(a2, v24) == 1;
    v86[0] = 0;
    v37 = (char)a15;
    v38 = RtlImageDirectoryEntryToData(a2, (BOOLEAN)a15, 6u, v86);
    if ( !v38 )
    {
      if ( !a5 )
      {
LABEL_46:
        *a6 = 1;
        v39 = a7;
        *(_DWORD *)a7 = 0;
        v32 = 0;
        goto LABEL_70;
      }
      *a6 = 1;
      v39 = a7;
      *(_DWORD *)a7 = 2;
LABEL_70:
      if ( v32 == 2 )
        goto LABEL_73;
      if ( v32 )
      {
        if ( v32 == 1 )
        {
LABEL_73:
          *((_DWORD *)v39 + 1) = v87;
          *((_DWORD *)v39 + 2) = v88;
          *((_DWORD *)v39 + 3) = v89;
          v44 = (const wchar_t *)((char *)v39 + 16);
          v45 = 775;
          OriginalFilename = SymGetOriginalFilename(lpwstrFilename, (HMODULE)a2);
          v47 = wcsrchr(lpwstrFilename, 0x2Fu);
          v48 = wcsrchr(lpwstrFilename, 0x5Cu);
          if ( v47 > v48 )
            v48 = v47;
          if ( v48 )
            lpwstrFilename = v48 + 1;
          v49 = -1;
          if ( OriginalFilename )
          {
            v50 = -1;
            do
              ++v50;
            while ( v44[v50] );
            if ( ((unsigned int)_o__wcsnicmp(v44, lpwstrFilename) || lpwstrFilename[v50] != 46)
              && wcschr(v44, 0x2Eu)
              && wcscspn(v44, L"<>:\"/\\|,?%&*") == v50 )
            {
              v51 = 2147483646;
LABEL_85:
              if ( v21 )
              {
                v52 = (unsigned int)a13;
                if ( (_DWORD)a13 && (unsigned int)a13 <= 0x7FFFFFFFuLL )
                {
                  v53 = 2147483646;
                  v54 = v44;
                  do
                  {
                    if ( !v53 )
                      break;
                    v55 = *v54;
                    if ( !*v54 )
                      break;
                    ++v54;
                    *v21++ = v55;
                    --v53;
                    --v52;
                  }
                  while ( v52 );
                  v56 = v21 - 1;
                  if ( v52 )
                    v56 = v21;
                  *v56 = 0;
                  v57 = -2147024774;
                  result = 2147942522LL;
                  if ( v52 )
                    result = 0;
                }
                else
                {
                  result = 2147942487LL;
                  if ( (_DWORD)a13 )
                    *v21 = 0;
                  v57 = -2147024774;
                }
                if ( (int)result < 0 )
                  return result;
              }
              else
              {
                v57 = -2147024774;
              }
              if ( *(_DWORD *)a7 == 2 )
              {
                v73 = wcsrchr(v44, 0x2Eu);
                if ( v73 )
                  *v73 = 0;
                v74 = 780;
                v75 = v44;
                do
                {
                  if ( !*v75 )
                    break;
                  ++v75;
                  --v74;
                }
                while ( v74 );
                if ( v74 )
                {
                  v76 = L".dbg";
                  v77 = v74;
                  v78 = (wchar_t *)&v44[780 - v74];
                  do
                  {
                    if ( !v51 )
                      break;
                    v79 = *v76;
                    if ( !*v76 )
                      break;
                    ++v76;
                    *v78++ = v79;
                    --v51;
                    --v77;
                  }
                  while ( v77 );
                  v80 = v78 - 1;
                  if ( v77 )
                    v80 = v78;
                  *v80 = 0;
                  if ( v77 )
                    v57 = 0;
                }
                else
                {
                  v57 = -2147024809;
                }
                if ( v57 < 0 )
                  return (unsigned int)v57;
              }
              if ( a8 )
              {
                do
                  ++v49;
                while ( v44[v49] );
                *(_DWORD *)a8 = 2 * v49 + 18;
              }
              return 0;
            }
          }
          v51 = 2147483646;
          v69 = 2147483646;
          v70 = (wchar_t *)v44;
          do
          {
            if ( !v69 )
              break;
            v71 = *lpwstrFilename;
            if ( !*lpwstrFilename )
              break;
            ++lpwstrFilename;
            *v70++ = v71;
            --v69;
            --v45;
          }
          while ( v45 );
          v72 = v70 - 1;
          if ( v45 )
            v72 = v70;
          *v72 = 0;
          if ( v45 )
            goto LABEL_85;
          v68 = a18;
          if ( a18 )
            goto LABEL_133;
          return 2147500037LL;
        }
      }
      else if ( a8 )
      {
        *(_DWORD *)a8 = 4;
      }
      if ( !v21 )
        return 0;
      v58 = (unsigned int)a13;
      if ( !(_DWORD)a13 )
        return 0;
      v59 = SymGetOriginalFilename(lpwstrFilename, (HMODULE)a2);
      v60 = wcsrchr(lpwstrFilename, 0x2Fu);
      v61 = wcsrchr(lpwstrFilename, 0x5Cu);
      if ( v60 > v61 )
        v61 = v60;
      if ( v61 )
        lpwstrFilename = v61 + 1;
      if ( v59 )
      {
        v62 = -1;
        do
          ++v62;
        while ( v21[v62] );
        if ( ((unsigned int)_o__wcsnicmp(v21, lpwstrFilename) || lpwstrFilename[v62] != 46)
          && wcschr(v21, 0x2Eu)
          && wcscspn(v21, L"<>:\"/\\|,?%&*") == v62 )
        {
          return 0;
        }
      }
      v63 = v58;
      if ( v58 <= 0x7FFFFFFF )
      {
        v65 = 2147483646;
        do
        {
          if ( !v65 )
            break;
          v66 = *lpwstrFilename;
          if ( !*lpwstrFilename )
            break;
          ++lpwstrFilename;
          *v21++ = v66;
          --v65;
          --v63;
        }
        while ( v63 );
        v67 = v21 - 1;
        if ( v63 )
          v67 = v21;
        *v67 = 0;
        v64 = -2147024774;
        if ( v63 )
          v64 = 0;
      }
      else
      {
        v64 = -2147024809;
        *v21 = 0;
      }
      if ( v64 >= 0 )
        return 0;
      v68 = a18;
      if ( a18 )
LABEL_133:
        (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)v68 + 8LL))(
          v68,
          L"Failed to obtain the original file name.");
      return 2147500037LL;
    }
    v93 = v38 - (_BYTE *)a2;
    v83[0] = -1;
    v82 = v37;
    v40 = a6;
    result = CvInfoFromDbgDir(
               a2,
               v94,
               v86[0],
               (int)v38 - (int)a2,
               v81,
               v83,
               a6,
               a7,
               (unsigned int *)a8,
               a9,
               v82,
               v20,
               (bool *)a17);
    if ( (int)result < 0 )
      return result;
    v41 = *v40;
    if ( *v40 <= 1 )
    {
      v39 = a7;
    }
    else
    {
      if ( v36 )
      {
        if ( a18 )
          (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(
            a18,
            L"Multiple CvDbg entries in IL-only image.");
        return ATL::AtlHresultFromWin32(0xC1u);
      }
      v42 = 0;
      v39 = a7;
      while ( 1 )
      {
        v86[1] = v42;
        if ( v42 >= v41 )
          break;
        v43 = 1576LL * v42;
        if ( *(_DWORD *)((char *)v39 + v43) == 1396986706 && v83[0] != -1 && v42 != v83[0] )
        {
          *(_DWORD *)((char *)v39 + v43) = 3;
          v41 = *v40;
        }
        ++v42;
      }
    }
    if ( *(_DWORD *)v39 == 1 )
    {
      v32 = 1;
    }
    else if ( *(_DWORD *)v39 || !a5 )
    {
      if ( v36 )
      {
        *(_DWORD *)v39 = 3;
        v32 = 3;
      }
      else
      {
        v32 = *(_DWORD *)v39;
      }
    }
    else
    {
      *(_DWORD *)v39 = 2;
    }
    goto LABEL_70;
  }
LABEL_163:
  if ( a18 )
    (*(void (__fastcall **)(bool *, const wchar_t *, _QWORD))(*(_QWORD *)a18 + 8LL))(
      a18,
      L"Invalid executable format.",
      0);
  return ATL::AtlHresultFromWin32(0xC1u);
}

```

## disassembly

```asm
0x18002a840  mov     [rsp+arg_0], rbx
0x18002a845  mov     [rsp+arg_8], rsi
0x18002a84a  mov     [rsp+arg_10], r8d
0x18002a84f  push    rdi
0x18002a850  push    r12
0x18002a852  push    r13
0x18002a854  push    r14
0x18002a856  push    r15
0x18002a858  sub     rsp, 0B0h
0x18002a85f  mov     r10d, r8d
0x18002a862  mov     rdi, rdx
0x18002a865  mov     rsi, rcx
0x18002a868  xorps   xmm0, xmm0
0x18002a86b  xor     eax, eax
0x18002a86d  mov     r13, [rsp+0D8h+arg_78]
0x18002a875  movups  xmmword ptr [r13+0], xmm0
0x18002a87a  mov     [r13+10h], rax
0x18002a87e  mov     rax, [rsp+0D8h+arg_80]
0x18002a886  mov     byte ptr [rax], 0
0x18002a889  mov     rbx, [rsp+0D8h+Str]
0x18002a891  xor     r8d, r8d
0x18002a894  test    rbx, rbx
0x18002a897  jz      short loc_18002A89D
0x18002a899  mov     [rbx], r8w
0x18002a89d  test    rdi, rdi
0x18002a8a0  jz      loc_18002B13B
0x18002a8a6  cmp     r10d, 40h ; '@'
0x18002a8aa  jbe     loc_18002B13B
0x18002a8b0  mov     eax, 5A4Dh
0x18002a8b5  cmp     [rdx], ax
0x18002a8b8  jnz     loc_18002B13B
0x18002a8be  mov     eax, [rdx+3Ch]
0x18002a8c1  test    al, 3
0x18002a8c3  jnz     loc_18002B13B
0x18002a8c9  cmp     eax, r10d
0x18002a8cc  jnb     loc_18002B13B
0x18002a8d2  mov     ecx, r10d
0x18002a8d5  sub     ecx, eax
0x18002a8d7  cmp     ecx, 1Bh
0x18002a8da  jb      loc_18002B13B
0x18002a8e0  lea     r14, [rdx+rax]
0x18002a8e4  cmp     dword ptr [r14], 4550h
0x18002a8eb  jnz     loc_18002B13B
0x18002a8f1  movzx   eax, word ptr [r14+18h]
0x18002a8f6  mov     r11d, 10Bh
0x18002a8fc  cmp     ax, r11w
0x18002a900  jz      short loc_18002A91E
0x18002a902  mov     edx, 20Bh
0x18002a907  cmp     ax, dx
0x18002a90a  jnz     loc_18002B13B
0x18002a910  cmp     ecx, 108h
0x18002a916  jbe     loc_18002B13B
0x18002a91c  jmp     short loc_18002A92F
0x18002a91e  cmp     ecx, 0F8h
0x18002a924  jbe     loc_18002B13B
0x18002a92a  mov     edx, 20Bh
0x18002a92f  test    r14, r14
0x18002a932  jz      loc_18002B13B
0x18002a938  mov     eax, [r14+58h]
0x18002a93c  mov     [rsp+0D8h+var_50], eax
0x18002a943  mov     [rsp+0D8h+var_44], eax
0x18002a94a  mov     r10d, [r14+8]
0x18002a94e  mov     [rsp+0D8h+var_4C], r10d
0x18002a956  mov     [rsp+0D8h+var_40], r10d
0x18002a95e  mov     ecx, [r14+50h]
0x18002a962  mov     [rsp+0D8h+var_48], ecx
0x18002a969  mov     [rsp+0D8h+var_3C], ecx
0x18002a970  test    r9d, r9d
0x18002a973  jz      short loc_18002A9A9
0x18002a975  cmp     eax, r9d
0x18002a978  jz      short loc_18002A9A9
0x18002a97a  mov     rcx, [rsp+0D8h+arg_88]
0x18002a982  test    rcx, rcx
0x18002a985  jz      short loc_18002A99A
0x18002a987  mov     rax, [rcx]
0x18002a98a  lea     rdx, aInvalidImageHe; "Invalid image header checksum."
0x18002a991  mov     rax, [rax+8]
0x18002a995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a99a  mov     ecx, 0Dh; unsigned int
0x18002a99f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002a9a4  jmp     loc_18002B192
0x18002a9a9  mov     rax, [rsp+0D8h+arg_48]
0x18002a9b1  test    rax, rax
0x18002a9b4  jz      short loc_18002A9B9
0x18002a9b6  mov     [rax], r10d
0x18002a9b9  mov     rax, [rsp+0D8h+arg_50]
0x18002a9c1  test    rax, rax
0x18002a9c4  jz      short loc_18002A9C8
0x18002a9c6  mov     [rax], ecx
0x18002a9c8  movzx   eax, word ptr [r14+18h]
0x18002a9cd  cmp     ax, r11w
0x18002a9d1  jz      short loc_18002A9EF
0x18002a9d3  cmp     ax, dx
0x18002a9d6  jz      short loc_18002A9E2
0x18002a9d8  mov     eax, 8000FFFFh
0x18002a9dd  jmp     loc_18002B192
0x18002a9e2  mov     rax, [rsp+0D8h+arg_68]
0x18002a9ea  mov     byte ptr [rax], 1
0x18002a9ed  jmp     short loc_18002A9FA
0x18002a9ef  mov     rax, [rsp+0D8h+arg_68]
0x18002a9f7  mov     byte ptr [rax], 0
0x18002a9fa  mov     [rsp+0D8h+Size], r8d
0x18002a9ff  mov     [rsp+0D8h+var_60], r8d
0x18002aa04  mov     [rsp+0D8h+arg_20], r8d
0x18002aa0c  xor     r8d, r8d; Directory
0x18002aa0f  lea     r9, [rsp+0D8h+Size]; Size
0x18002aa14  movzx   edx, byte ptr [rsp+0D8h+arg_70]; MappedAsImage
0x18002aa1c  mov     rcx, rdi; BaseAddress
0x18002aa1f  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002aa25  mov     qword ptr [rsp+0D8h+var_68], rax
0x18002aa2a  mov     r8d, 1; Directory
0x18002aa30  lea     r9, [rsp+0D8h+var_60]; Size
0x18002aa35  movzx   edx, byte ptr [rsp+0D8h+arg_70]; MappedAsImage
0x18002aa3d  mov     rcx, rdi; BaseAddress
0x18002aa40  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002aa46  mov     r12, rax
0x18002aa49  mov     r15d, 2
0x18002aa4f  mov     r8d, r15d; Directory
0x18002aa52  lea     r9, [rsp+0D8h+arg_20]; Size
0x18002aa5a  movzx   edx, byte ptr [rsp+0D8h+arg_70]; MappedAsImage
0x18002aa62  mov     rcx, rdi; BaseAddress
0x18002aa65  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002aa6b  test    rax, rax
0x18002aa6e  jz      loc_18002AAFC
0x18002aa74  cmp     [rsp+0D8h+arg_20], 0
0x18002aa7c  jz      short loc_18002AAFC
0x18002aa7e  test    r12, r12
0x18002aa81  jnz     short loc_18002AAFC
0x18002aa83  cmp     [rsp+0D8h+var_60], r12d
0x18002aa88  jnz     short loc_18002AAFC
0x18002aa8a  cmp     qword ptr [rsp+0D8h+var_68], r12
0x18002aa8f  jnz     short loc_18002AAFC
0x18002aa91  cmp     [rsp+0D8h+Size], r12d
0x18002aa96  jnz     short loc_18002AAFC
0x18002aa98  mov     ecx, [rdi+3Ch]
0x18002aa9b  movzx   eax, word ptr [rcx+rdi+18h]
0x18002aaa0  mov     edx, 10Bh
0x18002aaa5  sub     ax, dx
0x18002aaa8  mov     edx, 0FEFFh
0x18002aaad  test    dx, ax
0x18002aab0  jz      short loc_18002AAB6
0x18002aab2  xor     eax, eax
0x18002aab4  jmp     short loc_18002AAF6
0x18002aab6  cmp     dword ptr [rcx+rdi+28h], 0
0x18002aabb  jnz     short loc_18002AAFC
0x18002aabd  mov     r8d, 0Eh; Directory
0x18002aac3  lea     r9, [rsp+0D8h+arg_20]; Size
0x18002aacb  movzx   edx, byte ptr [rsp+0D8h+arg_70]; MappedAsImage
0x18002aad3  mov     rcx, rdi; BaseAddress
0x18002aad6  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002aadc  mov     rcx, rax
0x18002aadf  cmp     [rsp+0D8h+arg_20], 48h ; 'H'
0x18002aae7  jnz     short loc_18002AAFA
0x18002aae9  test    rax, rax
0x18002aaec  jz      short loc_18002AAFA
0x18002aaee  xor     eax, eax
0x18002aaf0  cmp     dword ptr [rcx], 48h ; 'H'
0x18002aaf3  setnz   al
0x18002aaf6  test    eax, eax
0x18002aaf8  jz      short loc_18002AAFC
0x18002aafa  jmp     short loc_18002AB6F
0x18002aafc  movzx   eax, word ptr [r14+16h]
0x18002ab01  and     eax, 200h
0x18002ab06  mov     [rsp+0D8h+arg_20], eax
0x18002ab0d  movzx   r8d, byte ptr [rsp+0D8h+arg_70]
0x18002ab16  mov     rdx, r14; NtHeader
0x18002ab19  mov     rcx, rdi; BaseAddress
0x18002ab1c  call    SymCommonTlbImpManagedDll
0x18002ab21  cmp     eax, 1
0x18002ab24  jnz     short loc_18002AB2C
0x18002ab26  movzx   r12d, al
0x18002ab2a  jmp     short loc_18002AB2F
0x18002ab2c  xor     r12b, r12b
0x18002ab2f  mov     [rsp+0D8h+var_58], 0
0x18002ab3a  mov     r8d, 6; Directory
0x18002ab40  lea     r9, [rsp+0D8h+var_58]; Size
0x18002ab48  movzx   r14d, byte ptr [rsp+0D8h+arg_70]
0x18002ab51  movzx   edx, r14b; MappedAsImage
0x18002ab55  mov     rcx, rdi; BaseAddress
0x18002ab58  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002ab5e  mov     r9, rax
0x18002ab61  test    rax, rax
0x18002ab64  jnz     short loc_18002ABB4
0x18002ab66  cmp     [rsp+0D8h+arg_20], eax
0x18002ab6d  jnz     short loc_18002AB93
0x18002ab6f  mov     rax, [rsp+0D8h+arg_28]
0x18002ab77  mov     dword ptr [rax], 1
0x18002ab7d  xor     r13d, r13d
0x18002ab80  mov     r9, [rsp+0D8h+arg_30]
0x18002ab88  mov     [r9], r13d
0x18002ab8b  mov     r15d, r13d
0x18002ab8e  jmp     loc_18002AD05
0x18002ab93  mov     rax, [rsp+0D8h+arg_28]
0x18002ab9b  mov     dword ptr [rax], 1
0x18002aba1  mov     r9, [rsp+0D8h+arg_30]
0x18002aba9  mov     [r9], r15d
0x18002abac  xor     r13d, r13d
0x18002abaf  jmp     loc_18002AD05
0x18002abb4  sub     r9, rdi; unsigned int
0x18002abb7  mov     [rsp+0D8h+var_38], r9
0x18002abbf  mov     [rsp+0D8h+var_68], 0FFFFFFFFh
0x18002abc7  mov     rax, [rsp+0D8h+arg_80]
0x18002abcf  mov     [rsp+0D8h+var_78], rax; bool *
0x18002abd4  mov     [rsp+0D8h+var_80], r13; struct EMBEDDED_PDB_INFORMATION *
0x18002abd9  mov     [rsp+0D8h+var_88], r14b; bool
0x18002abde  mov     rax, [rsp+0D8h+arg_40]
0x18002abe6  mov     [rsp+0D8h+var_90], rax; struct CODEVIEW_INFORMATION_1 *
0x18002abeb  mov     rax, [rsp+0D8h+arg_38]
0x18002abf3  mov     [rsp+0D8h+var_98], rax; unsigned int *
0x18002abf8  mov     rax, [rsp+0D8h+arg_30]
0x18002ac00  mov     [rsp+0D8h+var_A0], rax; union _CVDD *
0x18002ac05  mov     r14, [rsp+0D8h+arg_28]
0x18002ac0d  mov     [rsp+0D8h+var_A8], r14; unsigned int *
0x18002ac12  lea     rax, [rsp+0D8h+var_68]
0x18002ac17  mov     [rsp+0D8h+var_B0], rax; unsigned int *
0x18002ac1c  mov     r8d, [rsp+0D8h+var_58]; unsigned int
0x18002ac24  mov     edx, [rsp+0D8h+arg_10]; unsigned int
0x18002ac2b  mov     rcx, rdi; void *
0x18002ac2e  call    ?CvInfoFromDbgDir@@YAJPEAXKKK_NPEAK2PEAT_CVDD@@2PEAUCODEVIEW_INFORMATION_1@@1AEAUEMBEDDED_PDB_INFORMATION@@AEA_N@Z; CvInfoFromDbgDir(void *,ulong,ulong,ulong,bool,ulong *,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,bool,EMBEDDED_PDB_INFORMATION &,bool &)
0x18002ac33  test    eax, eax
0x18002ac35  js      loc_18002B192
0x18002ac3b  mov     r8d, [r14]
0x18002ac3e  cmp     r8d, 1
0x18002ac42  jbe     short loc_18002ACC1
0x18002ac44  test    r12b, r12b
0x18002ac47  jz      short loc_18002AC78
0x18002ac49  mov     rcx, [rsp+0D8h+arg_88]
0x18002ac51  test    rcx, rcx
0x18002ac54  jz      short loc_18002AC69
0x18002ac56  mov     rax, [rcx]
0x18002ac59  lea     rdx, aMultipleCvdbgE; "Multiple CvDbg entries in IL-only image"...
0x18002ac60  mov     rax, [rax+8]
0x18002ac64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac69  mov     ecx, 0C1h; unsigned int
0x18002ac6e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002ac73  jmp     loc_18002B192
0x18002ac78  xor     r13d, r13d
0x18002ac7b  mov     edx, r13d
0x18002ac7e  mov     r9, [rsp+0D8h+arg_30]
0x18002ac86  mov     [rsp+0D8h+var_54], edx
0x18002ac8d  cmp     edx, r8d
0x18002ac90  jnb     short loc_18002ACCC
0x18002ac92  mov     eax, edx
0x18002ac94  imul    rcx, rax, 628h
0x18002ac9b  cmp     dword ptr [rcx+r9], 53445352h
0x18002aca3  jnz     short loc_18002ACBD
0x18002aca5  cmp     [rsp+0D8h+var_68], 0FFFFFFFFh
0x18002acaa  jz      short loc_18002ACBD
0x18002acac  cmp     edx, [rsp+0D8h+var_68]
0x18002acb0  jz      short loc_18002ACBD
0x18002acb2  mov     dword ptr [rcx+r9], 3
0x18002acba  mov     r8d, [r14]
0x18002acbd  inc     edx
0x18002acbf  jmp     short loc_18002AC86
0x18002acc1  xor     r13d, r13d
0x18002acc4  mov     r9, [rsp+0D8h+arg_30]
0x18002accc  mov     eax, [r9]
0x18002accf  cmp     eax, 1
0x18002acd2  jz      short loc_18002ACFF
0x18002acd4  test    eax, eax
0x18002acd6  jnz     short loc_18002ACE6
0x18002acd8  cmp     [rsp+0D8h+arg_20], eax
0x18002acdf  jz      short loc_18002ACE6
0x18002ace1  mov     [r9], r15d
0x18002ace4  jmp     short loc_18002AD05
0x18002ace6  test    r12b, r12b
0x18002ace9  jz      short loc_18002ACFA
0x18002aceb  mov     dword ptr [r9], 3
0x18002acf2  mov     r15d, 3
0x18002acf8  jmp     short loc_18002ACFD
0x18002acfa  mov     r15d, eax
0x18002acfd  jmp     short loc_18002AD05
0x18002acff  mov     r15d, 1
0x18002ad05  cmp     r15d, 2
0x18002ad09  jz      short loc_18002AD1E
0x18002ad0b  test    r15d, r15d
0x18002ad0e  jz      loc_18002AE88
0x18002ad14  cmp     r15d, 1
0x18002ad18  jnz     loc_18002AE9B
0x18002ad1e  mov     eax, [rsp+0D8h+var_50]
0x18002ad25  mov     [r9+4], eax
0x18002ad29  mov     eax, [rsp+0D8h+var_4C]
0x18002ad30  mov     [r9+8], eax
0x18002ad34  mov     eax, [rsp+0D8h+var_48]
0x18002ad3b  mov     [r9+0Ch], eax
0x18002ad3f  lea     r12, [r9+10h]
0x18002ad43  mov     r9, r12
0x18002ad46  mov     r15d, 307h
0x18002ad4c  mov     r8d, r15d
0x18002ad4f  mov     rdx, rdi; hModule
0x18002ad52  mov     rcx, rsi; lpwstrFilename
0x18002ad55  call    SymGetOriginalFilename
0x18002ad5a  mov     r13d, eax
0x18002ad5d  mov     edx, 2Fh ; '/'; Ch
0x18002ad62  mov     rcx, rsi; Str
0x18002ad65  call    cs:__imp_wcsrchr
0x18002ad6b  mov     rdi, rax
0x18002ad6e  mov     edx, 5Ch ; '\'; Ch
0x18002ad73  mov     rcx, rsi; Str
0x18002ad76  call    cs:__imp_wcsrchr
  ... truncated ...
```
