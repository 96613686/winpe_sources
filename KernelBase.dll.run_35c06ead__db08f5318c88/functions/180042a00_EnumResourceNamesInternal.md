# EnumResourceNamesInternal

- ea: `0x180042a00`
- end: `0x180043f15`
- name: `EnumResourceNamesInternal`
- size: `5397`
- prototype: `__int64 __usercall@<rax>(PVOID BaseAddress@<rcx>, ULONG ResultSize, __int16, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180042530`
- `0x180107ab0`
- `0x1801753a0`

## callees

- `0x1800134a0`
- `0x180042a00`
- `0x180044090`
- `0x1800441cc`
- `0x180044ea0`
- `0x180044ed0`
- `0x180188eb9`
- `0x180197010`

## import_xrefs

- `ntdll!wcslen` at `0x1800435d8`
- `ntdll!wcslen` at `0x1800435d8`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18004384f`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18004384f`
- `ntdll!RtlFreeHeap` at `0x180042e8c`
- `ntdll!RtlFreeHeap` at `0x180043277`
- `ntdll!RtlFreeHeap` at `0x18004352e`
- `ntdll!RtlFreeHeap` at `0x180043617`
- `ntdll!RtlFreeHeap` at `0x1800436a0`
- `ntdll!RtlFreeHeap` at `0x180043914`
- `ntdll!RtlFreeHeap` at `0x180043947`
- `ntdll!RtlFreeHeap` at `0x180043966`
- `ntdll!RtlFreeHeap` at `0x180043985`
- `ntdll!RtlFreeHeap` at `0x1800439a7`
- `ntdll!RtlFreeHeap` at `0x18018948a`
- `ntdll!RtlFreeHeap` at `0x1801894b0`
- `ntdll!RtlFreeHeap` at `0x1801894da`
- `ntdll!RtlFreeHeap` at `0x180189503`
- `ntdll!RtlFreeHeap` at `0x180042e8c`
- `ntdll!RtlFreeHeap` at `0x180043277`
- `ntdll!RtlFreeHeap` at `0x18004352e`
- `ntdll!RtlFreeHeap` at `0x180043617`
- `ntdll!RtlFreeHeap` at `0x1800436a0`
- `ntdll!RtlFreeHeap` at `0x180043914`
- `ntdll!RtlFreeHeap` at `0x180043947`
- `ntdll!RtlFreeHeap` at `0x180043966`
- `ntdll!RtlFreeHeap` at `0x180043985`
- `ntdll!RtlFreeHeap` at `0x1800439a7`
- `ntdll!RtlFreeHeap` at `0x18018948a`
- `ntdll!RtlFreeHeap` at `0x1801894b0`
- `ntdll!RtlFreeHeap` at `0x1801894da`
- `ntdll!RtlFreeHeap` at `0x180189503`
- `ntdll!LdrResGetRCConfig` at `0x180043c47`
- `ntdll!LdrResGetRCConfig` at `0x180043cd7`
- `ntdll!LdrResGetRCConfig` at `0x180043da1`
- `ntdll!LdrResGetRCConfig` at `0x180043dbc`
- `ntdll!LdrResGetRCConfig` at `0x180043c47`
- `ntdll!LdrResGetRCConfig` at `0x180043cd7`
- `ntdll!LdrResGetRCConfig` at `0x180043da1`
- `ntdll!LdrResGetRCConfig` at `0x180043dbc`
- `ntdll!LdrpResGetResourceDirectory` at `0x180043aa0`
- `ntdll!LdrpResGetResourceDirectory` at `0x180043b9f`
- `ntdll!LdrpResGetResourceDirectory` at `0x180043e75`
- `ntdll!LdrpResGetResourceDirectory` at `0x180043ea7`
- `ntdll!LdrpResGetResourceDirectory` at `0x180043aa0`
- `ntdll!LdrpResGetResourceDirectory` at `0x180043b9f`
- `ntdll!LdrpResGetResourceDirectory` at `0x180043e75`
- `ntdll!LdrpResGetResourceDirectory` at `0x180043ea7`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180043d4a`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180043df6`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180043d4a`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180043df6`
- `ntdll!LdrLoadAlternateResourceModule` at `0x180043a02`
- `ntdll!LdrLoadAlternateResourceModule` at `0x180043b3d`
- `ntdll!LdrLoadAlternateResourceModule` at `0x180043a02`
- `ntdll!LdrLoadAlternateResourceModule` at `0x180043b3d`
- `ntdll!LdrRscIsTypeExist` at `0x180043c76`
- `ntdll!LdrRscIsTypeExist` at `0x180043d0c`
- `ntdll!LdrRscIsTypeExist` at `0x180043c76`
- `ntdll!LdrRscIsTypeExist` at `0x180043d0c`
- `ntdll!LdrLoadAlternateResourceModuleEx` at `0x180043e28`
- `ntdll!LdrLoadAlternateResourceModuleEx` at `0x180043e28`
- `ntdll!LdrpResGetMappingSize` at `0x180043a3a`
- `ntdll!LdrpResGetMappingSize` at `0x180043d80`
- `ntdll!LdrpResGetMappingSize` at `0x180043a3a`
- `ntdll!LdrpResGetMappingSize` at `0x180043d80`
- `ntdll!RtlAllocateHeap` at `0x1800432d1`
- `ntdll!RtlAllocateHeap` at `0x180043585`
- `ntdll!RtlAllocateHeap` at `0x18004365a`
- `ntdll!RtlAllocateHeap` at `0x1800432d1`
- `ntdll!RtlAllocateHeap` at `0x180043585`
- `ntdll!RtlAllocateHeap` at `0x18004365a`

## pseudocode

