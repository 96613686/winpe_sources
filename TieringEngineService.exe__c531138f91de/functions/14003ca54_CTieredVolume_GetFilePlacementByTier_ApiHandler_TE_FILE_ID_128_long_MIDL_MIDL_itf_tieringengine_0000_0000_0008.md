# CTieredVolume::GetFilePlacementByTier_ApiHandler(TE_FILE_ID_128 *,long *,__MIDL___MIDL_itf_tieringengine_0000_0000_0008 * *)

- ea: `0x14003ca54`
- end: `0x14003cdd8`
- name: `?GetFilePlacementByTier_ApiHandler@CTieredVolume@@QEAAJPEAUTE_FILE_ID_128@@PEAJPEAPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0008@@@Z`
- size: `900`
- prototype: `__int64 __fastcall(CTieredVolume *this, struct TE_FILE_ID_128 *, int *, struct _GUID **)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140038630`
- `0x14003cde0`

## callees

- `0x140002db0`
- `0x140004aa8`
- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x14000ccc0`
- `0x14000f728`
- `0x1400127dc`
- `0x1400185a0`
- `0x14002d844`
- `0x14003ca54`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14003cb84`
- `ntdll!NtOpenFile` at `0x14003cb84`
- `ntdll!RtlGetThreadErrorMode` at `0x14003cb0c`
- `ntdll!RtlGetThreadErrorMode` at `0x14003cb0c`
- `ntdll!RtlSetThreadErrorMode` at `0x14003cb1b`
- `ntdll!RtlSetThreadErrorMode` at `0x14003cdb2`
- `ntdll!RtlSetThreadErrorMode` at `0x14003cb1b`
- `ntdll!RtlSetThreadErrorMode` at `0x14003cdb2`
- `ntdll!NtClose` at `0x14003cda1`
- `ntdll!NtClose` at `0x14003cda1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003ccca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003ccca`

## pseudocode

