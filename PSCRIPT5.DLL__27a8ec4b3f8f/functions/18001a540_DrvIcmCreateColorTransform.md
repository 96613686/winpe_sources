# DrvIcmCreateColorTransform

- ea: `0x18001a540`
- end: `0x18001ab32`
- name: `DrvIcmCreateColorTransform`
- size: `1522`
- prototype: `HANDLE __stdcall(DHPDEV dhpdev, LPLOGCOLORSPACEW pLogColorSpace, PVOID pvSourceProfile, ULONG cjSourceProfile, PVOID pvDestProfile, ULONG cjDestProfile, PVOID pvTargetProfile, ULONG cjTargetProfile, DWORD dwReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18001a540`
- `0x18001ab40`
- `0x1800352ac`
- `0x18005f010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001ab0a`
- `KERNEL32!FreeLibrary` at `0x18001ab0a`
- `KERNEL32!GetProcAddress` at `0x18001a6d2`
- `KERNEL32!GetProcAddress` at `0x18001a6ec`
- `KERNEL32!GetProcAddress` at `0x18001a706`
- `KERNEL32!GetProcAddress` at `0x18001a6d2`
- `KERNEL32!GetProcAddress` at `0x18001a6ec`
- `KERNEL32!GetProcAddress` at `0x18001a706`
- `KERNEL32!SetLastError` at `0x18001a659`
- `KERNEL32!SetLastError` at `0x18001a659`
- `KERNEL32!LocalAlloc` at `0x18001a640`
- `KERNEL32!LocalAlloc` at `0x18001a791`
- `KERNEL32!LocalAlloc` at `0x18001a859`
- `KERNEL32!LocalAlloc` at `0x18001a8e5`
- `KERNEL32!LocalAlloc` at `0x18001a939`
- `KERNEL32!LocalAlloc` at `0x18001a9b1`
- `KERNEL32!LocalAlloc` at `0x18001aa32`
- `KERNEL32!LocalAlloc` at `0x18001aa9e`
- `KERNEL32!LocalAlloc` at `0x18001a640`
- `KERNEL32!LocalAlloc` at `0x18001a791`
- `KERNEL32!LocalAlloc` at `0x18001a859`
- `KERNEL32!LocalAlloc` at `0x18001a8e5`
- `KERNEL32!LocalAlloc` at `0x18001a939`
- `KERNEL32!LocalAlloc` at `0x18001a9b1`
- `KERNEL32!LocalAlloc` at `0x18001aa32`
- `KERNEL32!LocalAlloc` at `0x18001aa9e`
- `mscms!InternalGetPS2ColorSpaceArray` at `0x18001a775`
- `mscms!InternalGetPS2ColorSpaceArray` at `0x18001a7c8`
- `mscms!InternalGetPS2ColorSpaceArray` at `0x18001a775`
- `mscms!InternalGetPS2ColorSpaceArray` at `0x18001a7c8`
- `mscms!InternalGetPS2CSAFromLCS` at `0x18001a95f`
- `mscms!InternalGetPS2CSAFromLCS` at `0x18001a95f`
- `mscms!InternalGetPS2ColorRenderingDictionary` at `0x18001aa16`
- `mscms!InternalGetPS2ColorRenderingDictionary` at `0x18001aa61`
- `mscms!InternalGetPS2ColorRenderingDictionary` at `0x18001aa16`
- `mscms!InternalGetPS2ColorRenderingDictionary` at `0x18001aa61`
- `mscms!InternalGetPS2PreviewCRD` at `0x18001a83d`
- `mscms!InternalGetPS2PreviewCRD` at `0x18001a891`
- `mscms!InternalGetPS2PreviewCRD` at `0x18001a83d`
- `mscms!InternalGetPS2PreviewCRD` at `0x18001a891`

## string_xrefs

- `0x18001a6a1`: `mscms.dll`

## pseudocode

