# RdVhd::Util::CVhdHelper::SetVolumeOffline(ushort const *)

- ea: `0x18004ad48`
- end: `0x18004b09e`
- name: `?SetVolumeOffline@CVhdHelper@Util@RdVhd@@QEBAJPEBG@Z`
- size: `854`
- prototype: `__int64 __fastcall(RdVhd::Util::CVhdHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180017e40`
- `0x180018650`
- `0x180037310`
- `0x1800377c0`
- `0x180050c6c`
- `0x1800548a0`
- `0x180054b60`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180019b38`
- `0x18003114c`
- `0x180037110`
- `0x1800488e4`
- `0x180048b28`
- `0x18004ad48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aea8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004afbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aea8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004afbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b080`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ae93`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ae93`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004af3d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004afb4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004b027`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004af3d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004afb4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004b027`

## string_xrefs

- `0x18004adb5`: `szVolumePath`
- `0x18004aec6`: `Failed to open volume's disk drive ("%s")`

## pseudocode

```c
__int64 __fastcall RdVhd::Util::CVhdHelper::SetVolumeOffline(RdVhd::Util::CVhdHelper *this, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  int v3; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  const WCHAR *v7; // rax
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  void **v14; // [rsp+40h] [rbp-38h] BYREF
  int v15; // [rsp+48h] [rbp-30h]
  __int64 v16; // [rsp+4Ch] [rbp-2Ch]
  int v17; // [rsp+54h] [rbp-24h]
  __int64 v18; // [rsp+58h] [rbp-20h]
  int v19; // [rsp+60h] [rbp-18h]
  DWORD BytesReturned; // [rsp+B0h] [rbp+38h] BYREF
  int v21; // [rsp+B4h] [rbp+3Ch]

  v21 = HIDWORD(this);
  v16 = 128;
  BytesReturned = 0;
  v18 = 0;
  v17 = 0;
  v15 = 0;
  v14 = &CPathString::`vftable';
  v19 = 0x8000000;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_cd119b7af839377e03a1eca67cd76764_Traceguids,
        L"szVolumePath");
    }
    v2 = -2147024809;
    goto LABEL_51;
  }
  v3 = CBaseStringT<unsigned short>::Append((__int64)&v14, (__int64)a2);
  v2 = v3;
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_51;
    }
    v5 = 44;
LABEL_12:
    v6 = (unsigned int)v3;
    goto LABEL_13;
  }
  v3 = CPathString::TrimBackslash((CPathString *)&v14);
  v2 = v3;
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_51;
    }
    v5 = 45;
    goto LABEL_12;
  }
  v7 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v14);
  FileW = CreateFileW(v7, 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    CBaseStringT<unsigned short>::PContents(&v14);
    _TraceNrmRdvVmEx(L"VHDHLP", v2, L"Failed to open volume's disk drive (\"%s\")");
    if ( (v2 & 0x80000000) != 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_51;
      }
      v5 = 46;
      v6 = v2;
LABEL_13:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, v6);
      goto LABEL_51;
    }
  }
  if ( !DeviceIoControl(FileW, 0x90018u, 0, 0, 0, 0, &BytesReturned, 0) )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        WPP_cd119b7af839377e03a1eca67cd76764_Traceguids,
        (unsigned int)v10);
    }
  }
  if ( !DeviceIoControl(FileW, 0x90020u, 0, 0, 0, 0, &BytesReturned, 0) )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        WPP_cd119b7af839377e03a1eca67cd76764_Traceguids,
        (unsigned int)v11);
    }
  }
  v2 = 0;
  if ( !DeviceIoControl(FileW, 0x56C00Cu, 0, 0, 0, 0, &BytesReturned, 0) )
  {
    v12 = GetLastError();
    v2 = v12;
    if ( v12 > 0 )
      v2 = (unsigned __int16)v12 | 0x80070000;
    if ( (v2 & 0x80000000) != 0
      && WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, v2);
    }
  }
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
LABEL_51:
  CPathString::~CPathString((CPathString *)&v14);
  return v2;
}

