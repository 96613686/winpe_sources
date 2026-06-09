# CTieredVolume::GetFileSummaryByFileId(void *,TE_FILE_ID_128 const *,int *,int *,int *,unsigned __int64 *,void * *)

- ea: `0x14002dba8`
- end: `0x14002dfed`
- name: `?GetFileSummaryByFileId@CTieredVolume@@QEAAJPEAXPEBUTE_FILE_ID_128@@PEAH22PEA_KPEAPEAX@Z`
- size: `1093`
- prototype: `__int64 __fastcall(CTieredVolume *__hidden this, void *, const struct TE_FILE_ID_128 *, int *, int *, int *, unsigned __int64 *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002d844`
- `0x140030e10`

## callees

- `0x140002db0`
- `0x14002dba8`
- `0x140035bc4`
- `0x140035d68`
- `0x14003fbb0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14002dc83`
- `ntdll!NtOpenFile` at `0x14002dcbe`
- `ntdll!NtOpenFile` at `0x14002dc83`
- `ntdll!NtOpenFile` at `0x14002dcbe`
- `ntdll!RtlNtStatusToDosError` at `0x14002dd05`
- `ntdll!RtlNtStatusToDosError` at `0x14002dd16`
- `ntdll!RtlNtStatusToDosError` at `0x14002dd34`
- `ntdll!RtlNtStatusToDosError` at `0x14002dd05`
- `ntdll!RtlNtStatusToDosError` at `0x14002dd16`
- `ntdll!RtlNtStatusToDosError` at `0x14002dd34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ddac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002de14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ddac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002de14`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002de7b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002de7b`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x14002dd9b`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x14002de03`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x14002dd9b`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x14002de03`

## pseudocode

```c
__int64 __fastcall CTieredVolume::GetFileSummaryByFileId(
        CTieredVolume *this,
        void *a2,
        const struct TE_FILE_ID_128 *a3,
        int *a4,
        int *a5,
        int *a6,
        unsigned __int64 *a7,
        void **a8)
{
  unsigned int v11; // r15d
  int v12; // ebx
  int v13; // r8d
  ULONG v14; // eax
  int v15; // r8d
  _QWORD *v16; // rcx
  int v17; // edx
  DWORD v18; // eax
  DWORD LastError; // eax
  unsigned __int64 v20; // rax
  void *FileHandle; // [rsp+40h] [rbp-B1h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-A9h] BYREF
  unsigned __int64 *v24; // [rsp+50h] [rbp-A1h]
  _QWORD v25[2]; // [rsp+58h] [rbp-99h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-89h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-79h] BYREF
  __int128 v28; // [rsp+A8h] [rbp-49h] BYREF
  __int64 v29; // [rsp+B8h] [rbp-39h]
  __int128 FileInformation; // [rsp+C0h] [rbp-31h] BYREF
  __int128 v31; // [rsp+D0h] [rbp-21h]
  __int64 v32; // [rsp+E0h] [rbp-11h]

  v24 = a7;
  ObjectAttributes.RootDirectory = a2;
  *a4 = 0;
  v11 = 0;
  SystemTimeAsFileTime = (struct _FILETIME)a5;
  v32 = 0;
  v29 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v25;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 192;
  v25[0] = 1048592;
  FileHandle = (void *)-1LL;
  FileInformation = 0;
  v25[1] = a3;
  v31 = 0;
  v28 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x202060u);
  if ( (((unsigned __int64)FileHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
    || (v12 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x2021u),
        (char *)FileHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL) )
  {
    if ( v12 == -1073741772 || v12 == -1073741766 || v12 == -1073741533 )
    {
LABEL_41:
      *(_DWORD *)SystemTimeAsFileTime.dwLowDateTime = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_iiDZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          196,
          v13,
          *((_QWORD *)a3 + 1),
          *(_QWORD *)a3,
          v12,
          (__int64)this + 672);
      }
      goto LABEL_45;
    }
  }
  else
  {
    *a4 = 1;
    v12 = 0;
  }
  if ( RtlNtStatusToDosError(v12) == 87 || RtlNtStatusToDosError(v12) == 267 )
    goto LABEL_41;
  if ( v12 < 0 )
  {
    ++*((_DWORD *)this + 78);
    v14 = RtlNtStatusToDosError(v12);
    v11 = ATL::AtlHresultFromWin32(v14);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v17 = 197;
LABEL_14:
      WPP_SF_iiDZ(v16[2], v17, v15, *((_QWORD *)a3 + 1), *(_QWORD *)a3, v11, (__int64)this + 672);
      goto LABEL_45;
    }
    goto LABEL_45;
  }
  if ( GetFileInformationByHandleEx(FileHandle, FileBasicInfo, &FileInformation, 0x28u) )
  {
    if ( !GetFileInformationByHandleEx(FileHandle, FileStandardInfo, &v28, 0x18u) )
    {
      ++*((_DWORD *)this + 78);
      LastError = GetLastError();
      v11 = ATL::AtlHresultFromWin32(LastError);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v17 = 199;
        goto LABEL_14;
      }
      goto LABEL_45;
    }
    if ( (v32 & 0x200) == 0 )
    {
      if ( (v32 & 0x800) == 0
        || (SystemTimeAsFileTime = 0,
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
            (__int64)v31 <= *(_QWORD *)&SystemTimeAsFileTime - 36000000000LL) )
      {
LABEL_33:
        v20 = *((_QWORD *)&v28 + 1);
        if ( (__int64)v28 < *((__int64 *)&v28 + 1) )
        {
          if ( !*a6 )
          {
            *a6 = 1;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_iiZ(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                201,
                (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                *((_QWORD *)a3 + 1),
                *(_QWORD *)a3,
                (__int64)this + 672);
              v20 = *((_QWORD *)&v28 + 1);
            }
          }
          *v24 = v20;
        }
        else
        {
          *v24 = v28;
        }
        goto LABEL_45;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_iiZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          200,
          (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
          *((_QWORD *)a3 + 1),
          *(_QWORD *)a3,
          (__int64)this + 672);
      }
    }
    *a6 = 1;
    goto LABEL_33;
  }
  ++*((_DWORD *)this + 78);
  v18 = GetLastError();
  v11 = ATL::AtlHresultFromWin32(v18);
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v17 = 198;
    goto LABEL_14;
  }
