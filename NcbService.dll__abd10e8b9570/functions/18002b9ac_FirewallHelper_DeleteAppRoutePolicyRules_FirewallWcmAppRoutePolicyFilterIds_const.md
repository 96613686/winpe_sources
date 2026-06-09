# FirewallHelper::DeleteAppRoutePolicyRules(_FirewallWcmAppRoutePolicyFilterIds const &)

- ea: `0x18002b9ac`
- end: `0x18002bb45`
- name: `?DeleteAppRoutePolicyRules@FirewallHelper@@YAJAEBU_FirewallWcmAppRoutePolicyFilterIds@@@Z`
- size: `409`
- prototype: `int __fastcall(UINT64 *this, const struct _FirewallWcmAppRoutePolicyFilterIds *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180029b20`

## callees

- `0x18001c080`
- `0x18002b9ac`
- `0x18002bffc`

## import_xrefs

- `fwpuclnt!FwpmEngineOpen0` at `0x18002b9d6`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002b9d6`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002ba09`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002ba2e`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002ba53`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002ba78`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002ba9d`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002bac2`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002bae7`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002bb0c`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002ba09`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002ba2e`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002ba53`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002ba78`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002ba9d`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002bac2`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002bae7`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002bb0c`
- `fwpuclnt!FwpmEngineClose0` at `0x18002bb2b`
- `fwpuclnt!FwpmEngineClose0` at `0x18002bb2b`

## pseudocode

```c
int __fastcall FirewallHelper::DeleteAppRoutePolicyRules(
        UINT64 *this,
        const struct _FirewallWcmAppRoutePolicyFilterIds *a2)
{
  DWORD v3; // eax
  HANDLE v5; // rdi
  DWORD v6; // eax
  unsigned int v7; // r8d
  DWORD v8; // eax
  unsigned int v9; // r8d
  DWORD v10; // eax
  unsigned int v11; // r8d
  DWORD v12; // eax
  unsigned int v13; // r8d
  DWORD v14; // eax
  unsigned int v15; // r8d
  DWORD v16; // eax
  unsigned int v17; // r8d
  DWORD v18; // eax
  unsigned int v19; // r8d
  DWORD v20; // eax
  unsigned int v21; // r8d
  unsigned int v22; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE engineHandle; // [rsp+48h] [rbp+10h] BYREF

  engineHandle = 0;
  v3 = FwpmEngineOpen0(0, 0xFFFFFFFF, 0, 0, &engineHandle);
  if ( v3 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1B4,
             (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
             (const char *)v3,
             v22);
  v5 = engineHandle;
  v6 = FwpmFilterDeleteById0(engineHandle, *this);
  if ( v6 )
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x1BA, v7, (const char *)v6, v22);
  v8 = FwpmFilterDeleteById0(engineHandle, this[1]);
  if ( v8 )
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x1BB, v9, (const char *)v8, v22);
  v10 = FwpmFilterDeleteById0(engineHandle, this[2]);
  if ( v10 )
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x1BC, v11, (const char *)v10, v22);
  v12 = FwpmFilterDeleteById0(engineHandle, this[3]);
  if ( v12 )
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x1BD, v13, (const char *)v12, v22);
  v14 = FwpmFilterDeleteById0(engineHandle, this[4]);
  if ( v14 )
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x1BE, v15, (const char *)v14, v22);
  v16 = FwpmFilterDeleteById0(engineHandle, this[5]);
  if ( v16 )
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x1BF, v17, (const char *)v16, v22);
  v18 = FwpmFilterDeleteById0(engineHandle, this[6]);
  if ( v18 )
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x1C0, v19, (const char *)v18, v22);
  v20 = FwpmFilterDeleteById0(engineHandle, this[7]);
  if ( v20 )
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x1C1, v21, (const char *)v20, v22);
  FwpmEngineClose0(v5);
  return 0;
}

