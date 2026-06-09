# DrvIcmCreateColorTransform

- ea: `0x180019cb0`
- end: `0x18001a229`
- name: `DrvIcmCreateColorTransform`
- size: `1401`
- prototype: `HANDLE __stdcall(DHPDEV dhpdev, LPLOGCOLORSPACEW pLogColorSpace, PVOID pvSourceProfile, ULONG cjSourceProfile, PVOID pvDestProfile, ULONG cjDestProfile, PVOID pvTargetProfile, ULONG cjTargetProfile, DWORD dwReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180019cb0`
- `0x18001a230`
- `0x180033bc8`
- `0x18005d010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001a208`
- `KERNEL32!FreeLibrary` at `0x18001a208`
- `KERNEL32!GetProcAddress` at `0x180019e36`
- `KERNEL32!GetProcAddress` at `0x180019e4a`
- `KERNEL32!GetProcAddress` at `0x180019e5e`
- `KERNEL32!GetProcAddress` at `0x180019e36`
- `KERNEL32!GetProcAddress` at `0x180019e4a`
- `KERNEL32!GetProcAddress` at `0x180019e5e`
- `KERNEL32!SetLastError` at `0x180019dc3`
- `KERNEL32!SetLastError` at `0x180019dc3`
- `KERNEL32!LocalAlloc` at `0x180019db0`
- `KERNEL32!LocalAlloc` at `0x180019edd`
- `KERNEL32!LocalAlloc` at `0x180019f93`
- `KERNEL32!LocalAlloc` at `0x18001a013`
- `KERNEL32!LocalAlloc` at `0x18001a061`
- `KERNEL32!LocalAlloc` at `0x18001a0cd`
- `KERNEL32!LocalAlloc` at `0x18001a142`
- `KERNEL32!LocalAlloc` at `0x18001a1a2`
- `KERNEL32!LocalAlloc` at `0x180019db0`
- `KERNEL32!LocalAlloc` at `0x180019edd`
- `KERNEL32!LocalAlloc` at `0x180019f93`
- `KERNEL32!LocalAlloc` at `0x18001a013`
- `KERNEL32!LocalAlloc` at `0x18001a061`
- `KERNEL32!LocalAlloc` at `0x18001a0cd`
- `KERNEL32!LocalAlloc` at `0x18001a142`
- `KERNEL32!LocalAlloc` at `0x18001a1a2`
- `mscms!InternalGetPS2ColorSpaceArray` at `0x180019ec7`
- `mscms!InternalGetPS2ColorSpaceArray` at `0x180019f0e`
- `mscms!InternalGetPS2ColorSpaceArray` at `0x180019ec7`
- `mscms!InternalGetPS2ColorSpaceArray` at `0x180019f0e`
- `mscms!InternalGetPS2CSAFromLCS` at `0x18001a081`
- `mscms!InternalGetPS2CSAFromLCS` at `0x18001a081`
- `mscms!InternalGetPS2ColorRenderingDictionary` at `0x18001a12c`
- `mscms!InternalGetPS2ColorRenderingDictionary` at `0x18001a16b`
- `mscms!InternalGetPS2ColorRenderingDictionary` at `0x18001a12c`
- `mscms!InternalGetPS2ColorRenderingDictionary` at `0x18001a16b`
- `mscms!InternalGetPS2PreviewCRD` at `0x180019f7d`
- `mscms!InternalGetPS2PreviewCRD` at `0x180019fc5`
- `mscms!InternalGetPS2PreviewCRD` at `0x180019f7d`
- `mscms!InternalGetPS2PreviewCRD` at `0x180019fc5`

## string_xrefs

