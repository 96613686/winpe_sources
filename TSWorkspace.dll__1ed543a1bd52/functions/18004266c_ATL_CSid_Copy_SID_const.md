# ATL::CSid::Copy(_SID const &)

- ea: `0x18004266c`
- end: `0x1800426d5`
- name: `?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z`
- size: `105`
- prototype: `void(ATL::CSid *__hidden this, const struct _SID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180041b98`
- `0x180043b90`

## callees

- `0x180006d14`
- `0x180007598`
- `0x18004266c`

## import_xrefs

- `ADVAPI32!CopySid` at `0x1800426a4`
- `ADVAPI32!CopySid` at `0x1800426a4`
- `ADVAPI32!GetLengthSid` at `0x18004268c`
- `ADVAPI32!GetLengthSid` at `0x18004268c`
- `ADVAPI32!IsValidSid` at `0x18004267f`
- `ADVAPI32!IsValidSid` at `0x18004267f`

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
0x18004266c  mov     [rsp+arg_0], rbx
0x180042671  push    rdi
0x180042672  sub     rsp, 20h
0x180042676  mov     rdi, rcx
0x180042679  mov     rbx, rdx
0x18004267c  mov     rcx, rdx; pSid
0x18004267f  call    cs:__imp_IsValidSid
0x180042685  test    eax, eax
0x180042687  jz      short loc_1800426BF
0x180042689  mov     rcx, rbx; pSid
0x18004268c  call    cs:__imp_GetLengthSid
0x180042692  cmp     eax, 44h ; 'D'
0x180042695  ja      short loc_1800426BF
0x180042697  lea     rdx, [rdi+8]; pDestinationSid
0x18004269b  mov     byte ptr [rdi+4Ch], 1
0x18004269f  mov     r8, rbx; pSourceSid
0x1800426a2  mov     ecx, eax; nDestinationSidLength
0x1800426a4  call    cs:__imp_CopySid
0x1800426aa  test    eax, eax
0x1800426ac  jnz     short loc_1800426CA
0x1800426ae  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800426b3  mov     ecx, eax; int
0x1800426b5  mov     byte ptr [rdi+4Ch], 0
0x1800426b9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800426bf  mov     ecx, 80070057h; int
0x1800426c4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800426ca  mov     rbx, [rsp+28h+arg_0]
0x1800426cf  add     rsp, 20h
0x1800426d3  pop     rdi
0x1800426d4  retn
```
