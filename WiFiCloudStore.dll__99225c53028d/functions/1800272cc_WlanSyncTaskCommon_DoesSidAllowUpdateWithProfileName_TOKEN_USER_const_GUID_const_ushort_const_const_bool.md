# WlanSyncTaskCommon::DoesSidAllowUpdateWithProfileName(_TOKEN_USER const &,_GUID const &,ushort const * const,bool)

- ea: `0x1800272cc`
- end: `0x1800273a7`
- name: `?DoesSidAllowUpdateWithProfileName@WlanSyncTaskCommon@@SA_NAEBU_TOKEN_USER@@AEBU_GUID@@QEBG_N@Z`
- size: `219`
- prototype: `bool __fastcall(const struct _TOKEN_USER *, const struct _GUID *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001314c`

## callees

- `0x180015ee8`
- `0x1800272cc`
- `0x180031ce4`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x18002734a`
- `wlanapi!WlanFreeMemory` at `0x180027376`
- `wlanapi!WlanFreeMemory` at `0x18002734a`
- `wlanapi!WlanFreeMemory` at `0x180027376`
- `wlanapi!WlanGetProfileMetadata` at `0x180027329`
- `wlanapi!WlanGetProfileMetadata` at `0x180027329`

## string_xrefs

- `0x180027319`: `CreatorSid`
- `0x180027395`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall WlanSyncTaskCommon::DoesSidAllowUpdateWithProfileName(
        const struct _TOKEN_USER *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        bool a4)
{
  unsigned int ProfileMetadata; // ebx
  PVOID v7; // rcx
  PVOID v8; // rdx
  bool DoesSidAllowUpdateCommon; // bl
  PVOID v10; // rcx
  unsigned int v12; // [rsp+30h] [rbp-38h] BYREF
  PVOID pMemory; // [rsp+38h] [rbp-30h] BYREF
  PVOID *p_pMemory; // [rsp+40h] [rbp-28h]
  void *v15; // [rsp+48h] [rbp-20h]
  char v16; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  pMemory = 0;
  v12 = 0;
  p_pMemory = &pMemory;
  v15 = 0;
  v16 = 1;
  ProfileMetadata = WlanGetProfileMetadata(a2, a3, 0, L"CreatorSid");
  if ( v16 )
  {
    v7 = *p_pMemory;
    *p_pMemory = v15;
    if ( v7 )
      WlanFreeMemory(v7);
  }
  if ( ProfileMetadata )
  {
    v8 = 0;
    if ( ProfileMetadata != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
        (const char *)ProfileMetadata,
        (unsigned int)&v12);
  }
  else
  {
    v8 = pMemory;
  }
  DoesSidAllowUpdateCommon = WlanSyncTaskCommon::DoesSidAllowUpdateCommon(a1, v8, a4);
  v10 = pMemory;
  pMemory = 0;
  if ( v10 )
    WlanFreeMemory(v10);
  return DoesSidAllowUpdateCommon;
}

```

## disassembly

```asm
0x1800272cc  push    rbp
0x1800272ce  push    rbx
0x1800272cf  push    rsi
0x1800272d0  push    rdi
0x1800272d1  mov     rbp, rsp
0x1800272d4  sub     rsp, 68h
0x1800272d8  mov     dil, r9b
0x1800272db  mov     rax, r8
0x1800272de  mov     r10, rdx
0x1800272e1  mov     rsi, rcx
0x1800272e4  mov     [rbp+pMemory], 0
0x1800272ec  mov     [rbp+var_38], 0
0x1800272f3  lea     rcx, [rbp+pMemory]
0x1800272f7  mov     [rbp+var_28], rcx
0x1800272fb  mov     [rbp+var_20], 0
0x180027303  mov     [rbp+var_18], 1
0x180027307  lea     rcx, [rbp+var_20]
0x18002730b  mov     [rsp+68h+var_40], rcx
0x180027310  lea     rcx, [rbp+var_38]
0x180027314  mov     qword ptr [rsp+68h+var_48], rcx; unsigned int
0x180027319  lea     r9, aCreatorsid; "CreatorSid"
0x180027320  xor     r8d, r8d
0x180027323  mov     rdx, rax
0x180027326  mov     rcx, r10
0x180027329  call    cs:__imp_WlanGetProfileMetadata
0x18002732f  mov     ebx, eax
0x180027331  cmp     [rbp+var_18], 0
0x180027335  jz      short loc_180027350
0x180027337  mov     r8, [rbp+var_28]
0x18002733b  mov     rcx, [r8]; pMemory
0x18002733e  mov     rdx, [rbp+var_20]
0x180027342  mov     [r8], rdx
0x180027345  test    rcx, rcx
0x180027348  jz      short loc_180027350
0x18002734a  call    cs:__imp_WlanFreeMemory
0x180027350  test    ebx, ebx
0x180027352  jnz     short loc_180027387
0x180027354  mov     rdx, [rbp+pMemory]; void *
0x180027358  mov     r8b, dil; bool
0x18002735b  mov     rcx, rsi; struct _TOKEN_USER *
0x18002735e  call    ?DoesSidAllowUpdateCommon@WlanSyncTaskCommon@@CA_NAEBU_TOKEN_USER@@QEAX_N@Z; WlanSyncTaskCommon::DoesSidAllowUpdateCommon(_TOKEN_USER const &,void * const,bool)
0x180027363  mov     bl, al
0x180027365  mov     rcx, [rbp+pMemory]; pMemory
0x180027369  mov     [rbp+pMemory], 0
0x180027371  test    rcx, rcx
0x180027374  jz      short loc_18002737C
0x180027376  call    cs:__imp_WlanFreeMemory
0x18002737c  mov     al, bl
0x18002737e  add     rsp, 68h
0x180027382  pop     rdi
0x180027383  pop     rsi
0x180027384  pop     rbx
0x180027385  pop     rbp
0x180027386  retn
0x180027387  xor     edx, edx
0x180027389  cmp     ebx, 2
0x18002738c  jz      short loc_180027358
0x18002738e  mov     rcx, [rbp+20h]; this
0x180027392  mov     r9d, ebx; char *
0x180027395  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18002739c  mov     edx, 0B1h; void *
0x1800273a1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