- `0x180019e05`: `mscms.dll`

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
0x180019cb0  mov     [rsp-38h+arg_8], rbx
0x180019cb5  mov     [rsp-38h+arg_18], r9d
0x180019cba  mov     [rsp-38h+arg_10], r8
0x180019cbf  push    rbp
0x180019cc0  push    rsi
0x180019cc1  push    rdi
0x180019cc2  push    r12
0x180019cc4  push    r13
0x180019cc6  push    r14
0x180019cc8  push    r15
0x180019cca  mov     rbp, rsp
0x180019ccd  sub     rsp, 70h
0x180019cd1  mov     r14, rcx
0x180019cd4  mov     r12, rdx
0x180019cd7  xor     ecx, ecx
0x180019cd9  mov     dword ptr [rbp+uBytes], ecx
0x180019cdc  mov     r13d, ecx
0x180019cdf  mov     [rbp+var_20], ecx
0x180019ce2  mov     rax, [r14+60h]
0x180019ce6  mov     [rbp+hModule], rcx
0x180019cea  lea     esi, [rcx+1]
0x180019ced  cmp     dword ptr [rax+7Ch], 2
0x180019cf1  jnz     short loc_180019D03
0x180019cf3  cmp     [r14+87Ch], esi
0x180019cfa  jbe     short loc_180019D03
0x180019cfc  xor     eax, eax
0x180019cfe  jmp     loc_18001A211
0x180019d03  mov     r10, [r14+0D90h]
0x180019d0a  test    r10, r10
0x180019d0d  jz      loc_180019DA8
0x180019d13  cmp     [r10+1D0h], rcx
0x180019d1a  jz      loc_180019DA8
0x180019d20  mov     eax, [r14+0D98h]
0x180019d27  test    sil, al
0x180019d2a  jnz     short loc_180019DA8
0x180019d2c  or      eax, esi
0x180019d2e  mov     [r14+0D98h], eax
0x180019d35  mov     rax, [r10+1D8h]
0x180019d3c  mov     rcx, [rax+20h]
0x180019d40  mov     [r14+20h], rcx
0x180019d44  mov     rax, [r10+1D8h]
0x180019d4b  mov     rcx, [rax+28h]
0x180019d4f  mov     [r14+8], rcx
0x180019d53  mov     rax, [r10+1D8h]
0x180019d5a  mov     rcx, [rax+38h]
0x180019d5e  mov     [r14+30h], rcx
0x180019d62  mov     ecx, [rbp+dwReserved]
0x180019d68  mov     rax, [r10+1D0h]
0x180019d6f  mov     [rsp+70h+var_30], ecx
0x180019d73  mov     ecx, [rbp+cjTargetProfile]
0x180019d76  mov     dword ptr [rsp+70h+var_38], ecx
0x180019d7a  mov     rcx, [rbp+pvTargetProfile]
0x180019d7e  mov     [rsp+70h+var_40], rcx
0x180019d83  mov     ecx, [rbp+cjDestProfile]
0x180019d86  mov     dword ptr [rsp+70h+var_48], ecx
0x180019d8a  mov     rcx, [rbp+pvDestProfile]
0x180019d8e  mov     [rsp+70h+var_50], rcx
0x180019d93  mov     rcx, r14
0x180019d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d9b  and     dword ptr [r14+0D98h], 0FFFFFFFEh
0x180019da3  jmp     loc_18001A211
0x180019da8  mov     edx, 20h ; ' '; uBytes
0x180019dad  lea     ecx, [rdx+20h]; uFlags
0x180019db0  call    cs:__imp_LocalAlloc
0x180019db6  xor     edx, edx
0x180019db8  mov     rbx, rax
0x180019dbb  test    rax, rax
0x180019dbe  jnz     short loc_180019DCE
0x180019dc0  lea     ecx, [rax+8]; dwErrCode
0x180019dc3  call    cs:__imp_SetLastError
0x180019dc9  jmp     loc_180019CFC
0x180019dce  mov     ecx, [r12+10h]
0x180019dd3  sub     ecx, esi
0x180019dd5  jz      short loc_180019DF6
0x180019dd7  sub     ecx, esi
0x180019dd9  jz      short loc_180019DF2
0x180019ddb  sub     ecx, 2
0x180019dde  jz      short loc_180019DEE
0x180019de0  cmp     ecx, 4
0x180019de3  jnz     loc_18001A1F1
0x180019de9  lea     edi, [rcx-1]
0x180019dec  jmp     short loc_180019DFB
0x180019dee  mov     edi, edx
0x180019df0  jmp     short loc_180019DFB
0x180019df2  mov     edi, esi
0x180019df4  jmp     short loc_180019DFB
0x180019df6  mov     edi, 2
0x180019dfb  mov     r15d, edx
0x180019dfe  mov     [rax+1Ch], edi
0x180019e01  lea     rdx, [rbp+hModule]
0x180019e05  lea     rcx, aMscmsDll_0; "mscms.dll"
0x180019e0c  call    LoadLibraryFromSystemDirectory
0x180019e11  xor     edx, edx
0x180019e13  test    eax, eax
0x180019e15  jns     short loc_180019E28
0x180019e17  mov     [rbp+hModule], rdx
0x180019e1b  mov     r10d, edx
0x180019e1e  mov     [rbp+var_18], rdx
0x180019e22  mov     [rbp+var_8], rdx
0x180019e26  jmp     short loc_180019E80
0x180019e28  mov     r13, [rbp+hModule]
0x180019e2c  lea     rdx, aInternalgetps2_1; "InternalGetPS2ColorRenderingDictionary2"
0x180019e33  mov     rcx, r13; hModule
0x180019e36  call    cs:__imp_GetProcAddress
0x180019e3c  lea     rdx, aInternalgetps2; "InternalGetPS2ColorSpaceArray2"
0x180019e43  mov     rcx, r13; hModule
0x180019e46  mov     [rbp+hModule], rax
0x180019e4a  call    cs:__imp_GetProcAddress
0x180019e50  lea     rdx, aInternalgetps2_0; "InternalGetPS2PreviewCRD2"
0x180019e57  mov     rcx, r13; hModule
0x180019e5a  mov     [rbp+var_18], rax
0x180019e5e  call    cs:__imp_GetProcAddress
0x180019e64  mov     r10, [rbp+var_18]
0x180019e68  xor     edx, edx
0x180019e6a  mov     [rbp+var_8], rax
0x180019e6e  cmp     [rbp+hModule], rdx
0x180019e72  jz      short loc_180019E80
0x180019e74  test    r10, r10
0x180019e77  jz      short loc_180019E80
0x180019e79  test    rax, rax
0x180019e7c  cmovnz  r15d, esi
0x180019e80  cmp     [r14+0A6h], dx
0x180019e88  mov     eax, edx
0x180019e8a  setnz   al
0x180019e8d  mov     [rbp+var_20], eax
0x180019e90  mov     rax, [rbp+arg_10]
0x180019e94  test    rax, rax
0x180019e97  jz      loc_18001A057
0x180019e9d  mov     dword ptr [rbp+uBytes], edx
0x180019ea0  lea     rcx, [rbp+var_20]
0x180019ea4  test    r15d, r15d
0x180019ea7  jnz     loc_180019FD8
0x180019ead  mov     [rsp+70h+var_48], rcx
0x180019eb2  lea     r8d, [r15+2]
0x180019eb6  lea     rcx, [rbp+uBytes]
0x180019eba  xor     r9d, r9d
0x180019ebd  mov     [rsp+70h+var_50], rcx
0x180019ec2  mov     edx, edi
0x180019ec4  mov     rcx, rax
0x180019ec7  call    cs:__imp_InternalGetPS2ColorSpaceArray
0x180019ecd  xor     r12d, r12d
0x180019ed0  test    eax, eax
0x180019ed2  jz      loc_18001A1F1
0x180019ed8  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180019edb  xor     ecx, ecx; uFlags
0x180019edd  call    cs:__imp_LocalAlloc
0x180019ee3  mov     [rbx], rax
0x180019ee6  test    rax, rax
0x180019ee9  jz      loc_18001A1F1
0x180019eef  lea     rcx, [rbp+var_20]
0x180019ef3  mov     r9, rax
0x180019ef6  mov     [rsp+70h+var_48], rcx
0x180019efb  lea     r8d, [r15+2]
0x180019eff  lea     rcx, [rbp+uBytes]
0x180019f03  mov     edx, edi
0x180019f05  mov     [rsp+70h+var_50], rcx
0x180019f0a  mov     rcx, [rbp+arg_10]
0x180019f0e  call    cs:__imp_InternalGetPS2ColorSpaceArray
0x180019f14  test    eax, eax
0x180019f16  jz      loc_18001A1F1
0x180019f1c  mov     eax, dword ptr [rbp+uBytes]
0x180019f1f  mov     [rbx+8], eax
0x180019f22  mov     rax, [r14+58h]
0x180019f26  mov     dword ptr [rbp+uBytes], r12d
0x180019f2a  cmp     dword ptr [rax+0BCh], 3
0x180019f31  jnz     loc_18001A1E7
0x180019f37  cmp     [r14+0A6h], r12w
0x180019f3f  mov     eax, r12d
0x180019f42  mov     r12, [rbp+pvTargetProfile]
0x180019f46  mov     rcx, [rbp+pvDestProfile]
0x180019f4a  setnz   al
0x180019f4d  mov     [rbp+var_20], eax
0x180019f50  lea     rax, [rbp+var_20]
0x180019f54  test    r12, r12
0x180019f57  jz      loc_18001A119
0x180019f5d  test    r15d, r15d
0x180019f60  jnz     loc_18001A08F
0x180019f66  mov     [rsp+70h+var_48], rax
0x180019f6b  xor     r9d, r9d
0x180019f6e  lea     rax, [rbp+uBytes]
0x180019f72  mov     r8d, edi
0x180019f75  mov     rdx, r12
0x180019f78  mov     [rsp+70h+var_50], rax
0x180019f7d  call    cs:__imp_InternalGetPS2PreviewCRD
0x180019f83  xor     r15d, r15d
0x180019f86  test    eax, eax
0x180019f88  jz      loc_18001A1E4
0x180019f8e  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180019f91  xor     ecx, ecx; uFlags
0x180019f93  call    cs:__imp_LocalAlloc
0x180019f99  mov     [rbx+10h], rax
0x180019f9d  test    rax, rax
0x180019fa0  jz      loc_18001A1E4
0x180019fa6  lea     rcx, [rbp+var_20]
0x180019faa  mov     r9, rax
0x180019fad  mov     [rsp+70h+var_48], rcx
0x180019fb2  mov     r8d, edi
0x180019fb5  lea     rcx, [rbp+uBytes]
0x180019fb9  mov     rdx, r12
0x180019fbc  mov     [rsp+70h+var_50], rcx
0x180019fc1  mov     rcx, [rbp+pvDestProfile]
0x180019fc5  call    cs:__imp_InternalGetPS2PreviewCRD
0x180019fcb  test    eax, eax
0x180019fcd  jnz     loc_18001A1E7
0x180019fd3  jmp     loc_18001A1E4
0x180019fd8  mov     r12d, [rbp+arg_18]
0x180019fdc  mov     r9d, 2
0x180019fe2  mov     [rsp+70h+var_40], rcx
0x180019fe7  mov     r8d, edi
0x180019fea  lea     rcx, [rbp+uBytes]
0x180019fee  mov     [rsp+70h+var_48], rcx
0x180019ff3  mov     rcx, rax
0x180019ff6  mov     [rsp+70h+var_50], rdx
0x180019ffb  mov     rax, r10
0x180019ffe  mov     edx, r12d
0x18001a001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a006  test    eax, eax
0x18001a008  jz      loc_18001A1F1
0x18001a00e  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18001a011  xor     ecx, ecx; uFlags
0x18001a013  call    cs:__imp_LocalAlloc
0x18001a019  mov     [rbx], rax
0x18001a01c  test    rax, rax
0x18001a01f  jz      loc_18001A1F1
0x18001a025  lea     rcx, [rbp+var_20]
0x18001a029  mov     r9d, 2
0x18001a02f  mov     [rsp+70h+var_40], rcx
0x18001a034  mov     r8d, edi
0x18001a037  lea     rcx, [rbp+uBytes]
0x18001a03b  mov     edx, r12d
0x18001a03e  mov     [rsp+70h+var_48], rcx
0x18001a043  mov     rcx, [rbp+arg_10]
0x18001a047  mov     [rsp+70h+var_50], rax
0x18001a04c  mov     rax, [rbp+var_18]
0x18001a050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a055  jmp     short loc_18001A087
0x18001a057  mov     edx, 800h; uBytes
0x18001a05c  xor     ecx, ecx; uFlags
0x18001a05e  mov     dword ptr [rbp+uBytes], edx
0x18001a061  call    cs:__imp_LocalAlloc
0x18001a067  mov     [rbx], rax
0x18001a06a  test    rax, rax
0x18001a06d  jz      loc_18001A1F1
0x18001a073  lea     r9, [rbp+var_20]
0x18001a077  mov     rdx, rax
0x18001a07a  lea     r8, [rbp+uBytes]
0x18001a07e  mov     rcx, r12
0x18001a081  call    cs:__imp_InternalGetPS2CSAFromLCS
0x18001a087  xor     r12d, r12d
0x18001a08a  jmp     loc_180019F14
0x18001a08f  mov     r15, [rbp+var_8]
0x18001a093  mov     r8, r12
0x18001a096  mov     r9d, [rbp+cjTargetProfile]
0x18001a09a  mov     edx, [rbp+cjDestProfile]
0x18001a09d  mov     [rsp+70h+var_38], rax
0x18001a0a2  lea     rax, [rbp+uBytes]
0x18001a0a6  mov     [rsp+70h+var_40], rax
0x18001a0ab  mov     rax, r15
0x18001a0ae  mov     [rsp+70h+var_48], 0
0x18001a0b7  mov     dword ptr [rsp+70h+var_50], edi
0x18001a0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0c0  test    eax, eax
0x18001a0c2  jz      loc_18001A1E1
0x18001a0c8  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18001a0cb  xor     ecx, ecx; uFlags
0x18001a0cd  call    cs:__imp_LocalAlloc
0x18001a0d3  mov     [rbx+10h], rax
0x18001a0d7  test    rax, rax
0x18001a0da  jz      loc_18001A1E1
0x18001a0e0  mov     r9d, [rbp+cjTargetProfile]
0x18001a0e4  lea     rcx, [rbp+var_20]
0x18001a0e8  mov     edx, [rbp+cjDestProfile]
0x18001a0eb  mov     r8, r12
0x18001a0ee  mov     [rsp+70h+var_38], rcx
0x18001a0f3  lea     rcx, [rbp+uBytes]
0x18001a0f7  mov     [rsp+70h+var_40], rcx
0x18001a0fc  mov     rcx, [rbp+pvDestProfile]
0x18001a100  mov     [rsp+70h+var_48], rax
0x18001a105  mov     rax, r15
0x18001a108  mov     dword ptr [rsp+70h+var_50], edi
0x18001a10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a111  xor     r15d, r15d
0x18001a114  jmp     loc_180019FCB
0x18001a119  test    r15d, r15d
0x18001a11c  jnz     short loc_18001A176
0x18001a11e  lea     r9, [rbp+uBytes]
0x18001a122  mov     [rsp+70h+var_50], rax
0x18001a127  xor     r8d, r8d
0x18001a12a  mov     edx, edi
0x18001a12c  call    cs:__imp_InternalGetPS2ColorRenderingDictionary
0x18001a132  xor     r15d, r15d
0x18001a135  test    eax, eax
0x18001a137  jz      loc_18001A1E4
0x18001a13d  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18001a140  xor     ecx, ecx; uFlags
0x18001a142  call    cs:__imp_LocalAlloc
0x18001a148  mov     [rbx+10h], rax
0x18001a14c  test    rax, rax
0x18001a14f  jz      loc_18001A1E4
0x18001a155  lea     rcx, [rbp+var_20]
  ... truncated ...
```
