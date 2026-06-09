# CEtwLogHelper::IsProviderGuidValid(ushort const *)

- ea: `0x1800145e0`
- end: `0x1800146bd`
- name: `?IsProviderGuidValid@CEtwLogHelper@@SAJPEBG@Z`
- size: `221`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ea88`

## callees

- `0x1800011ac`
- `0x180001b90`
- `0x180006498`
- `0x1800145e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001463f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001463f`

## pseudocode

```c
__int64 __fastcall CEtwLogHelper::IsProviderGuidValid(const unsigned __int16 *a1, __int64 a2, int a3, int a4)
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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v8 = v5;
    if ( !v4 )
      v4 = &String2;
    v9 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)word_180042252,
      a3,
      a4,
      (__int64)&v9,
      (__int64)&v8);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800145e0  mov     [rsp+arg_8], rbx
0x1800145e5  push    rdi
0x1800145e6  sub     rsp, 0B0h
0x1800145ed  mov     rax, cs:__security_cookie
0x1800145f4  xor     rax, rsp
0x1800145f7  mov     [rsp+0B8h+var_18], rax
0x1800145ff  xorps   xmm0, xmm0
0x180014602  mov     rdi, rcx
0x180014605  movups  xmmword ptr [rsp+0B8h+pclsid.Data1], xmm0
0x18001460a  test    rcx, rcx
0x18001460d  jnz     short loc_180014616
0x18001460f  mov     ebx, 80070057h
0x180014614  jmp     short loc_180014657
0x180014616  mov     r9, rdi
0x180014619  lea     r8, aS; "{%s}"
0x180014620  mov     edx, 27h ; '''; unsigned __int64
0x180014625  lea     rcx, [rsp+0B8h+sz]; unsigned __int16 *
0x18001462a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001462f  mov     ebx, eax
0x180014631  test    eax, eax
0x180014633  js      short loc_180014657
0x180014635  lea     rdx, [rsp+0B8h+pclsid]; pclsid
0x18001463a  lea     rcx, [rsp+0B8h+sz]; lpsz
0x18001463f  call    cs:__imp_CLSIDFromString
0x180014646  nop     dword ptr [rax+rax+00h]
0x18001464b  mov     ebx, 80070057h
0x180014650  test    eax, eax
0x180014652  cmovs   eax, ebx
0x180014655  mov     ebx, eax
0x180014657  mov     eax, cs:dword_18004AE90
0x18001465d  cmp     eax, 5
0x180014660  jbe     short loc_180014699
0x180014662  test    rdi, rdi
0x180014665  mov     [rsp+0B8h+var_88], ebx
0x180014669  lea     rax, String2
0x180014670  cmovz   rdi, rax
0x180014674  lea     rdx, word_180042252
0x18001467b  lea     rax, [rsp+0B8h+var_88]
0x180014680  mov     [rsp+0B8h+var_80], rdi
0x180014685  mov     [rsp+0B8h+var_90], rax
0x18001468a  lea     rax, [rsp+0B8h+var_80]
0x18001468f  mov     [rsp+0B8h+var_98], rax
0x180014694  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180014699  mov     eax, ebx
0x18001469b  mov     rcx, [rsp+0B8h+var_18]
0x1800146a3  xor     rcx, rsp; StackCookie
0x1800146a6  call    __security_check_cookie
0x1800146ab  mov     rbx, [rsp+0B8h+arg_8]
0x1800146b3  add     rsp, 0B0h
0x1800146ba  pop     rdi
0x1800146bb  retn
```
