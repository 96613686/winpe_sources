# BasepCopyEncryptionIfNeeded

- ea: `0x1801125f4`
- end: `0x180112bc4`
- name: `BasepCopyEncryptionIfNeeded`
- size: `1488`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d061c`

## callees

- `0x1800134a0`
- `0x1800cf810`
- `0x1800cfa60`
- `0x1800e2fd4`
- `0x1801125c8`
- `0x1801125f4`
- `0x18012daf0`
- `0x180132718`
- `0x180132a80`
- `0x180188f10`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x180112785`
- `ntdll!NtSetInformationFile` at `0x1801128db`
- `ntdll!NtSetInformationFile` at `0x180112785`
- `ntdll!NtSetInformationFile` at `0x1801128db`
- `ntdll!NtQueryVolumeInformationFile` at `0x1801129a5`
- `ntdll!NtQueryVolumeInformationFile` at `0x1801129a5`
- `ntdll!NtCreateFile` at `0x180112891`
- `ntdll!NtCreateFile` at `0x180112891`
- `ntdll!RtlSetLastWin32Error` at `0x180112922`
- `ntdll!RtlSetLastWin32Error` at `0x180112922`
- `ntdll!NtClose` at `0x1801127b4`
- `ntdll!NtClose` at `0x1801127b4`
- `ext-ms-win-kernel32-file-l1-1-0!BasepCopyEncryption` at `0x18011282d`
- `ext-ms-win-kernel32-file-l1-1-0!BasepCopyEncryption` at `0x18011282d`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x1801127dd`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x1801127dd`
- `ext-ms-win-security-efswrt-l1-1-0!ProtectFileToIdentity` at `0x180112806`
- `ext-ms-win-security-efswrt-l1-1-0!ProtectFileToIdentity` at `0x180112806`

## pseudocode

