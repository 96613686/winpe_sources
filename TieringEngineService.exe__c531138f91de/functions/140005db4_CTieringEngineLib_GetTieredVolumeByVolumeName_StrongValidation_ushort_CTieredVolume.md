# CTieringEngineLib::GetTieredVolumeByVolumeName_StrongValidation(ushort *,CTieredVolume * *)

- ea: `0x140005db4`
- end: `0x14000667a`
- name: `?GetTieredVolumeByVolumeName_StrongValidation@CTieringEngineLib@@QEAAJPEAGPEAPEAVCTieredVolume@@@Z`
- size: `2246`
- prototype: `__int64 __fastcall(CTieringEngineLib *this, unsigned __int16 *, struct CTieredVolume **)`
- caller_count: `21`
- callee_count: `12`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1400382e0`
- `0x140038490`
- `0x140038630`
- `0x140038830`
- `0x140038a50`
- `0x140038ea0`
- `0x140039090`
- `0x140039340`
- `0x140039470`
- `0x1400397c0`
- `0x140039b10`
- `0x140039de0`
- `0x140039fd0`
- `0x14003a3d0`
- `0x14003a610`
- `0x14003a8f0`
- `0x14003aa90`
- `0x14003ad70`
- `0x14003af90`
- `0x14003b070`
- `0x14003b500`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x140005954`
- `0x140005db4`
- `0x140009a04`
- `0x140009a64`
- `0x140009af0`
- `0x140009c08`
- `0x14000a490`
- `0x14000a560`
- `0x14000b490`
- `0x14003fbb0`

## import_xrefs

- `msvcrt!malloc` at `0x1400061fc`
- `msvcrt!malloc` at `0x1400061fc`
- `msvcrt!free` at `0x140006245`
- `msvcrt!free` at `0x140006294`
- `msvcrt!free` at `0x1400062cf`
- `msvcrt!free` at `0x1400062f8`
- `msvcrt!free` at `0x140006300`
- `msvcrt!free` at `0x14000643b`
- `msvcrt!free` at `0x1400065b5`
- `msvcrt!free` at `0x140006245`
- `msvcrt!free` at `0x140006294`
- `msvcrt!free` at `0x1400062cf`
- `msvcrt!free` at `0x1400062f8`
- `msvcrt!free` at `0x140006300`
- `msvcrt!free` at `0x14000643b`
- `msvcrt!free` at `0x1400065b5`
- `ntdll!NtClose` at `0x1400063a5`
- `ntdll!NtClose` at `0x140006402`
- `ntdll!NtClose` at `0x140006449`
- `ntdll!NtClose` at `0x140006463`
- `ntdll!NtClose` at `0x140006553`
- `ntdll!NtClose` at `0x1400065ac`
- `ntdll!NtClose` at `0x1400065c3`
- `ntdll!NtClose` at `0x1400065d9`
- `ntdll!NtClose` at `0x1400063a5`
- `ntdll!NtClose` at `0x140006402`
- `ntdll!NtClose` at `0x140006449`
- `ntdll!NtClose` at `0x140006463`
- `ntdll!NtClose` at `0x140006553`
- `ntdll!NtClose` at `0x1400065ac`
- `ntdll!NtClose` at `0x1400065c3`
- `ntdll!NtClose` at `0x1400065d9`
- `ntdll!RtlNtStatusToDosError` at `0x14000616b`
- `ntdll!RtlNtStatusToDosError` at `0x14000616b`
- `ntdll!RtlGUIDFromString` at `0x14000615f`
- `ntdll!RtlGUIDFromString` at `0x14000615f`
- `ntdll!RtlCompareUnicodeString` at `0x1400060bf`
- `ntdll!RtlCompareUnicodeString` at `0x1400060d5`
- `ntdll!RtlCompareUnicodeString` at `0x14000612e`
- `ntdll!RtlCompareUnicodeString` at `0x1400060bf`
- `ntdll!RtlCompareUnicodeString` at `0x1400060d5`
- `ntdll!RtlCompareUnicodeString` at `0x14000612e`
- `ntdll!RtlInitUnicodeString` at `0x140005ebd`
- `ntdll!RtlInitUnicodeString` at `0x140005ece`
- `ntdll!RtlInitUnicodeString` at `0x140005fb1`
- `ntdll!RtlInitUnicodeString` at `0x14000609c`
- `ntdll!RtlInitUnicodeString` at `0x1400060ad`
- `ntdll!RtlInitUnicodeString` at `0x140005ebd`
- `ntdll!RtlInitUnicodeString` at `0x140005ece`
- `ntdll!RtlInitUnicodeString` at `0x140005fb1`
- `ntdll!RtlInitUnicodeString` at `0x14000609c`
- `ntdll!RtlInitUnicodeString` at `0x1400060ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000655b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000655b`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140005f5d`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140005f5d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000653d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000653d`

