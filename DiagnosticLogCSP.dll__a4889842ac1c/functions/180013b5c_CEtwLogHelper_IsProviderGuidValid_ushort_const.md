# CEtwLogHelper::IsProviderGuidValid(ushort const *)

- ea: `0x180013b5c`
- end: `0x180013c32`
- name: `?IsProviderGuidValid@CEtwLogHelper@@SAJPEBG@Z`
- size: `214`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e374`

## callees

- `0x1800011a4`
- `0x180001b60`
- `0x180006518`
- `0x180013b5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180013bbb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180013bbb`

## pseudocode

```c
__int64 __fastcall CEtwLogHelper::IsProviderGuidValid(const unsigned __int16 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  const WCHAR *v4; // rdi
  int v5; // ebx
  HRESULT v6; // eax
  int v8; // [rsp+30h] [rbp-88h] BYREF
  const WCHAR *v9; // [rsp+38h] [rbp-80h] BYREF
  GUID pclsid; // [rsp+40h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-68h] BYREF

  v4 = a1;
  pclsid = 0;
  if ( a1 )
  {
    v5 = StringCchPrintfW(sz, 0x27u, L"{%s}", a1);
    if ( v5 >= 0 )
    {
      v6 = CLSIDFromString(sz, &pclsid);
      if ( v6 < 0 )
        v6 = -2147024809;
      v5 = v6;
    }
  }
  else
  {
    v5 = -2147024809;
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v8 = v5;
    if ( !v4 )
      v4 = &String2;
    v9 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)word_180040252,
      a3,
      a4,
      &v9,
      (__int64)&v8);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013b5c  mov     [rsp+arg_8], rbx
0x180013b61  push    rdi
0x180013b62  sub     rsp, 0B0h
0x180013b69  mov     rax, cs:__security_cookie
0x180013b70  xor     rax, rsp
0x180013b73  mov     [rsp+0B8h+var_18], rax
0x180013b7b  xorps   xmm0, xmm0
0x180013b7e  mov     rdi, rcx
0x180013b81  movups  xmmword ptr [rsp+0B8h+pclsid.Data1], xmm0
0x180013b86  test    rcx, rcx
0x180013b89  jnz     short loc_180013B92
0x180013b8b  mov     ebx, 80070057h
0x180013b90  jmp     short loc_180013BCD
0x180013b92  mov     r9, rdi
0x180013b95  lea     r8, aS; "{%s}"
0x180013b9c  mov     edx, 27h ; '''; unsigned __int64
0x180013ba1  lea     rcx, [rsp+0B8h+sz]; unsigned __int16 *
0x180013ba6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013bab  mov     ebx, eax
0x180013bad  test    eax, eax
0x180013baf  js      short loc_180013BCD
0x180013bb1  lea     rdx, [rsp+0B8h+pclsid]; pclsid
0x180013bb6  lea     rcx, [rsp+0B8h+sz]; lpsz
0x180013bbb  call    cs:__imp_CLSIDFromString
0x180013bc1  mov     ebx, 80070057h
0x180013bc6  test    eax, eax
0x180013bc8  cmovs   eax, ebx
0x180013bcb  mov     ebx, eax
0x180013bcd  mov     eax, cs:dword_180048E90
0x180013bd3  cmp     eax, 5
0x180013bd6  jbe     short loc_180013C0F
0x180013bd8  test    rdi, rdi
0x180013bdb  mov     [rsp+0B8h+var_88], ebx
0x180013bdf  lea     rax, String2
0x180013be6  cmovz   rdi, rax
0x180013bea  lea     rdx, word_180040252
0x180013bf1  lea     rax, [rsp+0B8h+var_88]
0x180013bf6  mov     [rsp+0B8h+var_80], rdi
0x180013bfb  mov     [rsp+0B8h+var_90], rax
0x180013c00  lea     rax, [rsp+0B8h+var_80]
0x180013c05  mov     [rsp+0B8h+var_98], rax
0x180013c0a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180013c0f  mov     eax, ebx
0x180013c11  mov     rcx, [rsp+0B8h+var_18]
0x180013c19  xor     rcx, rsp; StackCookie
0x180013c1c  call    __security_check_cookie
0x180013c21  mov     rbx, [rsp+0B8h+arg_8]
0x180013c29  add     rsp, 0B0h
0x180013c30  pop     rdi
0x180013c31  retn
```
