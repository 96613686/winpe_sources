# CTieredVolume::ValidateFileId(TE_FILE_ID_128 *)

- ea: `0x14001742c`
- end: `0x140017701`
- name: `?ValidateFileId@CTieredVolume@@QEAAJPEAUTE_FILE_ID_128@@@Z`
- size: `725`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct TE_FILE_ID_128 *)`
- caller_count: `4`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000c444`
- `0x1400108e0`
- `0x1400122fc`
- `0x14003cfb4`

## callees

- `0x140002db0`
- `0x140004aa8`
- `0x14000b7f8`
- `0x14001742c`
- `0x1400185a0`
- `0x14002d844`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14001755b`
- `ntdll!NtOpenFile` at `0x14001755b`
- `ntdll!RtlGetThreadErrorMode` at `0x140017451`
- `ntdll!RtlGetThreadErrorMode` at `0x140017451`
- `ntdll!RtlSetThreadErrorMode` at `0x140017460`
- `ntdll!RtlSetThreadErrorMode` at `0x140017506`
- `ntdll!RtlSetThreadErrorMode` at `0x1400176e2`
- `ntdll!RtlSetThreadErrorMode` at `0x140017460`
- `ntdll!RtlSetThreadErrorMode` at `0x140017506`
- `ntdll!RtlSetThreadErrorMode` at `0x1400176e2`
- `ntdll!NtClose` at `0x1400174f5`
- `ntdll!NtClose` at `0x1400176d1`
- `ntdll!NtClose` at `0x1400174f5`
- `ntdll!NtClose` at `0x1400176d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400174e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400175c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400174e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400175c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001748b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001748b`

## pseudocode

```c
__int64 __fastcall CTieredVolume::ValidateFileId(RTL_SRWLOCK *this, struct TE_FILE_ID_128 *a2)
{
  ULONG ThreadErrorMode; // eax
  NTSTATUS v5; // eax
  char v6; // r8
  unsigned int v7; // edi
  NTSTATUS v9; // eax
  int FileExtentsByFileId; // ebx
  _QWORD *v11; // rcx
  int v12; // edx
  void **v13; // [rsp+58h] [rbp-41h]
  ULONG OldMode; // [rsp+60h] [rbp-39h] BYREF
  char v15; // [rsp+64h] [rbp-35h]
  HANDLE Handle; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int64 v17; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int64 v18; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int64 v19; // [rsp+80h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-11h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp+1Fh] BYREF
  int v22; // [rsp+100h] [rbp+67h] BYREF
  int v23; // [rsp+110h] [rbp+77h] BYREF
  int v24; // [rsp+118h] [rbp+7Fh] BYREF

  v15 = 0;
  ThreadErrorMode = RtlGetThreadErrorMode();
  v5 = RtlSetThreadErrorMode(ThreadErrorMode | 0x10, &OldMode);
  v6 = v15;
  Handle = 0;
  if ( v5 >= 0 )
    v6 = 1;
  v15 = v6;
  IoStatusBlock = 0;
  AcquireSRWLockShared(this + 3);
  if ( !BYTE1(this[90].Ptr) )
  {
    v7 = -2138898430;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        236,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        LODWORD(this[16].Ptr),
        -2138898430);
    }
LABEL_8:
    if ( this != (RTL_SRWLOCK *)-24LL )
      ReleaseSRWLockShared(this + 3);
    if ( Handle )
      NtClose(Handle);
    if ( v15 )
      RtlSetThreadErrorMode(OldMode, 0);
    return v7;
  }
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&this[18];
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 192;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = NtOpenFile(&Handle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x21u);
  if ( v9 < 0 )
  {
    v7 = v9 | 0x10000000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        237,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        (_DWORD)this + 672,
        v9);
    }
    goto LABEL_8;
  }
  if ( this != (RTL_SRWLOCK *)-24LL )
    ReleaseSRWLockShared(this + 3);
  v19 = 0;
  v17 = 0;
  v18 = 0;
  v23 = 0;
  v22 = 0;
  v24 = 0;
  FileExtentsByFileId = CTieredVolume::GetFileExtentsByFileId(
                          (CTieredVolume *)this,
                          Handle,
                          a2,
                          &v23,
                          &v22,
                          &v24,
                          &v19,
                          &v18,
                          &v17,
                          0,
                          0,
                          v13);
  if ( v22 )
    FileExtentsByFileId = ATL::AtlHresultFromWin32(2);
  if ( FileExtentsByFileId >= 0 )
  {
    if ( !v23 )
      goto LABEL_35;
    FileExtentsByFileId = -2138898425;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_35;
    }
    v12 = 239;
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_35;
    }
    v12 = 238;
  }
  WPP_SF_iiZd(
    v11[2],
    v12,
    (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
    *((_QWORD *)a2 + 1),
    *(_QWORD *)a2,
    (__int64)&this[84],
    FileExtentsByFileId);
LABEL_35:
  if ( Handle )
    NtClose(Handle);
  if ( v15 )
    RtlSetThreadErrorMode(OldMode, 0);
  return (unsigned int)FileExtentsByFileId;
}

