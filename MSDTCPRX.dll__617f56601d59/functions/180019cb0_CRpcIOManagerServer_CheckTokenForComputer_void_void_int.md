# CRpcIOManagerServer::CheckTokenForComputer(void *,void *,int *)

- ea: `0x180019cb0`
- end: `0x180019f73`
- name: `?CheckTokenForComputer@CRpcIOManagerServer@@AEAAJPEAX0PEAH@Z`
- size: `707`
- prototype: `__int64 __fastcall(CRpcIOManagerServer *this, void *, void *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000d000`

## callees

- `0x180003cf0`
- `0x180019cb0`
- `0x18001d178`
- `0x18001d184`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f4c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180019e8b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180019f3c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180019e8b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180019f3c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180019e45`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180019f02`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180019e45`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180019f02`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x180019d44`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x180019d44`

## string_xrefs

- `0x180019d29`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180019d67`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180019e71`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180019d16`: `CRpcIOManagerServer::CheckTokenForComputer`
- `0x180019d90`: `CRpcIOManagerServer::CheckTokenForComputer`
- `0x180019def`: `CRpcIOManagerServer::CheckTokenForComputer`
- `0x180019e64`: `Unable to calculate domain comp. SID`
- `0x180019eac`: `Unable to check token for domain comp. membership`
- `0x180019f61`: `Unable to check token for domain cont. membership`
- `0x180019f21`: `Unable to calculate domain cont. SID`
- `0x180019d01`: `Failed to alloc %d bytes for domain SID`
- `0x180019d7b`: `Incoming caller is not in a domain`
- `0x180019ddb`: `Failed to get domain SID for user`
- `0x180019e1f`: `Failed to alloc %d bytes for domain comp. SID`
- `0x180019edc`: `Failed to alloc %d bytes for domain cont. SID`

## pseudocode

```c
__int64 __fastcall CRpcIOManagerServer::CheckTokenForComputer(CRpcIOManagerServer *this, void *a2, void *a3, int *a4)
{
  void *v4; // rsi
  void *v8; // rdi
  void *v9; // rax
  void *v10; // r15
  __int64 v11; // r9
  const wchar_t *v12; // rax
  unsigned int v13; // ebx
  signed int v14; // eax
  const wchar_t *v16; // rax
  __int64 v17; // r9
  void *v18; // rax
  signed int v19; // eax
  signed int v20; // eax
  void *v21; // rax
  signed int v22; // eax
  signed int LastError; // eax
  __int64 v24; // [rsp+28h] [rbp-40h]
  DWORD v25; // [rsp+38h] [rbp-30h]
  DWORD cbDomainSid; // [rsp+70h] [rbp+8h] BYREF
  int v27; // [rsp+74h] [rbp+Ch]

  v27 = HIDWORD(this);
  v4 = 0;
  *a4 = 0;
  v8 = 0;
  cbDomainSid = 68;
  v9 = operator new[](0x44u);
  v10 = v9;
  if ( v9 )
  {
    if ( GetWindowsAccountDomainSid(a3, v9, &cbDomainSid) )
    {
      cbDomainSid = 68;
      v18 = operator new[](0x44u);
      v4 = v18;
      if ( !v18 )
      {
        v12 = L"Failed to alloc %d bytes for domain comp. SID";
        v25 = cbDomainSid;
        v11 = 1147;
        goto LABEL_3;
      }
      if ( CreateWellKnownSid(WinAccountComputersSid, v10, v18, &cbDomainSid) )
      {
        if ( CheckTokenMembership(a2, v4, a4) )
        {
          if ( *a4 )
            goto LABEL_9;
          cbDomainSid = 68;
          v21 = operator new[](0x44u);
          v8 = v21;
          if ( !v21 )
          {
            v12 = L"Failed to alloc %d bytes for domain cont. SID";
            v25 = cbDomainSid;
            v11 = 1194;
            goto LABEL_3;
          }
          if ( CreateWellKnownSid(WinAccountControllersSid, v10, v21, &cbDomainSid) )
          {
            if ( CheckTokenMembership(a2, v8, a4) )
              goto LABEL_9;
            *a4 = 0;
            LastError = GetLastError();
            v13 = LastError;
            if ( LastError > 0 )
              v13 = (unsigned __int16)LastError | 0x80070000;
            v16 = L"Unable to check token for domain cont. membership";
            v17 = 1217;
          }
          else
          {
            v22 = GetLastError();
            v13 = v22;
            if ( v22 > 0 )
              v13 = (unsigned __int16)v22 | 0x80070000;
            v16 = L"Unable to calculate domain cont. SID";
            v17 = 1204;
          }
        }
        else
        {
          *a4 = 0;
          v20 = GetLastError();
          v13 = v20;
          if ( v20 > 0 )
            v13 = (unsigned __int16)v20 | 0x80070000;
          v16 = L"Unable to check token for domain comp. membership";
          v17 = 1170;
        }
      }
      else
      {
        v19 = GetLastError();
        v13 = v19;
        if ( v19 > 0 )
          v13 = (unsigned __int16)v19 | 0x80070000;
        v16 = L"Unable to calculate domain comp. SID";
        v17 = 1157;
      }
    }
    else
    {
      v14 = GetLastError();
      v13 = v14;
      if ( v14 > 0 )
        v13 = (unsigned __int16)v14 | 0x80070000;
      if ( v13 == -2147023639 )
      {
        TraceStringInline(
          1,
          3,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
          1122,
          L"CRpcIOManagerServer::CheckTokenForComputer",
          0,
          L"Incoming caller is not in a domain");
LABEL_9:
        v13 = 0;
        goto LABEL_10;
      }
      v16 = L"Failed to get domain SID for user";
      v17 = 1127;
    }
    LODWORD(v24) = v13;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      v17,
      L"CRpcIOManagerServer::CheckTokenForComputer",
      v24,
      v16);
    goto LABEL_10;
  }
  v11 = 1109;
  v25 = cbDomainSid;
  v12 = L"Failed to alloc %d bytes for domain SID";
