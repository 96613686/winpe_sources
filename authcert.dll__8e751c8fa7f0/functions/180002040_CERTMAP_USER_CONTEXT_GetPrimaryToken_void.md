# CERTMAP_USER_CONTEXT::GetPrimaryToken(void)

- ea: `0x180002040`
- end: `0x1800020ce`
- name: `?GetPrimaryToken@CERTMAP_USER_CONTEXT@@UEAAPEAXXZ`
- size: `142`
- prototype: `void *__fastcall(CERTMAP_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002082`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000206f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000206f`
- `iisutil!PuDbgPrint` at `0x1800020bf`
- `iisutil!PuDbgPrint` at `0x1800020bf`

## string_xrefs

- `0x1800020ad`: `DuplicateTokenEx failed, hr = 0x%x\n`
- `0x1800020a6`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\certmap_auth\certmap_auth.cxx`
- `0x18000209b`: `CERTMAP_USER_CONTEXT::GetPrimaryToken`

## pseudocode

```c
void *__fastcall CERTMAP_USER_CONTEXT::GetPrimaryToken(CERTMAP_USER_CONTEXT *this)
{
  void **phNewToken; // rbx
  signed int LastError; // eax

  phNewToken = (void **)((char *)this + 80);
  if ( !*((_QWORD *)this + 10)
    && !DuplicateTokenEx(*((HANDLE *)this + 9), 0xF01FFu, 0, SecurityImpersonation, TokenPrimary, phNewToken)
    && (g_dwDebugFlags & 3) != 0 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\certmap_auth\\certmap_auth.cxx",
      798,
      "CERTMAP_USER_CONTEXT::GetPrimaryToken",
      "DuplicateTokenEx failed, hr = 0x%x\n",
      LastError);
  }
  return *phNewToken;
}

```

## disassembly

```asm
0x180002040  push    rbx
0x180002042  sub     rsp, 30h
0x180002046  lea     rbx, [rcx+50h]
0x18000204a  cmp     qword ptr [rbx], 0
0x18000204e  jnz     short loc_1800020C5
0x180002050  mov     rcx, [rcx+48h]; hExistingToken
0x180002054  mov     r9d, 2; ImpersonationLevel
0x18000205a  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x18000205f  xor     r8d, r8d; lpTokenAttributes
0x180002062  mov     edx, 0F01FFh; dwDesiredAccess
0x180002067  mov     [rsp+38h+TokenType], 1; TokenType
0x18000206f  call    cs:__imp_DuplicateTokenEx
0x180002075  test    eax, eax
0x180002077  jnz     short loc_1800020C5
0x180002079  test    byte ptr cs:g_dwDebugFlags, 3
0x180002080  jz      short loc_1800020C5
0x180002082  call    cs:__imp_GetLastError
0x180002088  test    eax, eax
0x18000208a  jle     short loc_180002094
0x18000208c  movzx   eax, ax
0x18000208f  or      eax, 80070000h
0x180002094  mov     rcx, cs:g_pDebug
0x18000209b  lea     r9, aCertmapUserCon; "CERTMAP_USER_CONTEXT::GetPrimaryToken"
0x1800020a2  mov     dword ptr [rsp+38h+phNewToken], eax
0x1800020a6  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800020ad  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, hr = 0x%x\n"
0x1800020b4  mov     r8d, 31Eh
0x1800020ba  mov     qword ptr [rsp+38h+TokenType], rax
0x1800020bf  call    cs:__imp_PuDbgPrint
0x1800020c5  mov     rax, [rbx]
0x1800020c8  add     rsp, 30h
0x1800020cc  pop     rbx
0x1800020cd  retn
```
