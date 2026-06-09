# ATL::CSid::LoadAccount(_SID const *,ushort const *)

- ea: `0x18001e858`
- end: `0x18001e8e8`
- name: `?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z`
- size: `144`
- prototype: `bool(ATL::CSid *__hidden this, const struct _SID *, const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001859c`
- `0x18001de04`
- `0x18001e614`
- `0x18001f55c`
- `0x180027ca8`
- `0x18002a1f8`
- `0x180056544`
- `0x18005affc`
- `0x180119d40`
- `0x180119ff0`

## callees

- `0x18001e838`
- `0x18001e858`
- `0x18001e8f0`
- `0x18001ea58`
- `0x18009e2e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001e8b2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001e8b2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001e883`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001e883`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001e89a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001e89a`

## pseudocode

```c
bool __fastcall ATL::CSid::LoadAccount(ATL::CSid *this, struct _SID *a2, const unsigned __int16 *a3)
{
  BOOL valid; // eax
  DWORD LengthSid; // eax
  bool result; // al
  int LastErrorAsHResult; // eax

  ATL::CSid::Clear(this);
  if ( !a2 )
    return 0;
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 112);
  valid = IsValidSid(a2);
  try
  {
    if ( !valid )
      ATL::AtlThrowImpl(-2147024809);
    LengthSid = GetLengthSid(a2);
    if ( LengthSid > 0x44 )
      ATL::AtlThrowImpl(-2147024809);
    *((_BYTE *)this + 76) = 1;
    if ( !CopySid(LengthSid, (char *)this + 8, a2) )
    {
      LastErrorAsHResult = LocationHelper::GetLastErrorAsHResult();
      *((_BYTE *)this + 76) = 0;
      ATL::AtlThrowImpl(LastErrorAsHResult);
    }
    result = 1;
  }
  catch ( ... )
  {
    ATL::CSid::Clear(this);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18001e858  mov     [rsp+arg_8], rbx
0x18001e85d  mov     [rsp+arg_0], rcx
0x18001e862  push    rdi
0x18001e863  sub     rsp, 20h
0x18001e867  mov     rdi, rdx
0x18001e86a  mov     rbx, rcx
0x18001e86d  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x18001e872  test    rdi, rdi
0x18001e875  jz      short loc_18001E8E4
0x18001e877  lea     rcx, [rbx+70h]
0x18001e87b  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18001e880  mov     rcx, rdi; pSid
0x18001e883  call    cs:__imp_IsValidSid
0x18001e889  test    eax, eax
0x18001e88b  jnz     short loc_18001E897
0x18001e88d  mov     ecx, 80070057h; int
0x18001e892  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e897  mov     rcx, rdi; pSid
0x18001e89a  call    cs:__imp_GetLengthSid
0x18001e8a0  cmp     eax, 44h ; 'D'
0x18001e8a3  ja      short loc_18001E8C9
0x18001e8a5  mov     byte ptr [rbx+4Ch], 1
0x18001e8a9  lea     rdx, [rbx+8]; pDestinationSid
0x18001e8ad  mov     r8, rdi; pSourceSid
0x18001e8b0  mov     ecx, eax; nDestinationSidLength
0x18001e8b2  call    cs:__imp_CopySid
0x18001e8b8  test    eax, eax
0x18001e8ba  jz      short loc_18001E8D3
0x18001e8bc  mov     al, 1
0x18001e8be  mov     rbx, [rsp+28h+arg_8]
0x18001e8c3  add     rsp, 20h
0x18001e8c7  pop     rdi
0x18001e8c8  retn
0x18001e8c9  mov     ecx, 80070057h; int
0x18001e8ce  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e8d3  call    ?GetLastErrorAsHResult@LocationHelper@@SAJXZ; LocationHelper::GetLastErrorAsHResult(void)
0x18001e8d8  mov     byte ptr [rbx+4Ch], 0
0x18001e8dc  mov     ecx, eax; int
0x18001e8de  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e8e4  xor     al, al
0x18001e8e6  jmp     short loc_18001E8BE
```
