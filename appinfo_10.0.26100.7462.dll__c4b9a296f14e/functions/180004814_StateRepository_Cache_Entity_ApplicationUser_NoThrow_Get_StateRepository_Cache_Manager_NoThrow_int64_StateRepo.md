# StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)

- ea: `0x180004814`
- end: `0x180004940`
- name: `?Get@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005880`

## callees

- `0x180004814`
- `0x180004950`
- `0x180007c78`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000489e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000491e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000489e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000491e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800048c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800048c1`

## string_xrefs

- `0x18000483d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180004881`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x1800048ef`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x1800048d7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        bool *a5)
{
  unsigned int v7; // ebx
  bool *v9; // r14
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int Field_UInt32; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  int savedregsa; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v17; // [rsp+50h] [rbp+30h] BYREF

  v17 = a3;
  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80070057LL,
      savedregs);
    return v7;
  }
  v9 = a5;
  v17 = 0;
  v7 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         a5);
  if ( (v7 & 0x80000000) != 0 )
  {
    v10 = 274;
    goto LABEL_6;
  }
  v12 = v17;
  if ( *v9 )
  {
    Field_UInt32 = SRCacheContext_GetField_UInt32(v17, L"Application", a4 + 3);
    v7 = Field_UInt32;
    if ( Field_UInt32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)Field_UInt32,
        savedregs);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45D,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
        (const char *)v7,
        savedregsa);
      v10 = 279;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
        (const char *)v7,
        savedregs);
      v11 = v17;
      v17 = 0;
      if ( v11 )
        SRCacheContext_Close(v11);
      return v7;
    }
    v12 = v17;
    *a4 = a2;
  }
  v17 = 0;
  if ( v12 )
    SRCacheContext_Close(v12);
  return 0;
}

```

## disassembly

```asm
0x180004814  mov     [rsp-18h+arg_0], rbx
0x180004819  mov     [rsp-18h+arg_8], rsi
0x18000481e  mov     [rsp-18h+arg_10], r8
0x180004823  push    rbp
0x180004824  push    rdi
0x180004825  push    r14; int
0x180004827  mov     rbp, rsp
0x18000482a  sub     rsp, 20h
0x18000482e  mov     rsi, r9
0x180004831  mov     rdi, rdx
0x180004834  test    rdx, rdx
0x180004837  jnz     short loc_18000485D
0x180004839  mov     rcx, [rbp+18h]; this
0x18000483d  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004844  mov     ebx, 80070057h
0x180004849  mov     edx, 10Fh; void *
0x18000484e  mov     r9d, ebx; char *
0x180004851  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004856  mov     eax, ebx
0x180004858  jmp     loc_18000492C
0x18000485d  mov     r14, [rbp+arg_20]
0x180004861  lea     r8, [rbp+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x180004865  and     [rbp+arg_10], 0
0x18000486a  mov     r9, r14; bool *
0x18000486d  call    ?Open@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180004872  mov     ebx, eax
0x180004874  test    eax, eax
0x180004876  jns     short loc_1800048AC
0x180004878  mov     edx, 112h; void *
0x18000487d  mov     rcx, [rbp+18h]; this
0x180004881  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004888  mov     r9d, ebx; char *
0x18000488b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004890  mov     rcx, [rbp+arg_10]
0x180004894  and     [rbp+arg_10], 0
0x180004899  test    rcx, rcx
0x18000489c  jz      short loc_180004856
0x18000489e  call    cs:__imp_SRCacheContext_Close
0x1800048a5  nop     dword ptr [rax+rax+00h]
0x1800048aa  jmp     short loc_180004856
0x1800048ac  cmp     byte ptr [r14], 0
0x1800048b0  mov     rcx, [rbp+arg_10]
0x1800048b4  jz      short loc_180004914
0x1800048b6  lea     r8, [rsi+18h]
0x1800048ba  lea     rdx, aApplication; "Application"
0x1800048c1  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800048c8  nop     dword ptr [rax+rax+00h]
0x1800048cd  mov     ebx, eax
0x1800048cf  test    eax, eax
0x1800048d1  jns     short loc_18000490D
0x1800048d3  mov     rcx, [rbp+18h]; this
0x1800048d7  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800048de  mov     r9d, eax; char *
0x1800048e1  mov     edx, 221h; void *
0x1800048e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048eb  mov     rcx, [rbp+18h]; this
0x1800048ef  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800048f6  mov     r9d, ebx; char *
0x1800048f9  mov     edx, 45Dh; void *
0x1800048fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004903  mov     edx, 117h
0x180004908  jmp     loc_18000487D
0x18000490d  mov     rcx, [rbp+arg_10]
0x180004911  mov     [rsi], rdi
0x180004914  and     [rbp+arg_10], 0
0x180004919  test    rcx, rcx
0x18000491c  jz      short loc_18000492A
0x18000491e  call    cs:__imp_SRCacheContext_Close
0x180004925  nop     dword ptr [rax+rax+00h]
0x18000492a  xor     eax, eax
0x18000492c  mov     rbx, [rsp+20h+arg_0]
0x180004931  mov     rsi, [rsp+20h+arg_8]
0x180004936  add     rsp, 20h
0x18000493a  pop     r14
0x18000493c  pop     rdi
0x18000493d  pop     rbp
0x18000493e  retn
```
