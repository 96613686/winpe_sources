# RegistryPath::CreateKey(ushort *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)

- ea: `0x18009182c`
- end: `0x18009191e`
- name: `?CreateKey@RegistryPath@@QEBAKPEAGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAUHKEY__@@PEAK@Z`
- size: `242`
- prototype: `unsigned int __fastcall(RegistryPath *__hidden this, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180091924`

## callees

- `0x18008aa28`
- `0x18008aecc`
- `0x18008afb0`
- `0x18009182c`
- `0x180092760`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180091894`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180091894`

## string_xrefs

- `0x1800918a3`: `RegCreateKeyExW`
- `0x1800918be`: `%s: Failed to create or open registry key "%s". Error code: 0x%08x.`
- `0x1800918d5`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x1800918b4`: `RegistryPath::CreateKey`
- `0x1800918ce`: `RegistryPath::CreateKey`
- `0x1800918e3`: `RegistryPath::CreateKey`
- `0x1800918fd`: `RegistryPath::CreateKey`

## pseudocode

```c
__int64 __fastcall RegistryPath::CreateKey(
        RegistryPath *this,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        struct _SECURITY_ATTRIBUTES *const a5,
        HKEY *a6)
{
  const WCHAR *v7; // rax
  __int64 v8; // rcx
  PHKEY phkResult; // r8
  LSTATUS Key; // eax
  unsigned int v11; // edi

  if ( !a6 )
  {
    Logger::TraceError(L"%s: phkResult should not be null.", L"RegistryPath::CreateKey");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistryPath::CreateKey", L"phkResult");
    return 87;
  }
  *a6 = 0;
  if ( !*((_QWORD *)this + 4) || !*(_QWORD *)this || !**(_WORD **)this )
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::CreateKey");
    return 87;
  }
  v7 = RegistryPath::SubPath(this);
  Key = RegCreateKeyExW(*(HKEY *)(v8 + 32), v7, 0, 0, 0, 2u, 0, phkResult, 0);
  v11 = Key;
  if ( Key )
  {
    Logger::WriteRegistryFailureEvent(Key, L"RegCreateKeyExW", *(const unsigned __int16 **)this);
    Logger::TraceError(
      L"%s: Failed to create or open registry key \"%s\". Error code: 0x%08x.",
      L"RegistryPath::CreateKey",
      *(_QWORD *)this,
      v11);
  }
  return v11;
}

```

## disassembly

```asm
0x18009182c  mov     [rsp+arg_0], rbx
0x180091831  mov     [rsp+arg_8], rsi
0x180091836  push    rdi
0x180091837  sub     rsp, 50h
0x18009183b  mov     r8, [rsp+58h+arg_28]
0x180091843  xor     esi, esi
0x180091845  mov     rbx, rcx
0x180091848  test    r8, r8
0x18009184b  jz      loc_1800918E3
0x180091851  mov     [r8], rsi
0x180091854  cmp     [rcx+20h], rsi
0x180091858  jz      short loc_1800918CE
0x18009185a  mov     rax, [rcx]
0x18009185d  test    rax, rax
0x180091860  jz      short loc_1800918CE
0x180091862  cmp     [rax], si
0x180091865  jz      short loc_1800918CE
0x180091867  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x18009186c  mov     rcx, [rcx+20h]; hKey
0x180091870  xor     r9d, r9d; lpClass
0x180091873  mov     [rsp+58h+lpdwDisposition], rsi; lpdwDisposition
0x180091878  mov     rdx, rax; lpSubKey
0x18009187b  mov     [rsp+58h+phkResult], r8; phkResult
0x180091880  xor     r8d, r8d; Reserved
0x180091883  mov     [rsp+58h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180091888  mov     [rsp+58h+samDesired], 2; samDesired
0x180091890  mov     [rsp+58h+dwOptions], esi; dwOptions
0x180091894  call    cs:__imp_RegCreateKeyExW
0x18009189a  mov     edi, eax
0x18009189c  test    eax, eax
0x18009189e  jz      short loc_1800918CA
0x1800918a0  mov     r8, [rbx]; unsigned __int16 *
0x1800918a3  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x1800918aa  mov     ecx, eax; unsigned int
0x1800918ac  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x1800918b1  mov     r8, [rbx]
0x1800918b4  lea     rdx, aRegistrypathCr_0; "RegistryPath::CreateKey"
0x1800918bb  mov     r9d, edi
0x1800918be  lea     rcx, aSFailedToCreat; "%s: Failed to create or open registry k"...
0x1800918c5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800918ca  mov     eax, edi
0x1800918cc  jmp     short loc_18009190E
0x1800918ce  lea     rdx, aRegistrypathCr_0; "RegistryPath::CreateKey"
0x1800918d5  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x1800918dc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800918e1  jmp     short loc_180091909
0x1800918e3  lea     rdx, aRegistrypathCr_0; "RegistryPath::CreateKey"
0x1800918ea  lea     rcx, aSPhkresultShou; "%s: phkResult should not be null."
0x1800918f1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800918f6  lea     rdx, aPhkresult; "phkResult"
0x1800918fd  lea     rcx, aRegistrypathCr_0; "RegistryPath::CreateKey"
0x180091904  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180091909  mov     eax, 57h ; 'W'
0x18009190e  mov     rbx, [rsp+58h+arg_0]
0x180091913  mov     rsi, [rsp+58h+arg_8]
0x180091918  add     rsp, 50h
0x18009191c  pop     rdi
0x18009191d  retn
```
