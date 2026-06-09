# Smb2GetHashFileHandle

- ea: `0x140071118`
- end: `0x1400715c7`
- name: `Smb2GetHashFileHandle`
- size: `1199`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140071f38`

## callees

- `0x140022958`
- `0x140028dbc`
- `0x1400379f8`
- `0x140038490`
- `0x140038980`
- `0x140070d48`
- `0x140071118`
- `0x140072158`
- `0x14008ed64`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400714b0`
- `ntoskrnl!ZwClose` at `0x1400714c1`
- `ntoskrnl!ZwClose` at `0x1400714b0`
- `ntoskrnl!ZwClose` at `0x1400714c1`
- `ntoskrnl!ZwCreateFile` at `0x14007147f`
- `ntoskrnl!ZwCreateFile` at `0x14007147f`
- `ntoskrnl!IoReuseIrp` at `0x14007136b`
- `ntoskrnl!IoReuseIrp` at `0x14007136b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007121b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400712dd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007121b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400712dd`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140071287`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140071287`
- `srvnet!SrvNotifyGroveler` at `0x1400714e8`
- `srvnet!SrvNotifyGroveler` at `0x14007155f`
- `srvnet!SrvNotifyGroveler` at `0x1400714e8`
- `srvnet!SrvNotifyGroveler` at `0x14007155f`

## pseudocode

```c
__int64 __fastcall Smb2GetHashFileHandle(__int64 a1, void **a2, struct _UNICODE_STRING *a3)
{
  __int64 v6; // rsi
  __int64 v7; // r12
  bool v8; // zf
  unsigned int v9; // ecx
  int v10; // eax
  unsigned int v11; // r15d
  unsigned int v12; // eax
  __int64 v13; // rcx
  unsigned int VolumeName; // ebx
  NTSTATUS appended; // eax
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  NTSTATUS FileObjectID; // ebx
  unsigned int v19; // eax
  int v20; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v23[2]; // [rsp+68h] [rbp-98h] BYREF
  char *v24; // [rsp+70h] [rbp-90h]
  __int64 v25; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING *v26; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING v27; // [rsp+88h] [rbp-78h] BYREF
  __int128 v28; // [rsp+98h] [rbp-68h] BYREF
  void **v29; // [rsp+B0h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int8 v32[64]; // [rsp+100h] [rbp+0h] BYREF
  char v33; // [rsp+140h] [rbp+40h] BYREF

  v26 = a3;
  v29 = a2;
  v23[1] = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v27 = 0;
  v28 = 0;
  memset(v32, 0, sizeof(v32));
  v6 = *(_QWORD *)(a1 + 560);
  v7 = *(_QWORD *)(v6 + 216);
  FileHandle = 0;
  *a2 = 0;
  v8 = *(_DWORD *)(v7 + 8) == 2;
  v9 = *(_DWORD *)(v7 + 12);
  v25 = *(_QWORD *)(v7 + 16);
  v10 = *(_DWORD *)(v6 + 200);
  if ( v8 )
  {
    v11 = v10 - 24;
    if ( v10 - 24 >= v9 )
      v11 = v9;
  }
  else
  {
    v12 = v10 - 16;
    v11 = v9;
    if ( v12 < v9 )
      v11 = v12;
  }
  v13 = *(_QWORD *)(v6 + 80);
  v24 = &v33;
  v23[0] = 34078720;
  VolumeName = Smb2GetVolumeName(*(_QWORD *)(v13 + 96), v23);
  if ( (VolumeName & 0x80000000) != 0 )
    return VolumeName;
  appended = RtlAppendUnicodeStringToString(a3, (PCUNICODE_STRING)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 96LL) + 152LL));
  VolumeName = appended;
  if ( appended < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v17 = 30;
LABEL_13:
      WPP_SF_qD(v16->AttachedDevice, v17, &WPP_8e7cd37454fb33500a68697303cffebe_Traceguids, a1, appended);
      return VolumeName;
    }
    return VolumeName;
  }
  appended = RtlAppendUnicodeToString(a3, L"\\");
  VolumeName = appended;
  if ( appended >= 0 )
  {
    appended = RtlAppendUnicodeStringToString(a3, (PCUNICODE_STRING)(*(_QWORD *)(v6 + 72) + 208LL));
    VolumeName = appended;
    if ( appended < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v17 = 32;
        goto LABEL_13;
      }
      return VolumeName;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        33,
        (unsigned int)&WPP_8e7cd37454fb33500a68697303cffebe_Traceguids,
        a1,
        (__int64)a3);
    }
    IoReuseIrp(*(PIRP *)(a1 + 120), 0);
    FileObjectID = Smb2GetFileObjectID(a1, *(_QWORD *)(*(_QWORD *)(v6 + 80) + 96LL), v32);
    if ( FileObjectID < 0 )
      goto LABEL_53;
    v27.Buffer = (PWSTR)&v24[2 * ((unsigned __int64)LOWORD(v23[0]) >> 1)];
    v27.Length = 0;
    v27.MaximumLength = 518 - LOWORD(v23[0]);
    VolumeName = I_ObjectIdToHashPath(&v27, v32);
    if ( (VolumeName & 0x80000000) != 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        appended = *(_DWORD *)(v7 + 4);
        v17 = 34;
        goto LABEL_13;
      }
      return VolumeName;
    }
    *((_QWORD *)&v28 + 1) = v24;
    LOWORD(v28) = LOWORD(v23[0]) + v27.Length;
    WORD1(v28) = LOWORD(v23[0]) + v27.Length;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v28;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 512;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    FileObjectID = ZwCreateFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0, 0, 0);
    if ( FileObjectID < 0 )
    {
LABEL_53:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          35,
          &WPP_8e7cd37454fb33500a68697303cffebe_Traceguids,
          a1,
          FileObjectID);
      }
      if ( FileObjectID == -1073741757 )
        return (unsigned int)-1073700607;
    }
    else
    {
      v19 = Smb2ValidateHashFile(a1, FileHandle);
      VolumeName = v19;
      if ( !v19 )
      {
        SrvNotifyGroveler(v26, 1, *(unsigned int *)(v7 + 4), v25, v11, 1);
        *v29 = FileHandle;
        return VolumeName;
      }
      if ( v19 != -1073741802 )
      {
        ZwClose(FileHandle);
        return VolumeName;
      }
      ZwClose(FileHandle);
    }
    SrvNotifyGroveler(v26, 1, *(unsigned int *)(v7 + 4), v25, v11, 2);
    v20 = *(_DWORD *)(v7 + 4);
    if ( v20 == 1 )
    {
      ++*(_DWORD *)(Srv2Statistics + 148);
    }
    else if ( v20 == 2 )
    {
      ++*(_DWORD *)(Srv2Statistics + 188);
    }
    return (unsigned int)-1073700607;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v17 = 31;
    goto LABEL_13;
  }
  return VolumeName;
}

```

