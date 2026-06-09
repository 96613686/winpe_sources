# StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)

- ea: `0x18001abd0`
- end: `0x18001afce`
- name: `?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z`
- size: `1022`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800526e0`

## callees

- `0x180018be0`
- `0x18001a1f0`
- `0x18001a29c`
- `0x18001abd0`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18001ac2b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18001ac2b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001ac7d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001ac7d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001aca1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ad1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001adee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ae81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001af52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001af89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001afbe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001aca1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ad1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001adee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ae81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001af52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001af89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001afbe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001adca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001adca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001ae76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001af3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001ae76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001af3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001ae13`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001ae13`

## string_xrefs

- `0x18001ae2a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001ae93`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001aeeb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001af10`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001acd0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001acf9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001ae57`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001aeae`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001aece`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001af9b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        bool *a4)
{
  __int64 v6; // rcx
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // ebx
  unsigned __int64 v12; // rdi
  __int64 *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rdx
  unsigned __int64 v25; // r9
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v34; // [rsp+28h] [rbp-D8h] BYREF
  int *v35; // [rsp+30h] [rbp-D0h]
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  char v37; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v40[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+258h] [rbp+158h]
  __int64 v42; // [rsp+260h] [rbp+160h]
  _BYTE *v43; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  v6 = *a1;
  if ( !v6 )
    return 0;
  v9 = *((unsigned int *)a1 + 2);
  v38 = 0;
  v10 = SRCacheContext_EnumerateData(v6, v9, &v38);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v12 = v38;
    if ( v38 )
    {
      v13 = (__int64 *)a1[2];
      v34 = 0;
      *(_QWORD *)v33 = 0;
      v35 = v33;
      v14 = *v13;
      v36 = 0;
      v37 = 1;
      v11 = SRCacheContext_Open(v14, L"Package\\Data", 0, &v36);
      if ( v37 )
      {
        v15 = *(_QWORD *)v35;
        *(_QWORD *)v35 = v36;
        if ( v15 )
          SRCacheContext_Close(v15);
      }
      if ( (v11 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18C,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)v11,
          v33[0]);
        v16 = 1192;
      }
      else
      {
        if ( *(_QWORD *)v33 )
        {
          v39 = 0;
          memset_0(v40, 0, sizeof(v40));
          v41 = 0;
          v43 = v40;
          v42 = 256;
          v20 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v39, v12);
          v11 = v20;
          if ( v20 < 0 )
          {
            v25 = (unsigned int)v20;
            v24 = 1196;
          }
          else
          {
            v35 = (int *)&v34;
            v36 = 0;
            v37 = 1;
            v11 = SRCacheContext_OpenSubContext(*(_QWORD *)v33, v43, 0, &v36);
            if ( v37 )
            {
              v21 = *(_QWORD *)v35;
              *(_QWORD *)v35 = v36;
              if ( v21 )
                SRCacheContext_Close(v21);
            }
            if ( (v11 & 0x80000000) != 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1B0,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
                (const char *)v11,
                v33[0]);
              v24 = 1197;
            }
            else
            {
              v22 = *(_QWORD *)v33;
              *a4 = v34 != 0;
              v23 = SRCacheContext_AddToCache(v22, L"Package\\Data");
              v11 = v23;
              if ( v23 >= 0 )
              {
                v28 = v39;
                v39 = 0;
                if ( v28 )
                  SRCache_Free(v28);
                v29 = *(_QWORD *)v33;
                *(_QWORD *)v33 = 0;
                if ( v29 )
                  SRCacheContext_Close(v29);
                if ( !*a4
                  || (v30 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&v34, a3, a2, v12),
                      v11 = v30,
                      v30 >= 0) )
                {
                  v31 = v34;
                  v34 = 0;
                  if ( v31 )
                    SRCacheContext_Close(v31);
                  return 0;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x45B,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
                  (const char *)(unsigned int)v30,
                  v33[0]);
                v32 = v34;
                v34 = 0;
                if ( v32 )
                  SRCacheContext_Close(v32);
LABEL_42:
                v27 = 1906;
                goto LABEL_29;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1A6,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
                (const char *)(unsigned int)v23,
                v33[0]);
              v24 = 1199;
            }
            v25 = v11;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v24,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
            (const char *)v25,
            v33[0]);
          v26 = v39;
          v39 = 0;
          if ( v26 )
            SRCache_Free(v26);
LABEL_11:
          v17 = *(_QWORD *)v33;
          *(_QWORD *)v33 = 0;
          if ( v17 )
            SRCacheContext_Close(v17);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x456,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
            (const char *)v11,
            v33[0]);
          v18 = v34;
          v34 = 0;
          if ( v18 )
            SRCacheContext_Close(v18);
          if ( (v11 & 0x80000000) == 0 )
            return 0;
          goto LABEL_42;
        }
        v11 = -2140733422;
        v16 = 1193;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)v11,
        v33[0]);
      goto LABEL_11;
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A6,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
    (const char *)(unsigned int)v10,
    v33[0]);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x755,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
    (const char *)v11,
    v33[0]);
  v27 = 1901;
LABEL_29:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v27,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
    (const char *)v11,
    v33[0]);
  return v11;
}

```

