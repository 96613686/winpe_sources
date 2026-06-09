# StateRepository::Cache::Entity::PackageFamilyIndexIterator_NoThrow::OpenByPackageSIDAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x1800c9c54`
- end: `0x1800c9f12`
- name: `?OpenByPackageSIDAsString@PackageFamilyIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `702`
- prototype: `int(StateRepository::Cache::Entity::PackageFamilyIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18006995c`

## callees

- `0x180058520`
- `0x180058768`
- `0x1800c9c54`
- `0x1800caf60`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800c9cd0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800c9cd0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c9c97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c9cf4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c9d43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c9d8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c9ee4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c9c97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c9cf4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c9d43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c9d8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c9ee4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c9e0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c9eb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c9ecf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c9e0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c9eb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c9ecf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800c9e60`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800c9e60`

## string_xrefs

- `0x1800c9d20`: `onecore\private\base\inc\appmodel\StateRepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800c9d63`: `onecore\private\base\inc\appmodel\StateRepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800c9dec`: `onecore\private\base\inc\appmodel\StateRepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800c9e8e`: `onecore\private\base\inc\appmodel\StateRepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800c9cb2`: `PackageFamily\Index\PackageSID`
- `0x1800c9e59`: `PackageFamily\Index\PackageSID`
- `0x1800c9d05`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800c9e73`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamilyIndexIterator_NoThrow::OpenByPackageSIDAsString(
        StateRepository::Cache::Entity::PackageFamilyIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rcx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int *v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  char v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+268h] [rbp+168h]
  __int64 v31; // [rsp+270h] [rbp+170h]
  _BYTE *v32; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close(v4);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v25 = &v24;
  v24 = 0;
  v26 = 0;
  v27 = 1;
  v8 = SRCacheContext_Open(v7, L"PackageFamily\\Index\\PackageSID", 0, &v26);
  if ( v27 )
  {
    v9 = *v25;
    *v25 = v26;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      (int)v20);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29A,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\StateRepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v8,
      v21);
LABEL_8:
    v10 = v24;
    v24 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !v24 )
  {
    v12 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\StateRepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)0x80670012LL,
      (int)v20);
LABEL_13:
    v13 = v24;
    v24 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    return v12;
  }
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v30 = 0;
  v32 = v29;
  v31 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, a3);
  if ( v8 < 0 )
  {
    v14 = 670;
    goto LABEL_18;
  }
  v20 = &v23;
  LOBYTE(v23) = 0;
  v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(this, &v24, v32);
  if ( v8 < 0 )
  {
    v14 = 673;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\StateRepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v8,
      (int)v20);
    v15 = v28;
    v28 = 0;
    if ( v15 )
      SRCache_Free(v15);
    goto LABEL_8;
  }
  if ( (_BYTE)v23 )
    *((_QWORD *)this + 2) = a2;
  v16 = SRCacheContext_AddToCache(v24, L"PackageFamily\\Index\\PackageSID");
  v12 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      (int)&v23);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\StateRepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)v12,
      v22);
    v17 = v28;
    v28 = 0;
    if ( v17 )
      SRCache_Free(v17);
    goto LABEL_13;
  }
  v18 = v28;
  v28 = 0;
  if ( v18 )
    SRCache_Free(v18);
  v19 = v24;
  v24 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  return 0;
}

