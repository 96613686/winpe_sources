# SecUtil::CACL::RemoveAceByPrefix(void *)

- ea: `0x140047318`
- end: `0x1400473a2`
- name: `?RemoveAceByPrefix@CACL@SecUtil@@QEAAXPEAX@Z`
- size: `138`
- prototype: `void(SecUtil::CACL *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140022778`

## callees

- `0x14003178c`
- `0x140047074`
- `0x140047318`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x140047371`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x140047371`
- `api-ms-win-security-base-l1-1-0!EqualPrefixSid` at `0x140047362`
- `api-ms-win-security-base-l1-1-0!EqualPrefixSid` at `0x140047362`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14004734c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14004734c`

## string_xrefs

- `0x140047380`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`

## pseudocode

```c
void __fastcall SecUtil::CACL::RemoveAceByPrefix(SecUtil::CACL *this, void *a2)
{
  unsigned int AceCount; // eax
  signed int i; // ebx
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPVOID pAce; // [rsp+40h] [rbp+18h] BYREF

  AceCount = SecUtil::CACL::GetAceCount(this);
  pAce = 0;
  for ( i = AceCount - 1; i >= 0; --i )
  {
    if ( !GetAce(*(PACL *)this, i, &pAce) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x611,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
        v6);
    if ( EqualPrefixSid((char *)pAce + 8, a2) )
      DeleteAce(*(PACL *)this, i);
  }
}

```

## disassembly

```asm
0x140047318  mov     [rsp+arg_0], rbx
0x14004731d  mov     [rsp+arg_8], rsi
0x140047322  push    rdi
0x140047323  sub     rsp, 20h
0x140047327  mov     rsi, rdx
0x14004732a  mov     rdi, rcx
0x14004732d  call    ?GetAceCount@CACL@SecUtil@@QEBAKXZ; SecUtil::CACL::GetAceCount(void)
0x140047332  mov     [rsp+28h+pAce], 0
0x14004733b  lea     ebx, [rax-1]
0x14004733e  test    ebx, ebx
0x140047340  js      short loc_140047392
0x140047342  mov     rcx, [rdi]; pAcl
0x140047345  lea     r8, [rsp+28h+pAce]; pAce
0x14004734a  mov     edx, ebx; dwAceIndex
0x14004734c  call    cs:__imp_GetAce
0x140047352  test    eax, eax
0x140047354  jz      short loc_14004737B
0x140047356  mov     rcx, [rsp+28h+pAce]
0x14004735b  mov     rdx, rsi; pSid2
0x14004735e  add     rcx, 8; pSid1
0x140047362  call    cs:__imp_EqualPrefixSid
0x140047368  test    eax, eax
0x14004736a  jz      short loc_140047377
0x14004736c  mov     rcx, [rdi]; pAcl
0x14004736f  mov     edx, ebx; dwAceIndex
0x140047371  call    cs:__imp_DeleteAce
0x140047377  dec     ebx
0x140047379  jmp     short loc_14004733E
0x14004737b  mov     rcx, [rsp+28h]; this
0x140047380  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x140047387  mov     edx, 611h; void *
0x14004738c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140047392  mov     rbx, [rsp+28h+arg_0]
0x140047397  mov     rsi, [rsp+28h+arg_8]
0x14004739c  add     rsp, 20h
0x1400473a0  pop     rdi
0x1400473a1  retn
```
