# MdmAccountHelper::IsAdminBySid(void *,int *,int *)

- ea: `0x1800166f8`
- end: `0x18001698e`
- name: `?IsAdminBySid@MdmAccountHelper@@CAJPEAXPEAH1@Z`
- size: `662`
- prototype: `__int64 __fastcall(void *, int *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800142c8`
- `0x180014e2c`

## callees

- `0x180006548`
- `0x1800166f8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001684b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001684b`
- `samcli!NetUserEnum` at `0x1800167e0`
- `samcli!NetUserEnum` at `0x1800167e0`
- `samcli!NetUserGetInfo` at `0x180016830`
- `samcli!NetUserGetInfo` at `0x180016830`
- `netutils!NetApiBufferFree` at `0x1800168aa`
- `netutils!NetApiBufferFree` at `0x1800168e8`
- `netutils!NetApiBufferFree` at `0x18001696e`
- `netutils!NetApiBufferFree` at `0x1800168aa`
- `netutils!NetApiBufferFree` at `0x1800168e8`
- `netutils!NetApiBufferFree` at `0x18001696e`

## string_xrefs

- `0x18001688d`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180016959`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`
- `0x180016942`: `CHR(IsAdminBySidAndName(pTempBuffer->usri0_name, pSid, &fFoundMatch, &fIsAdmin))`

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
0x1800166f8  mov     [rsp-38h+arg_10], rbx
0x1800166fd  mov     [rsp-38h+pSid1], rcx
0x180016702  push    rbp
0x180016703  push    rsi
0x180016704  push    rdi
0x180016705  push    r12
0x180016707  push    r13
0x180016709  push    r14
0x18001670b  push    r15
0x18001670d  mov     rbp, rsp
0x180016710  sub     rsp, 60h
0x180016714  mov     [rbp+bufptr], 0
0x18001671c  mov     r15, r8
0x18001671f  mov     [rbp+arg_18], 0
0x180016726  mov     r14, rdx
0x180016729  mov     [rbp+var_1C], 0
0x180016730  mov     [rbp+var_20], 0
0x180016737  test    rdx, rdx
0x18001673a  jnz     short loc_18001676B
0x18001673c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180016743  mov     r8d, 80070057h
0x180016749  mov     ebx, r8d
0x18001674c  jz      loc_180016974
0x180016752  lea     rax, aCprPffoundmatc; "CPR(pfFoundMatch)"
0x180016759  mov     [rsp+60h+entriesread], rax
0x18001675e  mov     dword ptr [rsp+60h+prefmaxlen], 1DEh
0x180016766  jmp     loc_180016959
0x18001676b  mov     dword ptr [rdx], 0
0x180016771  test    r15, r15
0x180016774  jnz     short loc_1800167A5
0x180016776  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001677d  mov     r8d, 80070057h
0x180016783  mov     ebx, r8d
0x180016786  jz      loc_180016974
0x18001678c  lea     rax, aCprPfisadmin; "CPR(pfIsAdmin)"
0x180016793  mov     [rsp+60h+entriesread], rax
0x180016798  mov     dword ptr [rsp+60h+prefmaxlen], 1E1h
0x1800167a0  jmp     loc_180016959
0x1800167a5  xor     ebx, ebx
0x1800167a7  xor     r13d, r13d
0x1800167aa  mov     [r8], ebx
0x1800167ad  mov     [rbp+arg_8], r13d
0x1800167b1  lea     rax, [rbp+var_20]
0x1800167b5  xor     edx, edx; level
0x1800167b7  mov     [rsp+60h+resume_handle], rax; resume_handle
0x1800167bc  lea     r9, [rbp+bufptr]; bufptr
0x1800167c0  lea     rax, [rbp+var_1C]
0x1800167c4  xor     ecx, ecx; servername
0x1800167c6  mov     [rsp+60h+totalentries], rax; totalentries
0x1800167cb  lea     rax, [rbp+arg_18]
0x1800167cf  mov     [rsp+60h+entriesread], rax; entriesread
0x1800167d4  lea     r8d, [rdx+2]; filter
0x1800167d8  mov     dword ptr [rsp+60h+prefmaxlen], 0FFFFFFFFh; prefmaxlen
0x1800167e0  call    cs:__imp_NetUserEnum
0x1800167e6  mov     edi, eax
0x1800167e8  test    eax, eax
0x1800167ea  jz      short loc_1800167F7
0x1800167ec  cmp     eax, 0EAh
0x1800167f1  jnz     loc_180016909
0x1800167f7  mov     rsi, [rbp+bufptr]
0x1800167fb  xor     r12d, r12d
0x1800167fe  cmp     [rbp+arg_18], r12d
0x180016802  jbe     loc_1800168DF
0x180016808  test    rsi, rsi
0x18001680b  jz      loc_1800168DB
0x180016811  mov     rdx, [rsi]; username
0x180016814  lea     r9, [rbp+var_10]; bufptr
0x180016818  xor     r13d, r13d
0x18001681b  mov     [rbp+var_10], 0
0x180016823  xor     ecx, ecx; servername
0x180016825  mov     [rbp+arg_8], 0
0x18001682c  lea     r8d, [r13+4]; level
0x180016830  call    cs:__imp_NetUserGetInfo
0x180016836  mov     ebx, eax
0x180016838  test    eax, eax
0x18001683a  jnz     short loc_18001686A
0x18001683c  mov     rdx, [rbp+var_10]
0x180016840  mov     rcx, [rbp+pSid1]; pSid1
0x180016844  mov     rdx, [rdx+98h]; pSid2
0x18001684b  call    cs:__imp_EqualSid
0x180016851  test    eax, eax
0x180016853  jz      short loc_1800168A1
0x180016855  mov     rax, [rbp+var_10]
0x180016859  mov     [rbp+arg_8], 1
0x180016860  cmp     dword ptr [rax+14h], 2
0x180016864  setz    r13b
0x180016868  jmp     short loc_1800168A1
0x18001686a  jle     short loc_180016875
0x18001686c  movzx   ebx, ax
0x18001686f  or      ebx, 80070000h
0x180016875  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001687c  jz      short loc_1800168A1
0x18001687e  lea     rax, aCbrNstatus0; "CBR(nStatus == 0)"
0x180016885  mov     r8d, ebx
0x180016888  mov     [rsp+60h+entriesread], rax
0x18001688d  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180016894  mov     dword ptr [rsp+60h+prefmaxlen], 22Dh
0x18001689c  call    McTemplateU0dsqs_EventWriteTransfer
0x1800168a1  mov     rcx, [rbp+var_10]; Buffer
0x1800168a5  test    rcx, rcx
0x1800168a8  jz      short loc_1800168B0
0x1800168aa  call    cs:__imp_NetApiBufferFree
0x1800168b0  test    ebx, ebx
0x1800168b2  js      loc_180016939
0x1800168b8  cmp     [rbp+arg_8], 0
0x1800168bc  jnz     short loc_1800168D1
0x1800168be  add     rsi, 8
0x1800168c2  inc     r12d
0x1800168c5  cmp     r12d, [rbp+arg_18]
0x1800168c9  jb      loc_180016808
0x1800168cf  jmp     short loc_1800168DB
0x1800168d1  mov     [r15], r13d
0x1800168d4  mov     dword ptr [r14], 1
0x1800168db  mov     r13d, [rbp+arg_8]
0x1800168df  mov     rcx, [rbp+bufptr]; Buffer
0x1800168e3  test    rcx, rcx
0x1800168e6  jz      short loc_1800168F6
0x1800168e8  call    cs:__imp_NetApiBufferFree
0x1800168ee  mov     [rbp+bufptr], 0
0x1800168f6  cmp     edi, 0EAh
0x1800168fc  jnz     short loc_180016965
0x1800168fe  test    r13d, r13d
0x180016901  jz      loc_1800167B1
0x180016907  jmp     short loc_180016965
0x180016909  test    edi, edi
0x18001690b  jg      short loc_180016911
0x18001690d  mov     ebx, edi
0x18001690f  jmp     short loc_18001691A
0x180016911  movzx   ebx, di
0x180016914  or      ebx, 80070000h
0x18001691a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180016921  jz      short loc_180016965
0x180016923  lea     rax, aCbrNstatus0Nst; "CBR(nStatus == 0 || nStatus == 234L)"
0x18001692a  mov     [rsp+60h+entriesread], rax
0x18001692f  mov     dword ptr [rsp+60h+prefmaxlen], 1F1h
0x180016937  jmp     short loc_180016956
0x180016939  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180016940  jz      short loc_180016965
0x180016942  lea     rax, aChrIsadminbysi; "CHR(IsAdminBySidAndName(pTempBuffer->us"...
0x180016949  mov     [rsp+60h+entriesread], rax
0x18001694e  mov     dword ptr [rsp+60h+prefmaxlen], 1FCh
0x180016956  mov     r8d, ebx
0x180016959  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180016960  call    McTemplateU0dsqs_EventWriteTransfer
0x180016965  mov     rcx, [rbp+bufptr]; Buffer
0x180016969  test    rcx, rcx
0x18001696c  jz      short loc_180016974
0x18001696e  call    cs:__imp_NetApiBufferFree
0x180016974  mov     eax, ebx
0x180016976  mov     rbx, [rsp+60h+arg_10]
0x18001697e  add     rsp, 60h
0x180016982  pop     r15
0x180016984  pop     r14
0x180016986  pop     r13
0x180016988  pop     r12
0x18001698a  pop     rdi
0x18001698b  pop     rsi
0x18001698c  pop     rbp
0x18001698d  retn
```
