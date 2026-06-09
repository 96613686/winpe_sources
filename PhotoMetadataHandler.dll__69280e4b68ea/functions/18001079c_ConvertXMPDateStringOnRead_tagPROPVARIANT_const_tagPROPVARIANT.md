# ConvertXMPDateStringOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001079c`
- end: `0x18001089c`
- name: `?ConvertXMPDateStringOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `256`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f610`

## callees

- `0x18000e460`
- `0x18001079c`
- `0x180010950`
- `0x180016a40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800107c2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800107c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010867`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x180010836`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x180010836`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001084e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001084e`

## pseudocode

```c
int __fastcall ConvertXMPDateStringOnRead(const struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2)
{
  bool v4; // zf
  int result; // eax
  const unsigned __int16 *bstrVal; // rcx
  int v7; // [rsp+20h] [rbp-30h] BYREF
  SYSTEMTIME LocalTime; // [rsp+28h] [rbp-28h] BYREF
  struct _SYSTEMTIME UniversalTime; // [rsp+38h] [rbp-18h] BYREF

  PropVariantClear(a2);
  v4 = a1->vt == 31;
  LocalTime = 0;
  result = -2147024809;
  UniversalTime = 0;
  if ( v4 )
  {
    RemoveISO8601TimeZoneOffset(a1->bstrVal);
    bstrVal = a1->bstrVal;
    v7 = -1;
    result = ISO8601ToSYSTEMTIMEExW(bstrVal, &LocalTime, (enum Iso8601ParsingStage *)&v7);
    if ( result >= 0 && v7 < 2 )
    {
      LocalTime.wDay = 1;
      if ( v7 < 1 )
        LocalTime.wMonth = 1;
      result = 0;
    }
  }
  if ( LocalTime.wYear )
  {
    if ( TzSpecificLocalTimeToSystemTime(0, &LocalTime, &UniversalTime)
      && SystemTimeToFileTime(&UniversalTime, &a2->filetime) )
    {
      a2->vt = 64;
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001079c  mov     [rsp-18h+arg_10], rbx
0x1800107a1  push    rbp
0x1800107a2  push    rsi
0x1800107a3  push    rdi
0x1800107a4  mov     rbp, rsp
0x1800107a7  sub     rsp, 50h
0x1800107ab  mov     rax, cs:__security_cookie
0x1800107b2  xor     rax, rsp
0x1800107b5  mov     [rbp+var_8], rax
0x1800107b9  mov     rdi, rcx
0x1800107bc  mov     rbx, rdx
0x1800107bf  mov     rcx, rdx; pvar
0x1800107c2  call    cs:__imp_PropVariantClear
0x1800107c9  nop     dword ptr [rax+rax+00h]
0x1800107ce  xor     esi, esi
0x1800107d0  xorps   xmm0, xmm0
0x1800107d3  cmp     word ptr [rdi], 1Fh
0x1800107d7  xorps   xmm1, xmm1
0x1800107da  movups  xmmword ptr [rbp+LocalTime.wYear], xmm0
0x1800107de  mov     eax, 80070057h
0x1800107e3  movups  xmmword ptr [rbp+UniversalTime.wYear], xmm1
0x1800107e7  jnz     short loc_180010826
0x1800107e9  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800107ed  call    ?RemoveISO8601TimeZoneOffset@@YAXPEAG@Z; RemoveISO8601TimeZoneOffset(ushort *)
0x1800107f2  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800107f6  lea     r8, [rbp+var_30]; enum Iso8601ParsingStage *
0x1800107fa  lea     rdx, [rbp+LocalTime]; struct _SYSTEMTIME *
0x1800107fe  mov     [rbp+var_30], 0FFFFFFFFh
0x180010805  call    ?ISO8601ToSYSTEMTIMEExW@@YAJPEBGPEAU_SYSTEMTIME@@PEAW4Iso8601ParsingStage@@@Z; ISO8601ToSYSTEMTIMEExW(ushort const *,_SYSTEMTIME *,Iso8601ParsingStage *)
0x18001080a  test    eax, eax
0x18001080c  js      short loc_180010826
0x18001080e  cmp     [rbp+var_30], 2
0x180010812  jge     short loc_180010826
0x180010814  lea     eax, [rsi+1]
0x180010817  mov     [rbp+LocalTime.wDay], ax
0x18001081b  cmp     [rbp+var_30], eax
0x18001081e  jge     short loc_180010824
0x180010820  mov     [rbp+LocalTime.wMonth], ax
0x180010824  mov     eax, esi
0x180010826  cmp     [rbp+LocalTime.wYear], si
0x18001082a  jz      short loc_18001087F
0x18001082c  lea     r8, [rbp+UniversalTime]; lpUniversalTime
0x180010830  xor     ecx, ecx; lpTimeZoneInformation
0x180010832  lea     rdx, [rbp+LocalTime]; lpLocalTime
0x180010836  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18001083d  nop     dword ptr [rax+rax+00h]
0x180010842  test    eax, eax
0x180010844  jz      short loc_180010867
0x180010846  lea     rdx, [rbx+8]; lpFileTime
0x18001084a  lea     rcx, [rbp+UniversalTime]; lpSystemTime
0x18001084e  call    cs:__imp_SystemTimeToFileTime
0x180010855  nop     dword ptr [rax+rax+00h]
0x18001085a  test    eax, eax
0x18001085c  jz      short loc_180010867
0x18001085e  mov     word ptr [rbx], 40h ; '@'
0x180010863  mov     eax, esi
0x180010865  jmp     short loc_18001087F
0x180010867  call    cs:__imp_GetLastError
0x18001086e  nop     dword ptr [rax+rax+00h]
0x180010873  test    eax, eax
0x180010875  jle     short loc_18001087F
0x180010877  movzx   eax, ax
0x18001087a  or      eax, 80070000h
0x18001087f  mov     rcx, [rbp+var_8]
0x180010883  xor     rcx, rsp; StackCookie
0x180010886  call    __security_check_cookie
0x18001088b  mov     rbx, [rsp+50h+arg_10]
0x180010893  add     rsp, 50h
0x180010897  pop     rdi
0x180010898  pop     rsi
0x180010899  pop     rbp
0x18001089a  retn
```
