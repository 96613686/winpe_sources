# CSubscription::put_SubscriberCLSID(ushort *)

- ea: `0x180033490`
- end: `0x1800335a9`
- name: `?put_SubscriberCLSID@CSubscription@@UEAAJPEAG@Z`
- size: `281`
- prototype: `int(CSubscription *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008938`
- `0x1800164f0`
- `0x180033490`
- `0x18003ecb0`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033513`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033513`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003352c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003352c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800334f0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800334f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003357c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003357c`

## string_xrefs

- `0x18003354e`: `com\complus\src\events\tier1\subscription.cpp`

## pseudocode

```c
__int64 __fastcall CSubscription::put_SubscriberCLSID(CSubscription *this, unsigned __int16 *a2)
{
  char v3; // bl
  HRESULT v5; // [rsp+20h] [rbp-38h]
  LPOLESTR lpsz; // [rsp+28h] [rbp-30h] BYREF
  GUID pclsid; // [rsp+30h] [rbp-28h] BYREF

  if ( !a2 || (v3 = 1, !*a2) )
    v3 = 0;
  pclsid = 0;
  if ( !v3 )
    goto LABEL_9;
  if ( *((_QWORD *)this + 59) )
    return 2147942487LL;
  if ( CLSIDFromString(a2, &pclsid) < 0 )
    return 2147942487LL;
LABEL_9:
  PropVariantClear((PROPVARIANT *)this + 20);
  if ( v3 )
  {
    lpsz = 0;
    v5 = StringFromCLSID(&pclsid, &lpsz);
    if ( v5 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x425u, 0x10u, v5);
    *((_WORD *)this + 80) = 8;
    SetBSTR((unsigned __int16 **)this + 21, lpsz);
    CoTaskMemFree(lpsz);
  }
  return 0;
}

```

## disassembly

```asm
0x180033490  mov     [rsp+arg_10], rbx
0x180033495  mov     [rsp+arg_18], rsi
0x18003349a  push    rdi
0x18003349b  sub     rsp, 50h
0x18003349f  mov     rax, cs:__security_cookie
0x1800334a6  xor     rax, rsp
0x1800334a9  mov     [rsp+58h+var_18], rax
0x1800334ae  mov     rax, rdx
0x1800334b1  mov     rdi, rcx
0x1800334b4  xor     esi, esi
0x1800334b6  mov     [rsp+58h+var_38], esi
0x1800334ba  test    rax, rax
0x1800334bd  jz      short loc_1800334C6
0x1800334bf  cmp     [rdx], si
0x1800334c2  mov     bl, 1
0x1800334c4  jnz     short loc_1800334C9
0x1800334c6  mov     bl, sil
0x1800334c9  xorps   xmm0, xmm0
0x1800334cc  movups  xmmword ptr [rsp+58h+pclsid.Data1], xmm0
0x1800334d1  test    bl, bl
0x1800334d3  jz      short loc_18003350C
0x1800334d5  cmp     [rcx+1D8h], rsi
0x1800334dc  jz      short loc_1800334E8
0x1800334de  mov     eax, 80070057h
0x1800334e3  jmp     loc_18003358C
0x1800334e8  lea     rdx, [rsp+58h+pclsid]; pclsid
0x1800334ed  mov     rcx, rax; lpsz
0x1800334f0  call    cs:__imp_CLSIDFromString
0x1800334f6  mov     [rsp+58h+var_38], eax
0x1800334fa  mov     eax, [rsp+58h+var_38]
0x1800334fe  test    eax, eax
0x180033500  jns     short loc_18003350C
0x180033502  mov     eax, 80070057h
0x180033507  jmp     loc_18003358C
0x18003350c  lea     rcx, [rdi+0A0h]; pvar
0x180033513  call    cs:__imp_PropVariantClear
0x180033519  test    bl, bl
0x18003351b  jz      short loc_180033582
0x18003351d  mov     [rsp+58h+lpsz], rsi
0x180033522  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x180033527  lea     rcx, [rsp+58h+pclsid]; rclsid
0x18003352c  call    cs:__imp_StringFromCLSID
0x180033532  mov     [rsp+58h+var_38], eax
0x180033536  mov     eax, [rsp+58h+var_38]
0x18003353a  test    eax, eax
0x18003353c  jns     short loc_18003355A
0x18003353e  mov     r8d, 10h; unsigned __int16
0x180033544  mov     r9d, [rsp+58h+var_38]; int
0x180033549  mov     edx, 425h; unsigned int
0x18003354e  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x180033555  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18003355a  mov     eax, 8
0x18003355f  mov     [rdi+0A0h], ax
0x180033566  lea     rcx, [rdi+0A8h]; unsigned __int16 **
0x18003356d  mov     rdx, [rsp+58h+lpsz]; unsigned __int16 *
0x180033572  call    ?SetBSTR@@YAJAEAPEAGPEBG@Z; SetBSTR(ushort * &,ushort const *)
0x180033577  mov     rcx, [rsp+58h+lpsz]; pv
0x18003357c  call    cs:__imp_CoTaskMemFree
0x180033582  mov     [rsp+58h+var_38], esi
0x180033586  jmp     short $+2
0x180033588  mov     eax, [rsp+58h+var_38]
0x18003358c  mov     rcx, [rsp+58h+var_18]
0x180033591  xor     rcx, rsp; StackCookie
0x180033594  call    __security_check_cookie
0x180033599  mov     rbx, [rsp+58h+arg_10]
0x18003359e  mov     rsi, [rsp+58h+arg_18]
0x1800335a3  add     rsp, 50h
0x1800335a7  pop     rdi
0x1800335a8  retn
0x18004572a  push    rbp
0x18004572c  sub     rsp, 20h
0x180045730  mov     rbp, rdx
0x180045733  lea     rdx, [rbp+20h]; int *
0x180045737  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z
0x18004573c  nop
0x18004573d  add     rsp, 20h
0x180045741  pop     rbp
0x180045742  retn
```
