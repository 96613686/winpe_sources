# Vml::VmSid::CreateV(_SID_IDENTIFIER_AUTHORITY const &,uchar,char *)

- ea: `0x1400165e4`
- end: `0x1400166e4`
- name: `?CreateV@VmSid@Vml@@AEAAXAEBU_SID_IDENTIFIER_AUTHORITY@@EPEAD@Z`
- size: `256`
- prototype: `void __fastcall(Vml::VmSid *this, struct _SID_IDENTIFIER_AUTHORITY *, UCHAR, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140015410`

## callees

- `0x14000e828`
- `0x1400165e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140016655`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140016655`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x140016601`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x140016601`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x14001662b`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x14001662b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001660b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001660b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001666f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001666f`

## string_xrefs

- `0x1400166bf`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400166d1`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmSid::CreateV(Vml::VmSid *this, struct _SID_IDENTIFIER_AUTHORITY *a2, UCHAR a3, char *a4)
{
  DWORD v5; // ebx
  DWORD SidLengthRequired; // eax
  HLOCAL v9; // rax
  const char *v10; // r9
  void *v11; // r14
  const char *v12; // r9
  DWORD v13; // r15d
  DWORD v14; // esi
  DWORD v15; // ebx
  void *v16; // rcx
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  HLOCAL v19; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = a3;
  SidLengthRequired = GetSidLengthRequired(a3);
  v9 = LocalAlloc(0, SidLengthRequired);
  v11 = v9;
  v19 = v9;
  if ( !v9 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x13CB,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v10);
  if ( !InitializeSid(v9, a2, v5) )
  {
    try
    {
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x13D3,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v12);
    }
    catch ( ... )
    {
      LocalFree(v19);
      throw;
    }
  }
  v13 = v5;
  v14 = 0;
  if ( (_BYTE)v5 )
  {
    do
    {
      v15 = *(_DWORD *)a4;
      a4 += 8;
      *GetSidSubAuthority(v11, v14++) = v15;
    }
    while ( v14 < v13 );
  }
  v16 = *(void **)this;
  *(_QWORD *)this = v11;
  if ( v16 )
    LocalFree(v16);
  *((_DWORD *)this + 2) = 7;
  v17 = (_QWORD *)((char *)this + 48);
  *((_QWORD *)this + 8) = 0;
  if ( *((_QWORD *)this + 9) > 7u )
    v17 = (_QWORD *)*v17;
  *(_WORD *)v17 = 0;
  v18 = (_QWORD *)((char *)this + 16);
  *((_QWORD *)this + 4) = 0;
  if ( *((_QWORD *)this + 5) > 7u )
    v18 = (_QWORD *)*v18;
  *(_WORD *)v18 = 0;
}

```

## disassembly

```asm
0x1400165e4  push    rbx
0x1400165e6  push    rsi
0x1400165e7  push    rdi
0x1400165e8  push    r12
0x1400165ea  push    r14
0x1400165ec  push    r15
0x1400165ee  sub     rsp, 38h
0x1400165f2  mov     r12, r9
0x1400165f5  movzx   ebx, r8b
0x1400165f9  mov     rsi, rdx
0x1400165fc  mov     rdi, rcx
0x1400165ff  mov     cl, bl; nSubAuthorityCount
0x140016601  call    cs:__imp_GetSidLengthRequired
0x140016607  mov     edx, eax; uBytes
0x140016609  xor     ecx, ecx; uFlags
0x14001660b  call    cs:__imp_LocalAlloc
0x140016611  mov     r14, rax
0x140016614  mov     [rsp+68h+var_48], rax
0x140016619  test    rax, rax
0x14001661c  jz      loc_1400166BA
0x140016622  mov     r8b, bl; nSubAuthorityCount
0x140016625  mov     rdx, rsi; pIdentifierAuthority
0x140016628  mov     rcx, r14; Sid
0x14001662b  call    cs:__imp_InitializeSid
0x140016631  mov     rcx, [rsp+68h]; this
0x140016636  test    eax, eax
0x140016638  jz      loc_1400166D1
0x14001663e  mov     r15d, ebx
0x140016641  xor     esi, esi
0x140016643  test    bl, bl
0x140016645  jz      short loc_140016664
0x140016647  mov     ebx, [r12]
0x14001664b  lea     r12, [r12+8]
0x140016650  mov     edx, esi; nSubAuthority
0x140016652  mov     rcx, r14; pSid
0x140016655  call    cs:__imp_GetSidSubAuthority
0x14001665b  mov     [rax], ebx
0x14001665d  inc     esi
0x14001665f  cmp     esi, r15d
0x140016662  jb      short loc_140016647
0x140016664  mov     rcx, [rdi]; hMem
0x140016667  mov     [rdi], r14
0x14001666a  test    rcx, rcx
0x14001666d  jz      short loc_140016675
0x14001666f  call    cs:__imp_LocalFree
0x140016675  mov     dword ptr [rdi+8], 7
0x14001667c  lea     rcx, [rdi+30h]
0x140016680  mov     qword ptr [rcx+10h], 0
0x140016688  cmp     qword ptr [rcx+18h], 7
0x14001668d  jbe     short loc_140016692
0x14001668f  mov     rcx, [rcx]
0x140016692  xor     eax, eax
0x140016694  mov     [rcx], ax
0x140016697  lea     rcx, [rdi+10h]
0x14001669b  mov     [rcx+10h], rax
0x14001669f  cmp     qword ptr [rcx+18h], 7
0x1400166a4  jbe     short loc_1400166A9
0x1400166a6  mov     rcx, [rcx]
0x1400166a9  mov     [rcx], ax
0x1400166ac  add     rsp, 38h
0x1400166b0  pop     r15
0x1400166b2  pop     r14
0x1400166b4  pop     r12
0x1400166b6  pop     rdi
0x1400166b7  pop     rsi
0x1400166b8  pop     rbx
0x1400166b9  retn
0x1400166ba  mov     rcx, [rsp+68h]; this
0x1400166bf  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400166c6  mov     edx, 13CBh; void *
0x1400166cb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400166d1  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400166d8  mov     edx, 13D3h; void *
0x1400166dd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
