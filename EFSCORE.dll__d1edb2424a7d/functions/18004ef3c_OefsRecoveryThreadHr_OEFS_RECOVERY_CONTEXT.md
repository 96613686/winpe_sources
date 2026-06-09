# OefsRecoveryThreadHr(_OEFS_RECOVERY_CONTEXT *)

- ea: `0x18004ef3c`
- end: `0x18004f0fc`
- name: `?OefsRecoveryThreadHr@@YAJPEAU_OEFS_RECOVERY_CONTEXT@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(struct _OEFS_RECOVERY_CONTEXT *lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ef10`

## callees

- `0x18000b12c`
- `0x18000dc68`
- `0x1800236f0`
- `0x18004ef3c`
- `0x180050e54`
- `0x180051820`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004efc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f0a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f0db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004efc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f0a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f0db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004efd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f0b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f0e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004efd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f0b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f0e9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18004efb3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18004f09b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18004f0c6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18004efb3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18004f09b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18004f0c6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18004ef86`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18004ef86`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18004f01e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18004f01e`

## string_xrefs

- `0x18004ef96`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004f075`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`

## pseudocode

```c
__int64 __fastcall OefsRecoveryThreadHr(struct _OEFS_RECOVERY_CONTEXT *lpMem)
{
  int v2; // eax
  unsigned int v3; // edi
  HANDLE ProcessHeap; // rax
  __int64 v6; // rcx
  unsigned int i; // edi
  int v8; // eax
  unsigned int v9; // esi
  ULONG v10; // eax
  __int64 v11; // r8
  HANDLE v12; // rax
  HANDLE v13; // rax
  _QWORD Parameter[4]; // [rsp+20h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v16; // [rsp+78h] [rbp+38h] BYREF
  __int64 v17; // [rsp+80h] [rbp+40h] BYREF
  __int64 v18; // [rsp+88h] [rbp+48h] BYREF

  if ( byte_1801173B1 )
    __debugbreak();
  if ( _InterlockedCompareExchange(&dword_18011739C, 1, 0) != 1 )
  {
    v17 = 0;
    v16 = 0;
    v2 = UMgrEnumerateSessionUsers(&v16, &v17);
    v3 = v2;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59C,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
        (const char *)(unsigned int)v2,
        Parameter[0]);
      if ( v17 )
        UMgrFreeSessionUsers();
      dword_18011739C = 0;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, lpMem);
      }
      return v3;
    }
    v6 = v17;
    for ( i = 0; i < v16; ++i )
    {
      if ( *(_DWORD *)(v6 + 16LL * i + 8) == *(_DWORD *)lpMem )
      {
        v18 = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v18,
          0);
        v8 = UMgrQueryUserToken(*(_QWORD *)(v17 + 16LL * i), &v18);
        v9 = v8;
        if ( v8 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5A2,
            (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
            (const char *)(unsigned int)v8,
            Parameter[0]);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
          if ( v17 )
            UMgrFreeSessionUsers();
          dword_18011739C = 0;
          v12 = GetProcessHeap();
          HeapFree(v12, 0, lpMem);
          return v9;
        }
        Parameter[1] = v18;
        Parameter[0] = 1;
        Parameter[2] = 0;
        v10 = EFSRecover(Parameter);
        if ( v10 )
          wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x5A9, v11, (const char *)v10);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
        v6 = v17;
      }
    }
    if ( v6 )
      UMgrFreeSessionUsers();
    dword_18011739C = 0;
  }
  if ( lpMem )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, lpMem);
  }
  return 0;
}

