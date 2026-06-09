# StorageAdapterGetCurrentRecord

- ea: `0x14000f9e0`
- end: `0x14000fcef`
- name: `StorageAdapterGetCurrentRecord`
- size: `783`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x140065380`

## callees

- `0x14000a2e4`
- `0x14000a420`
- `0x14000f9e0`
- `0x14001101c`
- `0x14001bd40`
- `0x14001cb90`
- `0x1400584a0`
- `0x1400586ec`
- `0x1400588f4`
- `0x1400594d0`
- `0x1400634e8`
- `0x14007dcf8`

## string_xrefs

- `0x14000fbf1`: `onecore\ds\security\biometrics\service\trustlet\exe\cachestoragehelpers.cpp`
- `0x14000fa27`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14000fa54`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14000fa85`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14000faeb`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14000fb59`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14000fc10`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall StorageAdapterGetCurrentRecord(__int64 a1, __int64 a2)
{
  __int64 v5; // rbx
  void **v6; // r15
  void **v7; // r12
  int Current; // eax
  unsigned int v9; // ebx
  struct CacheBuffer *v10; // r13
  int ProtectedBlock; // eax
  unsigned int v12; // ebx
  struct _LOCK_BOX_RECORD_HEADER *v13; // rbx
  SIZE_T v14; // r14
  int v15; // esi
  __int64 v16; // rdx
  char *v17; // rax
  unsigned __int8 *v18; // [rsp+20h] [rbp-478h] BYREF
  unsigned __int8 *v19; // [rsp+28h] [rbp-470h] BYREF
  struct _LOCK_BOX_RECORD_HEADER *v20; // [rsp+30h] [rbp-468h] BYREF
  union _LARGE_INTEGER v21; // [rsp+38h] [rbp-460h] BYREF
  unsigned __int8 *v22; // [rsp+40h] [rbp-458h]
  _BYTE v23[8]; // [rsp+48h] [rbp-450h] BYREF
  std::_Ref_count_base *v24; // [rsp+50h] [rbp-448h]
  _BYTE v25[1024]; // [rsp+60h] [rbp-438h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+0h]

  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5FE,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80004003LL,
      (int)v18);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x601,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80004003LL,
      (int)v18);
    return 2147500035LL;
  }
  v5 = *(_QWORD *)(a1 + 64);
  if ( !v5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x606,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x8009800FLL,
      (int)v18);
    return 2148106255LL;
  }
  v6 = (void **)(v5 + 88);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(v5 + 88);
  v7 = (void **)(v5 + 96);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(v5 + 96);
  v20 = 0;
  v21.QuadPart = 0;
  Current = ResGetCurrent((struct _RESULT_SET *)(v5 + 48), &v20, &v21);
  v9 = Current;
  if ( Current < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x611,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)(unsigned int)Current,
      (int)v18);
    return v9;
  }
  v10 = (struct CacheBuffer *)(*(_QWORD *)WinBioFramework::PipelineToPipelineObject(v23, a1) + 1296LL);
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  memset_0(v25, 0, sizeof(v25));
  ProtectedBlock = CacheGetProtectedBlock(v10, (struct _LOCK_BOX_PROTECTED_BLOCK *)v25);
  v12 = ProtectedBlock;
  if ( ProtectedBlock < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x619,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)(unsigned int)ProtectedBlock,
      (int)v18);
    return v12;
  }
  v13 = v20;
  v14 = *((_QWORD *)v20 + 5);
  wil::make_unique_hlocal_secure<unsigned char [0]>(&v19, v14);
  wil::make_unique_hlocal_secure<unsigned char [0]>(&v18, *((_QWORD *)v13 + 7));
  v20 = (struct _LOCK_BOX_RECORD_HEADER *)*((_QWORD *)v13 + 7);
  v22 = v18;
  v15 = CacheBuffer::Read(v10, v21.LowPart, v19, v14);
  if ( v15 < 0 )
  {
    v16 = 243;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\cachestoragehelpers.cpp",
      (const char *)(unsigned int)v15,
      (int)v18);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x625,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)(unsigned int)v15,
      (int)v18);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v18);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v19);
    return (unsigned int)v15;
  }
  v15 = CacheBuffer::Read(v10, v14 + v21.LowPart, v22, (unsigned int)v20);
  if ( v15 < 0 )
  {
    v16 = 249;
    goto LABEL_17;
  }
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::operator=(v6, (void **)&v19);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::operator=(v7, (void **)&v18);
  *(_QWORD *)a2 = (char *)v13 + 72;
  *(_BYTE *)(a2 + 8) = *((_BYTE *)v13 + 148);
  *(_QWORD *)(a2 + 24) = *((_QWORD *)v13 + 8);
  if ( *((_QWORD *)v13 + 8) )
    v17 = (char *)v13 + 152;
  else
    v17 = 0;
  *(_QWORD *)(a2 + 16) = v17;
  *(_QWORD *)(a2 + 56) = *((_QWORD *)v13 + 7);
  *(_QWORD *)(a2 + 48) = *v7;
  *(_QWORD *)(a2 + 40) = *((_QWORD *)v13 + 5);
  *(_QWORD *)(a2 + 32) = *v6;
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v18);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v19);
  return 0;
}