```

## disassembly

```asm
0x1800c9c54  mov     [rsp-8+arg_18], rbx
0x1800c9c59  push    rbp
0x1800c9c5a  push    rsi
0x1800c9c5b  push    rdi
0x1800c9c5c  push    r14
0x1800c9c5e  push    r15
0x1800c9c60  lea     rbp, [rsp-190h]
0x1800c9c68  sub     rsp, 290h
0x1800c9c6f  mov     rax, cs:__security_cookie
0x1800c9c76  xor     rax, rsp
0x1800c9c79  mov     [rbp+1B0h+var_30], rax
0x1800c9c80  mov     rbx, rcx
0x1800c9c83  xor     r15d, r15d
0x1800c9c86  mov     rcx, [rcx]
0x1800c9c89  mov     r14, r8
0x1800c9c8c  mov     rsi, rdx
0x1800c9c8f  mov     [rbx], r15
0x1800c9c92  test    rcx, rcx
0x1800c9c95  jz      short loc_1800C9C9D
0x1800c9c97  call    cs:__imp_SRCacheContext_Close
0x1800c9c9d  mov     [rbx+8], r15d
0x1800c9ca1  lea     rax, [rsp+2B0h+var_278]
0x1800c9ca6  mov     [rbx+10h], r15
0x1800c9caa  lea     r9, [rsp+2B0h+var_268]
0x1800c9caf  mov     rcx, [rsi]
0x1800c9cb2  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageSID"
0x1800c9cb9  xor     r8d, r8d
0x1800c9cbc  mov     [rsp+2B0h+var_270], rax
0x1800c9cc1  mov     [rsp+2B0h+var_278], r15
0x1800c9cc6  mov     [rsp+2B0h+var_268], r15
0x1800c9ccb  mov     [rsp+2B0h+var_260], 1
0x1800c9cd0  call    cs:__imp_SRCacheContext_Open
0x1800c9cd6  mov     edi, eax
0x1800c9cd8  cmp     [rsp+2B0h+var_260], r15b
0x1800c9cdd  jz      short loc_1800C9CFA
0x1800c9cdf  mov     r8, [rsp+2B0h+var_270]
0x1800c9ce4  mov     rdx, [rsp+2B0h+var_268]
0x1800c9ce9  mov     rcx, [r8]
0x1800c9cec  mov     [r8], rdx
0x1800c9cef  test    rcx, rcx
0x1800c9cf2  jz      short loc_1800C9CFA
0x1800c9cf4  call    cs:__imp_SRCacheContext_Close
0x1800c9cfa  test    edi, edi
0x1800c9cfc  jns     short loc_1800C9D50
0x1800c9cfe  mov     rcx, [rbp+1B8h]; this
0x1800c9d05  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800c9d0c  mov     r9d, edi; char *
0x1800c9d0f  mov     edx, 18Ch; void *
0x1800c9d14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9d19  mov     rcx, [rbp+1B8h]; this
0x1800c9d20  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800c9d27  mov     r9d, edi; char *
0x1800c9d2a  mov     edx, 29Ah; void *
0x1800c9d2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9d34  mov     rcx, [rsp+2B0h+var_278]
0x1800c9d39  mov     [rsp+2B0h+var_278], r15
0x1800c9d3e  test    rcx, rcx
0x1800c9d41  jz      short loc_1800C9D49
0x1800c9d43  call    cs:__imp_SRCacheContext_Close
0x1800c9d49  mov     eax, edi
0x1800c9d4b  jmp     loc_1800C9EEC
0x1800c9d50  cmp     [rsp+2B0h+var_278], r15
0x1800c9d55  setnz   al
0x1800c9d58  test    al, al
0x1800c9d5a  jnz     short loc_1800C9D98
0x1800c9d5c  mov     rcx, [rbp+1B8h]; this
0x1800c9d63  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800c9d6a  mov     ebx, 80670012h
0x1800c9d6f  mov     edx, 29Bh; void *
0x1800c9d74  mov     r9d, ebx; char *
0x1800c9d77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9d7c  mov     rcx, [rsp+2B0h+var_278]
0x1800c9d81  mov     [rsp+2B0h+var_278], r15
0x1800c9d86  test    rcx, rcx
0x1800c9d89  jz      short loc_1800C9D91
0x1800c9d8b  call    cs:__imp_SRCacheContext_Close
0x1800c9d91  mov     eax, ebx
0x1800c9d93  jmp     loc_1800C9EEC
0x1800c9d98  xor     edx, edx; Val
0x1800c9d9a  mov     [rsp+2B0h+var_250], r15
0x1800c9d9f  mov     r8d, 200h; Size
0x1800c9da5  lea     rcx, [rsp+2B0h+var_248]; void *
0x1800c9daa  call    memset_0
0x1800c9daf  lea     rax, [rsp+2B0h+var_248]
0x1800c9db4  mov     [rbp+1B0h+var_48], r15
0x1800c9dbb  mov     rdx, r14; unsigned __int16 *
0x1800c9dbe  mov     [rbp+1B0h+var_38], rax
0x1800c9dc5  lea     rcx, [rsp+2B0h+var_250]; this
0x1800c9dca  mov     [rbp+1B0h+var_40], 100h
0x1800c9dd5  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800c9dda  mov     edi, eax
0x1800c9ddc  test    eax, eax
0x1800c9dde  jns     short loc_1800C9E19
0x1800c9de0  mov     edx, 29Eh; void *
0x1800c9de5  mov     rcx, [rbp+1B8h]; this
0x1800c9dec  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800c9df3  mov     r9d, edi; char *
0x1800c9df6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9dfb  mov     rcx, [rsp+2B0h+var_250]
0x1800c9e00  mov     [rsp+2B0h+var_250], r15
0x1800c9e05  test    rcx, rcx
0x1800c9e08  jz      loc_1800C9D34
0x1800c9e0e  call    cs:__imp_SRCache_Free
0x1800c9e14  jmp     loc_1800C9D34
0x1800c9e19  mov     r8, [rbp+1B0h+var_38]
0x1800c9e20  lea     rax, [rsp+2B0h+var_280]
0x1800c9e25  lea     rdx, [rsp+2B0h+var_278]
0x1800c9e2a  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x1800c9e2f  mov     rcx, rbx
0x1800c9e32  mov     byte ptr [rsp+2B0h+var_280], r15b
0x1800c9e37  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800c9e3c  mov     edi, eax
0x1800c9e3e  test    eax, eax
0x1800c9e40  jns     short loc_1800C9E49
0x1800c9e42  mov     edx, 2A1h
0x1800c9e47  jmp     short loc_1800C9DE5
0x1800c9e49  cmp     byte ptr [rsp+2B0h+var_280], r15b
0x1800c9e4e  jz      short loc_1800C9E54
0x1800c9e50  mov     [rbx+10h], rsi
0x1800c9e54  mov     rcx, [rsp+2B0h+var_278]
0x1800c9e59  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageSID"
0x1800c9e60  call    cs:__imp_SRCacheContext_AddToCache
0x1800c9e66  mov     ebx, eax
0x1800c9e68  test    eax, eax
0x1800c9e6a  jns     short loc_1800C9EC0
0x1800c9e6c  mov     rcx, [rbp+1B8h]; this
0x1800c9e73  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800c9e7a  mov     r9d, eax; char *
0x1800c9e7d  mov     edx, 1A6h; void *
0x1800c9e82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9e87  mov     rcx, [rbp+1B8h]; this
0x1800c9e8e  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800c9e95  mov     r9d, ebx; char *
0x1800c9e98  mov     edx, 2A7h; void *
0x1800c9e9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9ea2  mov     rcx, [rsp+2B0h+var_250]
0x1800c9ea7  mov     [rsp+2B0h+var_250], r15
0x1800c9eac  test    rcx, rcx
0x1800c9eaf  jz      loc_1800C9D7C
0x1800c9eb5  call    cs:__imp_SRCache_Free
0x1800c9ebb  jmp     loc_1800C9D7C
0x1800c9ec0  mov     rcx, [rsp+2B0h+var_250]
0x1800c9ec5  mov     [rsp+2B0h+var_250], r15
0x1800c9eca  test    rcx, rcx
0x1800c9ecd  jz      short loc_1800C9ED5
0x1800c9ecf  call    cs:__imp_SRCache_Free
0x1800c9ed5  mov     rcx, [rsp+2B0h+var_278]
0x1800c9eda  mov     [rsp+2B0h+var_278], r15
0x1800c9edf  test    rcx, rcx
0x1800c9ee2  jz      short loc_1800C9EEA
0x1800c9ee4  call    cs:__imp_SRCacheContext_Close
0x1800c9eea  xor     eax, eax
0x1800c9eec  mov     rcx, [rbp+1B0h+var_30]
0x1800c9ef3  xor     rcx, rsp; StackCookie
0x1800c9ef6  call    __security_check_cookie
0x1800c9efb  mov     rbx, [rsp+2B0h+arg_18]
0x1800c9f03  add     rsp, 290h
0x1800c9f0a  pop     r15
0x1800c9f0c  pop     r14
0x1800c9f0e  pop     rdi
0x1800c9f0f  pop     rsi
0x1800c9f10  pop     rbp
0x1800c9f11  retn
```
