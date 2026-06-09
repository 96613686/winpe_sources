# SRCacheContext::Create(SRCacheManager &,ushort const *,SRCacheFlags)

- ea: `0x18000c05c`
- end: `0x18000c14b`
- name: `?Create@SRCacheContext@@QEAAJAEAUSRCacheManager@@PEBGW4SRCacheFlags@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(struct Common::RegistryKey *, Common::RegistryKey *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000caa0`

## callees

- `0x18000940c`
- `0x18000bf44`
- `0x18000bf7c`
- `0x18000c05c`
- `0x18000e4c0`
- `0x18000f95c`

## string_xrefs

- `0x18000c08c`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000c0e0`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext::Create(
        struct Common::RegistryKey *a1,
        Common::RegistryKey *a2,
        const unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HKEY *v9; // rbx
  int SubKey; // edi
  unsigned int v11; // r9d
  __int64 v12; // rdx
  struct _SECURITY_ATTRIBUTES *v13; // [rsp+20h] [rbp-38h]
  unsigned int *v14; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  SRCacheContext *v16; // [rsp+68h] [rbp+10h] BYREF

  if ( !*(_QWORD *)a2 )
  {
    v6 = -2147024809;
    v7 = 60;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v6,
      (int)v13);
    return v6;
  }
  wil::make_unique_nothrow<SRCacheContext,>(&v16);
  v9 = (HKEY *)v16;
  if ( !v16 )
  {
    v6 = -2147024882;
    v7 = 63;
    goto LABEL_3;
  }
  SubKey = StateRepository::SRCacheContextCacheSingleton::Get(a3, v16, a1);
  if ( SubKey < 0 )
  {
    v12 = 65;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)(unsigned int)SubKey,
      (int)v13);
    if ( v9 )
      SRCacheContext::`scalar deleting destructor'(v9);
    return (unsigned int)SubKey;
  }
  if ( !*(_QWORD *)a1 )
  {
    SubKey = Common::RegistryKey::CreateSubKey(a2, a3, 0x2011Fu, v11, v13, a1, v14);
    if ( SubKey < 0 )
    {
      v12 = 72;
      goto LABEL_8;
    }
  }
  if ( v9 )
    SRCacheContext::`scalar deleting destructor'(v9);
  return 0;
}

```

## disassembly

```asm
0x18000c05c  mov     [rsp+arg_0], rbx
0x18000c061  mov     [rsp+arg_10], rbp
0x18000c066  push    rsi
0x18000c067  push    rdi
0x18000c068  push    r14
0x18000c06a  sub     rsp, 40h
0x18000c06e  cmp     qword ptr [rdx], 0
0x18000c072  mov     r14, r8
0x18000c075  mov     rbp, rdx
0x18000c078  mov     rsi, rcx
0x18000c07b  jnz     short loc_18000C0A2
0x18000c07d  mov     ebx, 80070057h
0x18000c082  mov     edx, 3Ch ; '<'; void *
0x18000c087  mov     rcx, [rsp+58h]; this
0x18000c08c  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c093  mov     r9d, ebx; char *
0x18000c096  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c09b  mov     eax, ebx
0x18000c09d  jmp     loc_18000C138
0x18000c0a2  lea     rcx, [rsp+58h+arg_8]
0x18000c0a7  call    ??$make_unique_nothrow@USRCacheContext@@$$V@wil@@YA?AV?$unique_ptr@USRCacheContext@@U?$default_delete@USRCacheContext@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<SRCacheContext,>(void)
0x18000c0ac  mov     rbx, [rsp+58h+arg_8]
0x18000c0b1  test    rbx, rbx
0x18000c0b4  jnz     short loc_18000C0C2
0x18000c0b6  mov     ebx, 8007000Eh
0x18000c0bb  mov     edx, 3Fh ; '?'
0x18000c0c0  jmp     short loc_18000C087
0x18000c0c2  mov     r8, rsi; struct Common::RegistryKey *
0x18000c0c5  mov     rdx, rbx; struct SRCacheContext *
0x18000c0c8  mov     rcx, r14; unsigned __int16 *
0x18000c0cb  call    ?Get@SRCacheContextCacheSingleton@StateRepository@@SAJPEBGAEAUSRCacheContext@@AEAVRegistryKey@Common@@@Z; StateRepository::SRCacheContextCacheSingleton::Get(ushort const *,SRCacheContext &,Common::RegistryKey &)
0x18000c0d0  mov     edi, eax
0x18000c0d2  test    eax, eax
0x18000c0d4  jns     short loc_18000C100
0x18000c0d6  mov     edx, 41h ; 'A'; void *
0x18000c0db  mov     rcx, [rsp+58h]; this
0x18000c0e0  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c0e7  mov     r9d, edi; char *
0x18000c0ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c0ef  test    rbx, rbx
0x18000c0f2  jz      short loc_18000C0FC
0x18000c0f4  mov     rcx, rbx; this
0x18000c0f7  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000c0fc  mov     eax, edi
0x18000c0fe  jmp     short loc_18000C138
0x18000c100  cmp     qword ptr [rsi], 0
0x18000c104  jnz     short loc_18000C129
0x18000c106  mov     r8d, 2011Fh; unsigned int
0x18000c10c  mov     [rsp+58h+var_30], rsi; struct Common::AutoHandleHKEY *
0x18000c111  mov     rdx, r14; unsigned __int16 *
0x18000c114  mov     rcx, rbp; this
0x18000c117  call    ?CreateSubKey@RegistryKey@Common@@QEAAJPEBGKKQEAU_SECURITY_ATTRIBUTES@@AEAVAutoHandleHKEY@2@PEAK@Z; Common::RegistryKey::CreateSubKey(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,Common::AutoHandleHKEY &,ulong *)
0x18000c11c  mov     edi, eax
0x18000c11e  test    eax, eax
0x18000c120  jns     short loc_18000C129
0x18000c122  mov     edx, 48h ; 'H'
0x18000c127  jmp     short loc_18000C0DB
0x18000c129  test    rbx, rbx
0x18000c12c  jz      short loc_18000C136
0x18000c12e  mov     rcx, rbx; this
0x18000c131  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000c136  xor     eax, eax
0x18000c138  mov     rbx, [rsp+58h+arg_0]
0x18000c13d  mov     rbp, [rsp+58h+arg_10]
0x18000c142  add     rsp, 40h
0x18000c146  pop     r14
0x18000c148  pop     rdi
0x18000c149  pop     rsi
0x18000c14a  retn
```
