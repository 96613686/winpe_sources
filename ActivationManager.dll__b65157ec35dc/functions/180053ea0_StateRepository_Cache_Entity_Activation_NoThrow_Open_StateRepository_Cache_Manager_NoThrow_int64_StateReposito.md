# StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180053ea0`
- end: `0x18005405d`
- name: `?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `445`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18004d6ec`

## callees

- `0x180008be0`
- `0x18000b5c0`
- `0x18000cb80`
- `0x18002f830`
- `0x1800304a0`
- `0x180053ea0`
- `0x18005ae90`
- `0x18005ba40`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053f2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180054036`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053f2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180054036`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180053fc3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180054021`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180053fc3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180054021`

## string_xrefs

- `0x180053f0f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x180053fa1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::Open(
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
  v7 = StateRepository::Cache::Context_NoThrow::Open(&v17, a1, L"Activation\\Data");
  if ( v7 < 0 )
  {
    v8 = 391;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
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
    v8 = 392;
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
    v11 = 395;
    goto LABEL_11;
  }
  LODWORD(v15) = v6;
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v17, v22);
  if ( v7 < 0 )
  {
    v11 = 396;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v17,
         L"Activation\\Data");
  if ( v7 < 0 )
  {
    v11 = 398;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
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
0x180053ea0  push    rbp
0x180053ea2  push    rbx
0x180053ea3  push    rsi
0x180053ea4  push    rdi
0x180053ea5  push    r14
0x180053ea7  push    r15
0x180053ea9  lea     rbp, [rsp-178h]
0x180053eb1  sub     rsp, 278h
0x180053eb8  mov     rax, cs:__security_cookie
0x180053ebf  xor     rax, rsp
0x180053ec2  mov     [rbp+1A0h+var_40], rax
0x180053ec9  mov     r14, rdx
0x180053ecc  lea     rax, [rsp+2A0h+var_270]
0x180053ed1  mov     rdx, rcx
0x180053ed4  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x180053ed9  mov     rdi, r8
0x180053edc  lea     rcx, [rsp+2A0h+var_268]
0x180053ee1  xor     r15d, r15d
0x180053ee4  lea     r8, aActivationData; "Activation\\Data"
0x180053eeb  mov     rsi, r9
0x180053eee  mov     [rsp+2A0h+var_268], r15
0x180053ef3  mov     byte ptr [rsp+2A0h+var_270], r15b
0x180053ef8  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180053efd  mov     ebx, eax
0x180053eff  test    eax, eax
0x180053f01  jns     short loc_180053F3A
0x180053f03  mov     edx, 187h; void *
0x180053f08  mov     rcx, [rbp+1A8h]; this
0x180053f0f  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053f16  mov     r9d, ebx; char *
0x180053f19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053f1e  mov     rcx, [rsp+2A0h+var_268]
0x180053f23  mov     [rsp+2A0h+var_268], r15
0x180053f28  test    rcx, rcx
0x180053f2b  jz      short loc_180053F33
0x180053f2d  call    cs:__imp_SRCacheContext_Close
0x180053f33  mov     eax, ebx
0x180053f35  jmp     loc_18005403E
0x180053f3a  cmp     byte ptr [rsp+2A0h+var_270], r15b
0x180053f3f  jnz     short loc_180053F4D
0x180053f41  mov     ebx, 80670012h
0x180053f46  mov     edx, 188h
0x180053f4b  jmp     short loc_180053F08
0x180053f4d  xor     edx, edx; Val
0x180053f4f  mov     [rsp+2A0h+var_260], r15
0x180053f54  mov     r8d, 200h; Size
0x180053f5a  lea     rcx, [rsp+2A0h+var_258]; void *
0x180053f5f  call    memset_0
0x180053f64  lea     rax, [rsp+2A0h+var_258]
0x180053f69  mov     [rbp+1A0h+var_58], r15
0x180053f70  mov     rdx, r14; unsigned __int64
0x180053f73  mov     [rbp+1A0h+var_48], rax
0x180053f7a  lea     rcx, [rsp+2A0h+var_260]; this
0x180053f7f  mov     [rbp+1A0h+var_50], 100h
0x180053f8a  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180053f8f  mov     ebx, eax
0x180053f91  test    eax, eax
0x180053f93  jns     short loc_180053FCE
0x180053f95  mov     edx, 18Bh; void *
0x180053f9a  mov     rcx, [rbp+1A8h]; this
0x180053fa1  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053fa8  mov     r9d, ebx; char *
0x180053fab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053fb0  mov     rcx, [rsp+2A0h+var_260]
0x180053fb5  mov     [rsp+2A0h+var_260], r15
0x180053fba  test    rcx, rcx
0x180053fbd  jz      loc_180053F1E
0x180053fc3  call    cs:__imp_SRCache_Free
0x180053fc9  jmp     loc_180053F1E
0x180053fce  mov     r8, [rbp+1A0h+var_48]
0x180053fd5  lea     rdx, [rsp+2A0h+var_268]
0x180053fda  mov     rcx, rdi
0x180053fdd  mov     qword ptr [rsp+2A0h+var_280], rsi
0x180053fe2  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180053fe7  mov     ebx, eax
0x180053fe9  test    eax, eax
0x180053feb  jns     short loc_180053FF4
0x180053fed  mov     edx, 18Ch
0x180053ff2  jmp     short loc_180053F9A
0x180053ff4  lea     rdx, aActivationData; "Activation\\Data"
0x180053ffb  lea     rcx, [rsp+2A0h+var_268]; this
0x180054000  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180054005  mov     ebx, eax
0x180054007  test    eax, eax
0x180054009  jns     short loc_180054012
0x18005400b  mov     edx, 18Eh
0x180054010  jmp     short loc_180053F9A
0x180054012  mov     rcx, [rsp+2A0h+var_260]
0x180054017  mov     [rsp+2A0h+var_260], r15
0x18005401c  test    rcx, rcx
0x18005401f  jz      short loc_180054027
0x180054021  call    cs:__imp_SRCache_Free
0x180054027  mov     rcx, [rsp+2A0h+var_268]
0x18005402c  mov     [rsp+2A0h+var_268], r15
0x180054031  test    rcx, rcx
0x180054034  jz      short loc_18005403C
0x180054036  call    cs:__imp_SRCacheContext_Close
0x18005403c  xor     eax, eax
0x18005403e  mov     rcx, [rbp+1A0h+var_40]
0x180054045  xor     rcx, rsp; StackCookie
0x180054048  call    __security_check_cookie
0x18005404d  add     rsp, 278h
0x180054054  pop     r15
0x180054056  pop     r14
0x180054058  pop     rdi
0x180054059  pop     rsi
0x18005405a  pop     rbx
0x18005405b  pop     rbp
0x18005405c  retn
```
