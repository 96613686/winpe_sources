# CTieredVolume::PopulatePinnedCacheFromQfl(TieringPinnedSession *)

- ea: `0x14002e86c`
- end: `0x14002eee8`
- name: `?PopulatePinnedCacheFromQfl@CTieredVolume@@AEAAJPEAVTieringPinnedSession@@@Z`
- size: `1660`
- prototype: `__int64 __fastcall(CTieredVolume *__hidden this, struct TieringPinnedSession *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002eef0`

## callees

- `0x14000108c`
- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x14001846c`
- `0x14001e2e0`
- `0x14002e86c`
- `0x1400357f0`
- `0x14003c75c`
- `0x14003c7a0`
- `0x14003fb82`
- `0x14003fbb0`

## import_xrefs

- `msvcrt!malloc` at `0x14002e9d7`
- `msvcrt!malloc` at `0x14002e9d7`
- `msvcrt!free` at `0x14002ed4a`
- `msvcrt!free` at `0x14002ed4a`
- `ntdll!NtOpenFile` at `0x14002e953`
- `ntdll!NtOpenFile` at `0x14002e953`
- `ntdll!NtClose` at `0x14002eead`
- `ntdll!NtClose` at `0x14002eead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ea9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ea9a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002ea90`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002ea90`

## string_xrefs

- `0x14002e8b8`: `CTieredVolume::PopulatePinnedCacheFromQfl`

## pseudocode

