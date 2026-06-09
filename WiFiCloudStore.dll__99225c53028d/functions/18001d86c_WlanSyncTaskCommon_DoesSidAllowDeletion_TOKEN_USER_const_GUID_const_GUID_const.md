# WlanSyncTaskCommon::DoesSidAllowDeletion(_TOKEN_USER const &,_GUID const &,_GUID const &)

- ea: `0x18001d86c`
- end: `0x18001d975`
- name: `?DoesSidAllowDeletion@WlanSyncTaskCommon@@SA_NAEBU_TOKEN_USER@@AEBU_GUID@@1@Z`
- size: `265`
- prototype: `char __fastcall(const struct _TOKEN_USER *, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800211b0`

## callees

- `0x18001d86c`
- `0x18001d97c`
- `0x180024564`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x18001d8ec`
- `wlanapi!WlanFreeMemory` at `0x18001d92a`
- `wlanapi!WlanFreeMemory` at `0x18001d95d`
- `wlanapi!WlanFreeMemory` at `0x18001d8ec`
- `wlanapi!WlanFreeMemory` at `0x18001d92a`
- `wlanapi!WlanFreeMemory` at `0x18001d95d`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x18001d8cb`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x18001d8cb`

## string_xrefs

- `0x18001d8ab`: `CreatorSid`
- `0x18001d938`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`

## pseudocode

```c
char __fastcall WlanSyncTaskCommon::DoesSidAllowDeletion(
        const struct _TOKEN_USER *a1,
        const struct _GUID *a2,
        const struct _GUID *a3)
{
  unsigned int ProfileMetadataWithProfileGuid; // ebx
  PVOID v5; // rcx
  bool IsSidMe; // al
  PVOID v7; // rcx
  PVOID pMemory; // [rsp+30h] [rbp-20h] BYREF
  PVOID *p_pMemory; // [rsp+38h] [rbp-18h]
  void *v11; // [rsp+40h] [rbp-10h]
  char v12; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  int v14; // [rsp+78h] [rbp+28h] BYREF

  pMemory = 0;
  v14 = 0;
  v11 = 0;
  v12 = 1;
  p_pMemory = &pMemory;
  ProfileMetadataWithProfileGuid = WlanGetProfileMetadataWithProfileGuid(a2, a3, 0, L"CreatorSid");
  if ( v12 )
  {
    v5 = *p_pMemory;
    *p_pMemory = v11;
    if ( v5 )
      WlanFreeMemory(v5);
  }
  if ( ProfileMetadataWithProfileGuid )
  {
    if ( ProfileMetadataWithProfileGuid == 2 )
    {
      v7 = pMemory;
      pMemory = 0;
LABEL_9:
      if ( v7 )
        WlanFreeMemory(v7);
      return 1;
    }
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
      (const char *)ProfileMetadataWithProfileGuid,
      (unsigned int)&v14);
    v7 = pMemory;
    pMemory = 0;
  }
  else
  {
    IsSidMe = WlanSyncTaskCommon::IsSidMe(a1->User.Sid, pMemory);
    v7 = pMemory;
    pMemory = 0;
    if ( IsSidMe )
      goto LABEL_9;
  }
  if ( v7 )
    WlanFreeMemory(v7);
  return 0;
}

```

## disassembly

```asm
0x18001d86c  mov     r11, rsp
0x18001d86f  mov     [r11+8], rbx
0x18001d873  mov     [r11+10h], rdi
0x18001d877  push    rbp
0x18001d878  mov     rbp, rsp
0x18001d87b  sub     rsp, 50h
0x18001d87f  mov     rdi, rcx
0x18001d882  mov     [rbp+pMemory], 0
0x18001d88a  mov     rax, r8
0x18001d88d  mov     [rbp+arg_18], 0
0x18001d894  mov     r10, rdx
0x18001d897  mov     [rbp+var_10], 0
0x18001d89f  lea     rcx, [rbp+pMemory]
0x18001d8a3  mov     [rbp+var_8], 1
0x18001d8a7  mov     [rbp+var_18], rcx
0x18001d8ab  lea     r9, aCreatorsid; "CreatorSid"
0x18001d8b2  lea     rcx, [rbp+var_10]
0x18001d8b6  xor     r8d, r8d
0x18001d8b9  mov     [r11-30h], rcx
0x18001d8bd  mov     rdx, rax
0x18001d8c0  lea     rcx, [rbp+arg_18]
0x18001d8c4  mov     [r11-38h], rcx
0x18001d8c8  mov     rcx, r10
0x18001d8cb  call    cs:__imp_WlanGetProfileMetadataWithProfileGuid
0x18001d8d1  cmp     [rbp+var_8], 0
0x18001d8d5  mov     ebx, eax
0x18001d8d7  jz      short loc_18001D8F2
0x18001d8d9  mov     rdx, [rbp+var_18]
0x18001d8dd  mov     rax, [rbp+var_10]
0x18001d8e1  mov     rcx, [rdx]; pMemory
0x18001d8e4  mov     [rdx], rax
0x18001d8e7  test    rcx, rcx
0x18001d8ea  jz      short loc_18001D8F2
0x18001d8ec  call    cs:__imp_WlanFreeMemory
0x18001d8f2  test    ebx, ebx
0x18001d8f4  jnz     short loc_18001D914
0x18001d8f6  mov     rdx, [rbp+pMemory]; void *
0x18001d8fa  mov     rcx, [rdi]; void *
0x18001d8fd  call    ?IsSidMe@WlanSyncTaskCommon@@CA_NQEAX0@Z; WlanSyncTaskCommon::IsSidMe(void * const,void * const)
0x18001d902  mov     rcx, [rbp+pMemory]
0x18001d906  mov     [rbp+pMemory], 0
0x18001d90e  test    al, al
0x18001d910  jz      short loc_18001D958
0x18001d912  jmp     short loc_18001D925
0x18001d914  cmp     ebx, 2
0x18001d917  jnz     short loc_18001D934
0x18001d919  mov     rcx, [rbp+pMemory]; pMemory
0x18001d91d  mov     [rbp+pMemory], 0
0x18001d925  test    rcx, rcx
0x18001d928  jz      short loc_18001D930
0x18001d92a  call    cs:__imp_WlanFreeMemory
0x18001d930  mov     al, 1
0x18001d932  jmp     short loc_18001D965
0x18001d934  mov     rcx, [rbp+8]; this
0x18001d938  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18001d93f  mov     r9d, ebx; char *
0x18001d942  mov     edx, 67h ; 'g'; void *
0x18001d947  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18001d94c  mov     rcx, [rbp+pMemory]; pMemory
0x18001d950  mov     [rbp+pMemory], 0
0x18001d958  test    rcx, rcx
0x18001d95b  jz      short loc_18001D963
0x18001d95d  call    cs:__imp_WlanFreeMemory
0x18001d963  xor     al, al
0x18001d965  mov     rbx, [rsp+50h+arg_0]
0x18001d96a  mov     rdi, [rsp+50h+arg_8]
0x18001d96f  add     rsp, 50h
0x18001d973  pop     rbp
0x18001d974  retn
```
