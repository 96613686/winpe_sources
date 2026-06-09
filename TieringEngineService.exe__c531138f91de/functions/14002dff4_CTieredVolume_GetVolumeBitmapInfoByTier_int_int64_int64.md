# CTieredVolume::GetVolumeBitmapInfoByTier(int,__int64 *,__int64 *)

- ea: `0x14002dff4`
- end: `0x14002e864`
- name: `?GetVolumeBitmapInfoByTier@CTieredVolume@@AEAAJHPEA_J0@Z`
- size: `2160`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, int, __int64 *, __int64 *)`
- caller_count: `3`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140023bb8`
- `0x14002eef0`
- `0x14003e49c`

## callees

- `0x140002323`
- `0x140002db0`
- `0x140004aa8`
- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x140025d28`
- `0x14002dff4`
- `0x140035744`
- `0x1400357f0`
- `0x140035b60`
- `0x140035d68`
- `0x14003fbb0`

## import_xrefs

- `msvcrt!malloc` at `0x14002e22d`
- `msvcrt!malloc` at `0x14002e22d`
- `msvcrt!free` at `0x14002e819`
- `msvcrt!free` at `0x14002e819`
- `ntdll!RtlSetBits` at `0x14002e69a`
- `ntdll!RtlSetBits` at `0x14002e69a`
- `ntdll!RtlInitializeBitMap` at `0x14002e60e`
- `ntdll!RtlInitializeBitMap` at `0x14002e60e`
- `ntdll!NtOpenFile` at `0x14002e19e`
- `ntdll!NtOpenFile` at `0x14002e19e`
- `ntdll!RtlGetThreadErrorMode` at `0x14002e0a0`
- `ntdll!RtlGetThreadErrorMode` at `0x14002e0a0`
- `ntdll!RtlSetThreadErrorMode` at `0x14002e0b0`
- `ntdll!RtlSetThreadErrorMode` at `0x14002e0cf`
- `ntdll!RtlSetThreadErrorMode` at `0x14002e0b0`
- `ntdll!RtlSetThreadErrorMode` at `0x14002e0cf`
- `ntdll!RtlNumberOfClearBits` at `0x14002e6ac`
- `ntdll!RtlNumberOfClearBits` at `0x14002e6ac`
- `ntdll!NtClose` at `0x14002e829`
- `ntdll!NtClose` at `0x14002e829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e3d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e3d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002e14a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002e1af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002e7f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002e14a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002e1af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002e7f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14002e0e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14002e2ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14002e0e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14002e2ea`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002e320`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002e3cf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002e320`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002e3cf`

## pseudocode

