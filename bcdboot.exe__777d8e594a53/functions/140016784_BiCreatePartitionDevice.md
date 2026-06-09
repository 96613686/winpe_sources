# BiCreatePartitionDevice

- ea: `0x140016784`
- end: `0x140016c09`
- name: `BiCreatePartitionDevice`
- size: `1157`
- prototype: `__int64 __fastcall(PCWSTR SourceString, int, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140015cd8`

## callees

- `0x1400133e4`
- `0x140015cd8`
- `0x1400165b4`
- `0x140016784`
- `0x140016c10`
- `0x1400170dc`
- `0x140017658`
- `0x140017800`
- `0x140017c00`
- `0x1400265e2`
- `0x1400265fa`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1400168a0`
- `msvcrt!_wcsnicmp` at `0x140016915`
- `msvcrt!_wcsnicmp` at `0x1400168a0`
- `msvcrt!_wcsnicmp` at `0x140016915`
- `msvcrt!wcschr` at `0x1400168b1`
- `msvcrt!wcschr` at `0x1400168b1`
- `ntdll!ZwClose` at `0x140016bc9`
- `ntdll!ZwClose` at `0x140016bc9`
- `ntdll!RtlAllocateHeap` at `0x140016a97`
- `ntdll!RtlAllocateHeap` at `0x140016a97`
- `ntdll!RtlFreeHeap` at `0x1400168ff`
- `ntdll!RtlFreeHeap` at `0x140016b5d`
- `ntdll!RtlFreeHeap` at `0x140016b7f`
- `ntdll!RtlFreeHeap` at `0x140016b9c`
- `ntdll!RtlFreeHeap` at `0x140016bb9`
- `ntdll!RtlFreeHeap` at `0x140016be6`
- `ntdll!RtlFreeHeap` at `0x1400168ff`
- `ntdll!RtlFreeHeap` at `0x140016b5d`
- `ntdll!RtlFreeHeap` at `0x140016b7f`
- `ntdll!RtlFreeHeap` at `0x140016b9c`
- `ntdll!RtlFreeHeap` at `0x140016bb9`
- `ntdll!RtlFreeHeap` at `0x140016be6`
- `ntdll!RtlInitUnicodeString` at `0x1400169d0`
- `ntdll!RtlInitUnicodeString` at `0x1400169d0`
- `ntdll!ZwOpenFile` at `0x140016a1e`
- `ntdll!ZwOpenFile` at `0x140016a1e`

## string_xrefs

- `0x1400168dc`: `BiCreatePartitionDevice: NestedVhd detected %ws`

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
  __int64 v11; // rdi
  const wchar_t *PartitionVhdFilePath; // rax
  wchar_t *v13; // rax
  wchar_t *v14; // rbx
  __int64 v15; // rax
  void *v16; // rsi
  int v17; // eax
  __int64 v18; // xmm0_8
  unsigned int v19; // r13d
  SIZE_T v20; // r8
  struct _PEB *v21; // rcx
  _OWORD *Heap; // rax
  _OWORD *v23; // rsi
  size_t v24; // r8
  __int128 v25; // xmm1
  int v26; // eax
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  _DWORD *v29; // rcx
  char v31; // [rsp+30h] [rbp-D0h]
  void *Src; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v33[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+50h] [rbp-B0h]
  PVOID v35; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v38; // [rsp+70h] [rbp-90h]
  _DWORD *v39; // [rsp+78h] [rbp-88h]
  __int128 v40; // [rsp+80h] [rbp-80h] BYREF
  __int128 v41; // [rsp+90h] [rbp-70h]
  __m256i v42; // [rsp+A0h] [rbp-60h]
  __int64 v43; // [rsp+C0h] [rbp-40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+100h] [rbp+0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v47[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v48; // [rsp+128h] [rbp+28h]
  __int128 v49; // [rsp+150h] [rbp+50h]

  v38 = a3;
  v34 = a2;
  v39 = a4;
  v47[1] = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset_0(v47, 0, 0x8Cu);
  FileHandle = 0;
  DestinationString = 0;
  Src = 0;
  v5 = 0;
  P = 0;
  v6 = 0;
  v7 = 0;
  memset(v33, 0, sizeof(v33));
  v8 = 0;
  v35 = 0;
  memset_0(&v40, 0, 0x48u);
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
  v31 = 0;
  v11 = v33[1];
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
          v15 = BiGetPartitionVhdFilePath(v6);
          *v14 = 92;
          v16 = (void *)v15;
          if ( v15 )
          {
            BiLogMessage(3, L"BiCreatePartitionDevice: NestedVhd detected %ws", v15);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
          }
        }
      }
      if ( _wcsnicmp(v6, L"\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab79-03cfa2f6b750}", 0x35u) )
      {
        v17 = BiCreateFileDeviceElement(v6, &P, (unsigned int *)v33);
        v5 = P;
        DriveLayoutInformation = v17;
        if ( v17 < 0 )
          goto LABEL_41;
        DriveLayoutInformation = BiConvertNtDeviceToBootEnvironment((__int64)P, v33[0], 0x40u, &Src);
        if ( DriveLayoutInformation < 0 )
          goto LABEL_41;
      }
      else
      {
        DriveLayoutInformation = BiCreateVhdRamdiskBootDevice(v6, &Src);
        if ( DriveLayoutInformation < 0 )
          goto LABEL_43;
        v31 = 1;
      }
      v42.m256i_i32[0] = 6;
      v7 = *((_DWORD *)Src + 2);
      HIDWORD(v33[0]) = v7;
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
    v18 = *(_QWORD *)(v11 + 12);
    v42.m256i_i32[2] = *(_DWORD *)(v11 + 8);
    v42.m256i_i32[5] = *(_DWORD *)(v11 + 20);
    v42.m256i_i32[1] = 0;
    *(__int64 *)((char *)&v42.m256i_i64[1] + 4) = v18;
  }
  else
  {
    v42.m256i_i32[2] = *(_DWORD *)(v11 + 8);
    v42.m256i_i32[1] = 1;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  DriveLayoutInformation = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( DriveLayoutInformation >= 0 )
  {
    DriveLayoutInformation = BiGetPartitionInformation(FileHandle, *(_DWORD *)v11);
    if ( DriveLayoutInformation >= 0 )
    {
      if ( !v47[0] )
      {
        *(_QWORD *)&v41 = v48;
LABEL_27:
        v19 = v7 + 56;
        v20 = 72;
        v21 = NtCurrentPeb();
        if ( (unsigned int)(v7 + 56) > 0x48 )
          v20 = (unsigned int)(v7 + 56);
        Heap = RtlAllocateHeap(v21->ProcessHeap, 0, v20);
        v23 = Heap;
        if ( Heap )
        {
          v24 = 72;
          if ( v19 > 0x48 )
            v24 = v19;
          memset_0(Heap, 0, v24);
          v25 = v41;
          v26 = 72;
          LODWORD(v40) = 6;
          if ( v19 > 0x48 )
            v26 = v19;
          DWORD2(v40) = v26;
          *v23 = v40;
          v27 = *(_OWORD *)v42.m256i_i8;
          v23[1] = v25;
          v28 = *(_OWORD *)&v42.m256i_u64[2];
          v23[2] = v27;
          *(_QWORD *)&v27 = v43;
          v23[3] = v28;
          *((_QWORD *)v23 + 8) = v27;
          if ( v6 )
            memcpy_0((char *)v23 + 56, Src, HIDWORD(v33[0]));
          if ( v31 )
            *((_DWORD *)v23 + 1) |= 8u;
          v29 = v39;
          *v38 = v23;
          *v29 = *(_DWORD *)(v11 + 4);
        }
        else
        {
          DriveLayoutInformation = -1073741670;
        }
        goto LABEL_41;
      }
      if ( v47[0] == 1 )
      {
        v41 = v49;
        goto LABEL_27;
      }
      goto LABEL_40;
    }
  }
LABEL_41:
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
LABEL_43:
  if ( Src )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Src);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)DriveLayoutInformation;
}

```

