# SetNamedSecurityInfoExA

- ea: `0x18004b170`
- end: `0x18004b5f6`
- name: `SetNamedSecurityInfoExA`
- size: `1158`
- prototype: `__int64 __usercall@<rax>(CHAR *MultiByteString@<rcx>, struct _ACTRL_ALISTA *, struct _ACTRL_ALISTA *, CHAR *, CHAR *, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180027084`
- `0x18002a088`
- `0x180049874`
- `0x18004aa30`
- `0x18004b170`
- `0x18004c518`
- `0x18004d0a8`
- `0x180066010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18004b523`
- `ntdll!RtlNtStatusToDosError` at `0x18004b523`
- `KERNEL32!LocalFree` at `0x18004b5a1`
- `KERNEL32!LocalFree` at `0x18004b5b0`
- `KERNEL32!LocalFree` at `0x18004b5bb`
- `KERNEL32!LocalFree` at `0x18004b5c9`
- `KERNEL32!LocalFree` at `0x18004b5a1`
- `KERNEL32!LocalFree` at `0x18004b5b0`
- `KERNEL32!LocalFree` at `0x18004b5bb`
- `KERNEL32!LocalFree` at `0x18004b5c9`
- `KERNEL32!GetLastError` at `0x18004b4ac`
- `KERNEL32!GetLastError` at `0x18004b4ac`
- `KERNEL32!CreateEventW` at `0x18004b494`
- `KERNEL32!CreateEventW` at `0x18004b494`
- `KERNEL32!CloseHandle` at `0x18004b563`
- `KERNEL32!CloseHandle` at `0x18004b563`

## pseudocode

