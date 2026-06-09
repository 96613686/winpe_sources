# GetLatestSidKey(ushort const *,int,uchar * *,ulong *,uchar *,ulong,ulong)

- ea: `0x180019a6c`
- end: `0x180019be3`
- name: `?GetLatestSidKey@@YAJPEBGHPEAPEAEPEAKPEAEKK@Z`
- size: `375`
- prototype: `__int64 __fastcall(LPCWSTR StringSid, int, unsigned __int8 **, unsigned int *, unsigned __int8 *, ULONG SecurityDescriptorSize, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017850`

## callees

- `0x180003e70`
- `0x180010950`
- `0x180018520`
- `0x1800196cc`
- `0x180019a6c`
- `0x18001a450`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180019aed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180019aed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180019b26`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180019b26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019bc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b30`

## string_xrefs

- `0x180019b05`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180019ba4`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`

## pseudocode

```c
__int64 __fastcall GetLatestSidKey(
        LPCWSTR StringSid,
        int a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int8 *a5,
        ULONG SecurityDescriptorSize,
        unsigned int a7)
{
  DWORD LastError; // eax
  unsigned int v12; // r9d
  unsigned int v13; // ebx
  int LatestKey; // eax
  unsigned int v15; // r9d
  unsigned int v16; // ecx
  unsigned int v18; // [rsp+28h] [rbp-30h]
  PSID Sid; // [rsp+40h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+90h] [rbp+38h] BYREF

  Sid = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids, StringSid);
  if ( !StringSid || !*StringSid )
  {
    v13 = -2147024809;
    v15 = 1677;
    v16 = -2147024809;
    goto LABEL_19;
  }
  if ( a2 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            StringSid,
            1u,
            &SecurityDescriptor,
            &SecurityDescriptorSize) )
    {
      LastError = GetLastError();
      v12 = 1690;
LABEL_9:
      SidKeyDebugTraceError(
        LastError,
        "GetLastError()",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
        v12);
      v13 = -2147024809;
      goto LABEL_20;
    }
LABEL_15:
    LatestKey = GetLatestKey(
                  (struct _SECURITY_DESCRIPTOR *)SecurityDescriptor,
                  SecurityDescriptorSize,
                  a3,
                  a4,
                  a5,
                  v18,
                  a7);
    v13 = LatestKey;
    if ( LatestKey >= 0 )
    {
      v13 = 0;
      goto LABEL_20;
    }
    v15 = 1757;
    goto LABEL_14;
  }
  if ( !ConvertStringSidToSidW(StringSid, &Sid) )
  {
    LastError = GetLastError();
    v12 = 1703;
    goto LABEL_9;
  }
  LatestKey = ConvertSIDToSD(Sid, (struct _SECURITY_DESCRIPTOR **)&SecurityDescriptor, &SecurityDescriptorSize);
  v13 = LatestKey;
  if ( LatestKey >= 0 )
    goto LABEL_15;
  v15 = 1716;
LABEL_14:
  v16 = LatestKey;
LABEL_19:
  SidKeyDebugTraceError(v16, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx", v15);
LABEL_20:
  if ( Sid )
    LocalFree(Sid);
  if ( SecurityDescriptor )
    SIDKeyProvFree(SecurityDescriptor);
  return v13;
}

```

## disassembly