```

## disassembly

```asm
0x14000f9e0  mov     [rsp+arg_10], rbx
0x14000f9e5  mov     [rsp+arg_18], rsi
0x14000f9ea  push    rdi
0x14000f9eb  push    r12
0x14000f9ed  push    r13
0x14000f9ef  push    r14
0x14000f9f1  push    r15
0x14000f9f3  sub     rsp, 470h
0x14000f9fa  mov     rax, cs:__security_cookie
0x14000fa01  xor     rax, rsp
0x14000fa04  mov     [rsp+498h+var_38], rax
0x14000fa0c  mov     rdi, rdx
0x14000fa0f  mov     rsi, rcx
0x14000fa12  test    rcx, rcx
0x14000fa15  jnz     short loc_14000FA3F
0x14000fa17  mov     rcx, [rsp+498h]; this
0x14000fa1f  mov     ebx, 80004003h
0x14000fa24  mov     r9d, ebx; char *
0x14000fa27  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fa2e  mov     edx, 5FEh; void *
0x14000fa33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fa38  mov     eax, ebx
0x14000fa3a  jmp     loc_14000FCC1
0x14000fa3f  test    rdi, rdi
0x14000fa42  jnz     short loc_14000FA6C
0x14000fa44  mov     rcx, [rsp+498h]; this
0x14000fa4c  mov     ebx, 80004003h
0x14000fa51  mov     r9d, ebx; char *
0x14000fa54  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fa5b  mov     edx, 601h; void *
0x14000fa60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fa65  mov     eax, ebx
0x14000fa67  jmp     loc_14000FCC1
0x14000fa6c  mov     rbx, [rcx+40h]
0x14000fa70  test    rbx, rbx
0x14000fa73  jnz     short loc_14000FA9D
0x14000fa75  mov     rcx, [rsp+498h]; this
0x14000fa7d  mov     ebx, 8009800Fh
0x14000fa82  mov     r9d, ebx; char *
0x14000fa85  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fa8c  mov     edx, 606h; void *
0x14000fa91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fa96  mov     eax, ebx
0x14000fa98  jmp     loc_14000FCC1
0x14000fa9d  lea     r15, [rbx+58h]
0x14000faa1  mov     rcx, r15
0x14000faa4  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x14000faa9  lea     r12, [rbx+60h]
0x14000faad  mov     rcx, r12
0x14000fab0  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x14000fab5  mov     [rsp+498h+var_468], 0
0x14000fabe  mov     qword ptr [rsp+498h+var_460], 0
0x14000fac7  lea     rcx, [rbx+30h]; struct _RESULT_SET *
0x14000facb  lea     r8, [rsp+498h+var_460]; union _LARGE_INTEGER *
0x14000fad0  lea     rdx, [rsp+498h+var_468]; struct _LOCK_BOX_RECORD_HEADER **
0x14000fad5  call    ?ResGetCurrent@@YAJPEAU_RESULT_SET@@PEAPEAU_LOCK_BOX_RECORD_HEADER@@PEAT_LARGE_INTEGER@@@Z; ResGetCurrent(_RESULT_SET *,_LOCK_BOX_RECORD_HEADER * *,_LARGE_INTEGER *)
0x14000fada  mov     ebx, eax
0x14000fadc  test    eax, eax
0x14000fade  jns     short loc_14000FB03
0x14000fae0  mov     rcx, [rsp+498h]; this
0x14000fae8  mov     r9d, eax; char *
0x14000faeb  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000faf2  mov     edx, 611h; void *
0x14000faf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fafc  mov     eax, ebx
0x14000fafe  jmp     loc_14000FCC1
0x14000fb03  mov     rdx, rsi
0x14000fb06  lea     rcx, [rsp+498h+var_450]
0x14000fb0b  call    WinBioFramework__PipelineToPipelineObject
0x14000fb10  mov     r13, [rax]
0x14000fb13  add     r13, 510h
0x14000fb1a  mov     rcx, [rsp+498h+var_448]; this
0x14000fb1f  test    rcx, rcx
0x14000fb22  jz      short loc_14000FB29
0x14000fb24  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000fb29  xor     edx, edx; Val
0x14000fb2b  mov     r8d, 400h; Size
0x14000fb31  lea     rcx, [rsp+498h+var_438]; void *
0x14000fb36  call    memset_0
0x14000fb3b  lea     rdx, [rsp+498h+var_438]; struct _LOCK_BOX_PROTECTED_BLOCK *
0x14000fb40  mov     rcx, r13; struct CacheBuffer *
0x14000fb43  call    ?CacheGetProtectedBlock@@YAJPEAVCacheBuffer@@PEAU_LOCK_BOX_PROTECTED_BLOCK@@@Z; CacheGetProtectedBlock(CacheBuffer *,_LOCK_BOX_PROTECTED_BLOCK *)
0x14000fb48  mov     ebx, eax
0x14000fb4a  test    eax, eax
0x14000fb4c  jns     short loc_14000FB71
0x14000fb4e  mov     rcx, [rsp+498h]; this
0x14000fb56  mov     r9d, eax; char *
0x14000fb59  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fb60  mov     edx, 619h; void *
0x14000fb65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fb6a  mov     eax, ebx
0x14000fb6c  jmp     loc_14000FCC1
0x14000fb71  mov     rbx, [rsp+498h+var_468]
0x14000fb76  mov     r14, [rbx+28h]
0x14000fb7a  mov     rdx, r14
0x14000fb7d  lea     rcx, [rsp+498h+var_470]
0x14000fb82  call    ??$make_unique_hlocal_secure@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure<uchar [0]>(unsigned __int64)
0x14000fb87  nop
0x14000fb88  mov     rdx, [rbx+38h]
0x14000fb8c  lea     rcx, [rsp+498h+var_478]
0x14000fb91  call    ??$make_unique_hlocal_secure@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure<uchar [0]>(unsigned __int64)
0x14000fb96  mov     rax, [rbx+38h]
0x14000fb9a  mov     [rsp+498h+var_468], rax
0x14000fb9f  mov     rax, [rsp+498h+var_478]
0x14000fba4  mov     [rsp+498h+var_458], rax
0x14000fba9  mov     r9d, r14d; unsigned int
0x14000fbac  mov     r8, [rsp+498h+var_470]; unsigned __int8 *
0x14000fbb1  mov     edx, dword ptr [rsp+498h+var_460]; unsigned int
0x14000fbb5  mov     rcx, r13; this
0x14000fbb8  call    ?Read@CacheBuffer@@QEAAJKPEAEK@Z; CacheBuffer::Read(ulong,uchar *,ulong)
0x14000fbbd  mov     esi, eax
0x14000fbbf  test    eax, eax
0x14000fbc1  jns     short loc_14000FBCA
0x14000fbc3  mov     edx, 0F3h
0x14000fbc8  jmp     short loc_14000FBEE
0x14000fbca  mov     r9d, dword ptr [rsp+498h+var_468]; unsigned int
0x14000fbcf  mov     edx, dword ptr [rsp+498h+var_460]
0x14000fbd3  add     edx, r14d; unsigned int
0x14000fbd6  mov     r8, [rsp+498h+var_458]; unsigned __int8 *
0x14000fbdb  mov     rcx, r13; this
0x14000fbde  call    ?Read@CacheBuffer@@QEAAJKPEAEK@Z; CacheBuffer::Read(ulong,uchar *,ulong)
0x14000fbe3  mov     esi, eax
0x14000fbe5  test    eax, eax
0x14000fbe7  jns     short loc_14000FC3D
0x14000fbe9  mov     edx, 0F9h; void *
0x14000fbee  mov     r9d, esi; char *
0x14000fbf1  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fbf8  mov     rcx, [rsp+498h]; this
0x14000fc00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fc05  mov     rcx, [rsp+498h]; this
0x14000fc0d  mov     r9d, esi; char *
0x14000fc10  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fc17  mov     edx, 625h; void *
0x14000fc1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fc21  lea     rcx, [rsp+498h+var_478]
0x14000fc26  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x14000fc2b  nop
0x14000fc2c  lea     rcx, [rsp+498h+var_470]
0x14000fc31  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x14000fc36  mov     eax, esi
0x14000fc38  jmp     loc_14000FCC1
0x14000fc3d  lea     rdx, [rsp+498h+var_470]
0x14000fc42  mov     rcx, r15
0x14000fc45  call    ??4?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::operator=(wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter> &&)
0x14000fc4a  lea     rdx, [rsp+498h+var_478]
0x14000fc4f  mov     rcx, r12
0x14000fc52  call    ??4?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::operator=(wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter> &&)
0x14000fc57  lea     rax, [rbx+48h]
0x14000fc5b  mov     [rdi], rax
0x14000fc5e  mov     al, [rbx+94h]
0x14000fc64  mov     [rdi+8], al
0x14000fc67  mov     rax, [rbx+40h]
0x14000fc6b  mov     [rdi+18h], rax
0x14000fc6f  cmp     qword ptr [rbx+40h], 0
0x14000fc74  jbe     short loc_14000FC7F
0x14000fc76  lea     rax, [rbx+98h]
0x14000fc7d  jmp     short loc_14000FC81
0x14000fc7f  xor     eax, eax
0x14000fc81  mov     [rdi+10h], rax
0x14000fc85  mov     rax, [rbx+38h]
0x14000fc89  mov     [rdi+38h], rax
0x14000fc8d  mov     rax, [r12]
0x14000fc91  mov     [rdi+30h], rax
0x14000fc95  mov     rax, [rbx+28h]
0x14000fc99  mov     [rdi+28h], rax
0x14000fc9d  mov     rax, [r15]
0x14000fca0  mov     [rdi+20h], rax
0x14000fca4  lea     rcx, [rsp+498h+var_478]
0x14000fca9  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x14000fcae  nop
0x14000fcaf  lea     rcx, [rsp+498h+var_470]
0x14000fcb4  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x14000fcb9  xor     eax, eax
0x14000fcbb  jmp     short loc_14000FCC1
0x14000fcbd  mov     eax, dword ptr [rsp+498h+var_478]
0x14000fcc1  mov     rcx, [rsp+498h+var_38]
0x14000fcc9  xor     rcx, rsp; StackCookie
0x14000fccc  call    __security_check_cookie
0x14000fcd1  lea     r11, [rsp+498h+var_28]
0x14000fcd9  mov     rbx, [r11+40h]
0x14000fcdd  mov     rsi, [r11+48h]
0x14000fce1  mov     rsp, r11
0x14000fce4  pop     r15
0x14000fce6  pop     r14
0x14000fce8  pop     r13
0x14000fcea  pop     r12
0x14000fcec  pop     rdi
0x14000fced  retn
```