LABEL_3:
  LODWORD(v24) = -2147024882;
  v13 = -2147024882;
  TraceStringInline(
    1,
    1,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
    v11,
    L"CRpcIOManagerServer::CheckTokenForComputer",
    v24,
    v12,
    v25);
LABEL_10:
  operator delete(v10);
  operator delete(v4);
  operator delete(v8);
  return v13;
}

```

## disassembly

```asm
0x180019cb0  mov     rax, rsp
0x180019cb3  mov     [rax+10h], rbx
0x180019cb7  mov     [rax+18h], rbp
0x180019cbb  mov     [rax+8], rcx
0x180019cbf  push    rsi
0x180019cc0  push    rdi
0x180019cc1  push    r13
0x180019cc3  push    r14
0x180019cc5  push    r15
0x180019cc7  sub     rsp, 40h
0x180019ccb  xor     esi, esi
0x180019ccd  mov     rbx, r9
0x180019cd0  mov     r14, r8
0x180019cd3  mov     [r9], esi
0x180019cd6  mov     rbp, rdx
0x180019cd9  xor     edi, edi
0x180019cdb  lea     r13d, [rsi+44h]
0x180019cdf  mov     ecx, r13d; unsigned __int64
0x180019ce2  mov     [rax+8], r13d
0x180019ce6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019ceb  mov     r15, rax
0x180019cee  test    rax, rax
0x180019cf1  jnz     short loc_180019D39
0x180019cf3  mov     eax, [rsp+68h+cbDomainSid]
0x180019cf7  mov     r9d, 455h
0x180019cfd  mov     [rsp+68h+var_30], eax
0x180019d01  lea     rax, aFailedToAllocD_1; "Failed to alloc %d bytes for domain SID"
0x180019d08  mov     edx, 8007000Eh
0x180019d0d  mov     [rsp+68h+var_38], rax
0x180019d12  mov     dword ptr [rsp+68h+var_40], edx
0x180019d16  lea     rax, aCrpciomanagers_16; "CRpcIOManagerServer::CheckTokenForCompu"...
0x180019d1d  mov     ecx, 1
0x180019d22  mov     [rsp+68h+var_48], rax
0x180019d27  mov     ebx, edx
0x180019d29  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180019d30  mov     edx, ecx
0x180019d32  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180019d37  jmp     short loc_180019DA8
0x180019d39  lea     r8, [rsp+68h+cbDomainSid]; cbDomainSid
0x180019d3e  mov     rdx, r15; pDomainSid
0x180019d41  mov     rcx, r14; pSid
0x180019d44  call    cs:__imp_GetWindowsAccountDomainSid
0x180019d4a  test    eax, eax
0x180019d4c  jnz     loc_180019E06
0x180019d52  call    cs:__imp_GetLastError
0x180019d58  mov     ebx, eax
0x180019d5a  test    eax, eax
0x180019d5c  jle     short loc_180019D67
0x180019d5e  movzx   ebx, ax
0x180019d61  or      ebx, 80070000h
0x180019d67  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180019d6e  mov     ecx, 1
0x180019d73  cmp     ebx, 800704E9h
0x180019d79  jnz     short loc_180019DDB
0x180019d7b  lea     rax, aIncomingCaller; "Incoming caller is not in a domain"
0x180019d82  mov     r9d, 462h
0x180019d88  mov     [rsp+68h+var_38], rax
0x180019d8d  lea     edx, [rcx+2]
0x180019d90  lea     rax, aCrpciomanagers_16; "CRpcIOManagerServer::CheckTokenForCompu"...
0x180019d97  mov     [rsp+68h+var_40], rsi
0x180019d9c  mov     [rsp+68h+var_48], rax
0x180019da1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180019da6  xor     ebx, ebx
0x180019da8  mov     rcx, r15; Block
0x180019dab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019db0  mov     rcx, rsi; Block
0x180019db3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019db8  mov     rcx, rdi; Block
0x180019dbb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019dc0  lea     r11, [rsp+68h+var_28]
0x180019dc5  mov     eax, ebx
0x180019dc7  mov     rbx, [r11+38h]
0x180019dcb  mov     rbp, [r11+40h]
0x180019dcf  mov     rsp, r11
0x180019dd2  pop     r15
0x180019dd4  pop     r14
0x180019dd6  pop     r13
0x180019dd8  pop     rdi
0x180019dd9  pop     rsi
0x180019dda  retn
0x180019ddb  lea     rax, aFailedToGetDom; "Failed to get domain SID for user"
0x180019de2  mov     r9d, 467h
0x180019de8  mov     [rsp+68h+var_38], rax
0x180019ded  mov     edx, ecx
0x180019def  lea     rax, aCrpciomanagers_16; "CRpcIOManagerServer::CheckTokenForCompu"...
0x180019df6  mov     dword ptr [rsp+68h+var_40], ebx
0x180019dfa  mov     [rsp+68h+var_48], rax
0x180019dff  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180019e04  jmp     short loc_180019DA8
0x180019e06  mov     rcx, r13; unsigned __int64
0x180019e09  mov     [rsp+68h+cbDomainSid], r13d
0x180019e0e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019e13  mov     rsi, rax
0x180019e16  test    rax, rax
0x180019e19  jnz     short loc_180019E35
0x180019e1b  mov     ecx, [rsp+68h+cbDomainSid]
0x180019e1f  lea     rax, aFailedToAllocD; "Failed to alloc %d bytes for domain com"...
0x180019e26  mov     [rsp+68h+var_30], ecx
0x180019e2a  mov     r9d, 47Bh
0x180019e30  jmp     loc_180019D08
0x180019e35  lea     r9, [rsp+68h+cbDomainSid]; cbSid
0x180019e3a  mov     r8, rsi; pSid
0x180019e3d  mov     rdx, r15; DomainSid
0x180019e40  mov     ecx, 2Ch ; ','; WellKnownSidType
0x180019e45  call    cs:__imp_CreateWellKnownSid
0x180019e4b  test    eax, eax
0x180019e4d  jnz     short loc_180019E82
0x180019e4f  call    cs:__imp_GetLastError
0x180019e55  mov     ebx, eax
0x180019e57  test    eax, eax
0x180019e59  jle     short loc_180019E64
0x180019e5b  movzx   ebx, ax
0x180019e5e  or      ebx, 80070000h
0x180019e64  lea     rax, aUnableToCalcul; "Unable to calculate domain comp. SID"
0x180019e6b  mov     r9d, 485h
0x180019e71  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180019e78  mov     ecx, 1
0x180019e7d  jmp     loc_180019DE8
0x180019e82  mov     r8, rbx; IsMember
0x180019e85  mov     rdx, rsi; SidToCheck
0x180019e88  mov     rcx, rbp; TokenHandle
0x180019e8b  call    cs:__imp_CheckTokenMembership
0x180019e91  test    eax, eax
0x180019e93  jnz     short loc_180019EBB
0x180019e95  mov     [rbx], edi
0x180019e97  call    cs:__imp_GetLastError
0x180019e9d  mov     ebx, eax
0x180019e9f  test    eax, eax
0x180019ea1  jle     short loc_180019EAC
0x180019ea3  movzx   ebx, ax
0x180019ea6  or      ebx, 80070000h
0x180019eac  lea     rax, aUnableToCheckT; "Unable to check token for domain comp. "...
0x180019eb3  mov     r9d, 492h
0x180019eb9  jmp     short loc_180019E71
0x180019ebb  cmp     [rbx], edi
0x180019ebd  jnz     loc_180019DA6
0x180019ec3  mov     rcx, r13; unsigned __int64
0x180019ec6  mov     [rsp+68h+cbDomainSid], r13d
0x180019ecb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019ed0  mov     rdi, rax
0x180019ed3  test    rax, rax
0x180019ed6  jnz     short loc_180019EF2
0x180019ed8  mov     ecx, [rsp+68h+cbDomainSid]
0x180019edc  lea     rax, aFailedToAllocD_0; "Failed to alloc %d bytes for domain con"...
0x180019ee3  mov     [rsp+68h+var_30], ecx
0x180019ee7  mov     r9d, 4AAh
0x180019eed  jmp     loc_180019D08
0x180019ef2  lea     r9, [rsp+68h+cbDomainSid]; cbSid
0x180019ef7  mov     r8, rdi; pSid
0x180019efa  mov     rdx, r15; DomainSid
0x180019efd  mov     ecx, 2Dh ; '-'; WellKnownSidType
0x180019f02  call    cs:__imp_CreateWellKnownSid
0x180019f08  test    eax, eax
0x180019f0a  jnz     short loc_180019F33
0x180019f0c  call    cs:__imp_GetLastError
0x180019f12  mov     ebx, eax
0x180019f14  test    eax, eax
0x180019f16  jle     short loc_180019F21
0x180019f18  movzx   ebx, ax
0x180019f1b  or      ebx, 80070000h
0x180019f21  lea     rax, aUnableToCalcul_0; "Unable to calculate domain cont. SID"
0x180019f28  mov     r9d, 4B4h
0x180019f2e  jmp     loc_180019E71
0x180019f33  mov     r8, rbx; IsMember
0x180019f36  mov     rdx, rdi; SidToCheck
0x180019f39  mov     rcx, rbp; TokenHandle
0x180019f3c  call    cs:__imp_CheckTokenMembership
0x180019f42  test    eax, eax
0x180019f44  jnz     loc_180019DA6
0x180019f4a  mov     [rbx], eax
0x180019f4c  call    cs:__imp_GetLastError
0x180019f52  mov     ebx, eax
0x180019f54  test    eax, eax
0x180019f56  jle     short loc_180019F61
0x180019f58  movzx   ebx, ax
0x180019f5b  or      ebx, 80070000h
0x180019f61  lea     rax, aUnableToCheckT_1; "Unable to check token for domain cont. "...
0x180019f68  mov     r9d, 4C1h
0x180019f6e  jmp     loc_180019E71
```
