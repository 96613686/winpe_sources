# BfspCreateOsLoaderObject

- ea: `0x18004ede8`
- end: `0x18004f086`
- name: `BfspCreateOsLoaderObject`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180050410`

## callees

- `0x1800078b0`
- `0x18004cdd4`
- `0x18004ede8`
- `0x18004f854`
- `0x1800507fc`
- `0x180050894`
- `0x180050c94`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x18004efa7`
- `ntdll!RtlStringFromGUID` at `0x18004efa7`
- `ntdll!RtlFreeUnicodeString` at `0x18004efc6`
- `ntdll!RtlFreeUnicodeString` at `0x18004efc6`
- `ntdll!RtlInitUnicodeString` at `0x18004ee3a`
- `ntdll!RtlInitUnicodeString` at `0x18004ee3a`
- `bcd!BcdSetElementData` at `0x18004ef64`
- `bcd!BcdSetElementData` at `0x18004f038`
- `bcd!BcdSetElementData` at `0x18004ef64`
- `bcd!BcdSetElementData` at `0x18004f038`
- `bcd!BcdCloseObject` at `0x18004ee99`
- `bcd!BcdCloseObject` at `0x18004ef27`
- `bcd!BcdCloseObject` at `0x18004f061`
- `bcd!BcdCloseObject` at `0x18004ee99`
- `bcd!BcdCloseObject` at `0x18004ef27`
- `bcd!BcdCloseObject` at `0x18004f061`
- `bcd!BcdOpenObject` at `0x18004ee8d`
- `bcd!BcdOpenObject` at `0x18004eee8`
- `bcd!BcdOpenObject` at `0x18004ee8d`
- `bcd!BcdOpenObject` at `0x18004eee8`
- `bcd!BcdCopyObjectEx` at `0x18004ef1b`
- `bcd!BcdCopyObjectEx` at `0x18004ef1b`
- `bcd!BcdQueryObject` at `0x18004ef88`
- `bcd!BcdQueryObject` at `0x18004ef88`

## string_xrefs

