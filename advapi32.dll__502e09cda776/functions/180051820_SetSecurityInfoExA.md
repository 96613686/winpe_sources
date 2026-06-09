# SetSecurityInfoExA

- ea: `0x180051820`
- end: `0x180051c69`
- name: `SetSecurityInfoExA`
- size: `1097`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18002a4a0`
- `0x18002d8a0`
- `0x18004f534`
- `0x180050820`
- `0x180051820`
- `0x180052470`
- `0x180053004`
- `0x180074010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180051b95`
- `ntdll!RtlNtStatusToDosError` at `0x180051b95`
- `KERNEL32!LocalFree` at `0x180051c0e`
- `KERNEL32!LocalFree` at `0x180051c23`
- `KERNEL32!LocalFree` at `0x180051c34`
- `KERNEL32!LocalFree` at `0x180051c0e`
- `KERNEL32!LocalFree` at `0x180051c23`
- `KERNEL32!LocalFree` at `0x180051c34`
- `KERNEL32!GetLastError` at `0x180051b1c`
- `KERNEL32!GetLastError` at `0x180051b1c`
- `KERNEL32!CreateEventW` at `0x180051aff`
- `KERNEL32!CreateEventW` at `0x180051aff`
- `KERNEL32!CloseHandle` at `0x180051bca`
- `KERNEL32!CloseHandle` at `0x180051bca`

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
0x180051820  mov     [rsp+arg_10], rbx
0x180051825  mov     [rsp+arg_8], edx
0x180051829  mov     [rsp+arg_0], rcx
0x18005182e  push    rdi
0x18005182f  push    r12
0x180051831  push    r13
0x180051833  push    r14
0x180051835  push    r15
0x180051837  sub     rsp, 120h
0x18005183e  mov     r14, r9
0x180051841  mov     r12d, r8d
0x180051844  mov     r13d, edx
0x180051847  mov     r15, rcx
0x18005184a  call    AccProvpInitProviders
0x18005184f  mov     ebx, eax
0x180051851  xor     edi, edi
0x180051853  test    eax, eax
0x180051855  jnz     loc_180051C4F
0x18005185b  lea     rax, [r15-1]
0x18005185f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180051863  ja      short loc_18005188D
0x180051865  lea     eax, [rbx+57h]
0x180051868  test    r12b, 2
0x18005186c  jz      short loc_180051879
0x18005186e  cmp     [rsp+148h+MultiByteString], rdi
0x180051876  cmovz   ebx, eax
0x180051879  test    r12b, 1
0x18005187d  jz      short loc_180051892
0x18005187f  cmp     [rsp+148h+arg_30], rdi
0x180051887  jnz     short loc_180051892
0x180051889  mov     ebx, eax
0x18005188b  jmp     short loc_180051892
0x18005188d  mov     ebx, 6
0x180051892  test    ebx, ebx
0x180051894  jnz     loc_180051C4D
0x18005189a  mov     [rsp+148h+var_60], rdi
0x1800518a2  mov     [rsp+148h+var_50], edi
0x1800518a9  lea     rax, ?CleanupConvertNode@@YAXPEAX@Z; CleanupConvertNode(void *)
0x1800518b0  mov     [rsp+148h+var_48], rax
0x1800518b8  mov     [rsp+148h+var_68], rdi
0x1800518c0  mov     [rsp+148h+var_58], rdi
0x1800518c8  mov     [rsp+148h+hMem], rdi
0x1800518cd  lea     rdx, [rsp+148h+hMem]; unsigned __int16 **
0x1800518d2  mov     rcx, r14; MultiByteString
0x1800518d5  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x1800518da  mov     ebx, eax
0x1800518dc  mov     r14, rdi
0x1800518df  mov     [rsp+148h+var_D8], rdi
0x1800518e4  mov     [rsp+148h+var_F0], rdi
0x1800518e9  test    eax, eax
0x1800518eb  jnz     short loc_180051913
0x1800518ed  lea     rax, [rsp+148h+var_F0]
0x1800518f2  mov     [rsp+148h+var_128], rax
0x1800518f7  mov     r8, [rsp+148h+hMem]
0x1800518fc  mov     edx, r13d
0x1800518ff  mov     rcx, r15
0x180051902  call    AccProvpGetProviderForHandle
0x180051907  mov     ebx, eax
0x180051909  mov     r14, [rsp+148h+var_F0]
0x18005190e  mov     [rsp+148h+var_D8], r14
0x180051913  test    ebx, ebx
0x180051915  jnz     loc_180051C2F
0x18005191b  mov     rax, rdi
0x18005191e  mov     [rsp+148h+var_C0], rax
0x180051926  mov     [rsp+148h+var_E0], rax
0x18005192b  mov     [rsp+148h+var_C8], rax
0x180051933  mov     [rsp+148h+var_F8], rax
0x180051938  test    r12b, 4
0x18005193c  jz      short loc_18005196F
0x18005193e  mov     r8d, [r14+18h]
0x180051942  and     r8d, 1; int
0x180051946  lea     r9, [rsp+148h+var_E0]; struct _ACTRL_ALISTW **
0x18005194b  lea     rdx, [rsp+148h+var_68]; struct CSList *
0x180051953  mov     rcx, [rsp+148h+arg_20]; struct _ACTRL_ALISTA *
0x18005195b  call    ?ConvertAListAToNamedBasedW@@YAKPEAU_ACTRL_ALISTA@@AEAVCSList@@HPEAPEAU_ACTRL_ALISTW@@@Z; ConvertAListAToNamedBasedW(_ACTRL_ALISTA *,CSList &,int,_ACTRL_ALISTW * *)
0x180051960  mov     ebx, eax
0x180051962  mov     rax, [rsp+148h+var_E0]
0x180051967  mov     [rsp+148h+var_C0], rax
0x18005196f  test    ebx, ebx
0x180051971  jnz     loc_180051C2F
0x180051977  test    r12b, 8
0x18005197b  jz      short loc_1800519AE
0x18005197d  mov     r8d, [r14+18h]
0x180051981  and     r8d, 1; int
0x180051985  lea     r9, [rsp+148h+var_F8]; struct _ACTRL_ALISTW **
0x18005198a  lea     rdx, [rsp+148h+var_68]; struct CSList *
0x180051992  mov     rcx, [rsp+148h+arg_28]; struct _ACTRL_ALISTA *
0x18005199a  call    ?ConvertAListAToNamedBasedW@@YAKPEAU_ACTRL_ALISTA@@AEAVCSList@@HPEAPEAU_ACTRL_ALISTW@@@Z; ConvertAListAToNamedBasedW(_ACTRL_ALISTA *,CSList &,int,_ACTRL_ALISTW * *)
0x18005199f  mov     ebx, eax
0x1800519a1  mov     rax, [rsp+148h+var_F8]
0x1800519a6  mov     [rsp+148h+var_C8], rax
0x1800519ae  test    ebx, ebx
0x1800519b0  jnz     loc_180051C2F
0x1800519b6  xorps   xmm0, xmm0
0x1800519b9  xor     eax, eax
0x1800519bb  movups  [rsp+148h+var_40], xmm0
0x1800519c3  mov     [rsp+148h+var_30], rax
0x1800519cb  lea     r14, [rsp+148h+var_40]
0x1800519d3  mov     rax, [rsp+148h+arg_40]
0x1800519db  test    rax, rax
0x1800519de  cmovnz  r14, rax
0x1800519e2  mov     [rsp+148h+var_B0], r14
0x1800519ea  movups  [rsp+148h+var_A8], xmm0
0x1800519f2  movups  [rsp+148h+var_98], xmm0
0x1800519fa  xorps   xmm1, xmm1
0x1800519fd  movups  [rsp+148h+var_88], xmm1
0x180051a05  movups  [rsp+148h+var_78], xmm1
0x180051a0d  mov     r15, rdi
0x180051a10  mov     [rsp+148h+var_E0], rdi
0x180051a15  mov     r13, rdi
0x180051a18  mov     [rsp+148h+var_B8], rdi
0x180051a20  test    r12b, 2
0x180051a24  jz      short loc_180051A78
0x180051a26  lea     r15, [rsp+148h+var_A8]
0x180051a2e  mov     [rsp+148h+var_E0], r15
0x180051a33  mov     [rsp+148h+var_F8], rdi
0x180051a38  lea     rdx, [rsp+148h+var_F8]; unsigned __int16 **
0x180051a3d  mov     rcx, [rsp+148h+MultiByteString]; MultiByteString
0x180051a45  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x180051a4a  mov     ebx, eax
0x180051a4c  test    eax, eax
0x180051a4e  jnz     short loc_180051A78
0x180051a50  mov     qword ptr [rsp+148h+var_A8], rdi
0x180051a58  mov     dword ptr [rsp+148h+var_A8+8], edi
0x180051a5f  mov     qword ptr [rsp+148h+var_A8+0Ch], 1
0x180051a6b  mov     rax, [rsp+148h+var_F8]
0x180051a70  mov     qword ptr [rsp+148h+var_98+8], rax
0x180051a78  test    ebx, ebx
0x180051a7a  jnz     loc_180051C05
0x180051a80  test    r12b, 1
0x180051a84  jz      short loc_180051ADB
0x180051a86  lea     r13, [rsp+148h+var_88]
0x180051a8e  mov     [rsp+148h+var_B8], r13
0x180051a96  mov     [rsp+148h+var_F8], rdi
0x180051a9b  lea     rdx, [rsp+148h+var_F8]; unsigned __int16 **
0x180051aa0  mov     rcx, [rsp+148h+arg_30]; MultiByteString
0x180051aa8  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x180051aad  mov     ebx, eax
0x180051aaf  test    eax, eax
0x180051ab1  jnz     short loc_180051ADB
0x180051ab3  mov     qword ptr [rsp+148h+var_88], rdi
0x180051abb  mov     dword ptr [rsp+148h+var_88+8], edi
0x180051ac2  mov     qword ptr [rsp+148h+var_88+0Ch], 1
0x180051ace  mov     rax, [rsp+148h+var_F8]
0x180051ad3  mov     qword ptr [rsp+148h+var_78+8], rax
0x180051adb  test    ebx, ebx
0x180051add  jnz     loc_180051C05
0x180051ae3  mov     [r14+8], rdi
0x180051ae7  mov     [r14+10h], rdi
0x180051aeb  mov     rbx, [rsp+148h+var_D8]
0x180051af0  mov     [r14], rbx
0x180051af3  xor     r9d, r9d; lpName
0x180051af6  xor     r8d, r8d; bInitialState
0x180051af9  lea     edx, [r9+1]; bManualReset
0x180051afd  xor     ecx, ecx; lpEventAttributes
0x180051aff  call    cs:__imp_CreateEventW
0x180051b06  nop     dword ptr [rax+rax+00h]
0x180051b0b  lea     rcx, [r14+10h]
0x180051b0f  mov     [rsp+148h+var_D8], rcx
0x180051b14  mov     [rcx], rax
0x180051b17  test    rax, rax
0x180051b1a  jnz     short loc_180051B2F
0x180051b1c  call    cs:__imp_GetLastError
0x180051b23  nop     dword ptr [rax+rax+00h]
0x180051b28  mov     ebx, eax
0x180051b2a  jmp     loc_180051BD6
0x180051b2f  mov     [rsp+148h+var_110], r14
0x180051b34  mov     [rsp+148h+var_118], r15
0x180051b39  mov     [rsp+148h+var_120], r13
0x180051b3e  mov     rax, [rsp+148h+var_C8]
0x180051b46  mov     [rsp+148h+var_128], rax
0x180051b4b  mov     r9, [rsp+148h+var_C0]
0x180051b53  mov     r8d, r12d
0x180051b56  mov     edx, [rsp+148h+arg_8]
0x180051b5d  mov     rcx, [rsp+148h+arg_0]
0x180051b65  mov     rax, [rbx+88h]
0x180051b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b71  mov     ebx, eax
0x180051b73  mov     [rsp+148h+var_E8], eax
0x180051b77  jmp     short loc_180051BBE
0x180051b79  mov     rcx, [rsp+148h+var_F0]
0x180051b7e  cmp     qword ptr [rcx+88h], 0
0x180051b86  jnz     short loc_180051B93
0x180051b88  mov     ebx, 4B4h
0x180051b8d  mov     [rsp+148h+var_E8], ebx
0x180051b91  jmp     short loc_180051BA7
0x180051b93  mov     ecx, eax; Status
0x180051b95  call    cs:__imp_RtlNtStatusToDosError
0x180051b9c  nop     dword ptr [rax+rax+00h]
0x180051ba1  mov     ebx, eax
0x180051ba3  mov     [rsp+148h+var_E8], eax
0x180051ba7  xor     edi, edi
0x180051ba9  mov     r15, [rsp+148h+var_E0]
0x180051bae  mov     r13, [rsp+148h+var_B8]
0x180051bb6  mov     r14, [rsp+148h+var_B0]
0x180051bbe  test    ebx, ebx
0x180051bc0  jz      short loc_180051BDA
0x180051bc2  mov     rcx, [rsp+148h+var_D8]
0x180051bc7  mov     rcx, [rcx]; hObject
0x180051bca  call    cs:__imp_CloseHandle
0x180051bd1  nop     dword ptr [rax+rax+00h]
0x180051bd6  test    ebx, ebx
0x180051bd8  jnz     short loc_180051C05
0x180051bda  cmp     r14, [rsp+148h+arg_40]
0x180051be2  jz      short loc_180051C05
0x180051be4  mov     dword ptr [rsp+148h+var_F0], edi
0x180051be8  xor     r9d, r9d
0x180051beb  lea     r8, [rsp+148h+var_F0]
0x180051bf0  lea     edx, [r9+1]
0x180051bf4  mov     rcx, r14
0x180051bf7  call    GetOverlappedAccessResults
0x180051bfc  mov     ebx, eax
0x180051bfe  test    eax, eax
0x180051c00  cmovz   ebx, dword ptr [rsp+148h+var_F0]
0x180051c05  test    r13, r13
0x180051c08  jz      short loc_180051C1A
0x180051c0a  mov     rcx, [r13+18h]; hMem
0x180051c0e  call    cs:__imp_LocalFree
0x180051c15  nop     dword ptr [rax+rax+00h]
0x180051c1a  test    r15, r15
0x180051c1d  jz      short loc_180051C2F
0x180051c1f  mov     rcx, [r15+18h]; hMem
0x180051c23  call    cs:__imp_LocalFree
0x180051c2a  nop     dword ptr [rax+rax+00h]
0x180051c2f  mov     rcx, [rsp+148h+hMem]; hMem
0x180051c34  call    cs:__imp_LocalFree
0x180051c3b  nop     dword ptr [rax+rax+00h]
0x180051c40  lea     rcx, [rsp+148h+var_68]; this
0x180051c48  call    ??1CSList@@QEAA@XZ; CSList::~CSList(void)
0x180051c4d  mov     eax, ebx
0x180051c4f  mov     rbx, [rsp+148h+arg_10]
0x180051c57  add     rsp, 120h
0x180051c5e  pop     r15
0x180051c60  pop     r14
0x180051c62  pop     r13
0x180051c64  pop     r12
0x180051c66  pop     rdi
0x180051c67  retn
```