## disassembly

```asm
0x18001abd0  mov     [rsp-8+arg_8], rbx
0x18001abd5  push    rbp
0x18001abd6  push    rsi
0x18001abd7  push    rdi
0x18001abd8  push    r12
0x18001abda  push    r13
0x18001abdc  push    r14
0x18001abde  push    r15
0x18001abe0  lea     rbp, [rsp-180h]
0x18001abe8  sub     rsp, 280h
0x18001abef  mov     rax, cs:__security_cookie
0x18001abf6  xor     rax, rsp
0x18001abf9  mov     [rbp+1B0h+var_40], rax
0x18001ac00  xor     r13d, r13d
0x18001ac03  mov     rsi, rcx
0x18001ac06  mov     [r9], r13b
0x18001ac09  mov     r14, r9
0x18001ac0c  mov     rcx, [rcx]
0x18001ac0f  mov     r12, r8
0x18001ac12  mov     r15, rdx
0x18001ac15  test    rcx, rcx
0x18001ac18  jz      loc_18001AD2A
0x18001ac1e  mov     edx, [rsi+8]
0x18001ac21  lea     r8, [rsp+2B0h+var_268]
0x18001ac26  mov     [rsp+2B0h+var_268], r13
0x18001ac2b  call    cs:__imp_SRCacheContext_EnumerateData
0x18001ac31  mov     ebx, eax
0x18001ac33  test    eax, eax
0x18001ac35  js      loc_18001AE8C
0x18001ac3b  mov     rdi, [rsp+2B0h+var_268]
0x18001ac40  test    rdi, rdi
0x18001ac43  jz      loc_18001AD2A
0x18001ac49  mov     rcx, [rsi+10h]
0x18001ac4d  lea     rax, [rsp+2B0h+var_290]
0x18001ac52  lea     r9, [rsp+2B0h+var_278]
0x18001ac57  mov     [rsp+2B0h+var_288], r13
0x18001ac5c  xor     r8d, r8d
0x18001ac5f  mov     qword ptr [rsp+2B0h+var_290], r13; int
0x18001ac64  lea     rdx, aPackageData; "Package\\Data"
0x18001ac6b  mov     [rsp+2B0h+var_280], rax
0x18001ac70  mov     rcx, [rcx]
0x18001ac73  mov     [rsp+2B0h+var_278], r13
0x18001ac78  mov     [rsp+2B0h+var_270], 1
0x18001ac7d  call    cs:__imp_SRCacheContext_Open
0x18001ac83  mov     ebx, eax
0x18001ac85  cmp     [rsp+2B0h+var_270], r13b
0x18001ac8a  jz      short loc_18001ACA7
0x18001ac8c  mov     rdx, [rsp+2B0h+var_280]
0x18001ac91  mov     rax, [rsp+2B0h+var_278]
0x18001ac96  mov     rcx, [rdx]
0x18001ac99  mov     [rdx], rax
0x18001ac9c  test    rcx, rcx
0x18001ac9f  jz      short loc_18001ACA7
0x18001aca1  call    cs:__imp_SRCacheContext_Close
0x18001aca7  test    ebx, ebx
0x18001aca9  js      loc_18001AF09
0x18001acaf  cmp     qword ptr [rsp+2B0h+var_290], r13
0x18001acb4  setnz   al
0x18001acb7  test    al, al
0x18001acb9  jnz     loc_18001AD56
0x18001acbf  mov     ebx, 80670012h
0x18001acc4  mov     edx, 4A9h; void *
0x18001acc9  mov     rcx, [rbp+1B8h]; this
0x18001acd0  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001acd7  mov     r9d, ebx; char *
0x18001acda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001acdf  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001ace4  mov     qword ptr [rsp+2B0h+var_290], r13; int
0x18001ace9  test    rcx, rcx
0x18001acec  jnz     loc_18001AE81
0x18001acf2  mov     rcx, [rbp+1B8h]; this
0x18001acf9  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ad00  mov     r9d, ebx; char *
0x18001ad03  mov     edx, 456h; void *
0x18001ad08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ad0d  mov     rcx, [rsp+2B0h+var_288]
0x18001ad12  mov     [rsp+2B0h+var_288], r13
0x18001ad17  test    rcx, rcx
0x18001ad1a  jz      short loc_18001AD22
0x18001ad1c  call    cs:__imp_SRCacheContext_Close
0x18001ad22  test    ebx, ebx
0x18001ad24  js      loc_18001AFC4
0x18001ad2a  xor     eax, eax
0x18001ad2c  mov     rcx, [rbp+1B0h+var_40]
0x18001ad33  xor     rcx, rsp; StackCookie
0x18001ad36  call    __security_check_cookie
0x18001ad3b  mov     rbx, [rsp+2B0h+arg_8]
0x18001ad43  add     rsp, 280h
0x18001ad4a  pop     r15
0x18001ad4c  pop     r14
0x18001ad4e  pop     r13
0x18001ad50  pop     r12
0x18001ad52  pop     rdi
0x18001ad53  pop     rsi
0x18001ad54  pop     rbp
0x18001ad55  retn
0x18001ad56  xor     edx, edx; Val
0x18001ad58  mov     [rsp+2B0h+var_260], r13
0x18001ad5d  mov     r8d, 200h; Size
0x18001ad63  lea     rcx, [rsp+2B0h+var_258]; void *
0x18001ad68  call    memset_0
0x18001ad6d  lea     rax, [rsp+2B0h+var_258]
0x18001ad72  mov     [rbp+1B0h+var_58], r13
0x18001ad79  mov     rdx, rdi; unsigned __int64
0x18001ad7c  mov     [rbp+1B0h+var_48], rax
0x18001ad83  lea     rcx, [rsp+2B0h+var_260]; this
0x18001ad88  mov     [rbp+1B0h+var_50], 100h
0x18001ad93  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001ad98  mov     ebx, eax
0x18001ad9a  test    eax, eax
0x18001ad9c  js      loc_18001AE48
0x18001ada2  mov     rdx, [rbp+1B0h+var_48]
0x18001ada9  lea     rax, [rsp+2B0h+var_288]
0x18001adae  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001adb3  lea     r9, [rsp+2B0h+var_278]
0x18001adb8  xor     r8d, r8d
0x18001adbb  mov     [rsp+2B0h+var_280], rax
0x18001adc0  mov     [rsp+2B0h+var_278], r13
0x18001adc5  mov     [rsp+2B0h+var_270], 1
0x18001adca  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001add0  mov     ebx, eax
0x18001add2  cmp     [rsp+2B0h+var_270], r13b
0x18001add7  jz      short loc_18001ADF4
0x18001add9  mov     rdx, [rsp+2B0h+var_280]
0x18001adde  mov     rax, [rsp+2B0h+var_278]
0x18001ade3  mov     rcx, [rdx]
0x18001ade6  mov     [rdx], rax
0x18001ade9  test    rcx, rcx
0x18001adec  jz      short loc_18001ADF4
0x18001adee  call    cs:__imp_SRCacheContext_Close
0x18001adf4  test    ebx, ebx
0x18001adf6  js      loc_18001AEE4
0x18001adfc  cmp     [rsp+2B0h+var_288], r13
0x18001ae01  lea     rdx, aPackageData; "Package\\Data"
0x18001ae08  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001ae0d  setnz   al
0x18001ae10  mov     [r14], al
0x18001ae13  call    cs:__imp_SRCacheContext_AddToCache
0x18001ae19  mov     ebx, eax
0x18001ae1b  test    eax, eax
0x18001ae1d  jns     loc_18001AF2E
0x18001ae23  mov     rcx, [rbp+1B8h]; this
0x18001ae2a  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ae31  mov     r9d, eax; char *
0x18001ae34  mov     edx, 1A6h; void *
0x18001ae39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae3e  mov     edx, 4AFh
0x18001ae43  mov     r9d, ebx
0x18001ae46  jmp     short loc_18001AE50
0x18001ae48  mov     r9d, eax; char *
0x18001ae4b  mov     edx, 4ACh; void *
0x18001ae50  mov     rcx, [rbp+1B8h]; this
0x18001ae57  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ae5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae63  mov     rcx, [rsp+2B0h+var_260]
0x18001ae68  mov     [rsp+2B0h+var_260], r13
0x18001ae6d  test    rcx, rcx
0x18001ae70  jz      loc_18001ACDF
0x18001ae76  call    cs:__imp_SRCache_Free
0x18001ae7c  jmp     loc_18001ACDF
0x18001ae81  call    cs:__imp_SRCacheContext_Close
0x18001ae87  jmp     loc_18001ACF2
0x18001ae8c  mov     rcx, [rbp+1B8h]; this
0x18001ae93  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ae9a  mov     r9d, ebx; char *
0x18001ae9d  mov     edx, 2A6h; void *
0x18001aea2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aea7  mov     rcx, [rbp+1B8h]; this
0x18001aeae  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001aeb5  mov     r9d, ebx; char *
0x18001aeb8  mov     edx, 755h; void *
0x18001aebd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aec2  mov     edx, 76Dh; void *
0x18001aec7  mov     rcx, [rbp+1B8h]; this
0x18001aece  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001aed5  mov     r9d, ebx; char *
0x18001aed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aedd  mov     eax, ebx
0x18001aedf  jmp     loc_18001AD2C
0x18001aee4  mov     rcx, [rbp+1B8h]; this
0x18001aeeb  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001aef2  mov     r9d, ebx; char *
0x18001aef5  mov     edx, 1B0h; void *
0x18001aefa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aeff  mov     edx, 4ADh
0x18001af04  jmp     loc_18001AE43
0x18001af09  mov     rcx, [rbp+1B8h]; this
0x18001af10  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001af17  mov     r9d, ebx; char *
0x18001af1a  mov     edx, 18Ch; void *
0x18001af1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001af24  mov     edx, 4A8h
0x18001af29  jmp     loc_18001ACC9
0x18001af2e  mov     rcx, [rsp+2B0h+var_260]
0x18001af33  mov     [rsp+2B0h+var_260], r13
0x18001af38  test    rcx, rcx
0x18001af3b  jz      short loc_18001AF43
0x18001af3d  call    cs:__imp_SRCache_Free
0x18001af43  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18001af48  mov     qword ptr [rsp+2B0h+var_290], r13; int
0x18001af4d  test    rcx, rcx
0x18001af50  jz      short loc_18001AF58
0x18001af52  call    cs:__imp_SRCacheContext_Close
0x18001af58  cmp     [r14], r13b
0x18001af5b  jz      short loc_18001AF76
0x18001af5d  mov     r9, rdi
0x18001af60  lea     rcx, [rsp+2B0h+var_288]
0x18001af65  mov     r8, r15
0x18001af68  mov     rdx, r12
0x18001af6b  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x18001af70  mov     ebx, eax
0x18001af72  test    eax, eax
0x18001af74  js      short loc_18001AF94
0x18001af76  mov     rcx, [rsp+2B0h+var_288]
0x18001af7b  mov     [rsp+2B0h+var_288], r13
0x18001af80  test    rcx, rcx
0x18001af83  jz      loc_18001AD2A
0x18001af89  call    cs:__imp_SRCacheContext_Close
0x18001af8f  jmp     loc_18001AD2A
0x18001af94  mov     rcx, [rbp+1B8h]; this
0x18001af9b  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001afa2  mov     r9d, eax; char *
0x18001afa5  mov     edx, 45Bh; void *
0x18001afaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001afaf  mov     rcx, [rsp+2B0h+var_288]
0x18001afb4  mov     [rsp+2B0h+var_288], r13
0x18001afb9  test    rcx, rcx
0x18001afbc  jz      short loc_18001AFC4
0x18001afbe  call    cs:__imp_SRCacheContext_Close
0x18001afc4  mov     edx, 772h
0x18001afc9  jmp     loc_18001AEC7
```
