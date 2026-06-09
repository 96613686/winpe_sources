# MdmAccountHelper::IsAdminBySid(void *,int *,int *)

- ea: `0x180016bb4`
- end: `0x180016e6f`
- name: `?IsAdminBySid@MdmAccountHelper@@CAJPEAXPEAH1@Z`
- size: `699`
- prototype: `__int64 __fastcall(void *, int *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800146d4`
- `0x180015270`

## callees

- `0x1800065c0`
- `0x180016bb4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180016d13`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180016d13`
- `samcli!NetUserEnum` at `0x180016c9c`
- `samcli!NetUserEnum` at `0x180016c9c`
- `samcli!NetUserGetInfo` at `0x180016cf2`
- `samcli!NetUserGetInfo` at `0x180016cf2`
- `netutils!NetApiBufferFree` at `0x180016d78`
- `netutils!NetApiBufferFree` at `0x180016dbc`
- `netutils!NetApiBufferFree` at `0x180016e48`
- `netutils!NetApiBufferFree` at `0x180016d78`
- `netutils!NetApiBufferFree` at `0x180016dbc`
- `netutils!NetApiBufferFree` at `0x180016e48`

## string_xrefs

- `0x180016d5b`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180016e33`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180016e1c`: `CHR(IsAdminBySidAndName(pTempBuffer->usri0_name, pSid, &fFoundMatch, &fIsAdmin))`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::IsAdminBySid(void *a1, int *a2, int *a3)
{
  unsigned int v5; // ebx
  int v6; // r13d
  signed int v7; // eax
  int v8; // edx
  int v9; // ecx
  signed int v10; // edi
  LPBYTE v11; // rsi
  int v12; // r12d
  const WCHAR *v13; // rdx
  int v14; // r13d
  signed int Info; // eax
  int v16; // ecx
  char prefmaxlen; // [rsp+20h] [rbp-40h]
  const char *entriesread; // [rsp+28h] [rbp-38h]
  DWORD resume_handle; // [rsp+40h] [rbp-20h] BYREF
  DWORD totalentries; // [rsp+44h] [rbp-1Ch] BYREF
  LPBYTE bufptr; // [rsp+48h] [rbp-18h] BYREF
  LPBYTE v23; // [rsp+50h] [rbp-10h] BYREF
  int v25; // [rsp+A8h] [rbp+48h]
  DWORD v26; // [rsp+B8h] [rbp+58h] BYREF

  bufptr = 0;
  v26 = 0;
  totalentries = 0;
  resume_handle = 0;
  if ( a2 )
  {
    *a2 = 0;
    if ( a3 )
    {
      v5 = 0;
      v6 = 0;
      *a3 = 0;
      v25 = 0;
      while ( 1 )
      {
        v7 = NetUserEnum(0, 0, 2u, &bufptr, 0xFFFFFFFF, &v26, &totalentries, &resume_handle);
        v10 = v7;
        if ( v7 )
        {
          if ( v7 != 234 )
            break;
        }
        v11 = bufptr;
        v12 = 0;
        if ( v26 )
        {
          while ( 1 )
          {
            if ( !v11 )
              goto LABEL_26;
            v13 = *(const WCHAR **)v11;
            v14 = 0;
            v23 = 0;
            v25 = 0;
            Info = NetUserGetInfo(0, v13, 4u, &v23);
            v5 = Info;
            if ( Info )
            {
              if ( Info > 0 )
                v5 = (unsigned __int16)Info | 0x80070000;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v16,
                  v8,
                  v5,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
                  45,
                  "CBR(nStatus == 0)");
            }
            else if ( EqualSid(a1, *((PSID *)v23 + 19)) )
            {
              v25 = 1;
              LOBYTE(v14) = *((_DWORD *)v23 + 5) == 2;
            }
            v9 = (int)v23;
            if ( v23 )
              NetApiBufferFree(v23);
            if ( (v5 & 0x80000000) != 0 )
              break;
            if ( v25 )
            {
              *a3 = v14;
              *a2 = 1;
LABEL_26:
              v6 = v25;
              goto LABEL_27;
            }
            v11 += 8;
            if ( ++v12 >= v26 )
              goto LABEL_26;
          }
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          {
            entriesread = "CHR(IsAdminBySidAndName(pTempBuffer->usri0_name, pSid, &fFoundMatch, &fIsAdmin))";
            prefmaxlen = -4;
            goto LABEL_39;
          }
          goto LABEL_40;
        }
LABEL_27:
        if ( bufptr )
        {
          NetApiBufferFree(bufptr);
          bufptr = 0;
        }
        if ( v10 != 234 || v6 )
          goto LABEL_40;
      }
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      else
        v5 = v7;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        entriesread = "CBR(nStatus == 0 || nStatus == 234L)";
        prefmaxlen = -15;
LABEL_39:
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v8,
          v5,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
          prefmaxlen,
          entriesread);
      }
    }
    else
    {
      v5 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        return v5;
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
        225,
        "CPR(pfIsAdmin)");
    }
  }
  else
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      return v5;
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      0,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      222,
      "CPR(pfFoundMatch)");
  }
LABEL_40:
  if ( bufptr )
    NetApiBufferFree(bufptr);
  return v5;
}

```