```c
__int64 __fastcall BasepCopyEncryptionIfNeeded(
        __int64 a1,
        __int64 a2,
        HANDLE *a3,
        struct _OBJECT_ATTRIBUTES *a4,
        ACCESS_MASK DesiredAccess,
        ULONG ShareAccess,
        ULONG CreateOptions,
        int a8,
        int a9,
        _BYTE *a10,
        int a11,
        __int16 a12,
        int a13,
        __int64 a14,
        int a15,
        __int64 *a16,
        int a17,
        GUID *a18)
{
  _DWORD *v19; // r15
  unsigned int v20; // ebx
  int v21; // r8d
  int v22; // ecx
  __int64 v23; // r13
  int v24; // r10d
  int v25; // r9d
  int v26; // eax
  int v27; // eax
  NTSTATUS v28; // r15d
  __int64 v29; // rcx
  int v30; // eax
  NTSTATUS v31; // eax
  _BYTE *v32; // r15
  unsigned int v33; // eax
  int v35; // [rsp+60h] [rbp-158h]
  int v36; // [rsp+64h] [rbp-154h]
  int v37; // [rsp+6Ch] [rbp-14Ch] BYREF
  int v38; // [rsp+70h] [rbp-148h] BYREF
  int v39; // [rsp+74h] [rbp-144h] BYREF
  int v40; // [rsp+78h] [rbp-140h] BYREF
  unsigned int v41; // [rsp+7Ch] [rbp-13Ch] BYREF
  __int64 FsInformation; // [rsp+80h] [rbp-138h] BYREF
  unsigned int v43; // [rsp+88h] [rbp-130h]
  int v44; // [rsp+8Ch] [rbp-12Ch]
  int v45; // [rsp+90h] [rbp-128h]
  _DWORD *v46; // [rsp+98h] [rbp-120h]
  int v47; // [rsp+A0h] [rbp-118h]
  __int64 v48; // [rsp+A8h] [rbp-110h]
  POBJECT_ATTRIBUTES ObjectAttributes[2]; // [rsp+B0h] [rbp-108h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-F8h]
  LPGUID ActivityId; // [rsp+C8h] [rbp-F0h]
  GUID *v52; // [rsp+D0h] [rbp-E8h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-E0h] BYREF
  _OWORD FileInformation[2]; // [rsp+E8h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+108h] [rbp-B0h]
  char v56[32]; // [rsp+110h] [rbp-A8h] BYREF
  int *v57; // [rsp+130h] [rbp-88h]
  __int64 v58; // [rsp+138h] [rbp-80h]
  int *v59; // [rsp+140h] [rbp-78h]
  __int64 v60; // [rsp+148h] [rbp-70h]
  int *v61; // [rsp+150h] [rbp-68h]
  __int64 v62; // [rsp+158h] [rbp-60h]
  int *v63; // [rsp+160h] [rbp-58h]
  __int64 v64; // [rsp+168h] [rbp-50h]
  unsigned int *v65; // [rsp+170h] [rbp-48h]
  __int64 v66; // [rsp+178h] [rbp-40h]

  ObjectAttributes[0] = a4;
  FsInformation = a2;
  v50 = a1;
  v19 = a10;
  v46 = a10;
  v48 = a14;
  ActivityId = a18;
  v52 = a18;
  v20 = 0;
  v21 = 0;
  v43 = 0;
  v22 = 0;
  v44 = 0;
  IoStatusBlock = 0;
  v23 = *a16;
  memset(FileInformation, 0, sizeof(FileInformation));
  v55 = 0;
  v24 = 0;
  v35 = 0;
  v25 = 0;
  v36 = 0;
  v26 = a8 & 0x4000;
  v45 = v26;
  if ( (a8 & 0x4000) != 0 && (a9 & 0x4000) != 0 && (*(_DWORD *)a10 & 0x4000) == 0 )
  {
    if ( (a8 & 0x10) != 0 && (*a10 & 4) == 0 )
    {
      v21 = 1;
      v43 = 1;
    }
  }
  else if ( (a8 & 0x4000) == 0 && (*(_DWORD *)a10 & 0x4000) != 0 && (a12 & 0x200) != 0 )
  {
    v22 = 1;
  }
  if ( a13 == 3 || v22 || v21 )
  {
    v27 = *(_DWORD *)a10;
    if ( (*(_DWORD *)a10 & 1) != 0 )
    {
      v44 = 1;
      LODWORD(v55) = v27 & 0xFFFFFFFE;
      v28 = NtSetInformationFile(*a3, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
      if ( v28 < 0 )
        goto LABEL_16;
      v19 = v46;
    }
    NtClose(*a3);
    *a3 = (HANDLE)-1LL;
    if ( a13 == 3 )
    {
      if ( (*v19 & 0x4000) != 0 )
      {
        v30 = EfsClientDecryptFile(FsInformation, 0);
        v36 = v30;
        v47 = v30;
      }
      else
      {
        v30 = 0;
      }
      if ( !v30 )
        v35 = ProtectFileToIdentity(FsInformation, v48, 1);
    }
    else if ( (unsigned __int8)IsBasepGetComputerNameFromNtPathPresent() )
    {
      BasepCopyEncryption(FsInformation, v43, v19);
    }
    v31 = NtCreateFile(
            a3,
            DesiredAccess,
            ObjectAttributes[0],
            &IoStatusBlock,
            0,
            a9 & a8 & 0xDAFFB7,
            ShareAccess,
            1u,
            CreateOptions,
            0,
            0);
    if ( v31 < 0 )
    {
      *a3 = (HANDLE)-1LL;
      v29 = (unsigned int)v31;
      goto LABEL_17;
    }
    if ( v44 )
    {
      LODWORD(v55) = v55 | 1;
      v28 = NtSetInformationFile(*a3, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
      if ( v28 < 0 )
      {
LABEL_16:
        BaseMarkFileForDelete(*a3);
        v29 = (unsigned int)v28;
LABEL_17:
        BaseSetLastNTError(v29);
        goto LABEL_57;
      }
    }
    v24 = v35;
    v25 = v36;
    v26 = v45;
  }
  if ( a13 == 3 && (v25 || v24 < 0) )
    goto LABEL_35;
  if ( a13 )
    goto LABEL_56;
  if ( !v26 )
    goto LABEL_56;
  v32 = v46;
  if ( (*v46 & 0x4000) != 0 || (a12 & 8) != 0 )
    goto LABEL_56;
  if ( (unsigned int)CheckAllowDecryptedRemoteDestinationPolicy() )
  {
    *(_OWORD *)ObjectAttributes = 0;
    FsInformation = 0;
    if ( NtQueryVolumeInformationFile(
           *a3,
           (PIO_STATUS_BLOCK)ObjectAttributes,
           &FsInformation,
           8u,
           FileFsDeviceInformation) >= 0
      && (FsInformation & 0x1000000000LL) != 0 )
    {
      v20 = 1;
    }
  }
  if ( v20 )
    goto LABEL_56;
  if ( v23 && *(_QWORD *)(v23 + 144) && (a12 & 0x10) != 0 )
  {
    if ( (a11 & 0x20000) != 0 )
      v33 = (a9 & 0x4000) != 0 ? ((*v32 & 4) != 0 ? 21 : 12) : 12;
    else
      v33 = 11;
    *(_DWORD *)(v23 + 20) = 0;
    *(_DWORD *)(v23 + 24) = 6000;
    *(_QWORD *)(v23 + 64) = 0;
    *(_QWORD *)(v23 + 32) = v50;
    *(_QWORD *)(v23 + 40) = a3;
    if ( (unsigned int)BasepCopyFileCallback(v33) )
      v20 = 1;
  }
  if ( v20 )
  {
LABEL_56:
    v20 = 1;
  }
  else
  {
LABEL_35:
    BaseMarkFileForDelete(*a3);
    RtlSetLastWin32Error(0x1770u);
  }
LABEL_57:
  if ( (unsigned int)(a13 - 2) <= 1 || a15 )
  {
    if ( ActivityId && !ActivityId[2].Data1 )
      BasepBaseCopyStreamStartActivity(ActivityId);
    if ( (unsigned int)dword_18039CC08 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039CC08, 0x400000000000LL) )
    {
      v37 = a13;
      v57 = &v37;
      v58 = 4;
      v38 = v35;
      v59 = &v38;
      v60 = 4;
      v39 = a17;
      v61 = &v39;
      v62 = 4;
      v40 = a15;
      v63 = &v40;
      v64 = 4;
      v41 = v20;
      v65 = &v41;
      v66 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18039CC08, &word_180359156, 0, 0, 7, v56);
    }
  }
  return v20;
}

```

