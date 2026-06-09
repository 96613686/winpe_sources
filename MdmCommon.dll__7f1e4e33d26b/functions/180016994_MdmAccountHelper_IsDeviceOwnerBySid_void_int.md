# MdmAccountHelper::IsDeviceOwnerBySid(void *,int *)

- ea: `0x180016994`
- end: `0x180016b26`
- name: `?IsDeviceOwnerBySid@MdmAccountHelper@@CAJPEAXPEAH@Z`
- size: `402`
- prototype: `__int64 __fastcall(PSID pSid1, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800142c8`
- `0x180014e2c`

## callees

- `0x180006548`
- `0x180016994`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180016ab3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180016ab3`
- `samcli!NetLocalGroupGetMembers` at `0x180016a83`
- `samcli!NetLocalGroupGetMembers` at `0x180016a83`
- `netutils!NetApiBufferFree` at `0x180016a3f`
- `netutils!NetApiBufferFree` at `0x180016b13`
- `netutils!NetApiBufferFree` at `0x180016a3f`
- `netutils!NetApiBufferFree` at `0x180016b13`

## string_xrefs

- `0x1800169e8`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x1800169d4`: `CPR(pSid)`

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
0x180016994  push    rbp
0x180016996  push    rbx
0x180016997  push    rsi
0x180016998  push    rdi
0x180016999  push    r14
0x18001699b  mov     rbp, rsp
0x18001699e  sub     rsp, 50h
0x1800169a2  mov     r14, rcx
0x1800169a5  mov     [rbp+var_10], 0
0x1800169ad  xor     ecx, ecx; Buffer
0x1800169af  mov     rsi, rdx
0x1800169b2  mov     [rbp+bufptr], rcx
0x1800169b6  lea     edi, [rcx+1]
0x1800169b9  test    r14, r14
0x1800169bc  jnz     short loc_1800169F9
0x1800169be  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x1800169c5  mov     r8d, 80070057h
0x1800169cb  mov     ebx, r8d
0x1800169ce  jz      loc_180016B19
0x1800169d4  lea     rax, aCprPsid; "CPR(pSid)"
0x1800169db  mov     [rsp+50h+entriesread], rax
0x1800169e0  mov     [rsp+50h+prefmaxlen], 249h
0x1800169e8  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800169ef  call    McTemplateU0dsqs_EventWriteTransfer
0x1800169f4  jmp     loc_180016B0A
0x1800169f9  test    rsi, rsi
0x1800169fc  jnz     short loc_180016A2A
0x1800169fe  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180016a05  mov     r8d, 80070057h
0x180016a0b  mov     ebx, r8d
0x180016a0e  jz      loc_180016B19
0x180016a14  lea     rax, aCprPfisdeviceo; "CPR(pfIsDeviceOwner)"
0x180016a1b  mov     [rsp+50h+entriesread], rax
0x180016a20  mov     [rsp+50h+prefmaxlen], 24Ah
0x180016a28  jmp     short loc_1800169E8
0x180016a2a  mov     [rdx], ecx
0x180016a2c  mov     [rbp+arg_10], 0
0x180016a33  mov     [rbp+arg_0], 0
0x180016a3a  test    rcx, rcx
0x180016a3d  jz      short loc_180016A4D
0x180016a3f  call    cs:__imp_NetApiBufferFree
0x180016a45  mov     [rbp+bufptr], 0
0x180016a4d  lea     rax, [rbp+var_10]
0x180016a51  mov     r8d, 2; level
0x180016a57  mov     [rsp+50h+resumehandle], rax; resumehandle
0x180016a5c  lea     r9, [rbp+bufptr]; bufptr
0x180016a60  lea     rax, [rbp+arg_0]
0x180016a64  xor     ecx, ecx; servername
0x180016a66  mov     [rsp+50h+totalentries], rax; totalentries
0x180016a6b  lea     rdx, localgroupname; "Device Owners"
0x180016a72  lea     rax, [rbp+arg_10]
0x180016a76  mov     [rsp+50h+entriesread], rax; entriesread
0x180016a7b  mov     [rsp+50h+prefmaxlen], 0FFFFFFFFh; prefmaxlen
0x180016a83  call    cs:__imp_NetLocalGroupGetMembers
0x180016a89  mov     ebx, eax
0x180016a8b  cmp     eax, 8ACh
0x180016a90  jz      short loc_180016B04
0x180016a92  cmp     eax, 560h
0x180016a97  jz      short loc_180016B04
0x180016a99  test    eax, eax
0x180016a9b  jnz     short loc_180016AD4
0x180016a9d  mov     eax, [rbp+arg_0]
0x180016aa0  test    eax, eax
0x180016aa2  jz      short loc_180016AC6
0x180016aa4  mov     rdx, [rbp+bufptr]
0x180016aa8  lea     rcx, [rbx+rbx*2]
0x180016aac  mov     rdx, [rdx+rcx*8]; pSid2
0x180016ab0  mov     rcx, r14; pSid1
0x180016ab3  call    cs:__imp_EqualSid
0x180016ab9  test    eax, eax
0x180016abb  jnz     short loc_180016B06
0x180016abd  mov     eax, [rbp+arg_0]
0x180016ac0  add     ebx, edi
0x180016ac2  cmp     ebx, eax
0x180016ac4  jb      short loc_180016AA4
0x180016ac6  cmp     eax, [rbp+arg_10]
0x180016ac9  jnb     short loc_180016B04
0x180016acb  mov     rcx, [rbp+bufptr]
0x180016acf  jmp     loc_180016A2C
0x180016ad4  jle     short loc_180016ADF
0x180016ad6  movzx   ebx, ax
0x180016ad9  or      ebx, 80070000h
0x180016adf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180016ae6  jz      short loc_180016B0A
0x180016ae8  lea     rax, aCbrNtstatus0; "CBR(ntStatus == 0)"
0x180016aef  mov     r8d, ebx
0x180016af2  mov     [rsp+50h+entriesread], rax
0x180016af7  mov     [rsp+50h+prefmaxlen], 26Bh
0x180016aff  jmp     loc_1800169E8
0x180016b04  xor     edi, edi
0x180016b06  xor     ebx, ebx
0x180016b08  mov     [rsi], edi
0x180016b0a  mov     rcx, [rbp+bufptr]; Buffer
0x180016b0e  test    rcx, rcx
0x180016b11  jz      short loc_180016B19
0x180016b13  call    cs:__imp_NetApiBufferFree
0x180016b19  mov     eax, ebx
0x180016b1b  add     rsp, 50h
0x180016b1f  pop     r14
0x180016b21  pop     rdi
0x180016b22  pop     rsi
0x180016b23  pop     rbx
0x180016b24  pop     rbp
0x180016b25  retn
```