```c
__int64 __fastcall SetNamedSecurityInfoExA(
        CHAR *MultiByteString,
        unsigned int a2,
        unsigned int a3,
        CHAR *a4,
        struct _ACTRL_ALISTA *a5,
        struct _ACTRL_ALISTA *a6,
        CHAR *a7,
        CHAR *MultiByteStringa,
        __int128 *a9)
{
  char v10; // r15
  __int64 result; // rax
  unsigned int ProviderForPath; // ebx
  unsigned __int16 *v14; // r14
  int v15; // r9d
  __int64 v16; // r13
  BOOL v17; // esi
  __int128 *v18; // rsi
  HLOCAL *v19; // r15
  HLOCAL *v20; // r14
  HANDLE EventW; // rax
  struct _ACTRL_ALISTW *v22; // [rsp+50h] [rbp-118h] BYREF
  _DWORD v23[2]; // [rsp+58h] [rbp-110h] BYREF
  struct _ACTRL_ALISTW *v24; // [rsp+60h] [rbp-108h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-100h] BYREF
  int v26; // [rsp+70h] [rbp-F8h]
  __int64 v27; // [rsp+78h] [rbp-F0h] BYREF
  unsigned __int16 *v28; // [rsp+80h] [rbp-E8h] BYREF
  HLOCAL v29; // [rsp+88h] [rbp-E0h]
  struct _ACTRL_ALISTW *v30; // [rsp+90h] [rbp-D8h]
  struct _ACTRL_ALISTW *v31; // [rsp+98h] [rbp-D0h]
  __int64 v32; // [rsp+A0h] [rbp-C8h]
  _OWORD *v33; // [rsp+A8h] [rbp-C0h]
  __int128 *v34; // [rsp+B0h] [rbp-B8h]
  _OWORD v35[2]; // [rsp+B8h] [rbp-B0h] BYREF
  _OWORD v36[2]; // [rsp+D8h] [rbp-90h] BYREF
  _QWORD v37[3]; // [rsp+F8h] [rbp-70h] BYREF
  int v38; // [rsp+110h] [rbp-58h]
  void (__fastcall *v39)(void *); // [rsp+118h] [rbp-50h]
  __int128 v40; // [rsp+120h] [rbp-48h] BYREF
  __int64 v41; // [rsp+130h] [rbp-38h]

  v10 = a3;
  result = AccProvpInitProviders((__int64)MultiByteString);
  ProviderForPath = result;
  if ( !(_DWORD)result )
  {
    if ( !MultiByteString )
      return 87;
    v23[0] = v10 & 2;
    if ( (v10 & 2) != 0 && !MultiByteStringa )
      ProviderForPath = 87;
    v26 = v10 & 1;
    if ( (v10 & 1) != 0 && !a7 )
      ProviderForPath = 87;
    if ( ProviderForPath )
      return ProviderForPath;
    v38 = 0;
    v39 = CleanupConvertNode;
    memset(v37, 0, sizeof(v37));
    hMem = 0;
    v14 = 0;
    v29 = 0;
    v28 = 0;
    ProviderForPath = ConvertStringAToStringW(MultiByteString, (unsigned __int16 **)&hMem);
    if ( !ProviderForPath )
    {
      ProviderForPath = ConvertStringAToStringW(a4, &v28);
      v14 = v28;
      v29 = v28;
    }
    v32 = 0;
    v27 = 0;
    if ( ProviderForPath )
      goto LABEL_43;
    ProviderForPath = AccProvpGetProviderForPath((int)hMem, a2, v14, v15, &v27);
    v16 = v27;
    v32 = v27;
    if ( ProviderForPath )
      goto LABEL_43;
    v31 = 0;
    v24 = 0;
    v30 = 0;
    v22 = 0;
    v17 = (*(_DWORD *)(v27 + 24) & 1) == 0;
    if ( (v10 & 4) != 0 )
    {
      ProviderForPath = ConvertAListAToNamedBasedW(a5, (struct CSList *)v37, (*(_DWORD *)(v27 + 24) & 1) == 0, &v24);
      v31 = v24;
    }
    if ( ProviderForPath )
      goto LABEL_43;
    if ( (v10 & 8) != 0 )
    {
      ProviderForPath = ConvertAListAToNamedBasedW(a6, (struct CSList *)v37, v17, &v22);
      v30 = v22;
    }
    if ( ProviderForPath )
    {
LABEL_43:
      LocalFree(hMem);
      LocalFree(v29);
      CSList::~CSList((CSList *)v37);
      return ProviderForPath;
    }
    v40 = 0;
    v41 = 0;
    v18 = &v40;
    if ( a9 )
      v18 = a9;
    v34 = v18;
    memset(v35, 0, sizeof(v35));
    memset(v36, 0, sizeof(v36));
    v19 = 0;
    v24 = 0;
    v20 = 0;
    v33 = 0;
    if ( v23[0] )
    {
      v19 = (HLOCAL *)v35;
      v24 = (struct _ACTRL_ALISTW *)v35;
      v22 = 0;
      ProviderForPath = ConvertStringAToStringW(MultiByteStringa, (unsigned __int16 **)&v22);
      if ( !ProviderForPath )
      {
        *(_QWORD *)&v35[0] = 0;
        DWORD2(v35[0]) = 0;
        *(_QWORD *)((char *)v35 + 12) = 1;
        *((_QWORD *)&v35[1] + 1) = v22;
      }
    }
    if ( !ProviderForPath )
    {
      if ( v26 )
      {
        v20 = (HLOCAL *)v36;
        v33 = v36;
        v22 = 0;
        ProviderForPath = ConvertStringAToStringW(a7, (unsigned __int16 **)&v22);
        if ( !ProviderForPath )
        {
          *(_QWORD *)&v36[0] = 0;
          DWORD2(v36[0]) = 0;
          *(_QWORD *)((char *)v36 + 12) = 1;
          *((_QWORD *)&v36[1] + 1) = v22;
        }
      }
      if ( !ProviderForPath )
      {
        *((_QWORD *)v18 + 1) = 0;
        *((_QWORD *)v18 + 2) = 0;
        *(_QWORD *)v18 = v16;
        EventW = CreateEventW(0, 1, 0, 0);
        v22 = (struct _ACTRL_ALISTW *)(v18 + 1);
        *((_QWORD *)v18 + 2) = EventW;
        if ( EventW )
        {
          ProviderForPath = (*(__int64 (__fastcall **)(HLOCAL, _QWORD, _QWORD, struct _ACTRL_ALISTW *, struct _ACTRL_ALISTW *, HLOCAL *, HLOCAL *, __int128 *))(v32 + 72))(
                              hMem,
                              a2,
                              a3,
                              v31,
                              v30,
                              v20,
                              v19,
                              v18);
          v23[1] = ProviderForPath;
          if ( !ProviderForPath )
          {
LABEL_36:
            if ( v18 != a9 )
            {
              v23[0] = 0;
              ProviderForPath = GetOverlappedAccessResults(v18, 1, v23);
              if ( !ProviderForPath )
                ProviderForPath = v23[0];
            }
            goto LABEL_39;
          }
          CloseHandle(*((HANDLE *)v18 + 2));
        }
        else
        {
          ProviderForPath = GetLastError();
        }
        if ( !ProviderForPath )
          goto LABEL_36;
      }
    }
LABEL_39:
    if ( v20 )
      LocalFree(v20[3]);
    if ( v19 )
      LocalFree(v19[3]);
    goto LABEL_43;
  }
  return result;
}

```

