# InitSecurity(void)

- ea: `0x180023978`
- end: `0x180023c19`
- name: `?InitSecurity@@YAJXZ`
- size: `673`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002fec8`

## callees

- `0x180023978`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180023b75`
- `ntdll!RtlNtStatusToDosError` at `0x180023b95`
- `ntdll!RtlNtStatusToDosError` at `0x180023b75`
- `ntdll!RtlNtStatusToDosError` at `0x180023b95`
- `ntdll!RtlInitUnicodeString` at `0x180023a5f`
- `ntdll!RtlInitUnicodeString` at `0x180023ae2`
- `ntdll!RtlInitUnicodeString` at `0x180023a5f`
- `ntdll!RtlInitUnicodeString` at `0x180023ae2`
- `ntdll!RtlCreateServiceSid` at `0x180023a6f`
- `ntdll!RtlCreateServiceSid` at `0x180023aa3`
- `ntdll!RtlCreateServiceSid` at `0x180023af2`
- `ntdll!RtlCreateServiceSid` at `0x180023b20`
- `ntdll!RtlCreateServiceSid` at `0x180023a6f`
- `ntdll!RtlCreateServiceSid` at `0x180023aa3`
- `ntdll!RtlCreateServiceSid` at `0x180023af2`
- `ntdll!RtlCreateServiceSid` at `0x180023b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023abf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023b39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023bea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023abf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023b39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023bea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023a86`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023b07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023a86`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023b07`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800239bd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800239fe`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023a3c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800239bd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800239fe`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023a3c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023bb8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023bd1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023bb8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023bd1`

## pseudocode

```c
__int64 InitSecurity(void)
{
  HLOCAL v0; // rax
  void *v1; // rdi
  int v2; // eax
  signed int v3; // ebx
  HLOCAL v4; // rax
  void *v5; // rdi
  int v6; // eax
  signed int LastError; // eax
  signed int v9; // eax
  signed int v10; // eax
  _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-18h] BYREF
  ULONG ServiceSidLength; // [rsp+A0h] [rbp+28h] BYREF

  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 2u, 0, 0, 0, 0, 0, 0, 0, &pSid2) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
LABEL_16:
    if ( v3 >= 0 )
      return (unsigned int)v3;
    goto LABEL_24;
  }
  ServiceSidLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"EventSystem");
  if ( RtlCreateServiceSid(&DestinationString, 0, &ServiceSidLength) != -1073741789 )
    goto LABEL_19;
  v0 = LocalAlloc(0x40u, ServiceSidLength);
  v1 = v0;
  if ( !v0 )
    goto LABEL_18;
  v2 = RtlCreateServiceSid(&DestinationString, v0, &ServiceSidLength);
  if ( v2 < 0 )
  {
    v9 = RtlNtStatusToDosError(v2);
    v3 = v9;
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
  }
  else
  {
    hMem = v1;
    v3 = 0;
    v1 = 0;
  }
  LocalFree(v1);
  if ( v3 >= 0 )
  {
    ServiceSidLength = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"SENS");
    if ( RtlCreateServiceSid(&DestinationString, 0, &ServiceSidLength) == -1073741789 )
    {
      v4 = LocalAlloc(0x40u, ServiceSidLength);
      v5 = v4;
      if ( v4 )
      {
        v6 = RtlCreateServiceSid(&DestinationString, v4, &ServiceSidLength);
        if ( v6 < 0 )
        {
          v10 = RtlNtStatusToDosError(v6);
          v3 = v10;
          if ( v10 > 0 )
            v3 = (unsigned __int16)v10 | 0x80070000;
        }
        else
        {
          qword_180064668 = v5;
          v3 = 0;
          v5 = 0;
        }
        LocalFree(v5);
        goto LABEL_16;
      }
LABEL_18:
      v3 = -2147024882;
      goto LABEL_16;
    }
LABEL_19:
    v3 = -2147418113;
    goto LABEL_16;
  }
