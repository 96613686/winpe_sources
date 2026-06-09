# CreateCorrelationId(ushort * *)

- ea: `0x180074e6c`
- end: `0x180074f04`
- name: `?CreateCorrelationId@@YAJPEAPEAG@Z`
- size: `152`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180074fa0`

## callees

- `0x180007270`
- `0x18006dbb0`
- `0x180074e6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180074ea3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180074ea3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180074ec3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180074ec3`

## pseudocode

```c
HRESULT __fastcall CreateCorrelationId(unsigned __int16 **a1)
{
  HRESULT result; // eax
  int v3; // eax
  GUID pguid; // [rsp+20h] [rbp-78h] BYREF
  OLECHAR sz; // [rsp+30h] [rbp-68h] BYREF
  wchar_t pszSrc[39]; // [rsp+32h] [rbp-66h] BYREF

  pguid = 0;
  if ( !a1 )
    return -2147024809;
  result = CoCreateGuid(&pguid);
  if ( result >= 0 )
  {
    v3 = StringFromGUID2(&pguid, &sz, 39);
    if ( v3 )
      return CopyString(pszSrc, v3 - 3, a1);
    else
      return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x180074e6c  push    rbx
0x180074e6e  sub     rsp, 90h
0x180074e75  mov     rax, cs:__security_cookie
0x180074e7c  xor     rax, rsp
0x180074e7f  mov     [rsp+98h+var_18], rax
0x180074e87  xorps   xmm0, xmm0
0x180074e8a  mov     rbx, rcx
0x180074e8d  movups  xmmword ptr [rsp+98h+pguid.Data1], xmm0
0x180074e92  test    rcx, rcx
0x180074e95  jnz     short loc_180074E9E
0x180074e97  mov     eax, 80070057h
0x180074e9c  jmp     short loc_180074EEA
0x180074e9e  lea     rcx, [rsp+98h+pguid]; pguid
0x180074ea3  call    cs:__imp_CoCreateGuid
0x180074eaa  nop     dword ptr [rax+rax+00h]
0x180074eaf  test    eax, eax
0x180074eb1  js      short loc_180074EEA
0x180074eb3  mov     r8d, 27h ; '''; cchMax
0x180074eb9  lea     rdx, [rsp+98h+sz]; lpsz
0x180074ebe  lea     rcx, [rsp+98h+pguid]; rguid
0x180074ec3  call    cs:__imp_StringFromGUID2
0x180074eca  nop     dword ptr [rax+rax+00h]
0x180074ecf  test    eax, eax
0x180074ed1  jnz     short loc_180074EDA
0x180074ed3  mov     eax, 80004005h
0x180074ed8  jmp     short loc_180074EEA
0x180074eda  lea     edx, [rax-3]; unsigned int
0x180074edd  mov     r8, rbx; unsigned __int16 **
0x180074ee0  lea     rcx, [rsp+98h+pszSrc]; pszSrc
0x180074ee5  call    ?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180074eea  mov     rcx, [rsp+98h+var_18]
0x180074ef2  xor     rcx, rsp; StackCookie
0x180074ef5  call    __security_check_cookie
0x180074efa  add     rsp, 90h
0x180074f01  pop     rbx
0x180074f02  retn
```
