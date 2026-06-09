# Windows::UserMgrHelpers::GetUserSidStringFromToken(void *)

- ea: `0x180051808`
- end: `0x1800518b8`
- name: `?GetUserSidStringFromToken@UserMgrHelpers@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18005133c`
- `0x180051924`

## callees

- `0x18001ba70`
- `0x180023a18`
- `0x180051678`
- `0x180051808`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051879`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005188a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051879`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005188a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005183b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005183b`

## string_xrefs

- `0x1800518a3`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::UserMgrHelpers::GetUserSidStringFromToken(__int64 a1, void *a2)
{
  const char *v3; // r9
  LPWSTR v4; // rdx
  __int64 v5; // r8
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPWSTR StringSid; // [rsp+50h] [rbp+18h] BYREF
  PSID Sid; // [rsp+58h] [rbp+20h] BYREF

  Windows::UserMgrHelpers::GetUserSidFromToken(&Sid, a2);
  StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      v3);
  v4 = StringSid;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  std::wstring::_Construct<1,unsigned short const *>(a1, v4);
  if ( StringSid )
    LocalFree(StringSid);
  if ( Sid )
    LocalFree(Sid);
  return a1;
}

```

## disassembly

```asm
0x180051808  mov     [rsp+arg_0], rbx
0x18005180d  mov     [rsp+arg_8], rsi
0x180051812  push    rdi
0x180051813  sub     rsp, 30h
0x180051817  mov     rbx, rcx
0x18005181a  xor     esi, esi
0x18005181c  lea     rcx, [rsp+38h+Sid]
0x180051821  call    ?GetUserSidFromToken@UserMgrHelpers@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@Z; Windows::UserMgrHelpers::GetUserSidFromToken(void *)
0x180051826  nop
0x180051827  mov     [rsp+38h+StringSid], rsi
0x18005182c  mov     rdi, [rsp+38h]
0x180051831  lea     rdx, [rsp+38h+StringSid]; StringSid
0x180051836  mov     rcx, [rsp+38h+Sid]; Sid
0x18005183b  call    cs:__imp_ConvertSidToStringSidW
0x180051841  test    eax, eax
0x180051843  jz      short loc_1800518A3
0x180051845  mov     rdx, [rsp+38h+StringSid]
0x18005184a  xorps   xmm0, xmm0
0x18005184d  movups  xmmword ptr [rbx], xmm0
0x180051850  mov     [rbx+10h], rsi
0x180051854  mov     [rbx+18h], rsi
0x180051858  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005185c  inc     r8
0x18005185f  cmp     [rdx+r8*2], si
0x180051864  jnz     short loc_18005185C
0x180051866  mov     rcx, rbx
0x180051869  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005186e  nop
0x18005186f  mov     rcx, [rsp+38h+StringSid]; hMem
0x180051874  test    rcx, rcx
0x180051877  jz      short loc_180051880
0x180051879  call    cs:__imp_LocalFree
0x18005187f  nop
0x180051880  mov     rcx, [rsp+38h+Sid]; hMem
0x180051885  test    rcx, rcx
0x180051888  jz      short loc_180051890
0x18005188a  call    cs:__imp_LocalFree
0x180051890  mov     rax, rbx
0x180051893  mov     rbx, [rsp+38h+arg_0]
0x180051898  mov     rsi, [rsp+38h+arg_8]
0x18005189d  add     rsp, 30h
0x1800518a1  pop     rdi
0x1800518a2  retn
0x1800518a3  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800518aa  mov     edx, 55h ; 'U'; void *
0x1800518af  mov     rcx, rdi; this
0x1800518b2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
