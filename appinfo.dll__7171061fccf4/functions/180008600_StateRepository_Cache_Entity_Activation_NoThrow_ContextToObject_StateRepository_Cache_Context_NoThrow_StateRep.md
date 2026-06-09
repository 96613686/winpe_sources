# StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,__int64)

- ea: `0x180008600`
- end: `0x1800089d0`
- name: `?ContextToObject@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `976`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *, unsigned __int16 **, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001177c`

## callees

- `0x18000720c`
- `0x180008600`
- `0x18000d930`
- `0x18000eed0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000867c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000875e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800087e7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800088c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000894a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000867c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000875e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800087e7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800088c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000894a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800086b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800086b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000863a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000871c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800087a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000887f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180008908`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000863a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000871c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800087a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000887f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180008908`

## string_xrefs

- `0x18000868a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x1800086db`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18000876c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x1800087f5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x180008846`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x1800088cf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x180008958`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x1800089a6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18000864a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800086c3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000872c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800087b5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000888f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180008918`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        unsigned __int16 **a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  __int64 v6; // rcx
  int Field_String; // eax
  int v9; // ebx
  unsigned __int16 *v10; // rcx
  int Field_UInt32; // eax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  int v15; // eax
  int v16; // ebx
  unsigned __int16 *v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  int v20; // ebx
  unsigned __int16 *v21; // rcx
  int Field; // ebx
  __int64 v23; // rcx
  int v24; // eax
  int v25; // ebx
  unsigned __int16 *v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  int v29; // ebx
  unsigned __int16 *v30; // rcx
  int v31; // ebx
  unsigned __int16 **v32; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v33; // [rsp+28h] [rbp-20h] BYREF
  char v34; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  v34 = 1;
  v32 = a2 + 1;
  v6 = *(_QWORD *)a1;
  v33 = 0;
  Field_String = SRCacheContext_GetField_String(v6, L"ActivationKey", &v33);
  v9 = Field_String;
  if ( Field_String >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v32);
  if ( v34 )
  {
    v10 = *v32;
    *v32 = v33;
    if ( v10 )
      SRCache_Free(v10);
  }
  if ( v9 >= 0 )
  {
    Field_UInt32 = SRCacheContext_GetField_UInt32(*(_QWORD *)a1, L"Flags", a2 + 2);
    v13 = Field_UInt32;
    if ( Field_UInt32 >= 0 )
    {
      v14 = *(_QWORD *)a1;
      v32 = a2 + 3;
      v33 = 0;
      v34 = 1;
      v15 = SRCacheContext_GetField_String(v14, L"HostId", &v33);
      v16 = v15;
      if ( v15 >= 0 )
        v16 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v15,
          (int)v32);
      if ( v34 )
      {
        v17 = *v32;
        *v32 = v33;
        if ( v17 )
          SRCache_Free(v17);
      }
      if ( v16 >= 0 )
      {
        v18 = *(_QWORD *)a1;
        v32 = a2 + 4;
        v33 = 0;
        v34 = 1;
        v19 = SRCacheContext_GetField_String(v18, L"Executable", &v33);
        v20 = v19;
        if ( v19 >= 0 )
          v20 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x246,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
            (const char *)(unsigned int)v19,
            (int)v32);
        if ( v34 )
        {
          v21 = *v32;
          *v32 = v33;
          if ( v21 )
            SRCache_Free(v21);
        }
        if ( v20 >= 0 )
        {
          v33 = 0;
          v32 = a2 + 5;
          v34 = 1;
          Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Entrypoint", &v33);
          wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>((__int64 **)&v32);
          if ( Field >= 0 )
          {
            v23 = *(_QWORD *)a1;
            v32 = a2 + 6;
            v33 = 0;
            v34 = 1;
            v24 = SRCacheContext_GetField_String(v23, L"RuntimeType", &v33);
            v25 = v24;
            if ( v24 >= 0 )
              v25 = 0;
            else
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x246,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
                (const char *)(unsigned int)v24,
                (int)v32);
            if ( v34 )
            {
              v26 = *v32;
              *v32 = v33;
              if ( v26 )
                SRCache_Free(v26);
            }
            if ( v25 >= 0 )
            {
              v27 = *(_QWORD *)a1;
              v32 = a2 + 7;
              v33 = 0;
              v34 = 1;
              v28 = SRCacheContext_GetField_String(v27, L"StartPage", &v33);
              v29 = v28;
              if ( v28 >= 0 )
                v29 = 0;
              else
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x246,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
                  (const char *)(unsigned int)v28,
                  (int)v32);
              if ( v34 )
              {
                v30 = *v32;
                *v32 = v33;
                if ( v30 )
                  SRCache_Free(v30);
              }
              if ( v29 >= 0 )
              {
                v33 = 0;
                v32 = a2 + 8;
                v34 = 1;
                v31 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"ResourceGroup", &v33);
                wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>((__int64 **)&v32);
                if ( v31 >= 0 )
                {
                  *a2 = a4;
                  return 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x3B1,
                    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
                    (const char *)(unsigned int)v31,
                    (int)v32);
                  return (unsigned int)v31;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x3AD,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
                  (const char *)(unsigned int)v29,
                  (int)v32);
                return (unsigned int)v29;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3A9,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
                (const char *)(unsigned int)v25,
                (int)v32);
              return (unsigned int)v25;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3A5,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
              (const char *)(unsigned int)Field,
              (int)v32);
            return (unsigned int)Field;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3A1,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
            (const char *)(unsigned int)v20,
            (int)v32);
          return (unsigned int)v20;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39D,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
          (const char *)(unsigned int)v16,
          (int)v32);
        return (unsigned int)v16;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)Field_UInt32,
        (int)v32);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x399,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
        (const char *)v13,
        (int)v32);
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x395,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v9,
      (int)v32);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x180008600  push    rbp
