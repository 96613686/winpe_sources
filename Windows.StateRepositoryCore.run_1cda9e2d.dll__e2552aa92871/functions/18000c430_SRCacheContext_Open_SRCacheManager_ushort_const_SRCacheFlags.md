# SRCacheContext::Open(SRCacheManager &,ushort const *,SRCacheFlags)

- ea: `0x18000c430`
- end: `0x18000c524`
- name: `?Open@SRCacheContext@@QEAAJAEAUSRCacheManager@@PEBGW4SRCacheFlags@@@Z`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d090`

## callees

- `0x18000940c`
- `0x18000bf44`
- `0x18000bf7c`
- `0x18000c430`
- `0x18000e4c0`
- `0x18000fda8`

## string_xrefs

- `0x18000c45e`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000c4b2`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext::Open(
        struct Common::RegistryKey *a1,
        Common::RegistryKey *a2,
        const unsigned __int16 *a3,
        char a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  SRCacheContext *v11; // rbx
  unsigned int v12; // edx
  int v13; // edi
  __int64 v14; // rdx
  unsigned int v15; // edx
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  SRCacheContext *v18; // [rsp+68h] [rbp+10h] BYREF

  if ( !*(_QWORD *)a2 )
  {
    v8 = -2147024809;
    v9 = 12;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v8,
      v16);
    return v8;
  }
  wil::make_unique_nothrow<SRCacheContext,>(&v18);
  v11 = v18;
  if ( !v18 )
  {
    v8 = -2147024882;
    v9 = 15;
    goto LABEL_3;
  }
  v13 = StateRepository::SRCacheContextCacheSingleton::Get(a3, v18, a1);
  if ( v13 < 0 )
  {
    v14 = 17;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)(unsigned int)v13,
      v16);
    if ( v11 )
      SRCacheContext::`scalar deleting destructor'(v11, v15);
    return (unsigned int)v13;
  }
  if ( !*(_QWORD *)a1 )
  {
    v13 = Common::RegistryKey::OpenSubKeyIfExists(a2, a3, (a4 & 1) != 0 ? 131359 : 131353, a1);
    if ( v13 < 0 )
    {
      v14 = 24;
      goto LABEL_8;
    }
  }
  if ( v11 )
    SRCacheContext::`scalar deleting destructor'(v11, v12);
  return 0;
}

```

## disassembly

```asm
0x18000c430  push    rbx
0x18000c432  push    rbp
0x18000c433  push    rsi
0x18000c434  push    rdi
0x18000c435  push    r14
0x18000c437  push    r15
0x18000c439  sub     rsp, 28h
0x18000c43d  cmp     qword ptr [rdx], 0
0x18000c441  mov     ebp, r9d
0x18000c444  mov     r15, r8
0x18000c447  mov     r14, rdx
0x18000c44a  mov     rsi, rcx
0x18000c44d  jnz     short loc_18000C474
0x18000c44f  mov     ebx, 80070057h
0x18000c454  mov     edx, 0Ch; void *
0x18000c459  mov     rcx, [rsp+58h]; this
0x18000c45e  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c465  mov     r9d, ebx; char *
0x18000c468  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c46d  mov     eax, ebx
0x18000c46f  jmp     loc_18000C517
0x18000c474  lea     rcx, [rsp+58h+arg_8]
0x18000c479  call    ??$make_unique_nothrow@USRCacheContext@@$$V@wil@@YA?AV?$unique_ptr@USRCacheContext@@U?$default_delete@USRCacheContext@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<SRCacheContext,>(void)
0x18000c47e  mov     rbx, [rsp+58h+arg_8]
0x18000c483  test    rbx, rbx
0x18000c486  jnz     short loc_18000C494
0x18000c488  mov     ebx, 8007000Eh
0x18000c48d  mov     edx, 0Fh
0x18000c492  jmp     short loc_18000C459
0x18000c494  mov     r8, rsi; struct Common::RegistryKey *
0x18000c497  mov     rdx, rbx; struct SRCacheContext *
0x18000c49a  mov     rcx, r15; unsigned __int16 *
0x18000c49d  call    ?Get@SRCacheContextCacheSingleton@StateRepository@@SAJPEBGAEAUSRCacheContext@@AEAVRegistryKey@Common@@@Z; StateRepository::SRCacheContextCacheSingleton::Get(ushort const *,SRCacheContext &,Common::RegistryKey &)
0x18000c4a2  mov     edi, eax
0x18000c4a4  test    eax, eax
0x18000c4a6  jns     short loc_18000C4D2
0x18000c4a8  mov     edx, 11h; void *
0x18000c4ad  mov     rcx, [rsp+58h]; this
0x18000c4b2  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c4b9  mov     r9d, edi; char *
0x18000c4bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c4c1  test    rbx, rbx
0x18000c4c4  jz      short loc_18000C4CE
0x18000c4c6  mov     rcx, rbx; this
0x18000c4c9  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000c4ce  mov     eax, edi
0x18000c4d0  jmp     short loc_18000C517
0x18000c4d2  cmp     qword ptr [rsi], 0
0x18000c4d6  jnz     short loc_18000C508
0x18000c4d8  and     bpl, 1
0x18000c4dc  mov     r9, rsi; struct Common::AutoHandleHKEY *
0x18000c4df  neg     bpl
0x18000c4e2  mov     rdx, r15; unsigned __int16 *
0x18000c4e5  mov     rcx, r14; this
0x18000c4e8  sbb     r8d, r8d
0x18000c4eb  and     r8d, 6
0x18000c4ef  add     r8d, 20119h; unsigned int
0x18000c4f6  call    ?OpenSubKeyIfExists@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKeyIfExists(ushort const *,ulong,Common::AutoHandleHKEY &)
0x18000c4fb  mov     edi, eax
0x18000c4fd  test    eax, eax
0x18000c4ff  jns     short loc_18000C508
0x18000c501  mov     edx, 18h
0x18000c506  jmp     short loc_18000C4AD
0x18000c508  test    rbx, rbx
0x18000c50b  jz      short loc_18000C515
0x18000c50d  mov     rcx, rbx; this
0x18000c510  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000c515  xor     eax, eax
0x18000c517  add     rsp, 28h
0x18000c51b  pop     r15
0x18000c51d  pop     r14
0x18000c51f  pop     rdi
0x18000c520  pop     rsi
0x18000c521  pop     rbp
0x18000c522  pop     rbx
0x18000c523  retn
```