- `0x18004ef3a`: `Failed to copy OS loader object data. Status = [%x]`
- `0x18004eef4`: `Failed to open handle to the OS loader object. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCreateOsLoaderObject(__int64 a1, __int64 a2, __int64 a3, const GUID *a4)
{
  const GUID *v8; // r12
  char v9; // cl
  unsigned int BcdCopyFlags; // esi
  GUID v11; // xmm0
  int v12; // ebx
  int v13; // ecx
  int Object; // eax
  int v15; // ebx
  const wchar_t *v16; // rdx
  __int64 v17; // r9
  __int64 v19; // [rsp+30h] [rbp-48h] BYREF
  __int64 v20; // [rsp+38h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  GUID v22; // [rsp+50h] [rbp-28h] BYREF

  v20 = 0;
  v19 = 0;
  DestinationString = 0;
  v8 = 0;
  v22 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  BfspLogMessage(2, L"Creating OsLoader object.");
  BcdCopyFlags = BfspGetBcdCopyFlags((unsigned int)dword_1800A453C);
  if ( (v9 & 1) != 0 )
  {
    if ( byte_1800A4538 )
      v11 = GUID_WINDOWS_SETUP_EFI;
    else
      v11 = GUID_WINDOWS_SETUP_PCAT;
  }
  else
  {
    if ( (v9 & 0x40) != 0 )
    {
      v12 = BcdOpenObject(a2, a4, &v19);
      BcdCloseObject(v19);
      v19 = 0;
      v8 = a4;
      if ( v12 < 0 )
        v8 = 0;
      v13 = BcdCopyFlags | 1;
      if ( v12 >= 0 )
        v13 = BcdCopyFlags;
      BcdCopyFlags = v13;
    }
    else
    {
      BcdCopyFlags |= 1u;
    }
    if ( byte_1800A4538 )
      v11 = GUID_WINDOWS_OS_TARGET_TEMPLATE_EFI;
    else
      v11 = GUID_WINDOWS_OS_TARGET_TEMPLATE_PCAT;
  }
  v22 = v11;
  Object = BcdOpenObject(a1, &v22, &v20);
  v15 = Object;
  if ( Object < 0 )
  {
    v16 = L"Failed to open handle to the OS loader object. Status = [%x]";
LABEL_32:
    BfspLogMessage(4, v16, (unsigned int)Object);
    goto LABEL_33;
  }
  v15 = BcdCopyObjectEx(a1, v20, BcdCopyFlags, a2, v8, &v19);
  BcdCloseObject(v20);
  v20 = 0;
  if ( v15 < 0 )
  {
    BfspLogMessage(4, L"Failed to copy OS loader object data. Status = [%x]", (unsigned int)v15);
    goto LABEL_33;
  }
  if ( (dword_1800A453C & 0x400) != 0 )
  {
    Object = BcdSetElementData(v19, 587202563, a3, 16);
    v15 = Object;
    if ( Object < 0 )
    {
      v16 = L"Failed to set element associated resume object. Status = [%x]";
      goto LABEL_32;
    }
  }
  Object = BcdQueryObject(v19, 0, 0, a4);
  v15 = Object;
  if ( Object < 0 )
  {
    v16 = L"Failed to query OS loader identifier. Status = [%x]";
    goto LABEL_32;
  }
  RtlStringFromGUID(a4, &DestinationString);
  BfspLogMessage(2, L"OsLoader identifier: %wZ", &DestinationString);
  RtlFreeUnicodeString(&DestinationString);
  v15 = BfspSetObjectDeviceAndPath(a1, a2, &v22, a4);
  if ( v15 >= 0 )
  {
    v15 = BfspSetLocale(a2, a4);
    if ( v15 >= 0 )
    {
      v15 = BfspSetObjectStringElements(a1, a2, &v22, a4);
      if ( v15 >= 0 )
      {
        if ( qword_1800A4580 )
        {
          v17 = -1;
          do
            ++v17;
          while ( *((_WORD *)qword_1800A4580 + v17) );
          Object = BcdSetElementData(v19, 301989892, qword_1800A4580, (unsigned int)(2 * v17 + 2));
          v15 = Object;
          if ( Object < 0 )
          {
            v16 = L"Failed to set loader description override. Status = [%x]";
            goto LABEL_32;
          }
        }
      }
    }
  }
LABEL_33:
  if ( v19 )
    BcdCloseObject(v19);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18004ede8  push    rbp
0x18004edea  push    rbx
0x18004edeb  push    rsi
0x18004edec  push    rdi
0x18004eded  push    r12
0x18004edef  push    r13
0x18004edf1  push    r14
0x18004edf3  push    r15
0x18004edf5  mov     rbp, rsp
0x18004edf8  sub     rsp, 78h
0x18004edfc  mov     rax, cs:__security_cookie
0x18004ee03  xor     rax, rsp
0x18004ee06  mov     [rbp+var_18], rax
0x18004ee0a  xorps   xmm0, xmm0
0x18004ee0d  mov     [rbp+var_40], 0
0x18004ee15  mov     r14, rdx
0x18004ee18  mov     [rbp+var_48], 0
0x18004ee20  mov     r15, rcx
0x18004ee23  xor     edx, edx; SourceString
0x18004ee25  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004ee29  mov     rdi, r9
0x18004ee2c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004ee30  mov     r13, r8
0x18004ee33  xor     r12d, r12d
0x18004ee36  movups  [rbp+var_28], xmm0
0x18004ee3a  call    cs:__imp_RtlInitUnicodeString
0x18004ee40  lea     rdx, aCreatingOsload; "Creating OsLoader object."
0x18004ee47  lea     ecx, [r12+2]
0x18004ee4c  call    BfspLogMessage
0x18004ee51  mov     ecx, cs:dword_1800A453C
0x18004ee57  call    BfspGetBcdCopyFlags
0x18004ee5c  mov     esi, eax
0x18004ee5e  test    cl, 1
0x18004ee61  jz      short loc_18004EE7E
0x18004ee63  cmp     cs:byte_1800A4538, r12b
0x18004ee6a  jz      short loc_18004EE75
0x18004ee6c  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_SETUP_EFI.Data1
0x18004ee73  jmp     short loc_18004EED8
0x18004ee75  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_SETUP_PCAT.Data1
0x18004ee7c  jmp     short loc_18004EED8
0x18004ee7e  test    cl, 40h
0x18004ee81  jz      short loc_18004EEBC
0x18004ee83  lea     r8, [rbp+var_48]
0x18004ee87  mov     rdx, rdi
0x18004ee8a  mov     rcx, r14
0x18004ee8d  call    cs:__imp_BcdOpenObject
0x18004ee93  mov     rcx, [rbp+var_48]
0x18004ee97  mov     ebx, eax
0x18004ee99  call    cs:__imp_BcdCloseObject
0x18004ee9f  xor     ecx, ecx
0x18004eea1  mov     [rbp+var_48], r12
0x18004eea5  test    ebx, ebx
0x18004eea7  mov     r12, rdi
0x18004eeaa  cmovs   r12, rcx
0x18004eeae  mov     ecx, esi
0x18004eeb0  or      ecx, 1
0x18004eeb3  test    ebx, ebx
0x18004eeb5  cmovns  ecx, esi
0x18004eeb8  mov     esi, ecx
0x18004eeba  jmp     short loc_18004EEBF
0x18004eebc  or      esi, 1
0x18004eebf  cmp     cs:byte_1800A4538, 0
0x18004eec6  jz      short loc_18004EED1
0x18004eec8  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_OS_TARGET_TEMPLATE_EFI.Data1
0x18004eecf  jmp     short loc_18004EED8
0x18004eed1  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_OS_TARGET_TEMPLATE_PCAT.Data1
0x18004eed8  lea     r8, [rbp+var_40]
0x18004eedc  mov     rcx, r15
0x18004eedf  lea     rdx, [rbp+var_28]
0x18004eee3  movdqu  [rbp+var_28], xmm0
0x18004eee8  call    cs:__imp_BcdOpenObject
0x18004eeee  mov     ebx, eax
0x18004eef0  test    eax, eax
0x18004eef2  jns     short loc_18004EF00
0x18004eef4  lea     rdx, aFailedToOpenHa_1; "Failed to open handle to the OS loader "...
0x18004eefb  jmp     loc_18004F04B
0x18004ef00  mov     rdx, [rbp+var_40]
0x18004ef04  lea     rax, [rbp+var_48]
0x18004ef08  mov     [rsp+78h+var_50], rax
0x18004ef0d  mov     r9, r14
0x18004ef10  mov     r8d, esi
0x18004ef13  mov     [rsp+78h+var_58], r12
0x18004ef18  mov     rcx, r15
0x18004ef1b  call    cs:__imp_BcdCopyObjectEx
0x18004ef21  mov     rcx, [rbp+var_40]
0x18004ef25  mov     ebx, eax
0x18004ef27  call    cs:__imp_BcdCloseObject
0x18004ef2d  xor     esi, esi
0x18004ef2f  mov     [rbp+var_40], rsi
0x18004ef33  test    ebx, ebx
0x18004ef35  jns     short loc_18004EF46
0x18004ef37  mov     r8d, ebx
0x18004ef3a  lea     rdx, aFailedToCopyOs; "Failed to copy OS loader object data. S"...
0x18004ef41  jmp     loc_18004F04E
0x18004ef46  test    cs:dword_1800A453C, 400h
0x18004ef50  jz      short loc_18004EF7C
0x18004ef52  mov     rcx, [rbp+var_48]
0x18004ef56  mov     r9d, 10h
0x18004ef5c  mov     r8, r13
0x18004ef5f  mov     edx, 23000003h
0x18004ef64  call    cs:__imp_BcdSetElementData
0x18004ef6a  mov     ebx, eax
0x18004ef6c  test    eax, eax
0x18004ef6e  jns     short loc_18004EF7C
0x18004ef70  lea     rdx, aFailedToSetEle; "Failed to set element associated resume"...
0x18004ef77  jmp     loc_18004F04B
0x18004ef7c  mov     rcx, [rbp+var_48]
0x18004ef80  mov     r9, rdi
0x18004ef83  xor     r8d, r8d
0x18004ef86  xor     edx, edx
0x18004ef88  call    cs:__imp_BcdQueryObject
0x18004ef8e  mov     ebx, eax
0x18004ef90  test    eax, eax
0x18004ef92  jns     short loc_18004EFA0
0x18004ef94  lea     rdx, aFailedToQueryO_0; "Failed to query OS loader identifier. S"...
0x18004ef9b  jmp     loc_18004F04B
0x18004efa0  lea     rdx, [rbp+DestinationString]; GuidString
0x18004efa4  mov     rcx, rdi; Guid
0x18004efa7  call    cs:__imp_RtlStringFromGUID
0x18004efad  lea     r8, [rbp+DestinationString]
0x18004efb1  mov     ecx, 2
0x18004efb6  lea     rdx, aOsloaderIdenti; "OsLoader identifier: %wZ"
0x18004efbd  call    BfspLogMessage
0x18004efc2  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18004efc6  call    cs:__imp_RtlFreeUnicodeString
0x18004efcc  mov     r9, rdi
0x18004efcf  lea     r8, [rbp+var_28]
0x18004efd3  mov     rdx, r14
0x18004efd6  mov     rcx, r15
0x18004efd9  call    BfspSetObjectDeviceAndPath
0x18004efde  mov     ebx, eax
0x18004efe0  test    eax, eax
0x18004efe2  js      short loc_18004F058
0x18004efe4  mov     rdx, rdi
0x18004efe7  mov     rcx, r14
0x18004efea  call    BfspSetLocale
0x18004efef  mov     ebx, eax
0x18004eff1  test    eax, eax
0x18004eff3  js      short loc_18004F058
0x18004eff5  mov     r9, rdi
0x18004eff8  lea     r8, [rbp+var_28]
0x18004effc  mov     rdx, r14
0x18004efff  mov     rcx, r15
0x18004f002  call    BfspSetObjectStringElements
0x18004f007  mov     ebx, eax
0x18004f009  test    eax, eax
0x18004f00b  js      short loc_18004F058
0x18004f00d  mov     r8, cs:qword_1800A4580
0x18004f014  test    r8, r8
0x18004f017  jz      short loc_18004F058
0x18004f019  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004f01d  inc     r9
0x18004f020  cmp     [r8+r9*2], si
0x18004f025  jnz     short loc_18004F01D
0x18004f027  mov     rcx, [rbp+var_48]
0x18004f02b  lea     r9d, ds:2[r9*2]
0x18004f033  mov     edx, 12000004h
0x18004f038  call    cs:__imp_BcdSetElementData
0x18004f03e  mov     ebx, eax
0x18004f040  test    eax, eax
0x18004f042  jns     short loc_18004F058
0x18004f044  lea     rdx, aFailedToSetLoa; "Failed to set loader description overri"...
0x18004f04b  mov     r8d, eax
0x18004f04e  mov     ecx, 4
0x18004f053  call    BfspLogMessage
0x18004f058  mov     rcx, [rbp+var_48]
0x18004f05c  test    rcx, rcx
0x18004f05f  jz      short loc_18004F067
0x18004f061  call    cs:__imp_BcdCloseObject
0x18004f067  mov     eax, ebx
0x18004f069  mov     rcx, [rbp+var_18]
0x18004f06d  xor     rcx, rsp; StackCookie
0x18004f070  call    __security_check_cookie
0x18004f075  add     rsp, 78h
0x18004f079  pop     r15
0x18004f07b  pop     r14
0x18004f07d  pop     r13
0x18004f07f  pop     r12
0x18004f081  pop     rdi
0x18004f082  pop     rsi
0x18004f083  pop     rbx
0x18004f084  pop     rbp
0x18004f085  retn
```