0x180008602  push    rbx
0x180008603  push    rsi
0x180008604  push    rdi
0x180008605  push    r14
0x180008607  push    r15
0x180008609  mov     rbp, rsp
0x18000860c  sub     rsp, 48h
0x180008610  lea     rax, [rdx+8]
0x180008614  mov     [rbp+var_18], 1
0x180008618  mov     rdi, rdx
0x18000861b  mov     [rbp+var_28], rax
0x18000861f  mov     rsi, rcx
0x180008622  lea     rdx, aActivationkey; "ActivationKey"
0x180008629  mov     rcx, [rcx]
0x18000862c  lea     r8, [rbp+var_20]
0x180008630  xor     r15d, r15d
0x180008633  mov     r14, r9
0x180008636  mov     [rbp+var_20], r15
0x18000863a  call    cs:__imp_SRCacheContext_GetField_String
0x180008640  mov     ebx, eax
0x180008642  test    eax, eax
0x180008644  jns     short loc_180008660
0x180008646  mov     rcx, [rbp+30h]; this
0x18000864a  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008651  mov     r9d, eax; char *
0x180008654  mov     edx, 246h; void *
0x180008659  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000865e  jmp     short loc_180008663
0x180008660  mov     ebx, r15d
0x180008663  cmp     [rbp+var_18], r15b
0x180008667  jz      short loc_180008682
0x180008669  mov     rdx, [rbp+var_28]
0x18000866d  mov     rax, [rbp+var_20]
0x180008671  mov     rcx, [rdx]
0x180008674  mov     [rdx], rax
0x180008677  test    rcx, rcx
0x18000867a  jz      short loc_180008682
0x18000867c  call    cs:__imp_SRCache_Free
0x180008682  test    ebx, ebx
0x180008684  jns     short loc_1800086A5
0x180008686  mov     rcx, [rbp+30h]; this
0x18000868a  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008691  mov     r9d, ebx; char *
0x180008694  mov     edx, 395h; void *
0x180008699  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000869e  mov     eax, ebx
0x1800086a0  jmp     loc_1800089C3
0x1800086a5  mov     rcx, [rsi]
0x1800086a8  lea     r8, [rdi+10h]
0x1800086ac  lea     rdx, aFlags; "Flags"
0x1800086b3  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800086b9  mov     ebx, eax
0x1800086bb  test    eax, eax
0x1800086bd  jns     short loc_1800086FE
0x1800086bf  mov     rcx, [rbp+30h]; this
0x1800086c3  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800086ca  mov     r9d, eax; char *
0x1800086cd  mov     edx, 221h; void *
0x1800086d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086d7  mov     rcx, [rbp+30h]; this
0x1800086db  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800086e2  mov     r9d, ebx; char *
0x1800086e5  mov     edx, 399h; void *
0x1800086ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086ef  mov     eax, ebx
0x1800086f1  add     rsp, 48h
0x1800086f5  pop     r15
0x1800086f7  pop     r14
0x1800086f9  pop     rdi
0x1800086fa  pop     rsi
0x1800086fb  pop     rbx
0x1800086fc  pop     rbp
0x1800086fd  retn
0x1800086fe  mov     rcx, [rsi]
0x180008701  lea     rax, [rdi+18h]
0x180008705  lea     r8, [rbp+var_20]
0x180008709  mov     [rbp+var_28], rax
0x18000870d  lea     rdx, aHostid; "HostId"
0x180008714  mov     [rbp+var_20], r15
0x180008718  mov     [rbp+var_18], 1
0x18000871c  call    cs:__imp_SRCacheContext_GetField_String
0x180008722  mov     ebx, eax
0x180008724  test    eax, eax
0x180008726  jns     short loc_180008742
0x180008728  mov     rcx, [rbp+30h]; this
0x18000872c  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008733  mov     r9d, eax; char *
0x180008736  mov     edx, 246h; void *
0x18000873b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008740  jmp     short loc_180008745
0x180008742  mov     ebx, r15d
0x180008745  cmp     [rbp+var_18], r15b
0x180008749  jz      short loc_180008764
0x18000874b  mov     rdx, [rbp+var_28]
0x18000874f  mov     rax, [rbp+var_20]
0x180008753  mov     rcx, [rdx]
0x180008756  mov     [rdx], rax
0x180008759  test    rcx, rcx
0x18000875c  jz      short loc_180008764
0x18000875e  call    cs:__imp_SRCache_Free
0x180008764  test    ebx, ebx
0x180008766  jns     short loc_180008787
0x180008768  mov     rcx, [rbp+30h]; this
0x18000876c  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008773  mov     r9d, ebx; char *
0x180008776  mov     edx, 39Dh; void *
0x18000877b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008780  mov     eax, ebx
0x180008782  jmp     loc_1800089C3
0x180008787  mov     rcx, [rsi]
0x18000878a  lea     rax, [rdi+20h]
0x18000878e  lea     r8, [rbp+var_20]
0x180008792  mov     [rbp+var_28], rax
0x180008796  lea     rdx, aExecutable; "Executable"
0x18000879d  mov     [rbp+var_20], r15
0x1800087a1  mov     [rbp+var_18], 1
0x1800087a5  call    cs:__imp_SRCacheContext_GetField_String
0x1800087ab  mov     ebx, eax
0x1800087ad  test    eax, eax
0x1800087af  jns     short loc_1800087CB
0x1800087b1  mov     rcx, [rbp+30h]; this
0x1800087b5  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800087bc  mov     r9d, eax; char *
0x1800087bf  mov     edx, 246h; void *
0x1800087c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087c9  jmp     short loc_1800087CE
0x1800087cb  mov     ebx, r15d
0x1800087ce  cmp     [rbp+var_18], r15b
0x1800087d2  jz      short loc_1800087ED
0x1800087d4  mov     rdx, [rbp+var_28]
0x1800087d8  mov     rax, [rbp+var_20]
0x1800087dc  mov     rcx, [rdx]
0x1800087df  mov     [rdx], rax
0x1800087e2  test    rcx, rcx
0x1800087e5  jz      short loc_1800087ED
0x1800087e7  call    cs:__imp_SRCache_Free
0x1800087ed  test    ebx, ebx
0x1800087ef  jns     short loc_180008810
0x1800087f1  mov     rcx, [rbp+30h]; this
0x1800087f5  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800087fc  mov     r9d, ebx; char *
0x1800087ff  mov     edx, 3A1h; void *
0x180008804  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008809  mov     eax, ebx
0x18000880b  jmp     loc_1800089C3
0x180008810  lea     rax, [rdi+28h]
0x180008814  mov     [rbp+var_20], r15
0x180008818  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18000881c  mov     [rbp+var_28], rax
0x180008820  lea     rdx, aEntrypoint; "Entrypoint"
0x180008827  mov     [rbp+var_18], 1
0x18000882b  mov     rcx, rsi; this
0x18000882e  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180008833  lea     rcx, [rbp+var_28]
0x180008837  mov     ebx, eax
0x180008839  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18000883e  test    ebx, ebx
0x180008840  jns     short loc_180008861
0x180008842  mov     rcx, [rbp+30h]; this
0x180008846  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000884d  mov     r9d, ebx; char *
0x180008850  mov     edx, 3A5h; void *
0x180008855  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000885a  mov     eax, ebx
0x18000885c  jmp     loc_1800089C3
0x180008861  mov     rcx, [rsi]
0x180008864  lea     rax, [rdi+30h]
0x180008868  lea     r8, [rbp+var_20]
0x18000886c  mov     [rbp+var_28], rax
0x180008870  lea     rdx, aRuntimetype; "RuntimeType"
0x180008877  mov     [rbp+var_20], r15
0x18000887b  mov     [rbp+var_18], 1
0x18000887f  call    cs:__imp_SRCacheContext_GetField_String
0x180008885  mov     ebx, eax
0x180008887  test    eax, eax
0x180008889  jns     short loc_1800088A5
0x18000888b  mov     rcx, [rbp+30h]; this
0x18000888f  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008896  mov     r9d, eax; char *
0x180008899  mov     edx, 246h; void *
0x18000889e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088a3  jmp     short loc_1800088A8
0x1800088a5  mov     ebx, r15d
0x1800088a8  cmp     [rbp+var_18], r15b
0x1800088ac  jz      short loc_1800088C7
0x1800088ae  mov     rdx, [rbp+var_28]
0x1800088b2  mov     rax, [rbp+var_20]
0x1800088b6  mov     rcx, [rdx]
0x1800088b9  mov     [rdx], rax
0x1800088bc  test    rcx, rcx
0x1800088bf  jz      short loc_1800088C7
0x1800088c1  call    cs:__imp_SRCache_Free
0x1800088c7  test    ebx, ebx
0x1800088c9  jns     short loc_1800088EA
0x1800088cb  mov     rcx, [rbp+30h]; this
0x1800088cf  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800088d6  mov     r9d, ebx; char *
0x1800088d9  mov     edx, 3A9h; void *
0x1800088de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088e3  mov     eax, ebx
0x1800088e5  jmp     loc_1800089C3
0x1800088ea  mov     rcx, [rsi]
0x1800088ed  lea     rax, [rdi+38h]
0x1800088f1  lea     r8, [rbp+var_20]
0x1800088f5  mov     [rbp+var_28], rax
0x1800088f9  lea     rdx, aStartpage; "StartPage"
0x180008900  mov     [rbp+var_20], r15
0x180008904  mov     [rbp+var_18], 1
0x180008908  call    cs:__imp_SRCacheContext_GetField_String
0x18000890e  mov     ebx, eax
0x180008910  test    eax, eax
0x180008912  jns     short loc_18000892E
0x180008914  mov     rcx, [rbp+30h]; this
0x180008918  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000891f  mov     r9d, eax; char *
0x180008922  mov     edx, 246h; void *
0x180008927  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000892c  jmp     short loc_180008931
0x18000892e  mov     ebx, r15d
0x180008931  cmp     [rbp+var_18], r15b
0x180008935  jz      short loc_180008950
0x180008937  mov     rdx, [rbp+var_28]
0x18000893b  mov     rax, [rbp+var_20]
0x18000893f  mov     rcx, [rdx]
0x180008942  mov     [rdx], rax
0x180008945  test    rcx, rcx
0x180008948  jz      short loc_180008950
0x18000894a  call    cs:__imp_SRCache_Free
0x180008950  test    ebx, ebx
0x180008952  jns     short loc_180008970
0x180008954  mov     rcx, [rbp+30h]; this
0x180008958  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000895f  mov     r9d, ebx; char *
0x180008962  mov     edx, 3ADh; void *
0x180008967  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000896c  mov     eax, ebx
0x18000896e  jmp     short loc_1800089C3
0x180008970  lea     rax, [rdi+40h]
0x180008974  mov     [rbp+var_20], r15
0x180008978  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18000897c  mov     [rbp+var_28], rax
0x180008980  lea     rdx, aResourcegroup; "ResourceGroup"
0x180008987  mov     [rbp+var_18], 1
0x18000898b  mov     rcx, rsi; this
0x18000898e  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180008993  lea     rcx, [rbp+var_28]
0x180008997  mov     ebx, eax
0x180008999  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18000899e  test    ebx, ebx
0x1800089a0  jns     short loc_1800089BE
0x1800089a2  mov     rcx, [rbp+30h]; this
0x1800089a6  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800089ad  mov     r9d, ebx; char *
0x1800089b0  mov     edx, 3B1h; void *
0x1800089b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089ba  mov     eax, ebx
0x1800089bc  jmp     short loc_1800089C3
0x1800089be  mov     [rdi], r14
0x1800089c1  xor     eax, eax
0x1800089c3  add     rsp, 48h
0x1800089c7  pop     r15
0x1800089c9  pop     r14
0x1800089cb  pop     rdi
0x1800089cc  pop     rsi
0x1800089cd  pop     rbx
0x1800089ce  pop     rbp
0x1800089cf  retn
```
