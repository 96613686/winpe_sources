# StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)

- ea: `0x180063c0c`
- end: `0x18006409f`
- name: `?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z`
- size: `1171`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180062a00`
- `0x180063308`

## callees

- `0x18001a140`
- `0x18002c8d0`
- `0x180063c0c`
- `0x1800640a8`
- `0x1800862f0`
- `0x180086e44`
- `0x180086f7c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063e76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063f34`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063e76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063f34`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063cb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063e19`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063e61`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063e8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063f1f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063f49`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063cb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063e19`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063e61`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063e8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063f1f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063f49`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180063c89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180063c89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180063def`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180063def`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180063e42`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180063e42`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x180063ebc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x180063ebc`

## string_xrefs

- `0x180063f7f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180064008`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180064032`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180063ee1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180063fc1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006405c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180064081`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180063f01`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x180063f62`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x180063f9f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x180063fed`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        bool *a4)
{
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  bool v10; // r8
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int IsEmpty; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  int v28[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v29; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD v30[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v32[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+248h] [rbp+148h]
  __int64 v34; // [rsp+250h] [rbp+150h]
  _BYTE *v35; // [rsp+258h] [rbp+158h]
  unsigned __int16 v36[4]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v37; // [rsp+268h] [rbp+168h] BYREF
  char v38; // [rsp+270h] [rbp+170h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *a4 = 0;
  if ( !a2 )
  {
    v25 = 153;
LABEL_37:
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)0x80070057LL,
      v28[0]);
    return (unsigned int)v8;
  }
  if ( !a3 )
  {
    v25 = 154;
    goto LABEL_37;
  }
  v7 = *(_QWORD *)a1;
  *(_QWORD *)v36 = v28;
  *(_QWORD *)v28 = 0;
  v37 = 0;
  v38 = 1;
  v8 = SRCacheContext_Open(v7, L"PackageUser\\Index\\UserAndPackage", 0, &v37);
  if ( v38 )
  {
    v9 = **(_QWORD **)v36;
    **(_QWORD **)v36 = v37;
    if ( v9 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
    v27 = 158;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
LABEL_33:
    v24 = *(_QWORD *)v28;
    *(_QWORD *)v28 = 0;
    if ( v24 )
      SRCacheContext_Close(v24, v21);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v28 )
  {
    v8 = -2140733422;
    v27 = 159;
    goto LABEL_43;
  }
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v33 = 0;
  v34 = 256;
  v35 = v32;
  if ( (unsigned int)o__ui64tow_s_0(a2, v36, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v28[0]);
    goto LABEL_45;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, v36);
  if ( v8 < 0 )
  {
LABEL_45:
    v26 = 162;
    goto LABEL_39;
  }
  v11 = StateRepository::Cache::Key_NoThrow::EnsureCapacity((StateRepository::Cache::Key_NoThrow *)&v31, v33 + 2, v10);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)(unsigned int)v11,
      v28[0]);
    v26 = 163;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
LABEL_31:
    v23 = v31;
    v31 = 0;
    if ( v23 )
      SRCache_Free();
    goto LABEL_33;
  }
  *(_DWORD *)&v35[2 * v33++] = 94;
  if ( (unsigned int)o__ui64tow_s_0(a3, v36, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v28[0]);
    goto LABEL_47;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, v36);
  if ( v8 < 0 )
  {
LABEL_47:
    v26 = 164;
    goto LABEL_39;
  }
  *(_QWORD *)v36 = &v29;
  v29 = 0;
  v37 = 0;
  v38 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v28, v35, 0, &v37);
  if ( v38 )
  {
    v12 = **(_QWORD **)v36;
    **(_QWORD **)v36 = v37;
    if ( v12 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
    v20 = 168;
    goto LABEL_29;
  }
  if ( v29 )
  {
    v30[0] = 0;
    IsEmpty = SRCacheContext_IsEmpty(v29, v30);
    v8 = IsEmpty;
    if ( IsEmpty < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B8,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)IsEmpty,
        v28[0]);
      v20 = 172;
      goto LABEL_29;
    }
    *a4 = v30[0] == 0;
  }
  v13 = SRCacheContext_AddToCache(*(_QWORD *)v28, L"PackageUser\\Index\\UserAndPackage");
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      v28[0]);
    v20 = 176;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
    v22 = v29;
    v29 = 0;
    if ( v22 )
      ((void (*)(void))SRCacheContext_Close)();
    goto LABEL_31;
  }
  v15 = v29;
  v29 = 0;
  if ( v15 )
    SRCacheContext_Close(v15, v14);
  v16 = v31;
  v31 = 0;
  if ( v16 )
    SRCache_Free();
  v17 = *(_QWORD *)v28;
  *(_QWORD *)v28 = 0;
  if ( v17 )
    SRCacheContext_Close(v17, v14);
  return 0;
}