```

## disassembly

```asm
0x18004ad48  mov     qword ptr [rsp-30h+BytesReturned], rcx
0x18004ad4d  push    rbp
0x18004ad4e  push    rbx
0x18004ad4f  push    rsi
0x18004ad50  push    rdi
0x18004ad51  push    r14
0x18004ad53  push    r15
0x18004ad55  mov     rbp, rsp
0x18004ad58  sub     rsp, 78h
0x18004ad5c  xor     r14d, r14d
0x18004ad5f  mov     [rbp+var_2C], 80h
0x18004ad67  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x18004ad6e  mov     [rbp+BytesReturned], r14d
0x18004ad72  mov     [rbp+var_20], r14
0x18004ad76  mov     [rbp+var_24], r14d
0x18004ad7a  mov     [rbp+var_30], r14d
0x18004ad7e  mov     [rbp+var_38], rax
0x18004ad82  mov     [rbp+var_18], 8000000h
0x18004ad89  test    rdx, rdx
0x18004ad8c  jnz     short loc_18004ADD2
0x18004ad8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ad95  lea     rdi, WPP_GLOBAL_Control
0x18004ad9c  cmp     rcx, rdi
0x18004ad9f  jz      short loc_18004ADC8
0x18004ada1  test    byte ptr [rcx+1Ch], 1
0x18004ada5  jz      short loc_18004ADC8
0x18004ada7  cmp     byte ptr [rcx+19h], 2
0x18004adab  jb      short loc_18004ADC8
0x18004adad  mov     rcx, [rcx+10h]
0x18004adb1  lea     edx, [r14+2Bh]
0x18004adb5  lea     r9, aSzvolumepath; "szVolumePath"
0x18004adbc  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x18004adc3  call    WPP_SF_S
0x18004adc8  mov     ebx, 80070057h
0x18004adcd  jmp     loc_18004B086
0x18004add2  lea     rcx, [rbp+var_38]
0x18004add6  call    ?Append@?$CBaseStringT@G@@QEAAJPEBG@Z; CBaseStringT<ushort>::Append(ushort const *)
0x18004addb  mov     ebx, eax
0x18004addd  test    eax, eax
0x18004addf  jns     short loc_18004AE29
0x18004ade1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ade8  lea     rdi, WPP_GLOBAL_Control
0x18004adef  cmp     rcx, rdi
0x18004adf2  jz      loc_18004B086
0x18004adf8  test    byte ptr [rcx+1Ch], 1
0x18004adfc  jz      loc_18004B086
0x18004ae02  cmp     byte ptr [rcx+19h], 2
0x18004ae06  jb      loc_18004B086
0x18004ae0c  mov     edx, 2Ch ; ','
0x18004ae11  mov     r9d, eax
0x18004ae14  mov     rcx, [rcx+10h]
0x18004ae18  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x18004ae1f  call    WPP_SF_d
0x18004ae24  jmp     loc_18004B086
0x18004ae29  lea     rcx, [rbp+var_38]; this
0x18004ae2d  call    ?TrimBackslash@CPathString@@QEAAJXZ; CPathString::TrimBackslash(void)
0x18004ae32  mov     ebx, eax
0x18004ae34  test    eax, eax
0x18004ae36  jns     short loc_18004AE6A
0x18004ae38  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ae3f  lea     rdi, WPP_GLOBAL_Control
0x18004ae46  cmp     rcx, rdi
0x18004ae49  jz      loc_18004B086
0x18004ae4f  test    byte ptr [rcx+1Ch], 1
0x18004ae53  jz      loc_18004B086
0x18004ae59  cmp     byte ptr [rcx+19h], 2
0x18004ae5d  jb      loc_18004B086
0x18004ae63  mov     edx, 2Dh ; '-'
0x18004ae68  jmp     short loc_18004AE11
0x18004ae6a  lea     rcx, [rbp+var_38]
0x18004ae6e  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004ae73  mov     r8d, 3; dwShareMode
0x18004ae79  mov     [rsp+78h+hTemplateFile], r14; hTemplateFile
0x18004ae7e  mov     rcx, rax; lpFileName
0x18004ae81  mov     [rsp+78h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x18004ae86  xor     r9d, r9d; lpSecurityAttributes
0x18004ae89  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18004ae8e  mov     edx, 0C0000000h; dwDesiredAccess
0x18004ae93  call    cs:__imp_CreateFileW
0x18004ae99  mov     rsi, rax
0x18004ae9c  mov     r15d, 80070000h
0x18004aea2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004aea6  jnz     short loc_18004AF17
0x18004aea8  call    cs:__imp_GetLastError
0x18004aeae  mov     ebx, eax
0x18004aeb0  test    eax, eax
0x18004aeb2  jle     short loc_18004AEBA
0x18004aeb4  movzx   ebx, ax
0x18004aeb7  or      ebx, r15d
0x18004aeba  lea     rcx, [rbp+var_38]
0x18004aebe  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004aec3  mov     r9, rax
0x18004aec6  lea     r8, aFailedToOpenVo; "Failed to open volume's disk drive (\"%"...
0x18004aecd  mov     edx, ebx; int
0x18004aecf  lea     rcx, aVhdhlp; "VHDHLP"
0x18004aed6  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x18004aedb  test    ebx, ebx
0x18004aedd  jns     short loc_18004AF17
0x18004aedf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aee6  lea     rdi, WPP_GLOBAL_Control
0x18004aeed  cmp     rcx, rdi
0x18004aef0  jz      loc_18004B086
0x18004aef6  test    byte ptr [rcx+1Ch], 1
0x18004aefa  jz      loc_18004B086
0x18004af00  cmp     byte ptr [rcx+19h], 2
0x18004af04  jb      loc_18004B086
0x18004af0a  mov     edx, 2Eh ; '.'
0x18004af0f  mov     r9d, ebx
0x18004af12  jmp     loc_18004AE14
0x18004af17  mov     [rsp+78h+lpOverlapped], r14; lpOverlapped
0x18004af1c  lea     rax, [rbp+BytesReturned]
0x18004af20  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18004af25  xor     r9d, r9d; nInBufferSize
0x18004af28  mov     [rsp+78h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18004af2d  xor     r8d, r8d; lpInBuffer
0x18004af30  mov     edx, 90018h; dwIoControlCode
0x18004af35  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOutBuffer
0x18004af3a  mov     rcx, rsi; hDevice
0x18004af3d  call    cs:__imp_DeviceIoControl
0x18004af43  lea     rdi, WPP_GLOBAL_Control
0x18004af4a  test    eax, eax
0x18004af4c  jnz     short loc_18004AF8E
0x18004af4e  call    cs:__imp_GetLastError
0x18004af54  test    eax, eax
0x18004af56  jle     short loc_18004AF5E
0x18004af58  movzx   eax, ax
0x18004af5b  or      eax, r15d
0x18004af5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004af65  cmp     rcx, rdi
0x18004af68  jz      short loc_18004AF8E
0x18004af6a  test    byte ptr [rcx+1Ch], 1
0x18004af6e  jz      short loc_18004AF8E
0x18004af70  cmp     byte ptr [rcx+19h], 2
0x18004af74  jb      short loc_18004AF8E
0x18004af76  mov     rcx, [rcx+10h]
0x18004af7a  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x18004af81  mov     edx, 2Fh ; '/'
0x18004af86  mov     r9d, eax
0x18004af89  call    WPP_SF_d
0x18004af8e  mov     [rsp+78h+lpOverlapped], r14; lpOverlapped
0x18004af93  lea     rax, [rbp+BytesReturned]
0x18004af97  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18004af9c  xor     r9d, r9d; nInBufferSize
0x18004af9f  mov     [rsp+78h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18004afa4  xor     r8d, r8d; lpInBuffer
0x18004afa7  mov     edx, 90020h; dwIoControlCode
0x18004afac  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOutBuffer
0x18004afb1  mov     rcx, rsi; hDevice
0x18004afb4  call    cs:__imp_DeviceIoControl
0x18004afba  test    eax, eax
0x18004afbc  jnz     short loc_18004AFFE
0x18004afbe  call    cs:__imp_GetLastError
0x18004afc4  test    eax, eax
0x18004afc6  jle     short loc_18004AFCE
0x18004afc8  movzx   eax, ax
0x18004afcb  or      eax, r15d
0x18004afce  mov     rcx, cs:WPP_GLOBAL_Control
0x18004afd5  cmp     rcx, rdi
0x18004afd8  jz      short loc_18004AFFE
0x18004afda  test    byte ptr [rcx+1Ch], 1
0x18004afde  jz      short loc_18004AFFE
0x18004afe0  cmp     byte ptr [rcx+19h], 2
0x18004afe4  jb      short loc_18004AFFE
0x18004afe6  mov     rcx, [rcx+10h]
0x18004afea  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x18004aff1  mov     edx, 30h ; '0'
0x18004aff6  mov     r9d, eax
0x18004aff9  call    WPP_SF_d
0x18004affe  mov     [rsp+78h+lpOverlapped], r14; lpOverlapped
0x18004b003  lea     rax, [rbp+BytesReturned]
0x18004b007  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18004b00c  xor     r9d, r9d; nInBufferSize
0x18004b00f  mov     [rsp+78h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18004b014  xor     r8d, r8d; lpInBuffer
0x18004b017  mov     edx, 56C00Ch; dwIoControlCode
0x18004b01c  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOutBuffer
0x18004b021  mov     rcx, rsi; hDevice
0x18004b024  mov     ebx, r14d
0x18004b027  call    cs:__imp_DeviceIoControl
0x18004b02d  test    eax, eax
0x18004b02f  jnz     short loc_18004B077
0x18004b031  call    cs:__imp_GetLastError
0x18004b037  mov     ebx, eax
0x18004b039  test    eax, eax
0x18004b03b  jle     short loc_18004B043
0x18004b03d  movzx   ebx, ax
0x18004b040  or      ebx, r15d
0x18004b043  test    ebx, ebx
0x18004b045  jns     short loc_18004B077
0x18004b047  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b04e  cmp     rcx, rdi
0x18004b051  jz      short loc_18004B077
0x18004b053  test    byte ptr [rcx+1Ch], 1
0x18004b057  jz      short loc_18004B077
0x18004b059  cmp     byte ptr [rcx+19h], 2
0x18004b05d  jb      short loc_18004B077
0x18004b05f  mov     rcx, [rcx+10h]
0x18004b063  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x18004b06a  mov     edx, 31h ; '1'
0x18004b06f  mov     r9d, ebx
0x18004b072  call    WPP_SF_d
0x18004b077  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18004b07b  jz      short loc_18004B086
0x18004b07d  mov     rcx, rsi; hObject
0x18004b080  call    cs:__imp_CloseHandle
0x18004b086  lea     rcx, [rbp+var_38]; this
0x18004b08a  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18004b08f  mov     eax, ebx
0x18004b091  add     rsp, 78h
0x18004b095  pop     r15
0x18004b097  pop     r14
0x18004b099  pop     rdi
0x18004b09a  pop     rsi
0x18004b09b  pop     rbx
0x18004b09c  pop     rbp
0x18004b09d  retn
```
