# UlQueryDirectory

- ea: `0x1400ff308`
- end: `0x1400ff7f9`
- name: `UlQueryDirectory`
- size: `1265`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14005aeb0`
- `0x140100fd0`

## callees

- `0x14002a240`
- `0x1400afbe0`
- `0x1400ff308`
- `0x140167810`
- `0x1401c6e34`
- `0x1401ceeb4`
- `0x1401cf2b0`
- `0x1401cf328`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x1400ff428`
- `ntoskrnl!ZwCreateFile` at `0x1400ff428`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400ff541`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400ff6c5`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400ff541`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400ff6c5`
- `ntoskrnl!wcsstr` at `0x1400ff5bb`
- `ntoskrnl!wcsstr` at `0x1400ff5bb`
- `ntoskrnl!isdigit` at `0x1400ff5e1`
- `ntoskrnl!isdigit` at `0x1400ff5e1`
- `ntoskrnl!ZwClose` at `0x1400ff7ca`
- `ntoskrnl!ZwClose` at `0x1400ff7ca`
- `ntoskrnl!ExAllocatePool3` at `0x1400ff4e3`
- `ntoskrnl!ExAllocatePool3` at `0x1400ff4e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ff786`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ff786`

## pseudocode

```c
__int64 __fastcall UlQueryDirectory(
        struct _UNICODE_STRING *a1,
        wchar_t *a2,
        __int64 a3,
        wchar_t *a4,
        __int64 a5,
        _QWORD *a6)
{
  __int64 *p_Buffer; // rsi
  wchar_t v10; // bx
  __int64 v11; // r15
  __int64 v12; // rax
  NTSTATUS v13; // eax
  int v14; // edi
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned __int16 *Pool3; // rdi
  NTSTATUS v18; // eax
  int v19; // r8d
  NTSTATUS v20; // ebx
  unsigned int v21; // r13d
  unsigned __int64 v22; // r14
  __int64 v23; // rbx
  unsigned __int16 *v24; // r12
  unsigned __int64 v25; // rcx
  unsigned __int16 v26; // ax
  wchar_t *v27; // rax
  bool v28; // r12
  __int64 v29; // rax
  NTSTATUS v30; // eax
  int v31; // edx
  int v32; // r8d
  _DWORD *v33; // rcx
  __int64 CreateDisposition; // [rsp+38h] [rbp-C8h]
  __int64 CreateDispositiona; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v37; // [rsp+60h] [rbp-A0h]
  bool v38; // [rsp+64h] [rbp-9Ch]
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  PVOID FileInformation; // [rsp+78h] [rbp-88h]
  size_t pcchRemaining; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *SubStr; // [rsp+98h] [rbp-68h]
  __int64 v45; // [rsp+A0h] [rbp-60h]
  NTSTRSAFE_PWSTR v46; // [rsp+A8h] [rbp-58h]
  struct _UNICODE_STRING *v47; // [rsp+B0h] [rbp-50h]
  __int64 v48; // [rsp+B8h] [rbp-48h]
  _QWORD *v49; // [rsp+C0h] [rbp-40h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t pszDest; // [rsp+110h] [rbp+10h] BYREF
  char v53; // [rsp+112h] [rbp+12h] BYREF

  v48 = a5;
  v49 = a6;
  SubStr = a4;
  v45 = a3;
  FileHandle = 0;
  v46 = a2;
  v47 = a1;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileName = 0;
  p_Buffer = (__int64 *)&a1->Buffer;
  if ( (BYTE9(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_S(1291, 26, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids, *p_Buffer);
  v10 = a2[1];
  v11 = -1;
  a2[1] = 0;
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(*p_Buffer + 2 * v12) );
  a1->Length = 2 * v12;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = ZwCreateFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x21u, 0, 0);
  a2[1] = v10;
  v14 = v13;
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(*p_Buffer + 2 * v15) );
  a1->Length = 2 * v15;
  if ( v14 < 0 )
    goto LABEL_42;
  FileName.Buffer = (PWSTR)&v53;
  LODWORD(CreateDisposition) = 60;
  RtlStringCchPrintfExW(&pszDest, 0x21u, 0, &pcchRemaining, 0, L"%s%c.%s", v45, CreateDisposition, a4 + 1);
  v16 = -1;
  do
    ++v16;
  while ( FileName.Buffer[v16] );
  FileName.Length = 2 * v16;
  FileName.MaximumLength = 2 * v16;
  Pool3 = (unsigned __int16 *)ExAllocatePool3(66, 4098, 1196190805, UxLowPriorityPool, 1);
  FileInformation = Pool3;
  if ( !Pool3 )
  {
    v14 = -1073741670;
LABEL_42:
    if ( (BYTE9(xmmword_1401A2C90) & 8) != 0 )
      WPP_SF_dS(779, 29, (unsigned int)WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids, v14, *p_Buffer);
    goto LABEL_44;
  }
  v18 = ZwQueryDirectoryFile(
          FileHandle,
          0,
          0,
          0,
          &IoStatusBlock,
          Pool3,
          0xFFEu,
          FileDirectoryInformation,
          0,
          &FileName,
          1u);
  v20 = v18;
  if ( v18 >= 0 )
  {
    v38 = 0;
    v21 = 1;
    v22 = 1;
    v40 = 1;
    v23 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        v24 = Pool3 + 32;
        v25 = (unsigned __int64)*((unsigned int *)Pool3 + 15) >> 1;
        v26 = Pool3[v25 + 32];
        Pool3[v25 + 32] = 0;
        v37 = v26;
        v27 = wcsstr(Pool3 + 32, SubStr);
        pcchRemaining = (size_t)v27;
        if ( v27 )
        {
          *v27 = 0;
          while ( *v24 )
          {
            if ( isdigit(*(unsigned __int8 *)v24) )
            {
              if ( (int)HttpStringToULongLong(1, v24, (__int64)(pcchRemaining - (_QWORD)v24) >> 1, 0, 10, 0, &v40) < 0
                || (v22 = v40, v40 > 0xFFFFFF) )
              {
                v22 = 0;
                v40 = 0;
              }
              break;
            }
            ++v24;
          }
        }
        Pool3[((unsigned __int64)*((unsigned int *)Pool3 + 15) >> 1) + 32] = v37;
        if ( v22 < v21 )
        {
          v28 = v38;
        }
        else
        {
          v21 = v22;
          v23 = *((_QWORD *)Pool3 + 5);
          v28 = (*((_DWORD *)Pool3 + 14) & 0x10) != 0;
          v38 = v28;
        }
        v29 = *(unsigned int *)Pool3;
        if ( !(_DWORD)v29 )
          break;
        Pool3 = (unsigned __int16 *)((char *)Pool3 + v29);
      }
      v30 = ZwQueryDirectoryFile(
              FileHandle,
              0,
              0,
              0,
              &IoStatusBlock,
              FileInformation,
              0x1000u,
              FileDirectoryInformation,
              0,
              0,
              0);
      v14 = v30;
      if ( v30 == -2147483642 )
        break;
      if ( v30 < 0 )
        goto LABEL_41;
      Pool3 = (unsigned __int16 *)FileInformation;
    }
    v14 = 0;
    if ( v28 )
    {
      ++v21;
      v23 = 0;
    }
    LODWORD(CreateDispositiona) = v21;
    RtlStringCchPrintfExW(v46, 0x21u, 0, &pcchRemaining, 0, L"%s%d.%s", v45, CreateDispositiona, SubStr + 1);
    do
      ++v11;
    while ( *(_WORD *)(*p_Buffer + 2 * v11) );
    v33 = (_DWORD *)v48;
    v47->Length = 2 * v11;
    *v33 = v21 + 1;
    *v49 = v23;
    if ( (BYTE9(xmmword_1401A2CA0) & 8) != 0 )
      WPP_SF_SI((_DWORD)v33, v31, v32, *p_Buffer, v23);
  }
  else
  {
    if ( (BYTE9(xmmword_1401A2C90) & 8) != 0 )
      WPP_SF_dSS(*p_Buffer, 0, v19, v18, *p_Buffer, (__int64)FileName.Buffer);
    v14 = 0;
    if ( v20 != -1073741809 )
      v14 = v20;
  }
