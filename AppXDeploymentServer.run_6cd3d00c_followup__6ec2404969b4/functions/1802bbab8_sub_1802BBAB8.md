# sub_1802BBAB8

- ea: `0x1802bbab8`
- end: `0x1802bc0f2`
- name: `sub_1802BBAB8`
- size: `1594`
- prototype: `__int64 __fastcall(const WCHAR *, int, char, _QWORD *)`
- caller_count: `5`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180115440`
- `0x1801429bc`
- `0x1801436e4`
- `0x1801442e4`
- `0x1802bc3b4`

## callees

- `0x180006704`
- `0x180016e48`
- `0x180017140`
- `0x180017648`
- `0x180024b6c`
- `0x180029514`
- `0x180029810`
- `0x18003654c`
- `0x180039898`
- `0x18008fcac`
- `0x180101840`
- `0x180120c88`
- `0x18012b038`
- `0x1801471c0`
- `0x1801c5240`
- `0x1802bbab8`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1802bbb4c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1802bbb4c`
- `ntdll!NtCreateFile` at `0x1802bbd06`
- `ntdll!NtCreateFile` at `0x1802bbea9`
- `ntdll!NtCreateFile` at `0x1802bbd06`
- `ntdll!NtCreateFile` at `0x1802bbea9`
- `ntdll!RtlFreeUnicodeString` at `0x1802bbb77`
- `ntdll!RtlFreeUnicodeString` at `0x1802bbc82`
- `ntdll!RtlFreeUnicodeString` at `0x1802bbf84`
- `ntdll!RtlFreeUnicodeString` at `0x1802bbffa`
- `ntdll!RtlFreeUnicodeString` at `0x1802bc082`
- `ntdll!RtlFreeUnicodeString` at `0x1802bc0b9`
- `ntdll!RtlFreeUnicodeString` at `0x1802bbb77`
- `ntdll!RtlFreeUnicodeString` at `0x1802bbc82`
- `ntdll!RtlFreeUnicodeString` at `0x1802bbf84`
- `ntdll!RtlFreeUnicodeString` at `0x1802bbffa`
- `ntdll!RtlFreeUnicodeString` at `0x1802bc082`
- `ntdll!RtlFreeUnicodeString` at `0x1802bc0b9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1802bbfbd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1802bbfbd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1802bc045`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1802bc045`

## string_xrefs

- `0x1802bbb16`: `onecore\admin\appmodel\common\encryption.cpp`
- `0x1802bbb60`: `onecore\admin\appmodel\common\encryption.cpp`
- `0x1802bbc62`: `onecore\admin\appmodel\common\encryption.cpp`
- `0x1802bbf58`: `onecore\admin\appmodel\common\encryption.cpp`
- `0x1802bbfce`: `onecore\admin\appmodel\common\encryption.cpp`
- `0x1802bc056`: `onecore\admin\appmodel\common\encryption.cpp`
- `0x1802bbe51`: `EfsOpenFileRawInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall sub_1802BBAB8(const WCHAR *a1, int a2, char a3, _QWORD *a4)
{
  unsigned int v7; // ebx
  int v8; // eax
  ULONG CreateDisposition; // esi
  int v10; // r12d
  int v11; // r13d
  int v12; // edx
  ACCESS_MASK v13; // edi
  ULONG CreateOptions; // r14d
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rcx
  NTSTATUS v20; // ebx
  unsigned int *v21; // rax
  int v22; // r8d
  int v23; // r9d
  unsigned int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  const WCHAR *v27; // r15
  _DWORD *v28; // rax
  int v29; // r8d
  int v30; // r9d
  void *v31; // rax
  ULONG InBuffer; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-98h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  ULONG FileAttributes; // [rsp+78h] [rbp-88h]
  LPCWSTR v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h] BYREF
  __int64 v39; // [rsp+90h] [rbp-70h] BYREF
  __int64 v40; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR v41; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+A8h] [rbp-58h] BYREF
  void *TokenHandle[2]; // [rsp+B8h] [rbp-48h] BYREF
  char v44; // [rsp+C8h] [rbp-38h]
  char v45; // [rsp+D0h] [rbp-30h]
  __int64 v46; // [rsp+D8h] [rbp-28h]
  _QWORD *v47; // [rsp+E0h] [rbp-20h]
  _BYTE v48[8]; // [rsp+E8h] [rbp-18h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-10h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+120h] [rbp+20h] BYREF
  _OWORD FileInformation[2]; // [rsp+130h] [rbp+30h] BYREF
  int v52; // [rsp+150h] [rbp+50h]
  void *retaddr; // [rsp+198h] [rbp+98h]

  v47 = a4;
  lpFileName = a1;
  sub_180029514(v48);
  if ( a3 && a2 )
  {
    v7 = -2147024809;
    sub_180024B6C(retaddr, 182, "onecore\\admin\\appmodel\\common\\encryption.cpp", 2147942487LL);
  }
  else
  {
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    UnicodeString = 0;
    v8 = RtlDosPathNameToNtPathName_U_WithStatus(a1, &UnicodeString, 0, 0);
    if ( v8 >= 0 )
    {
      FileAttributes = 128;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &UnicodeString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      CreateDisposition = 1;
      v10 = a2 & 2;
      v11 = a2 & 1;
      if ( (a2 & 1) != 0 )
      {
        InBuffer = 0;
        v12 = 18;
        CreateDisposition = 3;
        if ( (a2 & 2) != 0 )
        {
          v13 = 1048963;
          CreateOptions = 32801;
          FileAttributes = 144;
        }
        else
        {
          v13 = 1048962;
          CreateOptions = 2132000;
          if ( (a2 & 4) != 0 )
            FileAttributes = 130;
        }
      }
      else
      {
        v12 = 17;
        InBuffer = 5;
        if ( (a2 & 2) != 0 )
        {
          v13 = 129;
          CreateOptions = 1;
        }
        else
        {
          CreateOptions = 2099232;
          v13 = a3 != 0 ? 1441945 : 1048704;
        }
      }
      *(_OWORD *)TokenHandle = 0;
      v44 = 0;
      v45 = 0;
      v46 = 0;
      v15 = sub_180017140(TokenHandle, v12);
      v7 = v15;
      if ( v15 >= 0 )
      {
        if ( (int)sub_180016E48(TokenHandle, v16, v17, v18) >= 0 )
        {
          CreateOptions |= 0x4000u;
          if ( (a2 & 2) == 0 )
            v13 |= 0x10000u;
        }
        else
        {
          v13 |= v11 + 1;
        }
        FileHandle = (void *)-1LL;
        IoStatusBlock = 0;
        sub_18008FCAC(&FileHandle, -1);
        v20 = NtCreateFile(
                &FileHandle,
                v13,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                FileAttributes,
                InBuffer,
                CreateDisposition,
                CreateOptions,
                0,
                0);
        if ( v20 == -1073741757 )
        {
          v21 = (unsigned int *)sub_180039898(v19);
          v24 = *v21;
          if ( a2 )
          {
            if ( v24 <= 5 )
            {
              v27 = lpFileName;
            }
            else
            {
              v41 = (LPCWSTR)CreateOptions;
              v40 = CreateDisposition;
              v39 = InBuffer;
              v38 = v13;
              v27 = lpFileName;
              v37 = lpFileName;
              LODWORD(lpFileName) = -1073741757;
              sub_180006704(
                (_DWORD)v21,
                (unsigned int)&word_1805064D6,
                v22,
                v23,
                (__int64)&lpFileName,
                (__int64)&v37,
                (__int64)&v38,
                (__int64)&v39,
                (__int64)&v40,
                (__int64)&v41);
            }
            sub_1801471C0(v27);
          }
          else
          {
            if ( v24 > 5 && (unsigned __int8)sub_180101840(v21, 0x400000000000LL) )
            {
              v37 = (LPCWSTR)CreateOptions;
              v38 = CreateDisposition;
              v39 = InBuffer;
              v40 = v13;
              v27 = lpFileName;
              v41 = lpFileName;
              LODWORD(lpFileName) = -1073741757;
              sub_180006704(
                v25,
                (unsigned int)word_18050645A,
                v25,
                v26,
                (__int64)&lpFileName,
                (__int64)&v41,
                (__int64)&v40,
                (__int64)&v39,
                (__int64)&v38,
                (__int64)&v37);
            }
            else
            {
              v27 = lpFileName;
            }
            v13 = 1179785;
          }
          sub_18008FCAC(&FileHandle, -1);
          v20 = NtCreateFile(
                  &FileHandle,
                  v13,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  FileAttributes,
                  InBuffer,
                  CreateDisposition,
                  CreateOptions,
                  0,
                  0);
        }
        else
        {
          v27 = lpFileName;
        }
        if ( v20 >= 0 )
        {
          v7 = 0;
          if ( v11 && v10 )
          {
            memset(FileInformation, 0, sizeof(FileInformation));
            v52 = 0;
            if ( !GetFileAttributesExW(v27, GetFileExInfoStandard, FileInformation) )
            {
              v7 = sub_18012B038(retaddr, 387, "onecore\\admin\\appmodel\\common\\encryption.cpp");
              sub_18003654C(&FileHandle);
              sub_180017648(TokenHandle);
              RtlFreeUnicodeString(&UnicodeString);
              goto LABEL_46;
            }
            if ( (FileInformation[0] & 0x800) != 0 )
            {
              LOWORD(InBuffer) = 0;
              LODWORD(lpFileName) = 0;
              if ( !DeviceIoControl(FileHandle, 0x9C040u, &InBuffer, 2u, 0, 0, (LPDWORD)&lpFileName, 0) )
              {
                v7 = sub_18012B038(retaddr, 400, "onecore\\admin\\appmodel\\common\\encryption.cpp");
                sub_18003654C(&FileHandle);
                sub_180017648(TokenHandle);
                RtlFreeUnicodeString(&UnicodeString);
                goto LABEL_46;
              }
            }
          }
          v31 = FileHandle;
          FileHandle = (void *)-1LL;
          *v47 = v31;
          sub_18003654C(&FileHandle);
          sub_180017648(TokenHandle);
          RtlFreeUnicodeString(&UnicodeString);
          goto LABEL_46;
        }
        v28 = (_DWORD *)sub_180039898(v19);
        if ( *v28 > 5u && (unsigned __int8)sub_180101840(v28, 0x400000000000LL) )
        {
          v41 = (LPCWSTR)CreateOptions;
          v40 = CreateDisposition;
          v39 = InBuffer;
          v38 = v13;
          v37 = v27;
          LODWORD(lpFileName) = v20;
          sub_180006704(
            v29,
            (unsigned int)word_18050655A,
            v29,
            v30,
            (__int64)&lpFileName,
            (__int64)&v37,
            (__int64)&v38,
            (__int64)&v39,
            (__int64)&v40,
            (__int64)&v41);
        }
        v7 = sub_180120C88(retaddr, 375, "onecore\\admin\\appmodel\\common\\encryption.cpp", (unsigned int)v20);
        sub_18003654C(&FileHandle);
        sub_180017648(TokenHandle);
        RtlFreeUnicodeString(&UnicodeString);
      }
      else
      {
        sub_180024B6C(retaddr, 275, "onecore\\admin\\appmodel\\common\\encryption.cpp", (unsigned int)v15);
        sub_180017648(TokenHandle);
        RtlFreeUnicodeString(&UnicodeString);
      }
    }
    else
    {
      v7 = sub_180120C88(retaddr, 194, "onecore\\admin\\appmodel\\common\\encryption.cpp", (unsigned int)v8);
      RtlFreeUnicodeString(&UnicodeString);
    }
  }
