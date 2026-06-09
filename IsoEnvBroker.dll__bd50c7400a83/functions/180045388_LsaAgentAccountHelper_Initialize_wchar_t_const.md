# LsaAgentAccountHelper::Initialize(wchar_t const *)

- ea: `0x180045388`
- end: `0x18004543c`
- name: `?Initialize@LsaAgentAccountHelper@@QEAAJPEB_W@Z`
- size: `180`
- prototype: `int(LsaAgentAccountHelper *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041b64`
- `0x180049a50`

## callees

- `0x180011e18`
- `0x180045388`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800453ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800453ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800453ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800453ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800453e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800453e7`

## string_xrefs

- `0x180045406`: `Failed converting owningUserSid to SID: %#x`

## pseudocode

```c
__int64 __fastcall LsaAgentAccountHelper::Initialize(LsaAgentAccountHelper *this, const wchar_t *a2)
{
  BOOL v3; // r15d
  PSID v4; // rbp
  void *v5; // rsi
  DWORD LastError; // ebx
  __int64 v7; // rbx
  void **v9; // [rsp+20h] [rbp-58h]
  PSID Sid; // [rsp+28h] [rbp-50h] BYREF
  char v11; // [rsp+30h] [rbp-48h]

  Sid = 0;
  v11 = 1;
  v9 = (void **)((char *)this + 8);
  v3 = ConvertStringSidToSidW(a2, &Sid);
  if ( v11 )
  {
    v4 = Sid;
    v5 = *v9;
    if ( *v9 )
    {
      LastError = GetLastError();
      LocalFree(v5);
      SetLastError(LastError);
    }
    *v9 = v4;
  }
  if ( v3 )
  {
    *(_BYTE *)this = 1;
    return 0;
  }
  else
  {
    v7 = GetLastError();
    Log(2u, L"Failed converting owningUserSid to SID: %#x", v7);
    if ( (int)v7 > 0 )
      LODWORD(v7) = (unsigned __int16)v7 | 0x80070000;
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x180045388  push    rbx
0x18004538a  push    rbp
0x18004538b  push    rsi
0x18004538c  push    rdi
0x18004538d  push    r14
0x18004538f  push    r15
0x180045391  sub     rsp, 48h
0x180045395  mov     r8, rdx
0x180045398  mov     [rsp+78h+Sid], 0
0x1800453a1  lea     rax, [rcx+8]
0x1800453a5  mov     [rsp+78h+var_48], 1
0x1800453aa  mov     r14, rcx
0x1800453ad  mov     [rsp+78h+var_58], rax
0x1800453b2  mov     rcx, r8; StringSid
0x1800453b5  lea     rdx, [rsp+78h+Sid]; Sid
0x1800453ba  call    cs:__imp_ConvertStringSidToSidW
0x1800453c0  cmp     [rsp+78h+var_48], 0
0x1800453c5  mov     r15d, eax
0x1800453c8  jz      short loc_1800453F8
0x1800453ca  mov     rdi, [rsp+78h+var_58]
0x1800453cf  mov     rbp, [rsp+78h+Sid]
0x1800453d4  mov     rsi, [rdi]
0x1800453d7  test    rsi, rsi
0x1800453da  jz      short loc_1800453F5
0x1800453dc  call    cs:__imp_GetLastError
0x1800453e2  mov     rcx, rsi; hMem
0x1800453e5  mov     ebx, eax
0x1800453e7  call    cs:__imp_LocalFree
0x1800453ed  mov     ecx, ebx; dwErrCode
0x1800453ef  call    cs:__imp_SetLastError
0x1800453f5  mov     [rdi], rbp
0x1800453f8  test    r15d, r15d
0x1800453fb  jnz     short loc_180045429
0x1800453fd  call    cs:__imp_GetLastError
0x180045403  mov     r8d, eax
0x180045406  lea     rdx, aFailedConverti_0; "Failed converting owningUserSid to SID:"...
0x18004540d  lea     ecx, [r15+2]; unsigned __int8
0x180045411  mov     ebx, eax
0x180045413  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180045418  test    ebx, ebx
0x18004541a  jle     short loc_180045425
0x18004541c  movzx   ebx, bx
0x18004541f  or      ebx, 80070000h
0x180045425  mov     eax, ebx
0x180045427  jmp     short loc_18004542F
0x180045429  mov     byte ptr [r14], 1
0x18004542d  xor     eax, eax
0x18004542f  add     rsp, 48h
0x180045433  pop     r15
0x180045435  pop     r14
0x180045437  pop     rdi
0x180045438  pop     rsi
0x180045439  pop     rbp
0x18004543a  pop     rbx
0x18004543b  retn
```
