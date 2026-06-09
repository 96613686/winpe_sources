# GetRootKey(ldap *,ushort const *,ushort const *,unsigned __int64,unsigned __int64,_ROOT_KEY_HEADER * *)

- ea: `0x1800058a0`
- end: `0x18000592b`
- name: `?GetRootKey@@YAJPEAUldap@@PEBG1_K2PEAPEAU_ROOT_KEY_HEADER@@@Z`
- size: `139`
- prototype: `__int64 __usercall@<rax>(LDAP *ld@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int64@<r9>, unsigned __int64, struct _ROOT_KEY_HEADER **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008e1c`

## callees

- `0x180005740`
- `0x1800058a0`
- `0x180006908`
- `0x18001a450`

## import_xrefs

- `WLDAP32!__imp_ldap_msgfree` at `0x180005918`
- `WLDAP32!__imp_ldap_msgfree` at `0x180005918`

## string_xrefs

- `0x1800058f9`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`

## pseudocode

```c
__int64 __fastcall GetRootKey(
        LDAP *ld,
        WCHAR *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int64 a5,
        struct _ROOT_KEY_HEADER **a6)
{
  int LastestKeyFromQueryResult; // eax
  unsigned int v8; // ebx
  char v9; // r9
  LDAPMessage *res; // [rsp+30h] [rbp-18h] BYREF

  res = 0;
  LastestKeyFromQueryResult = QueryRootKeyObjects(ld, a2, (__int64)a3, a4, a5, &res);
  v8 = LastestKeyFromQueryResult;
  if ( LastestKeyFromQueryResult >= 0 )
  {
    LastestKeyFromQueryResult = GetLastestKeyFromQueryResult(ld, res, a6);
    v8 = LastestKeyFromQueryResult;
    if ( LastestKeyFromQueryResult >= 0 )
      goto LABEL_6;
    v9 = -1;
  }
  else
  {
    v9 = -11;
  }
  SidKeyDebugTraceError(
    LastestKeyFromQueryResult,
    "hr",
    "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
    v9);
LABEL_6:
  if ( res )
    ldap_msgfree(res);
  return v8;
}

```

## disassembly

```asm
0x1800058a0  mov     r11, rsp
0x1800058a3  mov     [r11+8], rbx
0x1800058a7  push    rdi
0x1800058a8  sub     rsp, 40h
0x1800058ac  lea     rax, [r11-18h]
0x1800058b0  mov     qword ptr [r11-18h], 0
0x1800058b8  mov     [r11-20h], rax
0x1800058bc  mov     rdi, rcx
0x1800058bf  mov     rax, [rsp+48h+arg_20]
0x1800058c4  mov     [r11-28h], rax
0x1800058c8  call    QueryRootKeyObjects
0x1800058cd  mov     ebx, eax
0x1800058cf  test    eax, eax
0x1800058d1  jns     short loc_1800058DB
0x1800058d3  mov     r9d, 4F5h
0x1800058d9  jmp     short loc_1800058F9
0x1800058db  mov     r8, [rsp+48h+arg_28]
0x1800058e0  mov     rcx, rdi; ld
0x1800058e3  mov     rdx, [rsp+48h+res]
0x1800058e8  call    GetLastestKeyFromQueryResult
0x1800058ed  mov     ebx, eax
0x1800058ef  test    eax, eax
0x1800058f1  jns     short loc_18000590E
0x1800058f3  mov     r9d, 4FFh; unsigned int
0x1800058f9  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180005900  mov     ecx, eax; unsigned int
0x180005902  lea     rdx, aHr; "hr"
0x180005909  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000590e  mov     rcx, [rsp+48h+res]; res
0x180005913  test    rcx, rcx
0x180005916  jz      short loc_18000591E
0x180005918  call    cs:__imp_ldap_msgfree
0x18000591e  mov     eax, ebx
0x180005920  mov     rbx, [rsp+48h+arg_0]
0x180005925  add     rsp, 40h
0x180005929  pop     rdi
0x18000592a  retn
```
