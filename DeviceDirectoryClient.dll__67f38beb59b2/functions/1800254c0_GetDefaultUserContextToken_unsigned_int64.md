# _GetDefaultUserContextToken(unsigned __int64 *)

- ea: `0x1800254c0`
- end: `0x180025558`
- name: `?_GetDefaultUserContextToken@@YAJPEA_K@Z`
- size: `152`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180024954`

## callees

- `0x18000d08c`
- `0x18002475c`
- `0x1800247bc`
- `0x1800254c0`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180025518`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180025518`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x1800254f0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x1800254f0`

## string_xrefs

- `0x180025531`: `onecoreuap\private\base\inc\CreateWpnSystemPlatform.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _GetDefaultUserContextToken(unsigned __int64 *a1)
{
  int v2; // ebx
  unsigned __int64 v3; // r9
  __int64 v4; // rdx
  int UserContext; // eax
  __int64 *v7; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+28h] [rbp-20h] BYREF
  char v9; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF

  v8 = 0;
  v7 = &v11;
  v9 = 1;
  v11 = 0;
  v2 = UMgrQueryDefaultAccountToken(&v8);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v7);
  if ( v2 >= 0 )
  {
    UserContext = UMgrQueryUserContext(v11, a1);
    v2 = UserContext;
    if ( UserContext >= 0 )
    {
      v2 = 0;
      goto LABEL_7;
    }
    v3 = (unsigned int)UserContext;
    v4 = 17;
  }
  else
  {
    v3 = (unsigned int)v2;
    v4 = 16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\private\\base\\inc\\CreateWpnSystemPlatform.h",
    (const char *)v3,
    (int)v7);
LABEL_7:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800254c0  mov     r11, rsp
0x1800254c3  mov     [r11+8], rbx
0x1800254c7  push    rdi
0x1800254c8  sub     rsp, 40h
0x1800254cc  lea     rax, [r11+10h]
0x1800254d0  mov     qword ptr [r11-20h], 0
0x1800254d8  mov     rdi, rcx
0x1800254db  mov     [r11-28h], rax
0x1800254df  lea     rcx, [r11-20h]
0x1800254e3  mov     [rsp+48h+var_18], 1
0x1800254e8  mov     qword ptr [r11+10h], 0
0x1800254f0  call    cs:__imp_UMgrQueryDefaultAccountToken
0x1800254f6  lea     rcx, [rsp+48h+var_28]
0x1800254fb  mov     ebx, eax
0x1800254fd  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180025502  test    ebx, ebx
0x180025504  jns     short loc_180025510
0x180025506  mov     r9d, ebx
0x180025509  mov     edx, 10h
0x18002550e  jmp     short loc_18002552C
0x180025510  mov     rcx, [rsp+48h+arg_8]
0x180025515  mov     rdx, rdi
0x180025518  call    cs:__imp_UMgrQueryUserContext
0x18002551e  mov     ebx, eax
0x180025520  test    eax, eax
0x180025522  jns     short loc_18002553F
0x180025524  mov     r9d, eax; char *
0x180025527  mov     edx, 11h; void *
0x18002552c  mov     rcx, [rsp+48h]; this
0x180025531  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\base\\inc\\CreateW"...
0x180025538  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002553d  jmp     short loc_180025541
0x18002553f  xor     ebx, ebx
0x180025541  lea     rcx, [rsp+48h+arg_8]
0x180025546  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002554b  mov     eax, ebx
0x18002554d  mov     rbx, [rsp+48h+arg_0]
0x180025552  add     rsp, 40h
0x180025556  pop     rdi
0x180025557  retn
```
