# GetUserSidString(void *)

- ea: `0x180060070`
- end: `0x1800601e1`
- name: `?GetUserSidString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `369`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180015410`
- `0x1800179d8`
- `0x1800180d8`
- `0x18002ce04`
- `0x18002e4a0`
- `0x1800308a0`
- `0x180033418`
- `0x18003ddac`
- `0x18003fff4`

## callees

- `0x180003ea0`
- `0x1800044b8`
- `0x180005df8`
- `0x180011318`
- `0x180012a98`
- `0x1800137bc`
- `0x180060070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800600bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800600bd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800600aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180060105`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800600aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180060105`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180060125`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180060125`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060168`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060168`

## string_xrefs

- `0x18006018d`: `onecore\base\languageoverlay\common\platformutils.cpp`
- `0x1800601a5`: `onecore\base\languageoverlay\common\platformutils.cpp`
- `0x1800601ba`: `onecore\base\languageoverlay\common\platformutils.cpp`
- `0x1800601cf`: `onecore\base\languageoverlay\common\platformutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetUserSidString(__int64 a1, void *a2)
{
  const char *v4; // r9
  unsigned int v5; // ebx
  PSID *v6; // rsi
  const char *v7; // r9
  const char *v8; // r9
  LPWSTR v9; // rdx
  unsigned __int64 v10; // r8
  int ReturnLength; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  size_t Size; // [rsp+70h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp+20h] BYREF

  LODWORD(Size) = 0;
  if ( GetTokenInformation(a2, TokenUser, 0, 0, (PDWORD)&Size) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\platformutils.cpp",
      (const char *)0x8000FFFFLL,
      ReturnLength);
  if ( GetLastError() != 122 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\platformutils.cpp",
      v4);
  v5 = Size;
  v6 = (PSID *)operator new[]((unsigned int)Size);
  memset_0(v6, 0, v5);
  if ( !GetTokenInformation(a2, TokenUser, v6, Size, (PDWORD)&Size) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\platformutils.cpp",
      v7);
  StringSid = 0;
  if ( !ConvertSidToStringSidW(*v6, &StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\platformutils.cpp",
      v8);
  v9 = StringSid;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v10 = -1;
  do
    ++v10;
  while ( v9[v10] );
  std::wstring::_Construct<1,unsigned short const *>((char **)a1, v9, v10);
  if ( StringSid )
    LocalFree(StringSid);
  operator delete(v6);
  return a1;
}

```

## disassembly

```asm
0x180060070  mov     r11, rsp
0x180060073  mov     [r11+8], rbx
0x180060077  mov     [r11+10h], rbp
0x18006007b  push    rsi
0x18006007c  push    rdi
0x18006007d  push    r14
0x18006007f  sub     rsp, 40h
0x180060083  mov     rbp, rdx
0x180060086  mov     rdi, rcx
0x180060089  xor     r14d, r14d
0x18006008c  mov     [r11+18h], r14d
0x180060090  mov     rbx, [rsp+58h]
0x180060095  lea     rax, [r11+18h]
0x180060099  mov     [r11-38h], rax
0x18006009d  xor     r9d, r9d; TokenInformationLength
0x1800600a0  xor     r8d, r8d; TokenInformation
0x1800600a3  lea     edx, [r14+1]; TokenInformationClass
0x1800600a7  mov     rcx, rbp; TokenHandle
0x1800600aa  call    cs:__imp_GetTokenInformation
0x1800600b0  test    eax, eax
0x1800600b2  jnz     loc_18006019F
0x1800600b8  mov     rbx, [rsp+58h]
0x1800600bd  call    cs:__imp_GetLastError
0x1800600c3  cmp     eax, 7Ah ; 'z'
0x1800600c6  jnz     loc_1800601BA
0x1800600cc  mov     ebx, dword ptr [rsp+58h+Size]
0x1800600d0  mov     ecx, ebx; unsigned __int64
0x1800600d2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800600d7  mov     rsi, rax
0x1800600da  mov     r8d, ebx; Size
0x1800600dd  xor     edx, edx; Val
0x1800600df  mov     rcx, rax; void *
0x1800600e2  call    memset_0
0x1800600e7  mov     [rsp+58h+var_20], rsi
0x1800600ec  lea     rax, [rsp+58h+Size]
0x1800600f1  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x1800600f6  mov     r9d, dword ptr [rsp+58h+Size]; TokenInformationLength
0x1800600fb  mov     r8, rsi; TokenInformation
0x1800600fe  lea     edx, [r14+1]; TokenInformationClass
0x180060102  mov     rcx, rbp; TokenHandle
0x180060105  call    cs:__imp_GetTokenInformation
0x18006010b  mov     rcx, [rsp+58h]; this
0x180060110  test    eax, eax
0x180060112  jz      loc_1800601CF
0x180060118  mov     [rsp+58h+StringSid], r14
0x18006011d  lea     rdx, [rsp+58h+StringSid]; StringSid
0x180060122  mov     rcx, [rsi]; Sid
0x180060125  call    cs:__imp_ConvertSidToStringSidW
0x18006012b  mov     rcx, [rsp+58h]; this
0x180060130  test    eax, eax
0x180060132  jz      short loc_18006018D
0x180060134  mov     rdx, [rsp+58h+StringSid]
0x180060139  xorps   xmm0, xmm0
0x18006013c  movups  xmmword ptr [rdi], xmm0
0x18006013f  mov     [rdi+10h], r14
0x180060143  mov     [rdi+18h], r14
0x180060147  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006014b  inc     r8
0x18006014e  cmp     [rdx+r8*2], r14w
0x180060153  jnz     short loc_18006014B
0x180060155  mov     rcx, rdi
0x180060158  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006015d  nop
0x18006015e  mov     rcx, [rsp+58h+StringSid]; hMem
0x180060163  test    rcx, rcx
0x180060166  jz      short loc_18006016F
0x180060168  call    cs:__imp_LocalFree
0x18006016e  nop
0x18006016f  mov     rcx, rsi; void *
0x180060172  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180060177  mov     rax, rdi
0x18006017a  mov     rbx, [rsp+58h+arg_0]
0x18006017f  mov     rbp, [rsp+58h+arg_8]
0x180060184  add     rsp, 40h
0x180060188  pop     r14
0x18006018a  pop     rdi
0x18006018b  pop     rsi
0x18006018c  retn
0x18006018d  lea     r8, aOnecoreBaseLan_2; "onecore\\base\\languageoverlay\\common"...
0x180060194  mov     edx, 0A6h; void *
0x180060199  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18006019f  mov     r9d, 8000FFFFh; char *
0x1800601a5  lea     r8, aOnecoreBaseLan_2; "onecore\\base\\languageoverlay\\common"...
0x1800601ac  mov     edx, 97h; void *
0x1800601b1  mov     rcx, rbx; this
0x1800601b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800601ba  lea     r8, aOnecoreBaseLan_2; "onecore\\base\\languageoverlay\\common"...
0x1800601c1  mov     edx, 98h; void *
0x1800601c6  mov     rcx, rbx; this
0x1800601c9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800601cf  lea     r8, aOnecoreBaseLan_2; "onecore\\base\\languageoverlay\\common"...
0x1800601d6  mov     edx, 0A1h; void *
0x1800601db  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