```

## disassembly

```asm
0x180063c0c  push    rbp
0x180063c0e  push    rbx
0x180063c0f  push    rsi
0x180063c10  push    rdi
0x180063c11  push    r14
0x180063c13  push    r15
0x180063c15  lea     rbp, [rsp-198h]
0x180063c1d  sub     rsp, 298h
0x180063c24  mov     rax, cs:__security_cookie
0x180063c2b  xor     rax, rsp
0x180063c2e  mov     [rbp+1C0h+var_38], rax
0x180063c35  xor     r15d, r15d
0x180063c38  mov     r14, r9
0x180063c3b  mov     [r9], r15b
0x180063c3e  mov     rdi, r8
0x180063c41  mov     rsi, rdx
0x180063c44  test    rdx, rdx
0x180063c47  jz      loc_180063F56
0x180063c4d  test    r8, r8
0x180063c50  jz      loc_180063FB3
0x180063c56  mov     rcx, [rcx]
0x180063c59  lea     rax, [rsp+2C0h+var_2A0]
0x180063c5e  lea     r9, [rbp+1C0h+var_58]
0x180063c65  mov     qword ptr [rbp+1C0h+var_60], rax
0x180063c6c  xor     r8d, r8d
0x180063c6f  mov     qword ptr [rsp+2C0h+var_2A0], r15; int
0x180063c74  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x180063c7b  mov     [rbp+1C0h+var_58], r15
0x180063c82  mov     [rbp+1C0h+var_50], 1
0x180063c89  call    cs:__imp_SRCacheContext_Open
0x180063c8f  mov     ebx, eax
0x180063c91  cmp     [rbp+1C0h+var_50], r15b
0x180063c98  jz      short loc_180063CB9
0x180063c9a  mov     r8, qword ptr [rbp+1C0h+var_60]
0x180063ca1  mov     rdx, [rbp+1C0h+var_58]
0x180063ca8  mov     rcx, [r8]
0x180063cab  mov     [r8], rdx
0x180063cae  test    rcx, rcx
0x180063cb1  jz      short loc_180063CB9
0x180063cb3  call    cs:__imp_SRCacheContext_Close
0x180063cb9  test    ebx, ebx
0x180063cbb  js      loc_180063FBA
0x180063cc1  cmp     qword ptr [rsp+2C0h+var_2A0], r15
0x180063cc6  setnz   al
0x180063cc9  test    al, al
0x180063ccb  jz      loc_180063FDC
0x180063cd1  xor     edx, edx; Val
0x180063cd3  mov     [rsp+2C0h+var_280], r15
0x180063cd8  mov     r8d, 200h; Size
0x180063cde  lea     rcx, [rsp+2C0h+var_278]; void *
0x180063ce3  call    memset_0
0x180063ce8  mov     r9d, 10h
0x180063cee  mov     [rbp+1C0h+var_78], r15
0x180063cf5  lea     rax, [rsp+2C0h+var_278]
0x180063cfa  mov     [rbp+1C0h+var_70], 100h
0x180063d05  lea     rdx, [rbp+1C0h+var_60]
0x180063d0c  mov     [rbp+1C0h+var_68], rax
0x180063d13  mov     rcx, rsi
0x180063d16  lea     r8d, [r9+1]
0x180063d1a  call    _o__ui64tow_s_0
0x180063d1f  test    eax, eax
0x180063d21  jnz     loc_180064001
0x180063d27  lea     rdx, [rbp+1C0h+var_60]; unsigned __int16 *
0x180063d2e  lea     rcx, [rsp+2C0h+var_280]; this
0x180063d33  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180063d38  mov     ebx, eax
0x180063d3a  test    eax, eax
0x180063d3c  js      loc_180064021
0x180063d42  mov     rdx, [rbp+1C0h+var_78]
0x180063d49  lea     rcx, [rsp+2C0h+var_280]; this
0x180063d4e  add     rdx, 2; unsigned __int64
0x180063d52  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x180063d57  mov     ebx, eax
0x180063d59  test    eax, eax
0x180063d5b  js      loc_180063F78
0x180063d61  mov     r10, [rbp+1C0h+var_78]
0x180063d68  mov     r9d, 10h
0x180063d6e  mov     rdx, [rbp+1C0h+var_68]
0x180063d75  mov     rcx, rdi
0x180063d78  lea     r8d, [r9+1]
0x180063d7c  mov     dword ptr [rdx+r10*2], 5Eh ; '^'
0x180063d84  lea     rdx, [rbp+1C0h+var_60]
0x180063d8b  inc     [rbp+1C0h+var_78]
0x180063d92  call    _o__ui64tow_s_0
0x180063d97  test    eax, eax
0x180063d99  jnz     loc_18006402B
0x180063d9f  lea     rdx, [rbp+1C0h+var_60]; unsigned __int16 *
0x180063da6  lea     rcx, [rsp+2C0h+var_280]; this
0x180063dab  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180063db0  mov     ebx, eax
0x180063db2  test    eax, eax
0x180063db4  js      loc_18006404B
0x180063dba  mov     rdx, [rbp+1C0h+var_68]
0x180063dc1  lea     rax, [rsp+2C0h+var_298]
0x180063dc6  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x180063dcb  lea     r9, [rbp+1C0h+var_58]
0x180063dd2  xor     r8d, r8d
0x180063dd5  mov     qword ptr [rbp+1C0h+var_60], rax
0x180063ddc  mov     [rsp+2C0h+var_298], r15
0x180063de1  mov     [rbp+1C0h+var_58], r15
0x180063de8  mov     [rbp+1C0h+var_50], 1
0x180063def  call    cs:__imp_SRCacheContext_OpenSubContext
0x180063df5  mov     ebx, eax
0x180063df7  cmp     [rbp+1C0h+var_50], r15b
0x180063dfe  jz      short loc_180063E1F
0x180063e00  mov     r8, qword ptr [rbp+1C0h+var_60]
0x180063e07  mov     rdx, [rbp+1C0h+var_58]
0x180063e0e  mov     rcx, [r8]
0x180063e11  mov     [r8], rdx
0x180063e14  test    rcx, rcx
0x180063e17  jz      short loc_180063E1F
0x180063e19  call    cs:__imp_SRCacheContext_Close
0x180063e1f  test    ebx, ebx
0x180063e21  js      loc_180064055
0x180063e27  mov     rcx, [rsp+2C0h+var_298]
0x180063e2c  test    rcx, rcx
0x180063e2f  setnz   al
0x180063e32  test    al, al
0x180063e34  jnz     short loc_180063EB2
0x180063e36  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x180063e3b  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x180063e42  call    cs:__imp_SRCacheContext_AddToCache
0x180063e48  mov     ebx, eax
0x180063e4a  test    eax, eax
0x180063e4c  js      loc_18006407A
0x180063e52  mov     rcx, [rsp+2C0h+var_298]
0x180063e57  mov     [rsp+2C0h+var_298], r15
0x180063e5c  test    rcx, rcx
0x180063e5f  jz      short loc_180063E67
0x180063e61  call    cs:__imp_SRCacheContext_Close
0x180063e67  mov     rcx, [rsp+2C0h+var_280]
0x180063e6c  mov     [rsp+2C0h+var_280], r15
0x180063e71  test    rcx, rcx
0x180063e74  jz      short loc_180063E7C
0x180063e76  call    cs:__imp_SRCache_Free
0x180063e7c  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x180063e81  mov     qword ptr [rsp+2C0h+var_2A0], r15
0x180063e86  test    rcx, rcx
0x180063e89  jz      short loc_180063E91
0x180063e8b  call    cs:__imp_SRCacheContext_Close
0x180063e91  xor     eax, eax
0x180063e93  mov     rcx, [rbp+1C0h+var_38]
0x180063e9a  xor     rcx, rsp; StackCookie
0x180063e9d  call    __security_check_cookie
0x180063ea2  add     rsp, 298h
0x180063ea9  pop     r15
0x180063eab  pop     r14
0x180063ead  pop     rdi
0x180063eae  pop     rsi
0x180063eaf  pop     rbx
0x180063eb0  pop     rbp
0x180063eb1  retn
0x180063eb2  lea     rdx, [rsp+2C0h+var_290]
0x180063eb7  mov     [rsp+2C0h+var_290], r15d
0x180063ebc  call    cs:__imp_SRCacheContext_IsEmpty
0x180063ec2  mov     ebx, eax
0x180063ec4  test    eax, eax
0x180063ec6  js      short loc_180063EDA
0x180063ec8  cmp     [rsp+2C0h+var_290], r15d
0x180063ecd  setnz   al
0x180063ed0  xor     al, 1
0x180063ed2  mov     [r14], al
0x180063ed5  jmp     loc_180063E36
0x180063eda  mov     rcx, [rbp+1C8h]; this
0x180063ee1  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180063ee8  mov     r9d, ebx; char *
0x180063eeb  mov     edx, 2B8h; void *
0x180063ef0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063ef5  mov     edx, 0ACh; void *
0x180063efa  mov     rcx, [rbp+1C8h]; this
0x180063f01  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180063f08  mov     r9d, ebx; char *
0x180063f0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063f10  mov     rcx, [rsp+2C0h+var_298]
0x180063f15  mov     [rsp+2C0h+var_298], r15
0x180063f1a  test    rcx, rcx
0x180063f1d  jz      short loc_180063F25
0x180063f1f  call    cs:__imp_SRCacheContext_Close
0x180063f25  mov     rcx, [rsp+2C0h+var_280]
0x180063f2a  mov     [rsp+2C0h+var_280], r15
0x180063f2f  test    rcx, rcx
0x180063f32  jz      short loc_180063F3A
0x180063f34  call    cs:__imp_SRCache_Free
0x180063f3a  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x180063f3f  mov     qword ptr [rsp+2C0h+var_2A0], r15
0x180063f44  test    rcx, rcx
0x180063f47  jz      short loc_180063F4F
0x180063f49  call    cs:__imp_SRCacheContext_Close
0x180063f4f  mov     eax, ebx
0x180063f51  jmp     loc_180063E93
0x180063f56  mov     edx, 99h; void *
0x180063f5b  mov     rcx, [rbp+1C8h]; this
0x180063f62  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180063f69  mov     ebx, 80070057h
0x180063f6e  mov     r9d, ebx; char *
0x180063f71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063f76  jmp     short loc_180063F4F
0x180063f78  mov     rcx, [rbp+1C8h]; this
0x180063f7f  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180063f86  mov     r9d, ebx; char *
0x180063f89  mov     edx, 16Dh; void *
0x180063f8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063f93  mov     edx, 0A3h; void *
0x180063f98  mov     rcx, [rbp+1C8h]; this
0x180063f9f  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180063fa6  mov     r9d, ebx; char *
0x180063fa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063fae  jmp     loc_180063F25
0x180063fb3  mov     edx, 9Ah
0x180063fb8  jmp     short loc_180063F5B
0x180063fba  mov     rcx, [rbp+1C8h]; this
0x180063fc1  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180063fc8  mov     r9d, ebx; char *
0x180063fcb  mov     edx, 18Ch; void *
0x180063fd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063fd5  mov     edx, 9Eh
0x180063fda  jmp     short loc_180063FE6
0x180063fdc  mov     ebx, 80670012h
0x180063fe1  mov     edx, 9Fh; void *
0x180063fe6  mov     rcx, [rbp+1C8h]; this
0x180063fed  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180063ff4  mov     r9d, ebx; char *
0x180063ff7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063ffc  jmp     loc_180063F3A
0x180064001  mov     rcx, [rbp+1C8h]; this
0x180064008  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18006400f  mov     ebx, 8000FFFFh
0x180064014  mov     edx, 166h; void *
0x180064019  mov     r9d, ebx; char *
0x18006401c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064021  mov     edx, 0A2h
0x180064026  jmp     loc_180063F98
0x18006402b  mov     rcx, [rbp+1C8h]; this
0x180064032  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064039  mov     ebx, 8000FFFFh
0x18006403e  mov     edx, 166h; void *
0x180064043  mov     r9d, ebx; char *
0x180064046  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006404b  mov     edx, 0A4h
0x180064050  jmp     loc_180063F98
0x180064055  mov     rcx, [rbp+1C8h]; this
0x18006405c  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064063  mov     r9d, ebx; char *
0x180064066  mov     edx, 1B0h; void *
0x18006406b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064070  mov     edx, 0A8h
0x180064075  jmp     loc_180063EFA
0x18006407a  mov     rcx, [rbp+1C8h]; this
0x180064081  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064088  mov     r9d, ebx; char *
0x18006408b  mov     edx, 1A6h; void *
0x180064090  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064095  mov     edx, 0B0h
0x18006409a  jmp     loc_180063EFA
```
