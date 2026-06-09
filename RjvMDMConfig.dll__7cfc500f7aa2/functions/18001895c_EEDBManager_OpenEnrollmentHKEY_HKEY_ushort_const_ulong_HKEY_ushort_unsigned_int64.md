# EEDBManager::OpenEnrollmentHKEY(HKEY__ *,ushort const *,ulong,HKEY__ * *,ushort *,unsigned __int64)

- ea: `0x18001895c`
- end: `0x180018b28`
- name: `?OpenEnrollmentHKEY@EEDBManager@@SAJPEAUHKEY__@@PEBGKPEAPEAU2@PEAG_K@Z`
- size: `460`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, wchar_t *String1@<rdx>, unsigned int@<r8d>, HKEY *@<r9>, unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017ed8`
- `0x180018b30`
- `0x180018c54`

## callees

- `0x180001c60`
- `0x1800051d8`
- `0x18000ff80`
- `0x18001895c`
- `0x18001cf64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018a0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018aa7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018a0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018aa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018aee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018aee`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800189b8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800189b8`

## pseudocode

```c
int __fastcall EEDBManager::OpenEnrollmentHKEY(
        HKEY hKey,
        wchar_t *String1,
        int a3,
        HKEY *a4,
        unsigned __int16 *a5,
        unsigned __int64 a6)
{
  int result; // eax
  LSTATUS v11; // eax
  signed int v12; // ebx
  LSTATUS v13; // eax
  int v14; // eax
  WCHAR SubKey[264]; // [rsp+30h] [rbp-258h] BYREF

  if ( !a4 )
    return -2147467261;
  *a4 = 0;
  if ( hKey != HKEY_LOCAL_MACHINE || !(unsigned __int8)RtlIsStateSeparationEnabled() )
    goto LABEL_12;
  result = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"OSData\\Software\\Microsoft\\Enrollments", String1);
  if ( result < 0 )
    return result;
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, a3 | 0x100, a4);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( (v12 >= 0 || wcsncmp_0(String1, L"Status", 6u) && wcsncmp_0(String1, L"Context", 7u))
    && (unsigned int)(v12 + 2147024894) <= 1 )
  {
LABEL_12:
    result = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Enrollments", String1);
    if ( result < 0 )
      return result;
    v13 = RegOpenKeyExW(hKey, SubKey, 0, a3 | 0x100, a4);
    v12 = v13;
    if ( v13 > 0 )
      v12 = (unsigned __int16)v13 | 0x80070000;
  }
  if ( a5 )
  {
    v14 = StringCchCopyW(a5, a6, SubKey);
    if ( v12 < 0 )
      goto LABEL_19;
    v12 = v14;
  }
  if ( v12 >= 0 )
    return 0;
LABEL_19:
  if ( *a4 )
  {
    RegCloseKey(*a4);
    *a4 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x18001895c  push    rbx
0x18001895e  push    rbp
0x18001895f  push    rsi
0x180018960  push    rdi
0x180018961  push    r14
0x180018963  push    r15
0x180018965  sub     rsp, 258h
0x18001896c  mov     rax, cs:__security_cookie
0x180018973  xor     rax, rsp
0x180018976  mov     [rsp+288h+var_48], rax
0x18001897e  mov     r14, [rsp+288h+arg_20]
0x180018986  mov     rdi, r9
0x180018989  mov     esi, r8d
0x18001898c  mov     rbp, rdx
0x18001898f  mov     r15, rcx
0x180018992  test    r9, r9
0x180018995  jnz     short loc_1800189A1
0x180018997  mov     eax, 80004003h
0x18001899c  jmp     loc_180018B07
0x1800189a1  mov     rbx, 0FFFFFFFF80000002h
0x1800189a8  mov     qword ptr [r9], 0
0x1800189af  cmp     r15, rbx
0x1800189b2  jnz     loc_180018A6A
0x1800189b8  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800189bf  nop     dword ptr [rax+rax+00h]
0x1800189c4  test    al, al
0x1800189c6  jz      loc_180018A6A
0x1800189cc  lea     r9, aOsdataSoftware_2; "OSData\\Software\\Microsoft\\Enrollment"...
0x1800189d3  mov     [rsp+288h+phkResult], rbp
0x1800189d8  lea     r8, aSS; "%s\\%s"
0x1800189df  mov     edx, 104h; unsigned __int64
0x1800189e4  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x1800189e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800189ee  test    eax, eax
0x1800189f0  js      loc_180018B07
0x1800189f6  mov     r9d, esi
0x1800189f9  mov     [rsp+288h+phkResult], rdi; phkResult
0x1800189fe  bts     r9d, 8; samDesired
0x180018a03  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x180018a08  xor     r8d, r8d; ulOptions
0x180018a0b  mov     rcx, rbx; hKey
0x180018a0e  call    cs:__imp_RegOpenKeyExW
0x180018a15  nop     dword ptr [rax+rax+00h]
0x180018a1a  mov     ebx, eax
0x180018a1c  test    eax, eax
0x180018a1e  jle     short loc_180018A29
0x180018a20  movzx   ebx, ax
0x180018a23  or      ebx, 80070000h
0x180018a29  test    ebx, ebx
0x180018a2b  jns     short loc_180018A5F
0x180018a2d  mov     r8d, 6; MaxCount
0x180018a33  lea     rdx, aStatus; "Status"
0x180018a3a  mov     rcx, rbp; String1
0x180018a3d  call    wcsncmp_0
0x180018a42  test    eax, eax
0x180018a44  jz      short loc_180018AC2
0x180018a46  mov     r8d, 7; MaxCount
0x180018a4c  lea     rdx, aContext; "Context"
0x180018a53  mov     rcx, rbp; String1
0x180018a56  call    wcsncmp_0
0x180018a5b  test    eax, eax
0x180018a5d  jz      short loc_180018AC2
0x180018a5f  lea     eax, [rbx+7FF8FFFEh]
0x180018a65  cmp     eax, 1
0x180018a68  ja      short loc_180018AC2
0x180018a6a  lea     r9, SubKey; "Software\\Microsoft\\Enrollments"
0x180018a71  mov     [rsp+288h+phkResult], rbp
0x180018a76  lea     r8, aSS; "%s\\%s"
0x180018a7d  mov     edx, 104h; unsigned __int64
0x180018a82  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x180018a87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018a8c  test    eax, eax
0x180018a8e  js      short loc_180018B07
0x180018a90  bts     esi, 8
0x180018a94  mov     [rsp+288h+phkResult], rdi; phkResult
0x180018a99  mov     r9d, esi; samDesired
0x180018a9c  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x180018aa1  xor     r8d, r8d; ulOptions
0x180018aa4  mov     rcx, r15; hKey
0x180018aa7  call    cs:__imp_RegOpenKeyExW
0x180018aae  nop     dword ptr [rax+rax+00h]
0x180018ab3  mov     ebx, eax
0x180018ab5  test    eax, eax
0x180018ab7  jle     short loc_180018AC2
0x180018ab9  movzx   ebx, ax
0x180018abc  or      ebx, 80070000h
0x180018ac2  test    r14, r14
0x180018ac5  jz      short loc_180018AE2
0x180018ac7  mov     rdx, [rsp+288h+arg_28]; unsigned __int64
0x180018acf  lea     r8, [rsp+288h+SubKey]; unsigned __int16 *
0x180018ad4  mov     rcx, r14; unsigned __int16 *
0x180018ad7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018adc  test    ebx, ebx
0x180018ade  js      short loc_180018AE6
0x180018ae0  mov     ebx, eax
0x180018ae2  test    ebx, ebx
0x180018ae4  jns     short loc_180018B05
0x180018ae6  mov     rcx, [rdi]; hKey
0x180018ae9  test    rcx, rcx
0x180018aec  jz      short loc_180018B01
0x180018aee  call    cs:__imp_RegCloseKey
0x180018af5  nop     dword ptr [rax+rax+00h]
0x180018afa  mov     qword ptr [rdi], 0
0x180018b01  mov     eax, ebx
0x180018b03  jmp     short loc_180018B07
0x180018b05  xor     eax, eax
0x180018b07  mov     rcx, [rsp+288h+var_48]
0x180018b0f  xor     rcx, rsp; StackCookie
0x180018b12  call    __security_check_cookie
0x180018b17  add     rsp, 258h
0x180018b1e  pop     r15
0x180018b20  pop     r14
0x180018b22  pop     rdi
0x180018b23  pop     rsi
0x180018b24  pop     rbp
0x180018b25  pop     rbx
0x180018b26  retn
```
