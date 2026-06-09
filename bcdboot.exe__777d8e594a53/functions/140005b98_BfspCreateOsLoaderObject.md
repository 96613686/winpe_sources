# BfspCreateOsLoaderObject

- ea: `0x140005b98`
- end: `0x140005e11`
- name: `BfspCreateOsLoaderObject`
- size: `633`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int128 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140007cdc`

## callees

- `0x140005b98`
- `0x1400069e0`
- `0x1400087a8`
- `0x140008844`
- `0x140008c74`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`
- `0x1400140c4`
- `0x14001474c`
- `0x140018b54`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x140005d3a`
- `ntdll!RtlStringFromGUID` at `0x140005d3a`
- `ntdll!RtlFreeUnicodeString` at `0x140005d59`
- `ntdll!RtlFreeUnicodeString` at `0x140005d59`
- `ntdll!RtlInitUnicodeString` at `0x140005bd8`
- `ntdll!RtlInitUnicodeString` at `0x140005bd8`

## string_xrefs

- `0x140005c8f`: `Failed to open handle to the OS loader object. Status = [%x]`
- `0x140005ccf`: `Failed to copy OS loader object data. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCreateOsLoaderObject(__int64 a1, __int64 a2, __int64 a3, __int128 *a4)
{
  __int128 *v8; // r12
  char v9; // cl
  unsigned int BcdCopyFlags; // esi
  GUID v11; // xmm0
  int v12; // ebx
  int v13; // ecx
  int Object; // eax
  int v15; // ebx
  const wchar_t *v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  HANDLE Handle; // [rsp+30h] [rbp-38h] BYREF
  HANDLE v22; // [rsp+38h] [rbp-30h] BYREF
  GUID v23; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF

  v22 = 0;
  Handle = 0;
  DestinationString = 0;
  v8 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  BfspLogMessage(2, L"Creating OsLoader object.");
  BcdCopyFlags = BfspGetBcdCopyFlags((unsigned int)dword_14003F8FC);
  if ( (v9 & 1) != 0 )
  {
    if ( byte_14003F8F8 )
      v11 = GUID_WINDOWS_SETUP_EFI;
    else
      v11 = GUID_WINDOWS_SETUP_PCAT;
  }
  else
  {
    if ( (v9 & 0x40) != 0 )
    {
      v12 = BcdOpenObject(a2, a4, &Handle);
      BcdCloseObject(Handle);
      Handle = 0;
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
    if ( byte_14003F8F8 )
      v11 = GUID_WINDOWS_OS_TARGET_TEMPLATE_EFI;
    else
      v11 = GUID_WINDOWS_OS_TARGET_TEMPLATE_PCAT;
  }
  v23 = v11;
  Object = BcdOpenObject(a1, &v23, &v22);
  v15 = Object;
  if ( Object < 0 )
  {
    v16 = L"Failed to open handle to the OS loader object. Status = [%x]";
LABEL_32:
    BfspLogMessage(4, v16, (unsigned int)Object);
    goto LABEL_33;
  }
  v15 = BcdCopyObjectEx(a1, (__int64)v22, BcdCopyFlags, a2, v8, &Handle);
  BcdCloseObject(v22);
  if ( v15 < 0 )
  {
    BfspLogMessage(4, L"Failed to copy OS loader object data. Status = [%x]", (unsigned int)v15);
    goto LABEL_33;
  }
  if ( (dword_14003F8FC & 0x400) != 0 )
  {
    Object = BcdSetElementDataWithFlags((__int64)Handle, 587202563, 0, a3, 0x10u);
    v15 = Object;
    if ( Object < 0 )
    {
      v16 = L"Failed to set element associated resume object. Status = [%x]";
      goto LABEL_32;
    }
  }
  Object = BcdQueryObject((__int64)Handle, v17, v18, (__int64)a4);
  v15 = Object;
  if ( Object < 0 )
  {
    v16 = L"Failed to query OS loader identifier. Status = [%x]";
    goto LABEL_32;
  }
  RtlStringFromGUID((const GUID *const)a4, &DestinationString);
  BfspLogMessage(2, L"OsLoader identifier: %wZ", &DestinationString);
  RtlFreeUnicodeString(&DestinationString);
  v15 = BfspSetObjectDeviceAndPath(a1, a2, &v23, a4);
  if ( v15 >= 0 )
  {
    v15 = BfspSetLocale(a2, a4);
    if ( v15 >= 0 )
    {
      v15 = BfspSetObjectStringElements(a1, a2, &v23, a4);
      if ( v15 >= 0 )
      {
        if ( qword_14003F940 )
        {
          v19 = -1;
          do
            ++v19;
          while ( *((_WORD *)qword_14003F940 + v19) );
          Object = BcdSetElementDataWithFlags((__int64)Handle, 301989892, 0, (__int64)qword_14003F940, 2 * (int)v19 + 2);
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
  if ( Handle )
    BcdCloseObject(Handle);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140005b98  push    rbp
0x140005b9a  push    rbx
0x140005b9b  push    rsi
0x140005b9c  push    rdi
0x140005b9d  push    r12
0x140005b9f  push    r13
0x140005ba1  push    r14
0x140005ba3  push    r15
0x140005ba5  mov     rbp, rsp
0x140005ba8  sub     rsp, 68h
0x140005bac  mov     r14, rdx
0x140005baf  mov     [rbp+var_30], 0
0x140005bb7  mov     r15, rcx
0x140005bba  mov     [rbp+Handle], 0
0x140005bc2  xorps   xmm0, xmm0
0x140005bc5  lea     rcx, [rbp+DestinationString]; DestinationString
0x140005bc9  xor     edx, edx; SourceString
0x140005bcb  mov     rdi, r9
0x140005bce  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140005bd2  mov     r13, r8
0x140005bd5  xor     r12d, r12d
0x140005bd8  call    cs:__imp_RtlInitUnicodeString
0x140005bde  lea     rdx, aCreatingOsload; "Creating OsLoader object."
0x140005be5  lea     ecx, [r12+2]
0x140005bea  call    BfspLogMessage
0x140005bef  mov     ecx, cs:dword_14003F8FC
0x140005bf5  call    BfspGetBcdCopyFlags
0x140005bfa  mov     esi, eax
0x140005bfc  test    cl, 1
0x140005bff  jz      short loc_140005C1C
0x140005c01  cmp     cs:byte_14003F8F8, r12b
0x140005c08  jz      short loc_140005C13
0x140005c0a  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_SETUP_EFI.Data1
0x140005c11  jmp     short loc_140005C74
0x140005c13  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_SETUP_PCAT.Data1
0x140005c1a  jmp     short loc_140005C74
0x140005c1c  test    cl, 40h
0x140005c1f  jz      short loc_140005C58
0x140005c21  lea     r8, [rbp+Handle]
0x140005c25  mov     rdx, rdi
0x140005c28  mov     rcx, r14
0x140005c2b  call    BcdOpenObject
0x140005c30  mov     rcx, [rbp+Handle]; Handle
0x140005c34  mov     ebx, eax
0x140005c36  call    BcdCloseObject
0x140005c3b  xor     ecx, ecx
0x140005c3d  mov     [rbp+Handle], r12
0x140005c41  test    ebx, ebx
0x140005c43  mov     r12, rdi
0x140005c46  cmovs   r12, rcx
0x140005c4a  mov     ecx, esi
0x140005c4c  or      ecx, 1
0x140005c4f  test    ebx, ebx
0x140005c51  cmovns  ecx, esi
0x140005c54  mov     esi, ecx
0x140005c56  jmp     short loc_140005C5B
0x140005c58  or      esi, 1
0x140005c5b  cmp     cs:byte_14003F8F8, 0
0x140005c62  jz      short loc_140005C6D
0x140005c64  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_OS_TARGET_TEMPLATE_EFI.Data1
0x140005c6b  jmp     short loc_140005C74
0x140005c6d  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_OS_TARGET_TEMPLATE_PCAT.Data1
0x140005c74  lea     r8, [rbp+var_30]
0x140005c78  mov     rcx, r15
0x140005c7b  lea     rdx, [rbp+var_28]
0x140005c7f  movdqu  [rbp+var_28], xmm0
0x140005c84  call    BcdOpenObject
0x140005c89  mov     ebx, eax
0x140005c8b  test    eax, eax
0x140005c8d  jns     short loc_140005C9B
0x140005c8f  lea     rdx, aFailedToOpenHa_1; "Failed to open handle to the OS loader "...
0x140005c96  jmp     loc_140005DE3
0x140005c9b  mov     rdx, [rbp+var_30]
0x140005c9f  lea     rax, [rbp+Handle]
0x140005ca3  mov     [rsp+68h+var_40], rax
0x140005ca8  mov     r9, r14
0x140005cab  mov     r8d, esi
0x140005cae  mov     [rsp+68h+var_48], r12
0x140005cb3  mov     rcx, r15
0x140005cb6  call    BcdCopyObjectEx
0x140005cbb  mov     rcx, [rbp+var_30]; Handle
0x140005cbf  mov     ebx, eax
0x140005cc1  call    BcdCloseObject
0x140005cc6  xor     esi, esi
0x140005cc8  test    ebx, ebx
0x140005cca  jns     short loc_140005CDB
0x140005ccc  mov     r8d, ebx
0x140005ccf  lea     rdx, aFailedToCopyOs; "Failed to copy OS loader object data. S"...
0x140005cd6  jmp     loc_140005DE6
0x140005cdb  test    cs:dword_14003F8FC, 400h
0x140005ce5  jz      short loc_140005D15
0x140005ce7  mov     rcx, [rbp+Handle]
0x140005ceb  mov     r9, r13
0x140005cee  xor     r8d, r8d
0x140005cf1  mov     dword ptr [rsp+68h+var_48], 10h
0x140005cf9  mov     edx, 23000003h
0x140005cfe  call    BcdSetElementDataWithFlags
0x140005d03  mov     ebx, eax
0x140005d05  test    eax, eax
0x140005d07  jns     short loc_140005D15
0x140005d09  lea     rdx, aFailedToSetEle; "Failed to set element associated resume"...
0x140005d10  jmp     loc_140005DE3
0x140005d15  mov     rcx, [rbp+Handle]
0x140005d19  mov     r9, rdi
0x140005d1c  call    BcdQueryObject
0x140005d21  mov     ebx, eax
0x140005d23  test    eax, eax
0x140005d25  jns     short loc_140005D33
0x140005d27  lea     rdx, aFailedToQueryO_0; "Failed to query OS loader identifier. S"...
0x140005d2e  jmp     loc_140005DE3
0x140005d33  lea     rdx, [rbp+DestinationString]; GuidString
0x140005d37  mov     rcx, rdi; Guid
0x140005d3a  call    cs:__imp_RtlStringFromGUID
0x140005d40  lea     r8, [rbp+DestinationString]
0x140005d44  mov     ecx, 2
0x140005d49  lea     rdx, aOsloaderIdenti; "OsLoader identifier: %wZ"
0x140005d50  call    BfspLogMessage
0x140005d55  lea     rcx, [rbp+DestinationString]; UnicodeString
0x140005d59  call    cs:__imp_RtlFreeUnicodeString
0x140005d5f  mov     r9, rdi
0x140005d62  lea     r8, [rbp+var_28]
0x140005d66  mov     rdx, r14
0x140005d69  mov     rcx, r15
0x140005d6c  call    BfspSetObjectDeviceAndPath
0x140005d71  mov     ebx, eax
0x140005d73  test    eax, eax
0x140005d75  js      short loc_140005DF0
0x140005d77  mov     rdx, rdi
0x140005d7a  mov     rcx, r14
0x140005d7d  call    BfspSetLocale
0x140005d82  mov     ebx, eax
0x140005d84  test    eax, eax
0x140005d86  js      short loc_140005DF0
0x140005d88  mov     r9, rdi
0x140005d8b  lea     r8, [rbp+var_28]
0x140005d8f  mov     rdx, r14
0x140005d92  mov     rcx, r15
0x140005d95  call    BfspSetObjectStringElements
0x140005d9a  mov     ebx, eax
0x140005d9c  test    eax, eax
0x140005d9e  js      short loc_140005DF0
0x140005da0  mov     r9, cs:qword_14003F940
0x140005da7  test    r9, r9
0x140005daa  jz      short loc_140005DF0
0x140005dac  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005db0  inc     rax
0x140005db3  cmp     [r9+rax*2], si
0x140005db8  jnz     short loc_140005DB0
0x140005dba  mov     rcx, [rbp+Handle]
0x140005dbe  lea     eax, ds:2[rax*2]
0x140005dc5  xor     r8d, r8d
0x140005dc8  mov     dword ptr [rsp+68h+var_48], eax
0x140005dcc  mov     edx, 12000004h
0x140005dd1  call    BcdSetElementDataWithFlags
0x140005dd6  mov     ebx, eax
0x140005dd8  test    eax, eax
0x140005dda  jns     short loc_140005DF0
0x140005ddc  lea     rdx, aFailedToSetLoa; "Failed to set loader description overri"...
0x140005de3  mov     r8d, eax
0x140005de6  mov     ecx, 4
0x140005deb  call    BfspLogMessage
0x140005df0  mov     rcx, [rbp+Handle]; Handle
0x140005df4  test    rcx, rcx
0x140005df7  jz      short loc_140005DFE
0x140005df9  call    BcdCloseObject
0x140005dfe  mov     eax, ebx
0x140005e00  add     rsp, 68h
0x140005e04  pop     r15
0x140005e06  pop     r14
0x140005e08  pop     r13
0x140005e0a  pop     r12
0x140005e0c  pop     rdi
0x140005e0d  pop     rsi
0x140005e0e  pop     rbx
0x140005e0f  pop     rbp
0x140005e10  retn
```
