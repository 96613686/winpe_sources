# ATL::CSid::Copy(_SID const &)

- ea: `0x18001e7c8`
- end: `0x18001e831`
- name: `?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z`
- size: `105`
- prototype: `void(ATL::CSid *__hidden this, const struct _SID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800bf724`

## callees

- `0x18001e7c8`
- `0x18001e838`
- `0x18009e2e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001e80b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001e80b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001e7db`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001e7db`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001e7f3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001e7f3`

## pseudocode

```c
void __fastcall ATL::CSid::Copy(ATL::CSid *this, struct _SID *a2)
{
  DWORD LengthSid; // eax
  int LastErrorAsHResult; // eax

  if ( !IsValidSid(a2) || (LengthSid = GetLengthSid(a2), LengthSid > 0x44) )
    ATL::AtlThrowImpl(-2147024809);
  *((_BYTE *)this + 76) = 1;
  if ( !CopySid(LengthSid, (char *)this + 8, a2) )
  {
    LastErrorAsHResult = LocationHelper::GetLastErrorAsHResult();
    *((_BYTE *)this + 76) = 0;
    ATL::AtlThrowImpl(LastErrorAsHResult);
  }
}

```

## disassembly

```asm
0x18001e7c8  mov     [rsp+arg_0], rbx
0x18001e7cd  push    rdi
0x18001e7ce  sub     rsp, 20h
0x18001e7d2  mov     rdi, rcx
0x18001e7d5  mov     rbx, rdx
0x18001e7d8  mov     rcx, rdx; pSid
0x18001e7db  call    cs:__imp_IsValidSid
0x18001e7e1  test    eax, eax
0x18001e7e3  jnz     short loc_18001E7F0
0x18001e7e5  mov     ecx, 80070057h; int
0x18001e7ea  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e7f0  mov     rcx, rbx; pSid
0x18001e7f3  call    cs:__imp_GetLengthSid
0x18001e7f9  cmp     eax, 44h ; 'D'
0x18001e7fc  ja      short loc_18001E7E5
0x18001e7fe  lea     rdx, [rdi+8]; pDestinationSid
0x18001e802  mov     byte ptr [rdi+4Ch], 1
0x18001e806  mov     r8, rbx; pSourceSid
0x18001e809  mov     ecx, eax; nDestinationSidLength
0x18001e80b  call    cs:__imp_CopySid
0x18001e811  test    eax, eax
0x18001e813  jz      short loc_18001E820
0x18001e815  mov     rbx, [rsp+28h+arg_0]
0x18001e81a  add     rsp, 20h
0x18001e81e  pop     rdi
0x18001e81f  retn
0x18001e820  call    ?GetLastErrorAsHResult@LocationHelper@@SAJXZ; LocationHelper::GetLastErrorAsHResult(void)
0x18001e825  mov     ecx, eax; int
0x18001e827  mov     byte ptr [rdi+4Ch], 0
0x18001e82b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
