# SetNamedSecurityInfoExA

- ea: `0x180051010`
- end: `0x1800514c7`
- name: `SetNamedSecurityInfoExA`
- size: `1207`
- prototype: `__int64 __usercall@<rax>(CHAR *MultiByteString@<rcx>, struct _ACTRL_ALISTA *, struct _ACTRL_ALISTA *, CHAR *, CHAR *, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18002a4a0`
- `0x18002d8a0`
- `0x18004f534`
- `0x180050820`
- `0x180051010`
- `0x180052470`
- `0x1800530b4`
- `0x180074010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800513cf`
- `ntdll!RtlNtStatusToDosError` at `0x1800513cf`
- `KERNEL32!LocalFree` at `0x180051459`
- `KERNEL32!LocalFree` at `0x18005146e`
- `KERNEL32!LocalFree` at `0x18005147f`
- `KERNEL32!LocalFree` at `0x180051493`
- `KERNEL32!LocalFree` at `0x180051459`
- `KERNEL32!LocalFree` at `0x18005146e`
- `KERNEL32!LocalFree` at `0x18005147f`
- `KERNEL32!LocalFree` at `0x180051493`
- `KERNEL32!GetLastError` at `0x180051352`
- `KERNEL32!GetLastError` at `0x180051352`
- `KERNEL32!CreateEventW` at `0x180051334`
- `KERNEL32!CreateEventW` at `0x180051334`
- `KERNEL32!CloseHandle` at `0x180051415`
- `KERNEL32!CloseHandle` at `0x180051415`

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
0x180051010  mov     [rsp+arg_0], rbx
0x180051015  mov     [rsp+arg_10], r8d
0x18005101a  mov     [rsp+arg_8], edx
0x18005101e  push    rsi
0x18005101f  push    rdi
0x180051020  push    r13
0x180051022  push    r14
0x180051024  push    r15
0x180051026  sub     rsp, 140h
0x18005102d  mov     r13, r9
0x180051030  mov     r15d, r8d
0x180051033  mov     rsi, rcx
0x180051036  call    AccProvpInitProviders
0x18005103b  mov     ebx, eax
0x18005103d  xor     edi, edi
0x18005103f  test    eax, eax
0x180051041  jnz     loc_1800514AE
0x180051047  test    rsi, rsi
0x18005104a  jnz     short loc_180051054
0x18005104c  lea     ebx, [rax+57h]
0x18005104f  jmp     loc_1800514AC
0x180051054  mov     eax, r15d
0x180051057  and     eax, 2
0x18005105a  mov     [rsp+168h+var_110], eax
0x18005105e  mov     eax, 57h ; 'W'
0x180051063  jz      short loc_180051070
0x180051065  cmp     [rsp+168h+MultiByteString], rdi
0x18005106d  cmovz   ebx, eax
0x180051070  mov     ecx, r15d
0x180051073  and     ecx, 1
0x180051076  mov     [rsp+168h+var_F8], ecx
0x18005107a  jz      short loc_180051087
0x18005107c  cmp     [rsp+168h+arg_30], rdi
0x180051084  cmovz   ebx, eax
0x180051087  test    ebx, ebx
0x180051089  jnz     loc_1800514AC
0x18005108f  mov     [rsp+168h+var_68], rdi
0x180051097  mov     [rsp+168h+var_58], edi
0x18005109e  lea     rax, ?CleanupConvertNode@@YAXPEAX@Z; CleanupConvertNode(void *)
0x1800510a5  mov     [rsp+168h+var_50], rax
0x1800510ad  mov     [rsp+168h+var_70], rdi
0x1800510b5  mov     [rsp+168h+var_60], rdi
0x1800510bd  mov     [rsp+168h+hMem], rdi
0x1800510c2  mov     r14, rdi
0x1800510c5  mov     [rsp+168h+var_E0], rdi
0x1800510cd  mov     [rsp+168h+var_E8], rdi
0x1800510d5  lea     rdx, [rsp+168h+hMem]; unsigned __int16 **
0x1800510da  mov     rcx, rsi; MultiByteString
0x1800510dd  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x1800510e2  mov     ebx, eax
0x1800510e4  test    eax, eax
0x1800510e6  jnz     short loc_18005110A
0x1800510e8  lea     rdx, [rsp+168h+var_E8]; unsigned __int16 **
0x1800510f0  mov     rcx, r13; MultiByteString
0x1800510f3  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x1800510f8  mov     ebx, eax
0x1800510fa  mov     r14, [rsp+168h+var_E8]
0x180051102  mov     [rsp+168h+var_E0], r14
0x18005110a  mov     r13, rdi
0x18005110d  mov     [rsp+168h+var_C8], rdi
0x180051115  mov     [rsp+168h+var_F0], rdi
0x18005111a  test    ebx, ebx
0x18005111c  jnz     loc_18005147A
0x180051122  lea     rax, [rsp+168h+var_F0]
0x180051127  mov     [rsp+168h+var_148], rax
0x18005112c  mov     r8, r14
0x18005112f  mov     edx, [rsp+168h+arg_8]
0x180051136  mov     rcx, [rsp+168h+hMem]
0x18005113b  call    AccProvpGetProviderForPath
0x180051140  mov     ebx, eax
0x180051142  mov     r13, [rsp+168h+var_F0]
0x180051147  mov     [rsp+168h+var_C8], r13
0x18005114f  test    eax, eax
0x180051151  jnz     loc_18005147A
0x180051157  mov     rax, rdi
0x18005115a  mov     [rsp+168h+var_D0], rax
0x180051162  mov     [rsp+168h+var_108], rax
0x180051167  mov     [rsp+168h+var_D8], rax
0x18005116f  mov     [rsp+168h+var_118], rax
0x180051174  mov     esi, [r13+18h]
0x180051178  not     esi
0x18005117a  and     esi, 1
0x18005117d  test    r15b, 4
0x180051181  jz      short loc_1800511AF
0x180051183  lea     r9, [rsp+168h+var_108]; struct _ACTRL_ALISTW **
0x180051188  mov     r8d, esi; int
0x18005118b  lea     rdx, [rsp+168h+var_70]; struct CSList *
0x180051193  mov     rcx, [rsp+168h+arg_20]; struct _ACTRL_ALISTA *
0x18005119b  call    ?ConvertAListAToNamedBasedW@@YAKPEAU_ACTRL_ALISTA@@AEAVCSList@@HPEAPEAU_ACTRL_ALISTW@@@Z; ConvertAListAToNamedBasedW(_ACTRL_ALISTA *,CSList &,int,_ACTRL_ALISTW * *)
0x1800511a0  mov     ebx, eax
0x1800511a2  mov     rax, [rsp+168h+var_108]
0x1800511a7  mov     [rsp+168h+var_D0], rax
0x1800511af  test    ebx, ebx
0x1800511b1  jnz     loc_18005147A
0x1800511b7  test    r15b, 8
0x1800511bb  jz      short loc_1800511E9
0x1800511bd  lea     r9, [rsp+168h+var_118]; struct _ACTRL_ALISTW **
0x1800511c2  mov     r8d, esi; int
0x1800511c5  lea     rdx, [rsp+168h+var_70]; struct CSList *
0x1800511cd  mov     rcx, [rsp+168h+arg_28]; struct _ACTRL_ALISTA *
0x1800511d5  call    ?ConvertAListAToNamedBasedW@@YAKPEAU_ACTRL_ALISTA@@AEAVCSList@@HPEAPEAU_ACTRL_ALISTW@@@Z; ConvertAListAToNamedBasedW(_ACTRL_ALISTA *,CSList &,int,_ACTRL_ALISTW * *)
0x1800511da  mov     ebx, eax
0x1800511dc  mov     rax, [rsp+168h+var_118]
0x1800511e1  mov     [rsp+168h+var_D8], rax
0x1800511e9  test    ebx, ebx
0x1800511eb  jnz     loc_18005147A
0x1800511f1  xorps   xmm0, xmm0
0x1800511f4  xor     eax, eax
0x1800511f6  movups  [rsp+168h+var_48], xmm0
0x1800511fe  mov     [rsp+168h+var_38], rax
0x180051206  lea     rsi, [rsp+168h+var_48]
0x18005120e  mov     rax, [rsp+168h+arg_40]
0x180051216  test    rax, rax
0x180051219  cmovnz  rsi, rax
0x18005121d  mov     [rsp+168h+var_B8], rsi
0x180051225  movups  [rsp+168h+var_B0], xmm0
0x18005122d  movups  [rsp+168h+var_A0], xmm0
0x180051235  xorps   xmm1, xmm1
0x180051238  movups  [rsp+168h+var_90], xmm1
0x180051240  movups  [rsp+168h+var_80], xmm1
0x180051248  mov     r15, rdi
0x18005124b  mov     [rsp+168h+var_108], rdi
0x180051250  mov     r14, rdi
0x180051253  mov     [rsp+168h+var_C0], rdi
0x18005125b  cmp     [rsp+168h+var_110], edi
0x18005125f  jz      short loc_1800512B3
0x180051261  lea     r15, [rsp+168h+var_B0]
0x180051269  mov     [rsp+168h+var_108], r15
0x18005126e  mov     [rsp+168h+var_118], rdi
0x180051273  lea     rdx, [rsp+168h+var_118]; unsigned __int16 **
0x180051278  mov     rcx, [rsp+168h+MultiByteString]; MultiByteString
0x180051280  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x180051285  mov     ebx, eax
0x180051287  test    eax, eax
0x180051289  jnz     short loc_1800512B3
0x18005128b  mov     qword ptr [rsp+168h+var_B0], rdi
0x180051293  mov     dword ptr [rsp+168h+var_B0+8], edi
0x18005129a  mov     qword ptr [rsp+168h+var_B0+0Ch], 1
0x1800512a6  mov     rax, [rsp+168h+var_118]
0x1800512ab  mov     qword ptr [rsp+168h+var_A0+8], rax
0x1800512b3  test    ebx, ebx
0x1800512b5  jnz     loc_180051450
0x1800512bb  cmp     [rsp+168h+var_F8], edi
0x1800512bf  jz      short loc_180051316
0x1800512c1  lea     r14, [rsp+168h+var_90]
0x1800512c9  mov     [rsp+168h+var_C0], r14
0x1800512d1  mov     [rsp+168h+var_118], rdi
0x1800512d6  lea     rdx, [rsp+168h+var_118]; unsigned __int16 **
0x1800512db  mov     rcx, [rsp+168h+arg_30]; MultiByteString
0x1800512e3  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x1800512e8  mov     ebx, eax
0x1800512ea  test    eax, eax
0x1800512ec  jnz     short loc_180051316
0x1800512ee  mov     qword ptr [rsp+168h+var_90], rdi
0x1800512f6  mov     dword ptr [rsp+168h+var_90+8], edi
0x1800512fd  mov     qword ptr [rsp+168h+var_90+0Ch], 1
0x180051309  mov     rax, [rsp+168h+var_118]
0x18005130e  mov     qword ptr [rsp+168h+var_80+8], rax
0x180051316  test    ebx, ebx
0x180051318  jnz     loc_180051450
0x18005131e  mov     [rsi+8], rdi
0x180051322  mov     [rsi+10h], rdi
0x180051326  mov     [rsi], r13
0x180051329  xor     r9d, r9d; lpName
0x18005132c  xor     r8d, r8d; bInitialState
0x18005132f  lea     edx, [rbx+1]; bManualReset
0x180051332  xor     ecx, ecx; lpEventAttributes
0x180051334  call    cs:__imp_CreateEventW
0x18005133b  nop     dword ptr [rax+rax+00h]
0x180051340  lea     r13, [rsi+10h]
0x180051344  mov     [rsp+168h+var_118], r13
0x180051349  mov     [r13+0], rax
0x18005134d  test    rax, rax
0x180051350  jnz     short loc_180051365
0x180051352  call    cs:__imp_GetLastError
0x180051359  nop     dword ptr [rax+rax+00h]
0x18005135e  mov     ebx, eax
0x180051360  jmp     loc_180051421
0x180051365  mov     [rsp+168h+var_130], rsi
0x18005136a  mov     [rsp+168h+var_138], r15
0x18005136f  mov     [rsp+168h+var_140], r14
0x180051374  mov     rax, [rsp+168h+var_D8]
0x18005137c  mov     [rsp+168h+var_148], rax
0x180051381  mov     r9, [rsp+168h+var_D0]
0x180051389  mov     r8d, [rsp+168h+arg_10]
0x180051391  mov     edx, [rsp+168h+arg_8]
0x180051398  mov     rcx, [rsp+168h+hMem]
0x18005139d  mov     rax, [rsp+168h+var_C8]
0x1800513a5  mov     rax, [rax+48h]
0x1800513a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513ae  mov     ebx, eax
0x1800513b0  mov     [rsp+168h+var_10C], eax
0x1800513b4  jmp     short loc_18005140D
0x1800513b6  mov     rcx, [rsp+168h+var_F0]
0x1800513bb  cmp     qword ptr [rcx+48h], 0
0x1800513c0  jnz     short loc_1800513CD
0x1800513c2  mov     ebx, 4B4h
0x1800513c7  mov     [rsp+168h+var_10C], ebx
0x1800513cb  jmp     short loc_1800513E1
0x1800513cd  mov     ecx, eax; Status
0x1800513cf  call    cs:__imp_RtlNtStatusToDosError
0x1800513d6  nop     dword ptr [rax+rax+00h]
0x1800513db  mov     ebx, eax
0x1800513dd  mov     [rsp+168h+var_10C], eax
0x1800513e1  xor     edi, edi
0x1800513e3  mov     rax, [rsp+168h+var_E8]
0x1800513eb  mov     [rsp+168h+var_E0], rax
0x1800513f3  mov     r15, [rsp+168h+var_108]
0x1800513f8  mov     r14, [rsp+168h+var_C0]
0x180051400  mov     rsi, [rsp+168h+var_B8]
0x180051408  mov     r13, [rsp+168h+var_118]
0x18005140d  test    ebx, ebx
0x18005140f  jz      short loc_180051425
0x180051411  mov     rcx, [r13+0]; hObject
0x180051415  call    cs:__imp_CloseHandle
0x18005141c  nop     dword ptr [rax+rax+00h]
0x180051421  test    ebx, ebx
0x180051423  jnz     short loc_180051450
0x180051425  cmp     rsi, [rsp+168h+arg_40]
0x18005142d  jz      short loc_180051450
0x18005142f  mov     [rsp+168h+var_110], edi
0x180051433  xor     r9d, r9d
0x180051436  lea     r8, [rsp+168h+var_110]
0x18005143b  lea     edx, [r9+1]
0x18005143f  mov     rcx, rsi
0x180051442  call    GetOverlappedAccessResults
0x180051447  mov     ebx, eax
0x180051449  test    eax, eax
0x18005144b  cmovz   ebx, [rsp+168h+var_110]
0x180051450  test    r14, r14
0x180051453  jz      short loc_180051465
0x180051455  mov     rcx, [r14+18h]; hMem
0x180051459  call    cs:__imp_LocalFree
0x180051460  nop     dword ptr [rax+rax+00h]
0x180051465  test    r15, r15
0x180051468  jz      short loc_18005147A
0x18005146a  mov     rcx, [r15+18h]; hMem
0x18005146e  call    cs:__imp_LocalFree
0x180051475  nop     dword ptr [rax+rax+00h]
0x18005147a  mov     rcx, [rsp+168h+hMem]; hMem
0x18005147f  call    cs:__imp_LocalFree
0x180051486  nop     dword ptr [rax+rax+00h]
0x18005148b  mov     rcx, [rsp+168h+var_E0]; hMem
0x180051493  call    cs:__imp_LocalFree
0x18005149a  nop     dword ptr [rax+rax+00h]
0x18005149f  lea     rcx, [rsp+168h+var_70]; this
0x1800514a7  call    ??1CSList@@QEAA@XZ; CSList::~CSList(void)
0x1800514ac  mov     eax, ebx
0x1800514ae  mov     rbx, [rsp+168h+arg_0]
0x1800514b6  add     rsp, 140h
0x1800514bd  pop     r15
0x1800514bf  pop     r14
0x1800514c1  pop     r13
0x1800514c3  pop     rdi
0x1800514c4  pop     rsi
0x1800514c5  retn
```
