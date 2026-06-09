# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)

- ea: `0x18002d828`
- end: `0x18002dae0`
- name: `?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z`
- size: `696`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002dae8`

## callees

- `0x1800055d0`
- `0x180007be0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000b430`
- `0x18000df70`
- `0x18000e960`
- `0x18002d828`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d8e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002da1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002da7c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dab2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d8e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002da1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002da7c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dab2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d97b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002da97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d97b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002da97`

## string_xrefs

- `0x18002d86c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002d8c6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002d959`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002d9f9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

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
0x18002d828  push    rbp
0x18002d82a  push    rbx
0x18002d82b  push    rsi
0x18002d82c  push    rdi
0x18002d82d  push    r14
0x18002d82f  push    r15
0x18002d831  lea     rbp, [rsp-188h]
0x18002d839  sub     rsp, 288h
0x18002d840  mov     rax, cs:__security_cookie
0x18002d847  xor     rax, rsp
0x18002d84a  mov     [rbp+1B0h+var_40], rax
0x18002d851  xor     r15d, r15d
0x18002d854  mov     rsi, r9
0x18002d857  mov     [r9], r15
0x18002d85a  mov     rdi, r8
0x18002d85d  mov     r14, rdx
0x18002d860  test    r8, r8
0x18002d863  jnz     short loc_18002D88C
0x18002d865  mov     rcx, [rbp+1B8h]; this
0x18002d86c  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d873  mov     ebx, 80070057h
0x18002d878  mov     edx, 0B5h; void *
0x18002d87d  mov     r9d, ebx; char *
0x18002d880  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d885  mov     eax, ebx
0x18002d887  jmp     loc_18002DAC0
0x18002d88c  lea     rax, [rsp+2B0h+var_280]
0x18002d891  mov     byte ptr [rsp+2B0h+var_280], r15b
0x18002d896  mov     rdx, rcx
0x18002d899  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18002d89e  lea     rcx, [rsp+2B0h+var_278]
0x18002d8a3  mov     [rsp+2B0h+var_278], r15
0x18002d8a8  lea     r8, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18002d8af  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18002d8b4  mov     ebx, eax
0x18002d8b6  test    eax, eax
0x18002d8b8  jns     short loc_18002D8F2
0x18002d8ba  mov     edx, 0B9h; void *
0x18002d8bf  mov     rcx, [rbp+1B8h]; this
0x18002d8c6  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d8cd  mov     r9d, ebx; char *
0x18002d8d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d8d5  mov     rcx, [rsp+2B0h+var_278]
0x18002d8da  mov     [rsp+2B0h+var_278], r15
0x18002d8df  test    rcx, rcx
0x18002d8e2  jz      short loc_18002D885
0x18002d8e4  call    cs:__imp_SRCacheContext_Close
0x18002d8eb  nop     dword ptr [rax+rax+00h]
0x18002d8f0  jmp     short loc_18002D885
0x18002d8f2  cmp     byte ptr [rsp+2B0h+var_280], r15b
0x18002d8f7  jnz     short loc_18002D905
0x18002d8f9  mov     ebx, 80670012h
0x18002d8fe  mov     edx, 0BAh
0x18002d903  jmp     short loc_18002D8BF
0x18002d905  xor     edx, edx; Val
0x18002d907  mov     [rsp+2B0h+var_260], r15
0x18002d90c  mov     r8d, 200h; Size
0x18002d912  lea     rcx, [rsp+2B0h+var_258]; void *
0x18002d917  call    memset_0
0x18002d91c  lea     rax, [rsp+2B0h+var_258]
0x18002d921  mov     [rbp+1B0h+var_58], r15
0x18002d928  mov     rdx, r14; unsigned __int64
0x18002d92b  mov     [rbp+1B0h+var_48], rax
0x18002d932  lea     rcx, [rsp+2B0h+var_260]; this
0x18002d937  mov     [rbp+1B0h+var_50], 100h
0x18002d942  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002d947  mov     ebx, eax
0x18002d949  test    eax, eax
0x18002d94b  jns     short loc_18002D98C
0x18002d94d  mov     edx, 0BDh; void *
0x18002d952  mov     rcx, [rbp+1B8h]; this
0x18002d959  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d960  mov     r9d, ebx; char *
0x18002d963  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d968  mov     rcx, [rsp+2B0h+var_260]
0x18002d96d  mov     [rsp+2B0h+var_260], r15
0x18002d972  test    rcx, rcx
0x18002d975  jz      loc_18002D8D5
0x18002d97b  call    cs:__imp_SRCache_Free
0x18002d982  nop     dword ptr [rax+rax+00h]
0x18002d987  jmp     loc_18002D8D5
0x18002d98c  lea     rcx, [rsp+2B0h+var_260]; this
0x18002d991  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18002d996  mov     ebx, eax
0x18002d998  test    eax, eax
0x18002d99a  jns     short loc_18002D9A3
0x18002d99c  mov     edx, 0BEh
0x18002d9a1  jmp     short loc_18002D952
0x18002d9a3  mov     rdx, rdi; unsigned __int64
0x18002d9a6  lea     rcx, [rsp+2B0h+var_260]; this
0x18002d9ab  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002d9b0  mov     ebx, eax
0x18002d9b2  test    eax, eax
0x18002d9b4  jns     short loc_18002D9BD
0x18002d9b6  mov     edx, 0BFh
0x18002d9bb  jmp     short loc_18002D952
0x18002d9bd  mov     r8, [rbp+1B0h+var_48]
0x18002d9c4  lea     rax, [rsp+2B0h+var_280]
0x18002d9c9  lea     rdx, [rsp+2B0h+var_278]
0x18002d9ce  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18002d9d3  lea     rcx, [rsp+2B0h+var_270]
0x18002d9d8  mov     [rsp+2B0h+var_270], r15
0x18002d9dd  mov     byte ptr [rsp+2B0h+var_280], r15b
0x18002d9e2  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18002d9e7  mov     ebx, eax
0x18002d9e9  test    eax, eax
0x18002d9eb  jns     short loc_18002DA2C
0x18002d9ed  mov     edx, 0C3h; void *
0x18002d9f2  mov     rcx, [rbp+1B8h]; this
0x18002d9f9  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002da00  mov     r9d, ebx; char *
0x18002da03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002da08  mov     rcx, [rsp+2B0h+var_270]
0x18002da0d  mov     [rsp+2B0h+var_270], r15
0x18002da12  test    rcx, rcx
0x18002da15  jz      loc_18002D968
0x18002da1b  call    cs:__imp_SRCacheContext_Close
0x18002da22  nop     dword ptr [rax+rax+00h]
0x18002da27  jmp     loc_18002D968
0x18002da2c  cmp     byte ptr [rsp+2B0h+var_280], r15b
0x18002da31  jz      short loc_18002DA4F
0x18002da33  mov     r8, rsi; __int64 *
0x18002da36  lea     rcx, [rsp+2B0h+var_270]; this
0x18002da3b  xor     edx, edx; int
0x18002da3d  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18002da42  mov     ebx, eax
0x18002da44  test    eax, eax
0x18002da46  jns     short loc_18002DA4F
0x18002da48  mov     edx, 0C6h
0x18002da4d  jmp     short loc_18002D9F2
0x18002da4f  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18002da56  lea     rcx, [rsp+2B0h+var_278]; this
0x18002da5b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18002da60  mov     ebx, eax
0x18002da62  test    eax, eax
0x18002da64  jns     short loc_18002DA6D
0x18002da66  mov     edx, 0C9h
0x18002da6b  jmp     short loc_18002D9F2
0x18002da6d  mov     rcx, [rsp+2B0h+var_270]
0x18002da72  mov     [rsp+2B0h+var_270], r15
0x18002da77  test    rcx, rcx
0x18002da7a  jz      short loc_18002DA88
0x18002da7c  call    cs:__imp_SRCacheContext_Close
0x18002da83  nop     dword ptr [rax+rax+00h]
0x18002da88  mov     rcx, [rsp+2B0h+var_260]
0x18002da8d  mov     [rsp+2B0h+var_260], r15
0x18002da92  test    rcx, rcx
0x18002da95  jz      short loc_18002DAA3
0x18002da97  call    cs:__imp_SRCache_Free
0x18002da9e  nop     dword ptr [rax+rax+00h]
0x18002daa3  mov     rcx, [rsp+2B0h+var_278]
0x18002daa8  mov     [rsp+2B0h+var_278], r15
0x18002daad  test    rcx, rcx
0x18002dab0  jz      short loc_18002DABE
0x18002dab2  call    cs:__imp_SRCacheContext_Close
0x18002dab9  nop     dword ptr [rax+rax+00h]
0x18002dabe  xor     eax, eax
0x18002dac0  mov     rcx, [rbp+1B0h+var_40]
0x18002dac7  xor     rcx, rsp; StackCookie
0x18002daca  call    __security_check_cookie
0x18002dacf  add     rsp, 288h
0x18002dad6  pop     r15
0x18002dad8  pop     r14
0x18002dada  pop     rdi
0x18002dadb  pop     rsi
0x18002dadc  pop     rbx
0x18002dadd  pop     rbp
0x18002dade  retn
```
