# StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::GetStatusByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::PackageStatus &,bool &)

- ea: `0x1800155dc`
- end: `0x1800156db`
- name: `?GetStatusByPackageFullName@PackageMachineStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEAW4PackageStatus@34@AEA_N@Z`
- size: `255`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, enum StateRepository::Cache::PackageStatus *, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180015ec0`
- `0x180015ff0`

## callees

- `0x1800075e4`
- `0x180014cd8`
- `0x180014ef0`
- `0x1800155dc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001569b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800156c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001569b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800156c0`

## string_xrefs

- `0x180015663`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageMachineStatus.hpp`
- `0x180015676`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageMachineStatus.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::GetStatusByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        enum StateRepository::Cache::PackageStatus *a3,
        bool *a4)
{
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // rcx
  int v13; // [rsp+20h] [rbp-30h]
  int v14; // [rsp+20h] [rbp-30h]
  __int128 v15; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h]
  int v17; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v19; // [rsp+80h] [rbp+30h] BYREF

  *(_DWORD *)a3 = 0;
  v16 = 0;
  v17 = 0;
  v15 = 0;
  *a4 = 0;
  v19 = 0;
  v7 = StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::GetByPackageFullName(a1, a2, &v19);
  if ( v7 < 0 )
  {
    v9 = 233;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageMachineStatus.hpp",
      (const char *)(unsigned int)v7,
      v13);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D3,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageMachineStatus.hpp",
      (const char *)(unsigned int)v7,
      v14);
    v10 = v16;
    v16 = 0;
    if ( v10 )
      SRCache_Free();
    return (unsigned int)v7;
  }
  if ( v19 )
  {
    v7 = StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::Get(a1, v19, v8, (__int64)&v15, a4);
    if ( v7 < 0 )
    {
      v9 = 236;
      goto LABEL_6;
    }
  }
  if ( *a4 )
    *(_DWORD *)a3 = v17;
  v12 = v16;
  v16 = 0;
  if ( v12 )
    SRCache_Free();
  return 0;
}

```

## disassembly

```asm
0x1800155dc  mov     [rsp-18h+arg_0], rbx
0x1800155e1  mov     [rsp-18h+arg_8], rsi
0x1800155e6  push    rbp
0x1800155e7  push    rdi
0x1800155e8  push    r14
0x1800155ea  mov     rbp, rsp
0x1800155ed  sub     rsp, 50h
0x1800155f1  mov     rsi, r8
0x1800155f4  mov     dword ptr [r8], 0
0x1800155fb  xorps   xmm0, xmm0
0x1800155fe  mov     [rbp+var_10], 0
0x180015606  lea     r8, [rbp+arg_10]; __int64 *
0x18001560a  mov     [rbp+var_8], 0
0x180015611  movdqu  [rbp+var_20], xmm0
0x180015616  mov     rdi, r9
0x180015619  mov     byte ptr [r9], 0
0x18001561d  mov     r14, rcx
0x180015620  mov     [rbp+arg_10], 0
0x180015628  call    ?GetByPackageFullName@PackageMachineStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18001562d  mov     ebx, eax
0x18001562f  test    eax, eax
0x180015631  jns     short loc_18001563A
0x180015633  mov     edx, 0E9h
0x180015638  jmp     short loc_18001565F
0x18001563a  mov     rdx, [rbp+arg_10]
0x18001563e  test    rdx, rdx
0x180015641  jz      short loc_1800156A5
0x180015643  lea     r9, [rbp+var_20]
0x180015647  mov     qword ptr [rsp+50h+var_30], rdi; int
0x18001564c  mov     rcx, r14
0x18001564f  call    ?Get@PackageMachineStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageMachineStatus_NoThrow &,bool &)
0x180015654  mov     ebx, eax
0x180015656  test    eax, eax
0x180015658  jns     short loc_1800156A5
0x18001565a  mov     edx, 0ECh; void *
0x18001565f  mov     rcx, [rbp+18h]; this
0x180015663  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x18001566a  mov     r9d, ebx; char *
0x18001566d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015672  mov     rcx, [rbp+18h]; this
0x180015676  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x18001567d  mov     r9d, ebx; char *
0x180015680  mov     edx, 2D3h; void *
0x180015685  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001568a  mov     rcx, [rbp+var_10]
0x18001568e  mov     [rbp+var_10], 0
0x180015696  test    rcx, rcx
0x180015699  jz      short loc_1800156A1
0x18001569b  call    cs:__imp_SRCache_Free
0x1800156a1  mov     eax, ebx
0x1800156a3  jmp     short loc_1800156C8
0x1800156a5  cmp     byte ptr [rdi], 0
0x1800156a8  jz      short loc_1800156AF
0x1800156aa  mov     eax, [rbp+var_8]
0x1800156ad  mov     [rsi], eax
0x1800156af  mov     rcx, [rbp+var_10]
0x1800156b3  mov     [rbp+var_10], 0
0x1800156bb  test    rcx, rcx
0x1800156be  jz      short loc_1800156C6
0x1800156c0  call    cs:__imp_SRCache_Free
0x1800156c6  xor     eax, eax
0x1800156c8  mov     rbx, [rsp+50h+arg_0]
0x1800156cd  mov     rsi, [rsp+50h+arg_8]
0x1800156d2  add     rsp, 50h
0x1800156d6  pop     r14
0x1800156d8  pop     rdi
0x1800156d9  pop     rbp
0x1800156da  retn
```
