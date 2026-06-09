# MdmAccountHelper::IsDeviceOwnerBySid(void *,int *)

- ea: `0x180016e78`
- end: `0x180017023`
- name: `?IsDeviceOwnerBySid@MdmAccountHelper@@CAJPEAXPEAH@Z`
- size: `427`
- prototype: `__int64 __fastcall(PSID pSid1, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800146d4`
- `0x180015270`

## callees

- `0x1800065c0`
- `0x180016e78`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180016fa3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180016fa3`
- `samcli!NetLocalGroupGetMembers` at `0x180016f6d`
- `samcli!NetLocalGroupGetMembers` at `0x180016f6d`
- `netutils!NetApiBufferFree` at `0x180016f23`
- `netutils!NetApiBufferFree` at `0x180017009`
- `netutils!NetApiBufferFree` at `0x180016f23`
- `netutils!NetApiBufferFree` at `0x180017009`

## string_xrefs

- `0x180016ecc`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180016eb8`: `CPR(pSid)`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::IsDeviceOwnerBySid(PSID pSid1, int *a2)
{
  LPBYTE v3; // rcx
  int v5; // edi
  __int64 v6; // rbx
  signed int Members; // eax
  int v8; // edx
  int v9; // ecx
  DWORD v10; // eax
  ULONG_PTR resumehandle[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD totalentries; // [rsp+80h] [rbp+30h] BYREF
  DWORD entriesread; // [rsp+90h] [rbp+40h] BYREF
  LPBYTE bufptr; // [rsp+98h] [rbp+48h] BYREF

  resumehandle[0] = 0;
  v3 = 0;
  bufptr = 0;
  v5 = 1;
  if ( pSid1 )
  {
    if ( a2 )
    {
      *a2 = 0;
      while ( 1 )
      {
        entriesread = 0;
        totalentries = 0;
        if ( v3 )
        {
          NetApiBufferFree(v3);
          bufptr = 0;
        }
        Members = NetLocalGroupGetMembers(
                    0,
                    L"Device Owners",
                    2u,
                    &bufptr,
                    0xFFFFFFFF,
                    &entriesread,
                    &totalentries,
                    resumehandle);
        v6 = (unsigned int)Members;
        if ( Members == 2220 || Members == 1376 )
        {
LABEL_23:
          v5 = 0;
LABEL_24:
          LODWORD(v6) = 0;
          *a2 = v5;
          goto LABEL_25;
        }
        if ( Members )
          break;
        v10 = totalentries;
        if ( totalentries )
        {
          while ( !EqualSid(pSid1, *(PSID *)&bufptr[24 * v6]) )
          {
            v10 = totalentries;
            v6 = (unsigned int)(v6 + 1);
            if ( (unsigned int)v6 >= totalentries )
              goto LABEL_17;
          }
          goto LABEL_24;
        }
LABEL_17:
        if ( v10 >= entriesread )
          goto LABEL_23;
        v3 = bufptr;
      }
      if ( Members > 0 )
        LODWORD(v6) = (unsigned __int16)Members | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v8,
          v6,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          107,
          "CBR(ntStatus == 0)");
    }
    else
    {
      LODWORD(v6) = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        return (unsigned int)v6;
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
        74,
        "CPR(pfIsDeviceOwner)");
    }
  }
  else
  {
    LODWORD(v6) = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      return (unsigned int)v6;
    McTemplateU0dsqs_EventWriteTransfer(
      0,
      (_DWORD)a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      73,
      "CPR(pSid)");
  }
LABEL_25:
  if ( bufptr )
    NetApiBufferFree(bufptr);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016e78  push    rbp