```c
HANDLE __stdcall DrvIcmCreateColorTransform(
        DHPDEV dhpdev,
        LPLOGCOLORSPACEW pLogColorSpace,
        PVOID pvSourceProfile,
        ULONG cjSourceProfile,
        PVOID pvDestProfile,
        ULONG cjDestProfile,
        PVOID pvTargetProfile,
        ULONG cjTargetProfile,
        DWORD dwReserved)
{
  HMODULE v11; // r13
  __int64 v12; // rax
  int v13; // esi
  HANDLE result; // rax
  __int64 v15; // r10
  int v16; // eax
  _QWORD *v17; // rax
  _QWORD *v18; // rbx
  unsigned int v19; // edi
  BOOL v20; // r15d
  unsigned int (__fastcall *v21)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // r10
  FARPROC v22; // rax
  HLOCAL v23; // rax
  int PS2ColorSpaceArray; // eax
  __int64 v25; // rax
  PVOID v26; // r12
  HLOCAL v27; // rax
  int PS2PreviewCRD; // eax
  ULONG v29; // r12d
  HLOCAL v30; // rax
  HLOCAL v31; // rax
  __int64 (__fastcall *v32)(PVOID, _QWORD, PVOID, _QWORD, unsigned int, HLOCAL, SIZE_T *, BOOL *); // r15
  HLOCAL v33; // rax
  HLOCAL v34; // rax
  HMODULE v35; // r15
  HLOCAL v36; // rax
  BOOL v37; // [rsp+50h] [rbp-20h] BYREF
  FARPROC ProcAddress; // [rsp+58h] [rbp-18h]
  HMODULE hModule; // [rsp+60h] [rbp-10h] BYREF
  unsigned int (__fastcall *v40)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD); // [rsp+68h] [rbp-8h]
  SIZE_T uBytes; // [rsp+B0h] [rbp+40h] BYREF
  PVOID v42; // [rsp+C0h] [rbp+50h]
  ULONG v43; // [rsp+C8h] [rbp+58h]

  v43 = cjSourceProfile;
  v42 = pvSourceProfile;
  LODWORD(uBytes) = 0;
  v11 = 0;
  v37 = 0;
  v12 = *((_QWORD *)dhpdev + 12);
  hModule = 0;
  v13 = 1;
  if ( *(_DWORD *)(v12 + 124) == 2 && *((_DWORD *)dhpdev + 543) > 1u )
    return 0;
  v15 = *((_QWORD *)dhpdev + 434);
  if ( v15 )
  {
    if ( *(_QWORD *)(v15 + 464) )
    {
      v16 = *((_DWORD *)dhpdev + 870);
      if ( (v16 & 1) == 0 )
      {
        *((_DWORD *)dhpdev + 870) = v16 | 1;
        *((_QWORD *)dhpdev + 4) = *(_QWORD *)(*(_QWORD *)(v15 + 472) + 32LL);
        *((_QWORD *)dhpdev + 1) = *(_QWORD *)(*(_QWORD *)(v15 + 472) + 40LL);
        *((_QWORD *)dhpdev + 6) = *(_QWORD *)(*(_QWORD *)(v15 + 472) + 56LL);
        result = (HANDLE)(*(__int64 (__fastcall **)(DHPDEV))(v15 + 464))(dhpdev);
        *((_DWORD *)dhpdev + 870) &= ~1u;
        return result;
      }
    }
  }
  v17 = LocalAlloc(0x40u, 0x20u);
  v18 = v17;
  if ( !v17 )
  {
    SetLastError(8u);
    return 0;
  }
  switch ( pLogColorSpace->lcsIntent )
  {
    case 1:
      v19 = 2;
      break;
    case 2:
      v19 = 1;
      break;
    case 4:
      v19 = 0;
      break;
    case 8:
      v19 = 3;
      break;
    default:
      goto LABEL_54;
  }
  v20 = 0;
  *((_DWORD *)v17 + 7) = v19;
  if ( (int)LoadLibraryFromSystemDirectory(L"mscms.dll", &hModule) >= 0 )
  {
    v11 = hModule;
    hModule = (HMODULE)GetProcAddress(hModule, "InternalGetPS2ColorRenderingDictionary2");
    ProcAddress = GetProcAddress(v11, "InternalGetPS2ColorSpaceArray2");
    v22 = GetProcAddress(v11, "InternalGetPS2PreviewCRD2");
    v21 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
    v40 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD))v22;
    if ( hModule && ProcAddress )
      v20 = v22 != 0;
  }
  else
  {
    hModule = 0;
    v21 = 0;
    ProcAddress = 0;
    v40 = 0;
  }
  v37 = *((_WORD *)dhpdev + 83) != 0;
  if ( v42 )
  {
    LODWORD(uBytes) = 0;
    if ( v20 )
    {
      v29 = v43;
      if ( !v21(v42, v43, v19, 2, 0, &uBytes, &v37) )
        goto LABEL_54;
      v30 = LocalAlloc(0, (unsigned int)uBytes);
      *v18 = v30;
      if ( !v30 )
        goto LABEL_54;
      PS2ColorSpaceArray = ((__int64 (__fastcall *)(PVOID, _QWORD, _QWORD, __int64, HLOCAL, SIZE_T *, BOOL *))ProcAddress)(
                             v42,
                             v29,
                             v19,
                             2,
                             v30,
                             &uBytes,
                             &v37);
    }
    else
    {
      if ( !(unsigned int)InternalGetPS2ColorSpaceArray(v42, v19, 2, 0, &uBytes, &v37) )
        goto LABEL_54;
      v23 = LocalAlloc(0, (unsigned int)uBytes);
      *v18 = v23;
      if ( !v23 )
        goto LABEL_54;
      PS2ColorSpaceArray = InternalGetPS2ColorSpaceArray(v42, v19, 2, v23, &uBytes, &v37);
    }
  }
  else
  {
    LODWORD(uBytes) = 2048;
    v31 = LocalAlloc(0, 0x800u);
    *v18 = v31;
    if ( !v31 )
      goto LABEL_54;
    PS2ColorSpaceArray = InternalGetPS2CSAFromLCS(pLogColorSpace, v31, &uBytes, &v37);
  }
  if ( !PS2ColorSpaceArray )
  {
LABEL_54:
    DrvIcmDeleteColorTransform(dhpdev, v18);
    v18 = 0;
    goto LABEL_55;
  }
  *((_DWORD *)v18 + 2) = uBytes;
  v25 = *((_QWORD *)dhpdev + 11);
  LODWORD(uBytes) = 0;
  if ( *(_DWORD *)(v25 + 188) != 3 )
    goto LABEL_53;
  v26 = pvTargetProfile;
  v37 = *((_WORD *)dhpdev + 83) != 0;
  if ( pvTargetProfile )
  {
    if ( !v20 )
    {
      if ( (unsigned int)InternalGetPS2PreviewCRD(pvDestProfile, pvTargetProfile, v19, 0, &uBytes, &v37) )
      {
        v27 = LocalAlloc(0, (unsigned int)uBytes);
        v18[2] = v27;
        if ( v27 )
        {
          PS2PreviewCRD = InternalGetPS2PreviewCRD(pvDestProfile, v26, v19, v27, &uBytes, &v37);
          goto LABEL_35;
        }
      }
LABEL_52:
      v13 = 0;
      goto LABEL_53;
    }
    v32 = (__int64 (__fastcall *)(PVOID, _QWORD, PVOID, _QWORD, unsigned int, HLOCAL, SIZE_T *, BOOL *))v40;
    if ( !v40(pvDestProfile, cjDestProfile, pvTargetProfile, cjTargetProfile, v19, 0, &uBytes, &v37) )
      goto LABEL_52;
    v33 = LocalAlloc(0, (unsigned int)uBytes);
    v18[2] = v33;
    if ( !v33 )
      goto LABEL_52;
    PS2PreviewCRD = v32(pvDestProfile, cjDestProfile, v26, cjTargetProfile, v19, v33, &uBytes, &v37);
LABEL_35:
    if ( PS2PreviewCRD )
      goto LABEL_53;
    goto LABEL_52;
  }
  if ( !v20 )
  {
    if ( !(unsigned int)InternalGetPS2ColorRenderingDictionary(pvDestProfile, v19, 0, &uBytes, &v37) )
      goto LABEL_52;
    v34 = LocalAlloc(0, (unsigned int)uBytes);
    v18[2] = v34;
    if ( !v34 )
      goto LABEL_52;
    PS2PreviewCRD = InternalGetPS2ColorRenderingDictionary(pvDestProfile, v19, v34, &uBytes, &v37);
    goto LABEL_35;
  }
  v35 = hModule;
  if ( !((unsigned int (__fastcall *)(PVOID, _QWORD, _QWORD, _QWORD, SIZE_T *, BOOL *))hModule)(
          pvDestProfile,
          cjDestProfile,
          v19,
          0,
          &uBytes,
          &v37) )
    goto LABEL_52;
  v36 = LocalAlloc(0, (unsigned int)uBytes);
  v18[2] = v36;
  if ( !v36
    || !((unsigned int (__fastcall *)(PVOID, _QWORD, _QWORD, HLOCAL, SIZE_T *, BOOL *))v35)(
          pvDestProfile,
          cjDestProfile,
          v19,
          v36,
          &uBytes,
          &v37) )
  {
    goto LABEL_52;
  }
LABEL_53:
  *((_DWORD *)v18 + 6) = uBytes;
  if ( !v13 )
    goto LABEL_54;
LABEL_55:
  if ( v11 )
    FreeLibrary(v11);
  return v18;
}

```