```asm
0x180019a6c  push    rbp
0x180019a6e  push    rbx
0x180019a6f  push    rsi
0x180019a70  push    rdi
0x180019a71  push    r14
0x180019a73  push    r15
0x180019a75  mov     rbp, rsp
0x180019a78  sub     rsp, 58h
0x180019a7c  xor     r15d, r15d
0x180019a7f  mov     rsi, r9
0x180019a82  mov     [rbp+Sid], r15
0x180019a86  mov     r14, r8
0x180019a89  mov     [rbp+SecurityDescriptor], r15
0x180019a8d  mov     edi, edx
0x180019a8f  mov     [rbp+SecurityDescriptorSize], r15d
0x180019a93  mov     rbx, rcx
0x180019a96  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a9d  lea     rax, WPP_GLOBAL_Control
0x180019aa4  cmp     rcx, rax
0x180019aa7  jz      short loc_180019AC6
0x180019aa9  test    byte ptr [rcx+1Ch], 4
0x180019aad  jz      short loc_180019AC6
0x180019aaf  mov     rcx, [rcx+10h]
0x180019ab3  lea     edx, [r15+13h]
0x180019ab7  mov     r9, rbx
0x180019aba  lea     r8, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids
0x180019ac1  call    WPP_SF_S
0x180019ac6  test    rbx, rbx
0x180019ac9  jz      loc_180019B94
0x180019acf  cmp     [rbx], r15w
0x180019ad3  jz      loc_180019B94
0x180019ad9  mov     rcx, rbx; StringSid
0x180019adc  test    edi, edi
0x180019ade  jz      short loc_180019B22
0x180019ae0  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x180019ae4  mov     edx, 1; StringSDRevision
0x180019ae9  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180019aed  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180019af3  test    eax, eax
0x180019af5  jnz     short loc_180019B5F
0x180019af7  call    cs:__imp_GetLastError
0x180019afd  mov     r9d, 69Ah; unsigned int
0x180019b03  mov     ecx, eax; unsigned int
0x180019b05  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180019b0c  lea     rdx, aGetlasterror; "GetLastError()"
0x180019b13  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180019b18  mov     ebx, 80070057h
0x180019b1d  jmp     loc_180019BB7
0x180019b22  lea     rdx, [rbp+Sid]; Sid
0x180019b26  call    cs:__imp_ConvertStringSidToSidW
0x180019b2c  test    eax, eax
0x180019b2e  jnz     short loc_180019B3E
0x180019b30  call    cs:__imp_GetLastError
0x180019b36  mov     r9d, 6A7h
0x180019b3c  jmp     short loc_180019B03
0x180019b3e  mov     rcx, [rbp+Sid]; pSid
0x180019b42  lea     r8, [rbp+SecurityDescriptorSize]; unsigned int *
0x180019b46  lea     rdx, [rbp+SecurityDescriptor]; struct _SECURITY_DESCRIPTOR **
0x180019b4a  call    ?ConvertSIDToSD@@YAJPEAXPEAPEAU_SECURITY_DESCRIPTOR@@PEAK@Z; ConvertSIDToSD(void *,_SECURITY_DESCRIPTOR * *,ulong *)
0x180019b4f  mov     ebx, eax
0x180019b51  test    eax, eax
0x180019b53  jns     short loc_180019B5F
0x180019b55  mov     r9d, 6B4h
0x180019b5b  mov     ecx, eax
0x180019b5d  jmp     short loc_180019BA4
0x180019b5f  mov     eax, [rbp+arg_30]
0x180019b62  mov     r9, rsi; unsigned int *
0x180019b65  mov     edx, [rbp+SecurityDescriptorSize]; unsigned int
0x180019b68  mov     r8, r14; unsigned __int8 **
0x180019b6b  mov     rcx, [rbp+SecurityDescriptor]; struct _SECURITY_DESCRIPTOR *
0x180019b6f  mov     [rsp+58h+var_28], eax; unsigned int
0x180019b73  mov     rax, [rbp+arg_20]
0x180019b77  mov     [rsp+58h+var_38], rax; unsigned __int8 *
0x180019b7c  call    ?GetLatestKey@@YAJPEAU_SECURITY_DESCRIPTOR@@KPEAPEAEPEAKPEAEKK@Z; GetLatestKey(_SECURITY_DESCRIPTOR *,ulong,uchar * *,ulong *,uchar *,ulong,ulong)
0x180019b81  mov     ebx, eax
0x180019b83  test    eax, eax
0x180019b85  jns     short loc_180019B8F
0x180019b87  mov     r9d, 6DDh
0x180019b8d  jmp     short loc_180019B5B
0x180019b8f  mov     ebx, r15d
0x180019b92  jmp     short loc_180019BB7
0x180019b94  mov     ebx, 80070057h
0x180019b99  mov     r9d, 68Dh; unsigned int
0x180019b9f  mov     ecx, 80070057h; unsigned int
0x180019ba4  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180019bab  lea     rdx, aHr; "hr"
0x180019bb2  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180019bb7  mov     rcx, [rbp+Sid]; hMem
0x180019bbb  test    rcx, rcx
0x180019bbe  jz      short loc_180019BC6
0x180019bc0  call    cs:__imp_LocalFree
0x180019bc6  mov     rcx, [rbp+SecurityDescriptor]; lpMem
0x180019bca  test    rcx, rcx
0x180019bcd  jz      short loc_180019BD4
0x180019bcf  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180019bd4  mov     eax, ebx
0x180019bd6  add     rsp, 58h
0x180019bda  pop     r15
0x180019bdc  pop     r14
0x180019bde  pop     rdi
0x180019bdf  pop     rsi
0x180019be0  pop     rbx
0x180019be1  pop     rbp
0x180019be2  retn
```
