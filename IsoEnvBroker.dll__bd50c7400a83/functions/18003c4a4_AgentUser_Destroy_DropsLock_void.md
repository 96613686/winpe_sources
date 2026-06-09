# AgentUser::Destroy_DropsLock(void)

- ea: `0x18003c4a4`
- end: `0x18003c631`
- name: `?Destroy_DropsLock@AgentUser@@QEAAJXZ`
- size: `397`
- prototype: `__int64 __fastcall(AgentUser *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800373a0`
- `0x180037470`
- `0x180037924`
- `0x180037ab8`

## callees

- `0x180011e18`
- `0x18003bedc`
- `0x18003c324`
- `0x18003c4a4`
- `0x18003ca08`
- `0x18003cc34`
- `0x180040c90`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003c5c0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003c5c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c585`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c585`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c5d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c5d1`

## string_xrefs

- `0x18003c5a5`: `Failed to open registry key to remove config ID, hr: 0x%X`
- `0x18003c577`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker\ConfigIds`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AgentUser::Destroy_DropsLock(AgentUser *this)
{
  __int64 v2; // rcx
  _QWORD *v3; // rcx
  const WCHAR *v5; // rbx
  int v6; // eax
  bool v7; // sf
  HKEY v8; // rcx
  __int64 v9; // rbx
  struct OwningUserRegistry *OwningUserRegistry; // rax
  _QWORD v11[5]; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 244) )
    AgentUser::MarkCached(this, 0);
  AgentUser::CleanupProxyAndClientConnections(this);
  v2 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (_QWORD *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    v11[0] = v3[6];
    v11[1] = v3[7];
    v3[6] = 0;
    v3[7] = 0;
    v11[2] = v3[8];
    v11[3] = v3[9];
    v3[8] = 0;
    v3[9] = 0;
    std::tuple<std::shared_ptr<ClientIdentity>,std::shared_ptr<AgentUser>>::~tuple<std::shared_ptr<ClientIdentity>,std::shared_ptr<AgentUser>>((__int64)v11);
  }
  if ( !*((_QWORD *)this + 6) )
    return 0;
  v5 = (const WCHAR *)((char *)this + 80);
  if ( *((_QWORD *)this + 13) > 7u )
    v5 = *(const WCHAR **)v5;
  hKey = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\IsoEnvBroker\\ConfigIds",
         0,
         0xF003Fu,
         &hKey);
  v7 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v7 = v6 < 0;
  }
  if ( v7 )
  {
    if ( v6 != -2147024894 )
      Log(3u, L"Failed to open registry key to remove config ID, hr: 0x%X", (unsigned int)v6);
  }
  else
  {
    RegDeleteValueW(hKey, v5);
  }
  v8 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  v9 = *((_QWORD *)this + 6);
  OwningUserRegistry = (struct OwningUserRegistry *)AgentAccountRegistry::GetOrCreateOwningUserRegistry(
                                                      v8,
                                                      (_QWORD *)(*(_QWORD *)(v9 + 40) + 16LL),
                                                      (const wchar_t *)(*(_QWORD *)(v9 + 40) + 48LL));
  return AgentAccountHelpers::CleanupAgentUserForUser_DropsLock(
           (unsigned int)*(_QWORD *)(v9 + 40) + 16,
           (int)this + 112,
           *(_DWORD *)(*((_QWORD *)this + 6) + 112LL)
         + 168
         + (**(_BYTE **)(*((_QWORD *)this + 6) + 112LL) != 0 ? 0xFFFFFFA0 : 0),
           (int)this + 144,
           OwningUserRegistry);
}

