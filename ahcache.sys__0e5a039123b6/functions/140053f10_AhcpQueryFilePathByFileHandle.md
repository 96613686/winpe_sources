# AhcpQueryFilePathByFileHandle

- ea: `0x140053f10`
- end: `0x1400542f9`
- name: `AhcpQueryFilePathByFileHandle`
- size: `1001`
- prototype: `__int64 __fastcall(wchar_t **, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x14004c3a0`

## callees

- `0x14000211c`
- `0x140004553`
- `0x140007b40`
- `0x14003e364`
- `0x140045d44`
- `0x140053f10`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005405e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400542db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005405e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400542db`
- `ntoskrnl!ZwQueryInformationFile` at `0x140053f89`
- `ntoskrnl!ZwQueryInformationFile` at `0x1400541a3`
- `ntoskrnl!ZwQueryInformationFile` at `0x140053f89`
- `ntoskrnl!ZwQueryInformationFile` at `0x1400541a3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140053fd1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140053fd1`
- `ntoskrnl!IoFileObjectType` at `0x140053faa`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400541c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400541c1`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14005400f`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14005400f`
- `ntoskrnl!IoQueryFileDosDeviceName` at `0x140054241`
- `ntoskrnl!IoQueryFileDosDeviceName` at `0x140054241`
- `ntoskrnl!ObfDereferenceObject` at `0x140054044`
- `ntoskrnl!ObfDereferenceObject` at `0x140054044`

## string_xrefs

- `0x140054200`: `AhcpQueryFilePathByFileHandle`
- `0x140054227`: `AhcpQueryFilePathByFileHandle`
- `0x1400542b8`: `AhcpQueryFilePathByFileHandle`
- `0x1400542ab`: `Failed to make nt path [%x]`

## pseudocode

