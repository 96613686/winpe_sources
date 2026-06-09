# CCredUIBrokerBase::_CreateUniqueEventName(void)

- ea: `0x140017b60`
- end: `0x140017c22`
- name: `?_CreateUniqueEventName@CCredUIBrokerBase@@AEAAJXZ`
- size: `194`
- prototype: `HRESULT __fastcall(CCredUIBrokerBase *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400182c8`

## callees

- `0x140003620`
- `0x140007218`
- `0x1400163c8`
- `0x140017b60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x140017b8f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x140017b8f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140017ba9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140017ba9`

## pseudocode

```c
HRESULT __fastcall CCredUIBrokerBase::_CreateUniqueEventName(CCredUIBrokerBase *this)
{
  HRESULT result; // eax
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r9
  GUID pguid; // [rsp+30h] [rbp-1A8h] BYREF
  OLECHAR sz[64]; // [rsp+40h] [rbp-198h] BYREF
  unsigned __int16 v7[128]; // [rsp+C0h] [rbp-118h] BYREF

  pguid = 0;
  result = CoCreateGuid(&pguid);
  if ( result >= 0 )
  {
    result = StringFromGUID2(&pguid, sz, 64);
    if ( result >= 0 )
    {
      result = StringCchPrintfW(v7, 0x80u, L"Local\\AbortEvent-%s", sz);
      if ( result >= 0 )
      {
        v4 = -1;
        do
          ++v4;
        while ( v7[v4] );
        return _AllocStringWorker<CTCoAllocPolicy>(v3, v2, v7);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140017b60  mov     [rsp+arg_8], rbx
0x140017b65  push    rdi
0x140017b66  sub     rsp, 1D0h
0x140017b6d  mov     rax, cs:__security_cookie
0x140017b74  xor     rax, rsp
0x140017b77  mov     [rsp+1D8h+var_18], rax
0x140017b7f  mov     rbx, rcx
0x140017b82  xorps   xmm0, xmm0
0x140017b85  lea     rcx, [rsp+1D8h+pguid]; pguid
0x140017b8a  movups  xmmword ptr [rsp+1D8h+pguid.Data1], xmm0
0x140017b8f  call    cs:__imp_CoCreateGuid
0x140017b95  xor     edi, edi
0x140017b97  test    eax, eax
0x140017b99  js      short loc_140017C01
0x140017b9b  lea     r8d, [rdi+40h]; cchMax
0x140017b9f  lea     rdx, [rsp+1D8h+sz]; lpsz
0x140017ba4  lea     rcx, [rsp+1D8h+pguid]; rguid
0x140017ba9  call    cs:__imp_StringFromGUID2
0x140017baf  test    eax, eax
0x140017bb1  js      short loc_140017C01
0x140017bb3  lea     r9, [rsp+1D8h+sz]
0x140017bb8  mov     edx, 80h; unsigned __int64
0x140017bbd  lea     r8, aLocalAborteven; "Local\\AbortEvent-%s"
0x140017bc4  lea     rcx, [rsp+1D8h+var_118]; unsigned __int16 *
0x140017bcc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140017bd1  test    eax, eax
0x140017bd3  js      short loc_140017C01
0x140017bd5  lea     rax, [rsp+1D8h+var_118]
0x140017bdd  or      r9, 0FFFFFFFFFFFFFFFFh
0x140017be1  inc     r9
0x140017be4  cmp     [rax+r9*2], di
0x140017be9  jnz     short loc_140017BE1
0x140017beb  lea     rax, [rbx+38h]
0x140017bef  lea     r8, [rsp+1D8h+var_118]
0x140017bf7  mov     [rsp+1D8h+var_1B0], rax
0x140017bfc  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x140017c01  mov     rcx, [rsp+1D8h+var_18]
0x140017c09  xor     rcx, rsp; StackCookie
0x140017c0c  call    __security_check_cookie
0x140017c11  mov     rbx, [rsp+1D8h+arg_8]
0x140017c19  add     rsp, 1D0h
0x140017c20  pop     rdi
0x140017c21  retn
```
