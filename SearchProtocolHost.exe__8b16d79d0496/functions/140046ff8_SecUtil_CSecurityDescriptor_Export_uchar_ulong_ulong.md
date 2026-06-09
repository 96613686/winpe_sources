# SecUtil::CSecurityDescriptor::Export(uchar *,ulong,ulong *)

- ea: `0x140046ff8`
- end: `0x14004706d`
- name: `?Export@CSecurityDescriptor@SecUtil@@QEAAJPEAEKPEAK@Z`
- size: `117`
- prototype: `int(SecUtil::CSecurityDescriptor *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140022778`

## callees

- `0x140015958`
- `0x140046ff8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140047018`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140047018`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140047025`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140047025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140047031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140047031`

## string_xrefs

- `0x140047051`: `"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx"`
- `0x140047045`: `[UtilCommon] Bad pointer in SecUtil::CSecurityDescriptor::Export`

## pseudocode

```c
int __fastcall SecUtil::CSecurityDescriptor::Export(
        SecUtil::CSecurityDescriptor *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  int result; // eax

  if ( a2 && a4 )
  {
    *a4 = a3;
    if ( MakeSelfRelativeSD(this, a2, a4) )
    {
      *a4 = GetSecurityDescriptorLength(a2);
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\secutil\\\\secutil.cxx\"",
      (const wchar_t *)0x14D,
      (unsigned int)L"[UtilCommon] Bad pointer in SecUtil::CSecurityDescriptor::Export",
      (const wchar_t *)a4);
    return -2147467261;
  }
  return result;
}

```

## disassembly

```asm
0x140046ff8  mov     [rsp+arg_0], rbx
0x140046ffd  push    rdi
0x140046ffe  sub     rsp, 20h
0x140047002  mov     rbx, r9
0x140047005  mov     rdi, rdx
0x140047008  test    rdx, rdx
0x14004700b  jz      short loc_140047045
0x14004700d  test    rbx, rbx
0x140047010  jz      short loc_140047045
0x140047012  mov     [r9], r8d
0x140047015  mov     r8, rbx; lpdwBufferLength
0x140047018  call    cs:__imp_MakeSelfRelativeSD
0x14004701e  test    eax, eax
0x140047020  jz      short loc_140047031
0x140047022  mov     rcx, rdi; pSecurityDescriptor
0x140047025  call    cs:__imp_GetSecurityDescriptorLength
0x14004702b  mov     [rbx], eax
0x14004702d  xor     eax, eax
0x14004702f  jmp     short loc_140047062
0x140047031  call    cs:__imp_GetLastError
0x140047037  test    eax, eax
0x140047039  jle     short loc_140047062
0x14004703b  movzx   eax, ax
0x14004703e  or      eax, 80070000h
0x140047043  jmp     short loc_140047062
0x140047045  lea     r8, aUtilcommonBadP; "[UtilCommon] Bad pointer in SecUtil::CS"...
0x14004704c  mov     edx, 14Dh; wchar_t *
0x140047051  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140047058  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14004705d  mov     eax, 80004003h
0x140047062  mov     rbx, [rsp+28h+arg_0]
0x140047067  add     rsp, 20h
0x14004706b  pop     rdi
0x14004706c  retn
```