## disassembly

```asm
0x140071118  mov     [rsp-8+arg_18], rbx
0x14007111d  push    rbp
0x14007111e  push    rsi
0x14007111f  push    rdi
0x140071120  push    r12
0x140071122  push    r13
0x140071124  push    r14
0x140071126  push    r15
0x140071128  lea     rbp, [rsp-260h]
0x140071130  sub     rsp, 360h
0x140071137  mov     rax, cs:__security_cookie
0x14007113e  xor     rax, rsp
0x140071141  mov     [rbp+290h+var_40], rax
0x140071148  xorps   xmm0, xmm0
0x14007114b  mov     [rbp+290h+var_310], r8
0x14007114f  xor     eax, eax
0x140071151  mov     [rbp+290h+var_2E0], rdx
0x140071155  mov     rdi, r8
0x140071158  mov     rbx, rdx
0x14007115b  mov     r13, rcx
0x14007115e  xorps   xmm1, xmm1
0x140071161  movups  xmmword ptr [rbp+290h+ObjectAttributes.ObjectName], xmm0
0x140071165  xor     r14d, r14d
0x140071168  lea     r8d, [rax+40h]; Size
0x14007116c  xor     edx, edx; Val
0x14007116e  mov     [rsp+390h+var_324], r14d
0x140071173  lea     rcx, [rbp+290h+var_290]; void *
0x140071177  movups  xmmword ptr [rbp+290h+ObjectAttributes.Length], xmm0
0x14007117b  movups  xmmword ptr [rbp+290h+ObjectAttributes+1Ch], xmm0
0x14007117f  movups  xmmword ptr [rbp+290h+IoStatusBlock], xmm0
0x140071183  movups  xmmword ptr [rbp+290h+var_308.Length], xmm0
0x140071187  movups  [rbp+290h+var_2F8], xmm1
0x14007118b  call    memset
0x140071190  mov     rsi, [r13+230h]
0x140071197  mov     r12, [rsi+0D8h]
0x14007119e  mov     [rsp+390h+FileHandle], r14
0x1400711a3  mov     [rbx], r14
0x1400711a6  cmp     dword ptr [r12+8], 2
0x1400711ac  mov     rax, [r12+10h]
0x1400711b1  mov     ecx, [r12+0Ch]
0x1400711b6  mov     [rsp+390h+var_318], rax
0x1400711bb  mov     eax, [rsi+0C8h]
0x1400711c1  jnz     short loc_1400711D0
0x1400711c3  lea     r15d, [rax-18h]
0x1400711c7  cmp     r15d, ecx
0x1400711ca  cmovnb  r15d, ecx
0x1400711ce  jmp     short loc_1400711DC
0x1400711d0  add     eax, 0FFFFFFF0h
0x1400711d3  mov     r15d, ecx
0x1400711d6  cmp     eax, ecx
0x1400711d8  cmovb   r15d, eax
0x1400711dc  mov     rcx, [rsi+50h]
0x1400711e0  lea     rax, [rbp+290h+var_250]
0x1400711e4  lea     rdx, [rsp+390h+var_328]
0x1400711e9  mov     [rsp+390h+var_320], rax
0x1400711ee  mov     [rsp+390h+var_328], 2080000h
0x1400711f6  mov     rcx, [rcx+60h]
0x1400711fa  call    Smb2GetVolumeName
0x1400711ff  mov     ebx, eax
0x140071201  test    eax, eax
0x140071203  js      loc_14007159A
0x140071209  mov     rax, [rsi+38h]
0x14007120d  mov     rcx, rdi; Destination
0x140071210  mov     rdx, [rax+60h]
0x140071214  add     rdx, 98h; Source
0x14007121b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140071222  nop     dword ptr [rax+rax+00h]
0x140071227  mov     ebx, eax
0x140071229  test    eax, eax
0x14007122b  jns     short loc_14007127D
0x14007122d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140071234  lea     r14, WPP_GLOBAL_Control
0x14007123b  cmp     rcx, r14
0x14007123e  jz      loc_14007159A
0x140071244  bt      dword ptr [rcx+2Ch], 1Dh
0x140071249  jnb     loc_14007159A
0x14007124f  mov     edi, 1
0x140071254  cmp     [rcx+29h], dil
0x140071258  jb      loc_14007159A
0x14007125e  lea     edx, [rdi+1Dh]
0x140071261  mov     rcx, [rcx+18h]
0x140071265  lea     r8, WPP_8e7cd37454fb33500a68697303cffebe_Traceguids
0x14007126c  mov     r9, r13
0x14007126f  mov     dword ptr [rsp+390h+AllocationSize], eax
0x140071273  call    WPP_SF_qD
0x140071278  jmp     loc_14007159A
0x14007127d  lea     rdx, Source; "\\"
0x140071284  mov     rcx, rdi; Destination
0x140071287  call    cs:__imp_RtlAppendUnicodeToString
0x14007128e  nop     dword ptr [rax+rax+00h]
0x140071293  mov     ebx, eax
0x140071295  test    eax, eax
0x140071297  jns     short loc_1400712CF
0x140071299  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400712a0  lea     r14, WPP_GLOBAL_Control
0x1400712a7  cmp     rcx, r14
0x1400712aa  jz      loc_14007159A
0x1400712b0  bt      dword ptr [rcx+2Ch], 1Dh
0x1400712b5  jnb     loc_14007159A
0x1400712bb  mov     edi, 1
0x1400712c0  cmp     [rcx+29h], dil
0x1400712c4  jb      loc_14007159A
0x1400712ca  lea     edx, [rdi+1Eh]
0x1400712cd  jmp     short loc_140071261
0x1400712cf  mov     rdx, [rsi+48h]
0x1400712d3  mov     rcx, rdi; Destination
0x1400712d6  add     rdx, 0D0h; Source
0x1400712dd  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400712e4  nop     dword ptr [rax+rax+00h]
0x1400712e9  mov     ebx, eax
0x1400712eb  test    eax, eax
0x1400712ed  jns     short loc_140071328
0x1400712ef  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400712f6  lea     r14, WPP_GLOBAL_Control
0x1400712fd  cmp     rcx, r14
0x140071300  jz      loc_14007159A
0x140071306  bt      dword ptr [rcx+2Ch], 1Dh
0x14007130b  jnb     loc_14007159A
0x140071311  mov     edi, 1
0x140071316  cmp     [rcx+29h], dil
0x14007131a  jb      loc_14007159A
0x140071320  lea     edx, [rdi+1Fh]
0x140071323  jmp     loc_140071261
0x140071328  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007132f  lea     r14, WPP_GLOBAL_Control
0x140071336  cmp     rcx, r14
0x140071339  jz      short loc_140071365
0x14007133b  bt      dword ptr [rcx+2Ch], 1Dh
0x140071340  jnb     short loc_140071365
0x140071342  cmp     byte ptr [rcx+29h], 2
0x140071346  jb      short loc_140071365
0x140071348  mov     rcx, [rcx+18h]
0x14007134c  lea     r8, WPP_8e7cd37454fb33500a68697303cffebe_Traceguids
0x140071353  mov     edx, 21h ; '!'
0x140071358  mov     [rsp+390h+AllocationSize], rdi
0x14007135d  mov     r9, r13
0x140071360  call    WPP_SF_qZ
0x140071365  mov     rcx, [r13+78h]; Irp
0x140071369  xor     edx, edx; Iostatus
0x14007136b  call    cs:__imp_IoReuseIrp
0x140071372  nop     dword ptr [rax+rax+00h]
0x140071377  mov     rdx, [rsi+50h]
0x14007137b  lea     r8, [rbp+290h+var_290]
0x14007137f  mov     rcx, r13
0x140071382  mov     rdx, [rdx+60h]
0x140071386  call    Smb2GetFileObjectID
0x14007138b  mov     ebx, eax
0x14007138d  mov     edi, 1
0x140071392  test    eax, eax
0x140071394  js      loc_140071505
0x14007139a  mov     rcx, [rsp+390h+var_320]
0x14007139f  lea     rdx, [rbp+290h+var_290]; unsigned __int8 *
0x1400713a3  movzx   eax, word ptr [rsp+390h+var_328]
0x1400713a8  shr     rax, 1
0x1400713ab  lea     rax, [rcx+rax*2]
0x1400713af  mov     [rbp+290h+var_308.Buffer], rax
0x1400713b3  lea     rcx, [rbp+290h+var_308]; struct _UNICODE_STRING *
0x1400713b7  xor     eax, eax
0x1400713b9  mov     [rbp+290h+var_308.Length], ax
0x1400713bd  mov     eax, 206h
0x1400713c2  sub     ax, word ptr [rsp+390h+var_328]
0x1400713c7  mov     [rbp+290h+var_308.MaximumLength], ax
0x1400713cb  mov     r9d, [r12+4]
0x1400713d0  call    I_ObjectIdToHashPath
0x1400713d5  xor     ecx, ecx
0x1400713d7  mov     ebx, eax
0x1400713d9  test    eax, eax
0x1400713db  jns     short loc_14007140F
0x1400713dd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400713e4  cmp     rcx, r14
0x1400713e7  jz      loc_14007159A
0x1400713ed  bt      dword ptr [rcx+2Ch], 1Dh
0x1400713f2  jnb     loc_14007159A
0x1400713f8  cmp     [rcx+29h], dil
0x1400713fc  jb      loc_14007159A
0x140071402  mov     eax, [r12+4]
0x140071407  lea     edx, [rdi+21h]
0x14007140a  jmp     loc_140071261
0x14007140f  mov     rax, [rsp+390h+var_320]
0x140071414  lea     r9, [rbp+290h+IoStatusBlock]; IoStatusBlock
0x140071418  mov     [rsp+390h+EaLength], ecx; EaLength
0x14007141c  lea     r8, [rbp+290h+ObjectAttributes]; ObjectAttributes
0x140071420  mov     [rsp+390h+EaBuffer], rcx; EaBuffer
0x140071425  xorps   xmm0, xmm0
0x140071428  mov     [rsp+390h+CreateOptions], ecx; CreateOptions
0x14007142c  mov     edx, 80000000h; DesiredAccess
0x140071431  mov     qword ptr [rbp+290h+var_2F8+8], rax
0x140071435  movzx   eax, [rbp+290h+var_308.Length]
0x140071439  add     ax, word ptr [rsp+390h+var_328]
0x14007143e  mov     [rsp+390h+CreateDisposition], edi; CreateDisposition
0x140071442  mov     [rsp+390h+ShareAccess], edi; ShareAccess
0x140071446  mov     word ptr [rbp+290h+var_2F8], ax
0x14007144a  mov     word ptr [rbp+290h+var_2F8+2], ax
0x14007144e  lea     rax, [rbp+290h+var_2F8]
0x140071452  mov     [rbp+290h+ObjectAttributes.RootDirectory], rcx
0x140071456  mov     [rsp+390h+FileAttributes], 80h; FileAttributes
0x14007145e  mov     [rsp+390h+AllocationSize], rcx; AllocationSize
0x140071463  lea     rcx, [rsp+390h+FileHandle]; FileHandle
0x140071468  mov     [rbp+290h+ObjectAttributes.ObjectName], rax
0x14007146c  mov     [rbp+290h+ObjectAttributes.Length], 30h ; '0'
0x140071473  mov     [rbp+290h+ObjectAttributes.Attributes], 200h
0x14007147a  movdqu  xmmword ptr [rbp+290h+ObjectAttributes.SecurityDescriptor], xmm0
0x14007147f  call    cs:__imp_ZwCreateFile
0x140071486  nop     dword ptr [rax+rax+00h]
0x14007148b  mov     ebx, eax
0x14007148d  test    eax, eax
0x14007148f  js      short loc_140071505
0x140071491  mov     rdx, [rsp+390h+FileHandle]
0x140071496  mov     rcx, r13
0x140071499  call    Smb2ValidateHashFile
0x14007149e  mov     ebx, eax
0x1400714a0  test    eax, eax
0x1400714a2  jz      short loc_1400714CF
0x1400714a4  mov     rcx, [rsp+390h+FileHandle]; Handle
0x1400714a9  cmp     eax, 0C0000016h
0x1400714ae  jz      short loc_1400714C1
0x1400714b0  call    cs:__imp_ZwClose
0x1400714b7  nop     dword ptr [rax+rax+00h]
0x1400714bc  jmp     loc_14007159A
0x1400714c1  call    cs:__imp_ZwClose
0x1400714c8  nop     dword ptr [rax+rax+00h]
0x1400714cd  jmp     short loc_140071542
0x1400714cf  mov     r9, [rsp+390h+var_318]
0x1400714d4  mov     edx, edi
0x1400714d6  mov     r8d, [r12+4]
0x1400714db  mov     rcx, [rbp+290h+var_310]
0x1400714df  mov     [rsp+390h+FileAttributes], edi
0x1400714e3  mov     dword ptr [rsp+390h+AllocationSize], r15d
0x1400714e8  call    cs:__imp_SrvNotifyGroveler
0x1400714ef  nop     dword ptr [rax+rax+00h]
0x1400714f4  mov     rcx, [rbp+290h+var_2E0]
0x1400714f8  mov     rax, [rsp+390h+FileHandle]
0x1400714fd  mov     [rcx], rax
0x140071500  jmp     loc_14007159A
0x140071505  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007150c  cmp     rcx, r14
0x14007150f  jz      short loc_14007153A
0x140071511  bt      dword ptr [rcx+2Ch], 1Dh
0x140071516  jnb     short loc_14007153A
0x140071518  cmp     [rcx+29h], dil
0x14007151c  jb      short loc_14007153A
0x14007151e  mov     rcx, [rcx+18h]
0x140071522  lea     r8, WPP_8e7cd37454fb33500a68697303cffebe_Traceguids
0x140071529  mov     edx, 23h ; '#'
0x14007152e  mov     dword ptr [rsp+390h+AllocationSize], ebx
0x140071532  mov     r9, r13
0x140071535  call    WPP_SF_qD
0x14007153a  cmp     ebx, 0C0000043h
0x140071540  jz      short loc_140071595
0x140071542  mov     r9, [rsp+390h+var_318]
0x140071547  mov     edx, edi
0x140071549  mov     r8d, [r12+4]
0x14007154e  mov     rcx, [rbp+290h+var_310]
0x140071552  mov     [rsp+390h+FileAttributes], 2
0x14007155a  mov     dword ptr [rsp+390h+AllocationSize], r15d
0x14007155f  call    cs:__imp_SrvNotifyGroveler
0x140071566  nop     dword ptr [rax+rax+00h]
0x14007156b  mov     eax, [r12+4]
0x140071570  cmp     eax, edi
0x140071572  jnz     short loc_140071583
0x140071574  mov     rax, cs:Srv2Statistics
0x14007157b  add     [rax+94h], edi
0x140071581  jmp     short loc_140071595
0x140071583  cmp     eax, 2
0x140071586  jnz     short loc_140071595
0x140071588  mov     rax, cs:Srv2Statistics
0x14007158f  add     [rax+0BCh], edi
0x140071595  mov     ebx, 0C000A101h
0x14007159a  mov     eax, ebx
0x14007159c  mov     rcx, [rbp+290h+var_40]
0x1400715a3  xor     rcx, rsp; StackCookie
0x1400715a6  call    __security_check_cookie
0x1400715ab  mov     rbx, [rsp+390h+arg_18]
0x1400715b3  add     rsp, 360h
0x1400715ba  pop     r15
0x1400715bc  pop     r14
0x1400715be  pop     r13
0x1400715c0  pop     r12
0x1400715c2  pop     rdi
0x1400715c3  pop     rsi
0x1400715c4  pop     rbp
0x1400715c5  retn
```
