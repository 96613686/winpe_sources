# GetSpecifiedSidKey(ushort const *,int,ulong,uchar * const,ulong,_SID_KEY_BLOB_VER,uchar *,ulong)

- ea: `0x18001a034`
- end: `0x18001a20d`
- name: `?GetSpecifiedSidKey@@YAJPEBGHKQEAEKW4_SID_KEY_BLOB_VER@@PEAEK@Z`
- size: `473`
- prototype: `__int64 __fastcall(const WCHAR *, int, unsigned int, unsigned __int8 *, unsigned int, unsigned int, __int64, ULONG SecurityDescriptorSize)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017e20`

## callees

- `0x180003e08`
- `0x180009408`
- `0x180010950`
- `0x180018520`
- `0x180019bec`
- `0x18001a034`
- `0x18001a450`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a0ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a0ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001a107`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001a107`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a1b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a1b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a111`

## string_xrefs

- `0x18001a0e6`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x18001a19b`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`

## pseudocode

```c
__int64 __fastcall GetSpecifiedSidKey(
        const WCHAR *a1,
        int a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7,
        ULONG SecurityDescriptorSize)
{
  unsigned int v12; // r9d
  DWORD LastError; // eax
  unsigned int v14; // r9d
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ecx
  int SpecifiedKeyLdap; // eax
  unsigned int v20; // [rsp+38h] [rbp-18h]
  PSID Sid; // [rsp+40h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp+30h] BYREF

  Sid = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids);
  if ( !a1 || !*a1 )
  {
    v12 = 1377;
    goto LABEL_23;
  }
  if ( (a3 & 0xDFFEFFFF) != 0 )
  {
    v12 = 1384;
LABEL_23:
    v15 = -2147024809;
    v17 = -2147024809;
    goto LABEL_24;
  }
  if ( a2 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(a1, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
    {
      LastError = GetLastError();
      v14 = 1397;
LABEL_11:
      SidKeyDebugTraceError(
        LastError,
        "GetLastError()",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
        v14);
      v15 = -2147024809;
      goto LABEL_25;
    }
  }
  else
  {
    if ( !ConvertStringSidToSidW(a1, &Sid) )
    {
      LastError = GetLastError();
      v14 = 1410;
      goto LABEL_11;
    }
    v16 = ConvertSIDToSD(Sid, (struct _SECURITY_DESCRIPTOR **)&SecurityDescriptor, &SecurityDescriptorSize);
    v15 = v16;
    if ( v16 < 0 )
    {
      v12 = 1423;
      v17 = v16;
      goto LABEL_24;
    }
  }
  if ( (a3 & 0x10000) != 0 )
    SpecifiedKeyLdap = GetSpecifiedKeyLdap(SecurityDescriptor, SecurityDescriptorSize, a3, a4);
  else
    SpecifiedKeyLdap = GetSpecifiedKey(
                         (unsigned __int8 *)SecurityDescriptor,
                         SecurityDescriptorSize,
                         a3,
                         a4,
                         a5,
                         a6,
                         a7,
                         v20);
  v15 = SpecifiedKeyLdap;
  if ( SpecifiedKeyLdap >= 0 )
  {
    v15 = 0;
    goto LABEL_25;
  }
  v12 = 1455;
  v17 = SpecifiedKeyLdap;
LABEL_24:
  SidKeyDebugTraceError(v17, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx", v12);
LABEL_25:
  if ( Sid )
    LocalFree(Sid);
  if ( SecurityDescriptor )
    SIDKeyProvFree(SecurityDescriptor);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids);
  return v15;
}

