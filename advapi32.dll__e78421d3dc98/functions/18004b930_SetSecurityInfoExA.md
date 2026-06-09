# SetSecurityInfoExA

- ea: `0x18004b930`
- end: `0x18004bd4e`
- name: `SetSecurityInfoExA`
- size: `1054`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180027084`
- `0x18002a088`
- `0x180049874`
- `0x18004aa30`
- `0x18004b930`
- `0x18004c518`
- `0x18004d000`
- `0x180066010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18004bc99`
- `ntdll!RtlNtStatusToDosError` at `0x18004bc99`
- `KERNEL32!LocalFree` at `0x18004bd06`
- `KERNEL32!LocalFree` at `0x18004bd15`
- `KERNEL32!LocalFree` at `0x18004bd20`
- `KERNEL32!LocalFree` at `0x18004bd06`
- `KERNEL32!LocalFree` at `0x18004bd15`
- `KERNEL32!LocalFree` at `0x18004bd20`
- `KERNEL32!GetLastError` at `0x18004bc26`
- `KERNEL32!GetLastError` at `0x18004bc26`
- `KERNEL32!CreateEventW` at `0x18004bc0f`
- `KERNEL32!CreateEventW` at `0x18004bc0f`
- `KERNEL32!CloseHandle` at `0x18004bcc8`
- `KERNEL32!CloseHandle` at `0x18004bcc8`

## pseudocode

```c
__int64 __fastcall SetSecurityInfoExA(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        CHAR *a4,
        struct _ACTRL_ALISTA *a5,
        struct _ACTRL_ALISTA *a6,
        CHAR *a7,
        CHAR *MultiByteString,
        HANDLE **a9)
{
  __int64 result; // rax
  unsigned int ProviderForHandle; // ebx
  int v15; // r9d
  HANDLE *v16; // r14
  HANDLE **v17; // r14
  HLOCAL *v18; // r15
  HLOCAL *v19; // r13
  HANDLE *v20; // rbx
  HANDLE *EventW; // rax
  struct _ACTRL_ALISTW *v22; // [rsp+50h] [rbp-F8h] BYREF
  HANDLE *v23; // [rsp+58h] [rbp-F0h] BYREF
  unsigned int v24; // [rsp+60h] [rbp-E8h]
  struct _ACTRL_ALISTW *v25; // [rsp+68h] [rbp-E0h] BYREF
  HANDLE *v26; // [rsp+70h] [rbp-D8h]
  HLOCAL hMem; // [rsp+78h] [rbp-D0h] BYREF
  struct _ACTRL_ALISTW *v28; // [rsp+80h] [rbp-C8h]
  struct _ACTRL_ALISTW *v29; // [rsp+88h] [rbp-C0h]
  _OWORD *v30; // [rsp+90h] [rbp-B8h]
  HANDLE **v31; // [rsp+98h] [rbp-B0h]
  _OWORD v32[2]; // [rsp+A0h] [rbp-A8h] BYREF
  _OWORD v33[2]; // [rsp+C0h] [rbp-88h] BYREF
  _QWORD v34[3]; // [rsp+E0h] [rbp-68h] BYREF
  int v35; // [rsp+F8h] [rbp-50h]
  void (__fastcall *v36)(void *); // [rsp+100h] [rbp-48h]
  __int128 v37; // [rsp+108h] [rbp-40h] BYREF
  __int64 v38; // [rsp+118h] [rbp-30h]

  result = AccProvpInitProviders(a1);
  ProviderForHandle = result;
  if ( !(_DWORD)result )
  {
    if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      ProviderForHandle = 6;
    }
    else
    {
      if ( (a3 & 2) != 0 && !MultiByteString )
        ProviderForHandle = 87;
      if ( (a3 & 1) != 0 && !a7 )
        ProviderForHandle = 87;
    }
    if ( ProviderForHandle )
      return ProviderForHandle;
    v35 = 0;
    v36 = CleanupConvertNode;
    memset(v34, 0, sizeof(v34));
    hMem = 0;
    ProviderForHandle = ConvertStringAToStringW(a4, (unsigned __int16 **)&hMem);
    v16 = 0;
    v26 = 0;
    v23 = 0;
    if ( !ProviderForHandle )
    {
      ProviderForHandle = AccProvpGetProviderForHandle(a1, a2, (const wchar_t *)hMem, v15, (__int64)&v23);
      v16 = v23;
      v26 = v23;
    }
    if ( ProviderForHandle )
      goto LABEL_42;
    v29 = 0;
    v25 = 0;
    v28 = 0;
    v22 = 0;
    if ( (a3 & 4) != 0 )
    {
      ProviderForHandle = ConvertAListAToNamedBasedW(a5, (struct CSList *)v34, (_DWORD)v16[3] & 1, &v25);
      v29 = v25;
    }
    if ( ProviderForHandle )
      goto LABEL_42;
    if ( (a3 & 8) != 0 )
    {
      ProviderForHandle = ConvertAListAToNamedBasedW(a6, (struct CSList *)v34, (_DWORD)v16[3] & 1, &v22);
      v28 = v22;
    }
    if ( ProviderForHandle )
    {
LABEL_42:
      LocalFree(hMem);
      CSList::~CSList((CSList *)v34);
      return ProviderForHandle;
    }
    v37 = 0;
    v38 = 0;
    v17 = (HANDLE **)&v37;
    if ( a9 )
      v17 = a9;
    v31 = v17;
    memset(v32, 0, sizeof(v32));
    memset(v33, 0, sizeof(v33));
    v18 = 0;
    v25 = 0;
    v19 = 0;
    v30 = 0;
    if ( (a3 & 2) != 0 )
    {
      v18 = (HLOCAL *)v32;
      v25 = (struct _ACTRL_ALISTW *)v32;
      v22 = 0;
      ProviderForHandle = ConvertStringAToStringW(MultiByteString, (unsigned __int16 **)&v22);
      if ( !ProviderForHandle )
      {
        *(_QWORD *)&v32[0] = 0;
        DWORD2(v32[0]) = 0;
        *(_QWORD *)((char *)v32 + 12) = 1;
        *((_QWORD *)&v32[1] + 1) = v22;
      }
    }
    if ( !ProviderForHandle )
    {
      if ( (a3 & 1) != 0 )
      {
        v19 = (HLOCAL *)v33;
        v30 = v33;
        v22 = 0;
        ProviderForHandle = ConvertStringAToStringW(a7, (unsigned __int16 **)&v22);
        if ( !ProviderForHandle )
        {
          *(_QWORD *)&v33[0] = 0;
          DWORD2(v33[0]) = 0;
          *(_QWORD *)((char *)v33 + 12) = 1;
          *((_QWORD *)&v33[1] + 1) = v22;
        }
      }
      if ( !ProviderForHandle )
      {
        v17[1] = 0;
        v17[2] = 0;
        v20 = v26;
        *v17 = v26;
        EventW = (HANDLE *)CreateEventW(0, 1, 0, 0);
        v26 = (HANDLE *)(v17 + 2);
        v17[2] = EventW;
        if ( EventW )
        {
          ProviderForHandle = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, struct _ACTRL_ALISTW *, struct _ACTRL_ALISTW *, HLOCAL *, HLOCAL *, HANDLE **))v20[17])(
                                a1,
                                a2,
                                a3,
                                v29,
                                v28,
                                v19,
                                v18,
                                v17);
          v24 = ProviderForHandle;
          if ( !ProviderForHandle )
          {
LABEL_35:
            if ( v17 != a9 )
            {
              LODWORD(v23) = 0;
              ProviderForHandle = GetOverlappedAccessResults(v17, 1, &v23);
              if ( !ProviderForHandle )
                ProviderForHandle = (unsigned int)v23;
            }
            goto LABEL_38;
          }
          CloseHandle(*v26);
        }
        else
        {
          ProviderForHandle = GetLastError();
        }
        if ( !ProviderForHandle )
          goto LABEL_35;
      }
    }
