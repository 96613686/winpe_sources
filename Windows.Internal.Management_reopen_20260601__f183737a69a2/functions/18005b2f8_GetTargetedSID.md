# GetTargetedSID

- ea: `0x18005b2f8`
- end: `0x18005b401`
- name: `GetTargetedSID`
- size: `265`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180047f64`
- `0x180049bf0`
- `0x18004a650`
- `0x18004b1e0`
- `0x18004c560`
- `0x18004ca60`
- `0x18005bad0`

## callees

- `0x180017078`
- `0x180017a88`
- `0x1800181cc`
- `0x18004057c`
- `0x18005b2f8`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x18005b3a0`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18005b3a0`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18005b350`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18005b350`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b372`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b3c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b372`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b3c7`

## string_xrefs

- `0x18005b3df`: `S-1-0-INVALIDSID-1000`

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
0x18005b2f8  mov     [rsp-8+arg_0], rbx
0x18005b2fd  mov     [rsp-8+arg_10], rdi
0x18005b302  push    rbp
0x18005b303  mov     rbp, rsp
0x18005b306  sub     rsp, 30h
0x18005b30a  mov     rbx, rcx
0x18005b30d  mov     [rbp+var_10], 0
0x18005b311  mov     [rbp+var_E], 0
0x18005b315  lea     rcx, [rbp+var_10]; this
0x18005b319  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x18005b31e  mov     edi, eax
0x18005b320  mov     eax, 80000000h
0x18005b325  lea     edx, [rdi+rax]
0x18005b328  test    eax, edx
0x18005b32a  jnz     short loc_18005B344
0x18005b32c  cmp     edi, 80010117h
0x18005b332  jz      short loc_18005B344
0x18005b334  lea     rcx, [rbp+var_10]; this
0x18005b338  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18005b33d  mov     eax, edi
0x18005b33f  jmp     loc_18005B3F0
0x18005b344  mov     [rbp+hMem], 0
0x18005b34c  lea     rcx, [rbp+hMem]
0x18005b350  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x18005b357  nop     dword ptr [rax+rax+00h]
0x18005b35c  mov     edi, eax
0x18005b35e  test    eax, eax
0x18005b360  js      short loc_18005B334
0x18005b362  mov     rdx, [rbp+hMem]
0x18005b366  mov     rcx, rbx
0x18005b369  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18005b36e  mov     rcx, [rbp+hMem]; hMem
0x18005b372  call    cs:__imp_LocalFree
0x18005b379  nop     dword ptr [rax+rax+00h]
0x18005b37e  nop
0x18005b37f  lea     rcx, [rbp+var_10]; this
0x18005b383  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18005b388  mov     rcx, rbx
0x18005b38b  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const * const)
0x18005b390  test    al, al
0x18005b392  jz      short loc_18005B3D3
0x18005b394  mov     [rbp+hMem], 0
0x18005b39c  lea     rcx, [rbp+hMem]
0x18005b3a0  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18005b3a7  nop     dword ptr [rax+rax+00h]
0x18005b3ac  test    eax, eax
0x18005b3ae  jns     short loc_18005B3B7
0x18005b3b0  mov     eax, 80070525h
0x18005b3b5  jmp     short loc_18005B3F0
0x18005b3b7  mov     rdx, [rbp+hMem]
0x18005b3bb  mov     rcx, rbx
0x18005b3be  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18005b3c3  mov     rcx, [rbp+hMem]; hMem
0x18005b3c7  call    cs:__imp_LocalFree
0x18005b3ce  nop     dword ptr [rax+rax+00h]
0x18005b3d3  mov     rcx, rbx
0x18005b3d6  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const * const)
0x18005b3db  test    al, al
0x18005b3dd  jz      short loc_18005B3EE
0x18005b3df  lea     rdx, aS10Invalidsid1; "S-1-0-INVALIDSID-1000"
0x18005b3e6  mov     rcx, rbx
0x18005b3e9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18005b3ee  xor     eax, eax
0x18005b3f0  mov     rbx, [rsp+30h+arg_0]
0x18005b3f5  mov     rdi, [rsp+30h+arg_10]
0x18005b3fa  add     rsp, 30h
0x18005b3fe  pop     rbp
0x18005b3ff  retn
```
