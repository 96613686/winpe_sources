# SharingToken::GenerateTokenId(_GUID &)

- ea: `0x180011bdc`
- end: `0x180011c5b`
- name: `?GenerateTokenId@SharingToken@@SAJAEAU_GUID@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f740`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x180011bdc`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180011c05`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180011c05`

## string_xrefs

- `0x180011c27`: `SharingToken::GenerateTokenId`

## pseudocode

```c
__int64 __fastcall SharingToken::GenerateTokenId(struct _GUID *a1)
{
  HRESULT v2; // ebx
  DSLogger *v3; // rax
  HRESULT v5; // [rsp+20h] [rbp-38h]
  GUID pguid; // [rsp+30h] [rbp-28h] BYREF

  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 >= 0 )
  {
    *a1 = pguid;
  }
  else
  {
    v3 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    v5 = v2;
    DSLogger::LogError(v3, L"SharingToken::GenerateTokenId", 0x3Au, L"hr=0x%x.", v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180011bdc  mov     [rsp+arg_8], rbx
0x180011be1  push    rdi
0x180011be2  sub     rsp, 50h
0x180011be6  mov     rax, cs:__security_cookie
0x180011bed  xor     rax, rsp
0x180011bf0  mov     [rsp+58h+var_18], rax
0x180011bf5  mov     rdi, rcx
0x180011bf8  xorps   xmm0, xmm0
0x180011bfb  lea     rcx, [rsp+58h+pguid]; pguid
0x180011c00  movups  xmmword ptr [rsp+58h+pguid.Data1], xmm0
0x180011c05  call    cs:__imp_CoCreateGuid
0x180011c0b  mov     ebx, eax
0x180011c0d  test    eax, eax
0x180011c0f  jns     short loc_180011C38
0x180011c11  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180011c16  lea     r9, aHr0xX; "hr=0x%x."
0x180011c1d  mov     [rsp+58h+var_38], ebx
0x180011c21  mov     r8d, 3Ah ; ':'; unsigned int
0x180011c27  lea     rdx, aSharingtokenGe; "SharingToken::GenerateTokenId"
0x180011c2e  mov     rcx, rax; this
0x180011c31  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180011c36  jmp     short loc_180011C41
0x180011c38  movups  xmm0, xmmword ptr [rsp+58h+pguid.Data1]
0x180011c3d  movdqu  xmmword ptr [rdi], xmm0
0x180011c41  mov     eax, ebx
0x180011c43  mov     rcx, [rsp+58h+var_18]
0x180011c48  xor     rcx, rsp; StackCookie
0x180011c4b  call    __security_check_cookie
0x180011c50  mov     rbx, [rsp+58h+arg_8]
0x180011c55  add     rsp, 50h
0x180011c59  pop     rdi
0x180011c5a  retn
```
