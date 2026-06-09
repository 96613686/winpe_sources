# RegistryBasedBackupStatusCache::GetRecoveryPasswordBackupStatus(eFveVolumeType,_GUID const *,_GUID const *,long *,_FILETIME *)

- ea: `0x18001ada0`
- end: `0x18001b2f1`
- name: `?GetRecoveryPasswordBackupStatus@RegistryBasedBackupStatusCache@@UEBAJW4eFveVolumeType@@PEBU_GUID@@1PEAJPEAU_FILETIME@@@Z`
- size: `1361`
- prototype: `int __high(enum eFveVolumeType, const struct _GUID *, const struct _GUID *, int *, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180006260`
- `0x180009f30`
- `0x180009f60`
- `0x18001ada0`
- `0x18001b7f0`
- `0x180034070`
- `0x180034d28`
- `0x1800740ac`
- `0x18007e010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18001afef`
- `ntdll!RtlFreeUnicodeString` at `0x18001b000`
- `ntdll!RtlFreeUnicodeString` at `0x18001afef`
- `ntdll!RtlFreeUnicodeString` at `0x18001b000`
- `ntdll!RtlNtStatusToDosError` at `0x18001ae7c`
- `ntdll!RtlNtStatusToDosError` at `0x18001aeea`
- `ntdll!RtlNtStatusToDosError` at `0x18001ae7c`
- `ntdll!RtlNtStatusToDosError` at `0x18001aeea`
- `ntdll!RtlStringFromGUID` at `0x18001ae6e`
- `ntdll!RtlStringFromGUID` at `0x18001aedc`
- `ntdll!RtlStringFromGUID` at `0x18001ae6e`
- `ntdll!RtlStringFromGUID` at `0x18001aedc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b0af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b0af`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b142`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b1d0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b142`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b1d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b296`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b296`

## pseudocode

