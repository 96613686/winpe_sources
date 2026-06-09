# StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x18001ddf0`
- end: `0x18001e0a8`
- name: `?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `696`
- prototype: `int(StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800187f0`

## callees

- `0x180004cb0`
- `0x18000720c`
- `0x18000b840`
- `0x18000bb40`
- `0x18000dee0`
- `0x18001ddf0`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001dfc0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001e04b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001e065`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001dfc0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001e04b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001e065`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001de5f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001def3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001df3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001e07a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001de5f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001def3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001df3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001e07a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001de98`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001de98`

## string_xrefs

- `0x18001deb5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001de34`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18001ded0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18001df13`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18001df9e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18001e024`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
        StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int *v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  char v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v28; // [rsp+268h] [rbp+168h]
  __int64 v29; // [rsp+270h] [rbp+170h]
  _BYTE *v30; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      (int)v19);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  v23 = &v22;
  v22 = 0;
  v24 = 0;
  v25 = 1;
  v10 = SRCacheContext_Open(v9, L"Application\\Index\\Package", 0, &v24);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v23);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      (int)v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v10,
      v20);
LABEL_8:
    v11 = v22;
    v22 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v10;
  }
  if ( !v22 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80670012LL,
      (int)v19);
LABEL_13:
    v12 = v22;
    v22 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return v6;
  }
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v28 = 0;
  v30 = v27;
  v29 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, a3);
  if ( v10 < 0 )
  {
    v13 = 1001;
    goto LABEL_17;
  }
  v19 = &v21;
  LOBYTE(v21) = 0;
  v10 = StateRepository::Cache::Context_NoThrow::OpenSubContext(this, &v22, v30);
  if ( v10 < 0 )
  {
    v13 = 1004;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v10,
      (int)v19);
    v14 = v26;
    v26 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_8;
  }
  if ( (_BYTE)v21 )
    *((_QWORD *)this + 2) = a2;
  v15 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)&v22,
          L"Application\\Index\\Package");
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F2,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v15,
      (int)&v21);
    v16 = v26;
    v26 = 0;
    if ( v16 )
      SRCache_Free(v16);
    goto LABEL_13;
  }
  v17 = v26;
  v26 = 0;
  if ( v17 )
    SRCache_Free(v17);
  v18 = v22;
  v22 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return 0;
}

```

## disassembly

```asm
0x18001ddf0  mov     [rsp-8+arg_18], rbx
0x18001ddf5  push    rbp
0x18001ddf6  push    rsi
0x18001ddf7  push    rdi
0x18001ddf8  push    r14
0x18001ddfa  push    r15
0x18001ddfc  lea     rbp, [rsp-190h]
0x18001de04  sub     rsp, 290h
0x18001de0b  mov     rax, cs:__security_cookie
0x18001de12  xor     rax, rsp
0x18001de15  mov     [rbp+1B0h+var_30], rax
0x18001de1c  xor     r15d, r15d
0x18001de1f  mov     r14, r8
0x18001de22  mov     rsi, rdx
0x18001de25  mov     rbx, rcx
0x18001de28  test    r8, r8
0x18001de2b  jnz     short loc_18001DE54
0x18001de2d  mov     rcx, [rbp+1B8h]; this
0x18001de34  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001de3b  mov     ebx, 80070057h
0x18001de40  mov     edx, 3DFh; void *
0x18001de45  mov     r9d, ebx; char *
0x18001de48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de4d  mov     eax, ebx
0x18001de4f  jmp     loc_18001E082
0x18001de54  mov     rcx, [rcx]
0x18001de57  mov     [rbx], r15
0x18001de5a  test    rcx, rcx
0x18001de5d  jz      short loc_18001DE65
0x18001de5f  call    cs:__imp_SRCacheContext_Close
0x18001de65  mov     [rbx+8], r15d
0x18001de69  lea     rax, [rsp+2B0h+var_278]
0x18001de6e  mov     [rbx+10h], r15
0x18001de72  lea     r9, [rsp+2B0h+var_268]
0x18001de77  mov     rcx, [rsi]
0x18001de7a  lea     rdx, aApplicationInd; "Application\\Index\\Package"
0x18001de81  xor     r8d, r8d
0x18001de84  mov     [rsp+2B0h+var_270], rax
0x18001de89  mov     [rsp+2B0h+var_278], r15
0x18001de8e  mov     [rsp+2B0h+var_268], r15
0x18001de93  mov     [rsp+2B0h+var_260], 1
0x18001de98  call    cs:__imp_SRCacheContext_Open
0x18001de9e  lea     rcx, [rsp+2B0h+var_270]
0x18001dea3  mov     edi, eax
0x18001dea5  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001deaa  test    edi, edi
0x18001deac  jns     short loc_18001DF00
0x18001deae  mov     rcx, [rbp+1B8h]; this
0x18001deb5  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001debc  mov     r9d, edi; char *
0x18001debf  mov     edx, 18Ch; void *
0x18001dec4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dec9  mov     rcx, [rbp+1B8h]; this
0x18001ded0  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ded7  mov     r9d, edi; char *
0x18001deda  mov     edx, 3E5h; void *
0x18001dedf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dee4  mov     rcx, [rsp+2B0h+var_278]
0x18001dee9  mov     [rsp+2B0h+var_278], r15
0x18001deee  test    rcx, rcx
0x18001def1  jz      short loc_18001DEF9
0x18001def3  call    cs:__imp_SRCacheContext_Close
0x18001def9  mov     eax, edi
0x18001defb  jmp     loc_18001E082
0x18001df00  cmp     [rsp+2B0h+var_278], r15
0x18001df05  setnz   al
0x18001df08  test    al, al
0x18001df0a  jnz     short loc_18001DF4A
0x18001df0c  mov     rcx, [rbp+1B8h]; this
0x18001df13  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001df1a  mov     ebx, 80670012h
0x18001df1f  mov     edx, 3E6h; void *
0x18001df24  mov     r9d, ebx; char *
0x18001df27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df2c  mov     rcx, [rsp+2B0h+var_278]
0x18001df31  mov     [rsp+2B0h+var_278], r15
0x18001df36  test    rcx, rcx
0x18001df39  jz      loc_18001DE4D
0x18001df3f  call    cs:__imp_SRCacheContext_Close
0x18001df45  jmp     loc_18001DE4D
0x18001df4a  xor     edx, edx; Val
0x18001df4c  mov     [rsp+2B0h+var_250], r15
0x18001df51  mov     r8d, 200h; Size
0x18001df57  lea     rcx, [rsp+2B0h+var_248]; void *
0x18001df5c  call    memset_0
0x18001df61  lea     rax, [rsp+2B0h+var_248]
0x18001df66  mov     [rbp+1B0h+var_48], r15
0x18001df6d  mov     rdx, r14; unsigned __int64
0x18001df70  mov     [rbp+1B0h+var_38], rax
0x18001df77  lea     rcx, [rsp+2B0h+var_250]; this
0x18001df7c  mov     [rbp+1B0h+var_40], 100h
0x18001df87  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001df8c  mov     edi, eax
0x18001df8e  test    eax, eax
0x18001df90  jns     short loc_18001DFCB
0x18001df92  mov     edx, 3E9h; void *
0x18001df97  mov     rcx, [rbp+1B8h]; this
0x18001df9e  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001dfa5  mov     r9d, edi; char *
0x18001dfa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dfad  mov     rcx, [rsp+2B0h+var_250]
0x18001dfb2  mov     [rsp+2B0h+var_250], r15
0x18001dfb7  test    rcx, rcx
0x18001dfba  jz      loc_18001DEE4
0x18001dfc0  call    cs:__imp_SRCache_Free
0x18001dfc6  jmp     loc_18001DEE4
0x18001dfcb  mov     r8, [rbp+1B0h+var_38]
0x18001dfd2  lea     rax, [rsp+2B0h+var_280]
0x18001dfd7  lea     rdx, [rsp+2B0h+var_278]
0x18001dfdc  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18001dfe1  mov     rcx, rbx
0x18001dfe4  mov     byte ptr [rsp+2B0h+var_280], r15b
0x18001dfe9  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18001dfee  mov     edi, eax
0x18001dff0  test    eax, eax
0x18001dff2  jns     short loc_18001DFFB
0x18001dff4  mov     edx, 3ECh
0x18001dff9  jmp     short loc_18001DF97
0x18001dffb  cmp     byte ptr [rsp+2B0h+var_280], r15b
0x18001e000  jz      short loc_18001E006
0x18001e002  mov     [rbx+10h], rsi
0x18001e006  lea     rdx, aApplicationInd; "Application\\Index\\Package"
0x18001e00d  lea     rcx, [rsp+2B0h+var_278]; this
0x18001e012  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001e017  mov     ebx, eax
0x18001e019  test    eax, eax
0x18001e01b  jns     short loc_18001E056
0x18001e01d  mov     rcx, [rbp+1B8h]; this
0x18001e024  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001e02b  mov     r9d, eax; char *
0x18001e02e  mov     edx, 3F2h; void *
0x18001e033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e038  mov     rcx, [rsp+2B0h+var_250]
0x18001e03d  mov     [rsp+2B0h+var_250], r15
0x18001e042  test    rcx, rcx
0x18001e045  jz      loc_18001DF2C
0x18001e04b  call    cs:__imp_SRCache_Free
0x18001e051  jmp     loc_18001DF2C
0x18001e056  mov     rcx, [rsp+2B0h+var_250]
0x18001e05b  mov     [rsp+2B0h+var_250], r15
0x18001e060  test    rcx, rcx
0x18001e063  jz      short loc_18001E06B
0x18001e065  call    cs:__imp_SRCache_Free
0x18001e06b  mov     rcx, [rsp+2B0h+var_278]
0x18001e070  mov     [rsp+2B0h+var_278], r15
0x18001e075  test    rcx, rcx
0x18001e078  jz      short loc_18001E080
0x18001e07a  call    cs:__imp_SRCacheContext_Close
0x18001e080  xor     eax, eax
0x18001e082  mov     rcx, [rbp+1B0h+var_30]
0x18001e089  xor     rcx, rsp; StackCookie
0x18001e08c  call    __security_check_cookie
0x18001e091  mov     rbx, [rsp+2B0h+arg_18]
0x18001e099  add     rsp, 290h
0x18001e0a0  pop     r15
0x18001e0a2  pop     r14
0x18001e0a4  pop     rdi
0x18001e0a5  pop     rsi
0x18001e0a6  pop     rbp
0x18001e0a7  retn
```
