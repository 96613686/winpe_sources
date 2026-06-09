# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180005000`
- end: `0x18000529f`
- name: `?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `671`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180004eb0`

## callees

- `0x180005000`
- `0x1800055d0`
- `0x180007c78`
- `0x18000ea20`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005183`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000524f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005183`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000524f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180005063`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180005063`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000508d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800050e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800051e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000526a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000508d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800050e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800051e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000526a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800051b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800051b7`

## string_xrefs

- `0x18000504f`: `ApplicationExtension\Data`
- `0x180005219`: `ApplicationExtension\Data`
- `0x1800050a4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800051f8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800050c4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180005161`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v19; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  char v21; // [rsp+38h] [rbp-C8h]
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+248h] [rbp+148h]
  __int64 v25; // [rsp+250h] [rbp+150h]
  _BYTE *v26; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v19 = v18;
  v21 = 1;
  *(_QWORD *)v18 = 0;
  v20 = 0;
  v8 = SRCacheContext_Open(v4, L"ApplicationExtension\\Data", 0, &v20);
  if ( v21 )
  {
    v9 = *(_QWORD *)v19;
    *(_QWORD *)v19 = v20;
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
      v18[0]);
    v10 = 364;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
LABEL_7:
    v11 = *(_QWORD *)v18;
    *(_QWORD *)v18 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v18 )
  {
    v8 = -2140733422;
    v10 = 365;
    goto LABEL_6;
  }
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v24 = 0;
  v26 = v23;
  v25 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v22, a2);
  if ( v8 < 0 )
  {
    v13 = 368;
    goto LABEL_14;
  }
  v19 = (int *)a3;
  v20 = 0;
  v21 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v18, v26, 0, &v20);
  if ( v21 )
  {
    v15 = *(_QWORD *)v19;
    *(_QWORD *)v19 = v20;
    if ( v15 )
      SRCacheContext_Close(v15);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    v13 = 369;
    goto LABEL_14;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v18,
         L"ApplicationExtension\\Data");
  if ( v8 < 0 )
  {
    v13 = 371;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    v14 = v22;
    v22 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_7;
  }
  v16 = v22;
  v22 = 0;
  if ( v16 )
    SRCache_Free();
  v17 = *(_QWORD *)v18;
  *(_QWORD *)v18 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  return 0;
}

```

## disassembly

