# StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,__int64)

- ea: `0x18000e4d0`
- end: `0x18000e8f2`
- name: `?ContextToObject@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `1058`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001855c`

## callees

- `0x180007ae0`
- `0x180007c78`
- `0x18000e4d0`
- `0x18000ee70`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e55d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e649`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e6de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e7c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e859`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e55d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e649`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e6de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e7c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e859`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000e515`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000e601`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000e696`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000e77c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000e811`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000e515`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000e601`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000e696`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000e77c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000e811`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18000e59a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18000e59a`

## string_xrefs

- `0x18000e52b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e5b0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e617`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e6ac`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e792`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e827`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e571`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18000e5c8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18000e65d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18000e6f2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18000e743`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18000e7d8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18000e86d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18000e8bb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

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
  unsigned __int16 **v32; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v33; // [rsp+28h] [rbp-18h] BYREF
  char v34; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]

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
      SRCache_Free();
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
          SRCache_Free();
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
            SRCache_Free();
        }
        if ( v20 >= 0 )
        {
          v33 = 0;
          v32 = a2 + 5;
          v34 = 1;
          Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Entrypoint", &v33);
          wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v32);
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
                SRCache_Free();
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
                  SRCache_Free();
              }
              if ( v29 >= 0 )
              {
                v33 = 0;
                v32 = a2 + 8;
                v34 = 1;
                v31 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"ResourceGroup", &v33);
                wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v32);
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
0x18000e4d0  mov     [rsp-18h+arg_0], rbx
0x18000e4d5  mov     [rsp-18h+arg_8], rsi
0x18000e4da  mov     [rsp-18h+arg_10], rdi
0x18000e4df  push    rbp
0x18000e4e0  push    r14
0x18000e4e2  push    r15
0x18000e4e4  mov     rbp, rsp
0x18000e4e7  sub     rsp, 40h
0x18000e4eb  lea     rax, [rdx+8]
0x18000e4ef  mov     [rbp+var_10], 1
0x18000e4f3  mov     rdi, rdx
0x18000e4f6  mov     [rbp+var_20], rax
0x18000e4fa  mov     rsi, rcx
0x18000e4fd  lea     rdx, aActivationkey; "ActivationKey"
0x18000e504  mov     rcx, [rcx]
0x18000e507  lea     r8, [rbp+var_18]
0x18000e50b  xor     r15d, r15d
0x18000e50e  mov     r14, r9
0x18000e511  mov     [rbp+var_18], r15
0x18000e515  call    cs:__imp_SRCacheContext_GetField_String
0x18000e51c  nop     dword ptr [rax+rax+00h]
0x18000e521  mov     ebx, eax
0x18000e523  test    eax, eax
0x18000e525  jns     short loc_18000E541
0x18000e527  mov     rcx, [rbp+18h]; this
0x18000e52b  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e532  mov     r9d, eax; char *
0x18000e535  mov     edx, 246h; void *
0x18000e53a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e53f  jmp     short loc_18000E544
0x18000e541  mov     ebx, r15d
0x18000e544  cmp     [rbp+var_10], r15b
0x18000e548  jz      short loc_18000E569
0x18000e54a  mov     rdx, [rbp+var_20]
0x18000e54e  mov     rax, [rbp+var_18]
0x18000e552  mov     rcx, [rdx]
0x18000e555  mov     [rdx], rax
0x18000e558  test    rcx, rcx
0x18000e55b  jz      short loc_18000E569
0x18000e55d  call    cs:__imp_SRCache_Free
0x18000e564  nop     dword ptr [rax+rax+00h]
0x18000e569  test    ebx, ebx
0x18000e56b  jns     short loc_18000E58C
0x18000e56d  mov     rcx, [rbp+18h]; this
0x18000e571  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e578  mov     r9d, ebx; char *
0x18000e57b  mov     edx, 395h; void *
0x18000e580  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e585  mov     eax, ebx
0x18000e587  jmp     loc_18000E8D8
0x18000e58c  mov     rcx, [rsi]
0x18000e58f  lea     r8, [rdi+10h]
0x18000e593  lea     rdx, aFlags; "Flags"
0x18000e59a  call    cs:__imp_SRCacheContext_GetField_UInt32
0x18000e5a1  nop     dword ptr [rax+rax+00h]
0x18000e5a6  mov     ebx, eax
0x18000e5a8  test    eax, eax
0x18000e5aa  jns     short loc_18000E5E3
0x18000e5ac  mov     rcx, [rbp+18h]; this
0x18000e5b0  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e5b7  mov     r9d, eax; char *
0x18000e5ba  mov     edx, 221h; void *
0x18000e5bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e5c4  mov     rcx, [rbp+18h]; this
0x18000e5c8  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e5cf  mov     r9d, ebx; char *
0x18000e5d2  mov     edx, 399h; void *
0x18000e5d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e5dc  mov     eax, ebx
0x18000e5de  jmp     loc_18000E8D8
0x18000e5e3  mov     rcx, [rsi]
0x18000e5e6  lea     rax, [rdi+18h]
0x18000e5ea  lea     r8, [rbp+var_18]
0x18000e5ee  mov     [rbp+var_20], rax
0x18000e5f2  lea     rdx, aHostid; "HostId"
0x18000e5f9  mov     [rbp+var_18], r15
0x18000e5fd  mov     [rbp+var_10], 1
0x18000e601  call    cs:__imp_SRCacheContext_GetField_String
0x18000e608  nop     dword ptr [rax+rax+00h]
0x18000e60d  mov     ebx, eax
0x18000e60f  test    eax, eax
0x18000e611  jns     short loc_18000E62D
0x18000e613  mov     rcx, [rbp+18h]; this
0x18000e617  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e61e  mov     r9d, eax; char *
0x18000e621  mov     edx, 246h; void *
0x18000e626  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e62b  jmp     short loc_18000E630
0x18000e62d  mov     ebx, r15d
0x18000e630  cmp     [rbp+var_10], r15b
0x18000e634  jz      short loc_18000E655
0x18000e636  mov     rdx, [rbp+var_20]
0x18000e63a  mov     rax, [rbp+var_18]
0x18000e63e  mov     rcx, [rdx]
0x18000e641  mov     [rdx], rax
0x18000e644  test    rcx, rcx
0x18000e647  jz      short loc_18000E655
0x18000e649  call    cs:__imp_SRCache_Free
0x18000e650  nop     dword ptr [rax+rax+00h]
0x18000e655  test    ebx, ebx
0x18000e657  jns     short loc_18000E678
0x18000e659  mov     rcx, [rbp+18h]; this
0x18000e65d  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e664  mov     r9d, ebx; char *
0x18000e667  mov     edx, 39Dh; void *
0x18000e66c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e671  mov     eax, ebx
0x18000e673  jmp     loc_18000E8D8
0x18000e678  mov     rcx, [rsi]
0x18000e67b  lea     rax, [rdi+20h]
0x18000e67f  lea     r8, [rbp+var_18]
0x18000e683  mov     [rbp+var_20], rax
0x18000e687  lea     rdx, aExecutable; "Executable"
0x18000e68e  mov     [rbp+var_18], r15
0x18000e692  mov     [rbp+var_10], 1
0x18000e696  call    cs:__imp_SRCacheContext_GetField_String
0x18000e69d  nop     dword ptr [rax+rax+00h]
0x18000e6a2  mov     ebx, eax
0x18000e6a4  test    eax, eax
0x18000e6a6  jns     short loc_18000E6C2
0x18000e6a8  mov     rcx, [rbp+18h]; this
0x18000e6ac  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e6b3  mov     r9d, eax; char *
0x18000e6b6  mov     edx, 246h; void *
0x18000e6bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e6c0  jmp     short loc_18000E6C5
0x18000e6c2  mov     ebx, r15d
0x18000e6c5  cmp     [rbp+var_10], r15b
0x18000e6c9  jz      short loc_18000E6EA
0x18000e6cb  mov     rdx, [rbp+var_20]
0x18000e6cf  mov     rax, [rbp+var_18]
0x18000e6d3  mov     rcx, [rdx]
0x18000e6d6  mov     [rdx], rax
0x18000e6d9  test    rcx, rcx
0x18000e6dc  jz      short loc_18000E6EA
0x18000e6de  call    cs:__imp_SRCache_Free
0x18000e6e5  nop     dword ptr [rax+rax+00h]
0x18000e6ea  test    ebx, ebx
0x18000e6ec  jns     short loc_18000E70D
0x18000e6ee  mov     rcx, [rbp+18h]; this
0x18000e6f2  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e6f9  mov     r9d, ebx; char *
0x18000e6fc  mov     edx, 3A1h; void *
0x18000e701  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e706  mov     eax, ebx
0x18000e708  jmp     loc_18000E8D8
0x18000e70d  lea     rax, [rdi+28h]
0x18000e711  mov     [rbp+var_18], r15
0x18000e715  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18000e719  mov     [rbp+var_20], rax
0x18000e71d  lea     rdx, aEntrypoint; "Entrypoint"
0x18000e724  mov     [rbp+var_10], 1
0x18000e728  mov     rcx, rsi; this
0x18000e72b  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000e730  lea     rcx, [rbp+var_20]
0x18000e734  mov     ebx, eax
0x18000e736  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18000e73b  test    ebx, ebx
0x18000e73d  jns     short loc_18000E75E
0x18000e73f  mov     rcx, [rbp+18h]; this
0x18000e743  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e74a  mov     r9d, ebx; char *
0x18000e74d  mov     edx, 3A5h; void *
0x18000e752  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e757  mov     eax, ebx
0x18000e759  jmp     loc_18000E8D8
0x18000e75e  mov     rcx, [rsi]
0x18000e761  lea     rax, [rdi+30h]
0x18000e765  lea     r8, [rbp+var_18]
0x18000e769  mov     [rbp+var_20], rax
0x18000e76d  lea     rdx, aRuntimetype; "RuntimeType"
0x18000e774  mov     [rbp+var_18], r15
0x18000e778  mov     [rbp+var_10], 1
0x18000e77c  call    cs:__imp_SRCacheContext_GetField_String
0x18000e783  nop     dword ptr [rax+rax+00h]
0x18000e788  mov     ebx, eax
0x18000e78a  test    eax, eax
0x18000e78c  jns     short loc_18000E7A8
0x18000e78e  mov     rcx, [rbp+18h]; this
0x18000e792  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e799  mov     r9d, eax; char *
0x18000e79c  mov     edx, 246h; void *
0x18000e7a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e7a6  jmp     short loc_18000E7AB
0x18000e7a8  mov     ebx, r15d
0x18000e7ab  cmp     [rbp+var_10], r15b
0x18000e7af  jz      short loc_18000E7D0
0x18000e7b1  mov     rdx, [rbp+var_20]
0x18000e7b5  mov     rax, [rbp+var_18]
0x18000e7b9  mov     rcx, [rdx]
0x18000e7bc  mov     [rdx], rax
0x18000e7bf  test    rcx, rcx
0x18000e7c2  jz      short loc_18000E7D0
0x18000e7c4  call    cs:__imp_SRCache_Free
0x18000e7cb  nop     dword ptr [rax+rax+00h]
0x18000e7d0  test    ebx, ebx
0x18000e7d2  jns     short loc_18000E7F3
0x18000e7d4  mov     rcx, [rbp+18h]; this
0x18000e7d8  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e7df  mov     r9d, ebx; char *
0x18000e7e2  mov     edx, 3A9h; void *
0x18000e7e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e7ec  mov     eax, ebx
0x18000e7ee  jmp     loc_18000E8D8
0x18000e7f3  mov     rcx, [rsi]
0x18000e7f6  lea     rax, [rdi+38h]
0x18000e7fa  lea     r8, [rbp+var_18]
0x18000e7fe  mov     [rbp+var_20], rax
0x18000e802  lea     rdx, aStartpage; "StartPage"
0x18000e809  mov     [rbp+var_18], r15
0x18000e80d  mov     [rbp+var_10], 1
0x18000e811  call    cs:__imp_SRCacheContext_GetField_String
0x18000e818  nop     dword ptr [rax+rax+00h]
0x18000e81d  mov     ebx, eax
0x18000e81f  test    eax, eax
0x18000e821  jns     short loc_18000E83D
0x18000e823  mov     rcx, [rbp+18h]; this
0x18000e827  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e82e  mov     r9d, eax; char *
0x18000e831  mov     edx, 246h; void *
0x18000e836  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e83b  jmp     short loc_18000E840
0x18000e83d  mov     ebx, r15d
0x18000e840  cmp     [rbp+var_10], r15b
0x18000e844  jz      short loc_18000E865
0x18000e846  mov     rdx, [rbp+var_20]
0x18000e84a  mov     rax, [rbp+var_18]
0x18000e84e  mov     rcx, [rdx]
0x18000e851  mov     [rdx], rax
0x18000e854  test    rcx, rcx
0x18000e857  jz      short loc_18000E865
0x18000e859  call    cs:__imp_SRCache_Free
0x18000e860  nop     dword ptr [rax+rax+00h]
0x18000e865  test    ebx, ebx
0x18000e867  jns     short loc_18000E885
0x18000e869  mov     rcx, [rbp+18h]; this
0x18000e86d  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e874  mov     r9d, ebx; char *
0x18000e877  mov     edx, 3ADh; void *
0x18000e87c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e881  mov     eax, ebx
0x18000e883  jmp     short loc_18000E8D8
0x18000e885  lea     rax, [rdi+40h]
0x18000e889  mov     [rbp+var_18], r15
0x18000e88d  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18000e891  mov     [rbp+var_20], rax
0x18000e895  lea     rdx, aResourcegroup; "ResourceGroup"
0x18000e89c  mov     [rbp+var_10], 1
0x18000e8a0  mov     rcx, rsi; this
0x18000e8a3  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000e8a8  lea     rcx, [rbp+var_20]
0x18000e8ac  mov     ebx, eax
0x18000e8ae  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18000e8b3  test    ebx, ebx
0x18000e8b5  jns     short loc_18000E8D3
0x18000e8b7  mov     rcx, [rbp+18h]; this
0x18000e8bb  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e8c2  mov     r9d, ebx; char *
0x18000e8c5  mov     edx, 3B1h; void *
0x18000e8ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e8cf  mov     eax, ebx
0x18000e8d1  jmp     short loc_18000E8D8
0x18000e8d3  mov     [rdi], r14
0x18000e8d6  xor     eax, eax
0x18000e8d8  mov     rbx, [rsp+40h+arg_0]
0x18000e8dd  mov     rsi, [rsp+40h+arg_8]
0x18000e8e2  mov     rdi, [rsp+40h+arg_10]
0x18000e8e7  add     rsp, 40h
0x18000e8eb  pop     r15
0x18000e8ed  pop     r14
0x18000e8ef  pop     rbp
0x18000e8f0  retn
```