## pseudocode

```c
__int64 __fastcall CTieringEngineLib::GetTieredVolumeByVolumeName_StrongValidation(
        CTieringEngineLib *this,
        unsigned __int16 *a2,
        struct CTieredVolume **a3)
{
  unsigned int v5; // ebx
  int v6; // r8d
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // edi
  __int64 v10; // rsi
  unsigned int v11; // eax
  unsigned int v12; // edi
  __int64 v14; // r10
  int Buffer; // r9d
  int v16; // edx
  _QWORD *v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  ULONG v20; // eax
  unsigned int VolumeByGuid; // r13d
  USHORT Length; // si
  int v23; // edi
  void *v24; // rax
  int v25; // ebx
  HANDLE v26; // rbx
  int MdsPath; // eax
  char v28; // di
  void *v29; // rcx
  void *v30; // rsi
  int v31; // eax
  void *v32; // rdi
  char LastError; // al
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING hDevice; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-98h] BYREF
  UNICODE_STRING String1; // [rsp+70h] [rbp-90h] BYREF
  PSRWLOCK SRWLock; // [rsp+80h] [rbp-80h]
  UNICODE_STRING String2; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+98h] [rbp-68h] BYREF
  struct CTieredVolume **v42; // [rsp+A8h] [rbp-58h]
  struct _UNICODE_STRING v43; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING v44; // [rsp+C0h] [rbp-40h] BYREF
  __int64 OutBuffer; // [rsp+D0h] [rbp-30h] BYREF
  int v46; // [rsp+D8h] [rbp-28h]
  GUID Guid; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE szVolumeMountPoint[16]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR szVolumeName[56]; // [rsp+100h] [rbp+0h] BYREF

  v42 = a3;
  Guid = 0;
  v43 = 0;
  DestinationString = 0;
  String1 = 0;
  GuidString = 0;
  String2 = 0;
  v44 = 0;
  if ( !a3 )
  {
    v5 = ATL::AtlHresultFromWin32(0x57u);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v8 = (unsigned int)(v6 + 85);
    goto LABEL_6;
  }
  *a3 = 0;
  if ( !a2 )
  {
    v5 = ATL::AtlHresultFromWin32(0x57u);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v8 = 86;
LABEL_6:
    WPP_SF_d(v7[2], v8, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v5);
    return v5;
  }
  SRWLock = (PSRWLOCK)TieringEngineLibInstance;
  RtlInitUnicodeString(&DestinationString, a2);
  RtlInitUnicodeString(&v43, L"\\\\?\\Volume{bab6b806-2c70-4823-9d7c-aab8c6df6ca4}");
  v9 = DestinationString.Length >> 1;
  v10 = v43.Length >> 1;
  if ( v9 - 2 <= 1
    && a2[1] == 58
    && (v9 < 3 || a2[2] == 92)
    && ((unsigned __int16)(*a2 - 97) <= 0x19u || (unsigned __int16)(*a2 - 65) <= 0x19u) )
  {
    *(_WORD *)szVolumeMountPoint = *a2;
    wcscpy((wchar_t *)&szVolumeMountPoint[2], L":\\");
    if ( !GetVolumeNameForVolumeMountPointW((LPCWSTR)szVolumeMountPoint, szVolumeName, 0x32u) )
    {
      v11 = ATL::AtlHresultFromWin32(0x7Bu);
      v12 = v11;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          (unsigned int)&WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
          (_DWORD)a2,
          v11);
      }
      return v12;
    }
    RtlInitUnicodeString(&DestinationString, szVolumeName);
    v9 = DestinationString.Length >> 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        (unsigned int)&WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
        (_DWORD)a2,
        (__int64)DestinationString.Buffer);
    }
  }
  if ( v9 < (unsigned int)v10 )
  {
    v5 = ATL::AtlHresultFromWin32(0x7Bu);
    if ( (_UNKNOWN **)v14 == &WPP_GLOBAL_Control || (*(_BYTE *)(v14 + 28) & 1) == 0 || *(_BYTE *)(v14 + 25) < 2u )
      return v5;
    Buffer = (int)DestinationString.Buffer;
    v16 = 89;
    goto LABEL_119;
  }
  if ( v9 > (int)v10 + 1
    || v9 > (unsigned int)v10 && DestinationString.Buffer[v10] != 92
    || DestinationString.Buffer[(unsigned int)(v10 - 1)] != 125 )
  {
    v5 = ATL::AtlHresultFromWin32(0x7Bu);
    if ( (_UNKNOWN **)v14 == &WPP_GLOBAL_Control || (*(_BYTE *)(v14 + 28) & 1) == 0 || *(_BYTE *)(v14 + 25) < 2u )
      return v5;
    v16 = 90;
LABEL_119:
    v18 = *(_QWORD *)(v14 + 16);
    goto LABEL_120;
  }
  String1.Buffer = DestinationString.Buffer;
  String1.Length = 20;
  String1.MaximumLength = DestinationString.MaximumLength;
  RtlInitUnicodeString(&String2, L"\\\\?\\Volume");
  RtlInitUnicodeString(&v44, L"\\??\\Volume");
  if ( RtlCompareUnicodeString(&String1, &String2, 1u) && RtlCompareUnicodeString(&String1, &v44, 1u) )
  {
    v5 = ATL::AtlHresultFromWin32(0x7Bu);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v16 = 91;
    goto LABEL_44;
  }
  if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
    DestinationString.Buffer[1] = 63;
  GuidString.Buffer = (PWSTR)((char *)DestinationString.Buffer + String2.Length);
  *(_DWORD *)&GuidString.Length = 4980812;
  v19 = RtlGUIDFromString(&GuidString, &Guid);
  if ( v19 < 0 )
  {
    v20 = RtlNtStatusToDosError(v19);
    v5 = ATL::AtlHresultFromWin32(v20);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v16 = 92;
LABEL_44:
    Buffer = (int)DestinationString.Buffer;
    v18 = v17[2];
LABEL_120:
    WPP_SF_Sd(v18, v16, (unsigned int)&WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, Buffer, v5);
    return v5;
  }
  VolumeByGuid = CTieringEngineLib::FindVolumeByGuid(SRWLock, DestinationString.Buffer, &Guid, a3);
  if ( (VolumeByGuid & 0x80000000) == 0 )
    return VolumeByGuid;
  Length = DestinationString.Length;
  v23 = (int)DestinationString.Buffer;
  Handle = 0;
  if ( DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] == 92 )
  {
    v25 = OpenVolumeHandle(1, &DestinationString, &Handle, 0x100080u);
  }
  else
  {
    *(_DWORD *)(&hDevice.MaximumLength + 1) = 0;
    v24 = malloc(DestinationString.Length + 4LL);
    Block = v24;
    if ( !v24 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          93,
          (unsigned int)&WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
          v23,
          14);
      }
      free(0);
      return 2147942414LL;
    }
    hDevice.Buffer = (PWSTR)v24;
    hDevice.Length = 0;
    hDevice.MaximumLength = Length + 4;
    v5 = CopyUnicodeStringToBuffer(
           0,
           &DestinationString,
           (struct _UNICODE_STRING *)&BackslashString,
           &hDevice,
           (__int64)&Block);
    if ( (v5 & 0x80000000) != 0 )
    {
      free(Block);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          94,
          (unsigned int)&WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
          DestinationString.Buffer,
          VolumeByGuid);
      }
      free(0);
      return v5;
    }
    v25 = OpenVolumeHandle(1, &hDevice, &Handle, 0x100080u);
    free(Block);
    free(0);
  }
  if ( v25 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        (unsigned int)&WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
        DestinationString.Buffer,
        v25,
        VolumeByGuid);
    }
    if ( Handle )
      NtClose(Handle);
    return VolumeByGuid;
  }
  v26 = Handle;
  *(_QWORD *)&hDevice.Length = 0;
  LODWORD(Block) = 0;
  MdsPath = CsvQueryMdsPath(Handle);
  v28 = MdsPath;
  if ( MdsPath < 0 )
  {
    if ( v26 )
      NtClose(v26);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        (unsigned int)&WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
        DestinationString.Buffer,
        v28,
        VolumeByGuid);
    }
    v29 = *(void **)&hDevice.Length;
LABEL_110:
    free(v29);
    return VolumeByGuid;
  }
  v30 = *(void **)&hDevice.Length;
  if ( **(_DWORD **)&hDevice.Length == *(_DWORD *)(*(_QWORD *)&hDevice.Length + 4LL) )
  {
    if ( v26 )
      NtClose(v26);
    if ( DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] == 92 )
      DestinationString.Length -= 2;
    *(_QWORD *)&hDevice.Length = 0;
    v31 = OpenVolumeHandle(1, &DestinationString, (void **)&hDevice, 0x100080u);
    if ( v31 >= 0 )
    {
      OutBuffer = 0;
      v46 = 0;
      *(_DWORD *)szVolumeMountPoint = 0;
      v32 = *(void **)&hDevice.Length;
      if ( DeviceIoControl(
             *(HANDLE *)&hDevice.Length,
             0x2D1080u,
             0,
             0,
             &OutBuffer,
             0xCu,
             (LPDWORD)szVolumeMountPoint,
             0) )
      {
        if ( v32 )
          NtClose(v32);
        Guid.Data1 = HIDWORD(OutBuffer);
        *(_DWORD *)&Guid.Data2 = v46;
        *(_QWORD *)Guid.Data4 = 0;
        VolumeByGuid = CTieringEngineLib::FindVolumeByGuid(SRWLock, DestinationString.Buffer, &Guid, v42);
      }
      else
      {
        if ( v32 )
          NtClose(v32);
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SDd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            99,
            (unsigned int)&WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
            DestinationString.Buffer,
            LastError,
            VolumeByGuid);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SDd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          98,
          (unsigned int)&WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
          DestinationString.Buffer,
          v31,
          VolumeByGuid);
      }
      if ( *(_QWORD *)&hDevice.Length )
        NtClose(*(HANDLE *)&hDevice.Length);
    }
    v29 = v30;
    goto LABEL_110;
  }
  if ( v26 )
    NtClose(v26);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      97,
      &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
      DestinationString.Buffer);
  }
  free(v30);
  return 2156068869LL;
}

```

