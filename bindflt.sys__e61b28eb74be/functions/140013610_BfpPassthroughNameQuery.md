# BfpPassthroughNameQuery

- ea: `0x140013610`
- end: `0x140013778`
- name: `BfpPassthroughNameQuery`
- size: `360`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400127a0`
- `0x140012c60`
- `0x140013864`

## callees

- `0x140001348`
- `0x140013610`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140013690`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140013690`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14001366e`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14001366e`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400136d3`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400136d3`
- `FLTMGR!FltGetFileNameInformation` at `0x14001363e`
- `FLTMGR!FltGetFileNameInformation` at `0x14001363e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400136ab`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400136ab`

## pseudocode

```c
__int64 __fastcall BfpPassthroughNameQuery(
        struct _FLT_CALLBACK_DATA *a1,
        struct _FILE_OBJECT *a2,
        struct _FLT_INSTANCE *a3,
        FLT_FILE_NAME_OPTIONS a4,
        PFLT_NAME_CONTROL NameCtrl)
{
  NTSTATUS FileNameInformationUnsafe; // eax
  NTSTATUS v6; // ebx
  PFLT_NAME_CONTROL v7; // rdi
  int v9; // r9d
  char v10; // [rsp+30h] [rbp-18h]
  NTSTATUS v11; // [rsp+38h] [rbp-10h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp+8h] BYREF

  FileNameInformation = 0;
  if ( a1 )
  {
    FileNameInformationUnsafe = FltGetFileNameInformation(a1, a4, &FileNameInformation);
  }
  else
  {
    if ( !a2 )
      goto LABEL_12;
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(a2, a3, a4, &FileNameInformation);
  }
  v6 = FileNameInformationUnsafe;
  if ( FileNameInformationUnsafe < 0 )
  {
LABEL_13:
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_7;
    v11 = v6;
    v9 = 36;
    v10 = -77;
    goto LABEL_15;
  }
  LODWORD(a2) = FileNameInformation->Name.Length;
  if ( !(_WORD)a2 && FileNameInformation->Volume.Length )
  {
LABEL_12:
    v6 = -1073741811;
    goto LABEL_13;
  }
  v7 = NameCtrl;
  v6 = FltCheckAndGrowNameControl(NameCtrl, (USHORT)a2);
  if ( v6 >= 0 )
  {
    RtlCopyUnicodeString(&v7->Name, &FileNameInformation->Name);
    goto LABEL_7;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v11 = v6;
    v9 = 37;
    v10 = -69;
LABEL_15:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      9,
      v9,
      (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
      v10,
      v11);
  }
LABEL_7:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140013610  push    rbx
0x140013612  sub     rsp, 40h
0x140013616  mov     [rsp+48h+arg_8], rdi
0x14001361b  mov     r10d, r9d
0x14001361e  mov     [rsp+48h+FileNameInformation], 0
0x140013627  mov     r11, r8
0x14001362a  mov     rax, rdx
0x14001362d  test    rcx, rcx
0x140013630  jz      loc_1400136C0
0x140013636  lea     r8, [rsp+48h+FileNameInformation]; FileNameInformation
0x14001363b  mov     edx, r9d; NameOptions
0x14001363e  call    cs:__imp_FltGetFileNameInformation
0x140013645  nop     dword ptr [rax+rax+00h]
0x14001364a  mov     ebx, eax
0x14001364c  test    eax, eax
0x14001364e  js      loc_1400136E9
0x140013654  mov     rcx, [rsp+48h+FileNameInformation]
0x140013659  movzx   edx, word ptr [rcx+8]; NewSize
0x14001365d  test    dx, dx
0x140013660  jz      loc_140013768
0x140013666  mov     rdi, [rsp+48h+NameCtrl]
0x14001366b  mov     rcx, rdi; NameCtrl
0x14001366e  call    cs:__imp_FltCheckAndGrowNameControl
0x140013675  nop     dword ptr [rax+rax+00h]
0x14001367a  mov     ebx, eax
0x14001367c  test    eax, eax
0x14001367e  js      loc_140013740
0x140013684  mov     rdx, [rsp+48h+FileNameInformation]
0x140013689  mov     rcx, rdi; DestinationString
0x14001368c  add     rdx, 8; SourceString
0x140013690  call    cs:__imp_RtlCopyUnicodeString
0x140013697  nop     dword ptr [rax+rax+00h]
0x14001369c  mov     rcx, [rsp+48h+FileNameInformation]; FileNameInformation
0x1400136a1  mov     rdi, [rsp+48h+arg_8]
0x1400136a6  test    rcx, rcx
0x1400136a9  jz      short loc_1400136B7
0x1400136ab  call    cs:__imp_FltReleaseFileNameInformation
0x1400136b2  nop     dword ptr [rax+rax+00h]
0x1400136b7  mov     eax, ebx
0x1400136b9  add     rsp, 40h
0x1400136bd  pop     rbx
0x1400136be  retn
0x1400136c0  test    rax, rax
0x1400136c3  jz      short loc_1400136E4
0x1400136c5  lea     r9, [rsp+48h+FileNameInformation]; FileNameInformation
0x1400136ca  mov     r8d, r10d; NameOptions
0x1400136cd  mov     rdx, r11; Instance
0x1400136d0  mov     rcx, rax; FileObject
0x1400136d3  call    cs:__imp_FltGetFileNameInformationUnsafe
0x1400136da  nop     dword ptr [rax+rax+00h]
0x1400136df  jmp     loc_14001364A
0x1400136e4  mov     ebx, 0C000000Dh
0x1400136e9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400136f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400136f7  jz      short loc_14001369C
0x1400136f9  mov     [rsp+48h+var_10], ebx
0x1400136fd  mov     r9d, 24h ; '$'
0x140013703  mov     dword ptr [rsp+48h+var_18], 3B3h
0x14001370b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013712  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140013719  mov     [rsp+48h+var_20], rax
0x14001371e  mov     r8d, 9
0x140013724  lea     rax, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x14001372b  mov     dl, 2
0x14001372d  mov     [rsp+48h+var_28], rax
0x140013732  mov     rcx, [rcx+40h]
0x140013736  call    WPP_RECORDER_SF_sDd
0x14001373b  jmp     loc_14001369C
0x140013740  lea     rax, WPP_RECORDER_INITIALIZED
0x140013747  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001374e  jz      loc_14001369C
0x140013754  mov     [rsp+48h+var_10], ebx
0x140013758  mov     r9d, 25h ; '%'
0x14001375e  mov     dword ptr [rsp+48h+var_18], 3BBh
0x140013766  jmp     short loc_14001370B
0x140013768  cmp     word ptr [rcx+18h], 0
0x14001376d  ja      loc_1400136E4
0x140013773  jmp     loc_140013666
```
