# Windows::Internal::Security::Authentication::TokenBroker::PluginManager::ResolveMRTResourceString(Windows::Internal::String const &,Windows::Internal::String &)

- ea: `0x18009af30`
- end: `0x18009b0e8`
- name: `?ResolveMRTResourceString@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SAJAEBVString@56@AEAV756@@Z`
- size: `440`
- prototype: `__int64 __fastcall(HSTRING *, struct Windows::Internal::String *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800845d0`

## callees

- `0x18000bd40`
- `0x18003df30`
- `0x180040cc0`
- `0x18005fb0c`
- `0x18009a490`
- `0x18009af30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b0d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b0d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18009b03e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18009b03e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009afce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009afce`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueIsResourceReference` at `0x18009af80`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueIsResourceReference` at `0x18009af80`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueGetString` at `0x18009b006`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueGetString` at `0x18009b06e`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueGetString` at `0x18009b006`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueGetString` at `0x18009b06e`

## string_xrefs

- `0x18009af61`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`
- `0x18009b0c3`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::PluginManager::ResolveMRTResourceString(
        HSTRING *a1,
        struct Windows::Internal::String *this)
{
  int Lpcwstr; // eax
  unsigned int v5; // ebx
  void *v7; // rbx
  int String; // edi
  LPVOID v9; // rax
  int v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  int v14; // [rsp+20h] [rbp-20h]
  SIZE_T cb[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned __int16 *v17; // [rsp+78h] [rbp+38h] BYREF

  v17 = 0;
  Lpcwstr = Windows::Internal::String::GetLpcwstr((Windows::Internal::String *)a1, (const unsigned __int16 **)&v17);
  v5 = Lpcwstr;
  if ( Lpcwstr < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x192,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
      (const char *)(unsigned int)Lpcwstr,
      v14);
    return v5;
  }
  if ( (unsigned int)ResourceManagerQueueIsResourceReference(v17) == -2147009776 )
  {
    Windows::Internal::String::Initialize(this, a1);
    return 0;
  }
  v7 = 0;
  cb[0] = 0;
  if ( (int)ATL::AtlMultiply<unsigned __int64>(cb, 260) < 0
    || cb[0] > 0x7FFFFFFF
    || (cb[0] = (SIZE_T)CoTaskMemAlloc(LODWORD(cb[0])), (v7 = (void *)cb[0]) == 0) )
  {
    v12 = 415;
    goto LABEL_20;
  }
  v14 = 260;
  String = ResourceManagerQueueGetString(v17, 0, 0, cb[0]);
  if ( String != -2147024774 )
  {
    if ( String >= 0 )
      goto LABEL_17;
    v12 = 428;
LABEL_21:
    v11 = (unsigned int)String;
    goto LABEL_22;
  }
  cb[0] = 0;
  if ( (int)ATL::AtlMultiply<unsigned __int64>(cb, 0) < 0
    || cb[0] > 0x7FFFFFFF
    || (v9 = CoTaskMemRealloc(v7, LODWORD(cb[0]))) == 0 )
  {
    v12 = 421;
LABEL_20:
    String = -2147024882;
    goto LABEL_21;
  }
  v7 = v9;
  cb[0] = (SIZE_T)v9;
  v14 = 0;
  v10 = ResourceManagerQueueGetString(v17, 0, 0, v9);
  String = v10;
  if ( v10 < 0 )
  {
    v11 = (unsigned int)v10;
    v12 = 424;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
      (const char *)v11,
      v14);
    goto LABEL_23;
  }
LABEL_17:
  v13 = Windows::Internal::String::Initialize<unsigned short *>(this, cb);
  String = v13;
  if ( v13 < 0 )
  {
    v11 = (unsigned int)v13;
    v12 = 431;
    goto LABEL_22;
  }
LABEL_23:
  CoTaskMemFree(v7);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18009af30  mov     [rsp-18h+arg_0], rbx
0x18009af35  push    rbp
0x18009af36  push    rdi
0x18009af37  push    r14
0x18009af39  mov     rbp, rsp
0x18009af3c  sub     rsp, 40h
0x18009af40  mov     r14, rdx
0x18009af43  mov     [rbp+arg_18], 0
0x18009af4b  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x18009af4f  mov     rdi, rcx
0x18009af52  call    ?GetLpcwstr@String@Internal@Windows@@QEBAJPEAPEBG@Z; Windows::Internal::String::GetLpcwstr(ushort const * *)
0x18009af57  mov     ebx, eax
0x18009af59  test    eax, eax
0x18009af5b  jns     short loc_18009AF7C
0x18009af5d  mov     rcx, [rbp+18h]; this
0x18009af61  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\tokenbroker\\plu"...
0x18009af68  mov     r9d, eax; char *
0x18009af6b  mov     edx, 192h; void *
0x18009af70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009af75  mov     eax, ebx
0x18009af77  jmp     loc_18009B0DA
0x18009af7c  mov     rcx, [rbp+arg_18]
0x18009af80  call    cs:__imp_ResourceManagerQueueIsResourceReference
0x18009af86  cmp     eax, 80073B10h
0x18009af8b  jnz     short loc_18009AF9F
0x18009af8d  mov     rdx, rdi; HSTRING *
0x18009af90  mov     rcx, r14; this
0x18009af93  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18009af98  xor     eax, eax
0x18009af9a  jmp     loc_18009B0DA
0x18009af9f  mov     edi, 104h
0x18009afa4  lea     rcx, [rbp+cb]
0x18009afa8  xor     ebx, ebx
0x18009afaa  mov     edx, edi
0x18009afac  mov     [rbp+cb], rbx
0x18009afb0  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x18009afb5  test    eax, eax
0x18009afb7  js      loc_18009B0B2
0x18009afbd  cmp     [rbp+cb], 7FFFFFFFh
0x18009afc5  ja      loc_18009B0B2
0x18009afcb  mov     ecx, dword ptr [rbp+cb]; cb
0x18009afce  call    cs:__imp_CoTaskMemAlloc
0x18009afd4  mov     [rbp+cb], rax
0x18009afd8  mov     rbx, rax
0x18009afdb  test    rax, rax
0x18009afde  jz      loc_18009B0B2
0x18009afe4  mov     rcx, [rbp+arg_18]
0x18009afe8  lea     rax, [rbp+arg_10]
0x18009afec  mov     [rsp+40h+var_18], rax
0x18009aff1  mov     r9, rbx
0x18009aff4  xor     r8d, r8d
0x18009aff7  mov     [rsp+40h+var_20], rdi
0x18009affc  xor     edx, edx
0x18009affe  mov     [rbp+arg_10], 0
0x18009b006  call    cs:__imp_ResourceManagerQueueGetString
0x18009b00c  mov     edi, eax
0x18009b00e  cmp     eax, 8007007Ah
0x18009b013  jnz     short loc_18009B08B
0x18009b015  mov     rdx, [rbp+arg_10]
0x18009b019  lea     rcx, [rbp+cb]
0x18009b01d  mov     [rbp+cb], 0
0x18009b025  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x18009b02a  test    eax, eax
0x18009b02c  js      short loc_18009B084
0x18009b02e  cmp     [rbp+cb], 7FFFFFFFh
0x18009b036  ja      short loc_18009B084
0x18009b038  mov     edx, dword ptr [rbp+cb]; cb
0x18009b03b  mov     rcx, rbx; pv
0x18009b03e  call    cs:__imp_CoTaskMemRealloc
0x18009b044  test    rax, rax
0x18009b047  jz      short loc_18009B084
0x18009b049  mov     rbx, rax
0x18009b04c  mov     [rbp+cb], rax
0x18009b050  mov     rax, [rbp+arg_10]
0x18009b054  lea     rcx, [rbp+arg_10]
0x18009b058  mov     [rsp+40h+var_18], rcx
0x18009b05d  mov     r9, rbx
0x18009b060  mov     rcx, [rbp+arg_18]
0x18009b064  xor     r8d, r8d
0x18009b067  xor     edx, edx
0x18009b069  mov     [rsp+40h+var_20], rax
0x18009b06e  call    cs:__imp_ResourceManagerQueueGetString
0x18009b074  mov     edi, eax
0x18009b076  test    eax, eax
0x18009b078  jns     short loc_18009B096
0x18009b07a  mov     r9d, eax
0x18009b07d  mov     edx, 1A8h
0x18009b082  jmp     short loc_18009B0BF
0x18009b084  mov     edx, 1A5h
0x18009b089  jmp     short loc_18009B0B7
0x18009b08b  test    edi, edi
0x18009b08d  jns     short loc_18009B096
0x18009b08f  mov     edx, 1ACh
0x18009b094  jmp     short loc_18009B0BC
0x18009b096  lea     rdx, [rbp+cb]
0x18009b09a  mov     rcx, r14
0x18009b09d  call    ??$Initialize@PEAG@String@Internal@Windows@@QEAAJAEBQEAGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort *>(ushort * const &,Windows::Internal::_StringDetail::dummy_t)
0x18009b0a2  mov     edi, eax
0x18009b0a4  test    eax, eax
0x18009b0a6  jns     short loc_18009B0CF
0x18009b0a8  mov     r9d, eax
0x18009b0ab  mov     edx, 1AFh
0x18009b0b0  jmp     short loc_18009B0BF
0x18009b0b2  mov     edx, 19Fh; void *
0x18009b0b7  mov     edi, 8007000Eh
0x18009b0bc  mov     r9d, edi; char *
0x18009b0bf  mov     rcx, [rbp+18h]; this
0x18009b0c3  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\tokenbroker\\plu"...
0x18009b0ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b0cf  mov     rcx, rbx; pv
0x18009b0d2  call    cs:__imp_CoTaskMemFree
0x18009b0d8  mov     eax, edi
0x18009b0da  mov     rbx, [rsp+40h+arg_0]
0x18009b0df  add     rsp, 40h
0x18009b0e3  pop     r14
0x18009b0e5  pop     rdi
0x18009b0e6  pop     rbp
0x18009b0e7  retn
```