```c
__int64 __fastcall CTieredVolume::GetFilePlacementByTier_ApiHandler(
        CTieredVolume *this,
        struct TE_FILE_ID_128 *a2,
        int *a3,
        struct _GUID **a4)
{
  int FileExtentsByFileId; // edi
  ULONG ThreadErrorMode; // eax
  NTSTATUS v10; // eax
  char v11; // cl
  NTSTATUS v12; // eax
  int v13; // edx
  struct __MIDL___MIDL_itf_tieringengine_0000_0000_0008 *v14; // rax
  struct _GUID *v15; // rbx
  void **v17; // [rsp+58h] [rbp-81h]
  int v18; // [rsp+60h] [rbp-79h] BYREF
  ULONG OldMode; // [rsp+68h] [rbp-71h] BYREF
  char v20; // [rsp+6Ch] [rbp-6Dh]
  int v21; // [rsp+70h] [rbp-69h] BYREF
  int v22; // [rsp+74h] [rbp-65h] BYREF
  void *FileHandle; // [rsp+78h] [rbp-61h] BYREF
  _BYTE v24[8]; // [rsp+80h] [rbp-59h] BYREF
  int v25; // [rsp+88h] [rbp-51h]
  unsigned __int64 v26; // [rsp+90h] [rbp-49h] BYREF
  unsigned __int64 v27; // [rsp+98h] [rbp-41h] BYREF
  unsigned __int64 v28; // [rsp+A0h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-1h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::GetFilePlacementByTier_ApiHandler";
  CHResultImp::CHResultImp((CHResultImp *)v24);
  FileExtentsByFileId = CTieredVolume::ReferenceVolume(this, 0);
  v25 = FileExtentsByFileId;
  if ( FileExtentsByFileId >= 0 )
  {
    v20 = 0;
    ThreadErrorMode = RtlGetThreadErrorMode();
    v10 = RtlSetThreadErrorMode(ThreadErrorMode | 0x10, &OldMode);
    v11 = v20;
    if ( v10 >= 0 )
      v11 = 1;
    v20 = v11;
    IoStatusBlock = 0;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)((char *)this + 144);
    *(_QWORD *)&ObjectAttributes.Attributes = 192;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    FileHandle = 0;
    v12 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x21u);
    if ( v12 >= 0 )
    {
      v26 = 0;
      v28 = 0;
      v27 = 0;
      v21 = 0;
      v22 = 0;
      v18 = 0;
      FileExtentsByFileId = CTieredVolume::GetFileExtentsByFileId(
                              this,
                              FileHandle,
                              a2,
                              &v22,
                              &v18,
                              &v21,
                              &v26,
                              &v27,
                              &v28,
                              0,
                              0,
                              v17);
      v25 = FileExtentsByFileId;
      v13 = v18;
      if ( v18 )
      {
        FileExtentsByFileId = ATL::AtlHresultFromWin32(2);
        v25 = FileExtentsByFileId;
      }
      if ( FileExtentsByFileId >= 0 )
      {
        if ( v26 && !v13 )
        {
          v14 = (struct __MIDL___MIDL_itf_tieringengine_0000_0000_0008 *)CoTaskMemAlloc(0x30u);
          *a4 = (struct _GUID *)v14;
          if ( v14 )
          {
            *(_OWORD *)v14 = 0;
            *((_OWORD *)v14 + 1) = 0;
            *((_OWORD *)v14 + 2) = 0;
            *a3 = 2;
            v15 = *a4;
            CTieredVolume::GetTierInfo(this, StorageTierClassPerformance, *a4, 0);
            *(_QWORD *)&v15[1].Data1 = v27 / *((unsigned int *)this + 79);
            CTieredVolume::GetTierInfo(this, StorageTierClassCapacity, (struct _GUID *)((char *)v15 + 24), 0);
            *(_QWORD *)v15[2].Data4 = v28 / *((unsigned int *)this + 79);
          }
          else
          {
            FileExtentsByFileId = -2147024882;
            v25 = -2147024882;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Zd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                84,
                (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
                (_DWORD)this + 672,
                14);
            }
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_iiZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
          *((_QWORD *)a2 + 1),
          *(_QWORD *)a2,
          (__int64)this + 672,
          FileExtentsByFileId);
      }
    }
    else
    {
      FileExtentsByFileId = v12 | 0x10000000;
      v25 = v12 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_iiZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          82,
          (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
          *((_QWORD *)a2 + 1),
          *(_QWORD *)a2,
          (__int64)this + 672,
          v12);
      }
    }
    CTieredVolume::DereferenceVolume((RTL_SRWLOCK *)this);
    if ( FileHandle )
      NtClose(FileHandle);
    if ( v20 )
      RtlSetThreadErrorMode(OldMode, 0);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      81,
      &WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
      *((unsigned int *)this + 32),
      FileExtentsByFileId);
  }
  CHResultImp::~CHResultImp((CHResultImp *)v24);
  return (unsigned int)FileExtentsByFileId;
}

```

## disassembly

