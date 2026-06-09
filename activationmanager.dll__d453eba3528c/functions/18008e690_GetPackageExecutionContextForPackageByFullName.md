# GetPackageExecutionContextForPackageByFullName

- ea: `0x18008e690`
- end: `0x18008e7fb`
- name: `GetPackageExecutionContextForPackageByFullName`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000b5c0`
- `0x18002c900`
- `0x18002d5e0`
- `0x180037d38`
- `0x18008e690`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18008e6d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18008e6d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18008e721`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18008e7db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18008e721`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18008e7db`

## string_xrefs

- `0x18008e701`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18008e790`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18008e6e9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall GetPackageExecutionContextForPackageByFullName(__int64 a1, _DWORD *a2)
{
  int v4; // ebx
  __int64 v5; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // [rsp+20h] [rbp-59h]
  int v10; // [rsp+20h] [rbp-59h]
  __int64 *v11; // [rsp+30h] [rbp-49h] BYREF
  __int64 v12; // [rsp+38h] [rbp-41h] BYREF
  char v13; // [rsp+40h] [rbp-39h]
  __int128 v14; // [rsp+50h] [rbp-29h] BYREF
  __int64 v15; // [rsp+60h] [rbp-19h]
  __int128 v16; // [rsp+68h] [rbp-11h]
  __int64 v17; // [rsp+78h] [rbp-1h]
  __int64 v18; // [rsp+80h] [rbp+7h]
  __int64 v19; // [rsp+88h] [rbp+Fh]
  __int128 v20; // [rsp+90h] [rbp+17h]
  int v21; // [rsp+A0h] [rbp+27h]
  __int64 v22; // [rsp+A8h] [rbp+2Fh]
  __int64 v23; // [rsp+B0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  int v25; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v26; // [rsp+F0h] [rbp+77h] BYREF

  v13 = 1;
  *a2 = 0;
  v26 = 0;
  v11 = &v26;
  v12 = 0;
  v4 = SRCacheManager_Open(0, &v12);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v11);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v4,
      v9);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
      (const char *)(unsigned int)v4,
      v10);
LABEL_3:
    v5 = v26;
    v26 = 0;
    if ( v5 )
      SRCacheManager_Close(v5);
    return (unsigned int)v4;
  }
  LOBYTE(v25) = 0;
  v14 = 0;
  v20 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v16 = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v4 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(&v26, a1, 16, &v14);
  if ( v4 < 0 )
  {
    v7 = 66;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
      (const char *)(unsigned int)v4,
      (int)&v25);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v14);
    goto LABEL_3;
  }
  if ( !(_BYTE)v25 )
  {
    v4 = -2147024894;
    v7 = 67;
    goto LABEL_8;
  }
  *a2 = 1;
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v14);
  v8 = v26;
  v26 = 0;
  if ( v8 )
    SRCacheManager_Close(v8);
  return 0;
}

```

## disassembly

