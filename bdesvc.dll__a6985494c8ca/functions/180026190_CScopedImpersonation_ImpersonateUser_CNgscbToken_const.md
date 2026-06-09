# CScopedImpersonation::ImpersonateUser(CNgscbToken const &)

- ea: `0x180026190`
- end: `0x1800261d2`
- name: `?ImpersonateUser@CScopedImpersonation@@QEAAJAEBVCNgscbToken@@@Z`
- size: `66`
- prototype: `__int64 __fastcall(CScopedImpersonation *__hidden this, const struct CNgscbToken *)`
- caller_count: `13`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ff00`
- `0x180033618`
- `0x18003b560`
- `0x180043e5c`
- `0x180052594`
- `0x18005280c`
- `0x180054fac`
- `0x180055fb4`
- `0x18006fa9c`
- `0x18006fc78`
- `0x180070958`
- `0x180071170`
- `0x1800714cc`

## callees

- `0x180026190`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800261ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800261ac`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002619c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002619c`

## pseudocode

```c
signed int __fastcall CScopedImpersonation::ImpersonateUser(CScopedImpersonation *this, HANDLE *a2)
{
  signed int result; // eax

  if ( ImpersonateLoggedOnUser(*a2) )
  {
    result = 0;
    *(_BYTE *)this = 1;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180026190  push    rbx
0x180026192  sub     rsp, 20h
0x180026196  mov     rbx, rcx
0x180026199  mov     rcx, [rdx]; hToken
0x18002619c  call    cs:__imp_ImpersonateLoggedOnUser
0x1800261a3  nop     dword ptr [rax+rax+00h]
0x1800261a8  test    eax, eax
0x1800261aa  jnz     short loc_1800261C6
0x1800261ac  call    cs:__imp_GetLastError
0x1800261b3  nop     dword ptr [rax+rax+00h]
0x1800261b8  test    eax, eax
0x1800261ba  jle     short loc_1800261CB
0x1800261bc  movzx   eax, ax
0x1800261bf  or      eax, 80070000h
0x1800261c4  jmp     short loc_1800261CB
0x1800261c6  xor     eax, eax
0x1800261c8  mov     byte ptr [rbx], 1
0x1800261cb  add     rsp, 20h
0x1800261cf  pop     rbx
0x1800261d0  retn
```