```c
__int64 EnumResourceNamesInternal(
        PVOID BaseAddress,
        WCHAR *a2,
        unsigned int (__fastcall *a3)(PVOID, PVOID, __int64, __int64),
        __int64 a4,
        ...)
{
  int ResourceDirectory; // r15d
  unsigned int v6; // ebx
  int v7; // r14d
  int v8; // edi
  char *v9; // r12
  PVOID ImageBaseAddress; // r13
  int Resource; // edx
  __int64 v12; // rcx
  unsigned __int16 *v13; // rdi
  __int64 v14; // rsi
  void *v15; // r15
  const wchar_t *v16; // r13
  unsigned int v17; // r10d
  unsigned int v18; // r11d
  unsigned __int64 v19; // rbx
  unsigned __int64 v20; // r9
  unsigned int v21; // ebx
  unsigned __int64 v22; // r14
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  unsigned __int64 v26; // r8
  ULONG v27; // r10d
  __int64 v28; // rcx
  unsigned int v29; // r12d
  unsigned __int16 v30; // ax
  bool v31; // zf
  int v32; // r15d
  const wchar_t *v33; // r15
  __int64 v34; // rax
  unsigned __int64 v35; // r8
  __int64 v36; // r15
  char *v37; // r15
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // rdx
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // r8
  unsigned __int64 v42; // rdx
  PVOID v43; // rax
  const wchar_t *v44; // r10
  int v45; // eax
  unsigned __int64 v46; // rcx
  __int64 v47; // rax
  unsigned __int64 v48; // kr10_8
  int v49; // eax
  NTSTATUS v50; // eax
  __int64 v51; // r15
  char *v52; // r15
  unsigned __int64 v53; // rcx
  unsigned __int64 v54; // rdx
  unsigned __int64 v55; // rdx
  unsigned __int64 v56; // r8
  unsigned __int64 v57; // rdx
  unsigned __int16 v58; // ax
  const wchar_t *v59; // rcx
  int v60; // edx
  int v61; // r8d
  PVOID Heap; // rax
  int v63; // eax
  __int64 v64; // rcx
  ULONG v65; // eax
  ULONG v66; // r15d
  PVOID v67; // rcx
  __int64 v68; // rax
  unsigned __int64 v69; // r8
  unsigned __int16 v70; // ax
  __int64 v72; // r9
  __int64 v73; // r12
  int v74; // eax
  __int64 v75; // r9
  __int64 v76; // rdi
  __int64 v77; // r12
  int RCConfig; // eax
  int IsTypeExist; // eax
  int v80; // eax
  int UnicodeSize; // [rsp+20h] [rbp-158h]
  WCHAR *v82; // [rsp+38h] [rbp-140h]
  PVOID v83; // [rsp+40h] [rbp-138h]
  char *v84; // [rsp+48h] [rbp-130h]
  ULONG Size; // [rsp+58h] [rbp-120h] BYREF
  int v86; // [rsp+5Ch] [rbp-11Ch]
  unsigned int *v87; // [rsp+60h] [rbp-118h] BYREF
  PVOID P; // [rsp+68h] [rbp-110h]
  WCHAR Buffer[4]; // [rsp+70h] [rbp-108h] BYREF
  WCHAR v90[4]; // [rsp+78h] [rbp-100h] BYREF
  int v91; // [rsp+80h] [rbp-F8h] BYREF
  unsigned __int64 v92; // [rsp+88h] [rbp-F0h] BYREF
  unsigned __int64 v93; // [rsp+90h] [rbp-E8h] BYREF
  SIZE_T v94; // [rsp+98h] [rbp-E0h] BYREF
  unsigned __int64 v95; // [rsp+A0h] [rbp-D8h]
  __int64 v96; // [rsp+A8h] [rbp-D0h] BYREF
  __int64 v97; // [rsp+B0h] [rbp-C8h] BYREF
  unsigned int v98; // [rsp+B8h] [rbp-C0h]
  PVOID v99; // [rsp+C0h] [rbp-B8h]
  unsigned int *v100; // [rsp+C8h] [rbp-B0h] BYREF
  ULONG v101; // [rsp+D0h] [rbp-A8h]
  char *v102; // [rsp+D8h] [rbp-A0h] BYREF
  char *v103; // [rsp+E0h] [rbp-98h] BYREF
  ULONG v104; // [rsp+E8h] [rbp-90h]
  unsigned int *v105; // [rsp+F0h] [rbp-88h]
  unsigned __int16 *v106; // [rsp+F8h] [rbp-80h]
  unsigned int v107; // [rsp+100h] [rbp-78h]
  unsigned int v108; // [rsp+104h] [rbp-74h]
  const wchar_t *v109; // [rsp+108h] [rbp-70h]
  __int64 v110; // [rsp+110h] [rbp-68h]
  __int64 v111; // [rsp+118h] [rbp-60h]
  __int64 v112; // [rsp+120h] [rbp-58h]
  __int64 v113; // [rsp+128h] [rbp-50h]
  __int64 v114; // [rsp+130h] [rbp-48h]
  __int64 ResultSize; // [rsp+1A0h] [rbp+28h] BYREF
  va_list ResultSizea; // [rsp+1A0h] [rbp+28h]
  __int64 v121; // [rsp+1A8h] [rbp+30h]
  __int64 v122; // [rsp+1B0h] [rbp+38h]
  va_list va1; // [rsp+1B8h] [rbp+40h] BYREF

  va_start(va1, a4);
  va_start(ResultSizea, a4);
  ResultSize = va_arg(va1, _QWORD);
  v121 = va_arg(va1, _QWORD);
  v122 = va_arg(va1, _QWORD);
  ResourceDirectory = 0;
  v92 = 0;
  v93 = 0;
  v103 = 0;
  v102 = 0;
  v82 = 0;
  v104 = 0;
  v101 = 0;
  *(_QWORD *)v90 = 0;
  Size = 0;
  v97 = 0;
  v96 = 0;
  v100 = 0;
  v91 = 0;
  v6 = ResultSize;
  if ( (ResultSize & 0xFFFFFFE4) != 0 )
    goto LABEL_210;
  v7 = ResultSize & 8;
  v8 = ResultSize & 0x10;
  if ( (ResultSize & 0x17) == 0 )
    v6 = ResultSize | 3;
  if ( (ResultSize & 6) == 6 )
    goto LABEL_210;
  if ( (ResultSize & 0x10) != 0 )
  {
    if ( (ResultSize & 7) != 0 )
      goto LABEL_210;
    v6 = v6 & 0xFFFFFFEE | 1;
  }
  v9 = (char *)BaseDllMapResourceIdW(a2);
  v84 = v9;
  if ( v9 == (char *)-1LL )
  {
LABEL_210:
    v12 = 3221225485LL;
LABEL_211:
    BaseSetLastNTError(v12);
    return 0;
  }
  if ( BaseAddress )
    ImageBaseAddress = BaseAddress;
  else
    ImageBaseAddress = NtCurrentPeb()->ImageBaseAddress;
  v95 = (unsigned __int64)ImageBaseAddress;
  if ( v8 )
    goto LABEL_10;
  if ( !v7 )
  {
    RCConfig = LdrResGetRCConfig(ImageBaseAddress, 0, &v100, 0x2000, 1);
    goto LABEL_249;
  }
  RCConfig = LdrResGetRCConfig(ImageBaseAddress, 0, &v100, 0, 1);
  if ( RCConfig != -1073020925 )
  {
LABEL_249:
    if ( RCConfig >= 0 )
    {
      IsTypeExist = LdrRscIsTypeExist(v100, v9, 0, &v91);
      if ( IsTypeExist < 0 )
      {
        BaseSetLastNTError((unsigned int)IsTypeExist);
        return 0;
      }
    }
  }
LABEL_10:
  if ( (v6 & 2) == 0 )
    goto LABEL_11;
  if ( !v100 || (v100[4] & 1) == 0 )
    goto LABEL_252;
  if ( (v91 & 0x20000) != 0 )
  {
    ResourceDirectory = -1073741686;
    goto LABEL_11;
  }
  v74 = (_WORD)v121
      ? LdrLoadAlternateResourceModuleEx(ImageBaseAddress, (unsigned __int16)v121, v90, 0, 128)
      : LdrLoadAlternateResourceModule(ImageBaseAddress, v90);
  if ( v74 < 0 )
  {
LABEL_252:
    ResourceDirectory = -1073020927;
    goto LABEL_11;
  }
  if ( v7 )
  {
    LOBYTE(v75) = 1;
    if ( (int)LdrpResGetMappingSize(*(_QWORD *)v90, &v97, 256, v75) < 0 )
      v97 = 0;
  }
  v76 = *(_QWORD *)v90;
  *(_QWORD *)Buffer = 0;
  if ( !*(_QWORD *)v90 )
  {
    ResourceDirectory = -1073741811;
    goto LABEL_11;
  }
  if ( (v6 & 8) != 0 )
  {
    v77 = v97;
    if ( !v97 )
    {
      ResourceDirectory = -1073741811;
      v9 = v84;
      goto LABEL_11;
    }
    ResourceDirectory = LdrpResGetResourceDirectory(*(_QWORD *)v90, v97, 4096, &v102, Buffer);
    if ( ResourceDirectory == -1073741686 )
      ResourceDirectory = LdrpResGetResourceDirectory(v76, v77, 0, &v102, Buffer);
    v9 = v84;
  }
  else
  {
    v102 = (char *)RtlImageDirectoryEntryToData(*(PVOID *)v90, 1u, 2u, &Size);
    ResourceDirectory = -1073741687;
    if ( v102 )
      ResourceDirectory = 0;
  }
  if ( ResourceDirectory >= 0 )
    ResourceDirectory = EnumFindResource(*(_DWORD *)v90, (_DWORD)v9, 0, 0, v6 | 0x200, (__int64)&v93);
LABEL_11:
  Resource = 0;
  if ( (v6 & 1) == 0 )
    goto LABEL_12;
  *(_QWORD *)Buffer = 0;
  v87 = 0;
  LODWORD(ResultSize) = 0;
  if ( LdrLoadAlternateResourceModule(ImageBaseAddress, Buffer) >= 0 )
  {
    ImageBaseAddress = *(PVOID *)Buffer;
    v95 = *(_QWORD *)Buffer;
    if ( !*(_QWORD *)Buffer )
    {
      ImageBaseAddress = NtCurrentPeb()->ImageBaseAddress;
      v95 = (unsigned __int64)ImageBaseAddress;
    }
    if ( (v6 & 0x10) == 0 )
    {
      LOBYTE(UnicodeSize) = 1;
      if ( (v6 & 8) != 0 )
      {
        v80 = LdrResGetRCConfig(ImageBaseAddress, 0, &v87, 0, UnicodeSize);
        if ( v80 == -1073020925 )
          goto LABEL_213;
      }
      else
      {
        v80 = LdrResGetRCConfig(ImageBaseAddress, 0, &v87, 0x2000, UnicodeSize);
      }
      if ( v80 >= 0 )
      {
        if ( v9 )
        {
          if ( (int)LdrRscIsTypeExist(v87, v9, 0, (__int64 *)ResultSizea) >= 0 )
          {
            v100 = v87;
            v91 = ResultSize;
          }
        }
        else
        {
          v100 = v87;
        }
      }
    }
  }
LABEL_213:
  if ( (v91 & 0x40000) != 0 )
  {
    Resource = -1073741686;
  }
  else
  {
    if ( v7 )
    {
      LOBYTE(v72) = 1;
      if ( (int)LdrpResGetMappingSize(ImageBaseAddress, &v96, 256, v72) < 0 )
        v96 = 0;
    }
    v94 = 0;
    if ( ImageBaseAddress )
    {
      if ( (v6 & 8) != 0 )
      {
        v73 = v96;
        if ( !v96 )
        {
          Resource = -1073741811;
          v9 = v84;
          goto LABEL_12;
        }
        Resource = LdrpResGetResourceDirectory(ImageBaseAddress, v96, 4096, &v103, &v94);
        if ( Resource == -1073741686 )
          Resource = LdrpResGetResourceDirectory(ImageBaseAddress, v73, 0, &v103, &v94);
      }
      else
      {
        v103 = (char *)RtlImageDirectoryEntryToData(ImageBaseAddress, 1u, 2u, &Size);
        Resource = -1073741687;
        if ( v103 )
          Resource = 0;
      }
      v9 = v84;
      if ( Resource >= 0 )
        Resource = EnumFindResource((_DWORD)ImageBaseAddress, (_DWORD)v84, 0, 0, v6 | 0x200, (__int64)&v92);
    }
    else
    {
      Resource = -1073741811;
    }
  }
LABEL_12:
  if ( (v6 & 1) != 0 && (v6 & 2) != 0 && ResourceDirectory < 0 && Resource < 0 )
  {
    v12 = (unsigned int)Resource;
  }
  else
  {
    v12 = 0;
    if ( (v6 & 1) != 0 && (~(_BYTE)v6 & 2) != 0 && Resource < 0 )
      v12 = (unsigned int)Resource;
  }
  if ( (v6 & 1) == 0 && (v6 & 2) != 0 && ResourceDirectory < 0 )
    v12 = (unsigned int)ResourceDirectory;
  if ( (int)v12 < 0 )
    goto LABEL_211;
  v13 = 0;
  v87 = 0;
  v14 = 0;
  P = 0;
  v15 = 0;
  v83 = 0;
  v16 = 0;
  v17 = 0;
  *(_QWORD *)Buffer = 0;
  v18 = 0;
  v94 = 0;
  v99 = 0;
  v19 = 0;
  v20 = v93;
  if ( v93 )
  {
    if ( v7 )
    {
      v19 = v93 + 16;
      if ( v93 + 16 < v93
        || v19 < (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL)
        || v19 > v97 + (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL) )
      {
        goto LABEL_21;
      }
    }
    v87 = (unsigned int *)(v93 + 16);
    v105 = (unsigned int *)(v93 + 16);
  }
  v26 = v92;
  if ( v92 )
  {
    if ( v7 )
    {
      v19 = v92 + 16;
      if ( v92 + 16 < v92 || v19 < (v95 & 0xFFFFFFFFFFFFFFFCuLL) || v19 > v96 + (v95 & 0xFFFFFFFFFFFFFFFCuLL) )
      {
LABEL_21:
        BaseSetLastNTError(3221225595LL);
        v21 = 0;
        v22 = 0;
        goto LABEL_199;
      }
    }
    v13 = (unsigned __int16 *)(v92 + 16);
    v106 = (unsigned __int16 *)(v92 + 16);
  }
  Size = 0;
  v29 = 0;
  v98 = 0;
  if ( v7 )
  {
    if ( v93 )
    {
      v58 = *(_WORD *)(v93 + 12);
      if ( v58 )
      {
        v111 = 0;
        v19 = 8LL * v58;
        if ( !is_mul_ok(v58, 8u)
          || v19 + v93 < (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL)
          || v19 + v93 > (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL) + v97 )
        {
          goto LABEL_117;
        }
        v17 = *(_DWORD *)Buffer;
      }
    }
    if ( v92 )
    {
      v30 = *(_WORD *)(v92 + 12);
      if ( v30 )
      {
        v112 = 0;
        v48 = v30;
        v47 = 8LL * v30;
        v19 = v47;
        if ( !is_mul_ok(v48, 8u)
          || v47 + v92 < (v95 & 0xFFFFFFFFFFFFFFFCuLL)
          || v47 + v92 > v96 + (v95 & 0xFFFFFFFFFFFFFFFCuLL) )
        {
LABEL_117:
          BaseSetLastNTError(3221225595LL);
          v21 = 0;
          v9 = v84;
          v22 = 0;
          goto LABEL_199;
        }
      }
    }
  }
  v31 = (v122 & 1) == 0;
  v32 = v122 & 1;
  LODWORD(v122) = v32;
  if ( v31 )
    goto LABEL_65;
  if ( ((unsigned __int64)a2 & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    v50 = ConverStringWithHeapAlloc(a2);
    if ( v50 >= 0 )
      goto LABEL_126;
    goto LABEL_129;
  }
  v82 = a2;
  while ( 1 )
  {
LABEL_65:
    if ( (!v20 || Size >= *(unsigned __int16 *)(v20 + 12)) && (!v26 || v29 >= *(unsigned __int16 *)(v26 + 12)) )
      goto LABEL_102;
    if ( v20 && Size < *(unsigned __int16 *)(v20 + 12) )
    {
      if ( v7 )
      {
        v68 = *v87;
        LODWORD(v68) = v68 & 0x7FFFFFFF;
        v19 = (unsigned __int64)&v102[v68 + 4];
        if ( v19 < (unsigned __int64)v102
          || (v69 = (unsigned __int64)&v102[v68 + 4], v69 < (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL))
          || v69 > v97 + (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL) )
        {
LABEL_169:
          BaseSetLastNTError(3221225595LL);
          v21 = 0;
          v15 = v83;
          v9 = v84;
          v22 = (unsigned __int64)v82;
          goto LABEL_199;
        }
      }
      v51 = *v87;
      LODWORD(v51) = v51 & 0x7FFFFFFF;
      v52 = &v102[v51];
      if ( v7 )
      {
        v53 = *(unsigned __int16 *)v52;
        v54 = v53 + 1;
        if ( v53 + 1 < v53
          || (v113 = 0, v19 = 2 * v54, !is_mul_ok(v54, 2u))
          || (v55 = Size & 0xFFFFFFFC, v56 = Size + v53, v56 < v55)
          || v56 > v55 + 260 )
        {
LABEL_125:
          BaseSetLastNTError(3221225595LL);
          goto LABEL_53;
        }
        v57 = (unsigned __int64)&v52[v19 + 2];
        if ( v57 < (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL) )
          goto LABEL_140;
        if ( v57 > v97 + (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL) )
        {
          v28 = 3221225595LL;
          goto LABEL_52;
        }
      }
      Heap = P;
      if ( 2 * (unsigned int)*(unsigned __int16 *)v52 + 2 >= v17 )
      {
        if ( P )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
          P = 0;
        }
        if ( v7 )
        {
          if ( v19 + 64 < v19 )
            goto LABEL_169;
          v19 += 64LL;
        }
        v63 = *(unsigned __int16 *)v52;
        *(_QWORD *)Buffer = (2 * v63 + 64) & 0xFFFFFFC0;
        v108 = (2 * v63 + 64) & 0xFFFFFFC0;
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, *(SIZE_T *)Buffer);
        P = Heap;
        if ( !Heap )
        {
          v28 = 3221225495LL;
          goto LABEL_52;
        }
      }
      memcpy_0(Heap, v52 + 2, 2LL * *(unsigned __int16 *)v52);
      v64 = *(unsigned __int16 *)v52;
      v33 = (const wchar_t *)P;
      *((_WORD *)P + v64) = 0;
      goto LABEL_71;
    }
    v33 = (const wchar_t *)P;
    if ( P )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      v33 = 0;
      P = 0;
LABEL_71:
      v18 = v94;
      v20 = v93;
      v26 = v92;
    }
    if ( v26 && v29 < *(unsigned __int16 *)(v26 + 12) )
      break;
    v44 = (const wchar_t *)v83;
    if ( v83 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v83);
      v44 = 0;
      v83 = 0;
LABEL_87:
      v20 = v93;
      v26 = v92;
    }
    if ( !v33 )
    {
      if ( v44 )
      {
LABEL_90:
        v45 = 2;
LABEL_91:
        v86 = v45;
        goto LABEL_92;
      }
      v32 = v122;
LABEL_102:
      v27 = 0;
      Size = 0;
      v21 = 0;
      v98 = 0;
      if ( v7 )
      {
        if ( v20
          && (v70 = *(_WORD *)(v20 + 14)) != 0
          && ((*(_QWORD *)Buffer = 0, !is_mul_ok(v70, 8u))
           || v20 + 16 < (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL)
           || v20 + 16 > v97 + (*(_QWORD *)v90 & 0xFFFFFFFFFFFFFFFCuLL))
          || v26
          && (v46 = *(unsigned __int16 *)(v26 + 14), (_WORD)v46)
          && ((v94 = 0, !is_mul_ok(v46, 8u))
           || v26 + 16 < (v95 & 0xFFFFFFFFFFFFFFFCuLL)
           || v26 + 16 > v96 + (v95 & 0xFFFFFFFFFFFFFFFCuLL)) )
        {
          BaseSetLastNTError(3221225595LL);
          v15 = v83;
          v9 = v84;
          v22 = (unsigned __int64)v82;
          goto LABEL_199;
        }
      }
      while ( 1 )
      {
        if ( (!v20 || v27 >= *(unsigned __int16 *)(v20 + 14)) && (!v26 || v21 >= *(unsigned __int16 *)(v26 + 14)) )
        {
LABEL_50:
          v21 = 1;
          goto LABEL_54;
        }
        v23 = v20 && v27 < *(unsigned __int16 *)(v20 + 14) ? *(unsigned __int16 *)v87 : -1LL;
        v24 = v26 && v21 < *(unsigned __int16 *)(v26 + 14) ? *v13 : -1LL;
        if ( v23 == -1 )
          break;
        if ( v24 == -1 )
        {
          v25 = 1;
          goto LABEL_33;
        }
        LOBYTE(v25) = 1;
        v86 = 1;
        if ( (int)v23 - (int)v24 > 0 )
          goto LABEL_32;
        if ( (_DWORD)v23 == (_DWORD)v24 )
        {
          v25 = 3;
          goto LABEL_33;
        }
LABEL_34:
        if ( (v25 & 1) != 0 )
        {
          v14 = v23;
          v110 = v23;
          v87 += 2;
          v105 = v87;
          Size = v27 + 1;
        }
        if ( (v25 & 2) != 0 )
        {
          v14 = v24;
          v110 = v24;
          v13 += 4;
          v106 = v13;
          v98 = ++v21;
        }
        if ( v32 )
        {
          v22 = (unsigned __int64)v82;
          if ( !a3(BaseAddress, v82, v14, a4) )
          {
            BaseSetLastNTError(3221946375LL);
            v21 = 0;
            v15 = v83;
            v9 = v84;
            goto LABEL_199;
          }
        }
        else if ( !a3(BaseAddress, a2, v14, a4) )
        {
          BaseSetLastNTError(3221946375LL);
          goto LABEL_53;
        }
        v26 = v92;
        v20 = v93;
        v27 = Size;
      }
      if ( v24 == -1 )
        goto LABEL_50;
LABEL_32:
      v25 = 2;
LABEL_33:
      v86 = v25;
      goto LABEL_34;
    }
    if ( !v44 )
    {
      v45 = 1;
      goto LABEL_91;
    }
    LOBYTE(v45) = 1;
    v86 = 1;
    v59 = v33;
    do
    {
      v60 = *(const wchar_t *)((char *)v59 + (char *)v44 - (char *)v33);
      v61 = *v59 - v60;
      if ( v61 )
        break;
      ++v59;
    }
    while ( v60 );
    if ( v61 > 0 )
      goto LABEL_90;
    if ( !v61 )
    {
      v45 = 3;
      goto LABEL_91;
    }
LABEL_92:
    if ( (v45 & 1) != 0 )
    {
      v16 = v33;
      v109 = v33;
      v87 += 2;
      v105 = v87;
      ++Size;
    }
    if ( (v45 & 2) != 0 )
    {
      v16 = v44;
      v109 = v44;
      v13 += 4;
      v106 = v13;
      v98 = ++v29;
    }
    v32 = v122;
    if ( (_DWORD)v122 )
    {
      LODWORD(ResultSize) = 0;
      if ( !v16 )
      {
        v28 = 3221225485LL;
        goto LABEL_52;
      }
      v65 = wcslen(v16) + 1;
      LODWORD(ResultSize) = v65;
      v66 = v101;
      if ( v101 >= v65 )
      {
        v67 = v99;
      }
      else
      {
        if ( v99 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v99);
          v99 = 0;
          v65 = ResultSize;
        }
        v66 = v65 + 16;
        v101 = v65 + 16;
        v104 = v65 + 16;
        v67 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v65 + 16);
        v99 = v67;
        if ( !v67 )
        {
          v28 = 3221225495LL;
          goto LABEL_52;
        }
        v65 = ResultSize;
      }
      if ( !v67 )
      {
        v50 = -1073741801;
LABEL_129:
        v28 = (unsigned int)v50;
        goto LABEL_52;
      }
      v50 = RtlUnicodeToMultiByteN((PCHAR)v67, v66, (PULONG)ResultSizea, v16, 2 * v65);
      if ( v50 < 0 )
        goto LABEL_129;
      if ( !a3(BaseAddress, v82, (__int64)v99, a4) )
      {
        v28 = 3221946375LL;
        goto LABEL_52;
      }
      v32 = v122;
    }
    else if ( !a3(BaseAddress, a2, (__int64)v16, a4) )
    {
      v28 = 3221946375LL;
      goto LABEL_52;
    }
LABEL_126:
    v26 = v92;
    v20 = v93;
    v18 = v94;
    v17 = *(_DWORD *)Buffer;
  }
  if ( v7 )
  {
    v34 = *(unsigned int *)v13;
    LODWORD(v34) = v34 & 0x7FFFFFFF;
    v19 = (unsigned __int64)&v103[v34 + 4];
    if ( v19 < (unsigned __int64)v103 )
      goto LABEL_51;
    v35 = (unsigned __int64)&v103[v34 + 4];
    if ( v35 < (v95 & 0xFFFFFFFFFFFFFFFCuLL) || v35 > v96 + (v95 & 0xFFFFFFFFFFFFFFFCuLL) )
    {
LABEL_140:
      v28 = 3221225595LL;
      goto LABEL_52;
    }
  }
  v36 = *(unsigned int *)v13;
  LODWORD(v36) = v36 & 0x7FFFFFFF;
  v37 = &v103[v36];
  if ( !v7 )
    goto LABEL_85;
  v38 = *(unsigned __int16 *)v37;
  v39 = v38 + 1;
  if ( v38 + 1 < v38 )
    goto LABEL_125;
  v114 = 0;
  v19 = 2 * v39;
  if ( !is_mul_ok(v39, 2u) )
    goto LABEL_125;
  v40 = Size & 0xFFFFFFFC;
  v41 = v38 + Size;
  if ( v41 < v40 || v41 > v40 + 260 )
    goto LABEL_125;
  v42 = (unsigned __int64)&v37[v19 + 2];
  if ( v42 < (v95 & 0xFFFFFFFFFFFFFFFCuLL) )
    goto LABEL_140;
  if ( v42 <= v96 + (v95 & 0xFFFFFFFFFFFFFFFCuLL) )
  {
LABEL_85:
    v43 = v83;
    if ( 2 * (unsigned int)*(unsigned __int16 *)v37 + 2 >= v18 )
    {
      if ( v83 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v83);
        v83 = 0;
      }
      if ( v7 )
      {
        if ( v19 + 64 < v19 )
        {
LABEL_51:
          v28 = 3221225595LL;
          goto LABEL_52;
        }
        v19 += 64LL;
      }
      v49 = *(unsigned __int16 *)v37;
      v94 = (2 * v49 + 64) & 0xFFFFFFC0;
      v107 = (2 * v49 + 64) & 0xFFFFFFC0;
      v43 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v94);
      v83 = v43;
      if ( !v43 )
      {
        v28 = 3221225495LL;
        goto LABEL_52;
      }
    }
    memcpy_0(v43, v37 + 2, 2LL * *(unsigned __int16 *)v37);
    v44 = (const wchar_t *)v83;
    *((_WORD *)v83 + *(unsigned __int16 *)v37) = 0;
    v33 = (const wchar_t *)P;
    goto LABEL_87;
  }
  v28 = 3221225595LL;
LABEL_52:
  BaseSetLastNTError(v28);
LABEL_53:
  v21 = 0;
LABEL_54:
  v15 = v83;
  v9 = v84;
  v22 = (unsigned __int64)v82;
LABEL_199:
  if ( (unsigned __int64)(v9 - 0x10000) <= 0xFFFFFFFFFFFEFFFEuLL )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  if ( P )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    P = 0;
  }
  if ( v15 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  if ( (v22 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v22);
  if ( v99 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v99);
  return v21;
}

```