## disassembly

```asm
0x1801125f4  mov     [rsp+arg_0], rbx
0x1801125f9  push    rdi
0x1801125fa  push    r12
0x1801125fc  push    r13
0x1801125fe  push    r14
0x180112600  push    r15
0x180112602  sub     rsp, 190h
0x180112609  mov     rax, cs:__security_cookie
0x180112610  xor     rax, rsp
0x180112613  mov     [rsp+1B8h+var_38], rax
0x18011261b  mov     [rsp+1B8h+ObjectAttributes], r9
0x180112623  mov     r14, r8
0x180112626  mov     [rsp+1B8h+FsInformation], rdx
0x18011262e  mov     [rsp+1B8h+var_F8], rcx
0x180112636  mov     r15, [rsp+1B8h+arg_48]
0x18011263e  mov     [rsp+1B8h+var_120], r15
0x180112646  mov     rax, [rsp+1B8h+arg_68]
0x18011264e  mov     [rsp+1B8h+var_110], rax
0x180112656  mov     rax, [rsp+1B8h+arg_78]
0x18011265e  mov     rcx, [rsp+1B8h+arg_88]
0x180112666  mov     [rsp+1B8h+ActivityId], rcx
0x18011266e  mov     [rsp+1B8h+var_E8], rcx
0x180112676  xor     ebx, ebx
0x180112678  mov     [rsp+1B8h+var_150], ebx
0x18011267c  xor     r8d, r8d
0x18011267f  mov     [rsp+1B8h+var_130], r8d
0x180112687  xor     ecx, ecx
0x180112689  mov     [rsp+1B8h+var_12C], ecx
0x180112690  xorps   xmm0, xmm0
0x180112693  movups  xmmword ptr [rsp+1B8h+IoStatusBlock], xmm0
0x18011269b  mov     r13, [rax]
0x18011269e  xorps   xmm1, xmm1
0x1801126a1  xor     eax, eax
0x1801126a3  movups  [rsp+1B8h+FileInformation], xmm1
0x1801126ab  movups  [rsp+1B8h+var_C0], xmm1
0x1801126b3  mov     [rsp+1B8h+var_B0], rax
0x1801126bb  xor     r10d, r10d
0x1801126be  mov     [rsp+1B8h+var_158], r10d
0x1801126c3  xor     r9d, r9d
0x1801126c6  mov     [rsp+1B8h+var_154], r9d
0x1801126cb  mov     edx, [rsp+1B8h+arg_38]
0x1801126d2  mov     eax, edx
0x1801126d4  mov     r11d, 4000h
0x1801126da  and     eax, r11d
0x1801126dd  mov     [rsp+1B8h+var_128], eax
0x1801126e4  jz      short loc_18011270F
0x1801126e6  test    [rsp+1B8h+arg_40], r11d
0x1801126ee  jz      short loc_18011270F
0x1801126f0  test    [r15], r11d
0x1801126f3  jnz     short loc_18011270F
0x1801126f5  lea     edi, [rbx+1]
0x1801126f8  test    dl, 10h
0x1801126fb  jz      short loc_180112730
0x1801126fd  test    byte ptr [r15], 4
0x180112701  jnz     short loc_180112730
0x180112703  mov     r8d, edi
0x180112706  mov     [rsp+1B8h+var_130], edi
0x18011270d  jmp     short loc_180112730
0x18011270f  test    eax, eax
0x180112711  jnz     short loc_18011272B
0x180112713  test    [r15], r11d
0x180112716  jz      short loc_18011272B
0x180112718  test    dword ptr [rsp+1B8h+arg_58], 200h
0x180112723  lea     edi, [rax+1]
0x180112726  cmovnz  ecx, edi
0x180112729  jmp     short loc_180112730
0x18011272b  mov     edi, 1
0x180112730  mov     r12d, [rsp+1B8h+arg_60]
0x180112738  cmp     r12d, 3
0x18011273c  jz      short loc_18011274B
0x18011273e  test    ecx, ecx
0x180112740  jnz     short loc_18011274B
0x180112742  test    r8d, r8d
0x180112745  jz      loc_180112903
0x18011274b  mov     eax, [r15]
0x18011274e  test    dil, al
0x180112751  jz      short loc_1801127B1
0x180112753  mov     [rsp+1B8h+var_12C], edi
0x18011275a  and     eax, 0FFFFFFFEh
0x18011275d  mov     dword ptr [rsp+1B8h+var_B0], eax
0x180112764  mov     [rsp+1B8h+FileInformationClass], 4; FileInformationClass
0x18011276c  mov     r9d, 28h ; '('; Length
0x180112772  lea     r8, [rsp+1B8h+FileInformation]; FileInformation
0x18011277a  lea     rdx, [rsp+1B8h+IoStatusBlock]; IoStatusBlock
0x180112782  mov     rcx, [r14]; FileHandle
0x180112785  call    cs:__imp_NtSetInformationFile
0x18011278b  mov     r15d, eax
0x18011278e  test    eax, eax
0x180112790  jns     short loc_1801127A9
0x180112792  xor     edx, edx
0x180112794  mov     rcx, [r14]; FileHandle
0x180112797  call    BaseMarkFileForDelete
0x18011279c  mov     ecx, r15d
0x18011279f  call    BaseSetLastNTError
0x1801127a4  jmp     loc_180112A65
0x1801127a9  mov     r15, [rsp+1B8h+var_120]
0x1801127b1  mov     rcx, [r14]; Handle
0x1801127b4  call    cs:__imp_NtClose
0x1801127ba  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1801127c1  cmp     r12d, 3
0x1801127c5  jnz     short loc_180112812
0x1801127c7  test    dword ptr [r15], 4000h
0x1801127ce  mov     r15, [rsp+1B8h+FsInformation]
0x1801127d6  jz      short loc_1801127F0
0x1801127d8  xor     edx, edx
0x1801127da  mov     rcx, r15
0x1801127dd  call    cs:__imp_EfsClientDecryptFile
0x1801127e3  mov     [rsp+1B8h+var_154], eax
0x1801127e7  mov     [rsp+1B8h+var_118], eax
0x1801127ee  jmp     short loc_1801127F4
0x1801127f0  mov     eax, [rsp+1B8h+var_154]
0x1801127f4  test    eax, eax
0x1801127f6  jnz     short loc_180112833
0x1801127f8  mov     r8d, edi
0x1801127fb  mov     rdx, [rsp+1B8h+var_110]
0x180112803  mov     rcx, r15
0x180112806  call    cs:__imp_ProtectFileToIdentity
0x18011280c  mov     [rsp+1B8h+var_158], eax
0x180112810  jmp     short loc_180112833
0x180112812  call    IsBasepGetComputerNameFromNtPathPresent
0x180112817  test    al, al
0x180112819  jz      short loc_180112833
0x18011281b  mov     r8, r15
0x18011281e  mov     edx, [rsp+1B8h+var_130]
0x180112825  mov     rcx, [rsp+1B8h+FsInformation]
0x18011282d  call    cs:__imp_BasepCopyEncryption
0x180112833  mov     ecx, [rsp+1B8h+arg_38]
0x18011283a  and     ecx, [rsp+1B8h+arg_40]
0x180112841  and     ecx, 0DAFFB7h
0x180112847  xor     r15d, r15d
0x18011284a  mov     [rsp+1B8h+EaLength], r15d; EaLength
0x18011284f  mov     [rsp+1B8h+EaBuffer], r15; EaBuffer
0x180112854  mov     eax, [rsp+1B8h+arg_30]
0x18011285b  mov     [rsp+1B8h+CreateOptions], eax; CreateOptions
0x18011285f  mov     [rsp+1B8h+CreateDisposition], edi; CreateDisposition
0x180112863  mov     eax, [rsp+1B8h+arg_28]
0x18011286a  mov     [rsp+1B8h+ShareAccess], eax; ShareAccess
0x18011286e  mov     [rsp+1B8h+FileAttributes], ecx; FileAttributes
0x180112872  mov     qword ptr [rsp+1B8h+FileInformationClass], r15; AllocationSize
0x180112877  lea     r9, [rsp+1B8h+IoStatusBlock]; IoStatusBlock
0x18011287f  mov     r8, [rsp+1B8h+ObjectAttributes]; ObjectAttributes
0x180112887  mov     edx, [rsp+1B8h+DesiredAccess]; DesiredAccess
0x18011288e  mov     rcx, r14; FileHandle
0x180112891  call    cs:__imp_NtCreateFile
0x180112897  test    eax, eax
0x180112899  jns     short loc_1801128A9
0x18011289b  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1801128a2  mov     ecx, eax
0x1801128a4  jmp     loc_18011279F
0x1801128a9  cmp     [rsp+1B8h+var_12C], r15d
0x1801128b1  jz      short loc_1801128EC
0x1801128b3  or      dword ptr [rsp+1B8h+var_B0], edi
0x1801128ba  mov     [rsp+1B8h+FileInformationClass], 4; FileInformationClass
0x1801128c2  mov     r9d, 28h ; '('; Length
0x1801128c8  lea     r8, [rsp+1B8h+FileInformation]; FileInformation
0x1801128d0  lea     rdx, [rsp+1B8h+IoStatusBlock]; IoStatusBlock
0x1801128d8  mov     rcx, [r14]; FileHandle
0x1801128db  call    cs:__imp_NtSetInformationFile
0x1801128e1  mov     r15d, eax
0x1801128e4  test    eax, eax
0x1801128e6  js      loc_180112792
0x1801128ec  mov     r11d, 4000h
0x1801128f2  mov     r10d, [rsp+1B8h+var_158]
0x1801128f7  mov     r9d, [rsp+1B8h+var_154]
0x1801128fc  mov     eax, [rsp+1B8h+var_128]
0x180112903  cmp     r12d, 3
0x180112907  jnz     short loc_18011292D
0x180112909  test    r9d, r9d
0x18011290c  jnz     short loc_180112913
0x18011290e  test    r10d, r10d
0x180112911  jns     short loc_18011292D
0x180112913  xor     edx, edx
0x180112915  mov     rcx, [r14]; FileHandle
0x180112918  call    BaseMarkFileForDelete
0x18011291d  mov     ecx, 1770h; LastError
0x180112922  call    cs:__imp_RtlSetLastWin32Error
0x180112928  jmp     loc_180112A65
0x18011292d  test    r12d, r12d
0x180112930  jnz     loc_180112A5F
0x180112936  test    eax, eax
0x180112938  jz      loc_180112A5F
0x18011293e  mov     r15, [rsp+1B8h+var_120]
0x180112946  test    [r15], r11d
0x180112949  jnz     loc_180112A5F
0x18011294f  test    byte ptr [rsp+1B8h+arg_58], 8
0x180112957  jnz     loc_180112A5F
0x18011295d  call    CheckAllowDecryptedRemoteDestinationPolicy
0x180112962  test    eax, eax
0x180112964  jz      short loc_1801129BE
0x180112966  xorps   xmm0, xmm0
0x180112969  movups  xmmword ptr [rsp+1B8h+ObjectAttributes], xmm0
0x180112971  mov     [rsp+1B8h+FsInformation], 0
0x18011297d  mov     dword ptr [rsp+1B8h+FsInformation+4], r12d
0x180112985  mov     [rsp+1B8h+FileInformationClass], 4; FsInformationClass
0x18011298d  lea     r9d, [r12+8]; Length
0x180112992  lea     r8, [rsp+1B8h+FsInformation]; FsInformation
0x18011299a  lea     rdx, [rsp+1B8h+ObjectAttributes]; IoStatusBlock
0x1801129a2  mov     rcx, [r14]; FileHandle
0x1801129a5  call    cs:__imp_NtQueryVolumeInformationFile
0x1801129ab  test    eax, eax
0x1801129ad  js      short loc_1801129BE
0x1801129af  test    byte ptr [rsp+1B8h+FsInformation+4], 10h
0x1801129b7  cmovnz  ebx, edi
0x1801129ba  mov     [rsp+1B8h+var_150], ebx
0x1801129be  test    ebx, ebx
0x1801129c0  jnz     loc_180112A5F
0x1801129c6  test    r13, r13
0x1801129c9  jz      loc_180112A57
0x1801129cf  cmp     qword ptr [r13+90h], 0
0x1801129d7  jz      short loc_180112A57
0x1801129d9  test    byte ptr [rsp+1B8h+arg_58], 10h
0x1801129e1  jz      short loc_180112A57
0x1801129e3  test    [rsp+1B8h+arg_50], 20000h
0x1801129ee  jz      short loc_180112A17
0x1801129f0  test    [rsp+1B8h+arg_40], 4000h
0x1801129fb  jnz     short loc_180112A02
0x1801129fd  lea     eax, [rbx+0Ch]
0x180112a00  jmp     short loc_180112A1C
0x180112a02  mov     al, [r15]
0x180112a05  and     al, 4
0x180112a07  neg     al
0x180112a09  sbb     ecx, ecx
0x180112a0b  and     ecx, 9
0x180112a0e  mov     eax, 0Ch
0x180112a13  add     eax, ecx
0x180112a15  jmp     short loc_180112A1C
0x180112a17  mov     eax, 0Bh
0x180112a1c  mov     dword ptr [r13+14h], 0
0x180112a24  mov     dword ptr [r13+18h], 1770h
0x180112a2c  mov     qword ptr [r13+40h], 0
0x180112a34  mov     rcx, [rsp+1B8h+var_F8]
0x180112a3c  mov     [r13+20h], rcx
0x180112a40  mov     [r13+28h], r14
0x180112a44  mov     rdx, r13
0x180112a47  mov     ecx, eax
0x180112a49  call    BasepCopyFileCallback
0x180112a4e  test    eax, eax
0x180112a50  cmovnz  ebx, edi
0x180112a53  mov     [rsp+1B8h+var_150], ebx
0x180112a57  test    ebx, ebx
0x180112a59  jz      loc_180112913
0x180112a5f  mov     ebx, edi
0x180112a61  mov     [rsp+1B8h+var_150], ebx
0x180112a65  lea     eax, [r12-2]
0x180112a6a  xor     r8d, r8d
0x180112a6d  cmp     eax, edi
0x180112a6f  jbe     short loc_180112A7F
0x180112a71  cmp     [rsp+1B8h+arg_70], r8d
0x180112a79  jz      loc_180112B99
0x180112a7f  mov     rax, [rsp+1B8h+ActivityId]
0x180112a87  test    rax, rax
0x180112a8a  jz      short loc_180112A9A
0x180112a8c  cmp     [rax+20h], r8d
0x180112a90  jnz     short loc_180112A9A
0x180112a92  mov     rcx, rax; ActivityId
0x180112a95  call    BasepBaseCopyStreamStartActivity
0x180112a9a  mov     eax, cs:dword_18039CC08
0x180112aa0  cmp     eax, 5
0x180112aa3  jbe     loc_180112B99
0x180112aa9  mov     rdx, 400000000000h
0x180112ab3  lea     rcx, dword_18039CC08
0x180112aba  call    _tlgKeywordOn
0x180112abf  test    al, al
0x180112ac1  jz      loc_180112B99
0x180112ac7  mov     [rsp+1B8h+var_14C], r12d
0x180112acc  lea     rax, [rsp+1B8h+var_14C]
0x180112ad1  mov     [rsp+1B8h+var_88], rax
0x180112ad9  mov     [rsp+1B8h+var_80], 4
0x180112ae5  mov     eax, [rsp+1B8h+var_158]
0x180112ae9  mov     [rsp+1B8h+var_148], eax
0x180112aed  lea     rax, [rsp+1B8h+var_148]
0x180112af2  mov     [rsp+1B8h+var_78], rax
0x180112afa  mov     [rsp+1B8h+var_70], 4
0x180112b06  mov     eax, [rsp+1B8h+arg_80]
0x180112b0d  mov     [rsp+1B8h+var_144], eax
0x180112b11  lea     rax, [rsp+1B8h+var_144]
0x180112b16  mov     [rsp+1B8h+var_68], rax
0x180112b1e  mov     [rsp+1B8h+var_60], 4
0x180112b2a  mov     eax, [rsp+1B8h+arg_70]
0x180112b31  mov     [rsp+1B8h+var_140], eax
0x180112b35  lea     rax, [rsp+1B8h+var_140]
0x180112b3a  mov     [rsp+1B8h+var_58], rax
0x180112b42  mov     [rsp+1B8h+var_50], 4
0x180112b4e  mov     [rsp+1B8h+var_13C], ebx
0x180112b52  lea     rax, [rsp+1B8h+var_13C]
0x180112b57  mov     [rsp+1B8h+var_48], rax
0x180112b5f  mov     [rsp+1B8h+var_40], 4
0x180112b6b  lea     rax, [rsp+1B8h+var_A8]
0x180112b73  mov     qword ptr [rsp+1B8h+FileAttributes], rax
0x180112b78  mov     [rsp+1B8h+FileInformationClass], 7
0x180112b80  xor     r9d, r9d
0x180112b83  xor     r8d, r8d
0x180112b86  lea     rdx, word_180359156
0x180112b8d  lea     rcx, dword_18039CC08
0x180112b94  call    _tlgWriteTransfer_EventWriteTransfer
0x180112b99  mov     eax, ebx
0x180112b9b  mov     rcx, [rsp+1B8h+var_38]
0x180112ba3  xor     rcx, rsp; StackCookie
0x180112ba6  call    __security_check_cookie
0x180112bab  mov     rbx, [rsp+1B8h+arg_0]
  ... truncated ...
```
