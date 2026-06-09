# CSubscription::put_InterfaceID(ushort *)

- ea: `0x180016c60`
- end: `0x180016da5`
- name: `?put_InterfaceID@CSubscription@@UEAAJPEAG@Z`
- size: `325`
- prototype: `int(CSubscription *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180008938`
- `0x1800164f0`
- `0x180016c60`
- `0x18003ecb0`
- `0x1800434ae`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016d0a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016d0a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180016d24`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180016d24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d58`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180016ca9`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180016ca9`

## string_xrefs

- `0x180016d70`: `com\complus\src\events\tier1\subscription.cpp`

## pseudocode

```c
__int64 __fastcall CSubscription::put_InterfaceID(CSubscription *this, unsigned __int16 *a2)
{
  char v4; // di
  HRESULT v5; // [rsp+20h] [rbp-38h]
  LPOLESTR lpsz[2]; // [rsp+28h] [rbp-30h] BYREF
  GUID iid; // [rsp+38h] [rbp-20h] BYREF

  iid = 0;
  if ( a2 && *a2 )
  {
    *(_OWORD *)lpsz = 0;
    if ( IIDFromString(a2, &iid) < 0 )
      return 2147942487LL;
    if ( !memcmp_0(&iid, &IID_IUnknown, 0x10u) )
      return 2147942487LL;
    v4 = 1;
    if ( !memcmp_0(&iid, &IID_IDispatch, 0x10u) )
      return 2147942487LL;
  }
  else
  {
    v4 = 0;
  }
  PropVariantClear((PROPVARIANT *)this + 38);
  if ( v4 )
  {
    lpsz[0] = 0;
    v5 = StringFromCLSID(&iid, lpsz);
    if ( v5 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x630u, 0x10u, v5);
    *((_WORD *)this + 152) = 8;
    SetBSTR((unsigned __int16 **)this + 39, lpsz[0]);
    CoTaskMemFree(lpsz[0]);
  }
  return 0;
}

```

## disassembly

```asm
0x180016c60  mov     [rsp+arg_10], rbx
0x180016c65  mov     [rsp+arg_18], rsi
0x180016c6a  push    rdi
0x180016c6b  sub     rsp, 50h
0x180016c6f  mov     rax, cs:__security_cookie
0x180016c76  xor     rax, rsp
0x180016c79  mov     [rsp+58h+var_10], rax
0x180016c7e  mov     rax, rdx
0x180016c81  mov     rbx, rcx
0x180016c84  xor     esi, esi
0x180016c86  mov     [rsp+58h+var_38], esi
0x180016c8a  xorps   xmm0, xmm0
0x180016c8d  movups  xmmword ptr [rsp+58h+iid.Data1], xmm0
0x180016c92  test    rax, rax
0x180016c95  jz      short loc_180016D00
0x180016c97  cmp     [rdx], si
0x180016c9a  jz      short loc_180016D00
0x180016c9c  movups  xmmword ptr [rsp+58h+lpsz], xmm0
0x180016ca1  lea     rdx, [rsp+58h+iid]; lpiid
0x180016ca6  mov     rcx, rax; lpsz
0x180016ca9  call    cs:__imp_IIDFromString
0x180016caf  test    eax, eax
0x180016cb1  js      short loc_180016CD6
0x180016cb3  lea     r8d, [rsi+10h]; Size
0x180016cb7  lea     rdx, IID_IUnknown; Buf2
0x180016cbe  lea     rcx, [rsp+58h+iid]; Buf1
0x180016cc3  call    memcmp_0
0x180016cc8  test    eax, eax
0x180016cca  jnz     short loc_180016CE0
0x180016ccc  mov     eax, 80070057h
0x180016cd1  jmp     loc_180016D88
0x180016cd6  mov     eax, 80070057h
0x180016cdb  jmp     loc_180016D88
0x180016ce0  mov     dil, 1
0x180016ce3  mov     r8d, 10h; Size
0x180016ce9  lea     rdx, IID_IDispatch; Buf2
0x180016cf0  lea     rcx, [rsp+58h+iid]; Buf1
0x180016cf5  call    memcmp_0
0x180016cfa  test    eax, eax
0x180016cfc  jnz     short loc_180016D03
0x180016cfe  jmp     short loc_180016CCC
0x180016d00  mov     dil, sil
0x180016d03  lea     rcx, [rbx+130h]; pvar
0x180016d0a  call    cs:__imp_PropVariantClear
0x180016d10  test    dil, dil
0x180016d13  jz      short loc_180016D7E
0x180016d15  mov     [rsp+58h+lpsz], rsi
0x180016d1a  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x180016d1f  lea     rcx, [rsp+58h+iid]; rclsid
0x180016d24  call    cs:__imp_StringFromCLSID
0x180016d2a  mov     [rsp+58h+var_38], eax
0x180016d2e  mov     eax, [rsp+58h+var_38]
0x180016d32  test    eax, eax
0x180016d34  js      short loc_180016D60
0x180016d36  mov     eax, 8
0x180016d3b  mov     [rbx+130h], ax
0x180016d42  lea     rcx, [rbx+138h]; unsigned __int16 **
0x180016d49  mov     rdx, [rsp+58h+lpsz]; unsigned __int16 *
0x180016d4e  call    ?SetBSTR@@YAJAEAPEAGPEBG@Z; SetBSTR(ushort * &,ushort const *)
0x180016d53  mov     rcx, [rsp+58h+lpsz]; pv
0x180016d58  call    cs:__imp_CoTaskMemFree
0x180016d5e  jmp     short loc_180016D7E
0x180016d60  mov     r8d, 10h; unsigned __int16
0x180016d66  mov     r9d, [rsp+58h+var_38]; int
0x180016d6b  mov     edx, 630h; unsigned int
0x180016d70  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x180016d77  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180016d7c  jmp     short loc_180016D36
0x180016d7e  mov     [rsp+58h+var_38], esi
0x180016d82  jmp     short $+2
0x180016d84  mov     eax, [rsp+58h+var_38]
0x180016d88  mov     rcx, [rsp+58h+var_10]
0x180016d8d  xor     rcx, rsp; StackCookie
0x180016d90  call    __security_check_cookie
0x180016d95  mov     rbx, [rsp+58h+arg_10]
0x180016d9a  mov     rsi, [rsp+58h+arg_18]
0x180016d9f  add     rsp, 50h
0x180016da3  pop     rdi
0x180016da4  retn
0x18004455f  push    rbp
0x180044561  sub     rsp, 20h
0x180044565  mov     rbp, rdx
0x180044568  lea     rdx, [rbp+20h]; int *
0x18004456c  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180044571  nop
0x180044572  add     rsp, 20h
0x180044576  pop     rbp
0x180044577  retn
```
