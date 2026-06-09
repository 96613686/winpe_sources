# SRCacheManager::Open(SRCacheFlags)

- ea: `0x18000d560`
- end: `0x18000d6c5`
- name: `?Open@SRCacheManager@@QEAAJW4SRCacheFlags@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(__int64, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d8b0`

## callees

- `0x18000940c`
- `0x18000a8d4`
- `0x18000be00`
- `0x18000d4d0`
- `0x18000d560`
- `0x18000e55c`
- `0x18000f95c`
- `0x18000fcf4`
- `0x18000fda8`

## string_xrefs

- `0x18000d5a7`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`
- `0x18000d602`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`
- `0x18000d671`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheManager::Open(__int64 a1, HKEY a2, const unsigned __int16 *a3)
{
  char v3; // r14
  char v4; // bp
  REGSAM v6; // esi
  LSTATUS SubKey; // edi
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 result; // rax
  HKEY *v11; // rdi
  int UInt32ValueIf; // esi
  __int64 v13; // rdx
  int v14; // eax
  struct _SECURITY_ATTRIBUTES *v15; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  bool v17; // [rsp+68h] [rbp+10h] BYREF

  v3 = (char)a2;
  v4 = (unsigned __int8)a2 & 1;
  v6 = ((unsigned __int8)a2 & 1) != 0 ? 131359 : 131353;
  SubKey = Common::RegistryKey::Open((PHKEY)a1, a2, a3, v6);
  if ( SubKey < 0 )
  {
    v9 = 14;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
      (const char *)(unsigned int)SubKey,
      (int)v15);
    return (unsigned int)SubKey;
  }
  v11 = (HKEY *)(a1 + 8);
  if ( v4 )
  {
    SubKey = Common::RegistryKey::CreateSubKey((HKEY *)a1, L"Metadata", v6, v8, v15, (HKEY *)(a1 + 8));
    if ( SubKey < 0 )
    {
      v9 = 17;
      goto LABEL_3;
    }
    goto LABEL_15;
  }
  UInt32ValueIf = Common::RegistryKey::OpenSubKeyIfExists(
                    (Common::RegistryKey *)a1,
                    L"Metadata",
                    v6,
                    (struct Common::AutoHandleHKEY *)(a1 + 8));
  if ( UInt32ValueIf < 0 )
  {
    v13 = 33;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
      (const char *)(unsigned int)UInt32ValueIf,
      (int)v15);
    return (unsigned int)UInt32ValueIf;
  }
  if ( (((unsigned __int64)*v11 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
LABEL_21:
    Common::AutoHandleCloseHKEY<HKEY__ *>(*(HKEY *)a1);
    result = 2154233877LL;
    *(_QWORD *)a1 = 0;
    return result;
  }
  v17 = 0;
  UInt32ValueIf = Common::RegistryKey::GetUInt32ValueIfExists<unsigned int>(
                    (Common::RegistryKey *)(a1 + 8),
                    L"Revision",
                    (unsigned int *)(a1 + 16),
                    &v17);
  if ( UInt32ValueIf < 0 )
  {
    v13 = 42;
    goto LABEL_9;
  }
  if ( !v17 || !*(_DWORD *)(a1 + 16) )
  {
    Common::AutoHandleCloseHKEY<HKEY__ *>(*v11);
    *v11 = 0;
    goto LABEL_21;
  }
LABEL_15:
  if ( (v3 & 2) == 0 )
  {
    v14 = StateRepository::SRCacheContextCacheSingleton::Initialize();
    if ( v14 >= 0 )
      *(_BYTE *)(a1 + 20) = 1;
    else
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x37,
        (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
        (const char *)(unsigned int)v14);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d560  mov     [rsp+arg_0], rbx
0x18000d565  mov     [rsp+arg_10], rbp
0x18000d56a  push    rsi
0x18000d56b  push    rdi
0x18000d56c  push    r14
0x18000d56e  sub     rsp, 40h
0x18000d572  mov     bpl, dl
0x18000d575  mov     r14d, edx
0x18000d578  and     bpl, 1
0x18000d57c  mov     rbx, rcx
0x18000d57f  mov     al, bpl
0x18000d582  neg     al
0x18000d584  sbb     esi, esi
0x18000d586  and     esi, 6
0x18000d589  add     esi, 20119h
0x18000d58f  mov     r9d, esi; unsigned int
0x18000d592  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18000d597  mov     edi, eax
0x18000d599  test    eax, eax
0x18000d59b  jns     short loc_18000D5BD
0x18000d59d  mov     edx, 0Eh; void *
0x18000d5a2  mov     rcx, [rsp+58h]; this
0x18000d5a7  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000d5ae  mov     r9d, edi; char *
0x18000d5b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d5b6  mov     eax, edi
0x18000d5b8  jmp     loc_18000D6B2
0x18000d5bd  lea     rdi, [rbx+8]
0x18000d5c1  mov     r8d, esi; unsigned int
0x18000d5c4  lea     rdx, ?Metadata@Constants@Cache@StateRepository@@3QBGB; "Metadata"
0x18000d5cb  mov     rcx, rbx; this
0x18000d5ce  test    bpl, bpl
0x18000d5d1  jz      short loc_18000D5EA
0x18000d5d3  mov     [rsp+58h+var_30], rdi; struct Common::AutoHandleHKEY *
0x18000d5d8  call    ?CreateSubKey@RegistryKey@Common@@QEAAJPEBGKKQEAU_SECURITY_ATTRIBUTES@@AEAVAutoHandleHKEY@2@PEAK@Z; Common::RegistryKey::CreateSubKey(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,Common::AutoHandleHKEY &,ulong *)
0x18000d5dd  mov     edi, eax
0x18000d5df  test    eax, eax
0x18000d5e1  jns     short loc_18000D65D
0x18000d5e3  mov     edx, 11h
0x18000d5e8  jmp     short loc_18000D5A2
0x18000d5ea  mov     r9, rdi; struct Common::AutoHandleHKEY *
0x18000d5ed  call    ?OpenSubKeyIfExists@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKeyIfExists(ushort const *,ulong,Common::AutoHandleHKEY &)
0x18000d5f2  mov     esi, eax
0x18000d5f4  test    eax, eax
0x18000d5f6  jns     short loc_18000D618
0x18000d5f8  mov     edx, 21h ; '!'; void *
0x18000d5fd  mov     rcx, [rsp+58h]; this
0x18000d602  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000d609  mov     r9d, esi; char *
0x18000d60c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d611  mov     eax, esi
0x18000d613  jmp     loc_18000D6B2
0x18000d618  mov     rax, [rdi]
0x18000d61b  inc     rax
0x18000d61e  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000d624  jz      short loc_18000D69E
0x18000d626  lea     r9, [rsp+58h+arg_8]
0x18000d62b  mov     [rsp+58h+arg_8], 0
0x18000d630  lea     r8, [rbx+10h]
0x18000d634  mov     rcx, rdi
0x18000d637  lea     rdx, ?Revision@Constants@Cache@StateRepository@@3QBGB; "Revision"
0x18000d63e  call    ??$GetUInt32ValueIfExists@I@RegistryKey@Common@@QEAAJPEBGPEAIPEA_N@Z; Common::RegistryKey::GetUInt32ValueIfExists<uint>(ushort const *,uint *,bool *)
0x18000d643  mov     esi, eax
0x18000d645  test    eax, eax
0x18000d647  jns     short loc_18000D650
0x18000d649  mov     edx, 2Ah ; '*'
0x18000d64e  jmp     short loc_18000D5FD
0x18000d650  cmp     [rsp+58h+arg_8], 0
0x18000d655  jz      short loc_18000D68F
0x18000d657  cmp     dword ptr [rbx+10h], 0
0x18000d65b  jz      short loc_18000D68F
0x18000d65d  test    r14b, 2
0x18000d661  jnz     short loc_18000D68B
0x18000d663  call    ?Initialize@SRCacheContextCacheSingleton@StateRepository@@SAJXZ; StateRepository::SRCacheContextCacheSingleton::Initialize(void)
0x18000d668  test    eax, eax
0x18000d66a  jns     short loc_18000D687
0x18000d66c  mov     rcx, [rsp+58h]; this
0x18000d671  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000d678  mov     r9d, eax; char *
0x18000d67b  mov     edx, 37h ; '7'; void *
0x18000d680  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d685  jmp     short loc_18000D68B
0x18000d687  mov     byte ptr [rbx+14h], 1
0x18000d68b  xor     eax, eax
0x18000d68d  jmp     short loc_18000D6B2
0x18000d68f  mov     rcx, [rdi]
0x18000d692  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000d697  mov     qword ptr [rdi], 0
0x18000d69e  mov     rcx, [rbx]
0x18000d6a1  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000d6a6  mov     eax, 80670015h
0x18000d6ab  mov     qword ptr [rbx], 0
0x18000d6b2  mov     rbx, [rsp+58h+arg_0]
0x18000d6b7  mov     rbp, [rsp+58h+arg_10]
0x18000d6bc  add     rsp, 40h
0x18000d6c0  pop     r14
0x18000d6c2  pop     rdi
0x18000d6c3  pop     rsi
0x18000d6c4  retn
```
