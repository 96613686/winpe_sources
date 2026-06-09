# UserAccount::GetUserSid(ushort * *)

- ea: `0x180019f80`
- end: `0x180019fb6`
- name: `?GetUserSid@UserAccount@@UEAAJPEAPEAG@Z`
- size: `54`
- prototype: `int(UserAccount *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180008a38`
- `0x180019e4c`
- `0x180019f80`

## string_xrefs

- `0x180019f9a`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccount.cpp`

## pseudocode

```c
__int64 __fastcall UserAccount::GetUserSid(UserAccount *this, unsigned __int16 **a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CopyTo(
         (__int64)this + 56,
         a2);
  v3 = v2;
  if ( v2 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccount.cpp",
      (const char *)(unsigned int)v2,
      v5);
  return v3;
}

```

## disassembly

```asm
0x180019f80  push    rbx; int
0x180019f82  sub     rsp, 20h
0x180019f86  add     rcx, 38h ; '8'
0x180019f8a  call    ?CopyTo@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CopyTo(ushort * *)
0x180019f8f  mov     ebx, eax
0x180019f91  test    eax, eax
0x180019f93  jns     short loc_180019FAE
0x180019f95  mov     rcx, [rsp+28h]; this
0x180019f9a  lea     r8, aShellcommonShe_8; "shellcommon\\shell\\sharedpc\\accountma"...
0x180019fa1  mov     r9d, eax; char *
0x180019fa4  mov     edx, 2Bh ; '+'; void *
0x180019fa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019fae  mov     eax, ebx
0x180019fb0  add     rsp, 20h
0x180019fb4  pop     rbx
0x180019fb5  retn
```