LABEL_38:
    if ( v19 )
      LocalFree(v19[3]);
    if ( v18 )
      LocalFree(v18[3]);
    goto LABEL_42;
  }
  return result;
}

```

## disassembly

```asm
0x18004b930  mov     [rsp+arg_10], rbx
0x18004b935  mov     [rsp+arg_8], edx
0x18004b939  mov     [rsp+arg_0], rcx
0x18004b93e  push    rdi
0x18004b93f  push    r12
0x18004b941  push    r13
0x18004b943  push    r14
0x18004b945  push    r15
0x18004b947  sub     rsp, 120h
0x18004b94e  mov     r14, r9
0x18004b951  mov     r12d, r8d
0x18004b954  mov     r13d, edx
0x18004b957  mov     r15, rcx
0x18004b95a  call    AccProvpInitProviders
0x18004b95f  mov     ebx, eax
0x18004b961  xor     edi, edi
0x18004b963  test    eax, eax
0x18004b965  jnz     loc_18004BD35
0x18004b96b  lea     rax, [r15-1]
0x18004b96f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004b973  ja      short loc_18004B99D
0x18004b975  lea     eax, [rbx+57h]
0x18004b978  test    r12b, 2
0x18004b97c  jz      short loc_18004B989
0x18004b97e  cmp     [rsp+148h+MultiByteString], rdi
0x18004b986  cmovz   ebx, eax
0x18004b989  test    r12b, 1
0x18004b98d  jz      short loc_18004B9A2
0x18004b98f  cmp     [rsp+148h+arg_30], rdi
0x18004b997  jnz     short loc_18004B9A2
0x18004b999  mov     ebx, eax
0x18004b99b  jmp     short loc_18004B9A2
0x18004b99d  mov     ebx, 6
0x18004b9a2  test    ebx, ebx
0x18004b9a4  jnz     loc_18004BD33
0x18004b9aa  mov     [rsp+148h+var_60], rdi
0x18004b9b2  mov     [rsp+148h+var_50], edi
0x18004b9b9  lea     rax, ?CleanupConvertNode@@YAXPEAX@Z; CleanupConvertNode(void *)
0x18004b9c0  mov     [rsp+148h+var_48], rax
0x18004b9c8  mov     [rsp+148h+var_68], rdi
0x18004b9d0  mov     [rsp+148h+var_58], rdi
0x18004b9d8  mov     [rsp+148h+hMem], rdi
0x18004b9dd  lea     rdx, [rsp+148h+hMem]; unsigned __int16 **
0x18004b9e2  mov     rcx, r14; MultiByteString
0x18004b9e5  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x18004b9ea  mov     ebx, eax
0x18004b9ec  mov     r14, rdi
0x18004b9ef  mov     [rsp+148h+var_D8], rdi
0x18004b9f4  mov     [rsp+148h+var_F0], rdi
0x18004b9f9  test    eax, eax
0x18004b9fb  jnz     short loc_18004BA23
0x18004b9fd  lea     rax, [rsp+148h+var_F0]
0x18004ba02  mov     [rsp+148h+var_128], rax
0x18004ba07  mov     r8, [rsp+148h+hMem]
0x18004ba0c  mov     edx, r13d
0x18004ba0f  mov     rcx, r15
0x18004ba12  call    AccProvpGetProviderForHandle
0x18004ba17  mov     ebx, eax
0x18004ba19  mov     r14, [rsp+148h+var_F0]
0x18004ba1e  mov     [rsp+148h+var_D8], r14
0x18004ba23  test    ebx, ebx
0x18004ba25  jnz     loc_18004BD1B
0x18004ba2b  mov     rax, rdi
0x18004ba2e  mov     [rsp+148h+var_C0], rax
0x18004ba36  mov     [rsp+148h+var_E0], rax
0x18004ba3b  mov     [rsp+148h+var_C8], rax
0x18004ba43  mov     [rsp+148h+var_F8], rax
0x18004ba48  test    r12b, 4
0x18004ba4c  jz      short loc_18004BA7F
0x18004ba4e  mov     r8d, [r14+18h]
0x18004ba52  and     r8d, 1; int
0x18004ba56  lea     r9, [rsp+148h+var_E0]; struct _ACTRL_ALISTW **
0x18004ba5b  lea     rdx, [rsp+148h+var_68]; struct CSList *
0x18004ba63  mov     rcx, [rsp+148h+arg_20]; struct _ACTRL_ALISTA *
0x18004ba6b  call    ?ConvertAListAToNamedBasedW@@YAKPEAU_ACTRL_ALISTA@@AEAVCSList@@HPEAPEAU_ACTRL_ALISTW@@@Z; ConvertAListAToNamedBasedW(_ACTRL_ALISTA *,CSList &,int,_ACTRL_ALISTW * *)
0x18004ba70  mov     ebx, eax
0x18004ba72  mov     rax, [rsp+148h+var_E0]
0x18004ba77  mov     [rsp+148h+var_C0], rax
0x18004ba7f  test    ebx, ebx
0x18004ba81  jnz     loc_18004BD1B
0x18004ba87  test    r12b, 8
0x18004ba8b  jz      short loc_18004BABE
0x18004ba8d  mov     r8d, [r14+18h]
0x18004ba91  and     r8d, 1; int
0x18004ba95  lea     r9, [rsp+148h+var_F8]; struct _ACTRL_ALISTW **
0x18004ba9a  lea     rdx, [rsp+148h+var_68]; struct CSList *
0x18004baa2  mov     rcx, [rsp+148h+arg_28]; struct _ACTRL_ALISTA *
0x18004baaa  call    ?ConvertAListAToNamedBasedW@@YAKPEAU_ACTRL_ALISTA@@AEAVCSList@@HPEAPEAU_ACTRL_ALISTW@@@Z; ConvertAListAToNamedBasedW(_ACTRL_ALISTA *,CSList &,int,_ACTRL_ALISTW * *)
0x18004baaf  mov     ebx, eax
0x18004bab1  mov     rax, [rsp+148h+var_F8]
0x18004bab6  mov     [rsp+148h+var_C8], rax
0x18004babe  test    ebx, ebx
0x18004bac0  jnz     loc_18004BD1B
0x18004bac6  xorps   xmm0, xmm0
0x18004bac9  xor     eax, eax
0x18004bacb  movups  [rsp+148h+var_40], xmm0
0x18004bad3  mov     [rsp+148h+var_30], rax
0x18004badb  lea     r14, [rsp+148h+var_40]
0x18004bae3  mov     rax, [rsp+148h+arg_40]
0x18004baeb  test    rax, rax
0x18004baee  cmovnz  r14, rax
0x18004baf2  mov     [rsp+148h+var_B0], r14
0x18004bafa  movups  [rsp+148h+var_A8], xmm0
0x18004bb02  movups  [rsp+148h+var_98], xmm0
0x18004bb0a  xorps   xmm1, xmm1
0x18004bb0d  movups  [rsp+148h+var_88], xmm1
0x18004bb15  movups  [rsp+148h+var_78], xmm1
0x18004bb1d  mov     r15, rdi
0x18004bb20  mov     [rsp+148h+var_E0], rdi
0x18004bb25  mov     r13, rdi
0x18004bb28  mov     [rsp+148h+var_B8], rdi
0x18004bb30  test    r12b, 2
0x18004bb34  jz      short loc_18004BB88
0x18004bb36  lea     r15, [rsp+148h+var_A8]
0x18004bb3e  mov     [rsp+148h+var_E0], r15
0x18004bb43  mov     [rsp+148h+var_F8], rdi
0x18004bb48  lea     rdx, [rsp+148h+var_F8]; unsigned __int16 **
0x18004bb4d  mov     rcx, [rsp+148h+MultiByteString]; MultiByteString
0x18004bb55  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x18004bb5a  mov     ebx, eax
0x18004bb5c  test    eax, eax
0x18004bb5e  jnz     short loc_18004BB88
0x18004bb60  mov     qword ptr [rsp+148h+var_A8], rdi
0x18004bb68  mov     dword ptr [rsp+148h+var_A8+8], edi
0x18004bb6f  mov     qword ptr [rsp+148h+var_A8+0Ch], 1
0x18004bb7b  mov     rax, [rsp+148h+var_F8]
0x18004bb80  mov     qword ptr [rsp+148h+var_98+8], rax
0x18004bb88  test    ebx, ebx
0x18004bb8a  jnz     loc_18004BCFD
0x18004bb90  test    r12b, 1
0x18004bb94  jz      short loc_18004BBEB
0x18004bb96  lea     r13, [rsp+148h+var_88]
0x18004bb9e  mov     [rsp+148h+var_B8], r13
0x18004bba6  mov     [rsp+148h+var_F8], rdi
0x18004bbab  lea     rdx, [rsp+148h+var_F8]; unsigned __int16 **
0x18004bbb0  mov     rcx, [rsp+148h+arg_30]; MultiByteString
0x18004bbb8  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x18004bbbd  mov     ebx, eax
0x18004bbbf  test    eax, eax
0x18004bbc1  jnz     short loc_18004BBEB
0x18004bbc3  mov     qword ptr [rsp+148h+var_88], rdi
0x18004bbcb  mov     dword ptr [rsp+148h+var_88+8], edi
0x18004bbd2  mov     qword ptr [rsp+148h+var_88+0Ch], 1
0x18004bbde  mov     rax, [rsp+148h+var_F8]
0x18004bbe3  mov     qword ptr [rsp+148h+var_78+8], rax
0x18004bbeb  test    ebx, ebx
0x18004bbed  jnz     loc_18004BCFD
0x18004bbf3  mov     [r14+8], rdi
0x18004bbf7  mov     [r14+10h], rdi
0x18004bbfb  mov     rbx, [rsp+148h+var_D8]
0x18004bc00  mov     [r14], rbx
0x18004bc03  xor     r9d, r9d; lpName
0x18004bc06  xor     r8d, r8d; bInitialState
0x18004bc09  lea     edx, [r9+1]; bManualReset
0x18004bc0d  xor     ecx, ecx; lpEventAttributes
0x18004bc0f  call    cs:__imp_CreateEventW
0x18004bc15  lea     rcx, [r14+10h]
0x18004bc19  mov     [rsp+148h+var_D8], rcx
0x18004bc1e  mov     [rcx], rax
0x18004bc21  test    rax, rax
0x18004bc24  jnz     short loc_18004BC33
0x18004bc26  call    cs:__imp_GetLastError
0x18004bc2c  mov     ebx, eax
0x18004bc2e  jmp     loc_18004BCCE
0x18004bc33  mov     [rsp+148h+var_110], r14
0x18004bc38  mov     [rsp+148h+var_118], r15
0x18004bc3d  mov     [rsp+148h+var_120], r13
0x18004bc42  mov     rax, [rsp+148h+var_C8]
0x18004bc4a  mov     [rsp+148h+var_128], rax
0x18004bc4f  mov     r9, [rsp+148h+var_C0]
0x18004bc57  mov     r8d, r12d
0x18004bc5a  mov     edx, [rsp+148h+arg_8]
0x18004bc61  mov     rcx, [rsp+148h+arg_0]
0x18004bc69  mov     rax, [rbx+88h]
0x18004bc70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc75  mov     ebx, eax
0x18004bc77  mov     [rsp+148h+var_E8], eax
0x18004bc7b  jmp     short loc_18004BCBC
0x18004bc7d  mov     rcx, [rsp+148h+var_F0]
0x18004bc82  cmp     qword ptr [rcx+88h], 0
0x18004bc8a  jnz     short loc_18004BC97
0x18004bc8c  mov     ebx, 4B4h
0x18004bc91  mov     [rsp+148h+var_E8], ebx
0x18004bc95  jmp     short loc_18004BCA5
0x18004bc97  mov     ecx, eax; Status
0x18004bc99  call    cs:__imp_RtlNtStatusToDosError
0x18004bc9f  mov     ebx, eax
0x18004bca1  mov     [rsp+148h+var_E8], eax
0x18004bca5  xor     edi, edi
0x18004bca7  mov     r15, [rsp+148h+var_E0]
0x18004bcac  mov     r13, [rsp+148h+var_B8]
0x18004bcb4  mov     r14, [rsp+148h+var_B0]
0x18004bcbc  test    ebx, ebx
0x18004bcbe  jz      short loc_18004BCD2
0x18004bcc0  mov     rcx, [rsp+148h+var_D8]
0x18004bcc5  mov     rcx, [rcx]; hObject
0x18004bcc8  call    cs:__imp_CloseHandle
0x18004bcce  test    ebx, ebx
0x18004bcd0  jnz     short loc_18004BCFD
0x18004bcd2  cmp     r14, [rsp+148h+arg_40]
0x18004bcda  jz      short loc_18004BCFD
0x18004bcdc  mov     dword ptr [rsp+148h+var_F0], edi
0x18004bce0  xor     r9d, r9d
0x18004bce3  lea     r8, [rsp+148h+var_F0]
0x18004bce8  lea     edx, [r9+1]
0x18004bcec  mov     rcx, r14
0x18004bcef  call    GetOverlappedAccessResults
0x18004bcf4  mov     ebx, eax
0x18004bcf6  test    eax, eax
0x18004bcf8  cmovz   ebx, dword ptr [rsp+148h+var_F0]
0x18004bcfd  test    r13, r13
0x18004bd00  jz      short loc_18004BD0C
0x18004bd02  mov     rcx, [r13+18h]; hMem
0x18004bd06  call    cs:__imp_LocalFree
0x18004bd0c  test    r15, r15
0x18004bd0f  jz      short loc_18004BD1B
0x18004bd11  mov     rcx, [r15+18h]; hMem
0x18004bd15  call    cs:__imp_LocalFree
0x18004bd1b  mov     rcx, [rsp+148h+hMem]; hMem
0x18004bd20  call    cs:__imp_LocalFree
0x18004bd26  lea     rcx, [rsp+148h+var_68]; this
0x18004bd2e  call    ??1CSList@@QEAA@XZ; CSList::~CSList(void)
0x18004bd33  mov     eax, ebx
0x18004bd35  mov     rbx, [rsp+148h+arg_10]
0x18004bd3d  add     rsp, 120h
0x18004bd44  pop     r15
0x18004bd46  pop     r14
0x18004bd48  pop     r13
0x18004bd4a  pop     r12
0x18004bd4c  pop     rdi
0x18004bd4d  retn
```
