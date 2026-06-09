# Windows::Internal::AssignedAccess::UserInfoHelper::FillInWellKnownSid(WELL_KNOWN_SID_TYPE,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800501d8`
- end: `0x1800502ca`
- name: `?FillInWellKnownSid@UserInfoHelper@AssignedAccess@Internal@Windows@@CAJW4WELL_KNOWN_SID_TYPE@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180050980`

## callees

- `0x1800070f4`
- `0x18000b694`
- `0x18000b6b4`
- `0x180029888`
- `0x1800501d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005020b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005020b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180050201`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180050296`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180050201`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180050296`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::UserInfoHelper::FillInWellKnownSid(__int64 a1, __int64 a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  __int64 v6; // rsi
  unsigned __int64 v7; // rcx
  size_t v8; // rbx
  const char *v9; // r9
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF

  cbSid = 0;
  if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, 0, &cbSid)
    || (LastError = GetLastError(), v4 = LastError, LastError == 122) )
  {
    v6 = *(_QWORD *)(a2 + 8);
    v7 = v6 - *(_QWORD *)a2;
    if ( v7 < cbSid )
    {
      if ( (unsigned __int64)cbSid <= *(_QWORD *)(a2 + 16) - *(_QWORD *)a2 )
      {
        v8 = cbSid - v7;
        memset_0(*(void **)(a2 + 8), 0, v8);
        *(_QWORD *)(a2 + 8) = v8 + v6;
      }
      else
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a2, cbSid);
      }
    }
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, *(PSID *)a2, &cbSid) )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x13A,
               (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
               v9);
  }
  else
  {
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( (v4 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x132,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
        (const char *)v4,
        v10);
    return v4;
  }
}

```

## disassembly

```asm
0x1800501d8  mov     rax, rsp
0x1800501db  mov     [rax+10h], rbx
0x1800501df  mov     [rax+18h], rsi
0x1800501e3  mov     [rax+8], ecx
0x1800501e6  push    rdi; int
0x1800501e7  sub     rsp, 20h
0x1800501eb  mov     rdi, rdx
0x1800501ee  mov     dword ptr [rax+8], 0
0x1800501f5  xor     edx, edx; DomainSid
0x1800501f7  lea     r9, [rax+8]; cbSid
0x1800501fb  xor     r8d, r8d; pSid
0x1800501fe  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180050201  call    cs:__imp_CreateWellKnownSid
0x180050207  test    eax, eax
0x180050209  jnz     short loc_180050246
0x18005020b  call    cs:__imp_GetLastError
0x180050211  mov     ebx, eax
0x180050213  cmp     eax, 7Ah ; 'z'
0x180050216  jz      short loc_180050246
0x180050218  test    eax, eax
0x18005021a  jle     short loc_180050225
0x18005021c  movzx   ebx, ax
0x18005021f  or      ebx, 80070000h
0x180050225  test    ebx, ebx
0x180050227  jns     short loc_180050242
0x180050229  mov     rcx, [rsp+28h]; this
0x18005022e  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180050235  mov     r9d, ebx; char *
0x180050238  mov     edx, 132h; void *
0x18005023d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050242  mov     eax, ebx
0x180050244  jmp     short loc_1800502BA
0x180050246  mov     rsi, [rdi+8]
0x18005024a  mov     ebx, [rsp+28h+cbSid]
0x18005024e  mov     rcx, rsi
0x180050251  sub     rcx, [rdi]
0x180050254  cmp     rcx, rbx
0x180050257  jnb     short loc_180050289
0x180050259  mov     rax, [rdi+10h]
0x18005025d  sub     rax, [rdi]
0x180050260  cmp     rbx, rax
0x180050263  jbe     short loc_180050271
0x180050265  mov     edx, ebx
0x180050267  mov     rcx, rdi
0x18005026a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005026f  jmp     short loc_180050289
0x180050271  sub     rbx, rcx
0x180050274  xor     edx, edx; Val
0x180050276  mov     r8, rbx; Size
0x180050279  mov     rcx, rsi; void *
0x18005027c  call    memset_0
0x180050281  lea     rax, [rbx+rsi]
0x180050285  mov     [rdi+8], rax
0x180050289  mov     r8, [rdi]; pSid
0x18005028c  lea     r9, [rsp+28h+cbSid]; cbSid
0x180050291  xor     edx, edx; DomainSid
0x180050293  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180050296  call    cs:__imp_CreateWellKnownSid
0x18005029c  test    eax, eax
0x18005029e  jnz     short loc_1800502B8
0x1800502a0  mov     rcx, [rsp+28h]; this
0x1800502a5  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800502ac  mov     edx, 13Ah; void *
0x1800502b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800502b6  jmp     short loc_1800502BA
0x1800502b8  xor     eax, eax
0x1800502ba  mov     rbx, [rsp+28h+arg_8]
0x1800502bf  mov     rsi, [rsp+28h+arg_10]
0x1800502c4  add     rsp, 20h
0x1800502c8  pop     rdi
0x1800502c9  retn
```