## disassembly

```asm
0x18001a540  mov     [rsp-38h+arg_8], rbx
0x18001a545  mov     [rsp-38h+arg_18], r9d
0x18001a54a  mov     [rsp-38h+arg_10], r8
0x18001a54f  push    rbp
0x18001a550  push    rsi
0x18001a551  push    rdi
0x18001a552  push    r12
0x18001a554  push    r13
0x18001a556  push    r14
0x18001a558  push    r15
0x18001a55a  mov     rbp, rsp
0x18001a55d  sub     rsp, 70h
0x18001a561  mov     r14, rcx
0x18001a564  mov     r12, rdx
0x18001a567  xor     ecx, ecx
0x18001a569  mov     dword ptr [rbp+uBytes], ecx
0x18001a56c  mov     r13d, ecx
0x18001a56f  mov     [rbp+var_20], ecx
0x18001a572  mov     rax, [r14+60h]
0x18001a576  mov     [rbp+hModule], rcx
0x18001a57a  lea     esi, [rcx+1]
0x18001a57d  cmp     dword ptr [rax+7Ch], 2
0x18001a581  jnz     short loc_18001A593
0x18001a583  cmp     [r14+87Ch], esi
0x18001a58a  jbe     short loc_18001A593
0x18001a58c  xor     eax, eax
0x18001a58e  jmp     loc_18001AB19
0x18001a593  mov     r10, [r14+0D90h]
0x18001a59a  test    r10, r10
0x18001a59d  jz      loc_18001A638
0x18001a5a3  cmp     [r10+1D0h], rcx
0x18001a5aa  jz      loc_18001A638
0x18001a5b0  mov     eax, [r14+0D98h]
0x18001a5b7  test    sil, al
0x18001a5ba  jnz     short loc_18001A638
0x18001a5bc  or      eax, esi
0x18001a5be  mov     [r14+0D98h], eax
0x18001a5c5  mov     rax, [r10+1D8h]
0x18001a5cc  mov     rcx, [rax+20h]
0x18001a5d0  mov     [r14+20h], rcx
0x18001a5d4  mov     rax, [r10+1D8h]
0x18001a5db  mov     rcx, [rax+28h]
0x18001a5df  mov     [r14+8], rcx
0x18001a5e3  mov     rax, [r10+1D8h]
0x18001a5ea  mov     rcx, [rax+38h]
0x18001a5ee  mov     [r14+30h], rcx
0x18001a5f2  mov     ecx, [rbp+dwReserved]
0x18001a5f8  mov     rax, [r10+1D0h]
0x18001a5ff  mov     [rsp+70h+var_30], ecx
0x18001a603  mov     ecx, [rbp+cjTargetProfile]
0x18001a606  mov     dword ptr [rsp+70h+var_38], ecx
0x18001a60a  mov     rcx, [rbp+pvTargetProfile]
0x18001a60e  mov     [rsp+70h+var_40], rcx
0x18001a613  mov     ecx, [rbp+cjDestProfile]
0x18001a616  mov     dword ptr [rsp+70h+var_48], ecx
0x18001a61a  mov     rcx, [rbp+pvDestProfile]
0x18001a61e  mov     [rsp+70h+var_50], rcx
0x18001a623  mov     rcx, r14
0x18001a626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a62b  and     dword ptr [r14+0D98h], 0FFFFFFFEh
0x18001a633  jmp     loc_18001AB19
0x18001a638  mov     edx, 20h ; ' '; uBytes
0x18001a63d  lea     ecx, [rdx+20h]; uFlags
0x18001a640  call    cs:__imp_LocalAlloc
0x18001a647  nop     dword ptr [rax+rax+00h]
0x18001a64c  xor     edx, edx
0x18001a64e  mov     rbx, rax
0x18001a651  test    rax, rax
0x18001a654  jnz     short loc_18001A66A
0x18001a656  lea     ecx, [rax+8]; dwErrCode
0x18001a659  call    cs:__imp_SetLastError
0x18001a660  nop     dword ptr [rax+rax+00h]
0x18001a665  jmp     loc_18001A58C
0x18001a66a  mov     ecx, [r12+10h]
0x18001a66f  sub     ecx, esi
0x18001a671  jz      short loc_18001A692
0x18001a673  sub     ecx, esi
0x18001a675  jz      short loc_18001A68E
0x18001a677  sub     ecx, 2
0x18001a67a  jz      short loc_18001A68A
0x18001a67c  cmp     ecx, 4
0x18001a67f  jnz     loc_18001AAF3
0x18001a685  lea     edi, [rcx-1]
0x18001a688  jmp     short loc_18001A697
0x18001a68a  mov     edi, edx
0x18001a68c  jmp     short loc_18001A697
0x18001a68e  mov     edi, esi
0x18001a690  jmp     short loc_18001A697
0x18001a692  mov     edi, 2
0x18001a697  mov     r15d, edx
0x18001a69a  mov     [rax+1Ch], edi
0x18001a69d  lea     rdx, [rbp+hModule]
0x18001a6a1  lea     rcx, aMscmsDll_0; "mscms.dll"
0x18001a6a8  call    LoadLibraryFromSystemDirectory
0x18001a6ad  xor     edx, edx
0x18001a6af  test    eax, eax
0x18001a6b1  jns     short loc_18001A6C4
0x18001a6b3  mov     [rbp+hModule], rdx
0x18001a6b7  mov     r10d, edx
0x18001a6ba  mov     [rbp+var_18], rdx
0x18001a6be  mov     [rbp+var_8], rdx
0x18001a6c2  jmp     short loc_18001A72E
0x18001a6c4  mov     r13, [rbp+hModule]
0x18001a6c8  lea     rdx, aInternalgetps2_1; "InternalGetPS2ColorRenderingDictionary2"
0x18001a6cf  mov     rcx, r13; hModule
0x18001a6d2  call    cs:__imp_GetProcAddress
0x18001a6d9  nop     dword ptr [rax+rax+00h]
0x18001a6de  lea     rdx, aInternalgetps2; "InternalGetPS2ColorSpaceArray2"
0x18001a6e5  mov     rcx, r13; hModule
0x18001a6e8  mov     [rbp+hModule], rax
0x18001a6ec  call    cs:__imp_GetProcAddress
0x18001a6f3  nop     dword ptr [rax+rax+00h]
0x18001a6f8  lea     rdx, aInternalgetps2_0; "InternalGetPS2PreviewCRD2"
0x18001a6ff  mov     rcx, r13; hModule
0x18001a702  mov     [rbp+var_18], rax
0x18001a706  call    cs:__imp_GetProcAddress
0x18001a70d  nop     dword ptr [rax+rax+00h]
0x18001a712  mov     r10, [rbp+var_18]
0x18001a716  xor     edx, edx
0x18001a718  mov     [rbp+var_8], rax
0x18001a71c  cmp     [rbp+hModule], rdx
0x18001a720  jz      short loc_18001A72E
0x18001a722  test    r10, r10
0x18001a725  jz      short loc_18001A72E
0x18001a727  test    rax, rax
0x18001a72a  cmovnz  r15d, esi
0x18001a72e  cmp     [r14+0A6h], dx
0x18001a736  mov     eax, edx
0x18001a738  setnz   al
0x18001a73b  mov     [rbp+var_20], eax
0x18001a73e  mov     rax, [rbp+arg_10]
0x18001a742  test    rax, rax
0x18001a745  jz      loc_18001A92F
0x18001a74b  mov     dword ptr [rbp+uBytes], edx
0x18001a74e  lea     rcx, [rbp+var_20]
0x18001a752  test    r15d, r15d
0x18001a755  jnz     loc_18001A8AA
0x18001a75b  mov     [rsp+70h+var_48], rcx
0x18001a760  lea     r8d, [r15+2]
0x18001a764  lea     rcx, [rbp+uBytes]
0x18001a768  xor     r9d, r9d
0x18001a76b  mov     [rsp+70h+var_50], rcx
0x18001a770  mov     edx, edi
0x18001a772  mov     rcx, rax
0x18001a775  call    cs:__imp_InternalGetPS2ColorSpaceArray
0x18001a77c  nop     dword ptr [rax+rax+00h]
0x18001a781  xor     r12d, r12d
0x18001a784  test    eax, eax
0x18001a786  jz      loc_18001AAF3
0x18001a78c  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18001a78f  xor     ecx, ecx; uFlags
0x18001a791  call    cs:__imp_LocalAlloc
0x18001a798  nop     dword ptr [rax+rax+00h]
0x18001a79d  mov     [rbx], rax
0x18001a7a0  test    rax, rax
0x18001a7a3  jz      loc_18001AAF3
0x18001a7a9  lea     rcx, [rbp+var_20]
0x18001a7ad  mov     r9, rax
0x18001a7b0  mov     [rsp+70h+var_48], rcx
0x18001a7b5  lea     r8d, [r15+2]
0x18001a7b9  lea     rcx, [rbp+uBytes]
0x18001a7bd  mov     edx, edi
0x18001a7bf  mov     [rsp+70h+var_50], rcx
0x18001a7c4  mov     rcx, [rbp+arg_10]
0x18001a7c8  call    cs:__imp_InternalGetPS2ColorSpaceArray
0x18001a7cf  nop     dword ptr [rax+rax+00h]
0x18001a7d4  test    eax, eax
0x18001a7d6  jz      loc_18001AAF3
0x18001a7dc  mov     eax, dword ptr [rbp+uBytes]
0x18001a7df  mov     [rbx+8], eax
0x18001a7e2  mov     rax, [r14+58h]
0x18001a7e6  mov     dword ptr [rbp+uBytes], r12d
0x18001a7ea  cmp     dword ptr [rax+0BCh], 3
0x18001a7f1  jnz     loc_18001AAE9
0x18001a7f7  cmp     [r14+0A6h], r12w
0x18001a7ff  mov     eax, r12d
0x18001a802  mov     r12, [rbp+pvTargetProfile]
0x18001a806  mov     rcx, [rbp+pvDestProfile]
0x18001a80a  setnz   al
0x18001a80d  mov     [rbp+var_20], eax
0x18001a810  lea     rax, [rbp+var_20]
0x18001a814  test    r12, r12
0x18001a817  jz      loc_18001AA03
0x18001a81d  test    r15d, r15d
0x18001a820  jnz     loc_18001A973
0x18001a826  mov     [rsp+70h+var_48], rax
0x18001a82b  xor     r9d, r9d
0x18001a82e  lea     rax, [rbp+uBytes]
0x18001a832  mov     r8d, edi
0x18001a835  mov     rdx, r12
0x18001a838  mov     [rsp+70h+var_50], rax
0x18001a83d  call    cs:__imp_InternalGetPS2PreviewCRD
0x18001a844  nop     dword ptr [rax+rax+00h]
0x18001a849  xor     r15d, r15d
0x18001a84c  test    eax, eax
0x18001a84e  jz      loc_18001AAE6
0x18001a854  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18001a857  xor     ecx, ecx; uFlags
0x18001a859  call    cs:__imp_LocalAlloc
0x18001a860  nop     dword ptr [rax+rax+00h]
0x18001a865  mov     [rbx+10h], rax
0x18001a869  test    rax, rax
0x18001a86c  jz      loc_18001AAE6
0x18001a872  lea     rcx, [rbp+var_20]
0x18001a876  mov     r9, rax
0x18001a879  mov     [rsp+70h+var_48], rcx
0x18001a87e  mov     r8d, edi
0x18001a881  lea     rcx, [rbp+uBytes]
0x18001a885  mov     rdx, r12
0x18001a888  mov     [rsp+70h+var_50], rcx
0x18001a88d  mov     rcx, [rbp+pvDestProfile]
0x18001a891  call    cs:__imp_InternalGetPS2PreviewCRD
0x18001a898  nop     dword ptr [rax+rax+00h]
0x18001a89d  test    eax, eax
0x18001a89f  jnz     loc_18001AAE9
0x18001a8a5  jmp     loc_18001AAE6
0x18001a8aa  mov     r12d, [rbp+arg_18]
0x18001a8ae  mov     r9d, 2
0x18001a8b4  mov     [rsp+70h+var_40], rcx
0x18001a8b9  mov     r8d, edi
0x18001a8bc  lea     rcx, [rbp+uBytes]
0x18001a8c0  mov     [rsp+70h+var_48], rcx
0x18001a8c5  mov     rcx, rax
0x18001a8c8  mov     [rsp+70h+var_50], rdx
0x18001a8cd  mov     rax, r10
0x18001a8d0  mov     edx, r12d
0x18001a8d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8d8  test    eax, eax
0x18001a8da  jz      loc_18001AAF3
0x18001a8e0  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18001a8e3  xor     ecx, ecx; uFlags
0x18001a8e5  call    cs:__imp_LocalAlloc
0x18001a8ec  nop     dword ptr [rax+rax+00h]
0x18001a8f1  mov     [rbx], rax
0x18001a8f4  test    rax, rax
0x18001a8f7  jz      loc_18001AAF3
0x18001a8fd  lea     rcx, [rbp+var_20]
0x18001a901  mov     r9d, 2
0x18001a907  mov     [rsp+70h+var_40], rcx
0x18001a90c  mov     r8d, edi
0x18001a90f  lea     rcx, [rbp+uBytes]
0x18001a913  mov     edx, r12d
0x18001a916  mov     [rsp+70h+var_48], rcx
0x18001a91b  mov     rcx, [rbp+arg_10]
0x18001a91f  mov     [rsp+70h+var_50], rax
0x18001a924  mov     rax, [rbp+var_18]
0x18001a928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a92d  jmp     short loc_18001A96B
0x18001a92f  mov     edx, 800h; uBytes
0x18001a934  xor     ecx, ecx; uFlags
0x18001a936  mov     dword ptr [rbp+uBytes], edx
0x18001a939  call    cs:__imp_LocalAlloc
0x18001a940  nop     dword ptr [rax+rax+00h]
0x18001a945  mov     [rbx], rax
0x18001a948  test    rax, rax
0x18001a94b  jz      loc_18001AAF3
0x18001a951  lea     r9, [rbp+var_20]
0x18001a955  mov     rdx, rax
0x18001a958  lea     r8, [rbp+uBytes]
0x18001a95c  mov     rcx, r12
0x18001a95f  call    cs:__imp_InternalGetPS2CSAFromLCS
0x18001a966  nop     dword ptr [rax+rax+00h]
0x18001a96b  xor     r12d, r12d
0x18001a96e  jmp     loc_18001A7D4
0x18001a973  mov     r15, [rbp+var_8]
0x18001a977  mov     r8, r12
0x18001a97a  mov     r9d, [rbp+cjTargetProfile]
0x18001a97e  mov     edx, [rbp+cjDestProfile]
0x18001a981  mov     [rsp+70h+var_38], rax
0x18001a986  lea     rax, [rbp+uBytes]
0x18001a98a  mov     [rsp+70h+var_40], rax
0x18001a98f  mov     rax, r15
0x18001a992  mov     [rsp+70h+var_48], 0
0x18001a99b  mov     dword ptr [rsp+70h+var_50], edi
0x18001a99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9a4  test    eax, eax
0x18001a9a6  jz      loc_18001AAE3
0x18001a9ac  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18001a9af  xor     ecx, ecx; uFlags
0x18001a9b1  call    cs:__imp_LocalAlloc
0x18001a9b8  nop     dword ptr [rax+rax+00h]
0x18001a9bd  mov     [rbx+10h], rax
0x18001a9c1  test    rax, rax
0x18001a9c4  jz      loc_18001AAE3
0x18001a9ca  mov     r9d, [rbp+cjTargetProfile]
0x18001a9ce  lea     rcx, [rbp+var_20]
0x18001a9d2  mov     edx, [rbp+cjDestProfile]
0x18001a9d5  mov     r8, r12
0x18001a9d8  mov     [rsp+70h+var_38], rcx
0x18001a9dd  lea     rcx, [rbp+uBytes]
0x18001a9e1  mov     [rsp+70h+var_40], rcx
0x18001a9e6  mov     rcx, [rbp+pvDestProfile]
0x18001a9ea  mov     [rsp+70h+var_48], rax
0x18001a9ef  mov     rax, r15
0x18001a9f2  mov     dword ptr [rsp+70h+var_50], edi
0x18001a9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9fb  xor     r15d, r15d
0x18001a9fe  jmp     loc_18001A89D
0x18001aa03  test    r15d, r15d
0x18001aa06  jnz     short loc_18001AA72
  ... truncated ...
```
