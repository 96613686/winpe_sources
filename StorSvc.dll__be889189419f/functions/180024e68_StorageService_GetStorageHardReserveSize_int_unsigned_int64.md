# StorageService::GetStorageHardReserveSize(int,unsigned __int64 *)

- ea: `0x180024e68`
- end: `0x180024f8b`
- name: `?GetStorageHardReserveSize@StorageService@@QEAAJHPEA_K@Z`
- size: `291`
- prototype: `__int64 __fastcall(StorageService *__hidden this, int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180024ac4`

## callees

- `0x180012734`
- `0x18001fcac`
- `0x180024e68`

## import_xrefs

- `storageusage!FindNextStorageTypeEx` at `0x180024f55`
- `storageusage!FindNextStorageTypeEx` at `0x180024f55`
- `storageusage!CloseFindStorageSearch` at `0x180024f68`
- `storageusage!CloseFindStorageSearch` at `0x180024f68`
- `storageusage!SelectStorageVolumeEx` at `0x180024f27`
- `storageusage!SelectStorageVolumeEx` at `0x180024f27`
- `storageusage!OpenStorageTypeSearch` at `0x180024eb6`
- `storageusage!OpenStorageTypeSearch` at `0x180024eb6`
- `RPCRT4!RpcRevertToSelf` at `0x180024f7a`
- `RPCRT4!RpcRevertToSelf` at `0x180024f7a`

## string_xrefs

- `0x180024e8a`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`
- `0x180024ec9`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageService::GetStorageHardReserveSize(StorageService *this, int a2, unsigned __int64 *a3)
{
  int NextStorageType; // ebx
  int v6; // eax
  bool v7; // zf
  int v9; // [rsp+20h] [rbp-48h]
  _BYTE v10[8]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v11; // [rsp+48h] [rbp-20h] BYREF
  __int64 v12; // [rsp+50h] [rbp-18h] BYREF
  __int64 v13; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  if ( a3 )
  {
    AutoRpcImpersonateClient(v10);
    v11 = 0;
    v6 = OpenStorageTypeSearch(&v11);
    NextStorageType = v6;
    if ( v6 >= 0 )
    {
      v12 = 0;
      v13 = 0;
      NextStorageType = SelectStorageVolumeEx(v11, 0, 0, 0, 0, a2 != 0 ? 2 : 0, &v12, &v12);
      if ( NextStorageType >= 0 )
        NextStorageType = FindNextStorageTypeEx(v11, 30, &word_180092AF0, &v13, a3, &v12);
      if ( v11 )
        CloseFindStorageSearch(&v11);
      v7 = v10[0] == 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1942,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
        (const char *)(unsigned int)v6,
        v9);
      v7 = v10[0] == 0;
    }
    v10[0] = 0;
    if ( !v7 )
      RpcRevertToSelf();
  }
  else
  {
    NextStorageType = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193C,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
      (const char *)0x80070057LL,
      v9);
  }
  return (unsigned int)NextStorageType;
}

```

## disassembly

```asm
0x180024e68  push    rbp
0x180024e6a  push    rbx
0x180024e6b  push    rsi
0x180024e6c  push    rdi
0x180024e6d  mov     rbp, rsp
0x180024e70  sub     rsp, 68h
0x180024e74  mov     rdi, r8
0x180024e77  mov     esi, edx
0x180024e79  test    r8, r8
0x180024e7c  jnz     short loc_180024EA0
0x180024e7e  mov     rcx, [rbp+20h]; this
0x180024e82  mov     ebx, 80070057h
0x180024e87  mov     r9d, ebx; char *
0x180024e8a  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180024e91  mov     edx, 193Ch; void *
0x180024e96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024e9b  jmp     loc_180024F80
0x180024ea0  lea     rcx, [rbp+var_28]
0x180024ea4  call    ?AutoRpcImpersonateClient@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@XZ; AutoRpcImpersonateClient(void)
0x180024ea9  nop
0x180024eaa  mov     [rbp+var_20], 0
0x180024eb2  lea     rcx, [rbp+var_20]
0x180024eb6  call    cs:__imp_OpenStorageTypeSearch
0x180024ebc  mov     ebx, eax
0x180024ebe  test    eax, eax
0x180024ec0  jns     short loc_180024EE5
0x180024ec2  mov     rcx, [rbp+20h]; this
0x180024ec6  mov     r9d, eax; char *
0x180024ec9  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180024ed0  mov     edx, 1942h; void *
0x180024ed5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024eda  nop
0x180024edb  mov     cl, [rbp+var_28]
0x180024ede  test    cl, cl
0x180024ee0  jmp     loc_180024F74
0x180024ee5  mov     [rbp+var_18], 0
0x180024eed  mov     [rbp+var_10], 0
0x180024ef5  neg     esi
0x180024ef7  sbb     eax, eax
0x180024ef9  and     eax, 2
0x180024efc  lea     rcx, [rbp+var_18]
0x180024f00  mov     [rsp+68h+var_30], rcx
0x180024f05  lea     rcx, [rbp+var_18]
0x180024f09  mov     [rsp+68h+var_38], rcx
0x180024f0e  mov     dword ptr [rsp+68h+var_40], eax
0x180024f12  mov     [rsp+68h+var_48], 0
0x180024f1b  xor     r9d, r9d
0x180024f1e  xor     r8d, r8d
0x180024f21  xor     edx, edx
0x180024f23  mov     rcx, [rbp+var_20]
0x180024f27  call    cs:__imp_SelectStorageVolumeEx
0x180024f2d  mov     ebx, eax
0x180024f2f  test    eax, eax
0x180024f31  js      short loc_180024F5D
0x180024f33  lea     rax, [rbp+var_18]
0x180024f37  mov     [rsp+68h+var_40], rax
0x180024f3c  mov     [rsp+68h+var_48], rdi
0x180024f41  lea     r9, [rbp+var_10]
0x180024f45  lea     r8, word_180092AF0
0x180024f4c  mov     edx, 1Eh
0x180024f51  mov     rcx, [rbp+var_20]
0x180024f55  call    cs:__imp_FindNextStorageTypeEx
0x180024f5b  mov     ebx, eax
0x180024f5d  cmp     [rbp+var_20], 0
0x180024f62  jz      short loc_180024F6F
0x180024f64  lea     rcx, [rbp+var_20]
0x180024f68  call    cs:__imp_CloseFindStorageSearch
0x180024f6e  nop
0x180024f6f  mov     al, [rbp+var_28]
0x180024f72  test    al, al
0x180024f74  mov     [rbp+var_28], 0
0x180024f78  jz      short loc_180024F80
0x180024f7a  call    cs:__imp_RpcRevertToSelf
0x180024f80  mov     eax, ebx
0x180024f82  add     rsp, 68h
0x180024f86  pop     rdi
0x180024f87  pop     rsi
0x180024f88  pop     rbx
0x180024f89  pop     rbp
0x180024f8a  retn
```