```c
__int64 __fastcall CTieredVolume::GetVolumeBitmapInfoByTier(RTL_SRWLOCK *this, int a2, __int64 *a3, __int64 *a4)
{
  PVOID ThreadLocalStoragePointer; // rax
  char *v9; // r13
  ULONG ThreadErrorMode; // eax
  NTSTATUS v11; // eax
  char v12; // cl
  RTL_SRWLOCK *v13; // rbx
  unsigned int v14; // edi
  NTSTATUS v15; // r14d
  unsigned int v16; // edi
  char *v17; // rax
  unsigned int v18; // ecx
  char *v19; // r14
  DWORD v20; // eax
  DWORD LastError; // eax
  __int64 v22; // rdi
  _QWORD *v23; // r10
  ULONG v24; // r8d
  char *v25; // r13
  _QWORD *Ptr; // r12
  char *v27; // rbx
  __int64 v28; // rdi
  char *v29; // rcx
  char *v30; // rax
  ULONG v31; // r13d
  int v32; // edx
  __int64 v33; // r8
  ULONG v34; // edi
  ULONG v35; // r12d
  ULONG v36; // r12d
  ULONG v37; // eax
  __int64 v38; // r9
  char v39; // dl
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rax
  unsigned int v44; // [rsp+40h] [rbp-C0h]
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  ULONG OldMode; // [rsp+48h] [rbp-B8h] BYREF
  char v47; // [rsp+4Ch] [rbp-B4h]
  int v48; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v49; // [rsp+58h] [rbp-A8h]
  char *v50; // [rsp+60h] [rbp-A0h]
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  char v54[8]; // [rsp+80h] [rbp-80h] BYREF
  int v55; // [rsp+88h] [rbp-78h]
  unsigned __int64 v56; // [rsp+90h] [rbp-70h]
  unsigned __int64 v57; // [rsp+98h] [rbp-68h]
  unsigned __int64 v58; // [rsp+A0h] [rbp-60h]
  __int64 v59; // [rsp+A8h] [rbp-58h]
  _QWORD *v60; // [rsp+B0h] [rbp-50h]
  __int64 *v61; // [rsp+B8h] [rbp-48h]
  __int64 *v62; // [rsp+C0h] [rbp-40h]
  _RTL_BITMAP BitMapHeader; // [rsp+C8h] [rbp-38h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp+8h] BYREF
  __int128 InBuffer; // [rsp+118h] [rbp+18h] BYREF
  _BYTE OutBuffer[80]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v68; // [rsp+180h] [rbp+80h]
  unsigned __int64 v69; // [rsp+188h] [rbp+88h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v62 = a4;
  v61 = a3;
  *(_QWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 8LL) = "CTieredVolume::GetVolumeBitmapInfoByTier";
  CHResultImp::CHResultImp((CHResultImp *)v54);
  *a3 = 0;
  *a4 = 0;
  v9 = 0;
  BytesReturned = 0;
  InBuffer = 0;
  memset_0(OutBuffer, 0, 0x60u);
  v53 = 0;
  v52 = 0;
  if ( !a2 )
  {
    v47 = 0;
    ThreadErrorMode = RtlGetThreadErrorMode();
    v11 = RtlSetThreadErrorMode(ThreadErrorMode | 0x10, &OldMode);
    v12 = v47;
    if ( v11 >= 0 )
      v12 = 1;
    v47 = v12;
    if ( v12 )
      RtlSetThreadErrorMode(OldMode, 0);
  }
  FileHandle = 0;
  v13 = this + 3;
  IoStatusBlock = 0;
  AcquireSRWLockShared(this + 3);
  if ( !BYTE1(this[90].Ptr) )
  {
    v14 = -2138898430;
    v55 = -2138898430;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        209,
        &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        LODWORD(this[16].Ptr),
        -2138898430);
    }
LABEL_11:
    if ( v13 )
      ReleaseSRWLockShared(v13);
    goto LABEL_118;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&this[18];
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 192;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v15 = NtOpenFile(&FileHandle, 0x100003u, &ObjectAttributes, &IoStatusBlock, 7u, 0x21u);
  if ( this != (RTL_SRWLOCK *)-24LL )
    ReleaseSRWLockShared(this + 3);
  if ( v15 < 0 )
  {
    v14 = v15 | 0x10000000;
    v55 = v15 | 0x10000000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        210,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        (_DWORD)this + 144,
        v15);
    }
    goto LABEL_118;
  }
  v16 = 4 * (((unsigned __int64)this[72].Ptr + 31) >> 5);
  do
  {
    if ( !v16 )
      break;
    v17 = (char *)malloc(v16 + 28LL);
    v9 = v17;
    v18 = v16 >> 1;
    if ( v17 )
      v18 = v16;
    v16 = v18;
  }
  while ( !v17 );
  v50 = v9;
  if ( !v9 )
  {
    v14 = -2147024882;
    v55 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        211,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        (_DWORD)this + 144,
        14);
    }
    goto LABEL_118;
  }
  v19 = 0;
  v56 = -1;
  v49 = -1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_IIZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, v16, (_DWORD)v9, v16, (__int64)&this[84]);
  }
  AcquireSRWLockShared(this + 3);
  if ( DeviceIoControl(FileHandle, 0x90064u, 0, 0, OutBuffer, 0x60u, &BytesReturned, 0) )
  {
    v56 = v68;
    v49 = v69;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_iiZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        213,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        v68,
        v69,
        (__int64)&this[84]);
    }
  }
  if ( this[72].Ptr )
  {
    v20 = v16 + 24;
    OldMode = v16 + 24;
    while ( 2 )
    {
      *((_QWORD *)&InBuffer + 1) = 1;
      *(_QWORD *)&InBuffer = v19;
      if ( !DeviceIoControl(FileHandle, 0x9006Fu, &InBuffer, 0x10u, v9, v20, &BytesReturned, 0) )
      {
        LastError = GetLastError();
        if ( LastError != -2147483643 )
        {
          v14 = ATL::AtlHresultFromWin32(LastError);
          v55 = v14;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_iZd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              214,
              (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
              (_DWORD)v19,
              (__int64)&this[84],
              v14);
          }
          goto LABEL_11;
        }
      }
      v22 = BytesReturned - 24LL;
      v58 = v22;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_iiZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          215,
          (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
          BytesReturned,
          BytesReturned - 24,
          (__int64)&this[84]);
        v23 = WPP_GLOBAL_Control;
      }
      if ( !v22 )
        break;
      v24 = 0;
      v25 = &v19[8 * v22];
      v44 = 0;
      v57 = (unsigned __int64)v25;
LABEL_50:
      if ( v19 >= v25 )
        goto LABEL_109;
      if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 5u )
      {
        WPP_SF_iiZ(
          v23[2],
          216,
          (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
          v24,
          (char)v19,
          (__int64)&this[84]);
        v23 = WPP_GLOBAL_Control;
      }
      Ptr = this[10].Ptr;
      v48 = 0;
      if ( Ptr )
      {
        v27 = v50;
        while ( 1 )
        {
          v28 = Ptr[2];
          Ptr = (_QWORD *)*Ptr;
          v60 = Ptr;
          v59 = v28;
          if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 5u )
          {
            WPP_SF_iiZ(
              v23[2],
              217,
              (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
              *(_QWORD *)(v28 + 16),
              *(_QWORD *)(v28 + 24),
              (__int64)&this[84]);
            v23 = WPP_GLOBAL_Control;
          }
          v29 = (char *)this[72].Ptr;
          v30 = *(char **)(v28 + 24);
          if ( v30 >= v29 )
          {
            v30 = v29 - 1;
            *(_QWORD *)(v28 + 24) = v29 - 1;
            v23 = WPP_GLOBAL_Control;
          }
          if ( *(_QWORD *)(v28 + 16) <= (unsigned __int64)v19 && v30 >= v19 )
            break;
          v24 = v44;
LABEL_100:
          if ( !Ptr )
          {
            v13 = this + 3;
            v22 = v58;
            if ( !v48 )
              goto LABEL_104;
            if ( v58 <= v24 )
              goto LABEL_109;
            goto LABEL_50;
          }
        }
        v48 = 1;
        if ( v30 < v25 )
        {
          v31 = *(_DWORD *)(v28 + 24) - (_DWORD)v19 + 1;
          if ( v23 == &WPP_GLOBAL_Control || (*((_BYTE *)v23 + 28) & 1) == 0 || *((_BYTE *)v23 + 25) < 5u )
            goto LABEL_75;
          v32 = 219;
        }
        else
        {
          v31 = (_DWORD)v25 - (_DWORD)v19 + 1;
          if ( v23 == &WPP_GLOBAL_Control || (*((_BYTE *)v23 + 28) & 1) == 0 || *((_BYTE *)v23 + 25) < 5u )
            goto LABEL_75;
          v32 = 218;
        }
        WPP_SF_IZ(v23[2], v32, v24, v31, (__int64)&this[84]);
        v23 = WPP_GLOBAL_Control;
LABEL_75:
        BitMapHeader = 0;
        if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 5u )
          WPP_SF_IIZ(v23[2], 220, v31, (_DWORD)v27 + v44 + 16, v31, (__int64)&this[84]);
        RtlInitializeBitMap(&BitMapHeader, (PULONG)&v27[v44 + 16], v31);
        if ( (v56 & 0x8000000000000000uLL) == 0LL && (unsigned __int64)v19 >= v56 && (unsigned __int64)v19 <= v49
          || v57 >= v56 && v57 <= v49 )
        {
          if ( v56 <= (unsigned __int64)v19 )
            v34 = 0;
          else
            v34 = v56 - (_DWORD)v19;
          v35 = v49;
          if ( v49 >= (unsigned __int64)&v19[v31 - 1] )
            v35 = (_DWORD)v19 + v31 - 1;
          v36 = v35 - (_DWORD)v19 - v34 + 1;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_iDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v49, v33, v19, v34, v36);
          }
          RtlSetBits(&BitMapHeader, v34, v36);
          v28 = v59;
          Ptr = v60;
        }
        v37 = RtlNumberOfClearBits(&BitMapHeader);
        v38 = v53;
        v39 = *(_BYTE *)(v28 + 36);
        v23 = WPP_GLOBAL_Control;
        v24 = (v31 >> 3) + v44;
        v40 = v37;
        v41 = v31;
        v25 = (char *)v57;
        v19 += v41;
        v44 = v24;
        if ( !v39 )
          v38 = v40 + v53;
        v53 = v38;
        v42 = v40 + v52;
        if ( !v39 )
          v42 = v52;
        v52 = v42;
        goto LABEL_100;
      }
LABEL_104:
      if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 3u )
        WPP_SF_IZ(v23[2], 222, v24, (_DWORD)v19, (__int64)&this[84]);
      v19 += 8 * (v22 - v44);
LABEL_109:
      v9 = v50;
      if ( v19 < this[72].Ptr )
      {
        v20 = OldMode;
        continue;
      }
      break;
    }
  }
  if ( v13 )
    ReleaseSRWLockShared(v13);
  v14 = v55;
LABEL_118:
  *v61 = v52;
  *v62 = v53;
  if ( v9 )
    free(v9);
  if ( FileHandle )
    NtClose(FileHandle);
  CHResultImp::~CHResultImp((CHResultImp *)v54);
  return v14;
}

```