```

## disassembly

```asm
0x18001a034  mov     [rsp-28h+arg_8], rbx
0x18001a039  mov     [rsp-28h+arg_10], rsi
0x18001a03e  push    rbp
0x18001a03f  push    rdi
0x18001a040  push    r12
0x18001a042  push    r14
0x18001a044  push    r15
0x18001a046  mov     rbp, rsp
0x18001a049  sub     rsp, 50h
0x18001a04d  xor     r15d, r15d
0x18001a050  mov     r14, r9
0x18001a053  mov     [rbp+Sid], r15
0x18001a057  mov     edi, r8d
0x18001a05a  mov     [rbp+SecurityDescriptor], r15
0x18001a05e  mov     esi, edx
0x18001a060  mov     [rbp+SecurityDescriptorSize], r15d
0x18001a064  mov     rbx, rcx
0x18001a067  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a06e  lea     r12, WPP_GLOBAL_Control
0x18001a075  cmp     rcx, r12
0x18001a078  jz      short loc_18001A094
0x18001a07a  test    byte ptr [rcx+1Ch], 4
0x18001a07e  jz      short loc_18001A094
0x18001a080  mov     rcx, [rcx+10h]
0x18001a084  lea     edx, [r15+0Ah]
0x18001a088  lea     r8, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids
0x18001a08f  call    WPP_SF_
0x18001a094  test    rbx, rbx
0x18001a097  jz      loc_18001A18B
0x18001a09d  cmp     [rbx], r15w
0x18001a0a1  jz      loc_18001A18B
0x18001a0a7  test    edi, 0DFFEFFFFh
0x18001a0ad  jz      short loc_18001A0BA
0x18001a0af  mov     r9d, 568h
0x18001a0b5  jmp     loc_18001A191
0x18001a0ba  mov     rcx, rbx; StringSid
0x18001a0bd  test    esi, esi
0x18001a0bf  jz      short loc_18001A103
0x18001a0c1  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18001a0c5  mov     edx, 1; StringSDRevision
0x18001a0ca  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001a0ce  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001a0d4  test    eax, eax
0x18001a0d6  jnz     short loc_18001A140
0x18001a0d8  call    cs:__imp_GetLastError
0x18001a0de  mov     r9d, 575h; unsigned int
0x18001a0e4  mov     ecx, eax; unsigned int
0x18001a0e6  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18001a0ed  lea     rdx, aGetlasterror; "GetLastError()"
0x18001a0f4  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18001a0f9  mov     ebx, 80070057h
0x18001a0fe  jmp     loc_18001A1AE
0x18001a103  lea     rdx, [rbp+Sid]; Sid
0x18001a107  call    cs:__imp_ConvertStringSidToSidW
0x18001a10d  test    eax, eax
0x18001a10f  jnz     short loc_18001A11F
0x18001a111  call    cs:__imp_GetLastError
0x18001a117  mov     r9d, 582h
0x18001a11d  jmp     short loc_18001A0E4
0x18001a11f  mov     rcx, [rbp+Sid]; pSid
0x18001a123  lea     r8, [rbp+SecurityDescriptorSize]; unsigned int *
0x18001a127  lea     rdx, [rbp+SecurityDescriptor]; struct _SECURITY_DESCRIPTOR **
0x18001a12b  call    ?ConvertSIDToSD@@YAJPEAXPEAPEAU_SECURITY_DESCRIPTOR@@PEAK@Z; ConvertSIDToSD(void *,_SECURITY_DESCRIPTOR * *,ulong *)
0x18001a130  mov     ebx, eax
0x18001a132  test    eax, eax
0x18001a134  jns     short loc_18001A140
0x18001a136  mov     r9d, 58Fh
0x18001a13c  mov     ecx, eax
0x18001a13e  jmp     short loc_18001A19B
0x18001a140  mov     rax, [rbp+arg_30]
0x18001a144  mov     r9, r14
0x18001a147  mov     edx, [rbp+SecurityDescriptorSize]
0x18001a14a  mov     r8d, edi
0x18001a14d  mov     rcx, [rbp+SecurityDescriptor]
0x18001a151  mov     [rsp+50h+var_20], rax
0x18001a156  mov     eax, [rbp+arg_28]
0x18001a159  mov     [rsp+50h+var_28], eax
0x18001a15d  mov     eax, [rbp+arg_20]
0x18001a160  mov     [rsp+50h+var_30], eax
0x18001a164  bt      edi, 10h
0x18001a168  jnb     short loc_18001A171
0x18001a16a  call    ?GetSpecifiedKeyLdap@@YAJPEAU_SECURITY_DESCRIPTOR@@KKQEAEKW4_SID_KEY_BLOB_VER@@PEAEK@Z; GetSpecifiedKeyLdap(_SECURITY_DESCRIPTOR *,ulong,ulong,uchar * const,ulong,_SID_KEY_BLOB_VER,uchar *,ulong)
0x18001a16f  jmp     short loc_18001A176
0x18001a171  call    ?GetSpecifiedKey@@YAJPEAU_SECURITY_DESCRIPTOR@@KKQEAEKW4_SID_KEY_BLOB_VER@@PEAEK@Z; GetSpecifiedKey(_SECURITY_DESCRIPTOR *,ulong,ulong,uchar * const,ulong,_SID_KEY_BLOB_VER,uchar *,ulong)
0x18001a176  mov     ebx, eax
0x18001a178  test    eax, eax
0x18001a17a  jns     short loc_18001A186
0x18001a17c  mov     r9d, 5AFh
0x18001a182  mov     ecx, eax
0x18001a184  jmp     short loc_18001A19B
0x18001a186  mov     ebx, r15d
0x18001a189  jmp     short loc_18001A1AE
0x18001a18b  mov     r9d, 561h; unsigned int
0x18001a191  mov     ebx, 80070057h
0x18001a196  mov     ecx, 80070057h; unsigned int
0x18001a19b  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18001a1a2  lea     rdx, aHr; "hr"
0x18001a1a9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18001a1ae  mov     rcx, [rbp+Sid]; hMem
0x18001a1b2  test    rcx, rcx
0x18001a1b5  jz      short loc_18001A1BD
0x18001a1b7  call    cs:__imp_LocalFree
0x18001a1bd  mov     rcx, [rbp+SecurityDescriptor]; lpMem
0x18001a1c1  test    rcx, rcx
0x18001a1c4  jz      short loc_18001A1CB
0x18001a1c6  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18001a1cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1d2  cmp     rcx, r12
0x18001a1d5  jz      short loc_18001A1F2
0x18001a1d7  test    byte ptr [rcx+1Ch], 4
0x18001a1db  jz      short loc_18001A1F2
0x18001a1dd  mov     rcx, [rcx+10h]
0x18001a1e1  lea     r8, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids
0x18001a1e8  mov     edx, 0Bh
0x18001a1ed  call    WPP_SF_
0x18001a1f2  lea     r11, [rsp+50h+var_s0]
0x18001a1f7  mov     eax, ebx
0x18001a1f9  mov     rbx, [r11+38h]
0x18001a1fd  mov     rsi, [r11+40h]
0x18001a201  mov     rsp, r11
0x18001a204  pop     r15
0x18001a206  pop     r14
0x18001a208  pop     r12
0x18001a20a  pop     rdi
0x18001a20b  pop     rbp
0x18001a20c  retn
```
