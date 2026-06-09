# CapabilityUtils::CheckForPackageInPrivilegedList(ushort const *,ushort const *,bool *)

- ea: `0x1802f1d3c`
- end: `0x1802f205c`
- name: `?CheckForPackageInPrivilegedList@CapabilityUtils@@YAJPEBG0PEA_N@Z`
- size: `800`
- prototype: `__int64 __fastcall(LPCWSTR StringSid, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180118170`

## callees

- `0x180144f2c`
- `0x180144f94`
- `0x1802f1d3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f1f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f1f43`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1802f1fbf`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1802f1fbf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802f1fd3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802f200a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802f201a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802f1fd3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802f200a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802f201a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1802f1f8e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1802f1f8e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1802f1f33`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1802f1f33`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1802f1e42`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1802f202d`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1802f1e42`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1802f202d`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1802f1e07`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1802f1ed9`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1802f1e07`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1802f1ed9`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1802f1fa5`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1802f1fa5`

## pseudocode

```c
__int64 __fastcall CapabilityUtils::CheckForPackageInPrivilegedList(
        LPCWSTR StringSid,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        bool *a4)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v5; // r9
  __int64 v9; // rdi
  signed int ObjectProperties; // ebx
  __int64 v11; // rdx
  const WCHAR *v12; // rdi
  unsigned int v13; // esi
  signed int LastError; // eax
  char v15; // dl
  BOOL v16; // eax
  PSID v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  PSID pSid1; // [rsp+40h] [rbp-10h] BYREF
  PSID Sid; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v23; // [rsp+90h] [rbp+40h] BYREF
  __int64 v24; // [rsp+98h] [rbp+48h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v5 = (unsigned int)tls_index;
  v23 = 0;
  *(_BYTE *)a3 = 0;
  v9 = ThreadLocalStoragePointer[v5];
  v24 = 0;
  if ( dword_1804CF85C > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&dword_1804CF85C);
    if ( dword_1804CF85C == -1 )
    {
      *(DEVPROPKEY *)byte_1804CE6A0 = DEVPKEY_DeviceContainer_CustomPrivilegedPackageFamilyNames;
      dword_1804CE6B4 = 0;
      qword_1804CE6B8 = 0;
      Init_thread_footer(&dword_1804CF85C);
    }
  }
  ObjectProperties = DevGetObjectProperties(2, a2, 0, 1, byte_1804CE6A0, &v23, &v24);
  if ( ObjectProperties >= 0 )
  {
    v11 = v24;
    if ( v23 != 1 || *(_DWORD *)(v24 + 32) != 8210 || !*(_DWORD *)(v24 + 36) || !*(_QWORD *)(v24 + 40) )
    {
      DevFreeObjectProperties(v23, v24);
      v23 = 0;
      if ( dword_1804CF860 > *(_DWORD *)(v9 + 4) )
      {
        Init_thread_header(&dword_1804CF860);
        if ( dword_1804CF860 == -1 )
        {
          *(DEVPROPKEY *)byte_1804CE6C0 = DEVPKEY_DeviceContainer_PrivilegedPackageFamilyNames;
          dword_1804CE6D4 = 0;
          qword_1804CE6D8 = 0;
          Init_thread_footer(&dword_1804CF860);
        }
      }
      ObjectProperties = DevGetObjectProperties(2, a2, 0, 1, byte_1804CE6C0, &v23, &v24);
      if ( ObjectProperties < 0 )
      {
LABEL_35:
        v11 = v24;
LABEL_36:
        DevFreeObjectProperties(v23, v11);
        return (unsigned int)ObjectProperties;
      }
      v11 = v24;
      if ( v23 != 1 || *(_DWORD *)(v24 + 32) != 8210 || !*(_DWORD *)(v24 + 36) || !*(_QWORD *)(v24 + 40) )
      {
        ObjectProperties = -2147418113;
        goto LABEL_36;
      }
    }
    v12 = *(const WCHAR **)(v11 + 40);
    v13 = *(_DWORD *)(v11 + 36);
    ObjectProperties = 0;
    Sid = 0;
    if ( ConvertStringSidToSidW(StringSid, &Sid) )
      goto LABEL_21;
    LastError = GetLastError();
    ObjectProperties = LastError;
    if ( LastError > 0 )
      ObjectProperties = (unsigned __int16)LastError | 0x80070000;
    if ( ObjectProperties >= 0 )
    {
LABEL_21:
      v15 = 1;
      while ( v13 >= 2 && *v12 )
      {
        pSid1 = 0;
        if ( v15 == 1 && !lstrcmpiW(v12, L"*") )
        {
          *(_BYTE *)a3 = 1;
          break;
        }
        ObjectProperties = AppContainerDeriveSidFromMoniker(v12, &pSid1);
        if ( ObjectProperties >= 0 )
        {
          v16 = EqualSid(pSid1, Sid);
          v17 = pSid1;
          if ( v16 )
          {
            *(_BYTE *)a3 = 1;
            FreeSid(v17);
            break;
          }
          FreeSid(pSid1);
        }
        v15 = 0;
        v18 = -1;
        do
          ++v18;
        while ( v12[v18] );
        v19 = (unsigned int)(v18 + 1);
        v12 += v19;
        v13 += -2 * v19;
      }
      FreeSid(Sid);
    }
    goto LABEL_35;
  }
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x1802f1d3c  mov     [rsp-28h+arg_0], rbx
0x1802f1d41  mov     [rsp-28h+arg_8], rsi
0x1802f1d46  push    rbp
0x1802f1d47  push    rdi
0x1802f1d48  push    r12
0x1802f1d4a  push    r14
0x1802f1d4c  push    r15
0x1802f1d4e  mov     rbp, rsp
0x1802f1d51  sub     rsp, 50h
0x1802f1d55  mov     rax, gs:58h
0x1802f1d5e  xor     r12d, r12d
0x1802f1d61  mov     r9d, cs:_tls_index
0x1802f1d68  mov     r15, rcx
0x1802f1d6b  mov     ecx, 4
0x1802f1d70  mov     r14, r8
0x1802f1d73  mov     rsi, rdx
0x1802f1d76  mov     [rbp+arg_10], r12d
0x1802f1d7a  mov     [r8], r12b
0x1802f1d7d  mov     rdi, [rax+r9*8]
0x1802f1d81  mov     [rbp+arg_18], r12
0x1802f1d85  mov     eax, [rdi+rcx]
0x1802f1d88  cmp     cs:dword_1804CF85C, eax
0x1802f1d8e  jle     short loc_1802F1DD9
0x1802f1d90  lea     rcx, dword_1804CF85C
0x1802f1d97  call    _Init_thread_header
0x1802f1d9c  cmp     cs:dword_1804CF85C, 0FFFFFFFFh
0x1802f1da3  jnz     short loc_1802F1DD9
0x1802f1da5  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_CustomPrivilegedPackageFamilyNames.fmtid.Data1
0x1802f1dac  mov     eax, cs:DEVPKEY_DeviceContainer_CustomPrivilegedPackageFamilyNames.pid
0x1802f1db2  lea     rcx, dword_1804CF85C
0x1802f1db9  mov     dword ptr cs:byte_1804CE6A0+10h, eax
0x1802f1dbf  movups  xmmword ptr cs:byte_1804CE6A0, xmm0
0x1802f1dc6  mov     cs:dword_1804CE6B4, r12d
0x1802f1dcd  mov     cs:qword_1804CE6B8, r12
0x1802f1dd4  call    _Init_thread_footer
0x1802f1dd9  lea     rax, [rbp+arg_18]
0x1802f1ddd  mov     r9d, 1
0x1802f1de3  mov     [rsp+50h+var_20], rax
0x1802f1de8  xor     r8d, r8d
0x1802f1deb  lea     rax, [rbp+arg_10]
0x1802f1def  mov     rdx, rsi
0x1802f1df2  mov     [rsp+50h+var_28], rax
0x1802f1df7  lea     rax, byte_1804CE6A0
0x1802f1dfe  lea     ecx, [r9+1]
0x1802f1e02  mov     [rsp+50h+var_30], rax
0x1802f1e07  call    cs:__imp_DevGetObjectProperties
0x1802f1e0e  nop     dword ptr [rax+rax+00h]
0x1802f1e13  mov     ebx, eax
0x1802f1e15  test    eax, eax
0x1802f1e17  js      loc_1802F2039
0x1802f1e1d  mov     ecx, [rbp+arg_10]
0x1802f1e20  mov     rdx, [rbp+arg_18]
0x1802f1e24  cmp     ecx, 1
0x1802f1e27  jnz     short loc_1802F1E42
0x1802f1e29  cmp     dword ptr [rdx+20h], 2012h
0x1802f1e30  jnz     short loc_1802F1E42
0x1802f1e32  cmp     [rdx+24h], r12d
0x1802f1e36  jbe     short loc_1802F1E42
0x1802f1e38  cmp     [rdx+28h], r12
0x1802f1e3c  jnz     loc_1802F1F1E
0x1802f1e42  call    cs:__imp_DevFreeObjectProperties
0x1802f1e49  nop     dword ptr [rax+rax+00h]
0x1802f1e4e  mov     eax, 4
0x1802f1e53  mov     [rbp+arg_10], r12d
0x1802f1e57  mov     eax, [rdi+rax]
0x1802f1e5a  cmp     cs:dword_1804CF860, eax
0x1802f1e60  jle     short loc_1802F1EAB
0x1802f1e62  lea     rcx, dword_1804CF860
0x1802f1e69  call    _Init_thread_header
0x1802f1e6e  cmp     cs:dword_1804CF860, 0FFFFFFFFh
0x1802f1e75  jnz     short loc_1802F1EAB
0x1802f1e77  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_PrivilegedPackageFamilyNames.fmtid.Data1
0x1802f1e7e  mov     eax, cs:DEVPKEY_DeviceContainer_PrivilegedPackageFamilyNames.pid
0x1802f1e84  lea     rcx, dword_1804CF860
0x1802f1e8b  mov     dword ptr cs:byte_1804CE6C0+10h, eax
0x1802f1e91  movups  xmmword ptr cs:byte_1804CE6C0, xmm0
0x1802f1e98  mov     cs:dword_1804CE6D4, r12d
0x1802f1e9f  mov     cs:qword_1804CE6D8, r12
0x1802f1ea6  call    _Init_thread_footer
0x1802f1eab  lea     rax, [rbp+arg_18]
0x1802f1eaf  mov     r9d, 1
0x1802f1eb5  mov     [rsp+50h+var_20], rax
0x1802f1eba  xor     r8d, r8d
0x1802f1ebd  lea     rax, [rbp+arg_10]
0x1802f1ec1  mov     rdx, rsi
0x1802f1ec4  mov     [rsp+50h+var_28], rax
0x1802f1ec9  lea     rax, byte_1804CE6C0
0x1802f1ed0  lea     ecx, [r9+1]
0x1802f1ed4  mov     [rsp+50h+var_30], rax
0x1802f1ed9  call    cs:__imp_DevGetObjectProperties
0x1802f1ee0  nop     dword ptr [rax+rax+00h]
0x1802f1ee5  mov     ebx, eax
0x1802f1ee7  test    eax, eax
0x1802f1ee9  js      loc_1802F2026
0x1802f1eef  cmp     [rbp+arg_10], 1
0x1802f1ef3  mov     rdx, [rbp+arg_18]
0x1802f1ef7  jnz     loc_1802F2055
0x1802f1efd  cmp     dword ptr [rdx+20h], 2012h
0x1802f1f04  jnz     loc_1802F2055
0x1802f1f0a  cmp     [rdx+24h], r12d
0x1802f1f0e  jbe     loc_1802F2055
0x1802f1f14  cmp     [rdx+28h], r12
0x1802f1f18  jz      loc_1802F2055
0x1802f1f1e  mov     rdi, [rdx+28h]
0x1802f1f22  mov     rcx, r15; StringSid
0x1802f1f25  mov     esi, [rdx+24h]
0x1802f1f28  mov     ebx, r12d
0x1802f1f2b  lea     rdx, [rbp+Sid]; Sid
0x1802f1f2f  mov     [rbp+Sid], r12
0x1802f1f33  call    cs:__imp_ConvertStringSidToSidW
0x1802f1f3a  nop     dword ptr [rax+rax+00h]
0x1802f1f3f  test    eax, eax
0x1802f1f41  jnz     short loc_1802F1F66
0x1802f1f43  call    cs:__imp_GetLastError
0x1802f1f4a  nop     dword ptr [rax+rax+00h]
0x1802f1f4f  mov     ebx, eax
0x1802f1f51  test    eax, eax
0x1802f1f53  jle     short loc_1802F1F5E
0x1802f1f55  movzx   ebx, ax
0x1802f1f58  or      ebx, 80070000h
0x1802f1f5e  test    ebx, ebx
0x1802f1f60  js      loc_1802F2026
0x1802f1f66  mov     dl, 1
0x1802f1f68  cmp     esi, 2
0x1802f1f6b  jb      loc_1802F2016
0x1802f1f71  cmp     [rdi], r12w
0x1802f1f75  jz      loc_1802F2016
0x1802f1f7b  mov     [rbp+pSid1], r12
0x1802f1f7f  cmp     dl, 1
0x1802f1f82  jnz     short loc_1802F1F9E
0x1802f1f84  lea     rdx, asc_180414808; "*"
0x1802f1f8b  mov     rcx, rdi; lpString1
0x1802f1f8e  call    cs:__imp_lstrcmpiW
0x1802f1f95  nop     dword ptr [rax+rax+00h]
0x1802f1f9a  test    eax, eax
0x1802f1f9c  jz      short loc_1802F2000
0x1802f1f9e  lea     rdx, [rbp+pSid1]
0x1802f1fa2  mov     rcx, rdi
0x1802f1fa5  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x1802f1fac  nop     dword ptr [rax+rax+00h]
0x1802f1fb1  mov     ebx, eax
0x1802f1fb3  test    eax, eax
0x1802f1fb5  js      short loc_1802F1FDF
0x1802f1fb7  mov     rdx, [rbp+Sid]; pSid2
0x1802f1fbb  mov     rcx, [rbp+pSid1]; pSid1
0x1802f1fbf  call    cs:__imp_EqualSid
0x1802f1fc6  nop     dword ptr [rax+rax+00h]
0x1802f1fcb  mov     rcx, [rbp+pSid1]; pSid
0x1802f1fcf  test    eax, eax
0x1802f1fd1  jnz     short loc_1802F2006
0x1802f1fd3  call    cs:__imp_FreeSid
0x1802f1fda  nop     dword ptr [rax+rax+00h]
0x1802f1fdf  mov     dl, r12b
0x1802f1fe2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1802f1fe6  inc     rcx
0x1802f1fe9  cmp     [rdi+rcx*2], r12w
0x1802f1fee  jnz     short loc_1802F1FE6
0x1802f1ff0  inc     ecx
0x1802f1ff2  imul    eax, ecx, -2
0x1802f1ff5  lea     rdi, [rdi+rcx*2]
0x1802f1ff9  add     esi, eax
0x1802f1ffb  jmp     loc_1802F1F68
0x1802f2000  mov     byte ptr [r14], 1
0x1802f2004  jmp     short loc_1802F2016
0x1802f2006  mov     byte ptr [r14], 1
0x1802f200a  call    cs:__imp_FreeSid
0x1802f2011  nop     dword ptr [rax+rax+00h]
0x1802f2016  mov     rcx, [rbp+Sid]; pSid
0x1802f201a  call    cs:__imp_FreeSid
0x1802f2021  nop     dword ptr [rax+rax+00h]
0x1802f2026  mov     rdx, [rbp+arg_18]
0x1802f202a  mov     ecx, [rbp+arg_10]
0x1802f202d  call    cs:__imp_DevFreeObjectProperties
0x1802f2034  nop     dword ptr [rax+rax+00h]
0x1802f2039  lea     r11, [rsp+50h+var_s0]
0x1802f203e  mov     eax, ebx
0x1802f2040  mov     rbx, [r11+30h]
0x1802f2044  mov     rsi, [r11+38h]
0x1802f2048  mov     rsp, r11
0x1802f204b  pop     r15
0x1802f204d  pop     r14
0x1802f204f  pop     r12
0x1802f2051  pop     rdi
0x1802f2052  pop     rbp
0x1802f2053  retn
0x1802f2055  mov     ebx, 8000FFFFh
0x1802f205a  jmp     short loc_1802F202A
```