## disassembly

```asm
0x18004b170  mov     [rsp+arg_0], rbx
0x18004b175  mov     [rsp+arg_10], r8d
0x18004b17a  mov     [rsp+arg_8], edx
0x18004b17e  push    rsi
0x18004b17f  push    rdi
0x18004b180  push    r13
0x18004b182  push    r14
0x18004b184  push    r15
0x18004b186  sub     rsp, 140h
0x18004b18d  mov     r13, r9
0x18004b190  mov     r15d, r8d
0x18004b193  mov     rsi, rcx
0x18004b196  call    AccProvpInitProviders
0x18004b19b  mov     ebx, eax
0x18004b19d  xor     edi, edi
0x18004b19f  test    eax, eax
0x18004b1a1  jnz     loc_18004B5DE
0x18004b1a7  test    rsi, rsi
0x18004b1aa  jnz     short loc_18004B1B4
0x18004b1ac  lea     ebx, [rax+57h]
0x18004b1af  jmp     loc_18004B5DC
0x18004b1b4  mov     eax, r15d
0x18004b1b7  and     eax, 2
0x18004b1ba  mov     [rsp+168h+var_110], eax
0x18004b1be  mov     eax, 57h ; 'W'
0x18004b1c3  jz      short loc_18004B1D0
0x18004b1c5  cmp     [rsp+168h+MultiByteString], rdi
0x18004b1cd  cmovz   ebx, eax
0x18004b1d0  mov     ecx, r15d
0x18004b1d3  and     ecx, 1
0x18004b1d6  mov     [rsp+168h+var_F8], ecx
0x18004b1da  jz      short loc_18004B1E7
0x18004b1dc  cmp     [rsp+168h+arg_30], rdi
0x18004b1e4  cmovz   ebx, eax
0x18004b1e7  test    ebx, ebx
0x18004b1e9  jnz     loc_18004B5DC
0x18004b1ef  mov     [rsp+168h+var_68], rdi
0x18004b1f7  mov     [rsp+168h+var_58], edi
0x18004b1fe  lea     rax, ?CleanupConvertNode@@YAXPEAX@Z; CleanupConvertNode(void *)
0x18004b205  mov     [rsp+168h+var_50], rax
0x18004b20d  mov     [rsp+168h+var_70], rdi
0x18004b215  mov     [rsp+168h+var_60], rdi
0x18004b21d  mov     [rsp+168h+hMem], rdi
0x18004b222  mov     r14, rdi
0x18004b225  mov     [rsp+168h+var_E0], rdi
0x18004b22d  mov     [rsp+168h+var_E8], rdi
0x18004b235  lea     rdx, [rsp+168h+hMem]; unsigned __int16 **
0x18004b23a  mov     rcx, rsi; MultiByteString
0x18004b23d  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x18004b242  mov     ebx, eax
0x18004b244  test    eax, eax
0x18004b246  jnz     short loc_18004B26A
0x18004b248  lea     rdx, [rsp+168h+var_E8]; unsigned __int16 **
0x18004b250  mov     rcx, r13; MultiByteString
0x18004b253  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x18004b258  mov     ebx, eax
0x18004b25a  mov     r14, [rsp+168h+var_E8]
0x18004b262  mov     [rsp+168h+var_E0], r14
0x18004b26a  mov     r13, rdi
0x18004b26d  mov     [rsp+168h+var_C8], rdi
0x18004b275  mov     [rsp+168h+var_F0], rdi
0x18004b27a  test    ebx, ebx
0x18004b27c  jnz     loc_18004B5B6
0x18004b282  lea     rax, [rsp+168h+var_F0]
0x18004b287  mov     [rsp+168h+var_148], rax
0x18004b28c  mov     r8, r14
0x18004b28f  mov     edx, [rsp+168h+arg_8]
0x18004b296  mov     rcx, [rsp+168h+hMem]
0x18004b29b  call    AccProvpGetProviderForPath
0x18004b2a0  mov     ebx, eax
0x18004b2a2  mov     r13, [rsp+168h+var_F0]
0x18004b2a7  mov     [rsp+168h+var_C8], r13
0x18004b2af  test    eax, eax
0x18004b2b1  jnz     loc_18004B5B6
0x18004b2b7  mov     rax, rdi
0x18004b2ba  mov     [rsp+168h+var_D0], rax
0x18004b2c2  mov     [rsp+168h+var_108], rax
0x18004b2c7  mov     [rsp+168h+var_D8], rax
0x18004b2cf  mov     [rsp+168h+var_118], rax
0x18004b2d4  mov     esi, [r13+18h]
0x18004b2d8  not     esi
0x18004b2da  and     esi, 1
0x18004b2dd  test    r15b, 4
0x18004b2e1  jz      short loc_18004B30F
0x18004b2e3  lea     r9, [rsp+168h+var_108]; struct _ACTRL_ALISTW **
0x18004b2e8  mov     r8d, esi; int
0x18004b2eb  lea     rdx, [rsp+168h+var_70]; struct CSList *
0x18004b2f3  mov     rcx, [rsp+168h+arg_20]; struct _ACTRL_ALISTA *
0x18004b2fb  call    ?ConvertAListAToNamedBasedW@@YAKPEAU_ACTRL_ALISTA@@AEAVCSList@@HPEAPEAU_ACTRL_ALISTW@@@Z; ConvertAListAToNamedBasedW(_ACTRL_ALISTA *,CSList &,int,_ACTRL_ALISTW * *)
0x18004b300  mov     ebx, eax
0x18004b302  mov     rax, [rsp+168h+var_108]
0x18004b307  mov     [rsp+168h+var_D0], rax
0x18004b30f  test    ebx, ebx
0x18004b311  jnz     loc_18004B5B6
0x18004b317  test    r15b, 8
0x18004b31b  jz      short loc_18004B349
0x18004b31d  lea     r9, [rsp+168h+var_118]; struct _ACTRL_ALISTW **
0x18004b322  mov     r8d, esi; int
0x18004b325  lea     rdx, [rsp+168h+var_70]; struct CSList *
0x18004b32d  mov     rcx, [rsp+168h+arg_28]; struct _ACTRL_ALISTA *
0x18004b335  call    ?ConvertAListAToNamedBasedW@@YAKPEAU_ACTRL_ALISTA@@AEAVCSList@@HPEAPEAU_ACTRL_ALISTW@@@Z; ConvertAListAToNamedBasedW(_ACTRL_ALISTA *,CSList &,int,_ACTRL_ALISTW * *)
0x18004b33a  mov     ebx, eax
0x18004b33c  mov     rax, [rsp+168h+var_118]
0x18004b341  mov     [rsp+168h+var_D8], rax
0x18004b349  test    ebx, ebx
0x18004b34b  jnz     loc_18004B5B6
0x18004b351  xorps   xmm0, xmm0
0x18004b354  xor     eax, eax
0x18004b356  movups  [rsp+168h+var_48], xmm0
0x18004b35e  mov     [rsp+168h+var_38], rax
0x18004b366  lea     rsi, [rsp+168h+var_48]
0x18004b36e  mov     rax, [rsp+168h+arg_40]
0x18004b376  test    rax, rax
0x18004b379  cmovnz  rsi, rax
0x18004b37d  mov     [rsp+168h+var_B8], rsi
0x18004b385  movups  [rsp+168h+var_B0], xmm0
0x18004b38d  movups  [rsp+168h+var_A0], xmm0
0x18004b395  xorps   xmm1, xmm1
0x18004b398  movups  [rsp+168h+var_90], xmm1
0x18004b3a0  movups  [rsp+168h+var_80], xmm1
0x18004b3a8  mov     r15, rdi
0x18004b3ab  mov     [rsp+168h+var_108], rdi
0x18004b3b0  mov     r14, rdi
0x18004b3b3  mov     [rsp+168h+var_C0], rdi
0x18004b3bb  cmp     [rsp+168h+var_110], edi
0x18004b3bf  jz      short loc_18004B413
0x18004b3c1  lea     r15, [rsp+168h+var_B0]
0x18004b3c9  mov     [rsp+168h+var_108], r15
0x18004b3ce  mov     [rsp+168h+var_118], rdi
0x18004b3d3  lea     rdx, [rsp+168h+var_118]; unsigned __int16 **
0x18004b3d8  mov     rcx, [rsp+168h+MultiByteString]; MultiByteString
0x18004b3e0  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x18004b3e5  mov     ebx, eax
0x18004b3e7  test    eax, eax
0x18004b3e9  jnz     short loc_18004B413
0x18004b3eb  mov     qword ptr [rsp+168h+var_B0], rdi
0x18004b3f3  mov     dword ptr [rsp+168h+var_B0+8], edi
0x18004b3fa  mov     qword ptr [rsp+168h+var_B0+0Ch], 1
0x18004b406  mov     rax, [rsp+168h+var_118]
0x18004b40b  mov     qword ptr [rsp+168h+var_A0+8], rax
0x18004b413  test    ebx, ebx
0x18004b415  jnz     loc_18004B598
0x18004b41b  cmp     [rsp+168h+var_F8], edi
0x18004b41f  jz      short loc_18004B476
0x18004b421  lea     r14, [rsp+168h+var_90]
0x18004b429  mov     [rsp+168h+var_C0], r14
0x18004b431  mov     [rsp+168h+var_118], rdi
0x18004b436  lea     rdx, [rsp+168h+var_118]; unsigned __int16 **
0x18004b43b  mov     rcx, [rsp+168h+arg_30]; MultiByteString
0x18004b443  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x18004b448  mov     ebx, eax
0x18004b44a  test    eax, eax
0x18004b44c  jnz     short loc_18004B476
0x18004b44e  mov     qword ptr [rsp+168h+var_90], rdi
0x18004b456  mov     dword ptr [rsp+168h+var_90+8], edi
0x18004b45d  mov     qword ptr [rsp+168h+var_90+0Ch], 1
0x18004b469  mov     rax, [rsp+168h+var_118]
0x18004b46e  mov     qword ptr [rsp+168h+var_80+8], rax
0x18004b476  test    ebx, ebx
0x18004b478  jnz     loc_18004B598
0x18004b47e  mov     [rsi+8], rdi
0x18004b482  mov     [rsi+10h], rdi
0x18004b486  mov     [rsi], r13
0x18004b489  xor     r9d, r9d; lpName
0x18004b48c  xor     r8d, r8d; bInitialState
0x18004b48f  lea     edx, [rbx+1]; bManualReset
0x18004b492  xor     ecx, ecx; lpEventAttributes
0x18004b494  call    cs:__imp_CreateEventW
0x18004b49a  lea     r13, [rsi+10h]
0x18004b49e  mov     [rsp+168h+var_118], r13
0x18004b4a3  mov     [r13+0], rax
0x18004b4a7  test    rax, rax
0x18004b4aa  jnz     short loc_18004B4B9
0x18004b4ac  call    cs:__imp_GetLastError
0x18004b4b2  mov     ebx, eax
0x18004b4b4  jmp     loc_18004B569
0x18004b4b9  mov     [rsp+168h+var_130], rsi
0x18004b4be  mov     [rsp+168h+var_138], r15
0x18004b4c3  mov     [rsp+168h+var_140], r14
0x18004b4c8  mov     rax, [rsp+168h+var_D8]
0x18004b4d0  mov     [rsp+168h+var_148], rax
0x18004b4d5  mov     r9, [rsp+168h+var_D0]
0x18004b4dd  mov     r8d, [rsp+168h+arg_10]
0x18004b4e5  mov     edx, [rsp+168h+arg_8]
0x18004b4ec  mov     rcx, [rsp+168h+hMem]
0x18004b4f1  mov     rax, [rsp+168h+var_C8]
0x18004b4f9  mov     rax, [rax+48h]
0x18004b4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b502  mov     ebx, eax
0x18004b504  mov     [rsp+168h+var_10C], eax
0x18004b508  jmp     short loc_18004B55B
0x18004b50a  mov     rcx, [rsp+168h+var_F0]
0x18004b50f  cmp     qword ptr [rcx+48h], 0
0x18004b514  jnz     short loc_18004B521
0x18004b516  mov     ebx, 4B4h
0x18004b51b  mov     [rsp+168h+var_10C], ebx
0x18004b51f  jmp     short loc_18004B52F
0x18004b521  mov     ecx, eax; Status
0x18004b523  call    cs:__imp_RtlNtStatusToDosError
0x18004b529  mov     ebx, eax
0x18004b52b  mov     [rsp+168h+var_10C], eax
0x18004b52f  xor     edi, edi
0x18004b531  mov     rax, [rsp+168h+var_E8]
0x18004b539  mov     [rsp+168h+var_E0], rax
0x18004b541  mov     r15, [rsp+168h+var_108]
0x18004b546  mov     r14, [rsp+168h+var_C0]
0x18004b54e  mov     rsi, [rsp+168h+var_B8]
0x18004b556  mov     r13, [rsp+168h+var_118]
0x18004b55b  test    ebx, ebx
0x18004b55d  jz      short loc_18004B56D
0x18004b55f  mov     rcx, [r13+0]; hObject
0x18004b563  call    cs:__imp_CloseHandle
0x18004b569  test    ebx, ebx
0x18004b56b  jnz     short loc_18004B598
0x18004b56d  cmp     rsi, [rsp+168h+arg_40]
0x18004b575  jz      short loc_18004B598
0x18004b577  mov     [rsp+168h+var_110], edi
0x18004b57b  xor     r9d, r9d
0x18004b57e  lea     r8, [rsp+168h+var_110]
0x18004b583  lea     edx, [r9+1]
0x18004b587  mov     rcx, rsi
0x18004b58a  call    GetOverlappedAccessResults
0x18004b58f  mov     ebx, eax
0x18004b591  test    eax, eax
0x18004b593  cmovz   ebx, [rsp+168h+var_110]
0x18004b598  test    r14, r14
0x18004b59b  jz      short loc_18004B5A7
0x18004b59d  mov     rcx, [r14+18h]; hMem
0x18004b5a1  call    cs:__imp_LocalFree
0x18004b5a7  test    r15, r15
0x18004b5aa  jz      short loc_18004B5B6
0x18004b5ac  mov     rcx, [r15+18h]; hMem
0x18004b5b0  call    cs:__imp_LocalFree
0x18004b5b6  mov     rcx, [rsp+168h+hMem]; hMem
0x18004b5bb  call    cs:__imp_LocalFree
0x18004b5c1  mov     rcx, [rsp+168h+var_E0]; hMem
0x18004b5c9  call    cs:__imp_LocalFree
0x18004b5cf  lea     rcx, [rsp+168h+var_70]; this
0x18004b5d7  call    ??1CSList@@QEAA@XZ; CSList::~CSList(void)
0x18004b5dc  mov     eax, ebx
0x18004b5de  mov     rbx, [rsp+168h+arg_0]
0x18004b5e6  add     rsp, 140h
0x18004b5ed  pop     r15
0x18004b5ef  pop     r14
0x18004b5f1  pop     r13
0x18004b5f3  pop     rdi
0x18004b5f4  pop     rsi
0x18004b5f5  retn
```
