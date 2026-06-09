# MitigationRequestPayload::SetClientTransactionId(void)

- ea: `0x180026e18`
- end: `0x180026eb5`
- name: `?SetClientTransactionId@MitigationRequestPayload@@QEAAJXZ`
- size: `157`
- prototype: `__int64 __fastcall(MitigationRequestPayload *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180024918`

## callees

- `0x18000a6e0`
- `0x18001208c`
- `0x18002407c`
- `0x180026e18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180026e88`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180026e88`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180026e41`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180026e41`

## pseudocode

```c
__int64 __fastcall MitigationRequestPayload::SetClientTransactionId(MitigationRequestPayload *this)
{
  HRESULT v2; // ebx
  __int64 v3; // rdx
  GUID pguid; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 < 0 )
  {
    v3 = 56;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\mitigationrequestpayload.cpp",
      (const char *)(unsigned int)v2,
      pguid.Data1);
    return (unsigned int)v2;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 16);
  *((_QWORD *)this + 3) = -1;
  *((_QWORD *)this + 4) = -1;
  v2 = StringFromCLSID(&pguid, (LPOLESTR *)this + 2);
  if ( v2 < 0 )
  {
    v3 = 57;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180026e18  mov     [rsp+arg_8], rbx
0x180026e1d  push    rdi
0x180026e1e  sub     rsp, 40h
0x180026e22  mov     rax, cs:__security_cookie
0x180026e29  xor     rax, rsp
0x180026e2c  mov     [rsp+48h+var_18], rax
0x180026e31  mov     rdi, rcx
0x180026e34  xorps   xmm0, xmm0
0x180026e37  lea     rcx, [rsp+48h+pguid]; pguid
0x180026e3c  movups  xmmword ptr [rsp+48h+pguid.Data1], xmm0; int
0x180026e41  call    cs:__imp_CoCreateGuid
0x180026e47  mov     ebx, eax
0x180026e49  test    eax, eax
0x180026e4b  jns     short loc_180026E6A
0x180026e4d  mov     edx, 38h ; '8'; void *
0x180026e52  mov     rcx, [rsp+48h]; this
0x180026e57  lea     r8, aOnecoreBaseDia_40; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180026e5e  mov     r9d, ebx; char *
0x180026e61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026e66  mov     eax, ebx
0x180026e68  jmp     short loc_180026E9D
0x180026e6a  lea     rcx, [rdi+10h]
0x180026e6e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180026e73  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026e77  lea     rdx, [rdi+10h]; lplpsz
0x180026e7b  lea     rcx, [rsp+48h+pguid]; rclsid
0x180026e80  mov     [rdi+18h], rax
0x180026e84  mov     [rdi+20h], rax
0x180026e88  call    cs:__imp_StringFromCLSID
0x180026e8e  mov     ebx, eax
0x180026e90  test    eax, eax
0x180026e92  jns     short loc_180026E9B
0x180026e94  mov     edx, 39h ; '9'
0x180026e99  jmp     short loc_180026E52
0x180026e9b  xor     eax, eax
0x180026e9d  mov     rcx, [rsp+48h+var_18]
0x180026ea2  xor     rcx, rsp; StackCookie
0x180026ea5  call    __security_check_cookie
0x180026eaa  mov     rbx, [rsp+48h+arg_8]
0x180026eaf  add     rsp, 40h
0x180026eb3  pop     rdi
0x180026eb4  retn
```