```c
__int64 __fastcall RegistryBasedBackupStatusCache::GetRecoveryPasswordBackupStatus(
        __int64 a1,
        int a2,
        const GUID *a3,
        const GUID *a4,
        _DWORD *a5,
        _QWORD *a6)
{
  NTSTATUS v10; // eax
  signed int v11; // eax
  signed int v12; // ebx
  NTSTATUS v13; // eax
  signed int v14; // eax
  int v15; // edi
  const wchar_t *v16; // rbx
  __int64 v17; // rax
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  PVOID *v21; // r10
  HKEY v22; // rax
  LSTATUS v23; // eax
  LSTATUS ValueW; // eax
  LSTATUS v25; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  pcbData = 0;
  pvData = 0;
  v30 = 0;
  hkey = 0;
  memset_0(SubKey, 0, 0x208u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
  UnicodeString = 0;
  GuidString = 0;
  memset_0(SubKey, 0, 0x208u);
  v10 = RtlStringFromGUID(a3, &GuidString);
  v11 = RtlNtStatusToDosError(v10);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( !v12 )
    goto LABEL_11;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      131,
      &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
      (unsigned int)v12);
  if ( v12 >= 0 )
  {
LABEL_11:
    v13 = RtlStringFromGUID(a4, &UnicodeString);
    v14 = RtlNtStatusToDosError(v13);
    v12 = v14;
    if ( v14 > 0 )
      v12 = (unsigned __int16)v14 | 0x80070000;
    if ( !v12 )
      goto LABEL_18;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        132,
        &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
        (unsigned int)v12);
    if ( v12 >= 0 )
    {
LABEL_18:
      if ( a2 )
      {
        v15 = a2 - 1;
        if ( v15 )
        {
          if ( v15 == 1 )
            v16 = L"RDV";
          else
            v16 = &dword_180086574;
        }
        else
        {
          v16 = L"FDV";
        }
      }
      else
      {
        v16 = L"OSV";
      }
      v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
      v18 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%wZ\\%wZ", v17, v16, &GuidString, &UnicodeString);
      v12 = v18;
      if ( v18 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v18);
    }
  }
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&GuidString);
  if ( !v12 )
  {
    v21 = (PVOID *)WPP_GLOBAL_Control;
LABEL_36:
    if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
      WPP_SF_S(v21[2], 125, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, SubKey);
    v22 = (HKEY)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
    v23 = RegOpenKeyExW(v22, SubKey, 0, 1u, &hkey);
    v12 = v23;
    if ( v23 > 0 )
      v12 = (unsigned __int16)v23 | 0x80070000;
    if ( !v12 )
      goto LABEL_46;
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        126,
        &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
        (unsigned int)v12);
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v12 >= 0 )
    {
LABEL_46:
      pcbData = 4;
      ValueW = RegGetValueW(hkey, 0, L"LastBackupStatus", 0x10u, 0, &pvData, &pcbData);
      v12 = ValueW;
      if ( ValueW > 0 )
        v12 = (unsigned __int16)ValueW | 0x80070000;
      if ( !v12 )
        goto LABEL_53;
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          127,
          &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
          (unsigned int)v12);
        v21 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v12 >= 0 )
      {
LABEL_53:
        pcbData = 8;
        v25 = RegGetValueW(hkey, 0, L"LastBackupTime", 0x40u, 0, &v30, &pcbData);
        v12 = v25;
        if ( v25 > 0 )
          v12 = (unsigned __int16)v25 | 0x80070000;
        if ( !v12 )
          goto LABEL_60;
        v21 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            128,
            &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
            (unsigned int)v12);
          v21 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v12 >= 0 )
        {
LABEL_60:
          *a5 = pvData;
          *a6 = v30;
          v21 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
    }
    goto LABEL_61;
  }
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      124,
      &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
      (unsigned int)v12);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 >= 0 )
    goto LABEL_36;
LABEL_61:
  if ( v12 == -2147024894 )
  {
    *a5 = -2147024894;
    *a6 = 0;
    v12 = 0;
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  else if ( v12 < 0 )
  {
    goto LABEL_67;
  }
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
  {
    WPP_SF_di(v21[2], v19, v20, (unsigned int)*a5, *a6);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_67:
  if ( hkey )
  {
    RegCloseKey(hkey);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 0x20) != 0 )
    WPP_SF_d(v21[2], 130, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001ada0  push    rbp
0x18001ada2  push    rbx
0x18001ada3  push    rsi
0x18001ada4  push    rdi
0x18001ada5  push    r12
0x18001ada7  push    r14
0x18001ada9  push    r15
0x18001adab  lea     rbp, [rsp-1A0h]
0x18001adb3  sub     rsp, 2A0h
0x18001adba  mov     rax, cs:__security_cookie
0x18001adc1  xor     rax, rsp
0x18001adc4  mov     [rbp+1D0h+var_40], rax
0x18001adcb  mov     r15, [rbp+1D0h+arg_28]
0x18001add2  mov     rbx, r8
0x18001add5  mov     r12, [rbp+1D0h+arg_20]
0x18001addc  mov     edi, edx
0x18001adde  mov     r14, rcx
0x18001ade1  mov     [rsp+2D0h+var_290], 0
0x18001ade9  xor     edx, edx; Val
0x18001adeb  mov     [rsp+2D0h+var_28C], 0
0x18001adf3  mov     r8d, 208h; Size
0x18001adf9  mov     [rsp+2D0h+var_280], 0
0x18001ae02  lea     rcx, [rbp+1D0h+SubKey]; void *
0x18001ae06  mov     [rsp+2D0h+hkey], 0
0x18001ae0f  mov     rsi, r9
0x18001ae12  call    memset_0
0x18001ae17  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae1e  lea     rax, WPP_GLOBAL_Control
0x18001ae25  cmp     rcx, rax
0x18001ae28  jz      short loc_18001AE45
0x18001ae2a  test    byte ptr [rcx+1Ch], 20h
0x18001ae2e  jz      short loc_18001AE45
0x18001ae30  mov     rcx, [rcx+10h]
0x18001ae34  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001ae3b  mov     edx, 7Bh ; '{'
0x18001ae40  call    WPP_SF_
0x18001ae45  xorps   xmm0, xmm0
0x18001ae48  lea     rcx, [rbp+1D0h+SubKey]; void *
0x18001ae4c  xorps   xmm1, xmm1
0x18001ae4f  xor     edx, edx; Val
0x18001ae51  mov     r8d, 208h; Size
0x18001ae57  movups  xmmword ptr [rsp+2D0h+UnicodeString.Length], xmm0
0x18001ae5c  movups  xmmword ptr [rsp+2D0h+GuidString.Length], xmm1
0x18001ae61  call    memset_0
0x18001ae66  lea     rdx, [rsp+2D0h+GuidString]; GuidString
0x18001ae6b  mov     rcx, rbx; Guid
0x18001ae6e  call    cs:__imp_RtlStringFromGUID
0x18001ae75  nop     dword ptr [rax+rax+00h]
0x18001ae7a  mov     ecx, eax; Status
0x18001ae7c  call    cs:__imp_RtlNtStatusToDosError
0x18001ae83  nop     dword ptr [rax+rax+00h]
0x18001ae88  mov     ebx, eax
0x18001ae8a  test    eax, eax
0x18001ae8c  jle     short loc_18001AE97
0x18001ae8e  movzx   ebx, ax
0x18001ae91  or      ebx, 80070000h
0x18001ae97  test    ebx, ebx
0x18001ae99  jz      short loc_18001AED4
0x18001ae9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aea2  lea     rax, WPP_GLOBAL_Control
0x18001aea9  cmp     rcx, rax
0x18001aeac  jz      short loc_18001AECC
0x18001aeae  test    byte ptr [rcx+1Ch], 40h
0x18001aeb2  jz      short loc_18001AECC
0x18001aeb4  mov     rcx, [rcx+10h]
0x18001aeb8  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001aebf  mov     edx, 83h
0x18001aec4  mov     r9d, ebx
0x18001aec7  call    WPP_SF_d
0x18001aecc  test    ebx, ebx
0x18001aece  js      loc_18001AFEA
0x18001aed4  lea     rdx, [rsp+2D0h+UnicodeString]; GuidString
0x18001aed9  mov     rcx, rsi; Guid
0x18001aedc  call    cs:__imp_RtlStringFromGUID
0x18001aee3  nop     dword ptr [rax+rax+00h]
0x18001aee8  mov     ecx, eax; Status
0x18001aeea  call    cs:__imp_RtlNtStatusToDosError
0x18001aef1  nop     dword ptr [rax+rax+00h]
0x18001aef6  mov     ebx, eax
0x18001aef8  test    eax, eax
0x18001aefa  jle     short loc_18001AF05
0x18001aefc  movzx   ebx, ax
0x18001aeff  or      ebx, 80070000h
0x18001af05  test    ebx, ebx
0x18001af07  jz      short loc_18001AF43
0x18001af09  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af10  lea     rsi, WPP_GLOBAL_Control
0x18001af17  cmp     rcx, rsi
0x18001af1a  jz      short loc_18001AF3A
0x18001af1c  test    byte ptr [rcx+1Ch], 40h
0x18001af20  jz      short loc_18001AF3A
0x18001af22  mov     rcx, [rcx+10h]
0x18001af26  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001af2d  mov     edx, 84h
0x18001af32  mov     r9d, ebx
0x18001af35  call    WPP_SF_d
0x18001af3a  test    ebx, ebx
0x18001af3c  jns     short loc_18001AF4A
0x18001af3e  jmp     loc_18001AFEA
0x18001af43  lea     rsi, WPP_GLOBAL_Control
0x18001af4a  test    edi, edi
0x18001af4c  jz      short loc_18001AF73
0x18001af4e  sub     edi, 1
0x18001af51  jz      short loc_18001AF6A
0x18001af53  cmp     edi, 1
0x18001af56  jz      short loc_18001AF61
0x18001af58  lea     rbx, dword_180086574
0x18001af5f  jmp     short loc_18001AF7A
0x18001af61  lea     rbx, aRdv; "RDV"
0x18001af68  jmp     short loc_18001AF7A
0x18001af6a  lea     rbx, aFdv; "FDV"
0x18001af71  jmp     short loc_18001AF7A
0x18001af73  lea     rbx, aOsv; "OSV"
0x18001af7a  mov     rax, [r14]
0x18001af7d  mov     rcx, r14
0x18001af80  mov     rax, [rax+20h]
0x18001af84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af89  lea     rcx, [rsp+2D0h+UnicodeString]
0x18001af8e  mov     r9, rax
0x18001af91  mov     [rsp+2D0h+pcbData], rcx
0x18001af96  lea     r8, aSSWzWz; "%s\\%s\\%wZ\\%wZ"
0x18001af9d  lea     rcx, [rsp+2D0h+GuidString]
0x18001afa2  mov     edx, 104h; unsigned __int64
0x18001afa7  mov     [rsp+2D0h+pvData], rcx
0x18001afac  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x18001afb0  mov     [rsp+2D0h+phkResult], rbx
0x18001afb5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001afba  mov     ebx, eax
0x18001afbc  test    eax, eax
0x18001afbe  jz      short loc_18001AFEA
0x18001afc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afc7  cmp     rcx, rsi
0x18001afca  jz      short loc_18001AFEA
0x18001afcc  test    byte ptr [rcx+1Ch], 40h
0x18001afd0  jz      short loc_18001AFEA
0x18001afd2  mov     rcx, [rcx+10h]
0x18001afd6  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001afdd  mov     edx, 85h
0x18001afe2  mov     r9d, eax
0x18001afe5  call    WPP_SF_d
0x18001afea  lea     rcx, [rsp+2D0h+UnicodeString]; UnicodeString
0x18001afef  call    cs:__imp_RtlFreeUnicodeString
0x18001aff6  nop     dword ptr [rax+rax+00h]
0x18001affb  lea     rcx, [rsp+2D0h+GuidString]; UnicodeString
0x18001b000  call    cs:__imp_RtlFreeUnicodeString
0x18001b007  nop     dword ptr [rax+rax+00h]
0x18001b00c  test    ebx, ebx
0x18001b00e  jz      short loc_18001B053
0x18001b010  mov     r10, cs:WPP_GLOBAL_Control
0x18001b017  lea     rdi, WPP_GLOBAL_Control
0x18001b01e  cmp     r10, rdi
0x18001b021  jz      short loc_18001B049
0x18001b023  test    byte ptr [r10+1Ch], 40h
0x18001b028  jz      short loc_18001B049
0x18001b02a  mov     rcx, [r10+10h]
0x18001b02e  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001b035  mov     edx, 7Ch ; '|'
0x18001b03a  mov     r9d, ebx
0x18001b03d  call    WPP_SF_d
0x18001b042  mov     r10, cs:WPP_GLOBAL_Control
0x18001b049  test    ebx, ebx
0x18001b04b  js      loc_18001B238
0x18001b051  jmp     short loc_18001B061
0x18001b053  mov     r10, cs:WPP_GLOBAL_Control
0x18001b05a  lea     rdi, WPP_GLOBAL_Control
0x18001b061  cmp     r10, rdi
0x18001b064  jz      short loc_18001B086
0x18001b066  test    byte ptr [r10+1Ch], 8
0x18001b06b  jz      short loc_18001B086
0x18001b06d  mov     rcx, [r10+10h]
0x18001b071  lea     r9, [rbp+1D0h+SubKey]
0x18001b075  mov     edx, 7Dh ; '}'
0x18001b07a  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001b081  call    WPP_SF_S
0x18001b086  mov     rax, [r14]
0x18001b089  mov     rcx, r14
0x18001b08c  mov     rax, [rax+18h]
0x18001b090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b095  mov     rcx, rax; hKey
0x18001b098  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18001b09c  lea     rax, [rsp+2D0h+hkey]
0x18001b0a1  mov     r9d, 1; samDesired
0x18001b0a7  xor     r8d, r8d; ulOptions
0x18001b0aa  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18001b0af  call    cs:__imp_RegOpenKeyExW
0x18001b0b6  nop     dword ptr [rax+rax+00h]
0x18001b0bb  mov     ebx, eax
0x18001b0bd  mov     esi, 80070000h
0x18001b0c2  test    eax, eax
0x18001b0c4  jle     short loc_18001B0CB
0x18001b0c6  movzx   ebx, ax
0x18001b0c9  or      ebx, esi
0x18001b0cb  test    ebx, ebx
0x18001b0cd  jz      short loc_18001B109
0x18001b0cf  mov     r10, cs:WPP_GLOBAL_Control
0x18001b0d6  cmp     r10, rdi
0x18001b0d9  jz      short loc_18001B101
0x18001b0db  test    byte ptr [r10+1Ch], 40h
0x18001b0e0  jz      short loc_18001B101
0x18001b0e2  mov     rcx, [r10+10h]
0x18001b0e6  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001b0ed  mov     edx, 7Eh ; '~'
0x18001b0f2  mov     r9d, ebx
0x18001b0f5  call    WPP_SF_d
0x18001b0fa  mov     r10, cs:WPP_GLOBAL_Control
0x18001b101  test    ebx, ebx
0x18001b103  js      loc_18001B238
0x18001b109  mov     rcx, [rsp+2D0h+hkey]; hkey
0x18001b10e  lea     rax, [rsp+2D0h+var_290]
0x18001b113  mov     [rsp+2D0h+pcbData], rax; pcbData
0x18001b118  lea     r8, aLastbackupstat; "LastBackupStatus"
0x18001b11f  lea     rax, [rsp+2D0h+var_28C]
0x18001b124  mov     [rsp+2D0h+var_290], 4
0x18001b12c  mov     [rsp+2D0h+pvData], rax; pvData
0x18001b131  mov     r9d, 10h; dwFlags
0x18001b137  xor     edx, edx; lpSubKey
0x18001b139  mov     [rsp+2D0h+phkResult], 0; pdwType
0x18001b142  call    cs:__imp_RegGetValueW
0x18001b149  nop     dword ptr [rax+rax+00h]
0x18001b14e  mov     ebx, eax
0x18001b150  test    eax, eax
0x18001b152  jle     short loc_18001B159
0x18001b154  movzx   ebx, ax
0x18001b157  or      ebx, esi
0x18001b159  test    ebx, ebx
0x18001b15b  jz      short loc_18001B197
0x18001b15d  mov     r10, cs:WPP_GLOBAL_Control
0x18001b164  cmp     r10, rdi
0x18001b167  jz      short loc_18001B18F
0x18001b169  test    byte ptr [r10+1Ch], 40h
0x18001b16e  jz      short loc_18001B18F
0x18001b170  mov     rcx, [r10+10h]
0x18001b174  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001b17b  mov     edx, 7Fh
0x18001b180  mov     r9d, ebx
0x18001b183  call    WPP_SF_d
0x18001b188  mov     r10, cs:WPP_GLOBAL_Control
0x18001b18f  test    ebx, ebx
0x18001b191  js      loc_18001B238
0x18001b197  mov     rcx, [rsp+2D0h+hkey]; hkey
0x18001b19c  lea     rax, [rsp+2D0h+var_290]
0x18001b1a1  mov     [rsp+2D0h+pcbData], rax; pcbData
0x18001b1a6  lea     r8, aLastbackuptime; "LastBackupTime"
0x18001b1ad  lea     rax, [rsp+2D0h+var_280]
0x18001b1b2  mov     [rsp+2D0h+var_290], 8
0x18001b1ba  mov     [rsp+2D0h+pvData], rax; pvData
0x18001b1bf  mov     r9d, 40h ; '@'; dwFlags
0x18001b1c5  xor     edx, edx; lpSubKey
0x18001b1c7  mov     [rsp+2D0h+phkResult], 0; pdwType
0x18001b1d0  call    cs:__imp_RegGetValueW
0x18001b1d7  nop     dword ptr [rax+rax+00h]
0x18001b1dc  mov     ebx, eax
0x18001b1de  test    eax, eax
0x18001b1e0  jle     short loc_18001B1E7
0x18001b1e2  movzx   ebx, ax
0x18001b1e5  or      ebx, esi
0x18001b1e7  test    ebx, ebx
0x18001b1e9  jz      short loc_18001B221
0x18001b1eb  mov     r10, cs:WPP_GLOBAL_Control
0x18001b1f2  cmp     r10, rdi
0x18001b1f5  jz      short loc_18001B21D
0x18001b1f7  test    byte ptr [r10+1Ch], 40h
0x18001b1fc  jz      short loc_18001B21D
0x18001b1fe  mov     rcx, [r10+10h]
0x18001b202  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001b209  mov     edx, 80h
0x18001b20e  mov     r9d, ebx
0x18001b211  call    WPP_SF_d
0x18001b216  mov     r10, cs:WPP_GLOBAL_Control
0x18001b21d  test    ebx, ebx
0x18001b21f  js      short loc_18001B238
0x18001b221  mov     eax, [rsp+2D0h+var_28C]
0x18001b225  mov     [r12], eax
0x18001b229  mov     rax, [rsp+2D0h+var_280]
0x18001b22e  mov     [r15], rax
0x18001b231  mov     r10, cs:WPP_GLOBAL_Control
0x18001b238  mov     eax, 80070002h
0x18001b23d  cmp     ebx, eax
0x18001b23f  jnz     short loc_18001B255
0x18001b241  mov     [r12], eax
0x18001b245  xor     eax, eax
0x18001b247  mov     [r15], rax
0x18001b24a  xor     ebx, ebx
0x18001b24c  mov     r10, cs:WPP_GLOBAL_Control
0x18001b253  jmp     short loc_18001B259
0x18001b255  test    ebx, ebx
0x18001b257  js      short loc_18001B28C
0x18001b259  cmp     r10, rdi
0x18001b25c  jz      short loc_18001B28C
0x18001b25e  test    byte ptr [r10+1Ch], 8
0x18001b263  jz      short loc_18001B28C
0x18001b265  mov     ecx, [r15+4]
0x18001b269  mov     eax, [r15]
0x18001b26c  mov     r9d, [r12]
0x18001b270  shl     rcx, 20h
0x18001b274  or      rcx, rax
0x18001b277  mov     [rsp+2D0h+phkResult], rcx
0x18001b27c  mov     rcx, [r10+10h]
0x18001b280  call    WPP_SF_di
0x18001b285  mov     r10, cs:WPP_GLOBAL_Control
  ... truncated ...
```
