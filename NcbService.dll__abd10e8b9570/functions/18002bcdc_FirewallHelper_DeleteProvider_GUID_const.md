# FirewallHelper::DeleteProvider(_GUID const &)

- ea: `0x18002bcdc`
- end: `0x18002bd85`
- name: `?DeleteProvider@FirewallHelper@@YAJAEBU_GUID@@@Z`
- size: `169`
- prototype: `int __fastcall(GUID *key, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180029c40`

## callees

- `0x18001c080`
- `0x18002bcdc`

## import_xrefs

- `fwpuclnt!FwpmEngineOpen0` at `0x18002bd06`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002bd06`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18002bd36`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18002bd36`
- `fwpuclnt!FwpmEngineClose0` at `0x18002bd5e`
- `fwpuclnt!FwpmEngineClose0` at `0x18002bd6b`
- `fwpuclnt!FwpmEngineClose0` at `0x18002bd5e`
- `fwpuclnt!FwpmEngineClose0` at `0x18002bd6b`

## pseudocode

```c
int __fastcall FirewallHelper::DeleteProvider(GUID *key, const struct _GUID *a2)
{
  DWORD v3; // eax
  HANDLE v5; // rdi
  DWORD v6; // eax
  int v7; // ebx
  unsigned int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE engineHandle; // [rsp+48h] [rbp+10h] BYREF

  engineHandle = 0;
  v3 = FwpmEngineOpen0(0, 0xFFFFFFFF, 0, 0, &engineHandle);
  if ( v3 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x22E,
             (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
             (const char *)v3,
             v8);
  v5 = engineHandle;
  v6 = FwpmProviderDeleteByKey0(engineHandle, key);
  if ( v6 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x233,
           (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
           (const char *)v6,
           v8);
    FwpmEngineClose0(v5);
    return v7;
  }
  else
  {
    FwpmEngineClose0(v5);
    return 0;
  }
}

```

## disassembly

```asm
0x18002bcdc  mov     r11, rsp
0x18002bcdf  mov     [r11+8], rbx
0x18002bce3  push    rdi
0x18002bce4  sub     rsp, 30h
0x18002bce8  mov     rbx, rcx
0x18002bceb  mov     qword ptr [r11+10h], 0
0x18002bcf3  lea     rax, [r11+10h]
0x18002bcf7  mov     [r11-18h], rax
0x18002bcfb  xor     r9d, r9d; session
0x18002bcfe  xor     r8d, r8d; authIdentity
0x18002bd01  or      edx, 0FFFFFFFFh; authnService
0x18002bd04  xor     ecx, ecx; serverName
0x18002bd06  call    cs:__imp_FwpmEngineOpen0
0x18002bd0c  test    eax, eax
0x18002bd0e  jz      short loc_18002BD2B
0x18002bd10  mov     rcx, [rsp+38h]; this
0x18002bd15  mov     r9d, eax; char *
0x18002bd18  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002bd1f  mov     edx, 22Eh; void *
0x18002bd24  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002bd29  jmp     short loc_18002BD79
0x18002bd2b  mov     rdi, [rsp+38h+engineHandle]
0x18002bd30  mov     rdx, rbx; key
0x18002bd33  mov     rcx, rdi; engineHandle
0x18002bd36  call    cs:__imp_FwpmProviderDeleteByKey0
0x18002bd3c  test    eax, eax
0x18002bd3e  jz      short loc_18002BD68
0x18002bd40  mov     rcx, [rsp+38h]; this
0x18002bd45  mov     r9d, eax; char *
0x18002bd48  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002bd4f  mov     edx, 233h; void *
0x18002bd54  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002bd59  mov     ebx, eax
0x18002bd5b  mov     rcx, rdi; engineHandle
0x18002bd5e  call    cs:__imp_FwpmEngineClose0
0x18002bd64  mov     eax, ebx
0x18002bd66  jmp     short loc_18002BD79
0x18002bd68  mov     rcx, rdi; engineHandle
0x18002bd6b  call    cs:__imp_FwpmEngineClose0
0x18002bd71  xor     eax, eax
0x18002bd73  jmp     short loc_18002BD79
0x18002bd75  mov     eax, dword ptr [rsp+38h+engineHandle]
0x18002bd79  mov     rbx, [rsp+38h+arg_0]
0x18002bd7e  add     rsp, 30h
0x18002bd82  pop     rdi
0x18002bd83  retn
```