```asm
0x18008e690  mov     [rsp-8+arg_0], rbx
0x18008e695  mov     [rsp-8+arg_18], rsi
0x18008e69a  push    rbp
0x18008e69b  push    rdi
0x18008e69c  push    r14
0x18008e69e  lea     rbp, [rsp-47h]
0x18008e6a3  sub     rsp, 0C0h
0x18008e6aa  xor     r14d, r14d
0x18008e6ad  mov     [rbp+57h+var_90], 1
0x18008e6b1  mov     [rdx], r14d
0x18008e6b4  lea     rax, [rbp+57h+arg_10]
0x18008e6b8  mov     rdi, rdx
0x18008e6bb  mov     [rbp+57h+arg_10], r14
0x18008e6bf  mov     rsi, rcx
0x18008e6c2  mov     [rbp+57h+var_A0], rax
0x18008e6c6  lea     rdx, [rbp+57h+var_98]
0x18008e6ca  mov     [rbp+57h+var_98], r14
0x18008e6ce  xor     ecx, ecx
0x18008e6d0  call    cs:__imp_SRCacheManager_Open
0x18008e6d6  lea     rcx, [rbp+57h+var_A0]
0x18008e6da  mov     ebx, eax
0x18008e6dc  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18008e6e1  test    ebx, ebx
0x18008e6e3  jns     short loc_18008E72E
0x18008e6e5  mov     rcx, [rbp+5Fh]; this
0x18008e6e9  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008e6f0  mov     r9d, ebx; char *
0x18008e6f3  mov     edx, 0A5h; void *
0x18008e6f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e6fd  mov     rcx, [rbp+5Fh]; this
0x18008e701  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008e708  mov     r9d, ebx; char *
0x18008e70b  lea     edx, [r14+3Dh]; void *
0x18008e70f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e714  mov     rcx, [rbp+57h+arg_10]
0x18008e718  mov     [rbp+57h+arg_10], r14
0x18008e71c  test    rcx, rcx
0x18008e71f  jz      short loc_18008E727
0x18008e721  call    cs:__imp_SRCacheManager_Close
0x18008e727  mov     eax, ebx
0x18008e729  jmp     loc_18008E7E3
0x18008e72e  xorps   xmm0, xmm0
0x18008e731  mov     byte ptr [rbp+57h+arg_8], r14b
0x18008e735  xorps   xmm1, xmm1
0x18008e738  movdqa  [rbp+57h+var_80], xmm0
0x18008e73d  lea     rax, [rbp+57h+arg_8]
0x18008e741  movdqa  [rbp+57h+var_40], xmm0
0x18008e746  lea     r9, [rbp+57h+var_80]
0x18008e74a  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18008e74f  mov     r8d, 10h
0x18008e755  mov     [rbp+57h+var_70], r14
0x18008e759  mov     rdx, rsi
0x18008e75c  mov     [rbp+57h+var_58], r14
0x18008e760  lea     rcx, [rbp+57h+arg_10]
0x18008e764  mov     [rbp+57h+var_50], r14
0x18008e768  movups  [rbp+57h+var_68], xmm1
0x18008e76c  mov     [rbp+57h+var_48], r14
0x18008e770  mov     [rbp+57h+var_30], r14d
0x18008e774  mov     [rbp+57h+var_28], r14
0x18008e778  mov     [rbp+57h+var_20], r14
0x18008e77c  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18008e781  mov     ebx, eax
0x18008e783  test    eax, eax
0x18008e785  jns     short loc_18008E7AD
0x18008e787  mov     edx, 42h ; 'B'; void *
0x18008e78c  mov     rcx, [rbp+5Fh]; this
0x18008e790  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008e797  mov     r9d, ebx; char *
0x18008e79a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e79f  lea     rcx, [rbp+57h+var_80]; this
0x18008e7a3  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18008e7a8  jmp     loc_18008E714
0x18008e7ad  cmp     byte ptr [rbp+57h+arg_8], r14b
0x18008e7b1  jnz     short loc_18008E7BF
0x18008e7b3  mov     ebx, 80070002h
0x18008e7b8  mov     edx, 43h ; 'C'
0x18008e7bd  jmp     short loc_18008E78C
0x18008e7bf  lea     rcx, [rbp+57h+var_80]; this
0x18008e7c3  mov     dword ptr [rdi], 1
0x18008e7c9  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18008e7ce  mov     rcx, [rbp+57h+arg_10]
0x18008e7d2  mov     [rbp+57h+arg_10], r14
0x18008e7d6  test    rcx, rcx
0x18008e7d9  jz      short loc_18008E7E1
0x18008e7db  call    cs:__imp_SRCacheManager_Close
0x18008e7e1  xor     eax, eax
0x18008e7e3  lea     r11, [rsp+0D0h+var_10]
0x18008e7eb  mov     rbx, [r11+20h]
0x18008e7ef  mov     rsi, [r11+38h]
0x18008e7f3  mov     rsp, r11
0x18008e7f6  pop     r14
0x18008e7f8  pop     rdi
0x18008e7f9  pop     rbp
0x18008e7fa  retn
```