## disassembly

```asm
0x140005db4  mov     [rsp-8+arg_0], rbx
0x140005db9  mov     [rsp-8+arg_18], rsi
0x140005dbe  push    rbp
0x140005dbf  push    rdi
0x140005dc0  push    r12
0x140005dc2  push    r13
0x140005dc4  push    r15
0x140005dc6  lea     rbp, [rsp-80h]
0x140005dcb  sub     rsp, 180h
0x140005dd2  mov     rax, cs:__security_cookie
0x140005dd9  xor     rax, rsp
0x140005ddc  mov     [rbp+0A0h+var_30], rax
0x140005de0  mov     [rbp+0A0h+var_F8], r8
0x140005de4  xorps   xmm0, xmm0
0x140005de7  xorps   xmm1, xmm1
0x140005dea  mov     r13, r8
0x140005ded  mov     rbx, rdx
0x140005df0  movups  xmmword ptr [rbp+0A0h+Guid.Data1], xmm0
0x140005df4  movups  xmmword ptr [rbp+0A0h+var_F0.Length], xmm1
0x140005df8  movups  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm0
0x140005dfd  movups  xmmword ptr [rsp+1A0h+String1.Length], xmm1
0x140005e02  movups  xmmword ptr [rbp+0A0h+GuidString.Length], xmm0
0x140005e06  movups  xmmword ptr [rbp+0A0h+String2.Length], xmm1
0x140005e0a  movups  xmmword ptr [rbp+0A0h+var_E0.Length], xmm0
0x140005e0e  test    r8, r8
0x140005e11  jnz     short loc_140005E65
0x140005e13  lea     ecx, [r8+57h]; unsigned int
0x140005e17  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140005e1c  mov     ebx, eax
0x140005e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e25  lea     r15, WPP_GLOBAL_Control
0x140005e2c  cmp     rcx, r15
0x140005e2f  jz      loc_140006650
0x140005e35  test    byte ptr [rcx+1Ch], 1
0x140005e39  jz      loc_140006650
0x140005e3f  cmp     byte ptr [rcx+19h], 2
0x140005e43  jb      loc_140006650
0x140005e49  lea     edx, [r8+55h]
0x140005e4d  mov     rcx, [rcx+10h]
0x140005e51  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140005e58  mov     r9d, ebx
0x140005e5b  call    WPP_SF_d
0x140005e60  jmp     loc_140006650
0x140005e65  mov     qword ptr [r8], 0
0x140005e6c  test    rbx, rbx
0x140005e6f  jnz     short loc_140005EAD
0x140005e71  lea     ecx, [rbx+57h]; unsigned int
0x140005e74  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140005e79  mov     ebx, eax
0x140005e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e82  lea     r15, WPP_GLOBAL_Control
0x140005e89  cmp     rcx, r15
0x140005e8c  jz      loc_140006650
0x140005e92  test    byte ptr [rcx+1Ch], 1
0x140005e96  jz      loc_140006650
0x140005e9c  cmp     byte ptr [rcx+19h], 2
0x140005ea0  jb      loc_140006650
0x140005ea6  mov     edx, 56h ; 'V'; SourceString
0x140005eab  jmp     short loc_140005E4D
0x140005ead  mov     rax, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; CTieringEngineLib * TieringEngineLibInstance
0x140005eb4  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x140005eb9  mov     [rbp+0A0h+SRWLock], rax
0x140005ebd  call    cs:__imp_RtlInitUnicodeString
0x140005ec3  lea     rdx, SourceString; "\\\\?\\Volume{bab6b806-2c70-4823-9d7c-a"...
0x140005eca  lea     rcx, [rbp+0A0h+var_F0]; DestinationString
0x140005ece  call    cs:__imp_RtlInitUnicodeString
0x140005ed4  movzx   edi, [rsp+1A0h+DestinationString.Length]
0x140005ed9  lea     r12, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140005ee0  movzx   esi, [rbp+0A0h+var_F0.Length]
0x140005ee4  lea     r15, WPP_GLOBAL_Control
0x140005eeb  shr     edi, 1
0x140005eed  mov     r8d, 5Ch ; '\'
0x140005ef3  shr     esi, 1
0x140005ef5  lea     eax, [rdi-2]
0x140005ef8  lea     r9d, [r8+5]
0x140005efc  cmp     eax, 1
0x140005eff  ja      loc_140006041
0x140005f05  lea     edx, [r8-22h]
0x140005f09  cmp     [rbx+2], dx
0x140005f0d  jnz     loc_140006041
0x140005f13  cmp     edi, 3
0x140005f16  jb      short loc_140005F23
0x140005f18  cmp     [rbx+4], r8w
0x140005f1d  jnz     loc_140006041
0x140005f23  movzx   ecx, word ptr [rbx]
0x140005f26  movzx   eax, cx
0x140005f29  sub     ax, r9w
0x140005f2d  cmp     ax, 19h
0x140005f31  jbe     short loc_140005F40
0x140005f33  lea     eax, [rcx-41h]
0x140005f36  cmp     ax, 19h
0x140005f3a  ja      loc_140006041
0x140005f40  xor     eax, eax
0x140005f42  mov     [rbp+0A0h+szVolumeMountPoint], cx
0x140005f46  lea     rdx, [rbp+0A0h+szVolumeName]; lpszVolumeName
0x140005f4a  mov     dword ptr [rbp+0A0h+szVolumeMountPoint+2], 5C003Ah
0x140005f51  lea     rcx, [rbp+0A0h+szVolumeMountPoint]; lpszVolumeMountPoint
0x140005f55  mov     [rbp+0A0h+var_AA], ax
0x140005f59  lea     r8d, [rax+32h]; cchBufferLength
0x140005f5d  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140005f63  test    eax, eax
0x140005f65  jnz     short loc_140005FA8
0x140005f67  lea     ecx, [rax+7Bh]; unsigned int
0x140005f6a  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140005f6f  mov     edi, eax
0x140005f71  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f78  cmp     rcx, r15
0x140005f7b  jz      short loc_140005FA1
0x140005f7d  test    byte ptr [rcx+1Ch], 1
0x140005f81  jz      short loc_140005FA1
0x140005f83  cmp     byte ptr [rcx+19h], 2
0x140005f87  jb      short loc_140005FA1
0x140005f89  mov     rcx, [rcx+10h]
0x140005f8d  mov     edx, 57h ; 'W'
0x140005f92  mov     r9, rbx
0x140005f95  mov     dword ptr [rsp+1A0h+lpOutBuffer], eax
0x140005f99  mov     r8, r12
0x140005f9c  call    WPP_SF_Sd
0x140005fa1  mov     eax, edi
0x140005fa3  jmp     loc_140006652
0x140005fa8  lea     rdx, [rbp+0A0h+szVolumeName]; SourceString
0x140005fac  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x140005fb1  call    cs:__imp_RtlInitUnicodeString
0x140005fb7  movzx   edi, [rsp+1A0h+DestinationString.Length]
0x140005fbc  shr     edi, 1
0x140005fbe  mov     r10, cs:WPP_GLOBAL_Control
0x140005fc5  cmp     r10, r15
0x140005fc8  jz      short loc_140005FFD
0x140005fca  test    byte ptr [r10+1Ch], 1
0x140005fcf  jz      short loc_140005FFD
0x140005fd1  cmp     byte ptr [r10+19h], 4
0x140005fd6  jb      short loc_140005FFD
0x140005fd8  mov     rax, [rsp+1A0h+DestinationString.Buffer]
0x140005fdd  mov     edx, 58h ; 'X'
0x140005fe2  mov     rcx, [r10+10h]
0x140005fe6  mov     r9, rbx
0x140005fe9  mov     r8, r12
0x140005fec  mov     [rsp+1A0h+lpOutBuffer], rax
0x140005ff1  call    WPP_SF_SS
0x140005ff6  mov     r10, cs:WPP_GLOBAL_Control
0x140005ffd  mov     r8d, 5Ch ; '\'
0x140006003  cmp     edi, esi
0x140006005  jnb     short loc_14000604A
0x140006007  mov     ecx, 7Bh ; '{'; unsigned int
0x14000600c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140006011  mov     ebx, eax
0x140006013  cmp     r10, r15
0x140006016  jz      loc_140006650
0x14000601c  test    byte ptr [r10+1Ch], 1
0x140006021  jz      loc_140006650
0x140006027  cmp     byte ptr [r10+19h], 2
0x14000602c  jb      loc_140006650
0x140006032  mov     r9, [rsp+1A0h+DestinationString.Buffer]
0x140006037  mov     edx, 59h ; 'Y'
0x14000603c  jmp     loc_140006640
0x140006041  mov     r10, cs:WPP_GLOBAL_Control
0x140006048  jmp     short loc_140006003
0x14000604a  mov     r9, [rsp+1A0h+DestinationString.Buffer]
0x14000604f  lea     eax, [rsi+1]
0x140006052  cmp     edi, eax
0x140006054  ja      loc_14000661C
0x14000605a  cmp     edi, esi
0x14000605c  jbe     short loc_140006069
0x14000605e  cmp     [r9+rsi*2], r8w
0x140006063  jnz     loc_14000661C
0x140006069  lea     eax, [rsi-1]
0x14000606c  cmp     word ptr [r9+rax*2], 7Dh ; '}'
0x140006072  jnz     loc_14000661C
0x140006078  mov     eax, 14h
0x14000607d  mov     [rsp+1A0h+String1.Buffer], r9
0x140006082  mov     [rsp+1A0h+String1.Length], ax
0x140006087  lea     rdx, aVolume_0; "\\\\?\\Volume"
0x14000608e  movzx   eax, [rsp+1A0h+DestinationString.MaximumLength]
0x140006093  lea     rcx, [rbp+0A0h+String2]; DestinationString
0x140006097  mov     [rsp+1A0h+String1.MaximumLength], ax
0x14000609c  call    cs:__imp_RtlInitUnicodeString
0x1400060a2  lea     rdx, aVolume; "\\??\\Volume"
0x1400060a9  lea     rcx, [rbp+0A0h+var_E0]; DestinationString
0x1400060ad  call    cs:__imp_RtlInitUnicodeString
0x1400060b3  mov     r8b, 1; CaseInsensitive
0x1400060b6  lea     rdx, [rbp+0A0h+String2]; String2
0x1400060ba  lea     rcx, [rsp+1A0h+String1]; String1
0x1400060bf  call    cs:__imp_RtlCompareUnicodeString
0x1400060c5  test    eax, eax
0x1400060c7  jz      short loc_140006122
0x1400060c9  mov     r8b, 1; CaseInsensitive
0x1400060cc  lea     rdx, [rbp+0A0h+var_E0]; String2
0x1400060d0  lea     rcx, [rsp+1A0h+String1]; String1
0x1400060d5  call    cs:__imp_RtlCompareUnicodeString
0x1400060db  test    eax, eax
0x1400060dd  jz      short loc_140006122
0x1400060df  mov     ecx, 7Bh ; '{'; unsigned int
0x1400060e4  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1400060e9  mov     ebx, eax
0x1400060eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060f2  cmp     rcx, r15
0x1400060f5  jz      loc_140006650
0x1400060fb  test    byte ptr [rcx+1Ch], 1
0x1400060ff  jz      loc_140006650
0x140006105  cmp     byte ptr [rcx+19h], 2
0x140006109  jb      loc_140006650
0x14000610f  mov     edx, 5Bh ; '['
0x140006114  mov     r9, [rsp+1A0h+DestinationString.Buffer]
0x140006119  mov     rcx, [rcx+10h]
0x14000611d  jmp     loc_140006644
0x140006122  mov     r8b, 1; CaseInsensitive
0x140006125  lea     rdx, [rbp+0A0h+String2]; String2
0x140006129  lea     rcx, [rsp+1A0h+String1]; String1
0x14000612e  call    cs:__imp_RtlCompareUnicodeString
0x140006134  test    eax, eax
0x140006136  jnz     short loc_140006143
0x140006138  mov     rax, [rsp+1A0h+DestinationString.Buffer]
0x14000613d  mov     word ptr [rax+2], 3Fh ; '?'
0x140006143  movzx   eax, [rbp+0A0h+String2.Length]
0x140006147  lea     rdx, [rbp+0A0h+Guid]; Guid
0x14000614b  add     rax, [rsp+1A0h+DestinationString.Buffer]
0x140006150  lea     rcx, [rbp+0A0h+GuidString]; GuidString
0x140006154  mov     [rbp+0A0h+GuidString.Buffer], rax
0x140006158  mov     dword ptr [rbp+0A0h+GuidString.Length], 4C004Ch
0x14000615f  call    cs:__imp_RtlGUIDFromString
0x140006165  test    eax, eax
0x140006167  jns     short loc_1400061A8
0x140006169  mov     ecx, eax; Status
0x14000616b  call    cs:__imp_RtlNtStatusToDosError
0x140006171  mov     ecx, eax; unsigned int
0x140006173  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140006178  mov     ebx, eax
0x14000617a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006181  cmp     rcx, r15
0x140006184  jz      loc_140006650
0x14000618a  test    byte ptr [rcx+1Ch], 1
0x14000618e  jz      loc_140006650
0x140006194  cmp     byte ptr [rcx+19h], 2
0x140006198  jb      loc_140006650
0x14000619e  mov     edx, 5Ch ; '\'
0x1400061a3  jmp     loc_140006114
0x1400061a8  mov     rdx, [rsp+1A0h+DestinationString.Buffer]; unsigned __int16 *
0x1400061ad  lea     r8, [rbp+0A0h+Guid]; struct _GUID *
0x1400061b1  mov     rcx, [rbp+0A0h+SRWLock]; SRWLock
0x1400061b5  mov     r9, r13; struct CTieredVolume **
0x1400061b8  call    ?FindVolumeByGuid@CTieringEngineLib@@AEAAJPEAGPEAU_GUID@@PEAPEAVCTieredVolume@@@Z; CTieringEngineLib::FindVolumeByGuid(ushort *,_GUID *,CTieredVolume * *)
0x1400061bd  mov     r13d, eax
0x1400061c0  test    eax, eax
0x1400061c2  jns     loc_1400065C9
0x1400061c8  movzx   esi, [rsp+1A0h+DestinationString.Length]
0x1400061cd  mov     edx, 5Ch ; '\'
0x1400061d2  mov     rdi, [rsp+1A0h+DestinationString.Buffer]
0x1400061d7  mov     ecx, esi
0x1400061d9  shr     rcx, 1
0x1400061dc  mov     [rsp+1A0h+Handle], 0
0x1400061e5  cmp     [rdi+rcx*2-2], dx
0x1400061ea  jz      loc_140006308
0x1400061f0  lea     rcx, [rsi+4]; Size
0x1400061f4  mov     dword ptr [rsp+1A0h+hDevice+4], 0
0x1400061fc  call    cs:__imp_malloc
0x140006202  mov     [rsp+1A0h+Block], rax
0x140006207  mov     rbx, rax
0x14000620a  test    rax, rax
0x14000620d  jnz     short loc_140006252
0x14000620f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006216  mov     esi, 8007000Eh
0x14000621b  cmp     rcx, r15
0x14000621e  jz      short loc_140006242
0x140006220  test    byte ptr [rcx+1Ch], 1
0x140006224  jz      short loc_140006242
0x140006226  cmp     byte ptr [rcx+19h], 2
0x14000622a  jb      short loc_140006242
0x14000622c  mov     rcx, [rcx+10h]
0x140006230  lea     edx, [rax+5Dh]
0x140006233  mov     r9, rdi
0x140006236  mov     dword ptr [rsp+1A0h+lpOutBuffer], esi
0x14000623a  mov     r8, r12
0x14000623d  call    WPP_SF_Sd
0x140006242  mov     rcx, rbx; Block
0x140006245  call    cs:__imp_free
0x14000624b  mov     eax, esi
0x14000624d  jmp     loc_140006652
0x140006252  xor     eax, eax
0x140006254  mov     [rsp+1A0h+var_148], rbx
0x140006259  mov     word ptr [rsp+1A0h+hDevice], ax
0x14000625e  lea     r9, [rsp+1A0h+hDevice]; struct _UNICODE_STRING *
0x140006263  lea     rax, [rsp+1A0h+Block]
0x140006268  add     si, 4
0x14000626c  lea     r8, ?BackslashString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x140006273  mov     [rsp+1A0h+lpOutBuffer], rax; __int64
0x140006278  lea     rdx, [rsp+1A0h+DestinationString]; struct _UNICODE_STRING *
0x14000627d  mov     word ptr [rsp+1A0h+hDevice+2], si
0x140006282  xor     ecx, ecx; struct _UNICODE_STRING *
0x140006284  call    ?CopyUnicodeStringToBuffer@@YAJPEBU_UNICODE_STRING@@00PEAU1@AEAV?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@@Z; CopyUnicodeStringToBuffer(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING *,ATL::CHeapPtr<ushort,ATL::CCRTAllocator> &)
0x140006289  mov     ebx, eax
0x14000628b  test    eax, eax
0x14000628d  jns     short loc_1400062DA
0x14000628f  mov     rcx, [rsp+1A0h+Block]; Block
0x140006294  call    cs:__imp_free
0x14000629a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062a1  cmp     rcx, r15
0x1400062a4  jz      short loc_1400062CD
0x1400062a6  test    byte ptr [rcx+1Ch], 1
0x1400062aa  jz      short loc_1400062CD
0x1400062ac  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