```asm
0x180005000  mov     [rsp-8+arg_10], rbx
0x180005005  push    rbp
0x180005006  push    rsi
0x180005007  push    rdi
0x180005008  push    r14
0x18000500a  push    r15
0x18000500c  lea     rbp, [rsp-170h]
0x180005014  sub     rsp, 270h
0x18000501b  mov     rax, cs:__security_cookie
0x180005022  xor     rax, rsp
0x180005025  mov     [rbp+190h+var_30], rax
0x18000502c  mov     rcx, [rcx]
0x18000502f  lea     rax, [rsp+290h+var_270]
0x180005034  mov     r14, r9
0x180005037  mov     [rsp+290h+var_268], rax
0x18000503c  mov     rdi, r8
0x18000503f  mov     [rsp+290h+var_258], 1
0x180005044  mov     rsi, rdx
0x180005047  lea     r9, [rsp+290h+var_260]
0x18000504c  xor     r15d, r15d
0x18000504f  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x180005056  xor     r8d, r8d
0x180005059  mov     qword ptr [rsp+290h+var_270], r15; int
0x18000505e  mov     [rsp+290h+var_260], r15
0x180005063  call    cs:__imp_SRCacheContext_Open
0x18000506a  nop     dword ptr [rax+rax+00h]
0x18000506f  mov     ebx, eax
0x180005071  cmp     [rsp+290h+var_258], r15b
0x180005076  jz      short loc_180005099
0x180005078  mov     r8, [rsp+290h+var_268]
0x18000507d  mov     rdx, [rsp+290h+var_260]
0x180005082  mov     rcx, [r8]
0x180005085  mov     [r8], rdx
0x180005088  test    rcx, rcx
0x18000508b  jz      short loc_180005099
0x18000508d  call    cs:__imp_SRCacheContext_Close
0x180005094  nop     dword ptr [rax+rax+00h]
0x180005099  test    ebx, ebx
0x18000509b  jns     short loc_1800050F5
0x18000509d  mov     rcx, [rbp+198h]; this
0x1800050a4  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800050ab  mov     r9d, ebx; char *
0x1800050ae  mov     edx, 18Ch; void *
0x1800050b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050b8  mov     edx, 16Ch; void *
0x1800050bd  mov     rcx, [rbp+198h]; this
0x1800050c4  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800050cb  mov     r9d, ebx; char *
0x1800050ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050d3  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800050d8  mov     qword ptr [rsp+290h+var_270], r15
0x1800050dd  test    rcx, rcx
0x1800050e0  jz      short loc_1800050EE
0x1800050e2  call    cs:__imp_SRCacheContext_Close
0x1800050e9  nop     dword ptr [rax+rax+00h]
0x1800050ee  mov     eax, ebx
0x1800050f0  jmp     loc_180005278
0x1800050f5  cmp     qword ptr [rsp+290h+var_270], r15
0x1800050fa  setnz   al
0x1800050fd  test    al, al
0x1800050ff  jnz     short loc_18000510D
0x180005101  mov     ebx, 80670012h
0x180005106  mov     edx, 16Dh
0x18000510b  jmp     short loc_1800050BD
0x18000510d  xor     edx, edx; Val
0x18000510f  mov     [rsp+290h+var_250], r15
0x180005114  mov     r8d, 200h; Size
0x18000511a  lea     rcx, [rsp+290h+var_248]; void *
0x18000511f  call    memset_0
0x180005124  lea     rax, [rsp+290h+var_248]
0x180005129  mov     [rbp+190h+var_48], r15
0x180005130  mov     rdx, rsi; unsigned __int64
0x180005133  mov     [rbp+190h+var_38], rax
0x18000513a  lea     rcx, [rsp+290h+var_250]; this
0x18000513f  mov     [rbp+190h+var_40], 100h
0x18000514a  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18000514f  mov     ebx, eax
0x180005151  test    eax, eax
0x180005153  jns     short loc_180005194
0x180005155  mov     edx, 170h; void *
0x18000515a  mov     rcx, [rbp+198h]; this
0x180005161  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005168  mov     r9d, ebx; char *
0x18000516b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005170  mov     rcx, [rsp+290h+var_250]
0x180005175  mov     [rsp+290h+var_250], r15
0x18000517a  test    rcx, rcx
0x18000517d  jz      loc_1800050D3
0x180005183  call    cs:__imp_SRCache_Free
0x18000518a  nop     dword ptr [rax+rax+00h]
0x18000518f  jmp     loc_1800050D3
0x180005194  mov     rdx, [rbp+190h+var_38]
0x18000519b  lea     r9, [rsp+290h+var_260]
0x1800051a0  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800051a5  xor     r8d, r8d
0x1800051a8  mov     [rsp+290h+var_268], rdi
0x1800051ad  mov     [rsp+290h+var_260], r15
0x1800051b2  mov     [rsp+290h+var_258], 1
0x1800051b7  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800051be  nop     dword ptr [rax+rax+00h]
0x1800051c3  mov     ebx, eax
0x1800051c5  cmp     [rsp+290h+var_258], r15b
0x1800051ca  jz      short loc_1800051ED
0x1800051cc  mov     r8, [rsp+290h+var_268]
0x1800051d1  mov     rdx, [rsp+290h+var_260]
0x1800051d6  mov     rcx, [r8]
0x1800051d9  mov     [r8], rdx
0x1800051dc  test    rcx, rcx
0x1800051df  jz      short loc_1800051ED
0x1800051e1  call    cs:__imp_SRCacheContext_Close
0x1800051e8  nop     dword ptr [rax+rax+00h]
0x1800051ed  test    ebx, ebx
0x1800051ef  jns     short loc_180005216
0x1800051f1  mov     rcx, [rbp+198h]; this
0x1800051f8  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800051ff  mov     r9d, ebx; char *
0x180005202  mov     edx, 1B0h; void *
0x180005207  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000520c  mov     edx, 171h
0x180005211  jmp     loc_18000515A
0x180005216  cmp     [rdi], r15
0x180005219  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x180005220  lea     rcx, [rsp+290h+var_270]; this
0x180005225  setnz   al
0x180005228  mov     [r14], al
0x18000522b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180005230  mov     ebx, eax
0x180005232  test    eax, eax
0x180005234  jns     short loc_180005240
0x180005236  mov     edx, 173h
0x18000523b  jmp     loc_18000515A
0x180005240  mov     rcx, [rsp+290h+var_250]
0x180005245  mov     [rsp+290h+var_250], r15
0x18000524a  test    rcx, rcx
0x18000524d  jz      short loc_18000525B
0x18000524f  call    cs:__imp_SRCache_Free
0x180005256  nop     dword ptr [rax+rax+00h]
0x18000525b  mov     rcx, qword ptr [rsp+290h+var_270]
0x180005260  mov     qword ptr [rsp+290h+var_270], r15
0x180005265  test    rcx, rcx
0x180005268  jz      short loc_180005276
0x18000526a  call    cs:__imp_SRCacheContext_Close
0x180005271  nop     dword ptr [rax+rax+00h]
0x180005276  xor     eax, eax
0x180005278  mov     rcx, [rbp+190h+var_30]
0x18000527f  xor     rcx, rsp; StackCookie
0x180005282  call    __security_check_cookie
0x180005287  mov     rbx, [rsp+290h+arg_10]
0x18000528f  add     rsp, 270h
0x180005296  pop     r15
0x180005298  pop     r14
0x18000529a  pop     rdi
0x18000529b  pop     rsi
0x18000529c  pop     rbp
0x18000529d  retn
```