LABEL_24:
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( SidToCheck )
  {
    FreeSid(SidToCheck);
    SidToCheck = 0;
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( qword_180064668 )
  {
    LocalFree(qword_180064668);
    qword_180064668 = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180023978  push    rbp
0x18002397a  push    rbx
0x18002397b  push    rsi
0x18002397c  push    rdi
0x18002397d  mov     rbp, rsp
0x180023980  sub     rsp, 78h
0x180023984  xor     esi, esi
0x180023986  lea     rax, pSid
0x18002398d  mov     [rsp+78h+pSid], rax; pSid
0x180023992  lea     rbx, pIdentifierAuthority
0x180023999  mov     [rsp+78h+nSubAuthority7], esi; nSubAuthority7
0x18002399d  xor     r9d, r9d; nSubAuthority1
0x1800239a0  mov     [rsp+78h+nSubAuthority6], esi; nSubAuthority6
0x1800239a4  mov     dl, 1; nSubAuthorityCount
0x1800239a6  mov     [rsp+78h+nSubAuthority5], esi; nSubAuthority5
0x1800239aa  lea     r8d, [rsi+12h]; nSubAuthority0
0x1800239ae  mov     [rsp+78h+nSubAuthority4], esi; nSubAuthority4
0x1800239b2  mov     rcx, rbx; pIdentifierAuthority
0x1800239b5  mov     [rsp+78h+nSubAuthority3], esi; nSubAuthority3
0x1800239b9  mov     [rsp+78h+nSubAuthority2], esi; nSubAuthority2
0x1800239bd  call    cs:__imp_AllocateAndInitializeSid
0x1800239c3  test    eax, eax
0x1800239c5  jz      loc_180023B41
0x1800239cb  lea     rax, SidToCheck
0x1800239d2  mov     r9d, 220h; nSubAuthority1
0x1800239d8  mov     [rsp+78h+pSid], rax; pSid
0x1800239dd  lea     r8d, [rsi+20h]; nSubAuthority0
0x1800239e1  mov     [rsp+78h+nSubAuthority7], esi; nSubAuthority7
0x1800239e5  mov     dl, 2; nSubAuthorityCount
0x1800239e7  mov     [rsp+78h+nSubAuthority6], esi; nSubAuthority6
0x1800239eb  mov     rcx, rbx; pIdentifierAuthority
0x1800239ee  mov     [rsp+78h+nSubAuthority5], esi; nSubAuthority5
0x1800239f2  mov     [rsp+78h+nSubAuthority4], esi; nSubAuthority4
0x1800239f6  mov     [rsp+78h+nSubAuthority3], esi; nSubAuthority3
0x1800239fa  mov     [rsp+78h+nSubAuthority2], esi; nSubAuthority2
0x1800239fe  call    cs:__imp_AllocateAndInitializeSid
0x180023a04  test    eax, eax
0x180023a06  jz      loc_180023B41
0x180023a0c  lea     rax, pSid2
0x180023a13  xor     r9d, r9d; nSubAuthority1
0x180023a16  mov     [rsp+78h+pSid], rax; pSid
0x180023a1b  lea     r8d, [rsi+2]; nSubAuthority0
0x180023a1f  mov     [rsp+78h+nSubAuthority7], esi; nSubAuthority7
0x180023a23  mov     dl, 1; nSubAuthorityCount
0x180023a25  mov     [rsp+78h+nSubAuthority6], esi; nSubAuthority6
0x180023a29  mov     rcx, rbx; pIdentifierAuthority
0x180023a2c  mov     [rsp+78h+nSubAuthority5], esi; nSubAuthority5
0x180023a30  mov     [rsp+78h+nSubAuthority4], esi; nSubAuthority4
0x180023a34  mov     [rsp+78h+nSubAuthority3], esi; nSubAuthority3
0x180023a38  mov     [rsp+78h+nSubAuthority2], esi; nSubAuthority2
0x180023a3c  call    cs:__imp_AllocateAndInitializeSid
0x180023a42  test    eax, eax
0x180023a44  jz      loc_180023B41
0x180023a4a  xorps   xmm0, xmm0
0x180023a4d  mov     [rbp+ServiceSidLength], esi
0x180023a50  lea     rdx, SourceString; "EventSystem"
0x180023a57  lea     rcx, [rbp+DestinationString]; DestinationString
0x180023a5b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180023a5f  call    cs:__imp_RtlInitUnicodeString
0x180023a65  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x180023a69  xor     edx, edx; ServiceSid
0x180023a6b  lea     rcx, [rbp+DestinationString]; ServiceName
0x180023a6f  call    cs:__imp_RtlCreateServiceSid
0x180023a75  cmp     eax, 0C0000023h
0x180023a7a  jnz     loc_180023B6C
0x180023a80  mov     edx, [rbp+ServiceSidLength]; uBytes
0x180023a83  lea     ecx, [rsi+40h]; uFlags
0x180023a86  call    cs:__imp_LocalAlloc
0x180023a8c  mov     rdi, rax
0x180023a8f  test    rax, rax
0x180023a92  jz      loc_180023B65
0x180023a98  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x180023a9c  mov     rdx, rax; ServiceSid
0x180023a9f  lea     rcx, [rbp+DestinationString]; ServiceName
0x180023aa3  call    cs:__imp_RtlCreateServiceSid
0x180023aa9  test    eax, eax
0x180023aab  js      loc_180023B73
0x180023ab1  mov     cs:hMem, rdi
0x180023ab8  mov     ebx, esi
0x180023aba  mov     edi, esi
0x180023abc  mov     rcx, rdi; hMem
0x180023abf  call    cs:__imp_LocalFree
0x180023ac5  test    ebx, ebx
0x180023ac7  js      loc_180023BAC
0x180023acd  xorps   xmm0, xmm0
0x180023ad0  mov     [rbp+ServiceSidLength], esi
0x180023ad3  lea     rdx, aSens; "SENS"
0x180023ada  lea     rcx, [rbp+DestinationString]; DestinationString
0x180023ade  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180023ae2  call    cs:__imp_RtlInitUnicodeString
0x180023ae8  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x180023aec  xor     edx, edx; ServiceSid
0x180023aee  lea     rcx, [rbp+DestinationString]; ServiceName
0x180023af2  call    cs:__imp_RtlCreateServiceSid
0x180023af8  cmp     eax, 0C0000023h
0x180023afd  jnz     short loc_180023B6C
0x180023aff  mov     edx, [rbp+ServiceSidLength]; uBytes
0x180023b02  mov     ecx, 40h ; '@'; uFlags
0x180023b07  call    cs:__imp_LocalAlloc
0x180023b0d  mov     rdi, rax
0x180023b10  test    rax, rax
0x180023b13  jz      short loc_180023B65
0x180023b15  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x180023b19  mov     rdx, rax; ServiceSid
0x180023b1c  lea     rcx, [rbp+DestinationString]; ServiceName
0x180023b20  call    cs:__imp_RtlCreateServiceSid
0x180023b26  test    eax, eax
0x180023b28  js      short loc_180023B93
0x180023b2a  mov     cs:qword_180064668, rdi
0x180023b31  mov     ebx, esi
0x180023b33  mov     rdi, rsi
0x180023b36  mov     rcx, rdi; hMem
0x180023b39  call    cs:__imp_LocalFree
0x180023b3f  jmp     short loc_180023B56
0x180023b41  call    cs:__imp_GetLastError
0x180023b47  mov     ebx, eax
0x180023b49  test    eax, eax
0x180023b4b  jle     short loc_180023B56
0x180023b4d  movzx   ebx, ax
0x180023b50  or      ebx, 80070000h
0x180023b56  test    ebx, ebx
0x180023b58  js      short loc_180023BAC
0x180023b5a  mov     eax, ebx
0x180023b5c  add     rsp, 78h
0x180023b60  pop     rdi
0x180023b61  pop     rsi
0x180023b62  pop     rbx
0x180023b63  pop     rbp
0x180023b64  retn
0x180023b65  mov     ebx, 8007000Eh
0x180023b6a  jmp     short loc_180023B56
0x180023b6c  mov     ebx, 8000FFFFh
0x180023b71  jmp     short loc_180023B56
0x180023b73  mov     ecx, eax; Status
0x180023b75  call    cs:__imp_RtlNtStatusToDosError
0x180023b7b  mov     ebx, eax
0x180023b7d  test    eax, eax
0x180023b7f  jle     loc_180023ABC
0x180023b85  movzx   ebx, ax
0x180023b88  or      ebx, 80070000h
0x180023b8e  jmp     loc_180023ABC
0x180023b93  mov     ecx, eax; Status
0x180023b95  call    cs:__imp_RtlNtStatusToDosError
0x180023b9b  mov     ebx, eax
0x180023b9d  test    eax, eax
0x180023b9f  jle     short loc_180023B36
0x180023ba1  movzx   ebx, ax
0x180023ba4  or      ebx, 80070000h
0x180023baa  jmp     short loc_180023B36
0x180023bac  mov     rcx, cs:pSid; pSid
0x180023bb3  test    rcx, rcx
0x180023bb6  jz      short loc_180023BC5
0x180023bb8  call    cs:__imp_FreeSid
0x180023bbe  mov     cs:pSid, rsi
0x180023bc5  mov     rcx, cs:SidToCheck; pSid
0x180023bcc  test    rcx, rcx
0x180023bcf  jz      short loc_180023BDE
0x180023bd1  call    cs:__imp_FreeSid
0x180023bd7  mov     cs:SidToCheck, rsi
0x180023bde  mov     rcx, cs:hMem; hMem
0x180023be5  test    rcx, rcx
0x180023be8  jz      short loc_180023BF7
0x180023bea  call    cs:__imp_LocalFree
0x180023bf0  mov     cs:hMem, rsi
0x180023bf7  mov     rcx, cs:qword_180064668; hMem
0x180023bfe  test    rcx, rcx
0x180023c01  jz      loc_180023B5A
0x180023c07  call    cs:__imp_LocalFree
0x180023c0d  mov     cs:qword_180064668, rsi
0x180023c14  jmp     loc_180023B5A
```