LABEL_45:
  if ( (char *)FileHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( a8 )
      *a8 = (void *)-1LL;
  }
  else
  {
    *a8 = FileHandle;
  }
  return v11;
}

```

## disassembly

```asm
0x14002dba8  push    rbp
0x14002dbaa  push    rbx
0x14002dbab  push    rsi
0x14002dbac  push    rdi
0x14002dbad  push    r12
0x14002dbaf  push    r13
0x14002dbb1  push    r14
0x14002dbb3  push    r15
0x14002dbb5  lea     rbp, [rsp-7]
0x14002dbba  sub     rsp, 0F8h
0x14002dbc1  mov     rax, cs:__security_cookie
0x14002dbc8  xor     rax, rsp
0x14002dbcb  mov     [rbp+3Fh+var_48], rax
0x14002dbcf  mov     rax, [rbp+3Fh+arg_30]
0x14002dbd3  xorps   xmm0, xmm0
0x14002dbd6  mov     r12, [rbp+3Fh+arg_28]
0x14002dbda  mov     rdi, r9
0x14002dbdd  mov     r13, [rbp+3Fh+arg_38]
0x14002dbe4  xor     r9d, r9d
0x14002dbe7  mov     rsi, r8
0x14002dbea  mov     [rsp+130h+var_E0], rax
0x14002dbef  xor     r8d, r8d
0x14002dbf2  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rdx
0x14002dbf6  mov     [rdi], r9d
0x14002dbf9  mov     r14, rcx
0x14002dbfc  mov     rcx, [rbp+3Fh+arg_20]
0x14002dc00  mov     r15d, r9d
0x14002dc03  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x14002dc08  mov     edx, 100080h; DesiredAccess
0x14002dc0d  mov     [rbp+3Fh+var_50], r8
0x14002dc11  mov     [rbp+3Fh+var_78], r8
0x14002dc15  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x14002dc19  mov     [rcx], r9d
0x14002dc1c  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x14002dc21  mov     [r12], r9d
0x14002dc25  mov     [rax], r9
0x14002dc28  lea     rax, [rsp+130h+var_D8]
0x14002dc2d  mov     [rsp+130h+OpenOptions], 202060h; OpenOptions
0x14002dc35  lea     r9, [rsp+130h+IoStatusBlock]; IoStatusBlock
0x14002dc3a  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x14002dc3e  movups  xmmword ptr [rsp+130h+IoStatusBlock], xmm0
0x14002dc43  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x14002dc4b  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 0C0h
0x14002dc53  mov     [rsp+130h+var_D8], 100010h
0x14002dc5c  mov     [rsp+130h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x14002dc65  movups  [rbp+3Fh+FileInformation], xmm0
0x14002dc69  mov     [rsp+130h+var_D0], rsi
0x14002dc6e  movups  [rbp+3Fh+var_60], xmm0
0x14002dc72  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x14002dc7a  movups  [rbp+3Fh+var_88], xmm0
0x14002dc7e  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14002dc83  call    cs:__imp_NtOpenFile
0x14002dc89  mov     ebx, eax
0x14002dc8b  mov     rax, [rsp+130h+FileHandle]
0x14002dc90  inc     rax
0x14002dc93  test    rax, 0FFFFFFFFFFFFFFFEh
0x14002dc99  jnz     short loc_14002DCDE
0x14002dc9b  mov     [rsp+130h+OpenOptions], 2021h; OpenOptions
0x14002dca3  lea     r9, [rsp+130h+IoStatusBlock]; IoStatusBlock
0x14002dca8  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x14002dcac  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x14002dcb4  mov     edx, 100080h; DesiredAccess
0x14002dcb9  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x14002dcbe  call    cs:__imp_NtOpenFile
0x14002dcc4  mov     ebx, eax
0x14002dcc6  mov     rax, [rsp+130h+FileHandle]
0x14002dccb  dec     rax
0x14002dcce  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002dcd2  ja      short loc_14002DCDE
0x14002dcd4  mov     dword ptr [rdi], 1
0x14002dcda  xor     ebx, ebx
0x14002dcdc  jmp     short loc_14002DD03
0x14002dcde  cmp     ebx, 0C0000034h
0x14002dce4  jz      loc_14002DF54
0x14002dcea  mov     eax, ebx
0x14002dcec  cmp     ebx, 0C000003Ah
0x14002dcf2  jz      loc_14002DF54
0x14002dcf8  cmp     eax, 0C0000123h
0x14002dcfd  jz      loc_14002DF54
0x14002dd03  mov     ecx, ebx; Status
0x14002dd05  call    cs:__imp_RtlNtStatusToDosError
0x14002dd0b  cmp     eax, 57h ; 'W'
0x14002dd0e  jz      loc_14002DF54
0x14002dd14  mov     ecx, ebx; Status
0x14002dd16  call    cs:__imp_RtlNtStatusToDosError
0x14002dd1c  cmp     eax, 10Bh
0x14002dd21  jz      loc_14002DF54
0x14002dd27  test    ebx, ebx
0x14002dd29  jns     short loc_14002DD8A
0x14002dd2b  inc     dword ptr [r14+138h]
0x14002dd32  mov     ecx, ebx; Status
0x14002dd34  call    cs:__imp_RtlNtStatusToDosError
0x14002dd3a  mov     ecx, eax; unsigned int
0x14002dd3c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002dd41  mov     r15d, eax
0x14002dd44  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dd4b  lea     rdi, WPP_GLOBAL_Control
0x14002dd52  cmp     rcx, rdi
0x14002dd55  jz      loc_14002DFA8
0x14002dd5b  test    byte ptr [rcx+1Ch], 1
0x14002dd5f  jz      loc_14002DFA8
0x14002dd65  cmp     byte ptr [rcx+19h], 4
0x14002dd69  jb      loc_14002DFA8
0x14002dd6f  mov     edx, 0C5h
0x14002dd74  lea     rax, [r14+2A0h]
0x14002dd7b  mov     [rsp+130h+var_100], rax
0x14002dd80  mov     [rsp+130h+OpenOptions], r15d
0x14002dd85  jmp     loc_14002DF93
0x14002dd8a  mov     rcx, [rsp+130h+FileHandle]; hFile
0x14002dd8f  lea     r8, [rbp+3Fh+FileInformation]; lpFileInformation
0x14002dd93  mov     r9d, 28h ; '('; dwBufferSize
0x14002dd99  xor     edx, edx; FileInformationClass
0x14002dd9b  call    cs:__imp_GetFileInformationByHandleEx
0x14002dda1  test    eax, eax
0x14002dda3  jnz     short loc_14002DDEE
0x14002dda5  inc     dword ptr [r14+138h]
0x14002ddac  call    cs:__imp_GetLastError
0x14002ddb2  mov     ecx, eax; unsigned int
0x14002ddb4  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002ddb9  mov     r15d, eax
0x14002ddbc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ddc3  lea     rdi, WPP_GLOBAL_Control
0x14002ddca  cmp     rcx, rdi
0x14002ddcd  jz      loc_14002DFA8
0x14002ddd3  test    byte ptr [rcx+1Ch], 1
0x14002ddd7  jz      loc_14002DFA8
0x14002dddd  cmp     byte ptr [rcx+19h], 4
0x14002dde1  jb      loc_14002DFA8
0x14002dde7  mov     edx, 0C6h
0x14002ddec  jmp     short loc_14002DD74
0x14002ddee  mov     rcx, [rsp+130h+FileHandle]; hFile
0x14002ddf3  lea     r8, [rbp+3Fh+var_88]; lpFileInformation
0x14002ddf7  mov     r9d, 18h; dwBufferSize
0x14002ddfd  lea     ebx, [r9-17h]
0x14002de01  mov     edx, ebx; FileInformationClass
0x14002de03  call    cs:__imp_GetFileInformationByHandleEx
0x14002de09  test    eax, eax
0x14002de0b  jnz     short loc_14002DE58
0x14002de0d  add     [r14+138h], ebx
0x14002de14  call    cs:__imp_GetLastError
0x14002de1a  mov     ecx, eax; unsigned int
0x14002de1c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002de21  mov     r15d, eax
0x14002de24  mov     rcx, cs:WPP_GLOBAL_Control
0x14002de2b  lea     rdi, WPP_GLOBAL_Control
0x14002de32  cmp     rcx, rdi
0x14002de35  jz      loc_14002DFA8
0x14002de3b  test    [rcx+1Ch], bl
0x14002de3e  jz      loc_14002DFA8
0x14002de44  cmp     byte ptr [rcx+19h], 4
0x14002de48  jb      loc_14002DFA8
0x14002de4e  mov     edx, 0C7h
0x14002de53  jmp     loc_14002DD74
0x14002de58  test    dword ptr [rbp+3Fh+var_50], 200h
0x14002de5f  lea     rdi, WPP_GLOBAL_Control
0x14002de66  jnz     short loc_14002DEDA
0x14002de68  test    dword ptr [rbp+3Fh+var_50], 800h
0x14002de6f  jz      short loc_14002DEDE
0x14002de71  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14002de76  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], r15
0x14002de7b  call    cs:__imp_GetSystemTimeAsFileTime
0x14002de81  mov     rcx, 0FFFFFFF79E3B9800h
0x14002de8b  add     rcx, qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x14002de90  cmp     qword ptr [rbp+3Fh+var_60], rcx
0x14002de94  jle     short loc_14002DEDE
0x14002de96  mov     rcx, cs:WPP_GLOBAL_Control
0x14002de9d  cmp     rcx, rdi
0x14002dea0  jz      short loc_14002DEDA
0x14002dea2  test    [rcx+1Ch], bl
0x14002dea5  jz      short loc_14002DEDA
0x14002dea7  cmp     byte ptr [rcx+19h], 4
0x14002deab  jb      short loc_14002DEDA
0x14002dead  mov     r9, [rsi+8]
0x14002deb1  lea     rax, [r14+2A0h]
0x14002deb8  mov     rcx, [rcx+10h]
0x14002debc  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002dec3  mov     qword ptr [rsp+130h+OpenOptions], rax
0x14002dec8  mov     edx, 0C8h
0x14002decd  mov     rax, [rsi]
0x14002ded0  mov     qword ptr [rsp+130h+ShareAccess], rax
0x14002ded5  call    WPP_SF_iiZ
0x14002deda  mov     [r12], ebx
0x14002dede  mov     rcx, qword ptr [rbp+3Fh+var_88]
0x14002dee2  mov     rax, qword ptr [rbp+3Fh+var_88+8]
0x14002dee6  cmp     rcx, rax
0x14002dee9  jl      short loc_14002DEF8
0x14002deeb  mov     rdx, [rsp+130h+var_E0]
0x14002def0  mov     [rdx], rcx
0x14002def3  jmp     loc_14002DFA8
0x14002def8  cmp     [r12], r15d
0x14002defc  jnz     short loc_14002DF4A
0x14002defe  mov     [r12], ebx
0x14002df02  mov     rcx, cs:WPP_GLOBAL_Control
0x14002df09  cmp     rcx, rdi
0x14002df0c  jz      short loc_14002DF4A
0x14002df0e  test    [rcx+1Ch], bl
0x14002df11  jz      short loc_14002DF4A
0x14002df13  cmp     byte ptr [rcx+19h], 4
0x14002df17  jb      short loc_14002DF4A
0x14002df19  mov     r9, [rsi+8]
0x14002df1d  lea     rax, [r14+2A0h]
0x14002df24  mov     rcx, [rcx+10h]
0x14002df28  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002df2f  mov     qword ptr [rsp+130h+OpenOptions], rax
0x14002df34  mov     edx, 0C9h
0x14002df39  mov     rax, [rsi]
0x14002df3c  mov     qword ptr [rsp+130h+ShareAccess], rax
0x14002df41  call    WPP_SF_iiZ
0x14002df46  mov     rax, qword ptr [rbp+3Fh+var_88+8]
0x14002df4a  mov     rdx, [rsp+130h+var_E0]
0x14002df4f  mov     [rdx], rax
0x14002df52  jmp     short loc_14002DFA8
0x14002df54  mov     rax, qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x14002df59  mov     dword ptr [rax], 1
0x14002df5f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002df66  lea     rdi, WPP_GLOBAL_Control
0x14002df6d  cmp     rcx, rdi
0x14002df70  jz      short loc_14002DFA8
0x14002df72  test    byte ptr [rcx+1Ch], 1
0x14002df76  jz      short loc_14002DFA8
0x14002df78  cmp     byte ptr [rcx+19h], 4
0x14002df7c  jb      short loc_14002DFA8
0x14002df7e  lea     rax, [r14+2A0h]
0x14002df85  mov     edx, 0C4h
0x14002df8a  mov     [rsp+130h+var_100], rax
0x14002df8f  mov     [rsp+130h+OpenOptions], ebx
0x14002df93  mov     rax, [rsi]
0x14002df96  mov     r9, [rsi+8]
0x14002df9a  mov     rcx, [rcx+10h]
0x14002df9e  mov     qword ptr [rsp+130h+ShareAccess], rax
0x14002dfa3  call    WPP_SF_iiDZ
0x14002dfa8  mov     rcx, [rsp+130h+FileHandle]
0x14002dfad  lea     rax, [rcx-1]
0x14002dfb1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002dfb5  ja      short loc_14002DFBD
0x14002dfb7  mov     [r13+0], rcx
0x14002dfbb  jmp     short loc_14002DFCA
0x14002dfbd  test    r13, r13
0x14002dfc0  jz      short loc_14002DFCA
0x14002dfc2  mov     qword ptr [r13+0], 0FFFFFFFFFFFFFFFFh
0x14002dfca  mov     eax, r15d
0x14002dfcd  mov     rcx, [rbp+3Fh+var_48]
0x14002dfd1  xor     rcx, rsp; StackCookie
0x14002dfd4  call    __security_check_cookie
0x14002dfd9  add     rsp, 0F8h
0x14002dfe0  pop     r15
0x14002dfe2  pop     r14
0x14002dfe4  pop     r13
0x14002dfe6  pop     r12
0x14002dfe8  pop     rdi
0x14002dfe9  pop     rsi
0x14002dfea  pop     rbx
0x14002dfeb  pop     rbp
0x14002dfec  retn
```