## disassembly

```asm
0x14002dff4  mov     [rsp-8+arg_8], rbx
0x14002dff9  push    rbp
0x14002dffa  push    rsi
0x14002dffb  push    rdi
0x14002dffc  push    r12
0x14002dffe  push    r13
0x14002e000  push    r14
0x14002e002  push    r15
0x14002e004  lea     rbp, [rsp-0A0h]
0x14002e00c  sub     rsp, 1A0h
0x14002e013  mov     rax, cs:__security_cookie
0x14002e01a  xor     rax, rsp
0x14002e01d  mov     [rbp+0D0h+var_40], rax
0x14002e024  mov     rax, gs:58h
0x14002e02d  mov     r15, rcx
0x14002e030  mov     ebx, edx
0x14002e032  mov     [rbp+0D0h+var_110], r9
0x14002e036  mov     edx, 8
0x14002e03b  mov     rsi, r9
0x14002e03e  mov     rdi, r8
0x14002e041  mov     [rbp+0D0h+var_118], r8
0x14002e045  mov     rcx, [rax]
0x14002e048  lea     rax, aCtieredvolumeG_10; "CTieredVolume::GetVolumeBitmapInfoByTie"...
0x14002e04f  mov     [rdx+rcx], rax
0x14002e053  lea     rcx, [rbp+0D0h+var_150]; this
0x14002e057  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14002e05c  xorps   xmm0, xmm0
0x14002e05f  mov     qword ptr [rdi], 0
0x14002e066  mov     qword ptr [rsi], 0
0x14002e06d  lea     rcx, [rbp+0D0h+OutBuffer]; void *
0x14002e071  xor     esi, esi
0x14002e073  xor     edx, edx; Val
0x14002e075  mov     r13d, esi
0x14002e078  mov     [rsp+1D0h+BytesReturned], esi
0x14002e07c  movups  [rbp+0D0h+InBuffer], xmm0
0x14002e080  lea     r8d, [rsi+60h]; Size
0x14002e084  call    memset_0
0x14002e089  mov     [rsp+1D0h+var_158], rsi
0x14002e08e  lea     r14d, [rsi+1]
0x14002e092  mov     [rsp+1D0h+var_160], rsi
0x14002e097  test    ebx, ebx
0x14002e099  jnz     short loc_14002E0D5
0x14002e09b  mov     [rsp+1D0h+var_184], sil
0x14002e0a0  call    cs:__imp_RtlGetThreadErrorMode
0x14002e0a6  or      eax, 10h
0x14002e0a9  lea     rdx, [rsp+1D0h+OldMode]; OldMode
0x14002e0ae  mov     ecx, eax; NewMode
0x14002e0b0  call    cs:__imp_RtlSetThreadErrorMode
0x14002e0b6  movzx   ecx, [rsp+1D0h+var_184]
0x14002e0bb  test    eax, eax
0x14002e0bd  cmovns  ecx, r14d
0x14002e0c1  mov     [rsp+1D0h+var_184], cl
0x14002e0c5  test    cl, cl
0x14002e0c7  jz      short loc_14002E0D5
0x14002e0c9  mov     ecx, [rsp+1D0h+OldMode]; NewMode
0x14002e0cd  xor     edx, edx; OldMode
0x14002e0cf  call    cs:__imp_RtlSetThreadErrorMode
0x14002e0d5  xorps   xmm0, xmm0
0x14002e0d8  mov     [rsp+1D0h+FileHandle], rsi
0x14002e0dd  lea     rbx, [r15+18h]
0x14002e0e1  mov     rcx, rbx; SRWLock
0x14002e0e4  movups  xmmword ptr [rbp+0D0h+IoStatusBlock], xmm0
0x14002e0e8  call    cs:__imp_AcquireSRWLockShared
0x14002e0ee  cmp     [r15+2D1h], sil
0x14002e0f5  jnz     short loc_14002E155
0x14002e0f7  mov     edi, 80830002h
0x14002e0fc  mov     [rbp+0D0h+var_148], edi
0x14002e0ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e106  lea     rsi, WPP_GLOBAL_Control
0x14002e10d  cmp     rcx, rsi
0x14002e110  jz      short loc_14002E13E
0x14002e112  test    [rcx+1Ch], r14b
0x14002e116  jz      short loc_14002E13E
0x14002e118  cmp     byte ptr [rcx+19h], 2
0x14002e11c  jb      short loc_14002E13E
0x14002e11e  mov     r9d, [r15+80h]
0x14002e125  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002e12c  mov     rcx, [rcx+10h]
0x14002e130  mov     edx, 0D1h
0x14002e135  mov     [rsp+1D0h+ShareAccess], edi
0x14002e139  call    WPP_SF_Dd
0x14002e13e  test    rbx, rbx
0x14002e141  jz      loc_14002E7F9
0x14002e147  mov     rcx, rbx; SRWLock
0x14002e14a  call    cs:__imp_ReleaseSRWLockShared
0x14002e150  jmp     loc_14002E7F9
0x14002e155  xorps   xmm0, xmm0
0x14002e158  mov     [rsp+1D0h+OpenOptions], 21h ; '!'; OpenOptions
0x14002e160  lea     r12, [r15+90h]
0x14002e167  mov     qword ptr [rbp+0D0h+ObjectAttributes.Length], 30h ; '0'
0x14002e16f  lea     r9, [rbp+0D0h+IoStatusBlock]; IoStatusBlock
0x14002e173  mov     [rbp+0D0h+ObjectAttributes.ObjectName], r12
0x14002e177  lea     r8, [rbp+0D0h+ObjectAttributes]; ObjectAttributes
0x14002e17b  mov     [rbp+0D0h+ObjectAttributes.RootDirectory], rsi
0x14002e17f  mov     edx, 100003h; DesiredAccess
0x14002e184  mov     qword ptr [rbp+0D0h+ObjectAttributes.Attributes], 0C0h
0x14002e18c  lea     rcx, [rsp+1D0h+FileHandle]; FileHandle
0x14002e191  mov     [rsp+1D0h+ShareAccess], 7; ShareAccess
0x14002e199  movdqu  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002e19e  call    cs:__imp_NtOpenFile
0x14002e1a4  mov     r14d, eax
0x14002e1a7  test    rbx, rbx
0x14002e1aa  jz      short loc_14002E1B5
0x14002e1ac  mov     rcx, rbx; SRWLock
0x14002e1af  call    cs:__imp_ReleaseSRWLockShared
0x14002e1b5  test    r14d, r14d
0x14002e1b8  jns     short loc_14002E211
0x14002e1ba  mov     edi, r14d
0x14002e1bd  bts     edi, 1Ch
0x14002e1c1  mov     [rbp+0D0h+var_148], edi
0x14002e1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e1cb  lea     rsi, WPP_GLOBAL_Control
0x14002e1d2  cmp     rcx, rsi
0x14002e1d5  jz      loc_14002E7F9
0x14002e1db  test    byte ptr [rcx+1Ch], 1
0x14002e1df  jz      loc_14002E7F9
0x14002e1e5  cmp     byte ptr [rcx+19h], 2
0x14002e1e9  jb      loc_14002E7F9
0x14002e1ef  mov     edx, 0D2h
0x14002e1f4  mov     [rsp+1D0h+ShareAccess], r14d
0x14002e1f9  mov     rcx, [rcx+10h]
0x14002e1fd  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002e204  mov     r9, r12
0x14002e207  call    WPP_SF_Zd
0x14002e20c  jmp     loc_14002E7F9
0x14002e211  mov     rdi, [r15+240h]
0x14002e218  add     rdi, 1Fh
0x14002e21c  shr     rdi, 5
0x14002e220  shl     edi, 2
0x14002e223  test    edi, edi
0x14002e225  jz      short loc_14002E244
0x14002e227  mov     ecx, edi
0x14002e229  add     rcx, 1Ch; Size
0x14002e22d  call    cs:__imp_malloc
0x14002e233  mov     ecx, edi
0x14002e235  mov     r13, rax
0x14002e238  shr     ecx, 1
0x14002e23a  test    rax, rax
0x14002e23d  cmovnz  ecx, edi
0x14002e240  mov     edi, ecx
0x14002e242  jz      short loc_14002E223
0x14002e244  mov     [rsp+1D0h+var_170], r13
0x14002e249  test    r13, r13
0x14002e24c  jnz     short loc_14002E28F
0x14002e24e  mov     edi, 8007000Eh
0x14002e253  mov     [rbp+0D0h+var_148], edi
0x14002e256  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e25d  lea     rsi, WPP_GLOBAL_Control
0x14002e264  cmp     rcx, rsi
0x14002e267  jz      loc_14002E7F9
0x14002e26d  test    byte ptr [rcx+1Ch], 1
0x14002e271  jz      loc_14002E7F9
0x14002e277  cmp     byte ptr [rcx+19h], 2
0x14002e27b  jb      loc_14002E7F9
0x14002e281  mov     edx, 0D3h
0x14002e286  mov     [rsp+1D0h+ShareAccess], edi
0x14002e28a  jmp     loc_14002E1F9
0x14002e28f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e296  or      r9, 0FFFFFFFFFFFFFFFFh
0x14002e29a  mov     r14, rsi
0x14002e29d  mov     [rbp+0D0h+var_140], r9
0x14002e2a1  lea     rsi, WPP_GLOBAL_Control
0x14002e2a8  mov     [rsp+1D0h+var_178], r9
0x14002e2ad  lea     r12d, [r9+2]
0x14002e2b1  cmp     rcx, rsi
0x14002e2b4  jz      short loc_14002E2E7
0x14002e2b6  test    [rcx+1Ch], r12b
0x14002e2ba  jz      short loc_14002E2E7
0x14002e2bc  cmp     byte ptr [rcx+19h], 5
0x14002e2c0  jb      short loc_14002E2E7
0x14002e2c2  mov     rcx, [rcx+10h]
0x14002e2c6  lea     rax, [r15+2A0h]
0x14002e2cd  mov     r8d, edi
0x14002e2d0  mov     edx, 0D4h
0x14002e2d5  mov     qword ptr [rsp+1D0h+OpenOptions], rax
0x14002e2da  mov     r9, r13
0x14002e2dd  mov     qword ptr [rsp+1D0h+ShareAccess], r8
0x14002e2e2  call    WPP_SF_IIZ
0x14002e2e7  mov     rcx, rbx; SRWLock
0x14002e2ea  call    cs:__imp_AcquireSRWLockShared
0x14002e2f0  mov     rcx, [rsp+1D0h+FileHandle]; hDevice
0x14002e2f5  lea     rax, [rsp+1D0h+BytesReturned]
0x14002e2fa  mov     [rsp+1D0h+lpOverlapped], r14; lpOverlapped
0x14002e2ff  xor     r9d, r9d; nInBufferSize
0x14002e302  mov     [rsp+1D0h+lpBytesReturned], rax; lpBytesReturned
0x14002e307  xor     r8d, r8d; lpInBuffer
0x14002e30a  lea     rax, [rbp+0D0h+OutBuffer]
0x14002e30e  mov     [rsp+1D0h+OpenOptions], 60h ; '`'; nOutBufferSize
0x14002e316  mov     edx, 90064h; dwIoControlCode
0x14002e31b  mov     qword ptr [rsp+1D0h+ShareAccess], rax; lpOutBuffer
0x14002e320  call    cs:__imp_DeviceIoControl
0x14002e326  test    eax, eax
0x14002e328  jz      short loc_14002E37F
0x14002e32a  mov     r9, [rbp+0D0h+var_50]
0x14002e331  mov     r8, [rbp+0D0h+var_48]
0x14002e338  mov     [rbp+0D0h+var_140], r9
0x14002e33c  mov     [rsp+1D0h+var_178], r8
0x14002e341  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e348  cmp     rcx, rsi
0x14002e34b  jz      short loc_14002E37F
0x14002e34d  test    [rcx+1Ch], r12b
0x14002e351  jz      short loc_14002E37F
0x14002e353  cmp     byte ptr [rcx+19h], 4
0x14002e357  jb      short loc_14002E37F
0x14002e359  mov     rcx, [rcx+10h]
0x14002e35d  lea     rax, [r15+2A0h]
0x14002e364  mov     qword ptr [rsp+1D0h+OpenOptions], rax
0x14002e369  mov     edx, 0D5h
0x14002e36e  mov     qword ptr [rsp+1D0h+ShareAccess], r8
0x14002e373  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002e37a  call    WPP_SF_iiZ
0x14002e37f  cmp     [r15+240h], r14
0x14002e386  jbe     loc_14002E7E8
0x14002e38c  lea     eax, [rdi+18h]
0x14002e38f  mov     [rsp+1D0h+OldMode], eax
0x14002e393  mov     [rsp+1D0h+lpOverlapped], 0; lpOverlapped
0x14002e39c  lea     rcx, [rsp+1D0h+BytesReturned]
0x14002e3a1  mov     [rsp+1D0h+lpBytesReturned], rcx; lpBytesReturned
0x14002e3a6  lea     r8, [rbp+0D0h+InBuffer]; lpInBuffer
0x14002e3aa  mov     rcx, [rsp+1D0h+FileHandle]; hDevice
0x14002e3af  mov     r9d, 10h; nInBufferSize
0x14002e3b5  mov     [rsp+1D0h+OpenOptions], eax; nOutBufferSize
0x14002e3b9  mov     edx, 9006Fh; dwIoControlCode
0x14002e3be  mov     qword ptr [rsp+1D0h+ShareAccess], r13; lpOutBuffer
0x14002e3c3  mov     qword ptr [rbp+0D0h+InBuffer+8], 1
0x14002e3cb  mov     qword ptr [rbp+0D0h+InBuffer], r14
0x14002e3cf  call    cs:__imp_DeviceIoControl
0x14002e3d5  test    eax, eax
0x14002e3d7  jnz     short loc_14002E3EA
0x14002e3d9  call    cs:__imp_GetLastError
0x14002e3df  cmp     eax, 80000005h
0x14002e3e4  jnz     loc_14002E78B
0x14002e3ea  mov     r9d, [rsp+1D0h+BytesReturned]
0x14002e3ef  lea     rdi, [r9-18h]
0x14002e3f3  mov     [rbp+0D0h+var_130], rdi
0x14002e3f7  mov     r10, cs:WPP_GLOBAL_Control
0x14002e3fe  cmp     r10, rsi
0x14002e401  jz      short loc_14002E43D
0x14002e403  test    [r10+1Ch], r12b
0x14002e407  jz      short loc_14002E43D
0x14002e409  cmp     byte ptr [r10+19h], 5
0x14002e40e  jb      short loc_14002E43D
0x14002e410  mov     rcx, [r10+10h]
0x14002e414  lea     rax, [r15+2A0h]
0x14002e41b  mov     qword ptr [rsp+1D0h+OpenOptions], rax
0x14002e420  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002e427  mov     edx, 0D7h
0x14002e42c  mov     qword ptr [rsp+1D0h+ShareAccess], rdi
0x14002e431  call    WPP_SF_iiZ
0x14002e436  mov     r10, cs:WPP_GLOBAL_Control
0x14002e43d  test    rdi, rdi
0x14002e440  jz      loc_14002E7E8
0x14002e446  xor     r8d, r8d
0x14002e449  lea     r13, [r14+rdi*8]
0x14002e44d  mov     [rsp+1D0h+var_190], r8d
0x14002e452  mov     [rbp+0D0h+var_138], r13
0x14002e456  cmp     r14, r13
0x14002e459  jnb     loc_14002E774
0x14002e45f  cmp     r10, rsi
0x14002e462  jz      short loc_14002E4A1
0x14002e464  test    [r10+1Ch], r12b
0x14002e468  jz      short loc_14002E4A1
0x14002e46a  cmp     byte ptr [r10+19h], 5
0x14002e46f  jb      short loc_14002E4A1
0x14002e471  mov     rcx, [r10+10h]
0x14002e475  lea     rax, [r15+2A0h]
0x14002e47c  mov     r9d, r8d
0x14002e47f  mov     edx, 0D8h
0x14002e484  mov     qword ptr [rsp+1D0h+OpenOptions], rax
0x14002e489  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002e490  mov     qword ptr [rsp+1D0h+ShareAccess], r14
0x14002e495  call    WPP_SF_iiZ
0x14002e49a  mov     r10, cs:WPP_GLOBAL_Control
0x14002e4a1  mov     r12, [r15+50h]
0x14002e4a5  mov     [rsp+1D0h+var_180], 0
0x14002e4ad  test    r12, r12
0x14002e4b0  jz      loc_14002E734
0x14002e4b6  mov     rbx, [rsp+1D0h+var_170]
0x14002e4bb  mov     rdi, [r12+10h]
0x14002e4c0  mov     r12, [r12]
0x14002e4c4  mov     [rbp+0D0h+var_120], r12
0x14002e4c8  mov     [rbp+0D0h+var_128], rdi
0x14002e4cc  cmp     r10, rsi
0x14002e4cf  jz      short loc_14002E514
0x14002e4d1  test    byte ptr [r10+1Ch], 1
0x14002e4d6  jz      short loc_14002E514
0x14002e4d8  cmp     byte ptr [r10+19h], 5
0x14002e4dd  jb      short loc_14002E514
0x14002e4df  mov     r9, [rdi+10h]
0x14002e4e3  lea     rax, [r15+2A0h]
0x14002e4ea  mov     rcx, [r10+10h]
0x14002e4ee  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002e4f5  mov     qword ptr [rsp+1D0h+OpenOptions], rax
0x14002e4fa  mov     edx, 0D9h
0x14002e4ff  mov     rax, [rdi+18h]
0x14002e503  mov     qword ptr [rsp+1D0h+ShareAccess], rax
0x14002e508  call    WPP_SF_iiZ
0x14002e50d  mov     r10, cs:WPP_GLOBAL_Control
0x14002e514  mov     rcx, [r15+240h]
0x14002e51b  mov     rax, [rdi+18h]
  ... truncated ...
```