## disassembly

```asm
0x180016bb4  mov     [rsp-38h+arg_10], rbx
0x180016bb9  mov     [rsp-38h+pSid1], rcx
0x180016bbe  push    rbp
0x180016bbf  push    rsi
0x180016bc0  push    rdi
0x180016bc1  push    r12
0x180016bc3  push    r13
0x180016bc5  push    r14
0x180016bc7  push    r15
0x180016bc9  mov     rbp, rsp
0x180016bcc  sub     rsp, 60h
0x180016bd0  mov     [rbp+bufptr], 0
0x180016bd8  mov     r15, r8
0x180016bdb  mov     [rbp+arg_18], 0
0x180016be2  mov     r14, rdx
0x180016be5  mov     [rbp+var_1C], 0
0x180016bec  mov     [rbp+var_20], 0
0x180016bf3  test    rdx, rdx
0x180016bf6  jnz     short loc_180016C27
0x180016bf8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180016bff  mov     r8d, 80070057h
0x180016c05  mov     ebx, r8d
0x180016c08  jz      loc_180016E54
0x180016c0e  lea     rax, aCprPffoundmatc; "CPR(pfFoundMatch)"
0x180016c15  mov     [rsp+60h+entriesread], rax
0x180016c1a  mov     dword ptr [rsp+60h+prefmaxlen], 1DEh
0x180016c22  jmp     loc_180016E33
0x180016c27  mov     dword ptr [rdx], 0
0x180016c2d  test    r15, r15
0x180016c30  jnz     short loc_180016C61
0x180016c32  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180016c39  mov     r8d, 80070057h
0x180016c3f  mov     ebx, r8d
0x180016c42  jz      loc_180016E54
0x180016c48  lea     rax, aCprPfisadmin; "CPR(pfIsAdmin)"
0x180016c4f  mov     [rsp+60h+entriesread], rax
0x180016c54  mov     dword ptr [rsp+60h+prefmaxlen], 1E1h
0x180016c5c  jmp     loc_180016E33
0x180016c61  xor     ebx, ebx
0x180016c63  xor     r13d, r13d
0x180016c66  mov     [r8], ebx
0x180016c69  mov     [rbp+arg_8], r13d
0x180016c6d  lea     rax, [rbp+var_20]
0x180016c71  xor     edx, edx; level
0x180016c73  mov     [rsp+60h+resume_handle], rax; resume_handle
0x180016c78  lea     r9, [rbp+bufptr]; bufptr
0x180016c7c  lea     rax, [rbp+var_1C]
0x180016c80  xor     ecx, ecx; servername
0x180016c82  mov     [rsp+60h+totalentries], rax; totalentries
0x180016c87  lea     rax, [rbp+arg_18]
0x180016c8b  mov     [rsp+60h+entriesread], rax; entriesread
0x180016c90  lea     r8d, [rdx+2]; filter
0x180016c94  mov     dword ptr [rsp+60h+prefmaxlen], 0FFFFFFFFh; prefmaxlen
0x180016c9c  call    cs:__imp_NetUserEnum
0x180016ca3  nop     dword ptr [rax+rax+00h]
0x180016ca8  mov     edi, eax
0x180016caa  test    eax, eax
0x180016cac  jz      short loc_180016CB9
0x180016cae  cmp     eax, 0EAh
0x180016cb3  jnz     loc_180016DE3
0x180016cb9  mov     rsi, [rbp+bufptr]
0x180016cbd  xor     r12d, r12d
0x180016cc0  cmp     [rbp+arg_18], r12d
0x180016cc4  jbe     loc_180016DB3
0x180016cca  test    rsi, rsi
0x180016ccd  jz      loc_180016DAF
0x180016cd3  mov     rdx, [rsi]; username
0x180016cd6  lea     r9, [rbp+var_10]; bufptr
0x180016cda  xor     r13d, r13d
0x180016cdd  mov     [rbp+var_10], 0
0x180016ce5  xor     ecx, ecx; servername
0x180016ce7  mov     [rbp+arg_8], 0
0x180016cee  lea     r8d, [r13+4]; level
0x180016cf2  call    cs:__imp_NetUserGetInfo
0x180016cf9  nop     dword ptr [rax+rax+00h]
0x180016cfe  mov     ebx, eax
0x180016d00  test    eax, eax
0x180016d02  jnz     short loc_180016D38
0x180016d04  mov     rdx, [rbp+var_10]
0x180016d08  mov     rcx, [rbp+pSid1]; pSid1
0x180016d0c  mov     rdx, [rdx+98h]; pSid2
0x180016d13  call    cs:__imp_EqualSid
0x180016d1a  nop     dword ptr [rax+rax+00h]
0x180016d1f  test    eax, eax
0x180016d21  jz      short loc_180016D6F
0x180016d23  mov     rax, [rbp+var_10]
0x180016d27  mov     [rbp+arg_8], 1
0x180016d2e  cmp     dword ptr [rax+14h], 2
0x180016d32  setz    r13b
0x180016d36  jmp     short loc_180016D6F
0x180016d38  jle     short loc_180016D43
0x180016d3a  movzx   ebx, ax
0x180016d3d  or      ebx, 80070000h
0x180016d43  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180016d4a  jz      short loc_180016D6F
0x180016d4c  lea     rax, aCbrNstatus0; "CBR(nStatus == 0)"
0x180016d53  mov     r8d, ebx
0x180016d56  mov     [rsp+60h+entriesread], rax
0x180016d5b  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180016d62  mov     dword ptr [rsp+60h+prefmaxlen], 22Dh
0x180016d6a  call    McTemplateU0dsqs_EventWriteTransfer
0x180016d6f  mov     rcx, [rbp+var_10]; Buffer
0x180016d73  test    rcx, rcx
0x180016d76  jz      short loc_180016D84
0x180016d78  call    cs:__imp_NetApiBufferFree
0x180016d7f  nop     dword ptr [rax+rax+00h]
0x180016d84  test    ebx, ebx
0x180016d86  js      loc_180016E13
0x180016d8c  cmp     [rbp+arg_8], 0
0x180016d90  jnz     short loc_180016DA5
0x180016d92  add     rsi, 8
0x180016d96  inc     r12d
0x180016d99  cmp     r12d, [rbp+arg_18]
0x180016d9d  jb      loc_180016CCA
0x180016da3  jmp     short loc_180016DAF
0x180016da5  mov     [r15], r13d
0x180016da8  mov     dword ptr [r14], 1
0x180016daf  mov     r13d, [rbp+arg_8]
0x180016db3  mov     rcx, [rbp+bufptr]; Buffer
0x180016db7  test    rcx, rcx
0x180016dba  jz      short loc_180016DD0
0x180016dbc  call    cs:__imp_NetApiBufferFree
0x180016dc3  nop     dword ptr [rax+rax+00h]
0x180016dc8  mov     [rbp+bufptr], 0
0x180016dd0  cmp     edi, 0EAh
0x180016dd6  jnz     short loc_180016E3F
0x180016dd8  test    r13d, r13d
0x180016ddb  jz      loc_180016C6D
0x180016de1  jmp     short loc_180016E3F
0x180016de3  test    edi, edi
0x180016de5  jg      short loc_180016DEB
0x180016de7  mov     ebx, edi
0x180016de9  jmp     short loc_180016DF4
0x180016deb  movzx   ebx, di
0x180016dee  or      ebx, 80070000h
0x180016df4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180016dfb  jz      short loc_180016E3F
0x180016dfd  lea     rax, aCbrNstatus0Nst; "CBR(nStatus == 0 || nStatus == 234L)"
0x180016e04  mov     [rsp+60h+entriesread], rax
0x180016e09  mov     dword ptr [rsp+60h+prefmaxlen], 1F1h
0x180016e11  jmp     short loc_180016E30
0x180016e13  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180016e1a  jz      short loc_180016E3F
0x180016e1c  lea     rax, aChrIsadminbysi; "CHR(IsAdminBySidAndName(pTempBuffer->us"...
0x180016e23  mov     [rsp+60h+entriesread], rax
0x180016e28  mov     dword ptr [rsp+60h+prefmaxlen], 1FCh
0x180016e30  mov     r8d, ebx
0x180016e33  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180016e3a  call    McTemplateU0dsqs_EventWriteTransfer
0x180016e3f  mov     rcx, [rbp+bufptr]; Buffer
0x180016e43  test    rcx, rcx
0x180016e46  jz      short loc_180016E54
0x180016e48  call    cs:__imp_NetApiBufferFree
0x180016e4f  nop     dword ptr [rax+rax+00h]
0x180016e54  mov     eax, ebx
0x180016e56  mov     rbx, [rsp+60h+arg_10]
0x180016e5e  add     rsp, 60h
0x180016e62  pop     r15
0x180016e64  pop     r14
0x180016e66  pop     r13
0x180016e68  pop     r12
0x180016e6a  pop     rdi
0x180016e6b  pop     rsi
0x180016e6c  pop     rbp
0x180016e6d  retn
```
