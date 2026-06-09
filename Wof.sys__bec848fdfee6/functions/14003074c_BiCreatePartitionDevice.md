# BiCreatePartitionDevice

- ea: `0x14003074c`
- end: `0x140030b83`
- name: `BiCreatePartitionDevice`
- size: `1079`
- prototype: `__int64 __fastcall(PCWSTR SourceString, int, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002fce8`

## callees

- `0x14000da0d`
- `0x14000da31`
- `0x14000da55`
- `0x14000db18`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002fce8`
- `0x140030578`
- `0x14003074c`
- `0x140030b8c`
- `0x140030e64`
- `0x140031380`
- `0x140031520`
- `0x1400317c4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140030a45`
- `ntoskrnl!ExAllocatePool2` at `0x140030a45`
- `ntoskrnl!wcschr` at `0x14003087e`
- `ntoskrnl!wcschr` at `0x14003087e`
- `ntoskrnl!_wcsnicmp` at `0x140030865`
- `ntoskrnl!_wcsnicmp` at `0x1400308c4`
- `ntoskrnl!_wcsnicmp` at `0x140030865`
- `ntoskrnl!_wcsnicmp` at `0x1400308c4`

## pseudocode

```c
__int64 __fastcall BiCreatePartitionDevice(PCWSTR SourceString, int a2, _QWORD *a3, _DWORD *a4)
{
  PVOID v5; // r12
  WCHAR *v6; // r14
  int v7; // esi
  PVOID v8; // r15
  int PhysicalDriveName; // eax
  int DriveLayoutInformation; // ebx
  char *v11; // rdi
  const wchar_t *PartitionVhdFilePath; // rax
  wchar_t *v13; // rax
  wchar_t *v14; // rbx
  void *v15; // rax
  int v16; // eax
  __int64 v17; // xmm0_8
  unsigned int v18; // r13d
  __int64 v19; // rdx
  _OWORD *Pool2; // rax
  _OWORD *v21; // rsi
  size_t v22; // r8
  __int128 v23; // xmm1
  int v24; // eax
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  _DWORD *v27; // rcx
  char v29; // [rsp+30h] [rbp-D0h]
  unsigned int v30; // [rsp+34h] [rbp-CCh] BYREF
  size_t Size; // [rsp+38h] [rbp-C8h]
  PVOID v32; // [rsp+40h] [rbp-C0h]
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  int v34; // [rsp+50h] [rbp-B0h]
  PVOID v35; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v38; // [rsp+70h] [rbp-90h]
  _DWORD *v39; // [rsp+78h] [rbp-88h]
  _OWORD v40[5]; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+100h] [rbp+0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v44[9]; // [rsp+120h] [rbp+20h] BYREF

  v38 = a3;
  v34 = a2;
  v39 = a4;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(v44, 0, sizeof(v44));
  v32 = 0;
  FileHandle = 0;
  DestinationString = 0;
  Src = 0;
  v5 = 0;
  P = 0;
  v6 = 0;
  LODWORD(Size) = 0;
  v7 = 0;
  v30 = 0;
  v8 = 0;
  v35 = 0;
  memset(v40, 0, 0x48u);
  if ( (int)BiGetDriveLayoutInformation(SourceString) < 0 )
  {
    PhysicalDriveName = BiGetPhysicalDriveName(SourceString, &v35);
    v8 = v35;
    DriveLayoutInformation = PhysicalDriveName;
    if ( PhysicalDriveName < 0 )
      goto LABEL_43;
    DriveLayoutInformation = BiGetDriveLayoutInformation((PCWSTR)v35);
    if ( DriveLayoutInformation < 0 )
      goto LABEL_43;
  }
  v29 = 0;
  v11 = (char *)v32;
  if ( (v34 & 0x40) == 0 )
  {
    PartitionVhdFilePath = (const wchar_t *)BiGetPartitionVhdFilePath(SourceString);
    v6 = (WCHAR *)PartitionVhdFilePath;
    if ( PartitionVhdFilePath )
    {
      if ( !_wcsnicmp(PartitionVhdFilePath, L"\\Device\\HarddiskVolume", 0x16u) )
      {
        v13 = wcschr(v6 + 22, 0x5Cu);
        v14 = v13;
        if ( v13 )
        {
          *v13 = 0;
          v15 = (void *)BiGetPartitionVhdFilePath(v6);
          *v14 = 92;
          if ( v15 )
            ExFreePoolWithTag_0(v15, 0x4B444342u);
        }
      }
      if ( _wcsnicmp(v6, L"\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab79-03cfa2f6b750}", 0x35u) )
      {
        v16 = BiCreateFileDeviceElement(v6, &P, &v30);
        v5 = P;
        DriveLayoutInformation = v16;
        if ( v16 < 0 )
          goto LABEL_41;
        DriveLayoutInformation = BiConvertNtDeviceToBootEnvironment((__int64)P, v30, 0x40u, &Src);
        if ( DriveLayoutInformation < 0 )
          goto LABEL_41;
      }
      else
      {
        DriveLayoutInformation = BiCreateVhdRamdiskBootDevice(v6, &Src);
        if ( DriveLayoutInformation < 0 )
          goto LABEL_43;
        v29 = 1;
      }
      LODWORD(v40[2]) = 6;
      v7 = *((_DWORD *)Src + 2);
      LODWORD(Size) = v7;
    }
  }
  if ( *(_DWORD *)v11 )
  {
    if ( *(_DWORD *)v11 != 1 )
    {
LABEL_40:
      DriveLayoutInformation = -1073741811;
      goto LABEL_41;
    }
    v17 = *(_QWORD *)(v11 + 12);
    DWORD2(v40[2]) = *((_DWORD *)v11 + 2);
    DWORD1(v40[3]) = *((_DWORD *)v11 + 5);
    DWORD1(v40[2]) = 0;
    *(_QWORD *)((char *)&v40[2] + 12) = v17;
  }
  else
  {
    DWORD2(v40[2]) = *((_DWORD *)v11 + 2);
    DWORD1(v40[2]) = 1;
  }
  RtlInitUnicodeString_0(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  DriveLayoutInformation = ZwOpenFile_0(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( DriveLayoutInformation >= 0 )
  {
    DriveLayoutInformation = BiGetPartitionInformation(FileHandle, *(_DWORD *)v11);
    if ( DriveLayoutInformation >= 0 )
    {
      if ( !LODWORD(v44[0]) )
      {
        *(_QWORD *)&v40[1] = *((_QWORD *)&v44[0] + 1);
LABEL_27:
        v18 = v7 + 56;
        v19 = 72;
        if ( (unsigned int)(v7 + 56) > 0x48 )
          v19 = (unsigned int)(v7 + 56);
        Pool2 = (_OWORD *)ExAllocatePool2(258, v19, 1262764866);
        v21 = Pool2;
        if ( Pool2 )
        {
          v22 = 72;
          if ( v18 > 0x48 )
            v22 = v18;
          memset(Pool2, 0, v22);
          v23 = v40[1];
          v24 = 72;
          LODWORD(v40[0]) = 6;
          if ( v18 > 0x48 )
            v24 = v18;
          DWORD2(v40[0]) = v24;
          *v21 = v40[0];
          v25 = v40[2];
          v21[1] = v23;
          v26 = v40[3];
          v21[2] = v25;
          *(_QWORD *)&v25 = *(_QWORD *)&v40[4];
          v21[3] = v26;
          *((_QWORD *)v21 + 8) = v25;
          if ( v6 )
            memmove((char *)v21 + 56, Src, (unsigned int)Size);
          if ( v29 )
            *((_DWORD *)v21 + 1) |= 8u;
          v27 = v39;
          *v38 = v21;
          *v27 = *((_DWORD *)v11 + 1);
        }
        else
        {
          DriveLayoutInformation = -1073741670;
        }
        goto LABEL_41;
      }
      if ( LODWORD(v44[0]) == 1 )
      {
        v40[1] = v44[3];
        goto LABEL_27;
      }
      goto LABEL_40;
    }
  }
LABEL_41:
  if ( v5 )
    ExFreePoolWithTag_0(v5, 0x4B444342u);
LABEL_43:
  if ( Src )
    ExFreePoolWithTag_0(Src, 0x4B444342u);
  if ( v6 )
    ExFreePoolWithTag_0(v6, 0x4B444342u);
  if ( v8 )
    ExFreePoolWithTag_0(v8, 0x4B444342u);
  if ( FileHandle )
    ZwClose_0(FileHandle);
  return (unsigned int)DriveLayoutInformation;
}

```

## disassembly

```asm
0x14003074c  mov     [rsp-8+arg_8], rbx
0x140030751  push    rbp
0x140030752  push    rsi
0x140030753  push    rdi
0x140030754  push    r12
0x140030756  push    r13
0x140030758  push    r14
0x14003075a  push    r15
0x14003075c  lea     rbp, [rsp-0B0h]
0x140030764  sub     rsp, 1B0h
0x14003076b  xorps   xmm0, xmm0
0x14003076e  mov     [rsp+1E0h+var_170], r8
0x140030773  mov     [rsp+1E0h+var_190], edx
0x140030777  mov     r13, rcx
0x14003077a  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.ObjectName], xmm0
0x14003077e  xor     eax, eax
0x140030780  mov     [rsp+1E0h+var_168], r9
0x140030785  xor     edx, edx; Val
0x140030787  lea     rcx, [rbp+0E0h+var_C0]; void *
0x14003078b  mov     r8d, 90h; Size
0x140030791  movups  xmmword ptr [rbp+0E0h+ObjectAttributes+1Ch], xmm0
0x140030795  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.Length], xmm0
0x140030799  movups  xmmword ptr [rbp+0E0h+IoStatusBlock], xmm0
0x14003079d  call    memset
0x1400307a2  xor     edi, edi
0x1400307a4  lea     rcx, [rbp+0E0h+var_160]; void *
0x1400307a8  xorps   xmm0, xmm0
0x1400307ab  mov     [rsp+1E0h+var_1A0], rdi
0x1400307b0  xor     edx, edx; Val
0x1400307b2  mov     [rsp+1E0h+FileHandle], rdi
0x1400307b7  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x1400307bb  lea     r8d, [rdi+48h]; Size
0x1400307bf  mov     [rsp+1E0h+Src], rdi
0x1400307c4  mov     r12d, edi
0x1400307c7  mov     [rsp+1E0h+P], rdi
0x1400307cc  mov     r14d, edi
0x1400307cf  mov     dword ptr [rsp+1E0h+Size], edi
0x1400307d3  mov     esi, edi
0x1400307d5  mov     [rsp+1E0h+var_1AC], edi
0x1400307d9  mov     r15d, edi
0x1400307dc  mov     [rsp+1E0h+var_188], rdi
0x1400307e1  call    memset
0x1400307e6  lea     rdx, [rsp+1E0h+var_1A0]
0x1400307eb  mov     rcx, r13; SourceString
0x1400307ee  call    BiGetDriveLayoutInformation
0x1400307f3  test    eax, eax
0x1400307f5  jns     short loc_14003082C
0x1400307f7  lea     rdx, [rsp+1E0h+var_188]
0x1400307fc  mov     rcx, r13
0x1400307ff  call    BiGetPhysicalDriveName
0x140030804  mov     r15, [rsp+1E0h+var_188]
0x140030809  mov     ebx, eax
0x14003080b  test    eax, eax
0x14003080d  js      short loc_140030822
0x14003080f  lea     rdx, [rsp+1E0h+var_1A0]
0x140030814  mov     rcx, r15; SourceString
0x140030817  call    BiGetDriveLayoutInformation
0x14003081c  mov     ebx, eax
0x14003081e  test    eax, eax
0x140030820  jns     short loc_14003082C
0x140030822  mov     rdi, [rsp+1E0h+var_1A0]
0x140030827  jmp     loc_140030B0C
0x14003082c  test    byte ptr [rsp+1E0h+var_190], 40h
0x140030831  mov     [rsp+1E0h+var_1B0], dil
0x140030836  mov     rdi, [rsp+1E0h+var_1A0]
0x14003083b  jnz     loc_140030944
0x140030841  mov     rcx, r13; SourceString
0x140030844  call    BiGetPartitionVhdFilePath
0x140030849  mov     r14, rax
0x14003084c  test    rax, rax
0x14003084f  jz      loc_140030944
0x140030855  mov     r8d, 16h; MaxCount
0x14003085b  lea     rdx, aDeviceHarddisk_0; "\\Device\\HarddiskVolume"
0x140030862  mov     rcx, rax; Str1
0x140030865  call    cs:__imp__wcsnicmp
0x14003086c  nop     dword ptr [rax+rax+00h]
0x140030871  test    eax, eax
0x140030873  jnz     short loc_1400308B4
0x140030875  lea     esi, [rax+5Ch]
0x140030878  mov     edx, esi; Ch
0x14003087a  lea     rcx, [r14+2Ch]; Str
0x14003087e  call    cs:__imp_wcschr
0x140030885  nop     dword ptr [rax+rax+00h]
0x14003088a  mov     rbx, rax
0x14003088d  test    rax, rax
0x140030890  jz      short loc_1400308B4
0x140030892  xor     ecx, ecx
0x140030894  mov     [rax], cx
0x140030897  mov     rcx, r14; SourceString
0x14003089a  call    BiGetPartitionVhdFilePath
0x14003089f  mov     [rbx], si
0x1400308a2  test    rax, rax
0x1400308a5  jz      short loc_1400308B4
0x1400308a7  mov     edx, 4B444342h; Tag
0x1400308ac  mov     rcx, rax; P
0x1400308af  call    ExFreePoolWithTag_0
0x1400308b4  mov     r8d, 35h ; '5'; MaxCount
0x1400308ba  lea     rdx, aDeviceRamdiskD; "\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab"...
0x1400308c1  mov     rcx, r14; Str1
0x1400308c4  call    cs:__imp__wcsnicmp
0x1400308cb  nop     dword ptr [rax+rax+00h]
0x1400308d0  mov     rcx, r14; Src
0x1400308d3  test    eax, eax
0x1400308d5  jnz     short loc_1400308F2
0x1400308d7  lea     rdx, [rsp+1E0h+Src]
0x1400308dc  call    BiCreateVhdRamdiskBootDevice
0x1400308e1  mov     ebx, eax
0x1400308e3  test    eax, eax
0x1400308e5  js      loc_140030B0C
0x1400308eb  mov     [rsp+1E0h+var_1B0], 1
0x1400308f0  jmp     short loc_140030931
0x1400308f2  lea     r8, [rsp+1E0h+var_1AC]
0x1400308f7  lea     rdx, [rsp+1E0h+P]
0x1400308fc  call    BiCreateFileDeviceElement
0x140030901  mov     r12, [rsp+1E0h+P]
0x140030906  mov     ebx, eax
0x140030908  test    eax, eax
0x14003090a  js      loc_140030AFA
0x140030910  mov     edx, [rsp+1E0h+var_1AC]
0x140030914  lea     r9, [rsp+1E0h+Src]
0x140030919  mov     r8d, 40h ; '@'
0x14003091f  mov     rcx, r12
0x140030922  call    BiConvertNtDeviceToBootEnvironment
0x140030927  mov     ebx, eax
0x140030929  test    eax, eax
0x14003092b  js      loc_140030AFA
0x140030931  mov     rax, [rsp+1E0h+Src]
0x140030936  mov     dword ptr [rbp+0E0h+var_140], 6
0x14003093d  mov     esi, [rax+8]
0x140030940  mov     dword ptr [rsp+1E0h+Size], esi
0x140030944  mov     eax, [rdi]
0x140030946  test    eax, eax
0x140030948  jnz     short loc_140030959
0x14003094a  mov     eax, [rdi+8]
0x14003094d  mov     dword ptr [rbp+0E0h+var_140+8], eax
0x140030950  mov     dword ptr [rbp+0E0h+var_140+4], 1
0x140030957  jmp     short loc_14003097F
0x140030959  cmp     eax, 1
0x14003095c  jnz     loc_140030AF5
0x140030962  mov     eax, [rdi+8]
0x140030965  movsd   xmm0, qword ptr [rdi+0Ch]
0x14003096a  mov     dword ptr [rbp+0E0h+var_140+8], eax
0x14003096d  mov     eax, [rdi+14h]
0x140030970  mov     [rbp+0E0h+var_12C], eax
0x140030973  mov     dword ptr [rbp+0E0h+var_140+4], 0
0x14003097a  movsd   qword ptr [rbp+0E0h+var_140+0Ch], xmm0
0x14003097f  mov     rdx, r13; SourceString
0x140030982  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x140030986  call    RtlInitUnicodeString_0
0x14003098b  lea     rax, [rbp+0E0h+DestinationString]
0x14003098f  mov     [rsp+1E0h+OpenOptions], 20h ; ' '; OpenOptions
0x140030997  xorps   xmm0, xmm0
0x14003099a  mov     [rbp+0E0h+ObjectAttributes.ObjectName], rax
0x14003099e  lea     r9, [rbp+0E0h+IoStatusBlock]; IoStatusBlock
0x1400309a2  mov     [rbp+0E0h+ObjectAttributes.Length], 30h ; '0'
0x1400309a9  lea     r8, [rbp+0E0h+ObjectAttributes]; ObjectAttributes
0x1400309ad  mov     [rbp+0E0h+ObjectAttributes.RootDirectory], 0
0x1400309b5  mov     edx, 80100000h; DesiredAccess
0x1400309ba  mov     [rbp+0E0h+ObjectAttributes.Attributes], 240h
0x1400309c1  lea     rcx, [rsp+1E0h+FileHandle]; FileHandle
0x1400309c6  mov     [rsp+1E0h+ShareAccess], 3; ShareAccess
0x1400309ce  movdqu  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400309d3  call    ZwOpenFile_0
0x1400309d8  mov     ebx, eax
0x1400309da  test    eax, eax
0x1400309dc  js      loc_140030AFA
0x1400309e2  mov     edx, [rdi]; InputBufferLength
0x1400309e4  lea     r8, [rbp+0E0h+var_C0]
0x1400309e8  mov     rcx, [rsp+1E0h+FileHandle]; FileHandle
0x1400309ed  call    BiGetPartitionInformation
0x1400309f2  mov     ebx, eax
0x1400309f4  test    eax, eax
0x1400309f6  js      loc_140030AFA
0x1400309fc  mov     eax, [rbp+0E0h+var_C0]
0x1400309ff  test    eax, eax
0x140030a01  jnz     short loc_140030A0D
0x140030a03  mov     rax, [rbp+0E0h+var_B8]
0x140030a07  mov     qword ptr [rbp+0E0h+var_150], rax
0x140030a0b  jmp     short loc_140030A26
0x140030a0d  cmp     eax, 1
0x140030a10  jnz     loc_140030AF5
0x140030a16  mov     rax, qword ptr [rbp+0E0h+var_90]
0x140030a1a  mov     qword ptr [rbp+0E0h+var_150], rax
0x140030a1e  mov     rax, qword ptr [rbp+0E0h+var_90+8]
0x140030a22  mov     qword ptr [rbp+0E0h+var_150+8], rax
0x140030a26  mov     ecx, 48h ; 'H'
0x140030a2b  lea     r13d, [rsi+38h]
0x140030a2f  cmp     r13d, ecx
0x140030a32  mov     eax, r13d
0x140030a35  mov     edx, ecx
0x140030a37  mov     r8d, 4B444342h
0x140030a3d  cmova   edx, eax
0x140030a40  mov     ecx, 102h
0x140030a45  call    cs:__imp_ExAllocatePool2
0x140030a4c  nop     dword ptr [rax+rax+00h]
0x140030a51  mov     rsi, rax
0x140030a54  test    rax, rax
0x140030a57  jnz     short loc_140030A63
0x140030a59  mov     ebx, 0C000009Ah
0x140030a5e  jmp     loc_140030AFA
0x140030a63  mov     eax, 48h ; 'H'
0x140030a68  mov     rcx, rsi; void *
0x140030a6b  mov     r8d, eax
0x140030a6e  cmp     r13d, eax
0x140030a71  mov     eax, r13d
0x140030a74  cmova   r8d, eax; Size
0x140030a78  xor     edx, edx; Val
0x140030a7a  call    memset
0x140030a7f  movaps  xmm1, [rbp+0E0h+var_150]
0x140030a83  mov     eax, 48h ; 'H'
0x140030a88  cmp     r13d, eax
0x140030a8b  mov     dword ptr [rbp+0E0h+var_160], 6
0x140030a92  cmova   eax, r13d
0x140030a96  mov     dword ptr [rbp+0E0h+var_160+8], eax
0x140030a99  movaps  xmm0, [rbp+0E0h+var_160]
0x140030a9d  movups  xmmword ptr [rsi], xmm0
0x140030aa0  movaps  xmm0, [rbp+0E0h+var_140]
0x140030aa4  movups  xmmword ptr [rsi+10h], xmm1
0x140030aa8  movaps  xmm1, xmmword ptr [rbp-50h]
0x140030aac  movups  xmmword ptr [rsi+20h], xmm0
0x140030ab0  movsd   xmm0, [rbp+0E0h+var_120]
0x140030ab5  movups  xmmword ptr [rsi+30h], xmm1
0x140030ab9  movsd   qword ptr [rsi+40h], xmm0
0x140030abe  test    r14, r14
0x140030ac1  jz      short loc_140030AD6
0x140030ac3  mov     r8d, dword ptr [rsp+1E0h+Size]; Size
0x140030ac8  lea     rcx, [rsi+38h]; void *
0x140030acc  mov     rdx, [rsp+1E0h+Src]; Src
0x140030ad1  call    memmove
0x140030ad6  cmp     [rsp+1E0h+var_1B0], 0
0x140030adb  jz      short loc_140030AE1
0x140030add  or      dword ptr [rsi+4], 8
0x140030ae1  mov     rax, [rsp+1E0h+var_170]
0x140030ae6  mov     rcx, [rsp+1E0h+var_168]
0x140030aeb  mov     [rax], rsi
0x140030aee  mov     eax, [rdi+4]
0x140030af1  mov     [rcx], eax
0x140030af3  jmp     short loc_140030AFA
0x140030af5  mov     ebx, 0C000000Dh
0x140030afa  test    r12, r12
0x140030afd  jz      short loc_140030B0C
0x140030aff  mov     edx, 4B444342h; Tag
0x140030b04  mov     rcx, r12; P
0x140030b07  call    ExFreePoolWithTag_0
0x140030b0c  mov     rcx, [rsp+1E0h+Src]; P
0x140030b11  test    rcx, rcx
0x140030b14  jz      short loc_140030B20
0x140030b16  mov     edx, 4B444342h; Tag
0x140030b1b  call    ExFreePoolWithTag_0
0x140030b20  test    r14, r14
0x140030b23  jz      short loc_140030B32
0x140030b25  mov     edx, 4B444342h; Tag
0x140030b2a  mov     rcx, r14; P
0x140030b2d  call    ExFreePoolWithTag_0
0x140030b32  test    r15, r15
0x140030b35  jz      short loc_140030B44
0x140030b37  mov     edx, 4B444342h; Tag
0x140030b3c  mov     rcx, r15; P
0x140030b3f  call    ExFreePoolWithTag_0
0x140030b44  mov     rcx, [rsp+1E0h+FileHandle]; Handle
0x140030b49  test    rcx, rcx
0x140030b4c  jz      short loc_140030B53
0x140030b4e  call    ZwClose_0
0x140030b53  test    rdi, rdi
0x140030b56  jz      short loc_140030B65
0x140030b58  mov     edx, 4B444342h; Tag
0x140030b5d  mov     rcx, rdi; P
0x140030b60  call    ExFreePoolWithTag_0
0x140030b65  mov     eax, ebx
0x140030b67  mov     rbx, [rsp+1E0h+arg_8]
0x140030b6f  add     rsp, 1B0h
0x140030b76  pop     r15
0x140030b78  pop     r14
0x140030b7a  pop     r13
0x140030b7c  pop     r12
0x140030b7e  pop     rdi
0x140030b7f  pop     rsi
0x140030b80  pop     rbp
0x140030b81  retn
```
