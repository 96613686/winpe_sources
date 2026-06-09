# CIEAdminBrokerObject::UpdateAllowedDomainsList(_GUID const &,ushort *,int)

- ea: `0x406100`
- end: `0x406151`
- name: `?UpdateAllowedDomainsList@CIEAdminBrokerObject@@UAGJABU_GUID@@PAGH@Z`
- size: `81`
- prototype: `int __stdcall(CIEAdminBrokerObject *__hidden this, const struct _GUID *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x406100`

## import_xrefs

- `iertutil!__imp_?EDL_InitializeAllowedDomainsList@@YGJABU_GUID@@PBG@Z` at `0x406139`
- `iertutil!__imp_?EDL_InitializeAllowedDomainsList@@YGJABU_GUID@@PBG@Z` at `0x406139`
- `iertutil!__imp_?EDL_AddNewDomain@@YGJABU_GUID@@PBG@Z` at `0x406141`
- `iertutil!__imp_?EDL_AddNewDomain@@YGJABU_GUID@@PBG@Z` at `0x406141`

## pseudocode

```c
int __stdcall CIEAdminBrokerObject::UpdateAllowedDomainsList(
        CIEAdminBrokerObject *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        int a4)
{
  int v4; // ecx
  int v5; // edi
  int v6; // edx

  v4 = -2147467259;
  v5 = *((_DWORD *)this + 2);
  if ( v5 )
  {
    v4 = -2147024891;
    v6 = 0;
    while ( *(&a2->Data1 + v6) == *(_DWORD *)(v5 + 4 * v6 + 48) )
    {
      if ( ++v6 == 4 )
      {
        if ( a4 )
          return EDL_AddNewDomain(a2, a3);
        else
          return EDL_InitializeAllowedDomainsList(a2, a3);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x406100  mov     edi, edi
0x406102  push    ebp
0x406103  mov     ebp, esp
0x406105  mov     eax, [ebp+this]
0x406108  mov     ecx, 80004005h
0x40610d  push    edi
0x40610e  mov     edi, [eax+8]
0x406111  test    edi, edi
0x406113  jz      short loc_40614A
0x406115  push    esi
0x406116  mov     esi, [ebp+arg_4]
0x406119  mov     ecx, 80070005h
0x40611e  xor     edx, edx
0x406120  mov     eax, [esi+edx*4]
0x406123  cmp     eax, [edi+edx*4+30h]
0x406127  jnz     short loc_406149
0x406129  inc     edx
0x40612a  cmp     edx, 4
0x40612d  jnz     short loc_406120
0x40612f  cmp     [ebp+arg_C], 0
0x406133  push    [ebp+arg_8]
0x406136  push    esi
0x406137  jnz     short loc_406141
0x406139  call    ds:__imp_?EDL_InitializeAllowedDomainsList@@YGJABU_GUID@@PBG@Z; EDL_InitializeAllowedDomainsList(_GUID const &,ushort const *)
0x40613f  jmp     short loc_406147
0x406141  call    ds:__imp_?EDL_AddNewDomain@@YGJABU_GUID@@PBG@Z; EDL_AddNewDomain(_GUID const &,ushort const *)
0x406147  mov     ecx, eax
0x406149  pop     esi
0x40614a  mov     eax, ecx
0x40614c  pop     edi
0x40614d  pop     ebp
0x40614e  retn    10h
```