```

## disassembly

```asm
0x18004ef3c  push    rbp
0x18004ef3e  push    rbx
0x18004ef3f  push    rsi
0x18004ef40  push    rdi
0x18004ef41  push    r15
0x18004ef43  mov     rbp, rsp
0x18004ef46  sub     rsp, 40h
0x18004ef4a  cmp     cs:byte_1801173B1, 0
0x18004ef51  mov     rbx, rcx
0x18004ef54  jz      short loc_18004EF57
0x18004ef56  int     3; Trap to Debugger
0x18004ef57  xor     eax, eax
0x18004ef59  lea     r15d, [rax+1]
0x18004ef5d  lock cmpxchg cs:dword_18011739C, r15d
0x18004ef66  cmp     eax, r15d
0x18004ef69  jz      loc_18004F0D6
0x18004ef6f  lea     rdx, [rbp+arg_10]
0x18004ef73  mov     [rbp+arg_10], 0
0x18004ef7b  lea     rcx, [rbp+arg_8]
0x18004ef7f  mov     [rbp+arg_8], 0
0x18004ef86  call    cs:__imp_UMgrEnumerateSessionUsers
0x18004ef8c  mov     edi, eax
0x18004ef8e  test    eax, eax
0x18004ef90  jns     short loc_18004EFE3
0x18004ef92  mov     rcx, [rbp+28h]; this
0x18004ef96  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004ef9d  mov     r9d, eax; char *
0x18004efa0  mov     edx, 59Ch; void *
0x18004efa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004efaa  mov     rcx, [rbp+arg_10]
0x18004efae  test    rcx, rcx
0x18004efb1  jz      short loc_18004EFB9
0x18004efb3  call    cs:__imp_UMgrFreeSessionUsers
0x18004efb9  mov     cs:dword_18011739C, 0
0x18004efc3  test    rbx, rbx
0x18004efc6  jz      short loc_18004EFDC
0x18004efc8  call    cs:__imp_GetProcessHeap
0x18004efce  mov     r8, rbx; lpMem
0x18004efd1  xor     edx, edx; dwFlags
0x18004efd3  mov     rcx, rax; hHeap
0x18004efd6  call    cs:__imp_HeapFree
0x18004efdc  mov     eax, edi
0x18004efde  jmp     loc_18004F0F1
0x18004efe3  mov     rcx, [rbp+arg_10]
0x18004efe7  xor     edi, edi
0x18004efe9  cmp     edi, [rbp+arg_8]
0x18004efec  jnb     loc_18004F0C1
0x18004eff2  mov     eax, [rbx]
0x18004eff4  mov     esi, edi
0x18004eff6  add     rsi, rsi
0x18004eff9  cmp     [rcx+rsi*8+8], eax
0x18004effd  jnz     short loc_18004F069
0x18004efff  xor     edx, edx
0x18004f001  mov     [rbp+arg_18], 0
0x18004f009  lea     rcx, [rbp+arg_18]
0x18004f00d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004f012  mov     rcx, [rbp+arg_10]
0x18004f016  lea     rdx, [rbp+arg_18]
0x18004f01a  mov     rcx, [rcx+rsi*8]
0x18004f01e  call    cs:__imp_UMgrQueryUserToken
0x18004f024  mov     esi, eax
0x18004f026  test    eax, eax
0x18004f028  js      short loc_18004F071
0x18004f02a  mov     rax, [rbp+arg_18]
0x18004f02e  lea     rcx, [rbp+Parameter]; Parameter
0x18004f032  mov     [rbp+var_18], rax
0x18004f036  mov     [rbp+Parameter], r15
0x18004f03a  mov     [rbp+var_10], 0
0x18004f042  call    EFSRecover
0x18004f047  test    eax, eax
0x18004f049  jz      short loc_18004F05C
0x18004f04b  mov     rcx, [rbp+28h]; this
0x18004f04f  mov     r9d, eax; char *
0x18004f052  mov     edx, 5A9h; void *
0x18004f057  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18004f05c  lea     rcx, [rbp+arg_18]
0x18004f060  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004f065  mov     rcx, [rbp+arg_10]
0x18004f069  add     edi, r15d
0x18004f06c  jmp     loc_18004EFE9
0x18004f071  mov     rcx, [rbp+28h]; this
0x18004f075  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004f07c  mov     r9d, esi; char *
0x18004f07f  mov     edx, 5A2h; void *
0x18004f084  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f089  lea     rcx, [rbp+arg_18]
0x18004f08d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004f092  mov     rcx, [rbp+arg_10]
0x18004f096  test    rcx, rcx
0x18004f099  jz      short loc_18004F0A1
0x18004f09b  call    cs:__imp_UMgrFreeSessionUsers
0x18004f0a1  xor     eax, eax
0x18004f0a3  mov     cs:dword_18011739C, eax
0x18004f0a9  call    cs:__imp_GetProcessHeap
0x18004f0af  mov     r8, rbx; lpMem
0x18004f0b2  xor     edx, edx; dwFlags
0x18004f0b4  mov     rcx, rax; hHeap
0x18004f0b7  call    cs:__imp_HeapFree
0x18004f0bd  mov     eax, esi
0x18004f0bf  jmp     short loc_18004F0F1
0x18004f0c1  test    rcx, rcx
0x18004f0c4  jz      short loc_18004F0CC
0x18004f0c6  call    cs:__imp_UMgrFreeSessionUsers
0x18004f0cc  mov     cs:dword_18011739C, 0
0x18004f0d6  test    rbx, rbx
0x18004f0d9  jz      short loc_18004F0EF
0x18004f0db  call    cs:__imp_GetProcessHeap
0x18004f0e1  mov     r8, rbx; lpMem
0x18004f0e4  xor     edx, edx; dwFlags
0x18004f0e6  mov     rcx, rax; hHeap
0x18004f0e9  call    cs:__imp_HeapFree
0x18004f0ef  xor     eax, eax
0x18004f0f1  add     rsp, 40h
0x18004f0f5  pop     r15
0x18004f0f7  pop     rdi
0x18004f0f8  pop     rsi
0x18004f0f9  pop     rbx
0x18004f0fa  pop     rbp
0x18004f0fb  retn
```