```

## disassembly

```asm
0x14001742c  mov     [rsp-8+arg_8], rbx
0x140017431  push    rbp
0x140017432  push    rsi
0x140017433  push    rdi
0x140017434  push    r14
0x140017436  push    r15
0x140017438  lea     rbp, [rsp-37h]
0x14001743d  sub     rsp, 0D0h
0x140017444  xor     r14d, r14d
0x140017447  mov     rdi, rdx
0x14001744a  mov     [rbp+57h+var_8C], r14b
0x14001744e  mov     rsi, rcx
0x140017451  call    cs:__imp_RtlGetThreadErrorMode
0x140017457  or      eax, 10h
0x14001745a  lea     rdx, [rbp+57h+OldMode]; OldMode
0x14001745e  mov     ecx, eax; NewMode
0x140017460  call    cs:__imp_RtlSetThreadErrorMode
0x140017466  movzx   r8d, [rbp+57h+var_8C]
0x14001746b  lea     r15d, [r14+1]
0x14001746f  test    eax, eax
0x140017471  mov     [rbp+57h+Handle], r14
0x140017475  xorps   xmm0, xmm0
0x140017478  lea     rbx, [rsi+18h]
0x14001747c  cmovns  r8d, r15d
0x140017480  mov     rcx, rbx; SRWLock
0x140017483  mov     [rbp+57h+var_8C], r8b
0x140017487  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14001748b  call    cs:__imp_AcquireSRWLockShared
0x140017491  cmp     [rsi+2D1h], r14b
0x140017498  jnz     short loc_140017513
0x14001749a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400174a1  lea     rax, WPP_GLOBAL_Control
0x1400174a8  mov     edi, 80830002h
0x1400174ad  cmp     rcx, rax
0x1400174b0  jz      short loc_1400174DE
0x1400174b2  test    [rcx+1Ch], r15b
0x1400174b6  jz      short loc_1400174DE
0x1400174b8  cmp     byte ptr [rcx+19h], 2
0x1400174bc  jb      short loc_1400174DE
0x1400174be  mov     r9d, [rsi+80h]
0x1400174c5  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x1400174cc  mov     rcx, [rcx+10h]
0x1400174d0  mov     edx, 0ECh
0x1400174d5  mov     [rsp+0F0h+ShareAccess], edi
0x1400174d9  call    WPP_SF_Dd
0x1400174de  test    rbx, rbx
0x1400174e1  jz      short loc_1400174EC
0x1400174e3  mov     rcx, rbx; SRWLock
0x1400174e6  call    cs:__imp_ReleaseSRWLockShared
0x1400174ec  mov     rcx, [rbp+57h+Handle]; Handle
0x1400174f0  test    rcx, rcx
0x1400174f3  jz      short loc_1400174FB
0x1400174f5  call    cs:__imp_NtClose
0x1400174fb  cmp     [rbp+57h+var_8C], r14b
0x1400174ff  jz      short loc_14001750C
0x140017501  mov     ecx, [rbp+57h+OldMode]; NewMode
0x140017504  xor     edx, edx; OldMode
0x140017506  call    cs:__imp_RtlSetThreadErrorMode
0x14001750c  mov     eax, edi
0x14001750e  jmp     loc_1400176EA
0x140017513  lea     rax, [rsi+90h]
0x14001751a  mov     [rsp+0F0h+OpenOptions], 21h ; '!'; OpenOptions
0x140017522  xorps   xmm0, xmm0
0x140017525  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140017529  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14001752d  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140017535  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140017539  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14001753d  mov     edx, 100080h; DesiredAccess
0x140017542  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 0C0h
0x14001754a  lea     rcx, [rbp+57h+Handle]; FileHandle
0x14001754e  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x140017556  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001755b  call    cs:__imp_NtOpenFile
0x140017561  mov     r8d, eax
0x140017564  test    eax, eax
0x140017566  jns     short loc_1400175BF
0x140017568  mov     edi, eax
0x14001756a  bts     edi, 1Ch
0x14001756e  mov     rcx, cs:WPP_GLOBAL_Control
0x140017575  lea     rax, WPP_GLOBAL_Control
0x14001757c  cmp     rcx, rax
0x14001757f  jz      loc_1400174DE
0x140017585  test    [rcx+1Ch], r15b
0x140017589  jz      loc_1400174DE
0x14001758f  cmp     byte ptr [rcx+19h], 2
0x140017593  jb      loc_1400174DE
0x140017599  mov     rcx, [rcx+10h]
0x14001759d  lea     r9, [rsi+2A0h]
0x1400175a4  mov     [rsp+0F0h+ShareAccess], r8d
0x1400175a9  mov     edx, 0EDh
0x1400175ae  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x1400175b5  call    WPP_SF_Zd
0x1400175ba  jmp     loc_1400174DE
0x1400175bf  test    rbx, rbx
0x1400175c2  jz      short loc_1400175CD
0x1400175c4  mov     rcx, rbx; SRWLock
0x1400175c7  call    cs:__imp_ReleaseSRWLockShared
0x1400175cd  mov     rdx, [rbp+57h+Handle]; void *
0x1400175d1  lea     rax, [rbp+57h+var_80]
0x1400175d5  mov     [rsp+0F0h+var_A0], r14; struct _FILE_PLACEMENT **
0x1400175da  lea     r9, [rbp+57h+arg_10]; int *
0x1400175de  mov     [rsp+0F0h+var_A8], r14; unsigned int *
0x1400175e3  mov     r8, rdi; struct TE_FILE_ID_128 *
0x1400175e6  mov     [rsp+0F0h+var_B0], rax; unsigned __int64 *
0x1400175eb  mov     rcx, rsi; this
0x1400175ee  lea     rax, [rbp+57h+var_78]
0x1400175f2  mov     [rbp+57h+var_70], r14
0x1400175f6  mov     [rsp+0F0h+var_B8], rax; unsigned __int64 *
0x1400175fb  lea     rax, [rbp+57h+var_70]
0x1400175ff  mov     [rsp+0F0h+var_C0], rax; unsigned __int64 *
0x140017604  lea     rax, [rbp+57h+arg_18]
0x140017608  mov     qword ptr [rsp+0F0h+OpenOptions], rax; int *
0x14001760d  lea     rax, [rbp+57h+arg_0]
0x140017611  mov     qword ptr [rsp+0F0h+ShareAccess], rax; int *
0x140017616  mov     [rbp+57h+var_80], r14
0x14001761a  mov     [rbp+57h+var_78], r14
0x14001761e  mov     [rbp+57h+arg_10], r14d
0x140017622  mov     [rbp+57h+arg_0], r14d
0x140017626  mov     [rbp+57h+arg_18], r14d
0x14001762a  call    ?GetFileExtentsByFileId@CTieredVolume@@QEAAJPEAXPEBUTE_FILE_ID_128@@PEAH22PEA_K33PEAKPEAPEAU_FILE_PLACEMENT@@PEAPEAX@Z; CTieredVolume::GetFileExtentsByFileId(void *,TE_FILE_ID_128 const *,int *,int *,int *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,ulong *,_FILE_PLACEMENT * *,void * *)
0x14001762f  mov     ebx, eax
0x140017631  cmp     [rbp+57h+arg_0], r14d
0x140017635  jz      short loc_140017643
0x140017637  mov     ecx, 2; unsigned int
0x14001763c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140017641  mov     ebx, eax
0x140017643  test    ebx, ebx
0x140017645  jns     short loc_14001766D
0x140017647  mov     rcx, cs:WPP_GLOBAL_Control
0x14001764e  lea     rax, WPP_GLOBAL_Control
0x140017655  cmp     rcx, rax
0x140017658  jz      short loc_1400176C8
0x14001765a  test    [rcx+1Ch], r15b
0x14001765e  jz      short loc_1400176C8
0x140017660  cmp     byte ptr [rcx+19h], 2
0x140017664  jb      short loc_1400176C8
0x140017666  mov     edx, 0EEh
0x14001766b  jmp     short loc_14001769C
0x14001766d  cmp     [rbp+57h+arg_10], r14d
0x140017671  jz      short loc_1400176C8
0x140017673  mov     ebx, 80830007h
0x140017678  mov     rcx, cs:WPP_GLOBAL_Control
0x14001767f  lea     rax, WPP_GLOBAL_Control
0x140017686  cmp     rcx, rax
0x140017689  jz      short loc_1400176C8
0x14001768b  test    [rcx+1Ch], r15b
0x14001768f  jz      short loc_1400176C8
0x140017691  cmp     byte ptr [rcx+19h], 2
0x140017695  jb      short loc_1400176C8
0x140017697  mov     edx, 0EFh
0x14001769c  mov     r9, [rdi+8]
0x1400176a0  lea     rax, [rsi+2A0h]
0x1400176a7  mov     rcx, [rcx+10h]
0x1400176ab  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x1400176b2  mov     dword ptr [rsp+0F0h+var_C0], ebx
0x1400176b6  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x1400176bb  mov     rax, [rdi]
0x1400176be  mov     qword ptr [rsp+0F0h+ShareAccess], rax
0x1400176c3  call    WPP_SF_iiZd
0x1400176c8  mov     rcx, [rbp+57h+Handle]; Handle
0x1400176cc  test    rcx, rcx
0x1400176cf  jz      short loc_1400176D7
0x1400176d1  call    cs:__imp_NtClose
0x1400176d7  cmp     [rbp+57h+var_8C], r14b
0x1400176db  jz      short loc_1400176E8
0x1400176dd  mov     ecx, [rbp+57h+OldMode]; NewMode
0x1400176e0  xor     edx, edx; OldMode
0x1400176e2  call    cs:__imp_RtlSetThreadErrorMode
0x1400176e8  mov     eax, ebx
0x1400176ea  mov     rbx, [rsp+0F0h+arg_8]
0x1400176f2  add     rsp, 0D0h
0x1400176f9  pop     r15
0x1400176fb  pop     r14
0x1400176fd  pop     rdi
0x1400176fe  pop     rsi
0x1400176ff  pop     rbp
0x140017700  retn
```
