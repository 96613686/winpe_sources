# ConvertDateToGPSStringOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001ec58`
- end: `0x18001ed8c`
- name: `?ConvertDateToGPSStringOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `308`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001cae0`

## callees

- `0x1800076b0`
- `0x180007d90`
- `0x18000e364`
- `0x180016020`
- `0x18001ec58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ec87`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ed67`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ec87`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ed67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eca6`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001ec9c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001ec9c`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18001ecdd`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18001ecdd`

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
0x18001ec58  mov     [rsp+arg_10], rbx
0x18001ec5d  mov     [rsp+arg_18], rsi
0x18001ec62  push    rdi
0x18001ec63  sub     rsp, 50h
0x18001ec67  mov     rax, cs:__security_cookie
0x18001ec6e  xor     rax, rsp
0x18001ec71  mov     [rsp+58h+var_10], rax
0x18001ec76  mov     rsi, rcx
0x18001ec79  xorps   xmm0, xmm0
0x18001ec7c  mov     rcx, rdx; pvar
0x18001ec7f  mov     rdi, rdx
0x18001ec82  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x18001ec87  call    cs:__imp_PropVariantClear
0x18001ec8d  cmp     word ptr [rsi], 40h ; '@'
0x18001ec91  jnz     short loc_18001ECC4
0x18001ec93  lea     rcx, [rsi+8]; lpFileTime
0x18001ec97  lea     rdx, [rsp+58h+SystemTime]; lpSystemTime
0x18001ec9c  call    cs:__imp_FileTimeToSystemTime
0x18001eca2  test    eax, eax
0x18001eca4  jnz     short loc_18001ECEB
0x18001eca6  call    cs:__imp_GetLastError
0x18001ecac  mov     ebx, eax
0x18001ecae  test    eax, eax
0x18001ecb0  jle     short loc_18001ECBB
0x18001ecb2  movzx   ebx, ax
0x18001ecb5  or      ebx, 80070000h
0x18001ecbb  test    ebx, ebx
0x18001ecbd  jns     short loc_18001ECEB
0x18001ecbf  jmp     loc_18001ED6D
0x18001ecc4  cmp     word ptr [rsi], 7
0x18001ecc8  mov     ebx, 80070057h
0x18001eccd  jnz     loc_18001ED6D
0x18001ecd3  movsd   xmm0, qword ptr [rsi+8]; vtime
0x18001ecd8  lea     rdx, [rsp+58h+SystemTime]; lpSystemTime
0x18001ecdd  call    cs:__imp_VariantTimeToSystemTime
0x18001ece3  test    eax, eax
0x18001ece5  jz      loc_18001ED6D
0x18001eceb  mov     edx, 2; ullMultiplier
0x18001ecf0  mov     [rsp+58h+pullResult], 0
0x18001ecf9  lea     r8, [rsp+58h+pullResult]; pullResult
0x18001ecfe  lea     ecx, [rdx+9]; ullMultiplicand
0x18001ed01  call    ULongLongMult
0x18001ed06  mov     ebx, eax
0x18001ed08  test    eax, eax
0x18001ed0a  js      short loc_18001ED6D
0x18001ed0c  mov     rcx, [rsp+58h+pullResult]; Size
0x18001ed11  lea     rdx, [rdi+8]; void **
0x18001ed15  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001ed1a  mov     ebx, eax
0x18001ed1c  test    eax, eax
0x18001ed1e  js      short loc_18001ED6D
0x18001ed20  movzx   ecx, [rsp+58h+SystemTime.wMonth]
0x18001ed25  lea     r8, a04d02d02d; "%04d:%02d:%02d"
0x18001ed2c  movzx   eax, [rsp+58h+SystemTime.wDay]
0x18001ed31  mov     edx, 0Bh; unsigned __int64
0x18001ed36  movzx   r9d, [rsp+58h+SystemTime.wYear]
0x18001ed3c  mov     [rsp+58h+var_30], eax
0x18001ed40  mov     [rsp+58h+var_38], ecx
0x18001ed44  mov     rcx, [rdi+8]; unsigned __int16 *
0x18001ed48  mov     word ptr [rdi], 1Fh
0x18001ed4d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ed52  mov     ebx, eax
0x18001ed54  cmp     eax, 8007007Ah
0x18001ed59  jnz     short loc_18001ED60
0x18001ed5b  lea     ebx, [rax-23h]
0x18001ed5e  jmp     short loc_18001ED64
0x18001ed60  test    eax, eax
0x18001ed62  jns     short loc_18001ED6D
0x18001ed64  mov     rcx, rdi; pvar
0x18001ed67  call    cs:__imp_PropVariantClear
0x18001ed6d  mov     eax, ebx
0x18001ed6f  mov     rcx, [rsp+58h+var_10]
0x18001ed74  xor     rcx, rsp; StackCookie
0x18001ed77  call    __security_check_cookie
0x18001ed7c  mov     rbx, [rsp+58h+arg_10]
0x18001ed81  mov     rsi, [rsp+58h+arg_18]
0x18001ed86  add     rsp, 50h
0x18001ed8a  pop     rdi
0x18001ed8b  retn
```