## disassembly

```asm
0x180042a00  mov     rax, rsp
0x180042a03  mov     [rax+20h], r9
0x180042a07  mov     [rax+18h], r8
0x180042a0b  mov     [rax+10h], rdx
0x180042a0f  mov     [rax+8], rcx
0x180042a13  push    rbx
0x180042a14  push    rsi
0x180042a15  push    rdi
0x180042a16  push    r12
0x180042a18  push    r13
0x180042a1a  push    r14
0x180042a1c  push    r15
0x180042a1e  sub     rsp, 140h
0x180042a25  mov     rsi, rcx
0x180042a28  xor     r15d, r15d
0x180042a2b  mov     [rax-0F0h], r15
0x180042a32  mov     [rax-0E8h], r15
0x180042a39  mov     [rax-98h], r15
0x180042a40  mov     [rax-0A0h], r15
0x180042a47  mov     [rsp+178h+var_140], r15
0x180042a4c  mov     [rax-90h], r15d
0x180042a53  mov     [rax-0A8h], r15d
0x180042a5a  mov     qword ptr [rsp+178h+var_100], r15
0x180042a5f  mov     [rsp+178h+Size], r15d
0x180042a64  mov     [rax-0C8h], r15
0x180042a6b  mov     [rax-0D0h], r15
0x180042a72  mov     [rax-0B0h], r15
0x180042a79  mov     [rax-0F8h], r15d
0x180042a80  mov     ebx, dword ptr [rsp+178h+ResultSize]
0x180042a87  test    ebx, 0FFFFFFE4h
0x180042a8d  jnz     loc_1800439D2
0x180042a93  mov     r14d, ebx
0x180042a96  and     r14d, 8
0x180042a9a  mov     edi, ebx
0x180042a9c  and     edi, 10h
0x180042a9f  mov     ecx, ebx
0x180042aa1  test    bl, 17h
0x180042aa4  jz      loc_180043EDA
0x180042aaa  mov     eax, ecx
0x180042aac  and     eax, 6
0x180042aaf  cmp     al, 6
0x180042ab1  jz      loc_1800439D2
0x180042ab7  test    edi, edi
0x180042ab9  jnz     loc_180043DD2
0x180042abf  mov     rcx, rdx
0x180042ac2  call    BaseDllMapResourceIdW
0x180042ac7  mov     r12, rax
0x180042aca  mov     [rsp+178h+var_130], rax
0x180042acf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180042ad3  jz      loc_1800439D2
0x180042ad9  test    rsi, rsi
0x180042adc  jz      loc_180043E33
0x180042ae2  mov     r13, rsi
0x180042ae5  mov     [rsp+178h+var_D8], r13
0x180042aed  test    edi, edi
0x180042aef  jz      loc_180043C29
0x180042af5  mov     esi, ebx
0x180042af7  and     esi, 2
0x180042afa  jnz     loc_180043AEF
0x180042b00  xor     edx, edx
0x180042b02  mov     edi, ebx
0x180042b04  and     edi, 1
0x180042b07  jnz     loc_1800439E0
0x180042b0d  test    edi, edi
0x180042b0f  jnz     loc_180043BF3
0x180042b15  xor     ecx, ecx
0x180042b17  test    edi, edi
0x180042b19  jnz     loc_180043C13
0x180042b1f  not     ebx
0x180042b21  test    bl, 1
0x180042b24  jnz     loc_180043F01
0x180042b2a  test    ecx, ecx
0x180042b2c  js      loc_1800439D7
0x180042b32  xor     edx, edx
0x180042b34  mov     edi, edx
0x180042b36  mov     [rsp+178h+var_118], rdx
0x180042b3b  mov     esi, edx
0x180042b3d  mov     [rsp+178h+P], rdx
0x180042b42  mov     r15d, edx
0x180042b45  mov     [rsp+178h+var_138], rdx
0x180042b4a  mov     r13d, edx
0x180042b4d  mov     r10d, edx
0x180042b50  mov     qword ptr [rsp+178h+Buffer], r10
0x180042b55  mov     r11d, edx
0x180042b58  mov     [rsp+178h+var_E0], r11
0x180042b60  mov     [rsp+178h+var_B8], rdx
0x180042b68  mov     ebx, edx
0x180042b6a  mov     r9, [rsp+178h+var_E8]
0x180042b72  test    r9, r9
0x180042b75  jz      loc_180042DED
0x180042b7b  test    r14d, r14d
0x180042b7e  jz      loc_180042DDC
0x180042b84  lea     rbx, [r9+10h]
0x180042b88  cmp     rbx, r9
0x180042b8b  jb      loc_180042DB5
0x180042b91  mov     [rsp+178h+var_128], rbx
0x180042b96  mov     rcx, qword ptr [rsp+178h+var_100]
0x180042b9b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180042b9f  cmp     rbx, rcx
0x180042ba2  jb      short loc_180042BB8
0x180042ba4  mov     rax, [rsp+178h+var_C8]
0x180042bac  add     rcx, rax
0x180042baf  cmp     rbx, rcx
0x180042bb2  jbe     loc_180042DDC
0x180042bb8  mov     ecx, 0C000007Bh
0x180042bbd  call    BaseSetLastNTError
0x180042bc2  xor     r13d, r13d
0x180042bc5  mov     ebx, r13d
0x180042bc8  mov     [rsp+178h+var_148], ebx
0x180042bcc  mov     r14, [rsp+178h+var_140]
0x180042bd1  jmp     loc_1800438DF
0x180042bd6  test    r9, r9
0x180042bd9  jnz     loc_180042D1D
0x180042bdf  test    r8, r8
0x180042be2  jz      loc_180042D62
0x180042be8  movzx   eax, word ptr [r8+0Eh]
0x180042bed  cmp     ebx, eax
0x180042bef  jnb     loc_180042D62
0x180042bf5  test    r9, r9
0x180042bf8  jnz     loc_180042D9A
0x180042bfe  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180042c05  test    r8, r8
0x180042c08  jz      loc_180042D11
0x180042c0e  movzx   eax, word ptr [r8+0Eh]
0x180042c13  cmp     ebx, eax
0x180042c15  jnb     loc_180042D11
0x180042c1b  movzx   ecx, word ptr [rdi]
0x180042c1e  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180042c22  jnz     loc_180042D30
0x180042c28  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180042c2c  jz      loc_180042D62
0x180042c32  mov     eax, 2
0x180042c37  mov     [rsp+178h+var_11C], eax
0x180042c3b  test    al, 1
0x180042c3d  jnz     short loc_180042CB2
0x180042c3f  test    al, 2
0x180042c41  jz      short loc_180042C63
0x180042c43  mov     rsi, rcx
0x180042c46  mov     [rsp+178h+var_68], rcx
0x180042c4e  add     rdi, 8
0x180042c52  mov     [rsp+178h+var_80], rdi
0x180042c5a  inc     ebx
0x180042c5c  mov     [rsp+178h+var_C0], ebx
0x180042c63  mov     r9, [rsp+178h+arg_18]
0x180042c6b  mov     r8, rsi
0x180042c6e  mov     rcx, [rsp+178h+arg_0]
0x180042c76  mov     rax, [rsp+178h+arg_10]
0x180042c7e  test    r15d, r15d
0x180042c81  jnz     short loc_180042CE0
0x180042c83  mov     rdx, [rsp+178h+UnicodeString]
0x180042c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c90  test    eax, eax
0x180042c92  jz      loc_1800438D0
0x180042c98  mov     r8, [rsp+178h+var_F0]
0x180042ca0  mov     r9, [rsp+178h+var_E8]
0x180042ca8  mov     r10d, [rsp+178h+Size]
0x180042cad  jmp     loc_180042BD6
0x180042cb2  mov     rsi, rdx
0x180042cb5  mov     [rsp+178h+var_68], rdx
0x180042cbd  mov     rdx, [rsp+178h+var_118]
0x180042cc2  add     rdx, 8
0x180042cc6  mov     [rsp+178h+var_118], rdx
0x180042ccb  mov     [rsp+178h+var_88], rdx
0x180042cd3  inc     r10d
0x180042cd6  mov     [rsp+178h+Size], r10d
0x180042cdb  jmp     loc_180042C3F
0x180042ce0  mov     r14, [rsp+178h+var_140]
0x180042ce5  mov     rdx, r14
0x180042ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ced  test    eax, eax
0x180042cef  jnz     short loc_180042C98
0x180042cf1  mov     ecx, 0C00B0007h
0x180042cf6  call    BaseSetLastNTError
0x180042cfb  mov     ebx, r13d
0x180042cfe  mov     [rsp+178h+var_148], ebx
0x180042d02  mov     r15, [rsp+178h+var_138]
0x180042d07  mov     r12, [rsp+178h+var_130]
0x180042d0c  jmp     loc_1800438DF
0x180042d11  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180042d18  jmp     loc_180042C1E
0x180042d1d  movzx   eax, word ptr [r9+0Eh]
0x180042d22  cmp     r10d, eax
0x180042d25  jb      loc_180042BF5
0x180042d2b  jmp     loc_180042BDF
0x180042d30  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180042d34  jz      loc_180043817
0x180042d3a  mov     eax, 1
0x180042d3f  mov     [rsp+178h+var_11C], eax
0x180042d43  mov     r8d, edx
0x180042d46  sub     r8d, ecx
0x180042d49  test    r8d, r8d
0x180042d4c  jg      loc_180042C32
0x180042d52  jnz     loc_180042C3B
0x180042d58  mov     eax, 3
0x180042d5d  jmp     loc_180042C37
0x180042d62  mov     ebx, 1
0x180042d67  jmp     short loc_180042D86
0x180042d69  mov     [rsp+178h+var_128], 0FFFFFFFFFFFFFFFFh
0x180042d72  mov     ecx, 0C000007Bh
0x180042d77  call    BaseSetLastNTError
0x180042d7c  xor     r13d, r13d
0x180042d7f  mov     ebx, r13d
0x180042d82  mov     [rsp+178h+var_148], ebx
0x180042d86  mov     r15, [rsp+178h+var_138]
0x180042d8b  mov     r12, [rsp+178h+var_130]
0x180042d90  mov     r14, [rsp+178h+var_140]
0x180042d95  jmp     loc_1800438DF
0x180042d9a  movzx   eax, word ptr [r9+0Eh]
0x180042d9f  cmp     r10d, eax
0x180042da2  jnb     loc_180042BFE
0x180042da8  mov     rax, [rsp+178h+var_118]
0x180042dad  movzx   edx, word ptr [rax]
0x180042db0  jmp     loc_180042C05
0x180042db5  mov     [rsp+178h+var_128], 0FFFFFFFFFFFFFFFFh
0x180042dbe  mov     ecx, 0C000007Bh
0x180042dc3  call    BaseSetLastNTError
0x180042dc8  xor     r13d, r13d
0x180042dcb  mov     ebx, r13d
0x180042dce  mov     [rsp+178h+var_148], ebx
0x180042dd2  mov     r14, [rsp+178h+var_140]
0x180042dd7  jmp     loc_1800438DF
0x180042ddc  lea     rax, [r9+10h]
0x180042de0  mov     [rsp+178h+var_118], rax
0x180042de5  mov     [rsp+178h+var_88], rax
0x180042ded  mov     r8, [rsp+178h+var_F0]
0x180042df5  test    r8, r8
0x180042df8  jnz     loc_1800430D2
0x180042dfe  mov     [rsp+178h+Size], edx
0x180042e02  mov     r12d, edx
0x180042e05  mov     [rsp+178h+var_C0], edx
0x180042e0c  test    r14d, r14d
0x180042e0f  jz      short loc_180042E2D
0x180042e11  test    r9, r9
0x180042e14  jnz     loc_18004342E
0x180042e1a  test    r8, r8
0x180042e1d  jz      short loc_180042E2D
0x180042e1f  movzx   eax, word ptr [r8+0Ch]
0x180042e24  test    ax, ax
0x180042e27  jnz     loc_1800431F0
0x180042e2d  mov     r15d, dword ptr [rsp+178h+arg_30]
0x180042e35  and     r15d, 1
0x180042e39  mov     dword ptr [rsp+178h+arg_30], r15d
0x180042e41  jnz     loc_18004332B
0x180042e47  test    r9, r9
0x180042e4a  jnz     loc_18004335F
0x180042e50  test    r8, r8
0x180042e53  jz      loc_1800430F4
0x180042e59  movzx   eax, word ptr [r8+0Ch]
0x180042e5e  cmp     r12d, eax
0x180042e61  jnb     loc_1800430F4
0x180042e67  test    r9, r9
0x180042e6a  jnz     loc_180043373
0x180042e70  mov     r15, [rsp+178h+P]
0x180042e75  test    r15, r15
0x180042e78  jz      short loc_180042EB2
0x180042e7a  mov     rcx, gs:60h
0x180042e83  mov     r8, r15; P
0x180042e86  xor     edx, edx; Flags
0x180042e88  mov     rcx, [rcx+30h]; HeapHandle
0x180042e8c  call    cs:__imp_RtlFreeHeap
0x180042e92  xor     r15d, r15d
0x180042e95  mov     [rsp+178h+P], r15
0x180042e9a  mov     r11, [rsp+178h+var_E0]
0x180042ea2  mov     r9, [rsp+178h+var_E8]
0x180042eaa  mov     r8, [rsp+178h+var_F0]
0x180042eb2  test    r8, r8
0x180042eb5  jz      loc_180043680
0x180042ebb  movzx   eax, word ptr [r8+0Ch]
0x180042ec0  cmp     r12d, eax
0x180042ec3  jnb     loc_180043680
0x180042ec9  test    r14d, r14d
0x180042ecc  jz      short loc_180042F21
0x180042ece  mov     eax, [rdi]
0x180042ed0  btr     eax, 1Fh
0x180042ed4  mov     rdx, [rsp+178h+var_98]
0x180042edc  lea     rbx, [rdx+4]
0x180042ee0  add     rbx, rax
0x180042ee3  cmp     rbx, rdx
0x180042ee6  jb      loc_180042D69
0x180042eec  mov     [rsp+178h+var_128], rbx
0x180042ef1  mov     rcx, [rsp+178h+var_D8]
0x180042ef9  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180042efd  lea     r8, [rdx+4]
0x180042f01  add     r8, rax
0x180042f04  cmp     r8, rcx
0x180042f07  jb      loc_180043424
0x180042f0d  mov     rax, [rsp+178h+var_D0]
0x180042f15  add     rcx, rax
0x180042f18  cmp     r8, rcx
0x180042f1b  ja      loc_180043424
0x180042f21  mov     r15d, [rdi]
0x180042f24  btr     r15d, 1Fh
0x180042f29  add     r15, [rsp+178h+var_98]
0x180042f31  test    r14d, r14d
0x180042f34  jz      loc_180042FCC
0x180042f3a  movzx   ecx, word ptr [r15]
0x180042f3e  lea     rdx, [rcx+1]
0x180042f42  cmp     rdx, rcx
0x180042f45  jb      loc_1800432F1
0x180042f4b  mov     [rsp+178h+var_128], rdx
  ... truncated ...
```