0x180016e7a  push    rbx
0x180016e7b  push    rsi
0x180016e7c  push    rdi
0x180016e7d  push    r14
0x180016e7f  mov     rbp, rsp
0x180016e82  sub     rsp, 50h
0x180016e86  mov     r14, rcx
0x180016e89  mov     [rbp+var_10], 0
0x180016e91  xor     ecx, ecx; Buffer
0x180016e93  mov     rsi, rdx
0x180016e96  mov     [rbp+bufptr], rcx
0x180016e9a  lea     edi, [rcx+1]
0x180016e9d  test    r14, r14
0x180016ea0  jnz     short loc_180016EDD
0x180016ea2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180016ea9  mov     r8d, 80070057h
0x180016eaf  mov     ebx, r8d
0x180016eb2  jz      loc_180017015
0x180016eb8  lea     rax, aCprPsid; "CPR(pSid)"
0x180016ebf  mov     [rsp+50h+entriesread], rax
0x180016ec4  mov     [rsp+50h+prefmaxlen], 249h
0x180016ecc  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180016ed3  call    McTemplateU0dsqs_EventWriteTransfer
0x180016ed8  jmp     loc_180017000
0x180016edd  test    rsi, rsi
0x180016ee0  jnz     short loc_180016F0E
0x180016ee2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180016ee9  mov     r8d, 80070057h
0x180016eef  mov     ebx, r8d
0x180016ef2  jz      loc_180017015
0x180016ef8  lea     rax, aCprPfisdeviceo; "CPR(pfIsDeviceOwner)"
0x180016eff  mov     [rsp+50h+entriesread], rax
0x180016f04  mov     [rsp+50h+prefmaxlen], 24Ah
0x180016f0c  jmp     short loc_180016ECC
0x180016f0e  mov     [rdx], ecx
0x180016f10  mov     [rbp+arg_10], 0
0x180016f17  mov     [rbp+arg_0], 0
0x180016f1e  test    rcx, rcx
0x180016f21  jz      short loc_180016F37
0x180016f23  call    cs:__imp_NetApiBufferFree
0x180016f2a  nop     dword ptr [rax+rax+00h]
0x180016f2f  mov     [rbp+bufptr], 0
0x180016f37  lea     rax, [rbp+var_10]
0x180016f3b  mov     r8d, 2; level
0x180016f41  mov     [rsp+50h+resumehandle], rax; resumehandle
0x180016f46  lea     r9, [rbp+bufptr]; bufptr
0x180016f4a  lea     rax, [rbp+arg_0]
0x180016f4e  xor     ecx, ecx; servername
0x180016f50  mov     [rsp+50h+totalentries], rax; totalentries
0x180016f55  lea     rdx, localgroupname; "Device Owners"
0x180016f5c  lea     rax, [rbp+arg_10]
0x180016f60  mov     [rsp+50h+entriesread], rax; entriesread
0x180016f65  mov     [rsp+50h+prefmaxlen], 0FFFFFFFFh; prefmaxlen
0x180016f6d  call    cs:__imp_NetLocalGroupGetMembers
0x180016f74  nop     dword ptr [rax+rax+00h]
0x180016f79  mov     ebx, eax
0x180016f7b  cmp     eax, 8ACh
0x180016f80  jz      short loc_180016FFA
0x180016f82  cmp     eax, 560h
0x180016f87  jz      short loc_180016FFA
0x180016f89  test    eax, eax
0x180016f8b  jnz     short loc_180016FCA
0x180016f8d  mov     eax, [rbp+arg_0]
0x180016f90  test    eax, eax
0x180016f92  jz      short loc_180016FBC
0x180016f94  mov     rdx, [rbp+bufptr]
0x180016f98  lea     rcx, [rbx+rbx*2]
0x180016f9c  mov     rdx, [rdx+rcx*8]; pSid2
0x180016fa0  mov     rcx, r14; pSid1
0x180016fa3  call    cs:__imp_EqualSid
0x180016faa  nop     dword ptr [rax+rax+00h]
0x180016faf  test    eax, eax
0x180016fb1  jnz     short loc_180016FFC
0x180016fb3  mov     eax, [rbp+arg_0]
0x180016fb6  add     ebx, edi
0x180016fb8  cmp     ebx, eax
0x180016fba  jb      short loc_180016F94
0x180016fbc  cmp     eax, [rbp+arg_10]
0x180016fbf  jnb     short loc_180016FFA
0x180016fc1  mov     rcx, [rbp+bufptr]
0x180016fc5  jmp     loc_180016F10
0x180016fca  jle     short loc_180016FD5
0x180016fcc  movzx   ebx, ax
0x180016fcf  or      ebx, 80070000h
0x180016fd5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180016fdc  jz      short loc_180017000
0x180016fde  lea     rax, aCbrNtstatus0; "CBR(ntStatus == 0)"
0x180016fe5  mov     r8d, ebx
0x180016fe8  mov     [rsp+50h+entriesread], rax
0x180016fed  mov     [rsp+50h+prefmaxlen], 26Bh
0x180016ff5  jmp     loc_180016ECC
0x180016ffa  xor     edi, edi
0x180016ffc  xor     ebx, ebx
0x180016ffe  mov     [rsi], edi
0x180017000  mov     rcx, [rbp+bufptr]; Buffer
0x180017004  test    rcx, rcx
0x180017007  jz      short loc_180017015
0x180017009  call    cs:__imp_NetApiBufferFree
0x180017010  nop     dword ptr [rax+rax+00h]
0x180017015  mov     eax, ebx
0x180017017  add     rsp, 50h
0x18001701b  pop     r14
0x18001701d  pop     rdi
0x18001701e  pop     rsi
0x18001701f  pop     rbx
0x180017020  pop     rbp
0x180017021  retn
```
