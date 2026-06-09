# CSubscription::put_EventClassID(ushort *)

- ea: `0x180016aa0`
- end: `0x180016bae`
- name: `?put_EventClassID@CSubscription@@UEAAJPEAG@Z`
- size: `270`
- prototype: `int(CSubscription *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008938`
- `0x1800164f0`
- `0x180016aa0`
- `0x18003ecb0`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016b12`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016b12`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180016b2b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180016b2b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180016af2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180016af2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016b59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016b59`

## string_xrefs

- `0x180016b71`: `com\complus\src\events\tier1\subscription.cpp`

## pseudocode

```c
__int64 __fastcall CSubscription::put_EventClassID(CSubscription *this, unsigned __int16 *a2)
{
  char v3; // bl
  HRESULT v5; // [rsp+20h] [rbp-38h]
  LPOLESTR lpsz; // [rsp+28h] [rbp-30h] BYREF
  GUID pclsid; // [rsp+30h] [rbp-28h] BYREF

  if ( !a2 || (v3 = 1, !*a2) )
    v3 = 0;
  pclsid = 0;
  if ( v3 && CLSIDFromString(a2, &pclsid) < 0 )
    return 2147942487LL;
  PropVariantClear((PROPVARIANT *)this + 14);
  if ( v3 )
  {
    lpsz = 0;
    v5 = StringFromCLSID(&pclsid, &lpsz);
    if ( v5 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x3B3u, 0x10u, v5);
    *((_WORD *)this + 56) = 8;
    SetBSTR((unsigned __int16 **)this + 15, lpsz);
    CoTaskMemFree(lpsz);
  }
  return 0;
}

```

## disassembly

```asm
0x180016aa0  mov     [rsp+arg_10], rbx
0x180016aa5  mov     [rsp+arg_18], rsi
0x180016aaa  push    rdi
0x180016aab  sub     rsp, 50h
0x180016aaf  mov     rax, cs:__security_cookie
0x180016ab6  xor     rax, rsp
0x180016ab9  mov     [rsp+58h+var_18], rax
0x180016abe  mov     rax, rdx
0x180016ac1  mov     rdi, rcx
0x180016ac4  xor     esi, esi
0x180016ac6  mov     [rsp+58h+var_38], esi
0x180016aca  test    rax, rax
0x180016acd  jz      loc_180016B7F
0x180016ad3  cmp     [rdx], si
0x180016ad6  mov     bl, 1
0x180016ad8  jz      loc_180016B7F
0x180016ade  xorps   xmm0, xmm0
0x180016ae1  movups  xmmword ptr [rsp+58h+pclsid.Data1], xmm0
0x180016ae6  test    bl, bl
0x180016ae8  jz      short loc_180016B0E
0x180016aea  lea     rdx, [rsp+58h+pclsid]; pclsid
0x180016aef  mov     rcx, rax; lpsz
0x180016af2  call    cs:__imp_CLSIDFromString
0x180016af8  mov     [rsp+58h+var_38], eax
0x180016afc  mov     eax, [rsp+58h+var_38]
0x180016b00  test    eax, eax
0x180016b02  jns     short loc_180016B0E
0x180016b04  mov     eax, 80070057h
0x180016b09  jmp     loc_180016B91
0x180016b0e  lea     rcx, [rdi+70h]; pvar
0x180016b12  call    cs:__imp_PropVariantClear
0x180016b18  test    bl, bl
0x180016b1a  jz      short loc_180016B87
0x180016b1c  mov     [rsp+58h+lpsz], rsi
0x180016b21  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x180016b26  lea     rcx, [rsp+58h+pclsid]; rclsid
0x180016b2b  call    cs:__imp_StringFromCLSID
0x180016b31  mov     [rsp+58h+var_38], eax
0x180016b35  mov     eax, [rsp+58h+var_38]
0x180016b39  test    eax, eax
0x180016b3b  js      short loc_180016B61
0x180016b3d  mov     eax, 8
0x180016b42  mov     [rdi+70h], ax
0x180016b46  lea     rcx, [rdi+78h]; unsigned __int16 **
0x180016b4a  mov     rdx, [rsp+58h+lpsz]; unsigned __int16 *
0x180016b4f  call    ?SetBSTR@@YAJAEAPEAGPEBG@Z; SetBSTR(ushort * &,ushort const *)
0x180016b54  mov     rcx, [rsp+58h+lpsz]; pv
0x180016b59  call    cs:__imp_CoTaskMemFree
0x180016b5f  jmp     short loc_180016B87
0x180016b61  mov     r8d, 10h; unsigned __int16
0x180016b67  mov     r9d, [rsp+58h+var_38]; int
0x180016b6c  mov     edx, 3B3h; unsigned int
0x180016b71  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x180016b78  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180016b7d  jmp     short loc_180016B3D
0x180016b7f  mov     bl, sil
0x180016b82  jmp     loc_180016ADE
0x180016b87  mov     [rsp+58h+var_38], esi
0x180016b8b  jmp     short $+2
0x180016b8d  mov     eax, [rsp+58h+var_38]
0x180016b91  mov     rcx, [rsp+58h+var_18]
0x180016b96  xor     rcx, rsp; StackCookie
0x180016b99  call    __security_check_cookie
0x180016b9e  mov     rbx, [rsp+58h+arg_10]
0x180016ba3  mov     rsi, [rsp+58h+arg_18]
0x180016ba8  add     rsp, 50h
0x180016bac  pop     rdi
0x180016bad  retn
0x18004451f  push    rbp
0x180044521  sub     rsp, 20h
0x180044525  mov     rbp, rdx
0x180044528  lea     rdx, [rbp+20h]; int *
0x18004452c  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180044531  nop
0x180044532  add     rsp, 20h
0x180044536  pop     rbp
0x180044537  retn
```
