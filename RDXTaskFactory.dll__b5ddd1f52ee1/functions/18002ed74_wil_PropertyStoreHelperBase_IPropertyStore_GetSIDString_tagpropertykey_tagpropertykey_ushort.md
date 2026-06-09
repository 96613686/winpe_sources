# wil::PropertyStoreHelperBase<IPropertyStore>::GetSIDString<_tagpropertykey>(_tagpropertykey,ushort * *)

- ea: `0x18002ed74`
- end: `0x18002ee18`
- name: `??$GetSIDString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, __int128 *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180031284`

## callees

- `0x18001e19c`
- `0x18002107c`
- `0x180025cd8`
- `0x18002ed74`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002edf6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002edf6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002edbf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002edbf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ee07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ee07`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::PropertyStoreHelperBase<IPropertyStore>::GetSIDString<_tagpropertykey>(
        __int64 a1,
        __int128 *a2,
        _QWORD *a3)
{
  int FailIf; // ebx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r9
  __int128 v8; // [rsp+30h] [rbp-48h] BYREF
  int v9; // [rsp+40h] [rbp-38h]
  PROPVARIANT pvar[5]; // [rsp+50h] [rbp-28h] BYREF
  LPWSTR StringSid; // [rsp+A8h] [rbp+30h] BYREF

  *a3 = 0;
  LOWORD(pvar[0]) = 0;
  v8 = *a2;
  v9 = *((_DWORD *)a2 + 4);
  FailIf = wil::PropertyStoreHelperBase<IPropertyStore>::GetFailIfEmpty<_tagpropertykey>(a1, &v8, pvar);
  if ( FailIf >= 0 )
  {
    if ( LOWORD(pvar[0]) == 65 )
    {
      StringSid = 0;
      if ( ConvertSidToStringSidW(pvar[2], &StringSid) || (FailIf = ResultFromKnownLastError(), FailIf >= 0) )
      {
        v6 = -1;
        do
          ++v6;
        while ( StringSid[v6] );
        FailIf = _AllocStringWorker<CTCoAllocPolicy>(v5, v4, StringSid);
        LocalFree(StringSid);
      }
    }
    else
    {
      FailIf = -2147352571;
    }
  }
  PropVariantClear(pvar);
  return (unsigned int)FailIf;
}

```

## disassembly

```asm
0x18002ed74  push    rbp
0x18002ed76  push    rbx
0x18002ed77  push    rsi
0x18002ed78  push    rdi
0x18002ed79  mov     rbp, rsp
0x18002ed7c  sub     rsp, 78h
0x18002ed80  mov     rdi, r8
0x18002ed83  xor     esi, esi
0x18002ed85  mov     [r8], rsi
0x18002ed88  mov     word ptr [rbp+pvar], si
0x18002ed8c  movaps  xmm0, xmmword ptr [rdx]
0x18002ed8f  movaps  [rbp+var_48], xmm0
0x18002ed93  mov     eax, [rdx+10h]
0x18002ed96  mov     [rbp+var_38], eax
0x18002ed99  lea     r8, [rbp+pvar]
0x18002ed9d  lea     rdx, [rbp+var_48]
0x18002eda1  call    ??$GetFailIfEmpty@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetFailIfEmpty<_tagpropertykey>(_tagpropertykey,tagPROPVARIANT *)
0x18002eda6  mov     ebx, eax
0x18002eda8  test    eax, eax
0x18002edaa  js      short loc_18002EE03
0x18002edac  cmp     word ptr [rbp+pvar], 41h ; 'A'
0x18002edb1  jnz     short loc_18002EDFE
0x18002edb3  mov     [rbp+StringSid], rsi
0x18002edb7  lea     rdx, [rbp+StringSid]; StringSid
0x18002edbb  mov     rcx, [rbp+Sid]; Sid
0x18002edbf  call    cs:__imp_ConvertSidToStringSidW
0x18002edc5  test    eax, eax
0x18002edc7  jnz     short loc_18002EDD4
0x18002edc9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002edce  mov     ebx, eax
0x18002edd0  test    eax, eax
0x18002edd2  js      short loc_18002EE03
0x18002edd4  mov     r8, [rbp+StringSid]
0x18002edd8  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002eddc  inc     r9
0x18002eddf  cmp     [r8+r9*2], si
0x18002ede4  jnz     short loc_18002EDDC
0x18002ede6  mov     [rsp+78h+var_50], rdi
0x18002edeb  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002edf0  mov     ebx, eax
0x18002edf2  mov     rcx, [rbp+StringSid]; hMem
0x18002edf6  call    cs:__imp_LocalFree
0x18002edfc  jmp     short loc_18002EE03
0x18002edfe  mov     ebx, 80020005h
0x18002ee03  lea     rcx, [rbp+pvar]; pvar
0x18002ee07  call    cs:__imp_PropVariantClear
0x18002ee0d  mov     eax, ebx
0x18002ee0f  add     rsp, 78h
0x18002ee13  pop     rdi
0x18002ee14  pop     rsi
0x18002ee15  pop     rbx
0x18002ee16  pop     rbp
0x18002ee17  retn
```
