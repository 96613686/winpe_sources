# SecUtil::CSecurityDescriptor::SetDacl(int,_ACL *,int)

- ea: `0x1400473a8`
- end: `0x140047402`
- name: `?SetDacl@CSecurityDescriptor@SecUtil@@QEAAXHPEAU_ACL@@H@Z`
- size: `90`
- prototype: `void(SecUtil::CSecurityDescriptor *__hidden this, int, struct _ACL *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d5c4`
- `0x140022778`
- `0x14003a8e8`

## callees

- `0x140015958`
- `0x1400317c8`
- `0x1400473a8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400473b5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400473b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400473bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400473bf`

## string_xrefs

- `0x1400473d4`: `"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx"`
- `0x1400473e7`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x1400473c5`: `[UtilSecurity] SetSecurityDescriptorDacl failed. 0x%08x`

## pseudocode

```c
void __fastcall SecUtil::CSecurityDescriptor::SetDacl(SecUtil::CSecurityDescriptor *this, __int64 a2, struct _ACL *a3)
{
  const wchar_t *LastError; // rbx
  unsigned int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !SetSecurityDescriptorDacl(this, 1, a3, 0) )
  {
    LastError = (const wchar_t *)GetLastError();
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\secutil\\\\secutil.cxx\"",
      (const wchar_t *)0xC4,
      (unsigned int)L"[UtilSecurity] SetSecurityDescriptorDacl failed. 0x%08x",
      LastError);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
      (const char *)(unsigned int)LastError,
      v4);
  }
}

```

## disassembly

```asm
0x1400473a8  push    rbx; unsigned int
0x1400473aa  sub     rsp, 20h
0x1400473ae  xor     r9d, r9d; bDaclDefaulted
0x1400473b1  lea     edx, [r9+1]; bDaclPresent
0x1400473b5  call    cs:__imp_SetSecurityDescriptorDacl
0x1400473bb  test    eax, eax
0x1400473bd  jnz     short loc_1400473FC
0x1400473bf  call    cs:__imp_GetLastError
0x1400473c5  lea     r8, aUtilsecuritySe; "[UtilSecurity] SetSecurityDescriptorDac"...
0x1400473cc  mov     edx, 0C4h; wchar_t *
0x1400473d1  mov     r9d, eax; wchar_t *
0x1400473d4  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1400473db  mov     ebx, eax
0x1400473dd  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1400473e2  mov     rcx, [rsp+28h]; this
0x1400473e7  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400473ee  mov     r9d, ebx; char *
0x1400473f1  mov     edx, 0C5h; void *
0x1400473f6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400473fc  add     rsp, 20h
0x140047400  pop     rbx
0x140047401  retn
```
