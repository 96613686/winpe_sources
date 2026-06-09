# ShieldProvider::GetStringFromGUID(_GUID const &,ushort * *)

- ea: `0x1800ce43c`
- end: `0x1800ce4c0`
- name: `?GetStringFromGUID@ShieldProvider@@YAJAEBU_GUID@@PEAPEAG@Z`
- size: `132`
- prototype: `__int64 __fastcall(ShieldProvider *__hidden this, const struct _GUID *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000db9c`
- `0x18000dddc`
- `0x180078328`
- `0x1800bf804`
- `0x1800ce830`

## callees

- `0x180004ae0`
- `0x1800ce43c`
- `0x1800dfc38`

## import_xrefs

- `ole32!StringFromCLSID` at `0x1800ce45b`
- `ole32!StringFromCLSID` at `0x1800ce45b`
- `ole32!CoTaskMemFree` at `0x1800ce49b`
- `ole32!CoTaskMemFree` at `0x1800ce49b`

## pseudocode

```c
__int64 __fastcall ShieldProvider::GetStringFromGUID(const IID *this, const struct _GUID *a2, unsigned __int16 **a3)
{
  HRESULT v4; // edi
  const unsigned __int16 *v5; // r8
  void *v6; // rbx
  const struct std::nothrow_t *v7; // rdx
  void *v9; // [rsp+40h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+48h] [rbp+20h] BYREF

  pv = 0;
  v4 = StringFromCLSID(this, (LPOLESTR *)&pv);
  if ( v4 >= 0 )
  {
    v9 = 0;
    v4 = CommonUtil::HrDuplicateStringW((CommonUtil *)&v9, (unsigned __int16 **)pv, v5);
    if ( v4 < 0 )
    {
      v6 = v9;
    }
    else
    {
      v6 = 0;
      *(_QWORD *)&a2->Data1 = v9;
    }
    CoTaskMemFree(pv);
    if ( v6 )
      operator delete(v6, v7);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800ce43c  mov     rax, rsp
0x1800ce43f  mov     [rax+8], rbx
0x1800ce443  mov     [rax+10h], rsi
0x1800ce447  push    rdi
0x1800ce448  sub     rsp, 20h
0x1800ce44c  mov     rsi, rdx
0x1800ce44f  mov     qword ptr [rax+20h], 0
0x1800ce457  lea     rdx, [rax+20h]; lplpsz
0x1800ce45b  call    cs:__imp_StringFromCLSID
0x1800ce461  mov     edi, eax
0x1800ce463  test    eax, eax
0x1800ce465  js      short loc_1800CE4AE
0x1800ce467  mov     rdx, [rsp+28h+pv]; unsigned __int16 **
0x1800ce46c  lea     rcx, [rsp+28h+arg_10]; this
0x1800ce471  mov     [rsp+28h+arg_10], 0
0x1800ce47a  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x1800ce47f  mov     edi, eax
0x1800ce481  test    eax, eax
0x1800ce483  js      short loc_1800CE491
0x1800ce485  mov     rax, [rsp+28h+arg_10]
0x1800ce48a  xor     ebx, ebx
0x1800ce48c  mov     [rsi], rax
0x1800ce48f  jmp     short loc_1800CE496
0x1800ce491  mov     rbx, [rsp+28h+arg_10]
0x1800ce496  mov     rcx, [rsp+28h+pv]; pv
0x1800ce49b  call    cs:__imp_CoTaskMemFree
0x1800ce4a1  test    rbx, rbx
0x1800ce4a4  jz      short loc_1800CE4AE
0x1800ce4a6  mov     rcx, rbx; void *
0x1800ce4a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ce4ae  mov     rbx, [rsp+28h+arg_0]
0x1800ce4b3  mov     eax, edi
0x1800ce4b5  mov     rsi, [rsp+28h+arg_8]
0x1800ce4ba  add     rsp, 20h
0x1800ce4be  pop     rdi
0x1800ce4bf  retn
```