```asm
0x14003ca54  push    rbp
0x14003ca56  push    rbx
0x14003ca57  push    rsi
0x14003ca58  push    rdi
0x14003ca59  push    r12
0x14003ca5b  push    r13
0x14003ca5d  push    r14
0x14003ca5f  push    r15
0x14003ca61  lea     rbp, [rsp-1Fh]
0x14003ca66  sub     rsp, 0F8h
0x14003ca6d  mov     r15, r9
0x14003ca70  mov     r12, r8
0x14003ca73  mov     rbx, rdx
0x14003ca76  mov     rsi, rcx
0x14003ca79  mov     ecx, 8
0x14003ca7e  mov     rax, gs:58h
0x14003ca87  mov     r10, [rax]
0x14003ca8a  lea     rax, aCtieredvolumeG_4; "CTieredVolume::GetFilePlacementByTier_A"...
0x14003ca91  mov     [rcx+r10], rax
0x14003ca95  lea     rcx, [rbp+57h+var_B0]; this
0x14003ca99  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14003ca9e  nop
0x14003ca9f  xor     edx, edx; bool
0x14003caa1  mov     rcx, rsi; this
0x14003caa4  call    ?ReferenceVolume@CTieredVolume@@QEAAJ_N@Z; CTieredVolume::ReferenceVolume(bool)
0x14003caa9  mov     edi, eax
0x14003caab  mov     [rbp+57h+var_A8], eax
0x14003caae  xor     r13d, r13d
0x14003cab1  test    eax, eax
0x14003cab3  jns     short loc_14003CB08
0x14003cab5  lea     rax, WPP_GLOBAL_Control
0x14003cabc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cac3  cmp     rcx, rax
0x14003cac6  jz      loc_14003CDB9
0x14003cacc  lea     r14d, [r13+1]
0x14003cad0  test    [rcx+1Ch], r14b
0x14003cad4  jz      loc_14003CDB9
0x14003cada  cmp     byte ptr [rcx+19h], 2
0x14003cade  jb      loc_14003CDB9
0x14003cae4  lea     edx, [r13+51h]
0x14003cae8  mov     [rsp+130h+ShareAccess], edi
0x14003caec  mov     r9d, [rsi+80h]
0x14003caf3  lea     r8, WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids
0x14003cafa  mov     rcx, [rcx+10h]
0x14003cafe  call    WPP_SF_Dd
0x14003cb03  jmp     loc_14003CDB9
0x14003cb08  mov     [rbp+57h+var_C4], r13b
0x14003cb0c  call    cs:__imp_RtlGetThreadErrorMode
0x14003cb12  or      eax, 10h
0x14003cb15  lea     rdx, [rbp+57h+OldMode]; OldMode
0x14003cb19  mov     ecx, eax; NewMode
0x14003cb1b  call    cs:__imp_RtlSetThreadErrorMode
0x14003cb21  movzx   ecx, [rbp+57h+var_C4]
0x14003cb25  mov     r14d, 1
0x14003cb2b  test    eax, eax
0x14003cb2d  cmovns  ecx, r14d
0x14003cb31  mov     [rbp+57h+var_C4], cl
0x14003cb34  xorps   xmm0, xmm0
0x14003cb37  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14003cb3b  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14003cb43  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x14003cb47  lea     rax, [rsi+90h]
0x14003cb4e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14003cb52  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 0C0h
0x14003cb5a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003cb5f  mov     [rbp+57h+FileHandle], r13
0x14003cb63  mov     [rsp+130h+OpenOptions], 21h ; '!'; OpenOptions
0x14003cb6b  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x14003cb73  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14003cb77  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14003cb7b  mov     edx, 100080h; DesiredAccess
0x14003cb80  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14003cb84  call    cs:__imp_NtOpenFile
0x14003cb8a  mov     r8d, eax
0x14003cb8d  test    eax, eax
0x14003cb8f  jns     short loc_14003CBFB
0x14003cb91  mov     edi, eax
0x14003cb93  bts     edi, 1Ch
0x14003cb97  mov     [rbp+57h+var_A8], edi
0x14003cb9a  lea     rax, WPP_GLOBAL_Control
0x14003cba1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cba8  cmp     rcx, rax
0x14003cbab  jz      loc_14003CD90
0x14003cbb1  test    [rcx+1Ch], r14b
0x14003cbb5  jz      loc_14003CD90
0x14003cbbb  cmp     byte ptr [rcx+19h], 2
0x14003cbbf  jb      loc_14003CD90
0x14003cbc5  lea     edx, [r14+51h]
0x14003cbc9  mov     dword ptr [rsp+130h+var_100], r8d
0x14003cbce  lea     rax, [rsi+2A0h]
0x14003cbd5  mov     qword ptr [rsp+130h+OpenOptions], rax
0x14003cbda  mov     rax, [rbx]
0x14003cbdd  mov     qword ptr [rsp+130h+ShareAccess], rax
0x14003cbe2  mov     r9, [rbx+8]
0x14003cbe6  lea     r8, WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids
0x14003cbed  mov     rcx, [rcx+10h]
0x14003cbf1  call    WPP_SF_iiZd
0x14003cbf6  jmp     loc_14003CD90
0x14003cbfb  mov     [rbp+57h+var_A0], r13
0x14003cbff  mov     [rbp+57h+var_90], r13
0x14003cc03  mov     [rbp+57h+var_98], r13
0x14003cc07  mov     [rbp+57h+var_C0], r13d
0x14003cc0b  mov     [rbp+57h+var_BC], r13d
0x14003cc0f  mov     [rbp+57h+var_D0], r13d
0x14003cc13  mov     [rsp+130h+var_E0], r13; struct _FILE_PLACEMENT **
0x14003cc18  mov     [rsp+130h+var_E8], r13; unsigned int *
0x14003cc1d  lea     rax, [rbp+57h+var_90]
0x14003cc21  mov     [rsp+130h+var_F0], rax; unsigned __int64 *
0x14003cc26  lea     rax, [rbp+57h+var_98]
0x14003cc2a  mov     [rsp+130h+var_F8], rax; unsigned __int64 *
0x14003cc2f  lea     rax, [rbp+57h+var_A0]
0x14003cc33  mov     [rsp+130h+var_100], rax; unsigned __int64 *
0x14003cc38  lea     rax, [rbp+57h+var_C0]
0x14003cc3c  mov     qword ptr [rsp+130h+OpenOptions], rax; int *
0x14003cc41  lea     rax, [rbp+57h+var_D0]
0x14003cc45  mov     qword ptr [rsp+130h+ShareAccess], rax; int *
0x14003cc4a  lea     r9, [rbp+57h+var_BC]; int *
0x14003cc4e  mov     r8, rbx; struct TE_FILE_ID_128 *
0x14003cc51  mov     rdx, [rbp+57h+FileHandle]; void *
0x14003cc55  mov     rcx, rsi; this
0x14003cc58  call    ?GetFileExtentsByFileId@CTieredVolume@@QEAAJPEAXPEBUTE_FILE_ID_128@@PEAH22PEA_K33PEAKPEAPEAU_FILE_PLACEMENT@@PEAPEAX@Z; CTieredVolume::GetFileExtentsByFileId(void *,TE_FILE_ID_128 const *,int *,int *,int *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,ulong *,_FILE_PLACEMENT * *,void * *)
0x14003cc5d  mov     edi, eax
0x14003cc5f  mov     [rbp+57h+var_A8], eax
0x14003cc62  mov     edx, [rbp+57h+var_D0]
0x14003cc65  test    edx, edx
0x14003cc67  jz      short loc_14003CC78
0x14003cc69  mov     ecx, 2; unsigned int
0x14003cc6e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14003cc73  mov     edi, eax
0x14003cc75  mov     [rbp+57h+var_A8], eax
0x14003cc78  test    edi, edi
0x14003cc7a  jns     short loc_14003CCB5
0x14003cc7c  lea     rax, WPP_GLOBAL_Control
0x14003cc83  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cc8a  cmp     rcx, rax
0x14003cc8d  jz      loc_14003CD90
0x14003cc93  test    [rcx+1Ch], r14b
0x14003cc97  jz      loc_14003CD90
0x14003cc9d  cmp     byte ptr [rcx+19h], 2
0x14003cca1  jb      loc_14003CD90
0x14003cca7  mov     edx, 53h ; 'S'
0x14003ccac  mov     dword ptr [rsp+130h+var_100], edi
0x14003ccb0  jmp     loc_14003CBCE
0x14003ccb5  cmp     [rbp+57h+var_A0], r13
0x14003ccb9  jbe     loc_14003CD90
0x14003ccbf  test    edx, edx
0x14003ccc1  jnz     loc_14003CD90
0x14003ccc7  lea     ecx, [rdx+30h]; cb
0x14003ccca  call    cs:__imp_CoTaskMemAlloc
0x14003ccd0  mov     [r15], rax
0x14003ccd3  test    rax, rax
0x14003ccd6  jnz     short loc_14003CD2D
0x14003ccd8  mov     edi, 8007000Eh
0x14003ccdd  mov     [rbp+57h+var_A8], edi
0x14003cce0  lea     rax, WPP_GLOBAL_Control
0x14003cce7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ccee  cmp     rcx, rax
0x14003ccf1  jz      loc_14003CD90
0x14003ccf7  test    [rcx+1Ch], r14b
0x14003ccfb  jz      loc_14003CD90
0x14003cd01  cmp     byte ptr [rcx+19h], 2
0x14003cd05  jb      loc_14003CD90
0x14003cd0b  lea     r9, [rsi+2A0h]
0x14003cd12  mov     edx, 54h ; 'T'
0x14003cd17  mov     [rsp+130h+ShareAccess], edi
0x14003cd1b  lea     r8, WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids
0x14003cd22  mov     rcx, [rcx+10h]
0x14003cd26  call    WPP_SF_Zd
0x14003cd2b  jmp     short loc_14003CD90
0x14003cd2d  xorps   xmm0, xmm0
0x14003cd30  movups  xmmword ptr [rax], xmm0
0x14003cd33  movups  xmmword ptr [rax+10h], xmm0
0x14003cd37  movups  xmmword ptr [rax+20h], xmm0
0x14003cd3b  mov     dword ptr [r12], 2
0x14003cd43  mov     rbx, [r15]
0x14003cd46  xor     r9d, r9d; unsigned __int16 *
0x14003cd49  mov     r8, rbx; struct _GUID *
0x14003cd4c  lea     edx, [r9+2]; enum _STORAGE_TIER_CLASS
0x14003cd50  mov     rcx, rsi; this
0x14003cd53  call    ?GetTierInfo@CTieredVolume@@QEAAJW4_STORAGE_TIER_CLASS@@PEAU_GUID@@PEAG@Z; CTieredVolume::GetTierInfo(_STORAGE_TIER_CLASS,_GUID *,ushort *)
0x14003cd58  mov     ecx, [rsi+13Ch]
0x14003cd5e  xor     edx, edx
0x14003cd60  mov     rax, [rbp+57h+var_98]
0x14003cd64  div     rcx
0x14003cd67  mov     [rbx+10h], rax
0x14003cd6b  xor     r9d, r9d; unsigned __int16 *
0x14003cd6e  lea     r8, [rbx+18h]; struct _GUID *
0x14003cd72  mov     edx, r14d; enum _STORAGE_TIER_CLASS
0x14003cd75  mov     rcx, rsi; this
0x14003cd78  call    ?GetTierInfo@CTieredVolume@@QEAAJW4_STORAGE_TIER_CLASS@@PEAU_GUID@@PEAG@Z; CTieredVolume::GetTierInfo(_STORAGE_TIER_CLASS,_GUID *,ushort *)
0x14003cd7d  mov     ecx, [rsi+13Ch]
0x14003cd83  xor     edx, edx
0x14003cd85  mov     rax, [rbp+57h+var_90]
0x14003cd89  div     rcx
0x14003cd8c  mov     [rbx+28h], rax
0x14003cd90  mov     rcx, rsi; this
0x14003cd93  call    ?DereferenceVolume@CTieredVolume@@QEAAXXZ; CTieredVolume::DereferenceVolume(void)
0x14003cd98  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14003cd9c  test    rcx, rcx
0x14003cd9f  jz      short loc_14003CDA7
0x14003cda1  call    cs:__imp_NtClose
0x14003cda7  cmp     [rbp+57h+var_C4], r13b
0x14003cdab  jz      short loc_14003CDB9
0x14003cdad  xor     edx, edx; OldMode
0x14003cdaf  mov     ecx, [rbp+57h+OldMode]; NewMode
0x14003cdb2  call    cs:__imp_RtlSetThreadErrorMode
0x14003cdb8  nop
0x14003cdb9  lea     rcx, [rbp+57h+var_B0]; this
0x14003cdbd  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14003cdc2  mov     eax, edi
0x14003cdc4  add     rsp, 0F8h
0x14003cdcb  pop     r15
0x14003cdcd  pop     r14
0x14003cdcf  pop     r13
0x14003cdd1  pop     r12
0x14003cdd3  pop     rdi
0x14003cdd4  pop     rsi
0x14003cdd5  pop     rbx
0x14003cdd6  pop     rbp
0x14003cdd7  retn
```
