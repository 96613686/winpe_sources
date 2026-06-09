# EnterpriseFeatureControl::GetProcessEnvName(ulong,ushort * *)

- ea: `0x180032834`
- end: `0x1800328e7`
- name: `?GetProcessEnvName@EnterpriseFeatureControl@@CAJKPEAPEAG@Z`
- size: `179`
- prototype: `static int(unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800325c8`
- `0x1800359e4`

## callees

- `0x1800183f4`
- `0x180029948`
- `0x180032834`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800328c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800328c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800328ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800328ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032871`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032871`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::GetProcessEnvName(__int64 a1, LPVOID *a2)
{
  DWORD CurrentProcessId; // eax
  int v5; // eax
  unsigned int v6; // edi
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPVOID lpMem; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    lpMem = 0;
    CurrentProcessId = GetCurrentProcessId();
    v5 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           &lpMem,
           L"EFC_%lu_%lu",
           CurrentProcessId,
           4143551629LL);
    v6 = v5;
    if ( v5 >= 0 )
    {
      *a2 = lpMem;
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)(unsigned int)v5,
        v9);
      v7 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v7);
      }
      return v6;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)0x80004003LL,
      v9);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180032834  mov     [rsp+arg_0], rbx
0x180032839  push    rdi; int
0x18003283a  sub     rsp, 20h
0x18003283e  mov     rbx, rdx
0x180032841  test    rdx, rdx
0x180032844  jnz     short loc_180032868
0x180032846  mov     rcx, [rsp+28h]; this
0x18003284b  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180032852  mov     ebx, 80004003h
0x180032857  mov     edx, 22h ; '"'; void *
0x18003285c  mov     r9d, ebx; char *
0x18003285f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032864  mov     eax, ebx
0x180032866  jmp     short loc_1800328DC
0x180032868  mov     [rsp+28h+lpMem], 0
0x180032871  call    cs:__imp_GetCurrentProcessId
0x180032877  mov     r9d, 0F6F9948Dh
0x18003287d  lea     rdx, aEfcLuLu; "EFC_%lu_%lu"
0x180032884  mov     r8d, eax
0x180032887  lea     rcx, [rsp+28h+lpMem]
0x18003288c  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180032891  mov     edi, eax
0x180032893  test    eax, eax
0x180032895  jns     short loc_1800328D2
0x180032897  mov     rcx, [rsp+28h]; this
0x18003289c  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800328a3  mov     r9d, eax; char *
0x1800328a6  mov     edx, 26h ; '&'; void *
0x1800328ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800328b0  mov     rbx, [rsp+28h+lpMem]
0x1800328b5  test    rbx, rbx
0x1800328b8  jz      short loc_1800328CE
0x1800328ba  call    cs:__imp_GetProcessHeap
0x1800328c0  mov     r8, rbx; lpMem
0x1800328c3  xor     edx, edx; dwFlags
0x1800328c5  mov     rcx, rax; hHeap
0x1800328c8  call    cs:__imp_HeapFree
0x1800328ce  mov     eax, edi
0x1800328d0  jmp     short loc_1800328DC
0x1800328d2  mov     rax, [rsp+28h+lpMem]
0x1800328d7  mov     [rbx], rax
0x1800328da  xor     eax, eax
0x1800328dc  mov     rbx, [rsp+28h+arg_0]
0x1800328e1  add     rsp, 20h
0x1800328e5  pop     rdi
0x1800328e6  retn
```