```c
__int64 __fastcall CTieredVolume::PopulatePinnedCacheFromQfl(CTieredVolume *this, struct TieringPinnedSession *a2)
{
  PVOID ThreadLocalStoragePointer; // rax
  char *v4; // r13
  char v5; // r15
  __int64 v6; // rbx
  NTSTATUS v7; // eax
  unsigned int v8; // r8d
  NTSTATUS v9; // edi
  unsigned int *v10; // rsi
  _QWORD *v11; // rbx
  int v12; // edi
  signed int v13; // r12d
  signed int LastError; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int64 v17; // r15
  char *v18; // r13
  __int64 i; // rax
  __int64 v20; // rsi
  enum _STORAGE_TIER_CLASS v21; // esi
  unsigned __int16 v22; // ax
  int v23; // ecx
  __int64 v24; // rcx
  __int64 v25; // r12
  TieringPinnedSession *v26; // rdx
  int v27; // ecx
  char v29; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-BCh] BYREF
  int v31; // [rsp+48h] [rbp-B8h]
  char *v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h]
  DWORD BytesReturned; // [rsp+60h] [rbp-A0h] BYREF
  void *Block; // [rsp+68h] [rbp-98h]
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  __int128 *v37; // [rsp+78h] [rbp-88h]
  __int16 v38; // [rsp+80h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  TieringPinnedSession *v40; // [rsp+90h] [rbp-70h] BYREF
  char v41[8]; // [rsp+98h] [rbp-68h] BYREF
  int updated; // [rsp+A0h] [rbp-60h]
  CTieredVolume *v43; // [rsp+A8h] [rbp-58h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-20h] BYREF
  __int128 InBuffer; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v47; // [rsp+100h] [rbp+0h]
  __int128 v48; // [rsp+110h] [rbp+10h] BYREF
  __int128 v49; // [rsp+120h] [rbp+20h] BYREF
  int v50; // [rsp+130h] [rbp+30h]
  char v51[32]; // [rsp+140h] [rbp+40h] BYREF
  _DWORD *v52; // [rsp+160h] [rbp+60h]
  __int64 v53; // [rsp+168h] [rbp+68h]
  __int64 v54; // [rsp+170h] [rbp+70h]
  _DWORD v55[2]; // [rsp+178h] [rbp+78h] BYREF
  char *v56; // [rsp+180h] [rbp+80h]
  __int64 v57; // [rsp+188h] [rbp+88h]
  __int64 *v58; // [rsp+190h] [rbp+90h]
  __int64 v59; // [rsp+198h] [rbp+98h]
  TieringPinnedSession **v60; // [rsp+1A0h] [rbp+A0h]
  __int64 v61; // [rsp+1A8h] [rbp+A8h]
  unsigned int *v62; // [rsp+1B0h] [rbp+B0h]
  __int64 v63; // [rsp+1B8h] [rbp+B8h]
  __int16 *v64; // [rsp+1C0h] [rbp+C0h]
  __int64 v65; // [rsp+1C8h] [rbp+C8h]
  __int128 *v66; // [rsp+1D0h] [rbp+D0h]
  __int64 v67; // [rsp+1D8h] [rbp+D8h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v43 = this;
  v40 = a2;
  *(_QWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 8LL) = "CTieredVolume::PopulatePinnedCacheFromQfl";
  CHResultImp::CHResultImp((CHResultImp *)v41);
  FileHandle = 0;
  BytesReturned = 0;
  v4 = (char *)this + 672;
  v36 = 0;
  v5 = 3;
  v37 = 0;
  v6 = 0;
  v33 = 0;
  v50 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  v32 = (char *)this + 672;
  IoStatusBlock = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)((char *)this + 672);
  InBuffer = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 192;
  v47 = 0;
  v49 = 0;
  v48 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 3u, 0x40u);
  v9 = v7;
  if ( v7 >= 0 )
  {
    *(_QWORD *)((char *)&InBuffer + 4) = 6565;
    LODWORD(InBuffer) = 0;
    v47 = 0u;
    Block = malloc(0xA00000u);
    v10 = (unsigned int *)Block;
    if ( Block )
    {
      v12 = updated;
      v13 = 0;
      v31 = 0;
      v30 = 0;
      while ( 1 )
      {
        if ( !DeviceIoControl(FileHandle, 0x90277u, &InBuffer, 0x20u, v10, 0xA00000u, &BytesReturned, 0) )
        {
          LastError = GetLastError();
          v13 = LastError;
          if ( LastError != 38 )
          {
            if ( LastError > 0 )
              v12 = (unsigned __int16)LastError | 0x80070000;
            else
              v12 = LastError;
            updated = v12;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              v4 = v32;
            }
            else
            {
              v4 = v32;
              if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_Zd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  193,
                  (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                  (_DWORD)v32,
                  v12);
                v11 = WPP_GLOBAL_Control;
              }
            }
            v5 = 1;
            goto LABEL_63;
          }
        }
        if ( !v6 )
          DWORD1(InBuffer) &= ~1u;
        v15 = *v10;
        v33 = v15 + v6;
        if ( !(_DWORD)v15 )
        {
          v11 = WPP_GLOBAL_Control;
LABEL_62:
          v4 = v32;
          v5 = v31;
          goto LABEL_63;
        }
        if ( BytesReturned >= 0x10uLL )
        {
          if ( v10[1] )
          {
            v16 = v10[1];
            if ( v16 + 40 <= (unsigned __int64)BytesReturned )
            {
              v17 = BytesReturned - v16;
              v18 = (char *)v10 + v16;
              if ( (unsigned int *)((char *)v10 + v16) )
                break;
            }
          }
        }
        v11 = WPP_GLOBAL_Control;
LABEL_48:
        if ( v13 )
          goto LABEL_62;
        v6 = v33;
      }
      v11 = WPP_GLOBAL_Control;
LABEL_23:
      v48 = 0;
      *(_QWORD *)&v48 = *((_QWORD *)v18 + 2);
      for ( i = GetFirstStreamLayoutEntry(v18, v17, &v36); ; i = GetNextStreamLayoutEntry(v20, &v36) )
      {
        v20 = i;
        if ( !i )
          goto LABEL_43;
        if ( *(_DWORD *)i != 1 )
          break;
        if ( *(_DWORD *)(i + 36) == 256
          && (*(_BYTE *)(i + 8) & 0x10) != 0
          && *(_DWORD *)(i + 44) == 56
          && !wcsncmp_0((const wchar_t *)(i + 48), L":$DSC:$LOGGED_UTILITY_STREAM", 0x1Cu) )
        {
          v21 = *(_DWORD *)(*(unsigned int *)(v20 + 32) + v20 + 8);
          updated = TieringPinnedSession::AddOrUpdatePinnedRecord(v40, (const struct TE_FILE_ID_128 *)&v48, v21);
          v12 = updated;
          if ( updated < 0 )
          {
            v37 = (__int128 *)((char *)v37 + 1);
            v8 = v30;
            v31 = 5;
            v22 = 0;
            if ( v30 < 5 )
            {
              while ( v22 < 5u )
              {
                v23 = *((_DWORD *)&v49 + v22);
                if ( v23 == updated )
                  break;
                if ( !v23 )
                {
                  v8 = v30 + 1;
                  *((_DWORD *)&v49 + v22) = updated;
                  v30 = v8;
                  break;
                }
                ++v22;
              }
            }
          }
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_iL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              194,
              &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
              *((_QWORD *)v18 + 2),
              v21);
            v11 = WPP_GLOBAL_Control;
          }
LABEL_43:
          if ( v17 < 0x28
            || !*((_DWORD *)v18 + 1)
            || (v24 = *((unsigned int *)v18 + 1), v24 + 40 > v17)
            || (v17 -= v24, (v18 += v24) == 0) )
          {
            v10 = (unsigned int *)Block;
            goto LABEL_48;
          }
          goto LABEL_23;
        }
      }
      v10 = (unsigned int *)Block;
      v12 = -2147024809;
      v4 = v32;
      updated = -2147024809;
      v5 = 4;
    }
    else
    {
      v12 = -2147024882;
      updated = -2147024882;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          192,
          (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
          (_DWORD)v4,
          14);
        v11 = WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    v10 = 0;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        191,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        (_DWORD)v4,
        v7);
      v11 = WPP_GLOBAL_Control;
    }
    v12 = v9 | 0x10000000;
    v5 = 2;
    updated = v12;
  }
LABEL_63:
  if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
  {
    v25 = v33;
  }
  else
  {
    v25 = v33;
    if ( *((_BYTE *)v11 + 25) >= 4u )
      WPP_SF_IZ(v11[2], 195, v8, v33, (__int64)v4);
  }
  if ( v10 )
    free(v10);
  v26 = (TieringPinnedSession *)v37;
  if ( (v12 < 0 || v37)
    && (unsigned int)dword_14004C098 > 5
    && (qword_14004C0A8 & 0x200000000000LL) != 0
    && (qword_14004C0B0 & 0x200000000000LL) == qword_14004C0B0 )
  {
    v38 = 5;
    v37 = &v49;
    v40 = v26;
    v64 = &v38;
    v30 = v12;
    v66 = &v49;
    v36 = v25;
    v62 = &v30;
    v60 = &v40;
    v58 = &v36;
    v56 = &v29;
    v52 = v55;
    v29 = v5;
    v65 = 2;
    v67 = 20;
    v63 = 4;
    v61 = 8;
    v59 = 8;
    v57 = 1;
    v53 = 2;
    v27 = *((unsigned __int16 *)v43 + 348);
    v54 = *((_QWORD *)v43 + 88);
    v55[0] = v27;
    v55[1] = 0;
    tlgWriteTransfer_EventWriteTransfer(&dword_14004C098, byte_14004654B, 0, 0, 10, v51);
  }
  if ( FileHandle )
    NtClose(FileHandle);
  CHResultImp::~CHResultImp((CHResultImp *)v41);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14002e86c  mov     [rsp-8+arg_10], rbx
0x14002e871  push    rbp
0x14002e872  push    rsi
0x14002e873  push    rdi
0x14002e874  push    r12
0x14002e876  push    r13
0x14002e878  push    r14
0x14002e87a  push    r15
0x14002e87c  lea     rbp, [rsp-0F0h]
0x14002e884  sub     rsp, 1F0h
0x14002e88b  mov     rax, cs:__security_cookie
0x14002e892  xor     rax, rsp
0x14002e895  mov     [rbp+120h+var_40], rax
0x14002e89c  mov     rax, gs:58h
0x14002e8a5  mov     rdi, rcx
0x14002e8a8  mov     [rbp+120h+var_178], rcx
0x14002e8ac  mov     ecx, 8
0x14002e8b1  mov     [rbp+120h+var_190], rdx
0x14002e8b5  mov     r8, [rax]
0x14002e8b8  lea     rax, aCtieredvolumeP_2; "CTieredVolume::PopulatePinnedCacheFromQ"...
0x14002e8bf  mov     [rcx+r8], rax
0x14002e8c3  lea     rcx, [rbp+120h+var_188]; this
0x14002e8c7  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14002e8cc  xor     r14d, r14d
0x14002e8cf  mov     [rsp+220h+OpenOptions], 40h ; '@'; OpenOptions
0x14002e8d7  xorps   xmm0, xmm0
0x14002e8da  mov     [rbp+120h+FileHandle], r14
0x14002e8de  xor     eax, eax
0x14002e8e0  mov     [rsp+220h+BytesReturned], r14d
0x14002e8e5  lea     r13, [rdi+2A0h]
0x14002e8ec  mov     [rsp+220h+var_1B0], r14
0x14002e8f1  lea     r15d, [r14+3]
0x14002e8f5  mov     [rsp+220h+var_1A8], r14
0x14002e8fa  mov     ebx, r14d
0x14002e8fd  mov     [rsp+220h+ShareAccess], r15d; ShareAccess
0x14002e902  mov     r12d, 0C0h
0x14002e908  mov     [rsp+220h+var_1C8], rbx
0x14002e90d  lea     r9, [rbp+120h+IoStatusBlock]; IoStatusBlock
0x14002e911  mov     [rbp+120h+var_F0], eax
0x14002e914  lea     r8, [rbp+120h+ObjectAttributes]; ObjectAttributes
0x14002e918  mov     qword ptr [rbp+120h+ObjectAttributes.Length], 30h ; '0'
0x14002e920  mov     edx, 80000000h; DesiredAccess
0x14002e925  mov     [rbp+120h+ObjectAttributes.RootDirectory], r14
0x14002e929  lea     rcx, [rbp+120h+FileHandle]; FileHandle
0x14002e92d  mov     [rsp+220h+var_1D0], r13
0x14002e932  movups  xmmword ptr [rbp+120h+IoStatusBlock], xmm0
0x14002e936  mov     [rbp+120h+ObjectAttributes.ObjectName], r13
0x14002e93a  movups  [rbp+120h+InBuffer], xmm0
0x14002e93e  mov     qword ptr [rbp+120h+ObjectAttributes.Attributes], r12
0x14002e942  movups  [rbp+120h+var_120], xmm0
0x14002e946  movups  [rbp+120h+var_100], xmm0
0x14002e94a  movups  [rbp+120h+var_110], xmm0
0x14002e94e  movdqu  xmmword ptr [rbp+120h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002e953  call    cs:__imp_NtOpenFile
0x14002e959  lea     ecx, [r14+2]
0x14002e95d  mov     edi, eax
0x14002e95f  test    eax, eax
0x14002e961  jns     short loc_14002E9BE
0x14002e963  mov     esi, r14d
0x14002e966  mov     rbx, cs:WPP_GLOBAL_Control
0x14002e96d  lea     rax, WPP_GLOBAL_Control
0x14002e974  lea     r14d, [rsi+1]
0x14002e978  cmp     rbx, rax
0x14002e97b  jz      short loc_14002E9AE
0x14002e97d  test    [rbx+1Ch], r14b
0x14002e981  jz      short loc_14002E9AE
0x14002e983  cmp     [rbx+19h], cl
0x14002e986  jb      short loc_14002E9AE
0x14002e988  mov     rcx, [rbx+10h]
0x14002e98c  lea     edx, [r12-1]
0x14002e991  mov     r9, r13
0x14002e994  mov     [rsp+220h+ShareAccess], edi
0x14002e998  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002e99f  call    WPP_SF_Zd
0x14002e9a4  mov     rbx, cs:WPP_GLOBAL_Control
0x14002e9ab  lea     ecx, [rsi+2]
0x14002e9ae  bts     edi, 1Ch
0x14002e9b2  movzx   r15d, cx
0x14002e9b6  mov     [rbp+120h+var_180], edi
0x14002e9b9  jmp     loc_14002ED02
0x14002e9be  mov     ecx, 0A00000h; Size
0x14002e9c3  mov     qword ptr [rbp+120h+InBuffer+4], 19A5h
0x14002e9cb  mov     dword ptr [rbp+120h+InBuffer], r14d
0x14002e9cf  mov     qword ptr [rbp+120h+var_120], r14
0x14002e9d3  mov     qword ptr [rbp+120h+var_120+8], r14
0x14002e9d7  call    cs:__imp_malloc
0x14002e9dd  mov     [rsp+220h+Block], rax
0x14002e9e2  mov     rsi, rax
0x14002e9e5  test    rax, rax
0x14002e9e8  jnz     short loc_14002EA47
0x14002e9ea  mov     edi, 8007000Eh
0x14002e9ef  mov     [rbp+120h+var_180], edi
0x14002e9f2  mov     rbx, cs:WPP_GLOBAL_Control
0x14002e9f9  lea     rax, WPP_GLOBAL_Control
0x14002ea00  lea     r14d, [rsi+1]
0x14002ea04  cmp     rbx, rax
0x14002ea07  jz      loc_14002ED02
0x14002ea0d  test    [rbx+1Ch], r14b
0x14002ea11  jz      loc_14002ED02
0x14002ea17  cmp     byte ptr [rbx+19h], 2
0x14002ea1b  jb      loc_14002ED02
0x14002ea21  mov     rcx, [rbx+10h]
0x14002ea25  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002ea2c  mov     edx, r12d
0x14002ea2f  mov     [rsp+220h+ShareAccess], edi
0x14002ea33  mov     r9, r13
0x14002ea36  call    WPP_SF_Zd
0x14002ea3b  mov     rbx, cs:WPP_GLOBAL_Control
0x14002ea42  jmp     loc_14002ED02
0x14002ea47  mov     edi, [rbp+120h+var_180]
0x14002ea4a  mov     r12d, r14d
0x14002ea4d  mov     [rsp+220h+var_1D8], r14d
0x14002ea52  mov     [rsp+220h+var_1DC], r14d
0x14002ea57  mov     r14d, 1
0x14002ea5d  mov     rcx, [rbp+120h+FileHandle]; hDevice
0x14002ea61  lea     rax, [rsp+220h+BytesReturned]
0x14002ea66  mov     [rsp+220h+lpOverlapped], 0; lpOverlapped
0x14002ea6f  lea     r8, [rbp+120h+InBuffer]; lpInBuffer
0x14002ea73  mov     [rsp+220h+lpBytesReturned], rax; lpBytesReturned
0x14002ea78  mov     r9d, 20h ; ' '; nInBufferSize
0x14002ea7e  mov     [rsp+220h+OpenOptions], 0A00000h; nOutBufferSize
0x14002ea86  mov     edx, 90277h; dwIoControlCode
0x14002ea8b  mov     qword ptr [rsp+220h+ShareAccess], rsi; lpOutBuffer
0x14002ea90  call    cs:__imp_DeviceIoControl
0x14002ea96  test    eax, eax
0x14002ea98  jnz     short loc_14002EAAC
0x14002ea9a  call    cs:__imp_GetLastError
0x14002eaa0  mov     r12d, eax
0x14002eaa3  cmp     eax, 26h ; '&'
0x14002eaa6  jnz     loc_14002EC6C
0x14002eaac  test    rbx, rbx
0x14002eaaf  jnz     short loc_14002EAB5
0x14002eab1  and     dword ptr [rbp+120h+InBuffer+4], 0FFFFFFFEh
0x14002eab5  mov     ecx, [rsi]
0x14002eab7  add     rbx, rcx
0x14002eaba  mov     [rsp+220h+var_1C8], rbx
0x14002eabf  test    ecx, ecx
0x14002eac1  jz      loc_14002ECF1
0x14002eac7  mov     r15d, [rsp+220h+BytesReturned]
0x14002eacc  cmp     r15, 10h
0x14002ead0  jb      loc_14002EC63
0x14002ead6  cmp     dword ptr [rsi+4], 0
0x14002eada  jbe     loc_14002EC63
0x14002eae0  mov     ecx, [rsi+4]
0x14002eae3  lea     rax, [rcx+28h]
0x14002eae7  cmp     rax, r15
0x14002eaea  ja      loc_14002EC63
0x14002eaf0  sub     r15, rcx
0x14002eaf3  lea     r13, [rcx+rsi]
0x14002eaf7  test    r13, r13
0x14002eafa  jz      loc_14002EC63
0x14002eb00  mov     rbx, cs:WPP_GLOBAL_Control
0x14002eb07  xorps   xmm0, xmm0
0x14002eb0a  lea     r8, [rsp+220h+var_1B0]
0x14002eb0f  movups  [rbp+120h+var_110], xmm0
0x14002eb13  mov     rax, [r13+10h]
0x14002eb17  mov     rdx, r15
0x14002eb1a  mov     rcx, r13
0x14002eb1d  mov     qword ptr [rbp+120h+var_110], rax
0x14002eb21  call    GetFirstStreamLayoutEntry
0x14002eb26  jmp     short loc_14002EB6D
0x14002eb28  cmp     [rsi], r14d
0x14002eb2b  jnz     loc_14002ECD4
0x14002eb31  cmp     dword ptr [rsi+24h], 100h
0x14002eb38  jnz     short loc_14002EB60
0x14002eb3a  test    byte ptr [rsi+8], 10h
0x14002eb3e  jz      short loc_14002EB60
0x14002eb40  cmp     dword ptr [rsi+2Ch], 38h ; '8'
0x14002eb44  jnz     short loc_14002EB60
0x14002eb46  lea     rcx, [rsi+30h]; String1
0x14002eb4a  mov     r8d, 1Ch; MaxCount
0x14002eb50  lea     rdx, aDscLoggedUtili; ":$DSC:$LOGGED_UTILITY_STREAM"
0x14002eb57  call    wcsncmp_0
0x14002eb5c  test    eax, eax
0x14002eb5e  jz      short loc_14002EB7A
0x14002eb60  lea     rdx, [rsp+220h+var_1B0]
0x14002eb65  mov     rcx, rsi
0x14002eb68  call    GetNextStreamLayoutEntry
0x14002eb6d  mov     rsi, rax
0x14002eb70  test    rax, rax
0x14002eb73  jnz     short loc_14002EB28
0x14002eb75  jmp     loc_14002EC25
0x14002eb7a  mov     eax, [rsi+20h]
0x14002eb7d  lea     rdx, [rbp+120h+var_110]; struct TE_FILE_ID_128 *
0x14002eb81  mov     rcx, [rbp+120h+var_190]; this
0x14002eb85  mov     esi, [rax+rsi+8]
0x14002eb89  mov     r8d, esi; enum _STORAGE_TIER_CLASS
0x14002eb8c  call    ?AddOrUpdatePinnedRecord@TieringPinnedSession@@QEAAJPEBUTE_FILE_ID_128@@W4_STORAGE_TIER_CLASS@@@Z; TieringPinnedSession::AddOrUpdatePinnedRecord(TE_FILE_ID_128 const *,_STORAGE_TIER_CLASS)
0x14002eb91  mov     [rbp+120h+var_180], eax
0x14002eb94  mov     edi, eax
0x14002eb96  test    eax, eax
0x14002eb98  jns     short loc_14002EBE2
0x14002eb9a  add     [rsp+220h+var_1A8], r14
0x14002eb9f  mov     ecx, 5
0x14002eba4  mov     r8d, [rsp+220h+var_1DC]
0x14002eba9  movzx   eax, cx
0x14002ebac  mov     [rsp+220h+var_1D8], eax
0x14002ebb0  xor     eax, eax
0x14002ebb2  cmp     r8d, ecx
0x14002ebb5  jnb     short loc_14002EBE2
0x14002ebb7  cmp     ax, cx
0x14002ebba  jnb     short loc_14002EBE2
0x14002ebbc  movzx   edx, ax
0x14002ebbf  mov     ecx, dword ptr [rbp+rdx*4+120h+var_100]
0x14002ebc3  cmp     ecx, edi
0x14002ebc5  jz      short loc_14002EBE2
0x14002ebc7  test    ecx, ecx
0x14002ebc9  jz      short loc_14002EBD6
0x14002ebcb  add     ax, r14w
0x14002ebcf  mov     ecx, 5
0x14002ebd4  jmp     short loc_14002EBB7
0x14002ebd6  add     r8d, r14d
0x14002ebd9  mov     dword ptr [rbp+rdx*4+120h+var_100], edi
0x14002ebdd  mov     [rsp+220h+var_1DC], r8d
0x14002ebe2  mov     rbx, cs:WPP_GLOBAL_Control
0x14002ebe9  lea     rax, WPP_GLOBAL_Control
0x14002ebf0  cmp     rbx, rax
0x14002ebf3  jz      short loc_14002EC25
0x14002ebf5  test    [rbx+1Ch], r14b
0x14002ebf9  jz      short loc_14002EC25
0x14002ebfb  cmp     byte ptr [rbx+19h], 4
0x14002ebff  jb      short loc_14002EC25
0x14002ec01  mov     r9, [r13+10h]
0x14002ec05  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002ec0c  mov     rcx, [rbx+10h]
0x14002ec10  mov     edx, 0C2h
0x14002ec15  mov     [rsp+220h+ShareAccess], esi
0x14002ec19  call    WPP_SF_iL
0x14002ec1e  mov     rbx, cs:WPP_GLOBAL_Control
0x14002ec25  cmp     r15, 28h ; '('
0x14002ec29  jb      short loc_14002EC4B
0x14002ec2b  cmp     dword ptr [r13+4], 0
0x14002ec30  jbe     short loc_14002EC4B
0x14002ec32  mov     ecx, [r13+4]
0x14002ec36  lea     rax, [rcx+28h]
0x14002ec3a  cmp     rax, r15
0x14002ec3d  ja      short loc_14002EC4B
0x14002ec3f  sub     r15, rcx
0x14002ec42  add     r13, rcx
0x14002ec45  jnz     loc_14002EB07
0x14002ec4b  mov     rsi, [rsp+220h+Block]
0x14002ec50  test    r12d, r12d
0x14002ec53  jnz     loc_14002ECF8
0x14002ec59  mov     rbx, [rsp+220h+var_1C8]
0x14002ec5e  jmp     loc_14002EA5D
0x14002ec63  mov     rbx, cs:WPP_GLOBAL_Control
0x14002ec6a  jmp     short loc_14002EC50
0x14002ec6c  test    eax, eax
0x14002ec6e  jg      short loc_14002EC74
0x14002ec70  mov     edi, eax
0x14002ec72  jmp     short loc_14002EC7D
0x14002ec74  movzx   edi, ax
0x14002ec77  or      edi, 80070000h
0x14002ec7d  mov     [rbp+120h+var_180], edi
0x14002ec80  mov     rbx, cs:WPP_GLOBAL_Control
0x14002ec87  lea     rax, WPP_GLOBAL_Control
0x14002ec8e  cmp     rbx, rax
0x14002ec91  jz      short loc_14002ECC9
0x14002ec93  test    [rbx+1Ch], r14b
0x14002ec97  jz      short loc_14002ECC9
0x14002ec99  cmp     byte ptr [rbx+19h], 2
0x14002ec9d  mov     r13, [rsp+220h+var_1D0]
0x14002eca2  jb      short loc_14002ECCE
0x14002eca4  mov     rcx, [rbx+10h]
0x14002eca8  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002ecaf  mov     edx, 0C1h
0x14002ecb4  mov     [rsp+220h+ShareAccess], edi
0x14002ecb8  mov     r9, r13
0x14002ecbb  call    WPP_SF_Zd
0x14002ecc0  mov     rbx, cs:WPP_GLOBAL_Control
0x14002ecc7  jmp     short loc_14002ECCE
0x14002ecc9  mov     r13, [rsp+220h+var_1D0]
0x14002ecce  movzx   r15d, r14w
0x14002ecd2  jmp     short loc_14002ED02
0x14002ecd4  mov     rsi, [rsp+220h+Block]
0x14002ecd9  mov     edi, 80070057h
0x14002ecde  mov     r13, [rsp+220h+var_1D0]
0x14002ece3  mov     ecx, 4
0x14002ece8  mov     [rbp+120h+var_180], edi
0x14002eceb  movzx   r15d, cx
0x14002ecef  jmp     short loc_14002ED07
0x14002ecf1  mov     rbx, cs:WPP_GLOBAL_Control
0x14002ecf8  mov     r13, [rsp+220h+var_1D0]
0x14002ecfd  mov     r15d, [rsp+220h+var_1D8]
0x14002ed02  mov     ecx, 4
0x14002ed07  lea     rax, WPP_GLOBAL_Control
0x14002ed0e  cmp     rbx, rax
0x14002ed11  jz      short loc_14002ED3B
0x14002ed13  test    [rbx+1Ch], r14b
0x14002ed17  jz      short loc_14002ED3B
0x14002ed19  mov     r12, [rsp+220h+var_1C8]
0x14002ed1e  cmp     [rbx+19h], cl
0x14002ed21  jb      short loc_14002ED40
0x14002ed23  mov     rcx, [rbx+10h]
0x14002ed27  mov     edx, 0C3h
0x14002ed2c  mov     r9, r12
0x14002ed2f  mov     qword ptr [rsp+220h+ShareAccess], r13
0x14002ed34  call    WPP_SF_IZ
0x14002ed39  jmp     short loc_14002ED40
0x14002ed3b  mov     r12, [rsp+220h+var_1C8]
  ... truncated ...
```