```

## disassembly

```asm
0x18003c4a4  mov     [rsp+arg_8], rbx
0x18003c4a9  push    rdi
0x18003c4aa  sub     rsp, 50h
0x18003c4ae  mov     rdi, rcx
0x18003c4b1  cmp     byte ptr [rcx+0F4h], 0
0x18003c4b8  jz      short loc_18003C4C1
0x18003c4ba  xor     edx, edx; bool
0x18003c4bc  call    ?MarkCached@AgentUser@@QEAAX_N@Z; AgentUser::MarkCached(bool)
0x18003c4c1  mov     rcx, rdi; this
0x18003c4c4  call    ?CleanupProxyAndClientConnections@AgentUser@@AEAAXXZ; AgentUser::CleanupProxyAndClientConnections(void)
0x18003c4c9  nop
0x18003c4ca  mov     rcx, [rdi+48h]
0x18003c4ce  mov     qword ptr [rdi+48h], 0
0x18003c4d6  test    rcx, rcx
0x18003c4d9  jz      short loc_18003C4E8
0x18003c4db  mov     rax, [rcx]
0x18003c4de  mov     rax, [rax+10h]
0x18003c4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4e7  nop
0x18003c4e8  mov     rcx, [rdi+40h]
0x18003c4ec  test    rcx, rcx
0x18003c4ef  jz      short loc_18003C53F
0x18003c4f1  mov     rax, [rcx+30h]
0x18003c4f5  mov     [rsp+58h+var_28], rax
0x18003c4fa  mov     rax, [rcx+38h]
0x18003c4fe  mov     [rsp+58h+var_20], rax
0x18003c503  mov     qword ptr [rcx+30h], 0
0x18003c50b  mov     qword ptr [rcx+38h], 0
0x18003c513  mov     rax, [rcx+40h]
0x18003c517  mov     [rsp+58h+var_18], rax
0x18003c51c  mov     rax, [rcx+48h]
0x18003c520  mov     [rsp+58h+var_10], rax
0x18003c525  mov     qword ptr [rcx+40h], 0
0x18003c52d  mov     qword ptr [rcx+48h], 0
0x18003c535  lea     rcx, [rsp+58h+var_28]
0x18003c53a  call    ??1?$tuple@V?$shared_ptr@VClientIdentity@@@std@@V?$shared_ptr@VAgentUser@@@2@@std@@QEAA@XZ; std::tuple<std::shared_ptr<ClientIdentity>,std::shared_ptr<AgentUser>>::~tuple<std::shared_ptr<ClientIdentity>,std::shared_ptr<AgentUser>>(void)
0x18003c53f  cmp     qword ptr [rdi+30h], 0
0x18003c544  jnz     short loc_18003C54D
0x18003c546  xor     eax, eax
0x18003c548  jmp     loc_18003C626
0x18003c54d  lea     rbx, [rdi+50h]
0x18003c551  cmp     qword ptr [rbx+18h], 7
0x18003c556  jbe     short loc_18003C55B
0x18003c558  mov     rbx, [rbx]
0x18003c55b  mov     [rsp+58h+hKey], 0
0x18003c564  lea     rax, [rsp+58h+hKey]
0x18003c569  mov     [rsp+58h+phkResult], rax; phkResult
0x18003c56e  mov     r9d, 0F003Fh; samDesired
0x18003c574  xor     r8d, r8d; ulOptions
0x18003c577  lea     rdx, ?c_isoBrokerConfigIdRegPath@AgentAccountHelpers@@0QB_WB; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x18003c57e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c585  call    cs:__imp_RegOpenKeyExW
0x18003c58b  test    eax, eax
0x18003c58d  jle     short loc_18003C599
0x18003c58f  movzx   eax, ax
0x18003c592  or      eax, 80070000h
0x18003c597  test    eax, eax
0x18003c599  jns     short loc_18003C5B8
0x18003c59b  cmp     eax, 80070002h
0x18003c5a0  jz      short loc_18003C5C7
0x18003c5a2  mov     r8d, eax
0x18003c5a5  lea     rdx, aFailedToOpenRe_0; "Failed to open registry key to remove c"...
0x18003c5ac  mov     ecx, 3; unsigned __int8
0x18003c5b1  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003c5b6  jmp     short loc_18003C5C7
0x18003c5b8  mov     rdx, rbx; lpValueName
0x18003c5bb  mov     rcx, [rsp+58h+hKey]; hKey
0x18003c5c0  call    cs:__imp_RegDeleteValueW
0x18003c5c6  nop
0x18003c5c7  mov     rcx, [rsp+58h+hKey]; hKey
0x18003c5cc  test    rcx, rcx
0x18003c5cf  jz      short loc_18003C5D7
0x18003c5d1  call    cs:__imp_RegCloseKey
0x18003c5d7  mov     rbx, [rdi+30h]
0x18003c5db  mov     rdx, [rbx+28h]
0x18003c5df  lea     r8, [rdx+30h]
0x18003c5e3  add     rdx, 10h
0x18003c5e7  call    ?GetOrCreateOwningUserRegistry@AgentAccountRegistry@@QEAAAEAVOwningUserRegistry@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; AgentAccountRegistry::GetOrCreateOwningUserRegistry(std::wstring const &,std::wstring const &)
0x18003c5ec  mov     rcx, [rdi+30h]
0x18003c5f0  mov     rdx, [rcx+70h]
0x18003c5f4  lea     r9, [rdi+90h]
0x18003c5fb  mov     cl, [rdx]
0x18003c5fd  neg     cl
0x18003c5ff  sbb     r8, r8
0x18003c602  and     r8, 0FFFFFFFFFFFFFFA0h
0x18003c606  add     rdx, 0A8h
0x18003c60d  add     r8, rdx
0x18003c610  lea     rdx, [rdi+70h]
0x18003c614  mov     rcx, [rbx+28h]
0x18003c618  add     rcx, 10h
0x18003c61c  mov     [rsp+58h+phkResult], rax
0x18003c621  call    ?CleanupAgentUserForUser_DropsLock@AgentAccountHelpers@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000AEAVOwningUserRegistry@@@Z; AgentAccountHelpers::CleanupAgentUserForUser_DropsLock(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,OwningUserRegistry &)
0x18003c626  mov     rbx, [rsp+58h+arg_8]
0x18003c62b  add     rsp, 50h
0x18003c62f  pop     rdi
0x18003c630  retn
```
