# QueryCAMSettingAppList

- ea: `0x1800ee3c0`
- end: `0x1800ee48a`
- name: `QueryCAMSettingAppList`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800eabf4`
- `0x1800ee3c0`
- `0x1800f3528`

## string_xrefs

- `0x1800ee3d4`: `onecore\base\devices\cam\desktop\lib\storage\capabilityaccessmanagerdesktopstorage.cpp`
- `0x1800ee404`: `onecore\base\devices\cam\desktop\lib\storage\capabilityaccessmanagerdesktopstorage.cpp`
- `0x1800ee42c`: `onecore\base\devices\cam\desktop\lib\storage\capabilityaccessmanagerdesktopstorage.cpp`
- `0x1800ee454`: `onecore\base\devices\cam\desktop\lib\storage\capabilityaccessmanagerdesktopstorage.cpp`

## pseudocode

```c
__int64 __fastcall QueryCAMSettingAppList(
        Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM *a1,
        const wchar_t *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int64 *a5)
{
  __int64 result; // rax
  wil *v6; // rcx
  unsigned int v7; // r8d
  const char *v8; // r9
  int v9; // eax
  wil *v10; // rcx
  int v11; // eax
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a4 )
  {
    if ( a5 )
    {
      if ( a2 )
      {
        if ( a3 )
        {
          LOBYTE(a1) = (_BYTE)a1 != 0;
          try
          {
            try
            {
              Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM::QueryAppList(a1, a2, a3, a4, a5);
              result = 0;
            }
            catch ( wil::ResultException )
            {
              v9 = wil::ResultFromCaughtException(v6);
              if ( (unsigned int)HRESULT_SQLITE_STRIP_EXTENDED(v9) == -2018574325 )
              {
                v11 = wil::ResultFromCaughtException(v10);
                ForceRecoverDatabase(v11, L"QueryCAMSettingAppList");
              }
              throw;
            }
          }
          catch ( ... )
          {
            return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x189, v7, v8);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x177,
            (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\capabilityaccessmanagerdesktopstorage.cpp",
            (const char *)0x80070057LL,
            v12);
          return 2147942487LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x176,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\capabilityaccessmanagerdesktopstorage.cpp",
          (const char *)0x80070057LL,
          v12);
        return 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x175,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\capabilityaccessmanagerdesktopstorage.cpp",
        (const char *)0x80004003LL,
        v12);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x174,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\capabilityaccessmanagerdesktopstorage.cpp",
      (const char *)0x80004003LL,
      v12);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800ee3c0  sub     rsp, 38h
0x1800ee3c4  test    r9, r9
0x1800ee3c7  jnz     short loc_1800EE3EF
0x1800ee3c9  mov     rcx, [rsp+38h]; this
0x1800ee3ce  mov     r9d, 80004003h; char *
0x1800ee3d4  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ee3db  mov     edx, 174h; void *
0x1800ee3e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ee3e5  mov     eax, 80004003h
0x1800ee3ea  jmp     loc_1800EE484
0x1800ee3ef  mov     rax, [rsp+38h+arg_20]
0x1800ee3f4  test    rax, rax
0x1800ee3f7  jnz     short loc_1800EE41C
0x1800ee3f9  mov     rcx, [rsp+38h]; this
0x1800ee3fe  mov     r9d, 80004003h; char *
0x1800ee404  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ee40b  mov     edx, 175h; void *
0x1800ee410  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ee415  mov     eax, 80004003h
0x1800ee41a  jmp     short loc_1800EE484
0x1800ee41c  test    rdx, rdx
0x1800ee41f  jnz     short loc_1800EE444
0x1800ee421  mov     rcx, [rsp+38h]; this
0x1800ee426  mov     r9d, 80070057h; char *
0x1800ee42c  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ee433  mov     edx, 176h; void *
0x1800ee438  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ee43d  mov     eax, 80070057h
0x1800ee442  jmp     short loc_1800EE484
0x1800ee444  test    r8, r8
0x1800ee447  jnz     short loc_1800EE46C
0x1800ee449  mov     rcx, [rsp+38h]; this
0x1800ee44e  mov     r9d, 80070057h; char *
0x1800ee454  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ee45b  mov     edx, 177h; void *
0x1800ee460  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ee465  mov     eax, 80070057h
0x1800ee46a  jmp     short loc_1800EE484
0x1800ee46c  test    cl, cl
0x1800ee46e  setnz   cl; this
0x1800ee471  mov     qword ptr [rsp+38h+var_18], rax; unsigned __int64 *
0x1800ee476  call    ?QueryAppList@CAM@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAX_NPEBG1PEA_KPEAPEAUCAMStorageAppConsent@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM::QueryAppList(bool,ushort const *,ushort const *,unsigned __int64 *,CAMStorageAppConsent * *)
0x1800ee47b  nop
0x1800ee47c  xor     eax, eax
0x1800ee47e  jmp     short loc_1800EE484
0x1800ee480  mov     eax, [rsp+38h+arg_18]
0x1800ee484  add     rsp, 38h
0x1800ee488  retn
```