LABEL_46:
  sub_180029810(v48);
  return v7;
}

```

## disassembly

```asm
0x1802bbab8  mov     [rsp-8+arg_8], rbx
0x1802bbabd  push    rbp
0x1802bbabe  push    rsi
0x1802bbabf  push    rdi
0x1802bbac0  push    r12
0x1802bbac2  push    r13
0x1802bbac4  push    r14
0x1802bbac6  push    r15
0x1802bbac8  lea     rbp, [rsp-60h]
0x1802bbacd  sub     rsp, 160h
0x1802bbad4  mov     rax, cs:__security_cookie
0x1802bbadb  xor     rax, rsp
0x1802bbade  mov     [rbp+90h+var_38], rax
0x1802bbae2  mov     [rbp+90h+var_B0], r9
0x1802bbae6  mov     bl, r8b
0x1802bbae9  mov     r15d, edx
0x1802bbaec  mov     rdi, rcx
0x1802bbaef  mov     [rsp+190h+lpFileName], rcx
0x1802bbaf4  lea     rcx, [rbp+90h+var_A8]
0x1802bbaf8  call    sub_180029514
0x1802bbafd  nop
0x1802bbafe  test    bl, bl
0x1802bbb00  jz      short loc_1802BBB2C
0x1802bbb02  test    r15d, r15d
0x1802bbb05  jz      short loc_1802BBB2C
0x1802bbb07  mov     rcx, [rbp+98h]
0x1802bbb0e  mov     ebx, 80070057h
0x1802bbb13  mov     r9d, ebx
0x1802bbb16  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\common\\encry"...
0x1802bbb1d  mov     edx, 0B6h
0x1802bbb22  call    sub_180024B6C
0x1802bbb27  jmp     loc_1802BC0C0
0x1802bbb2c  xorps   xmm0, xmm0
0x1802bbb2f  movups  xmmword ptr [rbp+90h+ObjectAttributes.Length], xmm0
0x1802bbb33  movups  xmmword ptr [rbp+90h+ObjectAttributes.ObjectName], xmm0
0x1802bbb37  movups  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x1802bbb3b  movups  xmmword ptr [rbp+90h+UnicodeString.Length], xmm0
0x1802bbb3f  xor     r9d, r9d
0x1802bbb42  xor     r8d, r8d
0x1802bbb45  lea     rdx, [rbp+90h+UnicodeString]
0x1802bbb49  mov     rcx, rdi
0x1802bbb4c  call    cs:RtlDosPathNameToNtPathName_U_WithStatus
0x1802bbb52  test    eax, eax
0x1802bbb54  jns     short loc_1802BBB83
0x1802bbb56  mov     rcx, [rbp+98h]
0x1802bbb5d  mov     r9d, eax
0x1802bbb60  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\common\\encry"...
0x1802bbb67  mov     edx, 0C2h
0x1802bbb6c  call    sub_180120C88
0x1802bbb71  mov     ebx, eax
0x1802bbb73  lea     rcx, [rbp+90h+UnicodeString]; UnicodeString
0x1802bbb77  call    cs:RtlFreeUnicodeString
0x1802bbb7d  nop
0x1802bbb7e  jmp     loc_1802BC0C0
0x1802bbb83  mov     [rsp+190h+var_118], 80h
0x1802bbb8b  mov     [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x1802bbb92  mov     [rbp+90h+ObjectAttributes.RootDirectory], 0
0x1802bbb9a  mov     [rbp+90h+ObjectAttributes.Attributes], 40h ; '@'
0x1802bbba1  lea     rax, [rbp+90h+UnicodeString]
0x1802bbba5  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x1802bbba9  xorps   xmm0, xmm0
0x1802bbbac  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x1802bbbb1  mov     r13d, r15d
0x1802bbbb4  mov     esi, 1
0x1802bbbb9  mov     r12d, r15d
0x1802bbbbc  and     r12d, 2
0x1802bbbc0  and     r13d, esi
0x1802bbbc3  jz      short loc_1802BBC08
0x1802bbbc5  mov     [rsp+190h+InBuffer], 0
0x1802bbbcd  lea     edx, [rsi+11h]
0x1802bbbd0  lea     esi, [rdx-0Fh]
0x1802bbbd3  test    r12d, r12d
0x1802bbbd6  jz      short loc_1802BBBED
0x1802bbbd8  mov     edi, 100183h
0x1802bbbdd  mov     r14d, 8021h
0x1802bbbe3  mov     [rsp+190h+var_118], 90h
0x1802bbbeb  jmp     short loc_1802BBC38
0x1802bbbed  mov     edi, 100182h
0x1802bbbf2  mov     r14d, 208820h
0x1802bbbf8  test    r15b, 4
0x1802bbbfc  jz      short loc_1802BBC38
0x1802bbbfe  mov     [rsp+190h+var_118], 82h
0x1802bbc06  jmp     short loc_1802BBC38
0x1802bbc08  mov     edx, 11h
0x1802bbc0d  mov     [rsp+190h+InBuffer], 5
0x1802bbc15  test    r12d, r12d
0x1802bbc18  jz      short loc_1802BBC22
0x1802bbc1a  lea     edi, [rdx+70h]
0x1802bbc1d  mov     r14d, esi
0x1802bbc20  jmp     short loc_1802BBC38
0x1802bbc22  mov     r14d, 200820h
0x1802bbc28  neg     bl
0x1802bbc2a  sbb     edi, edi
0x1802bbc2c  and     edi, 60019h
0x1802bbc32  add     edi, 100080h
0x1802bbc38  movdqu  xmmword ptr [rbp+90h+TokenHandle], xmm0
0x1802bbc3d  xor     eax, eax
0x1802bbc3f  mov     [rbp+90h+var_C8], al
0x1802bbc42  mov     [rbp+90h+var_C0], al
0x1802bbc45  mov     [rbp+90h+var_B8], rax
0x1802bbc49  lea     rcx, [rbp+90h+TokenHandle]; TokenHandle
0x1802bbc4d  call    sub_180017140
0x1802bbc52  mov     ebx, eax
0x1802bbc54  test    eax, eax
0x1802bbc56  jns     short loc_1802BBC8E
0x1802bbc58  mov     rcx, [rbp+98h]
0x1802bbc5f  mov     r9d, eax
0x1802bbc62  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\common\\encry"...
0x1802bbc69  mov     edx, 113h
0x1802bbc6e  call    sub_180024B6C
0x1802bbc73  nop
0x1802bbc74  lea     rcx, [rbp+90h+TokenHandle]
0x1802bbc78  call    sub_180017648
0x1802bbc7d  nop
0x1802bbc7e  lea     rcx, [rbp+90h+UnicodeString]; UnicodeString
0x1802bbc82  call    cs:RtlFreeUnicodeString
0x1802bbc88  nop
0x1802bbc89  jmp     loc_1802BC0C0
0x1802bbc8e  lea     rcx, [rbp+90h+TokenHandle]
0x1802bbc92  call    sub_180016E48
0x1802bbc97  xor     ebx, ebx
0x1802bbc99  test    eax, eax
0x1802bbc9b  jns     short loc_1802BBCA5
0x1802bbc9d  lea     eax, [r13+1]
0x1802bbca1  or      edi, eax
0x1802bbca3  jmp     short loc_1802BBCB3
0x1802bbca5  bts     r14d, 0Eh
0x1802bbcaa  test    r12d, r12d
0x1802bbcad  jnz     short loc_1802BBCB3
0x1802bbcaf  bts     edi, 10h
0x1802bbcb3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802bbcb7  mov     [rsp+190h+FileHandle], rax
0x1802bbcbc  xorps   xmm0, xmm0
0x1802bbcbf  movups  xmmword ptr [rbp+90h+IoStatusBlock], xmm0
0x1802bbcc3  mov     rdx, rax
0x1802bbcc6  lea     rcx, [rsp+190h+FileHandle]
0x1802bbccb  call    sub_18008FCAC
0x1802bbcd0  mov     [rsp+190h+EaLength], ebx; EaLength
0x1802bbcd4  mov     [rsp+190h+EaBuffer], rbx; EaBuffer
0x1802bbcd9  mov     [rsp+190h+CreateOptions], r14d; CreateOptions
0x1802bbcde  mov     [rsp+190h+CreateDisposition], esi; CreateDisposition
0x1802bbce2  mov     eax, [rsp+190h+InBuffer]
0x1802bbce6  mov     [rsp+190h+ShareAccess], eax; ShareAccess
0x1802bbcea  mov     eax, [rsp+190h+var_118]
0x1802bbcee  mov     [rsp+190h+FileAttributes], eax; FileAttributes
0x1802bbcf2  mov     [rsp+190h+AllocationSize], rbx; AllocationSize
0x1802bbcf7  lea     r9, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x1802bbcfb  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x1802bbcff  mov     edx, edi; DesiredAccess
0x1802bbd01  lea     rcx, [rsp+190h+FileHandle]; FileHandle
0x1802bbd06  call    cs:NtCreateFile
0x1802bbd0c  mov     ebx, eax
0x1802bbd0e  cmp     eax, 0C0000043h
0x1802bbd13  jnz     loc_1802BBEB3
0x1802bbd19  xor     ebx, ebx
0x1802bbd1b  call    sub_180039898
0x1802bbd20  mov     ecx, [rax]
0x1802bbd22  test    r15d, r15d
0x1802bbd25  jnz     loc_1802BBDD0
0x1802bbd2b  mov     r8, rax
0x1802bbd2e  cmp     ecx, 5
0x1802bbd31  jbe     loc_1802BBDC1
0x1802bbd37  mov     rdx, 400000000000h
0x1802bbd41  mov     rcx, rax
0x1802bbd44  call    sub_180101840
0x1802bbd49  test    al, al
0x1802bbd4b  jz      short loc_1802BBDC1
0x1802bbd4d  mov     ecx, r14d
0x1802bbd50  mov     [rbp+90h+var_110], rcx
0x1802bbd54  mov     eax, esi
0x1802bbd56  mov     [rbp+90h+var_108], rax
0x1802bbd5a  mov     eax, [rsp+190h+InBuffer]
0x1802bbd5e  mov     [rbp+90h+var_100], rax
0x1802bbd62  mov     eax, edi
0x1802bbd64  mov     [rbp+90h+var_F8], rax
0x1802bbd68  mov     r15, [rsp+190h+lpFileName]
0x1802bbd6d  mov     [rbp+90h+var_F0], r15
0x1802bbd71  mov     dword ptr [rsp+190h+lpFileName], 0C0000043h
0x1802bbd79  lea     rax, [rbp+90h+var_110]
0x1802bbd7d  mov     [rsp+190h+EaBuffer], rax
0x1802bbd82  lea     rax, [rbp+90h+var_108]
0x1802bbd86  mov     qword ptr [rsp+190h+CreateOptions], rax
0x1802bbd8b  lea     rax, [rbp+90h+var_100]
0x1802bbd8f  mov     qword ptr [rsp+190h+CreateDisposition], rax
0x1802bbd94  lea     rax, [rbp+90h+var_F8]
0x1802bbd98  mov     qword ptr [rsp+190h+ShareAccess], rax
0x1802bbd9d  lea     rax, [rbp+90h+var_F0]
0x1802bbda1  mov     qword ptr [rsp+190h+FileAttributes], rax
0x1802bbda6  lea     rax, [rsp+190h+lpFileName]
0x1802bbdab  mov     [rsp+190h+AllocationSize], rax
0x1802bbdb0  lea     rdx, word_18050645A
0x1802bbdb7  mov     rcx, r8
0x1802bbdba  call    sub_180006704
0x1802bbdbf  jmp     short loc_1802BBDC6
0x1802bbdc1  mov     r15, [rsp+190h+lpFileName]
0x1802bbdc6  mov     edi, 120089h
0x1802bbdcb  jmp     loc_1802BBE65
0x1802bbdd0  cmp     ecx, 5
0x1802bbdd3  jbe     short loc_1802BBE49
0x1802bbdd5  mov     ecx, r14d
0x1802bbdd8  mov     [rbp+90h+var_F0], rcx
0x1802bbddc  mov     ecx, esi
0x1802bbdde  mov     [rbp+90h+var_F8], rcx
0x1802bbde2  mov     ecx, [rsp+190h+InBuffer]
0x1802bbde6  mov     [rbp+90h+var_100], rcx
0x1802bbdea  mov     ecx, edi
0x1802bbdec  mov     [rbp+90h+var_108], rcx
0x1802bbdf0  mov     r15, [rsp+190h+lpFileName]
0x1802bbdf5  mov     [rbp+90h+var_110], r15
0x1802bbdf9  mov     dword ptr [rsp+190h+lpFileName], 0C0000043h
0x1802bbe01  lea     rcx, [rbp+90h+var_F0]
0x1802bbe05  mov     [rsp+190h+EaBuffer], rcx
0x1802bbe0a  lea     rcx, [rbp+90h+var_F8]
0x1802bbe0e  mov     qword ptr [rsp+190h+CreateOptions], rcx
0x1802bbe13  lea     rcx, [rbp+90h+var_100]
0x1802bbe17  mov     qword ptr [rsp+190h+CreateDisposition], rcx
0x1802bbe1c  lea     rcx, [rbp+90h+var_108]
0x1802bbe20  mov     qword ptr [rsp+190h+ShareAccess], rcx
0x1802bbe25  lea     rcx, [rbp+90h+var_110]
0x1802bbe29  mov     qword ptr [rsp+190h+FileAttributes], rcx
0x1802bbe2e  lea     rcx, [rsp+190h+lpFileName]
0x1802bbe33  mov     [rsp+190h+AllocationSize], rcx
0x1802bbe38  lea     rdx, word_1805064D6
0x1802bbe3f  mov     rcx, rax
0x1802bbe42  call    sub_180006704
0x1802bbe47  jmp     short loc_1802BBE4E
0x1802bbe49  mov     r15, [rsp+190h+lpFileName]
0x1802bbe4e  xor     r9d, r9d
0x1802bbe51  lea     r8, aEfsopenfileraw; "EfsOpenFileRawInternal"
0x1802bbe58  mov     edx, 0D0000043h
0x1802bbe5d  mov     rcx, r15; lpFileName
0x1802bbe60  call    sub_1801471C0
0x1802bbe65  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1802bbe69  lea     rcx, [rsp+190h+FileHandle]
0x1802bbe6e  call    sub_18008FCAC
0x1802bbe73  mov     [rsp+190h+EaLength], ebx; EaLength
0x1802bbe77  mov     [rsp+190h+EaBuffer], rbx; EaBuffer
0x1802bbe7c  mov     [rsp+190h+CreateOptions], r14d; CreateOptions
0x1802bbe81  mov     [rsp+190h+CreateDisposition], esi; CreateDisposition
0x1802bbe85  mov     eax, [rsp+190h+InBuffer]
0x1802bbe89  mov     [rsp+190h+ShareAccess], eax; ShareAccess
0x1802bbe8d  mov     eax, [rsp+190h+var_118]
0x1802bbe91  mov     [rsp+190h+FileAttributes], eax; FileAttributes
0x1802bbe95  mov     [rsp+190h+AllocationSize], rbx; AllocationSize
0x1802bbe9a  lea     r9, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x1802bbe9e  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x1802bbea2  mov     edx, edi; DesiredAccess
0x1802bbea4  lea     rcx, [rsp+190h+FileHandle]; FileHandle
0x1802bbea9  call    cs:NtCreateFile
0x1802bbeaf  mov     ebx, eax
0x1802bbeb1  jmp     short loc_1802BBEB8
0x1802bbeb3  mov     r15, [rsp+190h+lpFileName]
0x1802bbeb8  test    ebx, ebx
0x1802bbeba  jns     loc_1802BBF90
0x1802bbec0  call    sub_180039898
0x1802bbec5  mov     r8, rax
0x1802bbec8  mov     ecx, [rax]
0x1802bbeca  cmp     ecx, 5
0x1802bbecd  jbe     short loc_1802BBF4E
0x1802bbecf  mov     rdx, 400000000000h
0x1802bbed9  mov     rcx, rax
0x1802bbedc  call    sub_180101840
0x1802bbee1  test    al, al
0x1802bbee3  jz      short loc_1802BBF4E
0x1802bbee5  mov     ecx, r14d
0x1802bbee8  mov     [rbp+90h+var_F0], rcx
0x1802bbeec  mov     eax, esi
0x1802bbeee  mov     [rbp+90h+var_F8], rax
0x1802bbef2  mov     eax, [rsp+190h+InBuffer]
0x1802bbef6  mov     [rbp+90h+var_100], rax
0x1802bbefa  mov     eax, edi
0x1802bbefc  mov     [rbp+90h+var_108], rax
0x1802bbf00  mov     [rbp+90h+var_110], r15
0x1802bbf04  mov     dword ptr [rsp+190h+lpFileName], ebx
0x1802bbf08  lea     rax, [rbp+90h+var_F0]
0x1802bbf0c  mov     [rsp+190h+EaBuffer], rax
0x1802bbf11  lea     rax, [rbp+90h+var_F8]
0x1802bbf15  mov     qword ptr [rsp+190h+CreateOptions], rax
0x1802bbf1a  lea     rax, [rbp+90h+var_100]
0x1802bbf1e  mov     qword ptr [rsp+190h+CreateDisposition], rax
0x1802bbf23  lea     rax, [rbp+90h+var_108]
0x1802bbf27  mov     qword ptr [rsp+190h+ShareAccess], rax
0x1802bbf2c  lea     rax, [rbp+90h+var_110]
0x1802bbf30  mov     qword ptr [rsp+190h+FileAttributes], rax
0x1802bbf35  lea     rax, [rsp+190h+lpFileName]
0x1802bbf3a  mov     [rsp+190h+AllocationSize], rax
0x1802bbf3f  lea     rdx, word_18050655A
0x1802bbf46  mov     rcx, r8
0x1802bbf49  call    sub_180006704
0x1802bbf4e  mov     rcx, [rbp+98h]
0x1802bbf55  mov     r9d, ebx
0x1802bbf58  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\common\\encry"...
0x1802bbf5f  mov     edx, 177h
0x1802bbf64  call    sub_180120C88
0x1802bbf69  mov     ebx, eax
0x1802bbf6b  lea     rcx, [rsp+190h+FileHandle]
0x1802bbf70  call    sub_18003654C
0x1802bbf75  nop
0x1802bbf76  lea     rcx, [rbp+90h+TokenHandle]
0x1802bbf7a  call    sub_180017648
  ... truncated ...
```
