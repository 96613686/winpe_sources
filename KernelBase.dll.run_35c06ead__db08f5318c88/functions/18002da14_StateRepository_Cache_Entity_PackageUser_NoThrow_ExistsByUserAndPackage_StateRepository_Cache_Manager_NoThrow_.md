# StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)

- ea: `0x18002da14`
- end: `0x18002ddb9`
- name: `?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z`
- size: `933`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, bool *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x18002af0c`
- `0x18002d000`
- `0x18009df60`
- `0x180147b50`
- `0x180154dcc`

## callees

- `0x18002da14`
- `0x18002f340`
- `0x18002f620`
- `0x180058768`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002db6f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002db6f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002da89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002da89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002daad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002db93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dbfe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dc28`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dc94`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dcbe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002daad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002db93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dbfe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dc28`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dc94`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dcbe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002dc13`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002dca9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002dc13`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002dca9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002dbe3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002dbe3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x18002dbba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x18002dbba`

## string_xrefs

- `0x18002dc76`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18002dcd7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18002dcf4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18002dd6f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18002dc56`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002dd11`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002dd36`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002dd8a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        bool *a4)
{
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  unsigned __int16 v10; // dx
  __int64 v11; // rcx
  int IsEmpty; // eax
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v25[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  int *v28; // [rsp+38h] [rbp-C8h]
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  char v30; // [rsp+48h] [rbp-B8h]
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v32[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+258h] [rbp+158h]
  __int64 v34; // [rsp+260h] [rbp+160h]
  _BYTE *v35; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a2 )
  {
    v23 = 153;
LABEL_37:
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)0x80070057LL,
      v25[0]);
    return (unsigned int)v8;
  }
  if ( !a3 )
  {
    v23 = 154;
    goto LABEL_37;
  }
  v7 = *(_QWORD *)a1;
  v28 = v25;
  *(_QWORD *)v25 = 0;
  v29 = 0;
  v30 = 1;
  v8 = SRCacheContext_Open(v7, L"PackageUser\\Index\\UserAndPackage", 0, &v29);
  if ( v30 )
  {
    v9 = *(_QWORD *)v28;
    *(_QWORD *)v28 = v29;
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
      v25[0]);
    v24 = 158;
    goto LABEL_42;
  }
  if ( !*(_QWORD *)v25 )
  {
    v8 = -2140733422;
    v24 = 159;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
LABEL_31:
    v21 = *(_QWORD *)v25;
    *(_QWORD *)v25 = 0;
    if ( v21 )
      SRCacheContext_Close(v21);
    return (unsigned int)v8;
  }
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v33 = 0;
  v35 = v32;
  v34 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, a2);
  if ( v8 < 0 )
  {
    v22 = 162;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
LABEL_29:
    v20 = v31;
    v31 = 0;
    if ( v20 )
      SRCache_Free(v20);
    goto LABEL_31;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, v10);
  if ( v8 < 0 )
  {
    v22 = 163;
    goto LABEL_35;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, a3);
  if ( v8 < 0 )
  {
    v22 = 164;
    goto LABEL_35;
  }
  v28 = (int *)&v26;
  v26 = 0;
  v29 = 0;
  v30 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v25, v35, 0, &v29);
  if ( v30 )
  {
    v11 = *(_QWORD *)v28;
    *(_QWORD *)v28 = v29;
    if ( v11 )
      SRCacheContext_Close(v11);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
    v18 = 168;
    goto LABEL_27;
  }
  if ( !v26 )
    goto LABEL_18;
  v27 = 0;
  IsEmpty = SRCacheContext_IsEmpty(v26, &v27);
  v8 = IsEmpty;
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v25[0]);
    v18 = 172;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v25[0]);
    v19 = v26;
    v26 = 0;
    if ( v19 )
      SRCacheContext_Close(v19);
    goto LABEL_29;
  }
  *a4 = v27 == 0;
LABEL_18:
  v13 = SRCacheContext_AddToCache(*(_QWORD *)v25, L"PackageUser\\Index\\UserAndPackage");
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      v25[0]);
    v18 = 176;
    goto LABEL_27;
  }
  v14 = v26;
  v26 = 0;
  if ( v14 )
    SRCacheContext_Close(v14);
  v15 = v31;
  v31 = 0;
  if ( v15 )
    SRCache_Free(v15);
  v16 = *(_QWORD *)v25;
  *(_QWORD *)v25 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x18002da14  push    rbp
0x18002da16  push    rbx
0x18002da17  push    rsi
0x18002da18  push    rdi
0x18002da19  push    r14
0x18002da1b  push    r15
0x18002da1d  lea     rbp, [rsp-188h]
0x18002da25  sub     rsp, 288h
0x18002da2c  mov     rax, cs:__security_cookie
0x18002da33  xor     rax, rsp
0x18002da36  mov     [rbp+1B0h+var_40], rax
0x18002da3d  xor     r15d, r15d
0x18002da40  mov     r14, r9
0x18002da43  mov     [r9], r15b
0x18002da46  mov     rdi, r8
0x18002da49  mov     rsi, rdx
0x18002da4c  test    rdx, rdx
0x18002da4f  jz      loc_18002DCE8
0x18002da55  test    r8, r8
0x18002da58  jz      loc_18002DDA5
0x18002da5e  mov     rcx, [rcx]
0x18002da61  lea     rax, [rsp+2B0h+var_290]
0x18002da66  lea     r9, [rsp+2B0h+var_270]
0x18002da6b  mov     [rsp+2B0h+var_278], rax
0x18002da70  xor     r8d, r8d
0x18002da73  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18002da78  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x18002da7f  mov     [rsp+2B0h+var_270], r15
0x18002da84  mov     [rsp+2B0h+var_268], 1
0x18002da89  call    cs:__imp_SRCacheContext_Open
0x18002da8f  mov     ebx, eax
0x18002da91  cmp     [rsp+2B0h+var_268], r15b
0x18002da96  jz      short loc_18002DAB3
0x18002da98  mov     r8, [rsp+2B0h+var_278]
0x18002da9d  mov     rdx, [rsp+2B0h+var_270]
0x18002daa2  mov     rcx, [r8]
0x18002daa5  mov     [r8], rdx
0x18002daa8  test    rcx, rcx
0x18002daab  jz      short loc_18002DAB3
0x18002daad  call    cs:__imp_SRCacheContext_Close
0x18002dab3  test    ebx, ebx
0x18002dab5  js      loc_18002DD83
0x18002dabb  cmp     qword ptr [rsp+2B0h+var_290], r15
0x18002dac0  setnz   al
0x18002dac3  test    al, al
0x18002dac5  jz      loc_18002DD5E
0x18002dacb  xor     edx, edx; Val
0x18002dacd  mov     [rsp+2B0h+var_260], r15
0x18002dad2  mov     r8d, 200h; Size
0x18002dad8  lea     rcx, [rsp+2B0h+var_258]; void *
0x18002dadd  call    memset_0
0x18002dae2  lea     rax, [rsp+2B0h+var_258]
0x18002dae7  mov     [rbp+1B0h+var_58], r15
0x18002daee  mov     rdx, rsi; unsigned __int64
0x18002daf1  mov     [rbp+1B0h+var_48], rax
0x18002daf8  lea     rcx, [rsp+2B0h+var_260]; this
0x18002dafd  mov     [rbp+1B0h+var_50], 100h
0x18002db08  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002db0d  mov     ebx, eax
0x18002db0f  test    eax, eax
0x18002db11  js      loc_18002DCCB
0x18002db17  lea     rcx, [rsp+2B0h+var_260]; this
0x18002db1c  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18002db21  mov     ebx, eax
0x18002db23  test    eax, eax
0x18002db25  js      loc_18002DDAF
0x18002db2b  mov     rdx, rdi; unsigned __int64
0x18002db2e  lea     rcx, [rsp+2B0h+var_260]; this
0x18002db33  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002db38  mov     ebx, eax
0x18002db3a  test    eax, eax
0x18002db3c  js      loc_18002DD54
0x18002db42  mov     rdx, [rbp+1B0h+var_48]
0x18002db49  lea     rax, [rsp+2B0h+var_288]
0x18002db4e  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18002db53  lea     r9, [rsp+2B0h+var_270]
0x18002db58  xor     r8d, r8d
0x18002db5b  mov     [rsp+2B0h+var_278], rax
0x18002db60  mov     [rsp+2B0h+var_288], r15
0x18002db65  mov     [rsp+2B0h+var_270], r15
0x18002db6a  mov     [rsp+2B0h+var_268], 1
0x18002db6f  call    cs:__imp_SRCacheContext_OpenSubContext
0x18002db75  mov     ebx, eax
0x18002db77  cmp     [rsp+2B0h+var_268], r15b
0x18002db7c  jz      short loc_18002DB99
0x18002db7e  mov     r8, [rsp+2B0h+var_278]
0x18002db83  mov     rdx, [rsp+2B0h+var_270]
0x18002db88  mov     rcx, [r8]
0x18002db8b  mov     [r8], rdx
0x18002db8e  test    rcx, rcx
0x18002db91  jz      short loc_18002DB99
0x18002db93  call    cs:__imp_SRCacheContext_Close
0x18002db99  test    ebx, ebx
0x18002db9b  js      loc_18002DD0A
0x18002dba1  mov     rcx, [rsp+2B0h+var_288]
0x18002dba6  test    rcx, rcx
0x18002dba9  setnz   al
0x18002dbac  test    al, al
0x18002dbae  jz      short loc_18002DBD7
0x18002dbb0  lea     rdx, [rsp+2B0h+var_280]
0x18002dbb5  mov     [rsp+2B0h+var_280], r15d
0x18002dbba  call    cs:__imp_SRCacheContext_IsEmpty
0x18002dbc0  mov     ebx, eax
0x18002dbc2  test    eax, eax
0x18002dbc4  js      loc_18002DD2F
0x18002dbca  cmp     [rsp+2B0h+var_280], r15d
0x18002dbcf  setnz   al
0x18002dbd2  xor     al, 1
0x18002dbd4  mov     [r14], al
0x18002dbd7  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18002dbdc  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x18002dbe3  call    cs:__imp_SRCacheContext_AddToCache
0x18002dbe9  mov     ebx, eax
0x18002dbeb  test    eax, eax
0x18002dbed  js      short loc_18002DC4F
0x18002dbef  mov     rcx, [rsp+2B0h+var_288]
0x18002dbf4  mov     [rsp+2B0h+var_288], r15
0x18002dbf9  test    rcx, rcx
0x18002dbfc  jz      short loc_18002DC04
0x18002dbfe  call    cs:__imp_SRCacheContext_Close
0x18002dc04  mov     rcx, [rsp+2B0h+var_260]
0x18002dc09  mov     [rsp+2B0h+var_260], r15
0x18002dc0e  test    rcx, rcx
0x18002dc11  jz      short loc_18002DC19
0x18002dc13  call    cs:__imp_SRCache_Free
0x18002dc19  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18002dc1e  mov     qword ptr [rsp+2B0h+var_290], r15
0x18002dc23  test    rcx, rcx
0x18002dc26  jz      short loc_18002DC2E
0x18002dc28  call    cs:__imp_SRCacheContext_Close
0x18002dc2e  xor     eax, eax
0x18002dc30  mov     rcx, [rbp+1B0h+var_40]
0x18002dc37  xor     rcx, rsp; StackCookie
0x18002dc3a  call    __security_check_cookie
0x18002dc3f  add     rsp, 288h
0x18002dc46  pop     r15
0x18002dc48  pop     r14
0x18002dc4a  pop     rdi
0x18002dc4b  pop     rsi
0x18002dc4c  pop     rbx
0x18002dc4d  pop     rbp
0x18002dc4e  retn
0x18002dc4f  mov     rcx, [rbp+1B8h]; this
0x18002dc56  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dc5d  mov     r9d, ebx; char *
0x18002dc60  mov     edx, 1A6h; void *
0x18002dc65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc6a  mov     edx, 0B0h; void *
0x18002dc6f  mov     rcx, [rbp+1B8h]; this
0x18002dc76  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dc7d  mov     r9d, ebx; char *
0x18002dc80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc85  mov     rcx, [rsp+2B0h+var_288]
0x18002dc8a  mov     [rsp+2B0h+var_288], r15
0x18002dc8f  test    rcx, rcx
0x18002dc92  jz      short loc_18002DC9A
0x18002dc94  call    cs:__imp_SRCacheContext_Close
0x18002dc9a  mov     rcx, [rsp+2B0h+var_260]
0x18002dc9f  mov     [rsp+2B0h+var_260], r15
0x18002dca4  test    rcx, rcx
0x18002dca7  jz      short loc_18002DCAF
0x18002dca9  call    cs:__imp_SRCache_Free
0x18002dcaf  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18002dcb4  mov     qword ptr [rsp+2B0h+var_290], r15
0x18002dcb9  test    rcx, rcx
0x18002dcbc  jz      short loc_18002DCC4
0x18002dcbe  call    cs:__imp_SRCacheContext_Close
0x18002dcc4  mov     eax, ebx
0x18002dcc6  jmp     loc_18002DC30
0x18002dccb  mov     edx, 0A2h; void *
0x18002dcd0  mov     rcx, [rbp+1B8h]; this
0x18002dcd7  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dcde  mov     r9d, ebx; char *
0x18002dce1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dce6  jmp     short loc_18002DC9A
0x18002dce8  mov     edx, 99h; void *
0x18002dced  mov     rcx, [rbp+1B8h]; this
0x18002dcf4  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dcfb  mov     ebx, 80070057h
0x18002dd00  mov     r9d, ebx; char *
0x18002dd03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dd08  jmp     short loc_18002DCC4
0x18002dd0a  mov     rcx, [rbp+1B8h]; this
0x18002dd11  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dd18  mov     r9d, ebx; char *
0x18002dd1b  mov     edx, 1B0h; void *
0x18002dd20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dd25  mov     edx, 0A8h
0x18002dd2a  jmp     loc_18002DC6F
0x18002dd2f  mov     rcx, [rbp+1B8h]; this
0x18002dd36  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dd3d  mov     r9d, ebx; char *
0x18002dd40  mov     edx, 2B8h; void *
0x18002dd45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dd4a  mov     edx, 0ACh
0x18002dd4f  jmp     loc_18002DC6F
0x18002dd54  mov     edx, 0A4h
0x18002dd59  jmp     loc_18002DCD0
0x18002dd5e  mov     ebx, 80670012h
0x18002dd63  mov     edx, 9Fh; void *
0x18002dd68  mov     rcx, [rbp+1B8h]; this
0x18002dd6f  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dd76  mov     r9d, ebx; char *
0x18002dd79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dd7e  jmp     loc_18002DCAF
0x18002dd83  mov     rcx, [rbp+1B8h]; this
0x18002dd8a  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dd91  mov     r9d, ebx; char *
0x18002dd94  mov     edx, 18Ch; void *
0x18002dd99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dd9e  mov     edx, 9Eh
0x18002dda3  jmp     short loc_18002DD68
0x18002dda5  mov     edx, 9Ah
0x18002ddaa  jmp     loc_18002DCED
0x18002ddaf  mov     edx, 0A3h
0x18002ddb4  jmp     loc_18002DCD0
```
