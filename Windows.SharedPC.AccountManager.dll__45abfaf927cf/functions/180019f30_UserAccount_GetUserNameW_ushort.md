# UserAccount::GetUserNameW(ushort * *)

- ea: `0x180019f30`
- end: `0x180019f7a`
- name: `?GetUserNameW@UserAccount@@UEAAJPEAPEAG@Z`
- size: `74`
- prototype: `int(UserAccount *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008a38`
- `0x180019e4c`
- `0x180019f30`

## string_xrefs

- `0x180019f57`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccount.cpp`

## pseudocode

```c
__int64 __fastcall UserAccount::GetUserNameW(UserAccount *this, unsigned __int16 **a2)
{
  _QWORD *v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (_QWORD *)((char *)this + 80);
  *a2 = 0;
  if ( !*v2 )
    return 2147943568LL;
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CopyTo((__int64)v2, a2);
  v4 = v3;
  if ( v3 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccount.cpp",
      (const char *)(unsigned int)v3,
      v6);
  return v4;
}

```

## disassembly

```asm
0x180019f30  push    rbx; int
0x180019f32  sub     rsp, 20h
0x180019f36  add     rcx, 50h ; 'P'
0x180019f3a  mov     qword ptr [rdx], 0
0x180019f41  cmp     qword ptr [rcx], 0
0x180019f45  jz      short loc_180019F6F
0x180019f47  call    ?CopyTo@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CopyTo(ushort * *)
0x180019f4c  mov     ebx, eax
0x180019f4e  test    eax, eax
0x180019f50  jns     short loc_180019F6B
0x180019f52  mov     rcx, [rsp+28h]; this
0x180019f57  lea     r8, aShellcommonShe_8; "shellcommon\\shell\\sharedpc\\accountma"...
0x180019f5e  mov     r9d, eax; char *
0x180019f61  mov     edx, 33h ; '3'; void *
0x180019f66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f6b  mov     eax, ebx
0x180019f6d  jmp     short loc_180019F74
0x180019f6f  mov     eax, 80070490h
0x180019f74  add     rsp, 20h
0x180019f78  pop     rbx
0x180019f79  retn
```
