# ConvertIPTCDateTimeOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x1800139f0`
- end: `0x180013bf2`
- name: `?ConvertIPTCDateTimeOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@1@Z`
- size: `514`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012be0`

## callees

- `0x1800089f0`
- `0x1800096a0`
- `0x18000ea14`
- `0x1800139f0`
- `0x180016a40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013a1d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013a2c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013bcc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013a1d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013a2c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013abb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180013a60`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180013a60`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180013aab`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180013aab`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180013a8d`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180013a8d`

## pseudocode

```c
__int64 __fastcall ConvertIPTCDateTimeOnWrite(
        const struct tagPROPVARIANT *a1,
        struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3)
{
  signed int v6; // ebx
  bool v7; // zf
  BOOL v8; // eax
  signed int LastError; // eax
  __int64 wYear; // r9
  unsigned __int16 *bstrVal; // rcx
  int v12; // eax
  PROPVARIANT *v13; // rcx
  __int64 wHour; // r9
  unsigned __int16 *v15; // rcx
  int wMonth; // [rsp+20h] [rbp-40h]
  __int64 v18; // [rsp+20h] [rbp-40h]
  int wDay; // [rsp+28h] [rbp-38h]
  __int64 v20; // [rsp+28h] [rbp-38h]
  ULONGLONG pullResult; // [rsp+30h] [rbp-30h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+38h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-18h] BYREF

  v6 = -2147024809;
  PropVariantClear(a2);
  PropVariantClear(a3);
  v7 = a1->vt == 7;
  SystemTime = 0;
  LocalTime = 0;
  if ( v7 )
  {
    if ( !VariantTimeToSystemTime(a1->dblVal, &SystemTime) )
      return (unsigned int)v6;
  }
  else
  {
    if ( a1->vt != 64 )
      return (unsigned int)v6;
    v8 = FileTimeToSystemTime(&a1->filetime, &SystemTime);
    v6 = !v8 ? 0x80070057 : 0;
    if ( !v8 )
      return (unsigned int)v6;
  }
  if ( SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
    goto LABEL_24;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_24:
    pullResult = 0;
    v6 = ULongLongMult(9u, 2u, &pullResult);
    if ( v6 >= 0 )
    {
      v6 = CoTaskMemAllocWithInit(pullResult, (void **)&a2->puuid);
      if ( v6 >= 0 )
      {
        wYear = LocalTime.wYear;
        wDay = LocalTime.wDay;
        wMonth = LocalTime.wMonth;
        bstrVal = a2->bstrVal;
        a2->vt = 31;
        v12 = StringCchPrintfW(bstrVal, 9u, L"%04u%02u%02u", wYear, wMonth, wDay);
        v6 = v12;
        if ( v12 == -2147024774 )
        {
          v6 = -2147024809;
        }
        else if ( v12 >= 0 )
        {
          pullResult = 0;
          v6 = ULongLongMult(0xCu, 2u, &pullResult);
          if ( v6 < 0 )
            return (unsigned int)v6;
          v6 = CoTaskMemAllocWithInit(pullResult, (void **)&a3->puuid);
          if ( v6 < 0 )
            return (unsigned int)v6;
          wHour = LocalTime.wHour;
          v15 = a3->bstrVal;
          LODWORD(v20) = LocalTime.wSecond;
          LODWORD(v18) = LocalTime.wMinute;
          a3->vt = 31;
          v6 = StringCchPrintfW(v15, 0xCu, L"%02u%02u%02u+0000", wHour, v18, v20);
          if ( v6 >= 0 )
            return (unsigned int)v6;
          v13 = a3;
LABEL_20:
          PropVariantClear(v13);
          return (unsigned int)v6;
        }
        v13 = a2;
        goto LABEL_20;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800139f0  push    rbp
0x1800139f2  push    rbx
0x1800139f3  push    rsi
0x1800139f4  push    rdi
0x1800139f5  push    r14
0x1800139f7  mov     rbp, rsp
0x1800139fa  sub     rsp, 60h
0x1800139fe  mov     rax, cs:__security_cookie
0x180013a05  xor     rax, rsp
0x180013a08  mov     [rbp+var_8], rax
0x180013a0c  mov     r14, rcx
0x180013a0f  mov     rsi, r8
0x180013a12  mov     rcx, rdx; pvar
0x180013a15  mov     rdi, rdx
0x180013a18  mov     ebx, 80070057h
0x180013a1d  call    cs:__imp_PropVariantClear
0x180013a24  nop     dword ptr [rax+rax+00h]
0x180013a29  mov     rcx, rsi; pvar
0x180013a2c  call    cs:__imp_PropVariantClear
0x180013a33  nop     dword ptr [rax+rax+00h]
0x180013a38  cmp     word ptr [r14], 7
0x180013a3d  xorps   xmm0, xmm0
0x180013a40  xorps   xmm1, xmm1
0x180013a43  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180013a47  movups  xmmword ptr [rbp+LocalTime.wYear], xmm1
0x180013a4b  jz      short loc_180013A83
0x180013a4d  cmp     word ptr [r14], 40h ; '@'
0x180013a52  jnz     loc_180013BD8
0x180013a58  lea     rcx, [r14+8]; lpFileTime
0x180013a5c  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180013a60  call    cs:__imp_FileTimeToSystemTime
0x180013a67  nop     dword ptr [rax+rax+00h]
0x180013a6c  mov     ecx, eax
0x180013a6e  neg     eax
0x180013a70  sbb     ebx, ebx
0x180013a72  not     ebx
0x180013a74  and     ebx, 80070057h
0x180013a7a  test    ecx, ecx
0x180013a7c  jnz     short loc_180013AA1
0x180013a7e  jmp     loc_180013BD8
0x180013a83  movsd   xmm0, qword ptr [r14+8]; vtime
0x180013a89  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180013a8d  call    cs:__imp_VariantTimeToSystemTime
0x180013a94  nop     dword ptr [rax+rax+00h]
0x180013a99  test    eax, eax
0x180013a9b  jz      loc_180013BD8
0x180013aa1  lea     r8, [rbp+LocalTime]; lpLocalTime
0x180013aa5  xor     ecx, ecx; lpTimeZoneInformation
0x180013aa7  lea     rdx, [rbp+SystemTime]; lpUniversalTime
0x180013aab  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180013ab2  nop     dword ptr [rax+rax+00h]
0x180013ab7  test    eax, eax
0x180013ab9  jnz     short loc_180013ADE
0x180013abb  call    cs:__imp_GetLastError
0x180013ac2  nop     dword ptr [rax+rax+00h]
0x180013ac7  mov     ebx, eax
0x180013ac9  test    eax, eax
0x180013acb  jle     short loc_180013AD6
0x180013acd  movzx   ebx, ax
0x180013ad0  or      ebx, 80070000h
0x180013ad6  test    ebx, ebx
0x180013ad8  js      loc_180013BD8
0x180013ade  mov     edx, 2; ullMultiplier
0x180013ae3  mov     [rbp+pullResult], 0
0x180013aeb  lea     r8, [rbp+pullResult]; pullResult
0x180013aef  lea     ecx, [rdx+7]; ullMultiplicand
0x180013af2  call    ULongLongMult
0x180013af7  mov     ebx, eax
0x180013af9  test    eax, eax
0x180013afb  js      loc_180013BD8
0x180013b01  mov     rcx, [rbp+pullResult]; Size
0x180013b05  lea     rdx, [rdi+8]; void **
0x180013b09  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180013b0e  mov     ebx, eax
0x180013b10  test    eax, eax
0x180013b12  js      loc_180013BD8
0x180013b18  movzx   ecx, [rbp+LocalTime.wMonth]
0x180013b1c  lea     r8, a04u02u02u; "%04u%02u%02u"
0x180013b23  movzx   eax, [rbp+LocalTime.wDay]
0x180013b27  mov     edx, 9; unsigned __int64
0x180013b2c  movzx   r9d, [rbp+LocalTime.wYear]
0x180013b31  mov     dword ptr [rsp+60h+var_38], eax
0x180013b35  mov     dword ptr [rsp+60h+var_40], ecx
0x180013b39  mov     rcx, [rdi+8]; unsigned __int16 *
0x180013b3d  mov     word ptr [rdi], 1Fh
0x180013b42  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013b47  mov     ebx, eax
0x180013b49  cmp     eax, 8007007Ah
0x180013b4e  jnz     short loc_180013B55
0x180013b50  lea     ebx, [rax-23h]
0x180013b53  jmp     short loc_180013B59
0x180013b55  test    eax, eax
0x180013b57  jns     short loc_180013B5E
0x180013b59  mov     rcx, rdi
0x180013b5c  jmp     short loc_180013BCC
0x180013b5e  mov     edx, 2; ullMultiplier
0x180013b63  mov     [rbp+pullResult], 0
0x180013b6b  lea     r8, [rbp+pullResult]; pullResult
0x180013b6f  lea     r14d, [rdx+0Ah]
0x180013b73  mov     ecx, r14d; ullMultiplicand
0x180013b76  call    ULongLongMult
0x180013b7b  mov     ebx, eax
0x180013b7d  test    eax, eax
0x180013b7f  js      short loc_180013BD8
0x180013b81  mov     rcx, [rbp+pullResult]; Size
0x180013b85  lea     rdx, [rsi+8]; void **
0x180013b89  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180013b8e  mov     ebx, eax
0x180013b90  test    eax, eax
0x180013b92  js      short loc_180013BD8
0x180013b94  movzx   r8d, [rbp+LocalTime.wMinute]
0x180013b99  mov     edx, r14d; unsigned __int64
0x180013b9c  movzx   eax, [rbp+LocalTime.wSecond]
0x180013ba0  movzx   r9d, [rbp+LocalTime.wHour]
0x180013ba5  mov     rcx, [rsi+8]; unsigned __int16 *
0x180013ba9  mov     dword ptr [rsp+60h+var_38], eax
0x180013bad  mov     dword ptr [rsp+60h+var_40], r8d
0x180013bb2  lea     r8, a02u02u02u0000; "%02u%02u%02u+0000"
0x180013bb9  mov     word ptr [rsi], 1Fh
0x180013bbe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013bc3  mov     ebx, eax
0x180013bc5  test    eax, eax
0x180013bc7  jns     short loc_180013BD8
0x180013bc9  mov     rcx, rsi; pvar
0x180013bcc  call    cs:__imp_PropVariantClear
0x180013bd3  nop     dword ptr [rax+rax+00h]
0x180013bd8  mov     eax, ebx
0x180013bda  mov     rcx, [rbp+var_8]
0x180013bde  xor     rcx, rsp; StackCookie
0x180013be1  call    __security_check_cookie
0x180013be6  add     rsp, 60h
0x180013bea  pop     r14
0x180013bec  pop     rdi
0x180013bed  pop     rsi
0x180013bee  pop     rbx
0x180013bef  pop     rbp
0x180013bf0  retn
```