LABEL_41:
  ExFreePoolWithTag(FileInformation, 0);
  if ( v14 < 0 )
    goto LABEL_42;
LABEL_44:
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400ff308  push    rbp
0x1400ff30a  push    rbx
0x1400ff30b  push    rsi
0x1400ff30c  push    rdi
0x1400ff30d  push    r12
0x1400ff30f  push    r13
0x1400ff311  push    r14
0x1400ff313  push    r15
0x1400ff315  lea     rbp, [rsp-78h]
0x1400ff31a  sub     rsp, 178h
0x1400ff321  mov     rax, cs:__security_cookie
0x1400ff328  xor     rax, rsp
0x1400ff32b  mov     [rbp+0B0h+var_50], rax
0x1400ff32f  mov     rax, [rbp+0B0h+arg_20]
0x1400ff336  xorps   xmm0, xmm0
0x1400ff339  mov     [rbp+0B0h+var_F8], rax
0x1400ff33d  xorps   xmm1, xmm1
0x1400ff340  mov     rax, [rbp+0B0h+arg_28]
0x1400ff347  mov     r13, r9
0x1400ff34a  mov     [rbp+0B0h+var_F0], rax
0x1400ff34e  mov     r14, rdx
0x1400ff351  xor     eax, eax
0x1400ff353  mov     [rbp+0B0h+SubStr], r9
0x1400ff357  xor     edi, edi
0x1400ff359  mov     [rbp+0B0h+var_110], r8
0x1400ff35d  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.ObjectName], xmm0
0x1400ff361  mov     [rsp+1B0h+FileHandle], rdi
0x1400ff366  mov     r12, rcx
0x1400ff369  mov     [rbp+0B0h+var_108], rdx
0x1400ff36d  mov     [rbp+0B0h+var_100], rcx
0x1400ff371  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.Length], xmm0
0x1400ff375  movups  xmmword ptr [rbp+0B0h+ObjectAttributes+1Ch], xmm0
0x1400ff379  movups  xmmword ptr [rbp+0B0h+IoStatusBlock], xmm0
0x1400ff37d  movups  xmmword ptr [rbp+0B0h+FileName.Length], xmm1
0x1400ff381  test    byte ptr cs:xmmword_1401A2CA0+9, 8
0x1400ff388  lea     rsi, [rcx+8]
0x1400ff38c  jz      short loc_1400FF3A5
0x1400ff38e  mov     r9, [rsi]
0x1400ff391  lea     edx, [rax+1Ah]
0x1400ff394  mov     ecx, 50Bh
0x1400ff399  lea     r8, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids
0x1400ff3a0  call    WPP_SF_S
0x1400ff3a5  movzx   ebx, word ptr [r14+2]
0x1400ff3aa  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400ff3ae  mov     [r14+2], di
0x1400ff3b3  mov     rax, r15
0x1400ff3b6  mov     rcx, [rsi]
0x1400ff3b9  inc     rax
0x1400ff3bc  cmp     [rcx+rax*2], di
0x1400ff3c0  jnz     short loc_1400FF3B9
0x1400ff3c2  mov     [rsp+1B0h+EaLength], edi; EaLength
0x1400ff3c6  lea     r9, [rbp+0B0h+IoStatusBlock]; IoStatusBlock
0x1400ff3ca  mov     [rsp+1B0h+EaBuffer], rdi; EaBuffer
0x1400ff3cf  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x1400ff3d3  mov     [rsp+1B0h+CreateOptions], 21h ; '!'; CreateOptions
0x1400ff3db  lea     rcx, [rsp+1B0h+FileHandle]; FileHandle
0x1400ff3e0  mov     dword ptr [rsp+1B0h+CreateDisposition], 1; CreateDisposition
0x1400ff3e8  add     ax, ax
0x1400ff3eb  mov     [rsp+1B0h+ShareAccess], 7; ShareAccess
0x1400ff3f3  xorps   xmm0, xmm0
0x1400ff3f6  mov     [rsp+1B0h+FileAttributes], 80h; FileAttributes
0x1400ff3fe  mov     edx, 100001h; DesiredAccess
0x1400ff403  mov     [rsp+1B0h+AllocationSize], rdi; AllocationSize
0x1400ff408  mov     [r12], ax
0x1400ff40d  mov     [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x1400ff414  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], rdi
0x1400ff418  mov     [rbp+0B0h+ObjectAttributes.Attributes], 240h
0x1400ff41f  mov     [rbp+0B0h+ObjectAttributes.ObjectName], r12
0x1400ff423  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ff428  call    cs:__imp_ZwCreateFile
0x1400ff42f  nop     dword ptr [rax+rax+00h]
0x1400ff434  mov     [r14+2], bx
0x1400ff439  mov     edi, eax
0x1400ff43b  mov     rcx, [rsi]
0x1400ff43e  xor     r14d, r14d
0x1400ff441  mov     rax, r15
0x1400ff444  inc     rax
0x1400ff447  cmp     [rcx+rax*2], r14w
0x1400ff44c  jnz     short loc_1400FF444
0x1400ff44e  add     ax, ax
0x1400ff451  mov     [r12], ax
0x1400ff456  test    edi, edi
0x1400ff458  js      loc_1400FF796
0x1400ff45e  lea     rax, [rbp+0B0h+var_9E]
0x1400ff462  xor     r8d, r8d; ppszDestEnd
0x1400ff465  mov     [rbp+0B0h+FileName.Buffer], rax
0x1400ff469  lea     r9, [rbp+0B0h+pcchRemaining]; pcchRemaining
0x1400ff46d  lea     rax, [r13+2]
0x1400ff471  mov     qword ptr [rsp+1B0h+CreateOptions], rax
0x1400ff476  lea     rcx, [rbp+0B0h+pszDest]; pszDest
0x1400ff47a  mov     rax, [rbp+0B0h+var_110]
0x1400ff47e  lea     edx, [r8+21h]; cchDest
0x1400ff482  mov     dword ptr [rsp+1B0h+CreateDisposition], 3Ch ; '<'
0x1400ff48a  mov     qword ptr [rsp+1B0h+ShareAccess], rax
0x1400ff48f  lea     rax, aSCS; "%s%c.%s"
0x1400ff496  mov     qword ptr [rsp+1B0h+FileAttributes], rax; pszFormat
0x1400ff49b  mov     [rsp+1B0h+AllocationSize], r14; dwFlags
0x1400ff4a0  call    RtlStringCchPrintfExW
0x1400ff4a5  mov     rcx, [rbp+0B0h+FileName.Buffer]
0x1400ff4a9  mov     rax, r15
0x1400ff4ac  inc     rax
0x1400ff4af  cmp     [rcx+rax*2], r14w
0x1400ff4b4  jnz     short loc_1400FF4AC
0x1400ff4b6  add     ax, ax
0x1400ff4b9  lea     r9, UxLowPriorityPool
0x1400ff4c0  mov     r12d, 1
0x1400ff4c6  mov     [rbp+0B0h+FileName.Length], ax
0x1400ff4ca  mov     edx, 1002h
0x1400ff4cf  mov     [rbp+0B0h+FileName.MaximumLength], ax
0x1400ff4d3  mov     r8d, 474C6C55h
0x1400ff4d9  mov     dword ptr [rsp+1B0h+AllocationSize], r12d
0x1400ff4de  lea     ecx, [r12+41h]
0x1400ff4e3  call    cs:__imp_ExAllocatePool3
0x1400ff4ea  nop     dword ptr [rax+rax+00h]
0x1400ff4ef  mov     rdi, rax
0x1400ff4f2  mov     [rsp+1B0h+FileInformation], rax
0x1400ff4f7  test    rax, rax
0x1400ff4fa  jnz     short loc_1400FF506
0x1400ff4fc  mov     edi, 0C000009Ah
0x1400ff501  jmp     loc_1400FF796
0x1400ff506  mov     rcx, [rsp+1B0h+FileHandle]; FileHandle
0x1400ff50b  lea     rax, [rbp+0B0h+FileName]
0x1400ff50f  mov     byte ptr [rsp+1B0h+EaLength], r12b; RestartScan
0x1400ff514  xor     r9d, r9d; ApcContext
0x1400ff517  mov     [rsp+1B0h+EaBuffer], rax; FileName
0x1400ff51c  xor     r8d, r8d; ApcRoutine
0x1400ff51f  mov     byte ptr [rsp+1B0h+CreateOptions], r14b; ReturnSingleEntry
0x1400ff524  lea     rax, [rbp+0B0h+IoStatusBlock]
0x1400ff528  mov     dword ptr [rsp+1B0h+CreateDisposition], r12d; FileInformationClass
0x1400ff52d  xor     edx, edx; Event
0x1400ff52f  mov     [rsp+1B0h+ShareAccess], 0FFEh; Length
0x1400ff537  mov     qword ptr [rsp+1B0h+FileAttributes], rdi; FileInformation
0x1400ff53c  mov     [rsp+1B0h+AllocationSize], rax; IoStatusBlock
0x1400ff541  call    cs:__imp_ZwQueryDirectoryFile
0x1400ff548  nop     dword ptr [rax+rax+00h]
0x1400ff54d  xor     edx, edx
0x1400ff54f  mov     ebx, eax
0x1400ff551  test    eax, eax
0x1400ff553  jns     short loc_1400FF589
0x1400ff555  test    byte ptr cs:xmmword_1401A2C90+9, 8
0x1400ff55c  jz      short loc_1400FF579
0x1400ff55e  mov     rcx, [rbp+0B0h+FileName.Buffer]
0x1400ff562  mov     r9d, eax
0x1400ff565  mov     qword ptr [rsp+1B0h+FileAttributes], rcx
0x1400ff56a  mov     rcx, [rsi]
0x1400ff56d  mov     [rsp+1B0h+AllocationSize], rcx
0x1400ff572  call    WPP_SF_dSS
0x1400ff577  xor     edx, edx
0x1400ff579  cmp     ebx, 0C000000Fh
0x1400ff57f  mov     edi, edx
0x1400ff581  cmovnz  edi, ebx
0x1400ff584  jmp     loc_1400FF77F
0x1400ff589  mov     byte ptr [rsp+1B0h+var_14C], dl
0x1400ff58d  mov     r13d, r12d
0x1400ff590  mov     r14, r12
0x1400ff593  mov     [rsp+1B0h+var_140], r12
0x1400ff598  mov     rbx, rdx
0x1400ff59b  mov     ecx, [rdi+3Ch]
0x1400ff59e  lea     r12, [rdi+40h]
0x1400ff5a2  shr     rcx, 1
0x1400ff5a5  movzx   eax, word ptr [rdi+rcx*2+40h]
0x1400ff5aa  mov     [rdi+rcx*2+40h], dx
0x1400ff5af  mov     rcx, r12; Str
0x1400ff5b2  mov     rdx, [rbp+0B0h+SubStr]; SubStr
0x1400ff5b6  mov     [rsp+1B0h+var_150], ax
0x1400ff5bb  call    cs:__imp_wcsstr
0x1400ff5c2  nop     dword ptr [rax+rax+00h]
0x1400ff5c7  xor     edx, edx
0x1400ff5c9  mov     [rbp+0B0h+pcchRemaining], rax
0x1400ff5cd  test    rax, rax
0x1400ff5d0  jz      short loc_1400FF643
0x1400ff5d2  mov     [rax], dx
0x1400ff5d5  cmp     [r12], dx
0x1400ff5da  jz      short loc_1400FF643
0x1400ff5dc  movzx   ecx, byte ptr [r12]; C
0x1400ff5e1  call    cs:__imp_isdigit
0x1400ff5e8  nop     dword ptr [rax+rax+00h]
0x1400ff5ed  xor     edx, edx
0x1400ff5ef  test    eax, eax
0x1400ff5f1  jnz     short loc_1400FF5F9
0x1400ff5f3  add     r12, 2
0x1400ff5f7  jmp     short loc_1400FF5D5
0x1400ff5f9  mov     r8, [rbp+0B0h+pcchRemaining]
0x1400ff5fd  lea     rcx, [rsp+1B0h+var_140]
0x1400ff602  mov     qword ptr [rsp+1B0h+ShareAccess], rcx
0x1400ff607  sub     r8, r12
0x1400ff60a  mov     qword ptr [rsp+1B0h+FileAttributes], rdx
0x1400ff60f  xor     r9d, r9d
0x1400ff612  sar     r8, 1
0x1400ff615  mov     rdx, r12
0x1400ff618  mov     cl, 1
0x1400ff61a  mov     dword ptr [rsp+1B0h+AllocationSize], 0Ah
0x1400ff622  call    HttpStringToULongLong
0x1400ff627  xor     edx, edx
0x1400ff629  test    eax, eax
0x1400ff62b  js      short loc_1400FF63B
0x1400ff62d  mov     r14, [rsp+1B0h+var_140]
0x1400ff632  cmp     r14, 0FFFFFFh
0x1400ff639  jbe     short loc_1400FF643
0x1400ff63b  mov     r14, rdx
0x1400ff63e  mov     [rsp+1B0h+var_140], rdx
0x1400ff643  mov     eax, [rdi+3Ch]
0x1400ff646  movzx   ecx, [rsp+1B0h+var_150]
0x1400ff64b  shr     rax, 1
0x1400ff64e  mov     [rdi+rax*2+40h], cx
0x1400ff653  mov     eax, r13d
0x1400ff656  cmp     r14, rax
0x1400ff659  jb      short loc_1400FF675
0x1400ff65b  mov     r12d, [rdi+38h]
0x1400ff65f  mov     r13d, r14d
0x1400ff662  mov     rbx, [rdi+28h]
0x1400ff666  shr     r12d, 4
0x1400ff66a  and     r12b, 1
0x1400ff66e  mov     [rsp+1B0h+var_14C], r12d
0x1400ff673  jmp     short loc_1400FF67A
0x1400ff675  mov     r12d, [rsp+1B0h+var_14C]
0x1400ff67a  mov     eax, [rdi]
0x1400ff67c  test    eax, eax
0x1400ff67e  jz      short loc_1400FF688
0x1400ff680  add     rdi, rax
0x1400ff683  jmp     loc_1400FF59B
0x1400ff688  mov     rax, [rsp+1B0h+FileInformation]
0x1400ff68d  xor     r9d, r9d; ApcContext
0x1400ff690  mov     rcx, [rsp+1B0h+FileHandle]; FileHandle
0x1400ff695  xor     r8d, r8d; ApcRoutine
0x1400ff698  mov     byte ptr [rsp+1B0h+EaLength], dl; RestartScan
0x1400ff69c  mov     [rsp+1B0h+EaBuffer], rdx; FileName
0x1400ff6a1  mov     byte ptr [rsp+1B0h+CreateOptions], dl; ReturnSingleEntry
0x1400ff6a5  xor     edx, edx; Event
0x1400ff6a7  mov     dword ptr [rsp+1B0h+CreateDisposition], 1; FileInformationClass
0x1400ff6af  mov     [rsp+1B0h+ShareAccess], 1000h; Length
0x1400ff6b7  mov     qword ptr [rsp+1B0h+FileAttributes], rax; FileInformation
0x1400ff6bc  lea     rax, [rbp+0B0h+IoStatusBlock]
0x1400ff6c0  mov     [rsp+1B0h+AllocationSize], rax; IoStatusBlock
0x1400ff6c5  call    cs:__imp_ZwQueryDirectoryFile
0x1400ff6cc  nop     dword ptr [rax+rax+00h]
0x1400ff6d1  mov     edi, eax
0x1400ff6d3  cmp     eax, 80000006h
0x1400ff6d8  jz      short loc_1400FF6EE
0x1400ff6da  xor     edx, edx
0x1400ff6dc  test    eax, eax
0x1400ff6de  js      loc_1400FF77F
0x1400ff6e4  mov     rdi, [rsp+1B0h+FileInformation]
0x1400ff6e9  jmp     loc_1400FF59B
0x1400ff6ee  xor     r14d, r14d
0x1400ff6f1  mov     edi, r14d
0x1400ff6f4  test    r12b, r12b
0x1400ff6f7  jz      short loc_1400FF6FF
0x1400ff6f9  inc     r13d
0x1400ff6fc  mov     ebx, r14d
0x1400ff6ff  mov     rax, [rbp+0B0h+SubStr]
0x1400ff703  lea     r9, [rbp+0B0h+pcchRemaining]; pcchRemaining
0x1400ff707  mov     rcx, [rbp+0B0h+var_108]; pszDest
0x1400ff70b  add     rax, 2
0x1400ff70f  mov     qword ptr [rsp+1B0h+CreateOptions], rax
0x1400ff714  xor     r8d, r8d; ppszDestEnd
0x1400ff717  mov     rax, [rbp+0B0h+var_110]
0x1400ff71b  mov     dword ptr [rsp+1B0h+CreateDisposition], r13d
0x1400ff720  mov     qword ptr [rsp+1B0h+ShareAccess], rax
0x1400ff725  lea     rax, aSDS; "%s%d.%s"
0x1400ff72c  mov     qword ptr [rsp+1B0h+FileAttributes], rax; pszFormat
0x1400ff731  lea     edx, [r8+21h]; cchDest
0x1400ff735  mov     [rsp+1B0h+AllocationSize], r14; dwFlags
0x1400ff73a  call    RtlStringCchPrintfExW
0x1400ff73f  mov     rax, [rsi]
0x1400ff742  inc     r15
0x1400ff745  cmp     [rax+r15*2], r14w
0x1400ff74a  jnz     short loc_1400FF742
0x1400ff74c  mov     rax, [rbp+0B0h+var_100]
0x1400ff750  add     r15w, r15w
0x1400ff754  mov     rcx, [rbp+0B0h+var_F8]
0x1400ff758  mov     [rax], r15w
0x1400ff75c  lea     eax, [r13+1]
0x1400ff760  mov     [rcx], eax
0x1400ff762  mov     rax, [rbp+0B0h+var_F0]
0x1400ff766  mov     [rax], rbx
0x1400ff769  test    byte ptr cs:xmmword_1401A2CA0+9, 8
0x1400ff770  jz      short loc_1400FF77F
0x1400ff772  mov     r9, [rsi]
0x1400ff775  mov     [rsp+1B0h+AllocationSize], rbx
0x1400ff77a  call    WPP_SF_SI
0x1400ff77f  mov     rcx, [rsp+1B0h+FileInformation]; P
0x1400ff784  xor     edx, edx; Tag
0x1400ff786  call    cs:__imp_ExFreePoolWithTag
0x1400ff78d  nop     dword ptr [rax+rax+00h]
0x1400ff792  test    edi, edi
0x1400ff794  jns     short loc_1400FF7C0
0x1400ff796  test    byte ptr cs:xmmword_1401A2C90+9, 8
0x1400ff79d  jz      short loc_1400FF7C0
0x1400ff79f  mov     rax, [rsi]
0x1400ff7a2  lea     r8, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids
0x1400ff7a9  mov     edx, 1Dh
0x1400ff7ae  mov     [rsp+1B0h+AllocationSize], rax
0x1400ff7b3  mov     ecx, 30Bh
0x1400ff7b8  mov     r9d, edi
0x1400ff7bb  call    WPP_SF_dS
0x1400ff7c0  mov     rcx, [rsp+1B0h+FileHandle]; Handle
0x1400ff7c5  test    rcx, rcx
0x1400ff7c8  jz      short loc_1400FF7D6
0x1400ff7ca  call    cs:__imp_ZwClose
  ... truncated ...
```