## disassembly

```asm
0x140016784  mov     [rsp-8+arg_8], rbx
0x140016789  push    rbp
0x14001678a  push    rsi
0x14001678b  push    rdi
0x14001678c  push    r12
0x14001678e  push    r13
0x140016790  push    r14
0x140016792  push    r15
0x140016794  lea     rbp, [rsp-0B0h]
0x14001679c  sub     rsp, 1B0h
0x1400167a3  xorps   xmm0, xmm0
0x1400167a6  mov     [rsp+1E0h+var_170], r8
0x1400167ab  mov     [rsp+1E0h+var_190], edx
0x1400167af  mov     r13, rcx
0x1400167b2  xor     eax, eax
0x1400167b4  mov     [rsp+1E0h+var_168], r9
0x1400167b9  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.ObjectName], xmm0
0x1400167bd  xor     edx, edx; Val
0x1400167bf  mov     [rbp+0E0h+var_BC], eax
0x1400167c2  mov     r8d, 8Ch; Size
0x1400167c8  lea     rcx, [rbp+0E0h+var_C0]; void *
0x1400167cc  movups  xmmword ptr [rbp+0E0h+ObjectAttributes+1Ch], xmm0
0x1400167d0  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.Length], xmm0
0x1400167d4  movups  xmmword ptr [rbp+0E0h+IoStatusBlock], xmm0
0x1400167d8  call    memset_0
0x1400167dd  xor     edi, edi
0x1400167df  lea     rcx, [rbp+0E0h+var_160]; void *
0x1400167e3  xorps   xmm0, xmm0
0x1400167e6  mov     qword ptr [rsp+1E0h+Size+4], rdi
0x1400167eb  xor     edx, edx; Val
0x1400167ed  mov     [rsp+1E0h+FileHandle], rdi
0x1400167f2  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x1400167f6  lea     r8d, [rdi+48h]; Size
0x1400167fa  mov     [rsp+1E0h+Src], rdi
0x1400167ff  mov     r12d, edi
0x140016802  mov     [rsp+1E0h+P], rdi
0x140016807  mov     r14d, edi
0x14001680a  mov     dword ptr [rsp+1E0h+Size], edi
0x14001680e  mov     esi, edi
0x140016810  mov     [rsp+1E0h+var_1A0], edi
0x140016814  mov     r15d, edi
0x140016817  mov     [rsp+1E0h+var_188], rdi
0x14001681c  call    memset_0
0x140016821  lea     rdx, [rsp+1E0h+Size+4]
0x140016826  mov     rcx, r13; SourceString
0x140016829  call    BiGetDriveLayoutInformation
0x14001682e  test    eax, eax
0x140016830  jns     short loc_140016867
0x140016832  lea     rdx, [rsp+1E0h+var_188]
0x140016837  mov     rcx, r13
0x14001683a  call    BiGetPhysicalDriveName
0x14001683f  mov     r15, [rsp+1E0h+var_188]
0x140016844  mov     ebx, eax
0x140016846  test    eax, eax
0x140016848  js      short loc_14001685D
0x14001684a  lea     rdx, [rsp+1E0h+Size+4]
0x14001684f  mov     rcx, r15; SourceString
0x140016852  call    BiGetDriveLayoutInformation
0x140016857  mov     ebx, eax
0x140016859  test    eax, eax
0x14001685b  jns     short loc_140016867
0x14001685d  mov     rdi, qword ptr [rsp+1E0h+Size+4]
0x140016862  jmp     loc_140016B63
0x140016867  test    byte ptr [rsp+1E0h+var_190], 40h
0x14001686c  mov     [rsp+1E0h+var_1B0], dil
0x140016871  mov     rdi, qword ptr [rsp+1E0h+Size+4]
0x140016876  jnz     loc_14001698F
0x14001687c  mov     rcx, r13; SourceString
0x14001687f  call    BiGetPartitionVhdFilePath
0x140016884  mov     r14, rax
0x140016887  test    rax, rax
0x14001688a  jz      loc_14001698F
0x140016890  mov     r8d, 16h; MaxCount
0x140016896  lea     rdx, aDeviceHarddisk_1; "\\Device\\HarddiskVolume"
0x14001689d  mov     rcx, rax; String1
0x1400168a0  call    cs:__imp__wcsnicmp
0x1400168a6  test    eax, eax
0x1400168a8  jnz     short loc_140016905
0x1400168aa  lea     edx, [rax+5Ch]; Ch
0x1400168ad  lea     rcx, [r14+2Ch]; Str
0x1400168b1  call    cs:__imp_wcschr
0x1400168b7  mov     rbx, rax
0x1400168ba  test    rax, rax
0x1400168bd  jz      short loc_140016905
0x1400168bf  xor     ecx, ecx
0x1400168c1  mov     [rax], cx
0x1400168c4  mov     rcx, r14; SourceString
0x1400168c7  call    BiGetPartitionVhdFilePath
0x1400168cc  mov     word ptr [rbx], 5Ch ; '\'
0x1400168d1  mov     rsi, rax
0x1400168d4  test    rax, rax
0x1400168d7  jz      short loc_140016905
0x1400168d9  mov     r8, rax
0x1400168dc  lea     rdx, aBicreatepartit; "BiCreatePartitionDevice: NestedVhd dete"...
0x1400168e3  mov     ecx, 3
0x1400168e8  call    BiLogMessage
0x1400168ed  mov     rcx, gs:60h
0x1400168f6  mov     r8, rsi; P
0x1400168f9  xor     edx, edx; Flags
0x1400168fb  mov     rcx, [rcx+30h]; HeapHandle
0x1400168ff  call    cs:__imp_RtlFreeHeap
0x140016905  mov     r8d, 35h ; '5'; MaxCount
0x14001690b  lea     rdx, aDeviceRamdiskD; "\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab"...
0x140016912  mov     rcx, r14; String1
0x140016915  call    cs:__imp__wcsnicmp
0x14001691b  mov     rcx, r14; Src
0x14001691e  test    eax, eax
0x140016920  jnz     short loc_14001693D
0x140016922  lea     rdx, [rsp+1E0h+Src]
0x140016927  call    BiCreateVhdRamdiskBootDevice
0x14001692c  mov     ebx, eax
0x14001692e  test    eax, eax
0x140016930  js      loc_140016B63
0x140016936  mov     [rsp+1E0h+var_1B0], 1
0x14001693b  jmp     short loc_14001697C
0x14001693d  lea     r8, [rsp+1E0h+var_1A0]
0x140016942  lea     rdx, [rsp+1E0h+P]
0x140016947  call    BiCreateFileDeviceElement
0x14001694c  mov     r12, [rsp+1E0h+P]
0x140016951  mov     ebx, eax
0x140016953  test    eax, eax
0x140016955  js      loc_140016B46
0x14001695b  mov     edx, [rsp+1E0h+var_1A0]
0x14001695f  lea     r9, [rsp+1E0h+Src]
0x140016964  mov     r8d, 40h ; '@'
0x14001696a  mov     rcx, r12
0x14001696d  call    BiConvertNtDeviceToBootEnvironment
0x140016972  mov     ebx, eax
0x140016974  test    eax, eax
0x140016976  js      loc_140016B46
0x14001697c  mov     rax, [rsp+1E0h+Src]
0x140016981  mov     dword ptr [rbp+0E0h+var_140], 6
0x140016988  mov     esi, [rax+8]
0x14001698b  mov     dword ptr [rsp+1E0h+Size], esi
0x14001698f  cmp     dword ptr [rdi], 0
0x140016992  jnz     short loc_1400169A3
0x140016994  mov     eax, [rdi+8]
0x140016997  mov     dword ptr [rbp+0E0h+var_140+8], eax
0x14001699a  mov     dword ptr [rbp+0E0h+var_140+4], 1
0x1400169a1  jmp     short loc_1400169C9
0x1400169a3  cmp     dword ptr [rdi], 1
0x1400169a6  jnz     loc_140016B41
0x1400169ac  mov     eax, [rdi+8]
0x1400169af  movsd   xmm0, qword ptr [rdi+0Ch]
0x1400169b4  mov     dword ptr [rbp+0E0h+var_140+8], eax
0x1400169b7  mov     eax, [rdi+14h]
0x1400169ba  mov     [rbp+0E0h+var_12C], eax
0x1400169bd  mov     dword ptr [rbp+0E0h+var_140+4], 0
0x1400169c4  movsd   qword ptr [rbp+0E0h+var_140+0Ch], xmm0
0x1400169c9  mov     rdx, r13; SourceString
0x1400169cc  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x1400169d0  call    cs:__imp_RtlInitUnicodeString
0x1400169d6  lea     rax, [rbp+0E0h+DestinationString]
0x1400169da  mov     [rsp+1E0h+OpenOptions], 20h ; ' '; OpenOptions
0x1400169e2  xorps   xmm0, xmm0
0x1400169e5  mov     [rbp+0E0h+ObjectAttributes.ObjectName], rax
0x1400169e9  lea     r9, [rbp+0E0h+IoStatusBlock]; IoStatusBlock
0x1400169ed  mov     [rbp+0E0h+ObjectAttributes.Length], 30h ; '0'
0x1400169f4  lea     r8, [rbp+0E0h+ObjectAttributes]; ObjectAttributes
0x1400169f8  mov     [rbp+0E0h+ObjectAttributes.RootDirectory], 0
0x140016a00  mov     edx, 80100000h; DesiredAccess
0x140016a05  mov     [rbp+0E0h+ObjectAttributes.Attributes], 40h ; '@'
0x140016a0c  lea     rcx, [rsp+1E0h+FileHandle]; FileHandle
0x140016a11  mov     [rsp+1E0h+ShareAccess], 3; ShareAccess
0x140016a19  movdqu  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140016a1e  call    cs:__imp_ZwOpenFile
0x140016a24  mov     ebx, eax
0x140016a26  test    eax, eax
0x140016a28  js      loc_140016B46
0x140016a2e  mov     edx, [rdi]; InputBufferLength
0x140016a30  lea     r8, [rbp+0E0h+var_C0]
0x140016a34  mov     rcx, [rsp+1E0h+FileHandle]; FileHandle
0x140016a39  call    BiGetPartitionInformation
0x140016a3e  mov     ebx, eax
0x140016a40  test    eax, eax
0x140016a42  js      loc_140016B46
0x140016a48  mov     eax, [rbp+0E0h+var_C0]
0x140016a4b  test    eax, eax
0x140016a4d  jnz     short loc_140016A59
0x140016a4f  mov     rax, [rbp+0E0h+var_B8]
0x140016a53  mov     qword ptr [rbp+0E0h+var_150], rax
0x140016a57  jmp     short loc_140016A72
0x140016a59  cmp     eax, 1
0x140016a5c  jnz     loc_140016B41
0x140016a62  mov     rax, qword ptr [rbp+0E0h+var_90]
0x140016a66  mov     qword ptr [rbp+0E0h+var_150], rax
0x140016a6a  mov     rax, qword ptr [rbp+0E0h+var_90+8]
0x140016a6e  mov     qword ptr [rbp+0E0h+var_150+8], rax
0x140016a72  mov     ecx, 48h ; 'H'
0x140016a77  lea     r13d, [rsi+38h]
0x140016a7b  mov     r8d, ecx
0x140016a7e  mov     eax, r13d
0x140016a81  cmp     r13d, ecx
0x140016a84  mov     rcx, gs:60h
0x140016a8d  cmova   r8d, eax; Size
0x140016a91  xor     edx, edx; Flags
0x140016a93  mov     rcx, [rcx+30h]; HeapHandle
0x140016a97  call    cs:__imp_RtlAllocateHeap
0x140016a9d  mov     rsi, rax
0x140016aa0  test    rax, rax
0x140016aa3  jnz     short loc_140016AAF
0x140016aa5  mov     ebx, 0C000009Ah
0x140016aaa  jmp     loc_140016B46
0x140016aaf  mov     eax, 48h ; 'H'
0x140016ab4  mov     rcx, rsi; void *
0x140016ab7  mov     r8d, eax
0x140016aba  cmp     r13d, eax
0x140016abd  mov     eax, r13d
0x140016ac0  cmova   r8d, eax; Size
0x140016ac4  xor     edx, edx; Val
0x140016ac6  call    memset_0
0x140016acb  movaps  xmm1, [rbp+0E0h+var_150]
0x140016acf  mov     eax, 48h ; 'H'
0x140016ad4  cmp     r13d, eax
0x140016ad7  mov     dword ptr [rbp+0E0h+var_160], 6
0x140016ade  cmova   eax, r13d
0x140016ae2  mov     dword ptr [rbp+0E0h+var_160+8], eax
0x140016ae5  movaps  xmm0, [rbp+0E0h+var_160]
0x140016ae9  movups  xmmword ptr [rsi], xmm0
0x140016aec  movaps  xmm0, [rbp+0E0h+var_140]
0x140016af0  movups  xmmword ptr [rsi+10h], xmm1
0x140016af4  movaps  xmm1, xmmword ptr [rbp-50h]
0x140016af8  movups  xmmword ptr [rsi+20h], xmm0
0x140016afc  movsd   xmm0, [rbp+0E0h+var_120]
0x140016b01  movups  xmmword ptr [rsi+30h], xmm1
0x140016b05  movsd   qword ptr [rsi+40h], xmm0
0x140016b0a  test    r14, r14
0x140016b0d  jz      short loc_140016B22
0x140016b0f  mov     r8d, dword ptr [rsp+1E0h+Size]; Size
0x140016b14  lea     rcx, [rsi+38h]; void *
0x140016b18  mov     rdx, [rsp+1E0h+Src]; Src
0x140016b1d  call    memcpy_0
0x140016b22  cmp     [rsp+1E0h+var_1B0], 0
0x140016b27  jz      short loc_140016B2D
0x140016b29  or      dword ptr [rsi+4], 8
0x140016b2d  mov     rax, [rsp+1E0h+var_170]
0x140016b32  mov     rcx, [rsp+1E0h+var_168]
0x140016b37  mov     [rax], rsi
0x140016b3a  mov     eax, [rdi+4]
0x140016b3d  mov     [rcx], eax
0x140016b3f  jmp     short loc_140016B46
0x140016b41  mov     ebx, 0C000000Dh
0x140016b46  test    r12, r12
0x140016b49  jz      short loc_140016B63
0x140016b4b  mov     rcx, gs:60h
0x140016b54  mov     r8, r12; P
0x140016b57  xor     edx, edx; Flags
0x140016b59  mov     rcx, [rcx+30h]; HeapHandle
0x140016b5d  call    cs:__imp_RtlFreeHeap
0x140016b63  cmp     [rsp+1E0h+Src], 0
0x140016b69  jz      short loc_140016B85
0x140016b6b  mov     rcx, gs:60h
0x140016b74  xor     edx, edx; Flags
0x140016b76  mov     r8, [rsp+1E0h+Src]; P
0x140016b7b  mov     rcx, [rcx+30h]; HeapHandle
0x140016b7f  call    cs:__imp_RtlFreeHeap
0x140016b85  test    r14, r14
0x140016b88  jz      short loc_140016BA2
0x140016b8a  mov     rcx, gs:60h
0x140016b93  mov     r8, r14; P
0x140016b96  xor     edx, edx; Flags
0x140016b98  mov     rcx, [rcx+30h]; HeapHandle
0x140016b9c  call    cs:__imp_RtlFreeHeap
0x140016ba2  test    r15, r15
0x140016ba5  jz      short loc_140016BBF
0x140016ba7  mov     rcx, gs:60h
0x140016bb0  mov     r8, r15; P
0x140016bb3  xor     edx, edx; Flags
0x140016bb5  mov     rcx, [rcx+30h]; HeapHandle
0x140016bb9  call    cs:__imp_RtlFreeHeap
0x140016bbf  mov     rcx, [rsp+1E0h+FileHandle]; Handle
0x140016bc4  test    rcx, rcx
0x140016bc7  jz      short loc_140016BCF
0x140016bc9  call    cs:__imp_ZwClose
0x140016bcf  test    rdi, rdi
0x140016bd2  jz      short loc_140016BEC
0x140016bd4  mov     rcx, gs:60h
0x140016bdd  mov     r8, rdi; P
0x140016be0  xor     edx, edx; Flags
0x140016be2  mov     rcx, [rcx+30h]; HeapHandle
0x140016be6  call    cs:__imp_RtlFreeHeap
0x140016bec  mov     eax, ebx
0x140016bee  mov     rbx, [rsp+1E0h+arg_8]
0x140016bf6  add     rsp, 1B0h
0x140016bfd  pop     r15
0x140016bff  pop     r14
0x140016c01  pop     r13
0x140016c03  pop     r12
0x140016c05  pop     rdi
0x140016c06  pop     rsi
0x140016c07  pop     rbp
0x140016c08  retn
```
