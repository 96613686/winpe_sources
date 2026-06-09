# CNetworkItemFactory::OnUpdate(tagQueryUpdateAction,unsigned __int64,IFunctionInstance *)

- ea: `0x1800037f8`
- end: `0x1800039ca`
- name: `?OnUpdate@CNetworkItemFactory@@QEAAJW4tagQueryUpdateAction@@_KPEAUIFunctionInstance@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(CNetworkItemFactory *this, enum tagQueryUpdateAction, __int64, struct IFunctionInstance *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180003780`

## callees

- `0x1800037f8`
- `0x18000488c`
- `0x1800049f4`
- `0x180005b84`
- `0x180005cc0`
- `0x18000b010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180003875`
- `KERNEL32!CompareStringW` at `0x1800038c8`
- `KERNEL32!CompareStringW` at `0x180003875`
- `KERNEL32!CompareStringW` at `0x1800038c8`
- `ole32!PropVariantClear` at `0x180003961`
- `ole32!PropVariantClear` at `0x180003961`
- `ole32!CoTaskMemFree` at `0x18000396b`
- `ole32!CoTaskMemFree` at `0x180003975`
- `ole32!CoTaskMemFree` at `0x18000396b`
- `ole32!CoTaskMemFree` at `0x180003975`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180003927`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180003951`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180003927`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180003951`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::OnUpdate(
        CNetworkItemFactory *this,
        enum tagQueryUpdateAction a2,
        __int64 a3,
        struct IFunctionInstance *a4)
{
  struct IFunctionInstanceVtbl *lpVtbl; // rax
  BOOL v8; // edi
  const struct _tagpropertykey *v9; // rdx
  __int64 v10; // rsi
  __int64 result; // rax
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  struct tagPROPVARIANT pszStr1; // [rsp+38h] [rbp-18h] BYREF
  __int64 v14; // [rsp+90h] [rbp+40h] BYREF
  PCNZWCH lpString1; // [rsp+98h] [rbp+48h] BYREF

  v14 = a3;
  lpVtbl = a4->lpVtbl;
  lpString1 = 0;
  pv = 0;
  if ( ((int (__fastcall *)(struct IFunctionInstance *, PCNZWCH *, LPVOID *))lpVtbl->GetCategory)(a4, &lpString1, &pv) >= 0 )
  {
    v8 = 0;
    if ( CompareStringW(0x7Fu, 0, lpString1, -1, L"Provider\\Microsoft.Networking.Netbios", -1) == 2 )
    {
      LODWORD(v14) = 0;
      if ( GetFIProperty(a4, v9, (unsigned int *)&v14) < 0 || (((_DWORD)v14 - 2) & 0xFFFFFFF7) != 0 )
        v8 = 1;
    }
    else if ( CompareStringW(0x7Fu, 0, lpString1, -1, L"Provider\\Microsoft.Networking.SSDP", -1) == 2 )
    {
      memset(&pszStr1, 0, sizeof(pszStr1));
      if ( (int)GetFIProperty(a4, &PKEY_PNPX_Types, &pszStr1) >= 0 )
      {
        if ( pszStr1.vt == 31 )
        {
          v8 = StrCmpNICW(pszStr1.bstrVal, L"urn:schemas-wifialliance-org:device:WFADevice", 45) == 0;
        }
        else if ( pszStr1.vt == 4127 )
        {
          v10 = 0;
          if ( pszStr1.lVal )
          {
            while ( StrCmpNICW(
                      *(LPCWSTR *)&pszStr1.bstrblobVal.pData[8 * v10],
                      L"urn:schemas-wifialliance-org:device:WFADevice",
                      45) )
            {
              v10 = (unsigned int)(v10 + 1);
              if ( (unsigned int)v10 >= pszStr1.lVal )
                goto LABEL_16;
            }
            v8 = 1;
          }
        }
LABEL_16:
        PropVariantClear((PROPVARIANT *)&pszStr1);
      }
    }
    CoTaskMemFree((LPVOID)lpString1);
    CoTaskMemFree(pv);
    if ( v8 )
      return 1;
  }
  if ( a2 == QUA_ADD )
    return CNetworkItemFactory::_HandleDeviceAdd(this, a4);
  if ( a2 == QUA_REMOVE )
    return CNetworkItemFactory::_HandleDeviceRemove(this, a4);
  result = 2147942487LL;
  if ( a2 == QUA_CHANGE )
    return CNetworkItemFactory::_HandleDeviceAdd(this, a4);
  return result;
}

