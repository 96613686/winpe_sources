# StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18008e0ec`
- end: `0x18008e2a9`
- name: `?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `445`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18008de44`

## callees

- `0x180008be0`
- `0x18000b5c0`
- `0x18000cb80`
- `0x18002f830`
- `0x1800304a0`
- `0x18005ae90`
- `0x18005ba40`
- `0x18008e0ec`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008e179`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008e282`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008e179`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008e282`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18008e20f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18008e26d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18008e20f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18008e26d`

## string_xrefs

- `0x18008e15b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18008e1ed`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  int v6; // esi
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int *v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+248h] [rbp+148h]
  __int64 v21; // [rsp+250h] [rbp+150h]
  _BYTE *v22; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v15 = &v16;
  v6 = (int)a4;
  v17 = 0;
  LOBYTE(v16) = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(&v17, a1, L"User\\Data");
  if ( v7 < 0 )
  {
    v8 = 267;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v7,
      (int)&v16);
LABEL_4:
    v9 = v17;
    v17 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    return (unsigned int)v7;
  }
  if ( !(_BYTE)v16 )
  {
    v7 = -2140733422;
    v8 = 268;
    goto LABEL_3;
  }
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v20 = 0;
  v22 = v19;
  v21 = 256;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v18, a2);
  if ( v7 < 0 )
  {
    v11 = 271;
    goto LABEL_11;
  }
  LODWORD(v15) = v6;
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v17, v22);
  if ( v7 < 0 )
  {
    v11 = 272;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v17,
         L"User\\Data");
  if ( v7 < 0 )
  {
    v11 = 274;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v7,
      (int)v15);
    v12 = v18;
    v18 = 0;
    if ( v12 )
      SRCache_Free(v12);
    goto LABEL_4;
  }
  v13 = v18;
  v18 = 0;
  if ( v13 )
    SRCache_Free(v13);
  v14 = v17;
  v17 = 0;
  if ( v14 )
    SRCacheContext_Close(v14);
  return 0;
}

```

## disassembly

```asm
0x18008e0ec  push    rbp
0x18008e0ee  push    rbx
0x18008e0ef  push    rsi
0x18008e0f0  push    rdi
0x18008e0f1  push    r14
0x18008e0f3  push    r15
0x18008e0f5  lea     rbp, [rsp-178h]
0x18008e0fd  sub     rsp, 278h
0x18008e104  mov     rax, cs:__security_cookie
0x18008e10b  xor     rax, rsp
0x18008e10e  mov     [rbp+1A0h+var_40], rax
0x18008e115  mov     r14, rdx
0x18008e118  lea     rax, [rsp+2A0h+var_270]
0x18008e11d  mov     rdx, rcx
0x18008e120  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x18008e125  mov     rdi, r8
0x18008e128  lea     rcx, [rsp+2A0h+var_268]
0x18008e12d  xor     r15d, r15d
0x18008e130  lea     r8, aUserData; "User\\Data"
0x18008e137  mov     rsi, r9
0x18008e13a  mov     [rsp+2A0h+var_268], r15
0x18008e13f  mov     byte ptr [rsp+2A0h+var_270], r15b
0x18008e144  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18008e149  mov     ebx, eax
0x18008e14b  test    eax, eax
0x18008e14d  jns     short loc_18008E186
0x18008e14f  mov     edx, 10Bh; void *
0x18008e154  mov     rcx, [rbp+1A8h]; this
0x18008e15b  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008e162  mov     r9d, ebx; char *
0x18008e165  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e16a  mov     rcx, [rsp+2A0h+var_268]
0x18008e16f  mov     [rsp+2A0h+var_268], r15
0x18008e174  test    rcx, rcx
0x18008e177  jz      short loc_18008E17F
0x18008e179  call    cs:__imp_SRCacheContext_Close
0x18008e17f  mov     eax, ebx
0x18008e181  jmp     loc_18008E28A
0x18008e186  cmp     byte ptr [rsp+2A0h+var_270], r15b
0x18008e18b  jnz     short loc_18008E199
0x18008e18d  mov     ebx, 80670012h
0x18008e192  mov     edx, 10Ch
0x18008e197  jmp     short loc_18008E154
0x18008e199  xor     edx, edx; Val
0x18008e19b  mov     [rsp+2A0h+var_260], r15
0x18008e1a0  mov     r8d, 200h; Size
0x18008e1a6  lea     rcx, [rsp+2A0h+var_258]; void *
0x18008e1ab  call    memset_0
0x18008e1b0  lea     rax, [rsp+2A0h+var_258]
0x18008e1b5  mov     [rbp+1A0h+var_58], r15
0x18008e1bc  mov     rdx, r14; unsigned __int64
0x18008e1bf  mov     [rbp+1A0h+var_48], rax
0x18008e1c6  lea     rcx, [rsp+2A0h+var_260]; this
0x18008e1cb  mov     [rbp+1A0h+var_50], 100h
0x18008e1d6  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18008e1db  mov     ebx, eax
0x18008e1dd  test    eax, eax
0x18008e1df  jns     short loc_18008E21A
0x18008e1e1  mov     edx, 10Fh; void *
0x18008e1e6  mov     rcx, [rbp+1A8h]; this
0x18008e1ed  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008e1f4  mov     r9d, ebx; char *
0x18008e1f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e1fc  mov     rcx, [rsp+2A0h+var_260]
0x18008e201  mov     [rsp+2A0h+var_260], r15
0x18008e206  test    rcx, rcx
0x18008e209  jz      loc_18008E16A
0x18008e20f  call    cs:__imp_SRCache_Free
0x18008e215  jmp     loc_18008E16A
0x18008e21a  mov     r8, [rbp+1A0h+var_48]
0x18008e221  lea     rdx, [rsp+2A0h+var_268]
0x18008e226  mov     rcx, rdi
0x18008e229  mov     qword ptr [rsp+2A0h+var_280], rsi
0x18008e22e  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18008e233  mov     ebx, eax
0x18008e235  test    eax, eax
0x18008e237  jns     short loc_18008E240
0x18008e239  mov     edx, 110h
0x18008e23e  jmp     short loc_18008E1E6
0x18008e240  lea     rdx, aUserData; "User\\Data"
0x18008e247  lea     rcx, [rsp+2A0h+var_268]; this
0x18008e24c  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18008e251  mov     ebx, eax
0x18008e253  test    eax, eax
0x18008e255  jns     short loc_18008E25E
0x18008e257  mov     edx, 112h
0x18008e25c  jmp     short loc_18008E1E6
0x18008e25e  mov     rcx, [rsp+2A0h+var_260]
0x18008e263  mov     [rsp+2A0h+var_260], r15
0x18008e268  test    rcx, rcx
0x18008e26b  jz      short loc_18008E273
0x18008e26d  call    cs:__imp_SRCache_Free
0x18008e273  mov     rcx, [rsp+2A0h+var_268]
0x18008e278  mov     [rsp+2A0h+var_268], r15
0x18008e27d  test    rcx, rcx
0x18008e280  jz      short loc_18008E288
0x18008e282  call    cs:__imp_SRCacheContext_Close
0x18008e288  xor     eax, eax
0x18008e28a  mov     rcx, [rbp+1A0h+var_40]
0x18008e291  xor     rcx, rsp; StackCookie
0x18008e294  call    __security_check_cookie
0x18008e299  add     rsp, 278h
0x18008e2a0  pop     r15
0x18008e2a2  pop     r14
0x18008e2a4  pop     rdi
0x18008e2a5  pop     rsi
0x18008e2a6  pop     rbx
0x18008e2a7  pop     rbp
0x18008e2a8  retn
```
