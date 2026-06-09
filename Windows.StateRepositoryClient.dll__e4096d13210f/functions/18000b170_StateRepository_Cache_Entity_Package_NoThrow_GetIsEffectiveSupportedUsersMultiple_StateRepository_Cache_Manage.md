# StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)

- ea: `0x18000b170`
- end: `0x18000b204`
- name: `?GetIsEffectiveSupportedUsersMultiple@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_N@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000db30`

## callees

- `0x1800075e4`
- `0x18000b170`
- `0x18000b20c`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-3!CouldMultiUserAppsBehaviorBePossibleForPackage` at `0x18000b192`
- `api-ms-win-appmodel-runtime-internal-l1-1-3!CouldMultiUserAppsBehaviorBePossibleForPackage` at `0x18000b192`

## string_xrefs

- `0x18000b1a8`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        bool *a3)
{
  int IsSupportedUsersMultiple; // edi
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-38h] BYREF
  _DWORD v10[13]; // [rsp+24h] [rbp-34h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  bool v12; // [rsp+78h] [rbp+20h] BYREF

  v10[0] = 0;
  IsSupportedUsersMultiple = CouldMultiUserAppsBehaviorBePossibleForPackage(a2, v10);
  if ( IsSupportedUsersMultiple < 0 )
  {
    v7 = 1387;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)IsSupportedUsersMultiple,
      v9);
    return (unsigned int)IsSupportedUsersMultiple;
  }
  if ( v10[0] )
  {
    v12 = 0;
    LOBYTE(v9) = 0;
    IsSupportedUsersMultiple = StateRepository::Cache::Entity::Package_NoThrow::GetIsSupportedUsersMultiple(
                                 a1,
                                 a2,
                                 &v12,
                                 (bool *)&v9);
    if ( IsSupportedUsersMultiple < 0 )
    {
      v7 = 1392;
      goto LABEL_3;
    }
    *a3 = v12;
  }
  else
  {
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000b170  push    rbx
0x18000b172  push    rbp
0x18000b173  push    rsi
0x18000b174  push    rdi
0x18000b175  sub     rsp, 38h
0x18000b179  mov     rsi, rdx
0x18000b17c  mov     [rsp+58h+var_34], 0
0x18000b184  mov     rbp, rcx
0x18000b187  lea     rdx, [rsp+58h+var_34]
0x18000b18c  mov     rcx, rsi
0x18000b18f  mov     rbx, r8
0x18000b192  call    cs:__imp_CouldMultiUserAppsBehaviorBePossibleForPackage
0x18000b198  mov     edi, eax
0x18000b19a  test    eax, eax
0x18000b19c  jns     short loc_18000B1BB
0x18000b19e  mov     edx, 56Bh; void *
0x18000b1a3  mov     rcx, [rsp+58h]; this
0x18000b1a8  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b1af  mov     r9d, edi; char *
0x18000b1b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b1b7  mov     eax, edi
0x18000b1b9  jmp     short loc_18000B1FB
0x18000b1bb  cmp     [rsp+58h+var_34], 0
0x18000b1c0  jz      short loc_18000B1F6
0x18000b1c2  lea     r9, [rsp+58h+var_38]; bool *
0x18000b1c7  mov     [rsp+58h+arg_18], 0
0x18000b1cc  lea     r8, [rsp+58h+arg_18]; bool *
0x18000b1d1  mov     byte ptr [rsp+58h+var_38], 0
0x18000b1d6  mov     rdx, rsi; unsigned __int16 *
0x18000b1d9  mov     rcx, rbp; struct StateRepository::Cache::Manager_NoThrow *
0x18000b1dc  call    ?GetIsSupportedUsersMultiple@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_N2@Z; StateRepository::Cache::Entity::Package_NoThrow::GetIsSupportedUsersMultiple(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &,bool &)
0x18000b1e1  mov     edi, eax
0x18000b1e3  test    eax, eax
0x18000b1e5  jns     short loc_18000B1EE
0x18000b1e7  mov     edx, 570h
0x18000b1ec  jmp     short loc_18000B1A3
0x18000b1ee  mov     al, [rsp+58h+arg_18]
0x18000b1f2  mov     [rbx], al
0x18000b1f4  jmp     short loc_18000B1F9
0x18000b1f6  mov     byte ptr [rbx], 0
0x18000b1f9  xor     eax, eax
0x18000b1fb  add     rsp, 38h
0x18000b1ff  pop     rdi
0x18000b200  pop     rsi
0x18000b201  pop     rbp
0x18000b202  pop     rbx
0x18000b203  retn
```