```

## disassembly

```asm
0x1800037f8  mov     [rsp-28h+arg_0], rbx
0x1800037fd  mov     [rsp-28h+arg_8], rsi
0x180003802  mov     [rsp-28h+arg_10], r8
0x180003807  push    rbp
0x180003808  push    rdi
0x180003809  push    r13
0x18000380b  push    r14
0x18000380d  push    r15
0x18000380f  mov     rbp, rsp
0x180003812  sub     rsp, 50h
0x180003816  mov     rax, [r9]
0x180003819  lea     r8, [rbp+pv]
0x18000381d  mov     r14d, edx
0x180003820  mov     [rbp+lpString1], 0
0x180003828  mov     r15, rcx
0x18000382b  mov     [rbp+pv], 0
0x180003833  lea     rdx, [rbp+lpString1]
0x180003837  mov     rcx, r9
0x18000383a  mov     rax, [rax+38h]
0x18000383e  mov     rbx, r9
0x180003841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003846  mov     r13d, 1
0x18000384c  test    eax, eax
0x18000384e  js      loc_180003984
0x180003854  mov     r8, [rbp+lpString1]; lpString1
0x180003858  lea     rax, aProviderMicros_0; "Provider\\Microsoft.Networking.Netbios"
0x18000385f  or      esi, 0FFFFFFFFh
0x180003862  xor     edi, edi
0x180003864  mov     [rsp+50h+cchCount2], esi; cchCount2
0x180003868  mov     r9d, esi; cchCount1
0x18000386b  xor     edx, edx; dwCmpFlags
0x18000386d  mov     [rsp+50h+lpString2], rax; lpString2
0x180003872  lea     ecx, [rdi+7Fh]; Locale
0x180003875  call    cs:__imp_CompareStringW
0x18000387b  cmp     eax, 2
0x18000387e  jnz     short loc_1800038AC
0x180003880  lea     r8, [rbp+arg_10]; unsigned int *
0x180003884  mov     dword ptr [rbp+arg_10], edi
0x180003887  mov     rcx, rbx; struct IFunctionInstance *
0x18000388a  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAI@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,uint *)
0x18000388f  test    eax, eax
0x180003891  js      short loc_1800038A4
0x180003893  mov     eax, dword ptr [rbp+arg_10]
0x180003896  add     eax, 0FFFFFFFEh
0x180003899  test    eax, 0FFFFFFF7h
0x18000389e  jz      loc_180003967
0x1800038a4  mov     edi, r13d
0x1800038a7  jmp     loc_180003967
0x1800038ac  mov     r8, [rbp+lpString1]; lpString1
0x1800038b0  lea     rax, aProviderMicros; "Provider\\Microsoft.Networking.SSDP"
0x1800038b7  xor     edx, edx; dwCmpFlags
0x1800038b9  mov     [rsp+50h+cchCount2], esi; cchCount2
0x1800038bd  mov     r9d, esi; cchCount1
0x1800038c0  mov     [rsp+50h+lpString2], rax; lpString2
0x1800038c5  lea     ecx, [rdx+7Fh]; Locale
0x1800038c8  call    cs:__imp_CompareStringW
0x1800038ce  cmp     eax, 2
0x1800038d1  jnz     loc_180003967
0x1800038d7  xorps   xmm0, xmm0
0x1800038da  lea     r8, [rbp+pszStr1]; struct tagPROPVARIANT *
0x1800038de  xor     eax, eax
0x1800038e0  lea     rdx, PKEY_PNPX_Types; struct _tagpropertykey *
0x1800038e7  mov     rcx, rbx; struct IFunctionInstance *
0x1800038ea  mov     [rbp+var_8], rax
0x1800038ee  movups  xmmword ptr [rbp+pszStr1], xmm0
0x1800038f2  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,tagPROPVARIANT *)
0x1800038f7  test    eax, eax
0x1800038f9  js      short loc_180003967
0x1800038fb  movzx   eax, word ptr [rbp+pszStr1]
0x1800038ff  cmp     eax, 1Fh
0x180003902  jz      short loc_180003940
0x180003904  cmp     eax, 101Fh
0x180003909  jnz     short loc_18000395D
0x18000390b  xor     esi, esi
0x18000390d  cmp     dword ptr [rbp+pszStr1+8], esi
0x180003910  jbe     short loc_18000395D
0x180003912  mov     rcx, [rbp+var_8]
0x180003916  lea     rdx, pszStr2; "urn:schemas-wifialliance-org:device:WFA"...
0x18000391d  mov     r8d, 2Dh ; '-'; nChar
0x180003923  mov     rcx, [rcx+rsi*8]; pszStr1
0x180003927  call    cs:__imp_StrCmpNICW
0x18000392d  test    eax, eax
0x18000392f  jz      short loc_18000393B
0x180003931  add     esi, r13d
0x180003934  cmp     esi, dword ptr [rbp+pszStr1+8]
0x180003937  jb      short loc_180003912
0x180003939  jmp     short loc_18000395D
0x18000393b  mov     edi, r13d
0x18000393e  jmp     short loc_18000395D
0x180003940  mov     rcx, [rbp+pszStr1+8]; pszStr1
0x180003944  lea     rdx, pszStr2; "urn:schemas-wifialliance-org:device:WFA"...
0x18000394b  mov     r8d, 2Dh ; '-'; nChar
0x180003951  call    cs:__imp_StrCmpNICW
0x180003957  test    eax, eax
0x180003959  cmovz   edi, r13d
0x18000395d  lea     rcx, [rbp+pszStr1]; pvar
0x180003961  call    cs:__imp_PropVariantClear
0x180003967  mov     rcx, [rbp+lpString1]; pv
0x18000396b  call    cs:__imp_CoTaskMemFree
0x180003971  mov     rcx, [rbp+pv]; pv
0x180003975  call    cs:__imp_CoTaskMemFree
0x18000397b  test    edi, edi
0x18000397d  jz      short loc_180003984
0x18000397f  mov     eax, r13d
0x180003982  jmp     short loc_1800039B1
0x180003984  test    r14d, r14d
0x180003987  jz      short loc_1800039A6
0x180003989  cmp     r14d, r13d
0x18000398c  jnz     short loc_18000399B
0x18000398e  mov     rdx, rbx; struct IFunctionInstance *
0x180003991  mov     rcx, r15; this
0x180003994  call    ?_HandleDeviceRemove@CNetworkItemFactory@@AEAAJPEAUIFunctionInstance@@@Z; CNetworkItemFactory::_HandleDeviceRemove(IFunctionInstance *)
0x180003999  jmp     short loc_1800039B1
0x18000399b  mov     eax, 80070057h
0x1800039a0  cmp     r14d, 2
0x1800039a4  jnz     short loc_1800039B1
0x1800039a6  mov     rdx, rbx; struct IFunctionInstance *
0x1800039a9  mov     rcx, r15; this
0x1800039ac  call    ?_HandleDeviceAdd@CNetworkItemFactory@@AEAAJPEAUIFunctionInstance@@@Z; CNetworkItemFactory::_HandleDeviceAdd(IFunctionInstance *)
0x1800039b1  lea     r11, [rsp+50h+var_s0]
0x1800039b6  mov     rbx, [r11+30h]
0x1800039ba  mov     rsi, [r11+38h]
0x1800039be  mov     rsp, r11
0x1800039c1  pop     r15
0x1800039c3  pop     r14
0x1800039c5  pop     r13
0x1800039c7  pop     rdi
0x1800039c8  pop     rbp
0x1800039c9  retn
```