```c
__int64 __fastcall AhcpQueryFilePathByFileHandle(wchar_t **a1, void *a2)
{
  _DWORD *Pool2_0; // rax
  _DWORD *v4; // rsi
  __int64 v5; // rcx
  NTSTATUS v6; // ebx
  NTSTATUS v7; // eax
  wchar_t *v8; // r15
  _WORD *v9; // r14
  char v10; // r12
  struct _FILE_OBJECT *v11; // r13
  _DWORD *v12; // rcx
  NTSTATUS v13; // eax
  __int64 Length; // rbx
  __int64 v15; // rcx
  _WORD *v17; // rax
  wchar_t *Buffer; // rdx
  size_t v19; // r8
  char *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rbx
  wchar_t *v23; // rax
  NTSTATUS v24; // eax
  ULONG v25; // ebx
  _DWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-40h]
  FILE_INFORMATION_CLASS FileInformationClassa[2]; // [rsp+20h] [rbp-40h]
  PVOID Object; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+38h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-18h] BYREF
  char v35; // [rsp+B0h] [rbp+50h]
  POBJECT_NAME_INFORMATION ObjectNameInformation; // [rsp+B8h] [rbp+58h] BYREF

  ObjectNameInformation = 0;
  DosName = 0;
  IoStatusBlock = 0;
  Pool2_0 = (_DWORD *)ExAllocatePool2_0(256, 528, 1953517633);
  v4 = Pool2_0;
  if ( !Pool2_0 )
    return (unsigned int)-1073741801;
  v6 = ZwQueryInformationFile(a2, &IoStatusBlock, Pool2_0, 0x210u, FileNameInformation);
  if ( v6 != -2147483643 )
    goto LABEL_3;
  v25 = *v4 + 8;
  AslFree(v5, v4);
  v26 = (_DWORD *)ExAllocatePool2_0(256, v25, 1953517633);
  v4 = v26;
  if ( !v26 )
    return (unsigned int)-1073741801;
  v6 = ZwQueryInformationFile(a2, &IoStatusBlock, v26, v25, FileNameInformation);
LABEL_3:
  if ( v6 < 0 )
  {
    FileInformationClass[0] = v6;
    AslLogCallPrintf(
      1,
      "AhcpQueryFilePathByFileHandle",
      549,
      "Failed to query file information. [%x]",
      *(_QWORD *)FileInformationClass);
  }
  else
  {
    Object = 0;
    v7 = ObReferenceObjectByHandle(a2, 0x80u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
    v6 = v7;
    if ( v7 >= 0 )
    {
      v8 = 0;
      v35 = 0;
      v9 = 0;
      v10 = 0;
      v11 = (struct _FILE_OBJECT *)Object;
      v12 = (_DWORD *)*((_QWORD *)Object + 1);
      if ( v12[18] == 20 )
      {
        RtlInitUnicodeString(&DosName, L"UNC");
      }
      else
      {
        v13 = IoVolumeDeviceToDosName(v12, &DosName);
        if ( v13 < 0 )
          AslLogCallPrintf(
            1,
            "AhcpQueryFilePathByFileHandle",
            584,
            "Failed to get dos volume name, will try to get dos device name instead. [%x]",
            v13);
        else
          v10 = 1;
      }
      if ( DosName.Buffer )
        goto LABEL_9;
      v6 = IoQueryFileDosDeviceName(v11, &ObjectNameInformation);
      if ( v6 < 0 || !ObjectNameInformation )
      {
        FileInformationClassa[0] = v6;
        AslLogCallPrintf(
          1,
          "AhcpQueryFilePathByFileHandle",
          595,
          "Failed to get dos device name. [%x]",
          *(_QWORD *)FileInformationClassa);
        goto LABEL_11;
      }
      v35 = 1;
      if ( DosName.Buffer )
      {
LABEL_9:
        LODWORD(Length) = DosName.Length + *v4;
        if ( (unsigned int)Length < DosName.Length )
          goto LABEL_10;
        v17 = (_WORD *)ExAllocatePool2_0(256, (unsigned int)Length + 2LL, 1953517633);
        v9 = v17;
        if ( v17 )
        {
          memmove(v17, DosName.Buffer, DosName.Length);
          Buffer = (wchar_t *)(v4 + 1);
          v19 = (unsigned int)*v4;
          v20 = (char *)&v9[(unsigned __int64)DosName.Length >> 1];
          goto LABEL_24;
        }
      }
      else
      {
        Length = ObjectNameInformation->Name.Length;
        v28 = AslAlloc(v27, Length + 2, 1);
        v9 = (_WORD *)v28;
        if ( v28 )
        {
          v19 = (unsigned int)Length;
          v20 = (char *)v28;
          Buffer = ObjectNameInformation->Name.Buffer;
LABEL_24:
          memmove(v20, Buffer, v19);
          v9[(unsigned __int64)(unsigned int)Length >> 1] = 0;
          v21 = (unsigned int)(Length + 8);
          if ( (unsigned int)v21 >= (unsigned int)Length )
          {
            v22 = (unsigned int)v21;
            v23 = (wchar_t *)ExAllocatePool2_0(256, v21 + 2, 1953517633);
            v8 = v23;
            if ( v23 )
            {
              v24 = RtlStringCbPrintfW(v23, v22 + 2, L"\\??\\%s", v9);
              v6 = v24;
              if ( v24 < 0 )
              {
                FileInformationClassa[0] = v24;
                AslLogCallPrintf(
                  1,
                  "AhcpQueryFilePathByFileHandle",
                  653,
                  "Failed to make nt path [%x]",
                  *(_QWORD *)FileInformationClassa);
              }
              else
              {
                *a1 = v8;
                v8 = 0;
                v6 = 0;
              }
              goto LABEL_11;
            }
            goto LABEL_42;
          }
LABEL_10:
          v6 = -1073741562;
LABEL_11:
          ObfDereferenceObject(v11);
          if ( v10 )
            ExFreePoolWithTag(DosName.Buffer, 0);
          if ( v35 )
            ExFreePoolWithTag(ObjectNameInformation, 0);
          if ( v9 )
            AslFree(v15, v9);
          if ( v8 )
            AslFree(v15, v8);
          goto LABEL_19;
        }
      }
LABEL_42:
      v6 = -1073741801;
      goto LABEL_11;
    }
    FileInformationClassa[0] = v7;
    AslLogCallPrintf(
      1,
      "AhcpQueryFilePathByFileHandle",
      566,
      "Failed to get file object [%x]",
      *(_QWORD *)FileInformationClassa);
  }
LABEL_19:
  if ( v4 )
    AslFree(v15, v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140053f10  mov     [rsp-38h+arg_8], rbx
0x140053f15  mov     [rsp-38h+arg_10], r8
0x140053f1a  mov     [rsp-38h+arg_0], rcx
0x140053f1f  push    rbp
0x140053f20  push    rsi
0x140053f21  push    rdi
0x140053f22  push    r12
0x140053f24  push    r13
0x140053f26  push    r14
0x140053f28  push    r15
0x140053f2a  mov     rbp, rsp
0x140053f2d  sub     rsp, 60h
0x140053f31  mov     rdi, rdx
0x140053f34  xorps   xmm0, xmm0
0x140053f37  xorps   xmm1, xmm1
0x140053f3a  mov     r15d, 74705041h
0x140053f40  mov     ebx, 210h
0x140053f45  mov     r12d, 100h
0x140053f4b  xor     r13d, r13d
0x140053f4e  mov     r8d, r15d
0x140053f51  mov     edx, ebx
0x140053f53  mov     [rbp+ObjectNameInformation], r13
0x140053f57  mov     ecx, r12d
0x140053f5a  movups  xmmword ptr [rbp+DosName.Length], xmm0
0x140053f5e  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x140053f62  call    ExAllocatePool2_0
0x140053f67  mov     rsi, rax
0x140053f6a  test    rax, rax
0x140053f6d  jz      loc_1400541D2
0x140053f73  lea     r14d, [r13+9]
0x140053f77  mov     r9d, ebx; Length
0x140053f7a  mov     r8, rax; FileInformation
0x140053f7d  mov     [rsp+60h+FileInformationClass], r14d; FileInformationClass
0x140053f82  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x140053f86  mov     rcx, rdi; FileHandle
0x140053f89  call    cs:__imp_ZwQueryInformationFile
0x140053f90  nop     dword ptr [rax+rax+00h]
0x140053f95  mov     ebx, eax
0x140053f97  cmp     eax, 80000005h
0x140053f9c  jz      loc_14005416F
0x140053fa2  test    ebx, ebx
0x140053fa4  js      loc_1400541DC
0x140053faa  mov     r8, cs:__imp_IoFileObjectType
0x140053fb1  lea     rax, [rbp+Object]
0x140053fb5  mov     [rsp+60h+HandleInformation], r13; HandleInformation
0x140053fba  xor     r9d, r9d; AccessMode
0x140053fbd  mov     edx, 80h; DesiredAccess
0x140053fc2  mov     [rbp+Object], r13
0x140053fc6  mov     rcx, rdi; Handle
0x140053fc9  mov     qword ptr [rsp+60h+FileInformationClass], rax; Object
0x140053fce  mov     r8, [r8]; ObjectType
0x140053fd1  call    cs:__imp_ObReferenceObjectByHandle
0x140053fd8  nop     dword ptr [rax+rax+00h]
0x140053fdd  mov     ebx, eax
0x140053fdf  test    eax, eax
0x140053fe1  js      loc_1400541EF
0x140053fe7  mov     r15, r13
0x140053fea  mov     byte ptr [rbp+arg_10], r13b
0x140053fee  mov     r14, r13
0x140053ff1  mov     r12b, r13b
0x140053ff4  mov     r13, [rbp+Object]
0x140053ff8  mov     edi, 1
0x140053ffd  mov     rcx, [r13+8]; VolumeDeviceObject
0x140054001  cmp     dword ptr [rcx+48h], 14h
0x140054005  jz      loc_1400541B6
0x14005400b  lea     rdx, [rbp+DosName]; DosName
0x14005400f  call    cs:__imp_IoVolumeDeviceToDosName
0x140054016  nop     dword ptr [rax+rax+00h]
0x14005401b  test    eax, eax
0x14005401d  js      loc_140054216
0x140054023  mov     r12b, dil
0x140054026  cmp     [rbp+DosName.Buffer], r14
0x14005402a  jz      loc_14005423A
0x140054030  movzx   ecx, [rbp+DosName.Length]
0x140054034  mov     ebx, [rsi]
0x140054036  add     ebx, ecx
0x140054038  cmp     ebx, ecx
0x14005403a  jnb     short loc_1400540AE
0x14005403c  mov     ebx, 0C0000106h
0x140054041  mov     rcx, r13; Object
0x140054044  call    cs:__imp_ObfDereferenceObject
0x14005404b  nop     dword ptr [rax+rax+00h]
0x140054050  xor     r13d, r13d
0x140054053  test    r12b, r12b
0x140054056  jz      short loc_14005406A
0x140054058  mov     rcx, [rbp+DosName.Buffer]; P
0x14005405c  xor     edx, edx; Tag
0x14005405e  call    cs:__imp_ExFreePoolWithTag
0x140054065  nop     dword ptr [rax+rax+00h]
0x14005406a  cmp     byte ptr [rbp+arg_10], r13b
0x14005406e  jnz     loc_1400542D5
0x140054074  test    r14, r14
0x140054077  jz      short loc_140054081
0x140054079  mov     rdx, r14
0x14005407c  call    AslFree
0x140054081  test    r15, r15
0x140054084  jnz     loc_1400542EC
0x14005408a  test    rsi, rsi
0x14005408d  jnz     loc_140054162
0x140054093  mov     eax, ebx
0x140054095  mov     rbx, [rsp+60h+arg_8]
0x14005409d  add     rsp, 60h
0x1400540a1  pop     r15
0x1400540a3  pop     r14
0x1400540a5  pop     r13
0x1400540a7  pop     r12
0x1400540a9  pop     rdi
0x1400540aa  pop     rsi
0x1400540ab  pop     rbp
0x1400540ac  retn
0x1400540ae  mov     edx, ebx
0x1400540b0  mov     ecx, 100h
0x1400540b5  add     rdx, 2
0x1400540b9  mov     r8d, 74705041h
0x1400540bf  call    ExAllocatePool2_0
0x1400540c4  mov     r14, rax
0x1400540c7  test    rax, rax
0x1400540ca  jz      loc_1400542CB
0x1400540d0  movzx   r8d, [rbp+DosName.Length]; Size
0x1400540d5  mov     rcx, rax; void *
0x1400540d8  mov     rdx, [rbp+DosName.Buffer]; Src
0x1400540dc  call    memmove
0x1400540e1  movzx   eax, [rbp+DosName.Length]
0x1400540e5  lea     rdx, [rsi+4]; Src
0x1400540e9  mov     r8d, [rsi]; Size
0x1400540ec  shr     rax, 1
0x1400540ef  lea     rcx, [r14+rax*2]; void *
0x1400540f3  call    memmove
0x1400540f8  xor     eax, eax
0x1400540fa  mov     ecx, ebx
0x1400540fc  shr     rcx, 1
0x1400540ff  mov     [r14+rcx*2], ax
0x140054104  lea     eax, [rbx+8]
0x140054107  cmp     eax, ebx
0x140054109  jb      loc_14005403C
0x14005410f  mov     r8d, 74705041h
0x140054115  mov     ebx, eax
0x140054117  lea     rdx, [rax+2]
0x14005411b  mov     ecx, 100h
0x140054120  call    ExAllocatePool2_0
0x140054125  mov     r15, rax
0x140054128  test    rax, rax
0x14005412b  jz      loc_1400542CB
0x140054131  mov     r9, r14
0x140054134  lea     r8, aS; "\\??\\%s"
0x14005413b  lea     rdx, [rbx+2]; cbDest
0x14005413f  mov     rcx, rax; pszDest
0x140054142  call    RtlStringCbPrintfW
0x140054147  mov     ebx, eax
0x140054149  test    eax, eax
0x14005414b  js      loc_1400542A7
0x140054151  mov     rax, [rbp+arg_0]
0x140054155  mov     [rax], r15
0x140054158  xor     r15d, r15d
0x14005415b  xor     ebx, ebx
0x14005415d  jmp     loc_140054041
0x140054162  mov     rdx, rsi
0x140054165  call    AslFree
0x14005416a  jmp     loc_140054093
0x14005416f  mov     ebx, [rsi]
0x140054171  mov     rdx, rsi
0x140054174  add     ebx, 8
0x140054177  call    AslFree
0x14005417c  mov     edx, ebx
0x14005417e  mov     r8d, r15d
0x140054181  mov     rcx, r12
0x140054184  call    ExAllocatePool2_0
0x140054189  mov     rsi, rax
0x14005418c  test    rax, rax
0x14005418f  jz      short loc_1400541D2
0x140054191  mov     r9d, ebx; Length
0x140054194  mov     [rsp+60h+FileInformationClass], r14d; FileInformationClass
0x140054199  mov     r8, rax; FileInformation
0x14005419c  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x1400541a0  mov     rcx, rdi; FileHandle
0x1400541a3  call    cs:__imp_ZwQueryInformationFile
0x1400541aa  nop     dword ptr [rax+rax+00h]
0x1400541af  mov     ebx, eax
0x1400541b1  jmp     loc_140053FA2
0x1400541b6  lea     rdx, aUnc_0; "UNC"
0x1400541bd  lea     rcx, [rbp+DosName]; DestinationString
0x1400541c1  call    cs:__imp_RtlInitUnicodeString
0x1400541c8  nop     dword ptr [rax+rax+00h]
0x1400541cd  jmp     loc_140054026
0x1400541d2  mov     ebx, 0C0000017h
0x1400541d7  jmp     loc_140054093
0x1400541dc  mov     [rsp+60h+FileInformationClass], ebx
0x1400541e0  lea     r9, aFailedToQueryF_0; "Failed to query file information. [%x]"
0x1400541e7  mov     r8d, 225h
0x1400541ed  jmp     short loc_140054200
0x1400541ef  mov     [rsp+60h+FileInformationClass], eax
0x1400541f3  lea     r9, aFailedToGetFil; "Failed to get file object [%x]"
0x1400541fa  mov     r8d, 236h
0x140054200  lea     rdx, aAhcpqueryfilep; "AhcpQueryFilePathByFileHandle"
0x140054207  mov     ecx, 1
0x14005420c  call    AslLogCallPrintf
0x140054211  jmp     loc_14005408A
0x140054216  lea     r9, aFailedToGetDos; "Failed to get dos volume name, will try"...
0x14005421d  mov     [rsp+60h+FileInformationClass], eax
0x140054221  mov     r8d, 248h
0x140054227  lea     rdx, aAhcpqueryfilep; "AhcpQueryFilePathByFileHandle"
0x14005422e  mov     ecx, edi
0x140054230  call    AslLogCallPrintf
0x140054235  jmp     loc_140054026
0x14005423a  lea     rdx, [rbp+ObjectNameInformation]; ObjectNameInformation
0x14005423e  mov     rcx, r13; FileObject
0x140054241  call    cs:__imp_IoQueryFileDosDeviceName
0x140054248  nop     dword ptr [rax+rax+00h]
0x14005424d  mov     ebx, eax
0x14005424f  test    eax, eax
0x140054251  js      short loc_140054294
0x140054253  mov     rax, [rbp+ObjectNameInformation]
0x140054257  test    rax, rax
0x14005425a  jz      short loc_140054294
0x14005425c  mov     byte ptr [rbp+arg_10], dil
0x140054260  cmp     [rbp+DosName.Buffer], r14
0x140054264  jnz     loc_140054030
0x14005426a  movzx   ebx, word ptr [rax]
0x14005426d  mov     r8d, edi
0x140054270  lea     rdx, [rbx+2]
0x140054274  call    AslAlloc
0x140054279  mov     r14, rax
0x14005427c  test    rax, rax
0x14005427f  jz      short loc_1400542CB
0x140054281  mov     rdx, [rbp+ObjectNameInformation]
0x140054285  mov     r8d, ebx
0x140054288  mov     rcx, rax
0x14005428b  mov     rdx, [rdx+8]
0x14005428f  jmp     loc_1400540F3
0x140054294  mov     [rsp+60h+FileInformationClass], ebx
0x140054298  lea     r9, aFailedToGetDos_0; "Failed to get dos device name. [%x]"
0x14005429f  mov     r8d, 253h
0x1400542a5  jmp     short loc_1400542B8
0x1400542a7  mov     [rsp+60h+FileInformationClass], eax
0x1400542ab  lea     r9, aFailedToMakeNt; "Failed to make nt path [%x]"
0x1400542b2  mov     r8d, 28Dh
0x1400542b8  lea     rdx, aAhcpqueryfilep; "AhcpQueryFilePathByFileHandle"
0x1400542bf  mov     ecx, edi
0x1400542c1  call    AslLogCallPrintf
0x1400542c6  jmp     loc_140054041
0x1400542cb  mov     ebx, 0C0000017h
0x1400542d0  jmp     loc_140054041
0x1400542d5  mov     rcx, [rbp+ObjectNameInformation]; P
0x1400542d9  xor     edx, edx; Tag
0x1400542db  call    cs:__imp_ExFreePoolWithTag
0x1400542e2  nop     dword ptr [rax+rax+00h]
0x1400542e7  jmp     loc_140054074
0x1400542ec  mov     rdx, r15
0x1400542ef  call    AslFree
0x1400542f4  jmp     loc_14005408A
```
