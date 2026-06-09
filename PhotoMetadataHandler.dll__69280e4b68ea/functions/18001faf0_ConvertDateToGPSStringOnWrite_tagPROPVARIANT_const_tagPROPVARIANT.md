# ConvertDateToGPSStringOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001faf0`
- end: `0x18001fc43`
- name: `?ConvertDateToGPSStringOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `339`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d860`

## callees

- `0x1800089f0`
- `0x1800096a0`
- `0x18000ea14`
- `0x180016a40`
- `0x18001faf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fb1f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fc17`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fb1f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fc17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb4a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001fb3a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001fb3a`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18001fb87`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18001fb87`

## pseudocode

```c
__int64 __fastcall ConvertDateToGPSStringOnWrite(const struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2)
{
  signed int LastError; // eax
  int v5; // ebx
  __int64 wYear; // r9
  unsigned __int16 *bstrVal; // rcx
  int v8; // eax
  int wMonth; // [rsp+20h] [rbp-38h]
  int wDay; // [rsp+28h] [rbp-30h]
  ULONGLONG pullResult; // [rsp+30h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-20h] BYREF

  SystemTime = 0;
  PropVariantClear(a2);
  if ( a1->vt == 64 )
  {
    if ( !FileTimeToSystemTime(&a1->filetime, &SystemTime) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 < 0 )
        return (unsigned int)v5;
    }
  }
  else
  {
    v5 = -2147024809;
    if ( a1->vt != 7 || !VariantTimeToSystemTime(a1->dblVal, &SystemTime) )
      return (unsigned int)v5;
  }
  pullResult = 0;
  v5 = ULongLongMult(0xBu, 2u, &pullResult);
  if ( v5 >= 0 )
  {
    v5 = CoTaskMemAllocWithInit(pullResult, (void **)&a2->puuid);
    if ( v5 >= 0 )
    {
      wYear = SystemTime.wYear;
      wDay = SystemTime.wDay;
      wMonth = SystemTime.wMonth;
      bstrVal = a2->bstrVal;
      a2->vt = 31;
      v8 = StringCchPrintfW(bstrVal, 0xBu, L"%04d:%02d:%02d", wYear, wMonth, wDay);
      v5 = v8;
      if ( v8 == -2147024774 )
      {
        v5 = -2147024809;
      }
      else if ( v8 >= 0 )
      {
        return (unsigned int)v5;
      }
      PropVariantClear(a2);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001faf0  mov     [rsp+arg_10], rbx
0x18001faf5  mov     [rsp+arg_18], rsi
0x18001fafa  push    rdi
0x18001fafb  sub     rsp, 50h
0x18001faff  mov     rax, cs:__security_cookie
0x18001fb06  xor     rax, rsp
0x18001fb09  mov     [rsp+58h+var_10], rax
0x18001fb0e  mov     rsi, rcx
0x18001fb11  xorps   xmm0, xmm0
0x18001fb14  mov     rcx, rdx; pvar
0x18001fb17  mov     rdi, rdx
0x18001fb1a  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x18001fb1f  call    cs:__imp_PropVariantClear
0x18001fb26  nop     dword ptr [rax+rax+00h]
0x18001fb2b  cmp     word ptr [rsi], 40h ; '@'
0x18001fb2f  jnz     short loc_18001FB6E
0x18001fb31  lea     rcx, [rsi+8]; lpFileTime
0x18001fb35  lea     rdx, [rsp+58h+SystemTime]; lpSystemTime
0x18001fb3a  call    cs:__imp_FileTimeToSystemTime
0x18001fb41  nop     dword ptr [rax+rax+00h]
0x18001fb46  test    eax, eax
0x18001fb48  jnz     short loc_18001FB9B
0x18001fb4a  call    cs:__imp_GetLastError
0x18001fb51  nop     dword ptr [rax+rax+00h]
0x18001fb56  mov     ebx, eax
0x18001fb58  test    eax, eax
0x18001fb5a  jle     short loc_18001FB65
0x18001fb5c  movzx   ebx, ax
0x18001fb5f  or      ebx, 80070000h
0x18001fb65  test    ebx, ebx
0x18001fb67  jns     short loc_18001FB9B
0x18001fb69  jmp     loc_18001FC23
0x18001fb6e  cmp     word ptr [rsi], 7
0x18001fb72  mov     ebx, 80070057h
0x18001fb77  jnz     loc_18001FC23
0x18001fb7d  movsd   xmm0, qword ptr [rsi+8]; vtime
0x18001fb82  lea     rdx, [rsp+58h+SystemTime]; lpSystemTime
0x18001fb87  call    cs:__imp_VariantTimeToSystemTime
0x18001fb8e  nop     dword ptr [rax+rax+00h]
0x18001fb93  test    eax, eax
0x18001fb95  jz      loc_18001FC23
0x18001fb9b  mov     edx, 2; ullMultiplier
0x18001fba0  mov     [rsp+58h+pullResult], 0
0x18001fba9  lea     r8, [rsp+58h+pullResult]; pullResult
0x18001fbae  lea     ecx, [rdx+9]; ullMultiplicand
0x18001fbb1  call    ULongLongMult
0x18001fbb6  mov     ebx, eax
0x18001fbb8  test    eax, eax
0x18001fbba  js      short loc_18001FC23
0x18001fbbc  mov     rcx, [rsp+58h+pullResult]; Size
0x18001fbc1  lea     rdx, [rdi+8]; void **
0x18001fbc5  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001fbca  mov     ebx, eax
0x18001fbcc  test    eax, eax
0x18001fbce  js      short loc_18001FC23
0x18001fbd0  movzx   ecx, [rsp+58h+SystemTime.wMonth]
0x18001fbd5  lea     r8, a04d02d02d; "%04d:%02d:%02d"
0x18001fbdc  movzx   eax, [rsp+58h+SystemTime.wDay]
0x18001fbe1  mov     edx, 0Bh; unsigned __int64
0x18001fbe6  movzx   r9d, [rsp+58h+SystemTime.wYear]
0x18001fbec  mov     [rsp+58h+var_30], eax
0x18001fbf0  mov     [rsp+58h+var_38], ecx
0x18001fbf4  mov     rcx, [rdi+8]; unsigned __int16 *
0x18001fbf8  mov     word ptr [rdi], 1Fh
0x18001fbfd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fc02  mov     ebx, eax
0x18001fc04  cmp     eax, 8007007Ah
0x18001fc09  jnz     short loc_18001FC10
0x18001fc0b  lea     ebx, [rax-23h]
0x18001fc0e  jmp     short loc_18001FC14
0x18001fc10  test    eax, eax
0x18001fc12  jns     short loc_18001FC23
0x18001fc14  mov     rcx, rdi; pvar
0x18001fc17  call    cs:__imp_PropVariantClear
0x18001fc1e  nop     dword ptr [rax+rax+00h]
0x18001fc23  mov     eax, ebx
0x18001fc25  mov     rcx, [rsp+58h+var_10]
0x18001fc2a  xor     rcx, rsp; StackCookie
0x18001fc2d  call    __security_check_cookie
0x18001fc32  mov     rbx, [rsp+58h+arg_10]
0x18001fc37  mov     rsi, [rsp+58h+arg_18]
0x18001fc3c  add     rsp, 50h
0x18001fc40  pop     rdi
0x18001fc41  retn
```
