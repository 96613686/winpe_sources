# ACUtil::CreateSecurityAttributesForAppContainer(void *,_SECURITY_ATTRIBUTES *)

- ea: `0x1800664b4`
- end: `0x180066622`
- name: `?CreateSecurityAttributesForAppContainer@ACUtil@@SAJPEAXPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(PSID Sid, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180066168`
- `0x18008610c`

## callees

- `0x180035dd8`
- `0x180061320`
- `0x180062314`
- `0x1800664b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006653f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800665b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006653f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800665b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006657f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006657f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800665aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800665aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180066535`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180066535`

## pseudocode

```c
__int64 __fastcall ACUtil::CreateSecurityAttributesForAppContainer(PSID Sid, struct _SECURITY_ATTRIBUTES *a2)
{
  signed int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  ULONG SecurityDescriptorSize; // [rsp+20h] [rbp-E0h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-D8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v11; // [rsp+38h] [rbp-C8h]
  __int64 v12; // [rsp+48h] [rbp-B8h]
  WCHAR StringSecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[526]; // [rsp+52h] [rbp-AEh] BYREF

  StringSecurityDescriptor = 0;
  memset_0(v14, 0, 0x206u);
  if ( Sid )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
      goto LABEL_7;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
LABEL_7:
      v4 = StringCchPrintfW(&StringSecurityDescriptor, 0x104u, L"D:(A;;GA;;;WD)(A;;GA;;;%s)", StringSid);
    if ( StringSid )
      LocalFree(StringSid);
  }
  else
  {
    v4 = StringCchPrintfW(&StringSecurityDescriptor, 0x104u, L"D:(A;;GA;;;WD)(A;;GA;;;%s)", L"AC");
  }
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          &StringSecurityDescriptor,
          1u,
          &SecurityDescriptor,
          &SecurityDescriptorSize) )
  {
    v6 = GetLastError();
    v4 = v6;
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0x80070000;
  }
  if ( v4 >= 0 )
  {
    *((_QWORD *)&v11 + 1) = SecurityDescriptor;
    *(_QWORD *)&v11 = 24;
    v12 = 1;
    *(_OWORD *)&a2->nLength = v11;
    *(_QWORD *)&a2->bInheritHandle = 1;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800664b4  mov     [rsp-8+arg_10], rbx
0x1800664b9  mov     [rsp-8+arg_18], rdi
0x1800664be  push    rbp
0x1800664bf  lea     rbp, [rsp-170h]
0x1800664c7  sub     rsp, 270h
0x1800664ce  mov     rax, cs:__security_cookie
0x1800664d5  xor     rax, rsp
0x1800664d8  mov     [rbp+170h+var_10], rax
0x1800664df  mov     rdi, rdx
0x1800664e2  mov     rbx, rcx
0x1800664e5  xor     eax, eax
0x1800664e7  lea     rcx, [rsp+270h+var_21E]; void *
0x1800664ec  xor     edx, edx; Val
0x1800664ee  mov     [rsp+270h+StringSecurityDescriptor], ax
0x1800664f3  mov     r8d, 206h; Size
0x1800664f9  call    memset_0
0x1800664fe  test    rbx, rbx
0x180066501  jnz     short loc_180066524
0x180066503  lea     r9, aAc; "AC"
0x18006650a  mov     edx, 104h; unsigned __int64
0x18006650f  lea     r8, aDAGaWdAGaS; "D:(A;;GA;;;WD)(A;;GA;;;%s)"
0x180066516  lea     rcx, [rsp+270h+StringSecurityDescriptor]; Buffer
0x18006651b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180066520  mov     ebx, eax
0x180066522  jmp     short loc_180066585
0x180066524  lea     rdx, [rsp+270h+StringSid]; StringSid
0x180066529  mov     [rsp+270h+StringSid], 0
0x180066532  mov     rcx, rbx; Sid
0x180066535  call    cs:__imp_ConvertSidToStringSidW
0x18006653b  test    eax, eax
0x18006653d  jnz     short loc_180066558
0x18006653f  call    cs:__imp_GetLastError
0x180066545  mov     ebx, eax
0x180066547  test    eax, eax
0x180066549  jle     short loc_180066554
0x18006654b  movzx   ebx, ax
0x18006654e  or      ebx, 80070000h
0x180066554  test    ebx, ebx
0x180066556  js      short loc_180066575
0x180066558  mov     r9, [rsp+270h+StringSid]
0x18006655d  lea     r8, aDAGaWdAGaS; "D:(A;;GA;;;WD)(A;;GA;;;%s)"
0x180066564  mov     edx, 104h; unsigned __int64
0x180066569  lea     rcx, [rsp+270h+StringSecurityDescriptor]; Buffer
0x18006656e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180066573  mov     ebx, eax
0x180066575  mov     rcx, [rsp+270h+StringSid]; hMem
0x18006657a  test    rcx, rcx
0x18006657d  jz      short loc_180066585
0x18006657f  call    cs:__imp_LocalFree
0x180066585  lea     r9, [rsp+270h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18006658a  mov     [rsp+270h+SecurityDescriptor], 0
0x180066593  lea     r8, [rsp+270h+SecurityDescriptor]; SecurityDescriptor
0x180066598  mov     [rsp+270h+SecurityDescriptorSize], 0
0x1800665a0  mov     edx, 1; StringSDRevision
0x1800665a5  lea     rcx, [rsp+270h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800665aa  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800665b0  test    eax, eax
0x1800665b2  jnz     short loc_1800665C9
0x1800665b4  call    cs:__imp_GetLastError
0x1800665ba  mov     ebx, eax
0x1800665bc  test    eax, eax
0x1800665be  jle     short loc_1800665C9
0x1800665c0  movzx   ebx, ax
0x1800665c3  or      ebx, 80070000h
0x1800665c9  test    ebx, ebx
0x1800665cb  js      short loc_1800665FC
0x1800665cd  mov     rax, [rsp+270h+SecurityDescriptor]
0x1800665d2  mov     qword ptr [rsp+270h+var_238+8], rax
0x1800665d7  mov     qword ptr [rsp+270h+var_238], 18h
0x1800665e0  movups  xmm0, [rsp+270h+var_238]
0x1800665e5  mov     [rsp+270h+var_228], 1
0x1800665ee  movsd   xmm1, [rsp+270h+var_228]
0x1800665f4  movups  xmmword ptr [rdi], xmm0
0x1800665f7  movsd   qword ptr [rdi+10h], xmm1
0x1800665fc  mov     eax, ebx
0x1800665fe  mov     rcx, [rbp+170h+var_10]
0x180066605  xor     rcx, rsp; StackCookie
0x180066608  call    __security_check_cookie
0x18006660d  lea     r11, [rsp+270h+var_s0]
0x180066615  mov     rbx, [r11+20h]
0x180066619  mov     rdi, [r11+28h]
0x18006661d  mov     rsp, r11
0x180066620  pop     rbp
0x180066621  retn
```
