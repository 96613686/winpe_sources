# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)

- ea: `0x18002ee48`
- end: `0x18002f100`
- name: `?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z`
- size: `696`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002f108`

## callees

- `0x1800055d0`
- `0x180007be0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000b430`
- `0x18000e030`
- `0x18000ea20`
- `0x18002ee48`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002ef9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002f0b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002ef9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002f0b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ef04`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f03b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f09c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f0d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ef04`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f03b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f09c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f0d2`

## string_xrefs

- `0x18002ee8c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002eee6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002ef79`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002f019`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

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
0x18002ee48  push    rbp
0x18002ee4a  push    rbx
0x18002ee4b  push    rsi
0x18002ee4c  push    rdi
0x18002ee4d  push    r14
0x18002ee4f  push    r15
0x18002ee51  lea     rbp, [rsp-188h]
0x18002ee59  sub     rsp, 288h
0x18002ee60  mov     rax, cs:__security_cookie
0x18002ee67  xor     rax, rsp
0x18002ee6a  mov     [rbp+1B0h+var_40], rax
0x18002ee71  xor     r15d, r15d
0x18002ee74  mov     rsi, r9
0x18002ee77  mov     [r9], r15
0x18002ee7a  mov     rdi, r8
0x18002ee7d  mov     r14, rdx
0x18002ee80  test    r8, r8
0x18002ee83  jnz     short loc_18002EEAC
0x18002ee85  mov     rcx, [rbp+1B8h]; this
0x18002ee8c  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ee93  mov     ebx, 80070057h
0x18002ee98  mov     edx, 0B5h; void *
0x18002ee9d  mov     r9d, ebx; char *
0x18002eea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eea5  mov     eax, ebx
0x18002eea7  jmp     loc_18002F0E0
0x18002eeac  lea     rax, [rsp+2B0h+var_280]
0x18002eeb1  mov     byte ptr [rsp+2B0h+var_280], r15b
0x18002eeb6  mov     rdx, rcx
0x18002eeb9  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18002eebe  lea     rcx, [rsp+2B0h+var_278]
0x18002eec3  mov     [rsp+2B0h+var_278], r15
0x18002eec8  lea     r8, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18002eecf  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18002eed4  mov     ebx, eax
0x18002eed6  test    eax, eax
0x18002eed8  jns     short loc_18002EF12
0x18002eeda  mov     edx, 0B9h; void *
0x18002eedf  mov     rcx, [rbp+1B8h]; this
0x18002eee6  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002eeed  mov     r9d, ebx; char *
0x18002eef0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eef5  mov     rcx, [rsp+2B0h+var_278]
0x18002eefa  mov     [rsp+2B0h+var_278], r15
0x18002eeff  test    rcx, rcx
0x18002ef02  jz      short loc_18002EEA5
0x18002ef04  call    cs:__imp_SRCacheContext_Close
0x18002ef0b  nop     dword ptr [rax+rax+00h]
0x18002ef10  jmp     short loc_18002EEA5
0x18002ef12  cmp     byte ptr [rsp+2B0h+var_280], r15b
0x18002ef17  jnz     short loc_18002EF25
0x18002ef19  mov     ebx, 80670012h
0x18002ef1e  mov     edx, 0BAh
0x18002ef23  jmp     short loc_18002EEDF
0x18002ef25  xor     edx, edx; Val
0x18002ef27  mov     [rsp+2B0h+var_260], r15
0x18002ef2c  mov     r8d, 200h; Size
0x18002ef32  lea     rcx, [rsp+2B0h+var_258]; void *
0x18002ef37  call    memset_0
0x18002ef3c  lea     rax, [rsp+2B0h+var_258]
0x18002ef41  mov     [rbp+1B0h+var_58], r15
0x18002ef48  mov     rdx, r14; unsigned __int64
0x18002ef4b  mov     [rbp+1B0h+var_48], rax
0x18002ef52  lea     rcx, [rsp+2B0h+var_260]; this
0x18002ef57  mov     [rbp+1B0h+var_50], 100h
0x18002ef62  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002ef67  mov     ebx, eax
0x18002ef69  test    eax, eax
0x18002ef6b  jns     short loc_18002EFAC
0x18002ef6d  mov     edx, 0BDh; void *
0x18002ef72  mov     rcx, [rbp+1B8h]; this
0x18002ef79  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ef80  mov     r9d, ebx; char *
0x18002ef83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ef88  mov     rcx, [rsp+2B0h+var_260]
0x18002ef8d  mov     [rsp+2B0h+var_260], r15
0x18002ef92  test    rcx, rcx
0x18002ef95  jz      loc_18002EEF5
0x18002ef9b  call    cs:__imp_SRCache_Free
0x18002efa2  nop     dword ptr [rax+rax+00h]
0x18002efa7  jmp     loc_18002EEF5
0x18002efac  lea     rcx, [rsp+2B0h+var_260]; this
0x18002efb1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18002efb6  mov     ebx, eax
0x18002efb8  test    eax, eax
0x18002efba  jns     short loc_18002EFC3
0x18002efbc  mov     edx, 0BEh
0x18002efc1  jmp     short loc_18002EF72
0x18002efc3  mov     rdx, rdi; unsigned __int64
0x18002efc6  lea     rcx, [rsp+2B0h+var_260]; this
0x18002efcb  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002efd0  mov     ebx, eax
0x18002efd2  test    eax, eax
0x18002efd4  jns     short loc_18002EFDD
0x18002efd6  mov     edx, 0BFh
0x18002efdb  jmp     short loc_18002EF72
0x18002efdd  mov     r8, [rbp+1B0h+var_48]
0x18002efe4  lea     rax, [rsp+2B0h+var_280]
0x18002efe9  lea     rdx, [rsp+2B0h+var_278]
0x18002efee  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18002eff3  lea     rcx, [rsp+2B0h+var_270]
0x18002eff8  mov     [rsp+2B0h+var_270], r15
0x18002effd  mov     byte ptr [rsp+2B0h+var_280], r15b
0x18002f002  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18002f007  mov     ebx, eax
0x18002f009  test    eax, eax
0x18002f00b  jns     short loc_18002F04C
0x18002f00d  mov     edx, 0C3h; void *
0x18002f012  mov     rcx, [rbp+1B8h]; this
0x18002f019  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f020  mov     r9d, ebx; char *
0x18002f023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f028  mov     rcx, [rsp+2B0h+var_270]
0x18002f02d  mov     [rsp+2B0h+var_270], r15
0x18002f032  test    rcx, rcx
0x18002f035  jz      loc_18002EF88
0x18002f03b  call    cs:__imp_SRCacheContext_Close
0x18002f042  nop     dword ptr [rax+rax+00h]
0x18002f047  jmp     loc_18002EF88
0x18002f04c  cmp     byte ptr [rsp+2B0h+var_280], r15b
0x18002f051  jz      short loc_18002F06F
0x18002f053  mov     r8, rsi; __int64 *
0x18002f056  lea     rcx, [rsp+2B0h+var_270]; this
0x18002f05b  xor     edx, edx; int
0x18002f05d  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18002f062  mov     ebx, eax
0x18002f064  test    eax, eax
0x18002f066  jns     short loc_18002F06F
0x18002f068  mov     edx, 0C6h
0x18002f06d  jmp     short loc_18002F012
0x18002f06f  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18002f076  lea     rcx, [rsp+2B0h+var_278]; this
0x18002f07b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18002f080  mov     ebx, eax
0x18002f082  test    eax, eax
0x18002f084  jns     short loc_18002F08D
0x18002f086  mov     edx, 0C9h
0x18002f08b  jmp     short loc_18002F012
0x18002f08d  mov     rcx, [rsp+2B0h+var_270]
0x18002f092  mov     [rsp+2B0h+var_270], r15
0x18002f097  test    rcx, rcx
0x18002f09a  jz      short loc_18002F0A8
0x18002f09c  call    cs:__imp_SRCacheContext_Close
0x18002f0a3  nop     dword ptr [rax+rax+00h]
0x18002f0a8  mov     rcx, [rsp+2B0h+var_260]
0x18002f0ad  mov     [rsp+2B0h+var_260], r15
0x18002f0b2  test    rcx, rcx
0x18002f0b5  jz      short loc_18002F0C3
0x18002f0b7  call    cs:__imp_SRCache_Free
0x18002f0be  nop     dword ptr [rax+rax+00h]
0x18002f0c3  mov     rcx, [rsp+2B0h+var_278]
0x18002f0c8  mov     [rsp+2B0h+var_278], r15
0x18002f0cd  test    rcx, rcx
0x18002f0d0  jz      short loc_18002F0DE
0x18002f0d2  call    cs:__imp_SRCacheContext_Close
0x18002f0d9  nop     dword ptr [rax+rax+00h]
0x18002f0de  xor     eax, eax
0x18002f0e0  mov     rcx, [rbp+1B0h+var_40]
0x18002f0e7  xor     rcx, rsp; StackCookie
0x18002f0ea  call    __security_check_cookie
0x18002f0ef  add     rsp, 288h
0x18002f0f6  pop     r15
0x18002f0f8  pop     r14
0x18002f0fa  pop     rdi
0x18002f0fb  pop     rsi
0x18002f0fc  pop     rbx
0x18002f0fd  pop     rbp
0x18002f0fe  retn
```
