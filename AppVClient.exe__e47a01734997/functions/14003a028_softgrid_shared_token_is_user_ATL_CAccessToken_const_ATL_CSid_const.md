# softgrid::shared::token_is_user(ATL::CAccessToken const &,ATL::CSid const &)

- ea: `0x14003a028`
- end: `0x14003a0df`
- name: `?token_is_user@shared@softgrid@@YA_NAEBVCAccessToken@ATL@@AEBVCSid@4@@Z`
- size: `183`
- prototype: `bool __fastcall(softgrid::shared *__hidden this, const struct ATL::CAccessToken *, const struct ATL::CSid *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140039f30`
- `0x140039fac`

## callees

- `0x140004280`
- `0x1400086fc`
- `0x140009230`
- `0x14000d3bc`
- `0x14003a028`

## import_xrefs

- `ADVAPI32!IsValidSid` at `0x14003a07b`
- `ADVAPI32!IsValidSid` at `0x14003a091`
- `ADVAPI32!IsValidSid` at `0x14003a07b`
- `ADVAPI32!IsValidSid` at `0x14003a091`
- `ADVAPI32!EqualSid` at `0x14003a0a3`
- `ADVAPI32!EqualSid` at `0x14003a0a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall softgrid::shared::token_is_user(
        softgrid::shared *this,
        const struct ATL::CAccessToken *a2,
        const struct ATL::CSid *a3)
{
  bool v5; // bl
  _BYTE v7[8]; // [rsp+20h] [rbp-98h] BYREF
  _BYTE pSid[120]; // [rsp+28h] [rbp-90h] BYREF

  ATL::CSid::CSid((ATL::CSid *)v7);
  v5 = ATL::CAccessToken::GetUser(this, (struct ATL::CSid *)v7)
    && a2 != (const struct ATL::CAccessToken *)-8LL
    && *((_BYTE *)a2 + 76)
    && IsValidSid((char *)a2 + 8)
    && pSid[68]
    && IsValidSid(pSid)
    && EqualSid((char *)a2 + 8, pSid);
  ATL::CSid::~CSid((ATL::CSid *)v7);
  return v5;
}

```

## disassembly

```asm
0x14003a028  mov     [rsp+arg_10], rbx
0x14003a02d  push    rdi
0x14003a02e  sub     rsp, 0B0h
0x14003a035  mov     rax, cs:__security_cookie
0x14003a03c  xor     rax, rsp
0x14003a03f  mov     [rsp+0B8h+var_18], rax
0x14003a047  mov     rdi, rdx
0x14003a04a  mov     rbx, rcx
0x14003a04d  lea     rcx, [rsp+0B8h+var_98]; this
0x14003a052  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x14003a057  nop
0x14003a058  lea     rdx, [rsp+0B8h+var_98]; struct ATL::CSid *
0x14003a05d  mov     rcx, rbx; this
0x14003a060  call    ?GetUser@CAccessToken@ATL@@QEBA_NPEAVCSid@2@@Z; ATL::CAccessToken::GetUser(ATL::CSid *)
0x14003a065  test    al, al
0x14003a067  jz      short loc_14003A0B0
0x14003a069  lea     rbx, [rdi+8]
0x14003a06d  test    rbx, rbx
0x14003a070  jz      short loc_14003A0B0
0x14003a072  cmp     byte ptr [rdi+4Ch], 0
0x14003a076  jz      short loc_14003A0B0
0x14003a078  mov     rcx, rbx; pSid
0x14003a07b  call    cs:__imp_IsValidSid
0x14003a081  test    eax, eax
0x14003a083  jz      short loc_14003A0B0
0x14003a085  cmp     [rsp+0B8h+var_4C], 0
0x14003a08a  jz      short loc_14003A0B0
0x14003a08c  lea     rcx, [rsp+0B8h+pSid]; pSid
0x14003a091  call    cs:__imp_IsValidSid
0x14003a097  test    eax, eax
0x14003a099  jz      short loc_14003A0B0
0x14003a09b  lea     rdx, [rsp+0B8h+pSid]; pSid2
0x14003a0a0  mov     rcx, rbx; pSid1
0x14003a0a3  call    cs:__imp_EqualSid
0x14003a0a9  test    eax, eax
0x14003a0ab  setnz   bl
0x14003a0ae  jmp     short loc_14003A0B2
0x14003a0b0  xor     bl, bl
0x14003a0b2  lea     rcx, [rsp+0B8h+var_98]; this
0x14003a0b7  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14003a0bc  mov     al, bl
0x14003a0be  mov     rcx, [rsp+0B8h+var_18]
0x14003a0c6  xor     rcx, rsp; StackCookie
0x14003a0c9  call    __security_check_cookie
0x14003a0ce  mov     rbx, [rsp+0B8h+arg_10]
0x14003a0d6  add     rsp, 0B0h
0x14003a0dd  pop     rdi
0x14003a0de  retn
```