```

## disassembly

```asm
0x18002b9ac  mov     r11, rsp
0x18002b9af  mov     [r11+8], rbx
0x18002b9b3  push    rdi
0x18002b9b4  sub     rsp, 30h
0x18002b9b8  mov     rbx, rcx
0x18002b9bb  mov     qword ptr [r11+10h], 0
0x18002b9c3  lea     rax, [r11+10h]
0x18002b9c7  mov     [r11-18h], rax
0x18002b9cb  xor     r9d, r9d; session
0x18002b9ce  xor     r8d, r8d; authIdentity
0x18002b9d1  or      edx, 0FFFFFFFFh; authnService
0x18002b9d4  xor     ecx, ecx; serverName
0x18002b9d6  call    cs:__imp_FwpmEngineOpen0
0x18002b9dc  test    eax, eax
0x18002b9de  jz      short loc_18002B9FE
0x18002b9e0  mov     rcx, [rsp+38h]; this
0x18002b9e5  mov     r9d, eax; char *
0x18002b9e8  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002b9ef  mov     edx, 1B4h; void *
0x18002b9f4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b9f9  jmp     loc_18002BB39
0x18002b9fe  mov     rdi, [rsp+38h+engineHandle]
0x18002ba03  mov     rdx, [rbx]; id
0x18002ba06  mov     rcx, rdi; engineHandle
0x18002ba09  call    cs:__imp_FwpmFilterDeleteById0
0x18002ba0f  mov     rcx, [rsp+38h]; this
0x18002ba14  test    eax, eax
0x18002ba16  jz      short loc_18002BA25
0x18002ba18  mov     r9d, eax; char *
0x18002ba1b  mov     edx, 1BAh; void *
0x18002ba20  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002ba25  mov     rdx, [rbx+8]; id
0x18002ba29  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x18002ba2e  call    cs:__imp_FwpmFilterDeleteById0
0x18002ba34  mov     rcx, [rsp+38h]; this
0x18002ba39  test    eax, eax
0x18002ba3b  jz      short loc_18002BA4A
0x18002ba3d  mov     r9d, eax; char *
0x18002ba40  mov     edx, 1BBh; void *
0x18002ba45  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002ba4a  mov     rdx, [rbx+10h]; id
0x18002ba4e  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x18002ba53  call    cs:__imp_FwpmFilterDeleteById0
0x18002ba59  mov     rcx, [rsp+38h]; this
0x18002ba5e  test    eax, eax
0x18002ba60  jz      short loc_18002BA6F
0x18002ba62  mov     r9d, eax; char *
0x18002ba65  mov     edx, 1BCh; void *
0x18002ba6a  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002ba6f  mov     rdx, [rbx+18h]; id
0x18002ba73  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x18002ba78  call    cs:__imp_FwpmFilterDeleteById0
0x18002ba7e  mov     rcx, [rsp+38h]; this
0x18002ba83  test    eax, eax
0x18002ba85  jz      short loc_18002BA94
0x18002ba87  mov     r9d, eax; char *
0x18002ba8a  mov     edx, 1BDh; void *
0x18002ba8f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002ba94  mov     rdx, [rbx+20h]; id
0x18002ba98  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x18002ba9d  call    cs:__imp_FwpmFilterDeleteById0
0x18002baa3  mov     rcx, [rsp+38h]; this
0x18002baa8  test    eax, eax
0x18002baaa  jz      short loc_18002BAB9
0x18002baac  mov     r9d, eax; char *
0x18002baaf  mov     edx, 1BEh; void *
0x18002bab4  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002bab9  mov     rdx, [rbx+28h]; id
0x18002babd  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x18002bac2  call    cs:__imp_FwpmFilterDeleteById0
0x18002bac8  mov     rcx, [rsp+38h]; this
0x18002bacd  test    eax, eax
0x18002bacf  jz      short loc_18002BADE
0x18002bad1  mov     r9d, eax; char *
0x18002bad4  mov     edx, 1BFh; void *
0x18002bad9  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002bade  mov     rdx, [rbx+30h]; id
0x18002bae2  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x18002bae7  call    cs:__imp_FwpmFilterDeleteById0
0x18002baed  mov     rcx, [rsp+38h]; this
0x18002baf2  test    eax, eax
0x18002baf4  jz      short loc_18002BB03
0x18002baf6  mov     r9d, eax; char *
0x18002baf9  mov     edx, 1C0h; void *
0x18002bafe  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002bb03  mov     rdx, [rbx+38h]; id
0x18002bb07  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x18002bb0c  call    cs:__imp_FwpmFilterDeleteById0
0x18002bb12  mov     rcx, [rsp+38h]; this
0x18002bb17  test    eax, eax
0x18002bb19  jz      short loc_18002BB28
0x18002bb1b  mov     r9d, eax; char *
0x18002bb1e  mov     edx, 1C1h; void *
0x18002bb23  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002bb28  mov     rcx, rdi; engineHandle
0x18002bb2b  call    cs:__imp_FwpmEngineClose0
0x18002bb31  xor     eax, eax
0x18002bb33  jmp     short loc_18002BB39
0x18002bb35  mov     eax, dword ptr [rsp+38h+engineHandle]
0x18002bb39  mov     rbx, [rsp+38h+arg_0]
0x18002bb3e  add     rsp, 30h
0x18002bb42  pop     rdi
0x18002bb43  retn
```
