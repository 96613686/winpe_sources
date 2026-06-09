# EnterpriseFeatureControl::GetProcessEnvName(ulong,ushort * *)

- ea: `0x180017dbc`
- end: `0x180017e60`
- name: `?GetProcessEnvName@EnterpriseFeatureControl@@CAJKPEAPEAG@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180017a80`
- `0x18001bae8`

## callees

- `0x18000972c`
- `0x1800112c0`
- `0x180012940`
- `0x180017dbc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017df5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017df5`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::GetProcessEnvName(__int64 a1, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  DWORD CurrentProcessId; // eax
  int v5; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int16 *v9; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    v9 = 0;
    CurrentProcessId = GetCurrentProcessId();
    v5 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           &v9,
           L"EFC_%lu_%lu",
           CurrentProcessId,
           3024495246LL);
    v3 = v5;
    if ( v5 >= 0 )
    {
      v3 = 0;
      *a2 = v9;
      v9 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)(unsigned int)v5,
        v7);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v9);
  }
  else
  {
    v3 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)0x80004003LL,
      v7);
  }
  return v3;
}

```

## disassembly

```asm
0x180017dbc  mov     [rsp+arg_0], rbx
0x180017dc1  push    rdi; int
0x180017dc2  sub     rsp, 20h
0x180017dc6  mov     rdi, rdx
0x180017dc9  test    rdx, rdx
0x180017dcc  jnz     short loc_180017DEC
0x180017dce  mov     rcx, [rsp+28h]; this
0x180017dd3  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180017dda  mov     ebx, 80004003h
0x180017ddf  lea     edx, [rdi+22h]; void *
0x180017de2  mov     r9d, ebx; char *
0x180017de5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017dea  jmp     short loc_180017E53
0x180017dec  mov     [rsp+28h+arg_8], 0
0x180017df5  call    cs:__imp_GetCurrentProcessId
0x180017dfb  mov     r9d, 0B446228Eh
0x180017e01  lea     rdx, aEfcLuLu; "EFC_%lu_%lu"
0x180017e08  mov     r8d, eax
0x180017e0b  lea     rcx, [rsp+28h+arg_8]
0x180017e10  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180017e15  mov     ebx, eax
0x180017e17  test    eax, eax
0x180017e19  jns     short loc_180017E36
0x180017e1b  mov     rcx, [rsp+28h]; this
0x180017e20  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180017e27  mov     r9d, eax; char *
0x180017e2a  mov     edx, 26h ; '&'; void *
0x180017e2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e34  jmp     short loc_180017E49
0x180017e36  mov     rax, [rsp+28h+arg_8]
0x180017e3b  xor     ebx, ebx
0x180017e3d  mov     [rdi], rax
0x180017e40  mov     [rsp+28h+arg_8], 0
0x180017e49  lea     rcx, [rsp+28h+arg_8]
0x180017e4e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017e53  mov     eax, ebx
0x180017e55  mov     rbx, [rsp+28h+arg_0]
0x180017e5a  add     rsp, 20h
0x180017e5e  pop     rdi
0x180017e5f  retn
```
