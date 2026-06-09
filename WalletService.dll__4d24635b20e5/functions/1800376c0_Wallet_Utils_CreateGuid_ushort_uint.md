# Wallet::Utils::CreateGuid(ushort *,uint)

- ea: `0x1800376c0`
- end: `0x180037726`
- name: `?CreateGuid@Utils@Wallet@@YAJPEAGI@Z`
- size: `102`
- prototype: `__int64 __fastcall(LPOLESTR lpsz, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014d28`
- `0x180027434`
- `0x18002f86c`
- `0x180037ce0`
- `0x180039a7c`

## callees

- `0x1800376c0`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800376ff`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800376ff`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800376e5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800376e5`

## pseudocode

```c
__int64 __fastcall Wallet::Utils::CreateGuid(LPOLESTR lpsz, unsigned __int16 *a2)
{
  HRESULT v3; // ecx
  int v4; // eax
  GUID pguid; // [rsp+20h] [rbp-28h] BYREF

  pguid = 0;
  v3 = CoCreateGuid(&pguid);
  if ( v3 >= 0 )
  {
    v4 = StringFromGUID2(&pguid, lpsz, 40);
    v3 = 0;
    if ( !v4 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800376c0  push    rbx
0x1800376c2  sub     rsp, 40h
0x1800376c6  mov     rax, cs:__security_cookie
0x1800376cd  xor     rax, rsp
0x1800376d0  mov     [rsp+48h+var_18], rax
0x1800376d5  mov     rbx, rcx
0x1800376d8  xorps   xmm0, xmm0
0x1800376db  lea     rcx, [rsp+48h+pguid]; pguid
0x1800376e0  movups  xmmword ptr [rsp+48h+pguid.Data1], xmm0
0x1800376e5  call    cs:__imp_CoCreateGuid
0x1800376eb  mov     ecx, eax
0x1800376ed  test    eax, eax
0x1800376ef  js      short loc_180037711
0x1800376f1  mov     r8d, 28h ; '('; cchMax
0x1800376f7  lea     rcx, [rsp+48h+pguid]; rguid
0x1800376fc  mov     rdx, rbx; lpsz
0x1800376ff  call    cs:__imp_StringFromGUID2
0x180037705  xor     ecx, ecx
0x180037707  mov     edx, 80004005h
0x18003770c  test    eax, eax
0x18003770e  cmovz   ecx, edx
0x180037711  mov     eax, ecx
0x180037713  mov     rcx, [rsp+48h+var_18]
0x180037718  xor     rcx, rsp; StackCookie
0x18003771b  call    __security_check_cookie
0x180037720  add     rsp, 40h
0x180037724  pop     rbx
0x180037725  retn
```
