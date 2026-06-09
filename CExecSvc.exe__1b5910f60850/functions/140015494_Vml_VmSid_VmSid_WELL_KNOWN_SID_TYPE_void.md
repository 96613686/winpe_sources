# Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)

- ea: `0x140015494`
- end: `0x1400155de`
- name: `??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z`
- size: `330`
- prototype: `Vml::VmSid *__fastcall(Vml::VmSid *this, enum WELL_KNOWN_SID_TYPE, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400188cc`

## callees

- `0x140002310`
- `0x14000e828`
- `0x140015494`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140015518`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140015518`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14001554e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14001554e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140015534`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140015534`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001555f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001555f`

## string_xrefs

- `0x1400155ba`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400155cc`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
Vml::VmSid *__fastcall Vml::VmSid::VmSid(Vml::VmSid *this, enum WELL_KNOWN_SID_TYPE a2, void *a3)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rdi
  const char *v6; // r9
  HLOCAL v7; // rax
  const char *v8; // r9
  HLOCAL v9; // rbp
  void *v10; // rcx
  DWORD cbSid[4]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE pSid[80]; // [rsp+40h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 7;
  v4 = (_QWORD *)((char *)this + 16);
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 7;
  *((_WORD *)this + 8) = 0;
  v5 = (_QWORD *)((char *)this + 48);
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 7;
  *((_WORD *)this + 24) = 0;
  cbSid[0] = 68;
  if ( !CreateWellKnownSid(a2, a3, pSid, cbSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1469,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v6);
  v7 = LocalAlloc(0, cbSid[0]);
  v9 = v7;
  if ( !v7 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x146F,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v8);
  CopySid(cbSid[0], v7, pSid);
  v10 = *(void **)this;
  *(_QWORD *)this = v9;
  if ( v10 )
    LocalFree(v10);
  *((_DWORD *)this + 2) = 7;
  v5[2] = 0;
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  *(_WORD *)v5 = 0;
  v4[2] = 0;
  if ( v4[3] > 7u )
    v4 = (_QWORD *)*v4;
  *(_WORD *)v4 = 0;
  return this;
}

```

## disassembly

```asm
0x140015494  push    rbx
0x140015496  push    rbp
0x140015497  push    rsi
0x140015498  push    rdi
0x140015499  push    r15
0x14001549b  sub     rsp, 0A0h
0x1400154a2  mov     rax, cs:__security_cookie
0x1400154a9  xor     rax, rsp
0x1400154ac  mov     [rsp+0C8h+var_38], rax
0x1400154b4  mov     r11, r8
0x1400154b7  mov     r10d, edx
0x1400154ba  mov     rsi, rcx
0x1400154bd  mov     [rsp+0C8h+var_A8], rcx
0x1400154c2  mov     qword ptr [rcx], 0
0x1400154c9  mov     r15d, 7
0x1400154cf  mov     [rcx+8], r15d
0x1400154d3  lea     rbx, [rcx+10h]
0x1400154d7  xorps   xmm0, xmm0
0x1400154da  movups  xmmword ptr [rbx], xmm0
0x1400154dd  mov     qword ptr [rbx+10h], 0
0x1400154e5  mov     [rbx+18h], r15
0x1400154e9  xor     eax, eax
0x1400154eb  mov     [rbx], ax
0x1400154ee  lea     rdi, [rcx+30h]
0x1400154f2  movups  xmmword ptr [rdi], xmm0
0x1400154f5  mov     [rdi+10h], rax
0x1400154f9  mov     [rdi+18h], r15
0x1400154fd  mov     [rdi], ax
0x140015500  mov     [rsp+0C8h+cbSid], 44h ; 'D'
0x140015508  lea     r9, [rsp+0C8h+cbSid]; cbSid
0x14001550d  lea     r8, [rsp+0C8h+pSid]; pSid
0x140015512  mov     rdx, r11; DomainSid
0x140015515  mov     ecx, r10d; WellKnownSidType
0x140015518  call    cs:__imp_CreateWellKnownSid
0x14001551e  mov     rcx, [rsp+0C8h]; this
0x140015526  test    eax, eax
0x140015528  jz      loc_1400155CC
0x14001552e  mov     edx, [rsp+0C8h+cbSid]; uBytes
0x140015532  xor     ecx, ecx; uFlags
0x140015534  call    cs:__imp_LocalAlloc
0x14001553a  mov     rbp, rax
0x14001553d  test    rax, rax
0x140015540  jz      short loc_1400155B2
0x140015542  lea     r8, [rsp+0C8h+pSid]; pSourceSid
0x140015547  mov     rdx, rax; pDestinationSid
0x14001554a  mov     ecx, [rsp+0C8h+cbSid]; nDestinationSidLength
0x14001554e  call    cs:__imp_CopySid
0x140015554  mov     rcx, [rsi]; hMem
0x140015557  mov     [rsi], rbp
0x14001555a  test    rcx, rcx
0x14001555d  jz      short loc_140015565
0x14001555f  call    cs:__imp_LocalFree
0x140015565  mov     [rsi+8], r15d
0x140015569  mov     qword ptr [rdi+10h], 0
0x140015571  cmp     [rdi+18h], r15
0x140015575  jbe     short loc_14001557A
0x140015577  mov     rdi, [rdi]
0x14001557a  xor     eax, eax
0x14001557c  mov     [rdi], ax
0x14001557f  mov     [rbx+10h], rax
0x140015583  cmp     [rbx+18h], r15
0x140015587  jbe     short loc_14001558C
0x140015589  mov     rbx, [rbx]
0x14001558c  xor     ecx, ecx
0x14001558e  mov     [rbx], cx
0x140015591  mov     rax, rsi
0x140015594  mov     rcx, [rsp+0C8h+var_38]
0x14001559c  xor     rcx, rsp; StackCookie
0x14001559f  call    __security_check_cookie
0x1400155a4  add     rsp, 0A0h
0x1400155ab  pop     r15
0x1400155ad  pop     rdi
0x1400155ae  pop     rsi
0x1400155af  pop     rbp
0x1400155b0  pop     rbx
0x1400155b1  retn
0x1400155b2  mov     rcx, [rsp+0C8h]; this
0x1400155ba  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400155c1  mov     edx, 146Fh; void *
0x1400155c6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400155cc  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400155d3  mov     edx, 1469h; void *
0x1400155d8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
