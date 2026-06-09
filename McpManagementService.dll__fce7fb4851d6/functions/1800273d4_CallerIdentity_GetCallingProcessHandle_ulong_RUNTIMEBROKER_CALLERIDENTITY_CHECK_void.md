# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x1800273d4`
- end: `0x180027483`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `175`
- prototype: `__int64 __fastcall(__int64, __int64, HANDLE *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008f84`
- `0x180027324`
- `0x1800273b4`

## callees

- `0x18000c4cc`
- `0x1800273d4`
- `0x18002748c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180027407`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180027407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002743c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002743c`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCallingProcessHandle(__int64 a1, __int64 a2, HANDLE *a3)
{
  HRESULT v4; // eax
  int v5; // ebx
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *ppInterface; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  ppInterface = 0;
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&ppInterface, a2);
  v4 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(ppInterface, 4096, a3);
    if ( v5 < 0 )
      goto LABEL_8;
LABEL_6:
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&ppInterface, v6);
    return 0;
  }
  if ( v4 == -2147417833 )
  {
    *a3 = GetCurrentProcess();
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x58,
    (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
    (const char *)(unsigned int)v4,
    v8);
LABEL_8:
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&ppInterface, v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800273d4  mov     [rsp+arg_0], rbx
0x1800273d9  push    rdi; int
0x1800273da  sub     rsp, 20h
0x1800273de  lea     rcx, [rsp+28h+ppInterface]
0x1800273e3  mov     qword ptr [r8], 0
0x1800273ea  mov     rdi, r8
0x1800273ed  mov     [rsp+28h+ppInterface], 0
0x1800273f6  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800273fb  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x180027400  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x180027407  call    cs:__imp_CoGetCallContext
0x18002740d  mov     ebx, eax
0x18002740f  test    eax, eax
0x180027411  js      short loc_180027434
0x180027413  mov     rcx, [rsp+28h+ppInterface]
0x180027418  mov     r8, rdi
0x18002741b  mov     edx, 1000h
0x180027420  mov     rax, [rcx]
0x180027423  mov     rax, [rax+18h]
0x180027427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002742c  mov     ebx, eax
0x18002742e  test    eax, eax
0x180027430  jns     short loc_180027445
0x180027432  jmp     short loc_18002746C
0x180027434  cmp     ebx, 80010117h
0x18002743a  jnz     short loc_180027453
0x18002743c  call    cs:__imp_GetCurrentProcess
0x180027442  mov     [rdi], rax
0x180027445  lea     rcx, [rsp+28h+ppInterface]
0x18002744a  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18002744f  xor     eax, eax
0x180027451  jmp     short loc_180027478
0x180027453  mov     rcx, [rsp+28h]; this
0x180027458  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18002745f  mov     r9d, ebx; char *
0x180027462  mov     edx, 58h ; 'X'; void *
0x180027467  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002746c  lea     rcx, [rsp+28h+ppInterface]
0x180027471  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180027476  mov     eax, ebx
0x180027478  mov     rbx, [rsp+28h+arg_0]
0x18002747d  add     rsp, 20h
0x180027481  pop     rdi
0x180027482  retn
```
