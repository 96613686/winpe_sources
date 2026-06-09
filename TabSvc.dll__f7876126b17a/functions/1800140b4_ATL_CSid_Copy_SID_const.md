# ATL::CSid::Copy(_SID const &)

- ea: `0x1800140b4`
- end: `0x18001411d`
- name: `?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z`
- size: `105`
- prototype: `void __fastcall(ATL::CSid *this, struct _SID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000dff0`
- `0x18002d00c`

## callees

- `0x1800140b4`
- `0x180019e00`
- `0x18001a5e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800140ec`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800140ec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800140d4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800140d4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800140c7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800140c7`

## pseudocode

```c
void __fastcall ATL::CSid::Copy(ATL::CSid *this, struct _SID *a2)
{
  DWORD LengthSid; // eax
  int Error; // eax

  if ( !IsValidSid(a2) || (LengthSid = GetLengthSid(a2), LengthSid > 0x44) )
    ATL::AtlThrowImpl(-2147024809);
  *((_BYTE *)this + 76) = 1;
  if ( !CopySid(LengthSid, (char *)this + 8, a2) )
  {
    Error = ATL::AtlHresultFromLastError();
    *((_BYTE *)this + 76) = 0;
    ATL::AtlThrowImpl(Error);
  }
}

```

## disassembly

```asm
0x1800140b4  mov     [rsp+arg_0], rbx
0x1800140b9  push    rdi
0x1800140ba  sub     rsp, 20h
0x1800140be  mov     rdi, rcx
0x1800140c1  mov     rbx, rdx
0x1800140c4  mov     rcx, rdx; pSid
0x1800140c7  call    cs:__imp_IsValidSid
0x1800140cd  test    eax, eax
0x1800140cf  jz      short loc_180014107
0x1800140d1  mov     rcx, rbx; pSid
0x1800140d4  call    cs:__imp_GetLengthSid
0x1800140da  cmp     eax, 44h ; 'D'
0x1800140dd  ja      short loc_180014107
0x1800140df  lea     rdx, [rdi+8]; pDestinationSid
0x1800140e3  mov     byte ptr [rdi+4Ch], 1
0x1800140e7  mov     r8, rbx; pSourceSid
0x1800140ea  mov     ecx, eax; nDestinationSidLength
0x1800140ec  call    cs:__imp_CopySid
0x1800140f2  test    eax, eax
0x1800140f4  jnz     short loc_180014112
0x1800140f6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800140fb  mov     ecx, eax; int
0x1800140fd  mov     byte ptr [rdi+4Ch], 0
0x180014101  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180014107  mov     ecx, 80070057h; int
0x18001410c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180014112  mov     rbx, [rsp+28h+arg_0]
0x180014117  add     rsp, 20h
0x18001411b  pop     rdi
0x18001411c  retn
```
