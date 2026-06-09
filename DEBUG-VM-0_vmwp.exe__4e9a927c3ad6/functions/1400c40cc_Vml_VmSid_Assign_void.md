# Vml::VmSid::Assign(void *)

- ea: `0x1400c40cc`
- end: `0x1400c4196`
- name: `?Assign@VmSid@Vml@@QEAAXPEAX@Z`
- size: `202`
- prototype: `void(Vml::VmSid *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400c3a80`

## callees

- `0x14005b628`
- `0x1400c40cc`
- `0x14013fed8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c4164`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c4164`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400c40f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400c40f9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400c4132`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400c4132`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400c40e6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400c40e6`

## string_xrefs

- `0x1400c4117`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400c4147`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmSid::Assign(Vml::VmSid *this, void *a2)
{
  HLOCAL v4; // rdi
  SIZE_T LengthSid; // r14
  HLOCAL v6; // rax
  const char *v7; // r9
  const char *v8; // r9
  void *v9; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HLOCAL v11; // [rsp+58h] [rbp+10h]

  v4 = 0;
  if ( a2 )
  {
    LengthSid = GetLengthSid(a2);
    v6 = LocalAlloc(0, LengthSid);
    v4 = v6;
    if ( !v6 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1540,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v7);
    if ( !CopySid(LengthSid, v6, a2) )
    {
      try
      {
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1545,
          (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
          v8);
      }
      catch ( ... )
      {
        LocalFree(v11);
        throw;
      }
    }
  }
  v9 = *(void **)this;
  *(_QWORD *)this = v4;
  if ( v9 )
    LocalFree(v9);
  *((_DWORD *)this + 2) = 7;
  std::wstring::erase((char *)this + 48, 0);
  std::wstring::erase((char *)this + 16, 0);
}

```

## disassembly

```asm
0x1400c40cc  push    rbx
0x1400c40ce  push    rsi
0x1400c40cf  push    rdi
0x1400c40d0  push    r14
0x1400c40d2  sub     rsp, 28h
0x1400c40d6  mov     rsi, rdx
0x1400c40d9  mov     rbx, rcx
0x1400c40dc  xor     edi, edi
0x1400c40de  test    rdx, rdx
0x1400c40e1  jz      short loc_1400C4159
0x1400c40e3  mov     rcx, rdx; pSid
0x1400c40e6  call    cs:__imp_GetLengthSid
0x1400c40ed  nop     dword ptr [rax+rax+00h]
0x1400c40f2  mov     r14d, eax
0x1400c40f5  mov     edx, eax; uBytes
0x1400c40f7  xor     ecx, ecx; uFlags
0x1400c40f9  call    cs:__imp_LocalAlloc
0x1400c4100  nop     dword ptr [rax+rax+00h]
0x1400c4105  mov     rdi, rax
0x1400c4108  mov     [rsp+48h+arg_8], rax
0x1400c410d  test    rax, rax
0x1400c4110  jnz     short loc_1400C4129
0x1400c4112  mov     rcx, [rsp+48h]; this
0x1400c4117  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400c411e  mov     edx, 1540h; void *
0x1400c4123  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c4129  mov     r8, rsi; pSourceSid
0x1400c412c  mov     rdx, rax; pDestinationSid
0x1400c412f  mov     ecx, r14d; nDestinationSidLength
0x1400c4132  call    cs:__imp_CopySid
0x1400c4139  nop     dword ptr [rax+rax+00h]
0x1400c413e  mov     rcx, [rsp+48h]; this
0x1400c4143  test    eax, eax
0x1400c4145  jnz     short loc_1400C4159
0x1400c4147  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400c414e  mov     edx, 1545h; void *
0x1400c4153  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c4159  mov     rcx, [rbx]; hMem
0x1400c415c  mov     [rbx], rdi
0x1400c415f  test    rcx, rcx
0x1400c4162  jz      short loc_1400C4170
0x1400c4164  call    cs:__imp_LocalFree
0x1400c416b  nop     dword ptr [rax+rax+00h]
0x1400c4170  mov     dword ptr [rbx+8], 7
0x1400c4177  lea     rcx, [rbx+30h]
0x1400c417b  xor     edx, edx
0x1400c417d  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K@Z; std::wstring::erase(unsigned __int64)
0x1400c4182  lea     rcx, [rbx+10h]
0x1400c4186  xor     edx, edx
0x1400c4188  add     rsp, 28h
0x1400c418c  pop     r14
0x1400c418e  pop     rdi
0x1400c418f  pop     rsi
0x1400c4190  pop     rbx
0x1400c4191  jmp     ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K@Z; std::wstring::erase(unsigned __int64)
```
