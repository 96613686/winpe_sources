# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)

- ea: `0x18002d8f8`
- end: `0x18002dbb0`
- name: `?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z`
- size: `696`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002dbb8`

## callees

- `0x1800055d0`
- `0x180007be0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000b430`
- `0x18000df70`
- `0x18000e960`
- `0x18002d8f8`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d9b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002daeb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002db4c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002db82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d9b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002daeb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002db4c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002db82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002da4b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002db67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002da4b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002db67`

## string_xrefs

- `0x18002d93c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002d996`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002da29`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002dac9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4)
{
  int v4; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // [rsp+20h] [rbp-E0h]
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( a3 )
  {
    LOBYTE(v9) = 0;
    v10 = 0;
    v4 = StateRepository::Cache::Context_NoThrow::Open(&v10, a1, L"PackageExternalLocation\\Index\\UserAndPackage");
    if ( v4 >= 0 )
    {
      v4 = -2140733422;
      v6 = 186;
    }
    else
    {
      v6 = 185;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v4,
      (int)&v9);
    v7 = v10;
    v10 = 0;
    if ( v7 )
      SRCacheContext_Close(v7);
  }
  else
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)0x80070057LL,
      v8);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002d8f8  push    rbp
0x18002d8fa  push    rbx
0x18002d8fb  push    rsi
0x18002d8fc  push    rdi
0x18002d8fd  push    r14
0x18002d8ff  push    r15
0x18002d901  lea     rbp, [rsp-188h]
0x18002d909  sub     rsp, 288h
0x18002d910  mov     rax, cs:__security_cookie
0x18002d917  xor     rax, rsp
0x18002d91a  mov     [rbp+1B0h+var_40], rax
0x18002d921  xor     r15d, r15d
0x18002d924  mov     rsi, r9
0x18002d927  mov     [r9], r15
0x18002d92a  mov     rdi, r8
0x18002d92d  mov     r14, rdx
0x18002d930  test    r8, r8
0x18002d933  jnz     short loc_18002D95C
0x18002d935  mov     rcx, [rbp+1B8h]; this
0x18002d93c  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d943  mov     ebx, 80070057h
0x18002d948  mov     edx, 0B5h; void *
0x18002d94d  mov     r9d, ebx; char *
0x18002d950  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d955  mov     eax, ebx
0x18002d957  jmp     loc_18002DB90
0x18002d95c  lea     rax, [rsp+2B0h+var_280]
0x18002d961  mov     byte ptr [rsp+2B0h+var_280], r15b
0x18002d966  mov     rdx, rcx
0x18002d969  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18002d96e  lea     rcx, [rsp+2B0h+var_278]
0x18002d973  mov     [rsp+2B0h+var_278], r15
0x18002d978  lea     r8, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18002d97f  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18002d984  mov     ebx, eax
0x18002d986  test    eax, eax
0x18002d988  jns     short loc_18002D9C2
0x18002d98a  mov     edx, 0B9h; void *
0x18002d98f  mov     rcx, [rbp+1B8h]; this
0x18002d996  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d99d  mov     r9d, ebx; char *
0x18002d9a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d9a5  mov     rcx, [rsp+2B0h+var_278]
0x18002d9aa  mov     [rsp+2B0h+var_278], r15
0x18002d9af  test    rcx, rcx
0x18002d9b2  jz      short loc_18002D955
0x18002d9b4  call    cs:__imp_SRCacheContext_Close
0x18002d9bb  nop     dword ptr [rax+rax+00h]
0x18002d9c0  jmp     short loc_18002D955
0x18002d9c2  cmp     byte ptr [rsp+2B0h+var_280], r15b
0x18002d9c7  jnz     short loc_18002D9D5
0x18002d9c9  mov     ebx, 80670012h
0x18002d9ce  mov     edx, 0BAh
0x18002d9d3  jmp     short loc_18002D98F
0x18002d9d5  xor     edx, edx; Val
0x18002d9d7  mov     [rsp+2B0h+var_260], r15
0x18002d9dc  mov     r8d, 200h; Size
0x18002d9e2  lea     rcx, [rsp+2B0h+var_258]; void *
0x18002d9e7  call    memset_0
0x18002d9ec  lea     rax, [rsp+2B0h+var_258]
0x18002d9f1  mov     [rbp+1B0h+var_58], r15
0x18002d9f8  mov     rdx, r14; unsigned __int64
0x18002d9fb  mov     [rbp+1B0h+var_48], rax
0x18002da02  lea     rcx, [rsp+2B0h+var_260]; this
0x18002da07  mov     [rbp+1B0h+var_50], 100h
0x18002da12  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002da17  mov     ebx, eax
0x18002da19  test    eax, eax
0x18002da1b  jns     short loc_18002DA5C
0x18002da1d  mov     edx, 0BDh; void *
0x18002da22  mov     rcx, [rbp+1B8h]; this
0x18002da29  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002da30  mov     r9d, ebx; char *
0x18002da33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002da38  mov     rcx, [rsp+2B0h+var_260]
0x18002da3d  mov     [rsp+2B0h+var_260], r15
0x18002da42  test    rcx, rcx
0x18002da45  jz      loc_18002D9A5
0x18002da4b  call    cs:__imp_SRCache_Free
0x18002da52  nop     dword ptr [rax+rax+00h]
0x18002da57  jmp     loc_18002D9A5
0x18002da5c  lea     rcx, [rsp+2B0h+var_260]; this
0x18002da61  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18002da66  mov     ebx, eax
0x18002da68  test    eax, eax
0x18002da6a  jns     short loc_18002DA73
0x18002da6c  mov     edx, 0BEh
0x18002da71  jmp     short loc_18002DA22
0x18002da73  mov     rdx, rdi; unsigned __int64
0x18002da76  lea     rcx, [rsp+2B0h+var_260]; this
0x18002da7b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002da80  mov     ebx, eax
0x18002da82  test    eax, eax
0x18002da84  jns     short loc_18002DA8D
0x18002da86  mov     edx, 0BFh
0x18002da8b  jmp     short loc_18002DA22
0x18002da8d  mov     r8, [rbp+1B0h+var_48]
0x18002da94  lea     rax, [rsp+2B0h+var_280]
0x18002da99  lea     rdx, [rsp+2B0h+var_278]
0x18002da9e  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18002daa3  lea     rcx, [rsp+2B0h+var_270]
0x18002daa8  mov     [rsp+2B0h+var_270], r15
0x18002daad  mov     byte ptr [rsp+2B0h+var_280], r15b
0x18002dab2  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18002dab7  mov     ebx, eax
0x18002dab9  test    eax, eax
0x18002dabb  jns     short loc_18002DAFC
0x18002dabd  mov     edx, 0C3h; void *
0x18002dac2  mov     rcx, [rbp+1B8h]; this
0x18002dac9  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dad0  mov     r9d, ebx; char *
0x18002dad3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dad8  mov     rcx, [rsp+2B0h+var_270]
0x18002dadd  mov     [rsp+2B0h+var_270], r15
0x18002dae2  test    rcx, rcx
0x18002dae5  jz      loc_18002DA38
0x18002daeb  call    cs:__imp_SRCacheContext_Close
0x18002daf2  nop     dword ptr [rax+rax+00h]
0x18002daf7  jmp     loc_18002DA38
0x18002dafc  cmp     byte ptr [rsp+2B0h+var_280], r15b
0x18002db01  jz      short loc_18002DB1F
0x18002db03  mov     r8, rsi; __int64 *
0x18002db06  lea     rcx, [rsp+2B0h+var_270]; this
0x18002db0b  xor     edx, edx; int
0x18002db0d  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18002db12  mov     ebx, eax
0x18002db14  test    eax, eax
0x18002db16  jns     short loc_18002DB1F
0x18002db18  mov     edx, 0C6h
0x18002db1d  jmp     short loc_18002DAC2
0x18002db1f  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18002db26  lea     rcx, [rsp+2B0h+var_278]; this
0x18002db2b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18002db30  mov     ebx, eax
0x18002db32  test    eax, eax
0x18002db34  jns     short loc_18002DB3D
0x18002db36  mov     edx, 0C9h
0x18002db3b  jmp     short loc_18002DAC2
0x18002db3d  mov     rcx, [rsp+2B0h+var_270]
0x18002db42  mov     [rsp+2B0h+var_270], r15
0x18002db47  test    rcx, rcx
0x18002db4a  jz      short loc_18002DB58
0x18002db4c  call    cs:__imp_SRCacheContext_Close
0x18002db53  nop     dword ptr [rax+rax+00h]
0x18002db58  mov     rcx, [rsp+2B0h+var_260]
0x18002db5d  mov     [rsp+2B0h+var_260], r15
0x18002db62  test    rcx, rcx
0x18002db65  jz      short loc_18002DB73
0x18002db67  call    cs:__imp_SRCache_Free
0x18002db6e  nop     dword ptr [rax+rax+00h]
0x18002db73  mov     rcx, [rsp+2B0h+var_278]
0x18002db78  mov     [rsp+2B0h+var_278], r15
0x18002db7d  test    rcx, rcx
0x18002db80  jz      short loc_18002DB8E
0x18002db82  call    cs:__imp_SRCacheContext_Close
0x18002db89  nop     dword ptr [rax+rax+00h]
0x18002db8e  xor     eax, eax
0x18002db90  mov     rcx, [rbp+1B0h+var_40]
0x18002db97  xor     rcx, rsp; StackCookie
0x18002db9a  call    __security_check_cookie
0x18002db9f  add     rsp, 288h
0x18002dba6  pop     r15
0x18002dba8  pop     r14
0x18002dbaa  pop     rdi
0x18002dbab  pop     rsi
0x18002dbac  pop     rbx
0x18002dbad  pop     rbp
0x18002dbae  retn
```
