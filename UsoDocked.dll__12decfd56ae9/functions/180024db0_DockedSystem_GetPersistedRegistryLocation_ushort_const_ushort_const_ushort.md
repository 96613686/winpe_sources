# DockedSystem::GetPersistedRegistryLocation(ushort const *,ushort const *,ushort * *)

- ea: `0x180024db0`
- end: `0x180024ece`
- name: `?GetPersistedRegistryLocation@DockedSystem@@UEAAJPEBG0PEAPEAG@Z`
- size: `286`
- prototype: `int(DockedSystem *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180007660`
- `0x18000856c`
- `0x1800183f4`
- `0x180023a34`
- `0x180024db0`
- `0x180025614`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180024e75`
- `OLEAUT32!__imp_SysAllocString` at `0x180024e75`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180024e37`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180024e37`

## string_xrefs

- `0x180024ebb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180024df3`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180024e5d`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall DockedSystem::GetPersistedRegistryLocation(
        DockedSystem *this,
        const char *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned int PersistedRegistryLocationW; // eax
  unsigned __int16 *v9; // rax
  const char *v10; // r9
  int v11; // [rsp+20h] [rbp-248h]
  OLECHAR psz[256]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  if ( a4 )
  {
    memset_0(psz, 0, sizeof(psz));
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(a2, a3, psz, 256);
    if ( PersistedRegistryLocationW )
    {
      return wil::details::in1diag3::Return_Win32Msg(
               retaddr,
               (void *)0x5B,
               (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
               (const char *)PersistedRegistryLocationW,
               (unsigned int)"%ws",
               a2,
               0);
    }
    else
    {
      v9 = SysAllocString(psz);
      if ( !v9 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x15F3,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v10);
      *a4 = v9;
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
      (const char *)0x80004003LL,
      v11);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180024db0  push    rbx
0x180024db2  push    rsi
0x180024db3  push    rdi
0x180024db4  sub     rsp, 250h
0x180024dbb  mov     rax, cs:__security_cookie
0x180024dc2  xor     rax, rsp
0x180024dc5  mov     [rsp+268h+var_28], rax
0x180024dcd  mov     rbx, r9
0x180024dd0  mov     rsi, r8
0x180024dd3  mov     rdi, rdx
0x180024dd6  mov     [rsp+268h+var_238], 0
0x180024dde  test    rbx, rbx
0x180024de1  jnz     short loc_180024E0B
0x180024de3  mov     rcx, [rsp+268h]; this
0x180024deb  mov     ebx, 80004003h
0x180024df0  mov     r9d, ebx; char *
0x180024df3  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024dfa  mov     edx, 57h ; 'W'; void *
0x180024dff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024e04  mov     eax, ebx
0x180024e06  jmp     loc_180024EA0
0x180024e0b  xor     edx, edx; Val
0x180024e0d  mov     r8d, 200h; Size
0x180024e13  lea     rcx, [rsp+268h+psz]; void *
0x180024e18  call    memset_0
0x180024e1d  mov     qword ptr [rsp+268h+var_248], 0
0x180024e26  mov     r9d, 100h
0x180024e2c  lea     r8, [rsp+268h+psz]
0x180024e31  mov     rdx, rsi
0x180024e34  mov     rcx, rdi
0x180024e37  call    cs:__imp_GetPersistedRegistryLocationW
0x180024e3d  test    eax, eax
0x180024e3f  jz      short loc_180024E70
0x180024e41  mov     rcx, [rsp+268h]; this
0x180024e49  mov     [rsp+268h+var_240], rdi; char *
0x180024e4e  lea     rdx, aWs; "%ws"
0x180024e55  mov     qword ptr [rsp+268h+var_248], rdx; unsigned int
0x180024e5a  mov     r9d, eax; char *
0x180024e5d  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024e64  mov     edx, 5Bh ; '['; void *
0x180024e69  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180024e6e  jmp     short loc_180024EA0
0x180024e70  lea     rcx, [rsp+268h+psz]; psz
0x180024e75  call    cs:__imp_SysAllocString
0x180024e7b  mov     [rsp+268h+var_230], rax
0x180024e80  mov     [rsp+268h+var_238], 1
0x180024e88  mov     rcx, [rsp+268h]; this
0x180024e90  test    rax, rax
0x180024e93  jz      short loc_180024EBB
0x180024e95  mov     [rbx], rax
0x180024e98  xor     eax, eax
0x180024e9a  jmp     short loc_180024EA0
0x180024e9c  mov     eax, [rsp+268h+var_238]
0x180024ea0  mov     rcx, [rsp+268h+var_28]
0x180024ea8  xor     rcx, rsp; StackCookie
0x180024eab  call    __security_check_cookie
0x180024eb0  add     rsp, 250h
0x180024eb7  pop     rdi
0x180024eb8  pop     rsi
0x180024eb9  pop     rbx
0x180024eba  retn
0x180024ebb  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024ec2  mov     edx, 15F3h; void *
0x180024ec7  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
