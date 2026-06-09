# GetTargetedSID

- ea: `0x18005a894`
- end: `0x18005a984`
- name: `GetTargetedSID`
- size: `240`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800474c8`
- `0x180049a80`
- `0x18004a470`
- `0x18004afe4`
- `0x18004c280`
- `0x18004c770`
- `0x18005b020`

## callees

- `0x180016918`
- `0x180017284`
- `0x180018f88`
- `0x180040b40`
- `0x18005a894`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x18005a930`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18005a930`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18005a8ec`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18005a8ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a908`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a951`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a908`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a951`

## string_xrefs

- `0x18005a963`: `S-1-0-INVALIDSID-1000`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetTargetedSID(__int64 a1)
{
  int CurrentUserSid; // edi
  _BYTE v4[16]; // [rsp+20h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp+18h] BYREF

  v4[0] = 0;
  v4[2] = 0;
  CurrentUserSid = AutoImpersonate::ImpersonateClient((AutoImpersonate *)v4);
  if ( (int)(CurrentUserSid + 0x80000000) >= 0 && CurrentUserSid != -2147417833
    || (hMem = 0, CurrentUserSid = DmGetCurrentUserSid((unsigned __int16 **)&hMem), CurrentUserSid < 0) )
  {
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v4);
    return (unsigned int)CurrentUserSid;
  }
  std::wstring::operator=(a1, hMem);
  LocalFree(hMem);
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v4);
  if ( (unsigned __int8)std::operator==<unsigned short>(a1) )
  {
    hMem = 0;
    if ( (int)DmGetActiveUserSid((unsigned __int16 **)&hMem) < 0 )
      return 2147943717LL;
    std::wstring::operator=(a1, hMem);
    LocalFree(hMem);
  }
  if ( (unsigned __int8)std::operator==<unsigned short>(a1) )
    std::wstring::operator=(a1, L"S-1-0-INVALIDSID-1000");
  return 0;
}

```

## disassembly

```asm
0x18005a894  mov     [rsp-8+arg_0], rbx
0x18005a899  mov     [rsp-8+arg_10], rdi
0x18005a89e  push    rbp
0x18005a89f  mov     rbp, rsp
0x18005a8a2  sub     rsp, 30h
0x18005a8a6  mov     rbx, rcx
0x18005a8a9  mov     [rbp+var_10], 0
0x18005a8ad  mov     [rbp+var_E], 0
0x18005a8b1  lea     rcx, [rbp+var_10]; this
0x18005a8b5  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x18005a8ba  mov     edi, eax
0x18005a8bc  mov     eax, 80000000h
0x18005a8c1  lea     edx, [rdi+rax]
0x18005a8c4  test    eax, edx
0x18005a8c6  jnz     short loc_18005A8E0
0x18005a8c8  cmp     edi, 80010117h
0x18005a8ce  jz      short loc_18005A8E0
0x18005a8d0  lea     rcx, [rbp+var_10]; this
0x18005a8d4  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18005a8d9  mov     eax, edi
0x18005a8db  jmp     loc_18005A974
0x18005a8e0  mov     [rbp+hMem], 0
0x18005a8e8  lea     rcx, [rbp+hMem]
0x18005a8ec  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x18005a8f2  mov     edi, eax
0x18005a8f4  test    eax, eax
0x18005a8f6  js      short loc_18005A8D0
0x18005a8f8  mov     rdx, [rbp+hMem]
0x18005a8fc  mov     rcx, rbx
0x18005a8ff  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18005a904  mov     rcx, [rbp+hMem]; hMem
0x18005a908  call    cs:__imp_LocalFree
0x18005a90e  nop
0x18005a90f  lea     rcx, [rbp+var_10]; this
0x18005a913  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18005a918  mov     rcx, rbx
0x18005a91b  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const * const)
0x18005a920  test    al, al
0x18005a922  jz      short loc_18005A957
0x18005a924  mov     [rbp+hMem], 0
0x18005a92c  lea     rcx, [rbp+hMem]
0x18005a930  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18005a936  test    eax, eax
0x18005a938  jns     short loc_18005A941
0x18005a93a  mov     eax, 80070525h
0x18005a93f  jmp     short loc_18005A974
0x18005a941  mov     rdx, [rbp+hMem]
0x18005a945  mov     rcx, rbx
0x18005a948  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18005a94d  mov     rcx, [rbp+hMem]; hMem
0x18005a951  call    cs:__imp_LocalFree
0x18005a957  mov     rcx, rbx
0x18005a95a  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const * const)
0x18005a95f  test    al, al
0x18005a961  jz      short loc_18005A972
0x18005a963  lea     rdx, aS10Invalidsid1; "S-1-0-INVALIDSID-1000"
0x18005a96a  mov     rcx, rbx
0x18005a96d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18005a972  xor     eax, eax
0x18005a974  mov     rbx, [rsp+30h+arg_0]
0x18005a979  mov     rdi, [rsp+30h+arg_10]
0x18005a97e  add     rsp, 30h
0x18005a982  pop     rbp
0x18005a983  retn
```
