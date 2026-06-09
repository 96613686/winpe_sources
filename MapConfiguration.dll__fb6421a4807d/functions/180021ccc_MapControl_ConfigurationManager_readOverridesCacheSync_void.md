# MapControl::ConfigurationManager::readOverridesCacheSync(void)

- ea: `0x180021ccc`
- end: `0x180021e0d`
- name: `?readOverridesCacheSync@ConfigurationManager@MapControl@@AEAAXXZ`
- size: `321`
- prototype: `void __fastcall(MapControl::ConfigurationManager *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18001efcc`

## callees

- `0x1800094a0`
- `0x18000c354`
- `0x18000c850`
- `0x18000d980`
- `0x180013da8`
- `0x180020e18`
- `0x180021630`
- `0x1800219fc`
- `0x180021ccc`
- `0x180029980`
- `0x180029b2c`
- `0x180034324`
- `0x180034538`
- `0x180043010`

## string_xrefs

- `0x180021cfa`: `overrides.json`
- `0x180021d8e`: `overrides.json`

## pseudocode

```c
void __fastcall MapControl::ConfigurationManager::readOverridesCacheSync(MapControl::ConfigurationManager *this)
{
  unsigned int v2; // ebx
  struct Pal::Infrastructure *Instance; // rax
  _QWORD *v4; // rbx
  __int64 v5; // rdx
  _BYTE *v6; // r8
  unsigned int v7; // ebx
  const struct Json::Value *v8; // rax
  _QWORD *v9; // [rsp+38h] [rbp-11h] BYREF
  std::_Ref_count_base *v10; // [rsp+40h] [rbp-9h]
  _BYTE v11[40]; // [rsp+48h] [rbp-1h] BYREF
  _BYTE v12[32]; // [rsp+70h] [rbp+27h] BYREF

  v2 = *((_DWORD *)this + 100);
  std::wstring::wstring(v12, L"overrides.json");
  Instance = Pal::Infrastructure::getInstance();
  (*(void (__fastcall **)(_QWORD, _QWORD **, _BYTE *, _QWORD))(**((_QWORD **)Instance + 1) + 32LL))(
    *((_QWORD *)Instance + 1),
    &v9,
    v12,
    v2);
  std::wstring::_Tidy_deallocate(v12);
  v4 = v9;
  if ( !v9 )
    goto LABEL_8;
  v5 = v9[1];
  if ( *v9 == v5 )
    goto LABEL_8;
  if ( (unsigned __int64)(v5 - *v9) > 2 )
  {
    v6 = (_BYTE *)*v9;
    if ( *(_BYTE *)*v9 == 0xFF && v6[1] == 0xFE )
      v4[1] = std::_Copy_memmove<Pal::EventHandlerAndId<Core::EventHandler<>> *,Pal::EventHandlerAndId<Core::EventHandler<>> *>(v6 + 2);
  }
  if ( !(unsigned __int8)MapControl::ConfigurationManager::processOverridesCache(this) )
  {
LABEL_8:
    v7 = *((_DWORD *)this + 100);
    std::wstring::wstring(v11, L"overrides.json");
    Pal::IO::deleteFile(v11, v7);
    std::wstring::_Tidy_deallocate(v11);
    v8 = (const struct Json::Value *)Json::Value::Value(v11, 0);
    MapControl::ConfigurationManager::initializeClientBucket(this, v8);
    Json::Value::~Value((Json::Value *)v11);
  }
  MapControl::ConfigurationManager::fetchOverridesForAllConfigurations(this);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
}

```

## disassembly

```asm
0x180021ccc  mov     [rsp-8+arg_8], rbx
0x180021cd1  mov     [rsp-8+arg_10], rdi
0x180021cd6  push    rbp
0x180021cd7  lea     rbp, [rsp-57h]
0x180021cdc  sub     rsp, 0A0h
0x180021ce3  mov     rax, cs:__security_cookie
0x180021cea  xor     rax, rsp
0x180021ced  mov     [rbp+57h+var_10], rax
0x180021cf1  mov     rdi, rcx
0x180021cf4  mov     ebx, [rcx+190h]
0x180021cfa  lea     rdx, aOverridesJson; "overrides.json"
0x180021d01  lea     rcx, [rbp+57h+var_30]
0x180021d05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021d0a  nop
0x180021d0b  call    ?getInstance@Infrastructure@Pal@@CAAEAV12@XZ; Pal::Infrastructure::getInstance(void)
0x180021d10  mov     rcx, [rax+8]
0x180021d14  mov     rax, [rcx]
0x180021d17  mov     r9d, ebx
0x180021d1a  lea     r8, [rbp+57h+var_30]
0x180021d1e  lea     rdx, [rbp+57h+var_68]
0x180021d22  mov     rax, [rax+20h]
0x180021d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d2b  nop
0x180021d2c  lea     rcx, [rbp+57h+var_30]
0x180021d30  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021d35  mov     rbx, [rbp+57h+var_68]
0x180021d39  test    rbx, rbx
0x180021d3c  jz      short loc_180021D88
0x180021d3e  mov     rdx, [rbx+8]
0x180021d42  cmp     [rbx], rdx
0x180021d45  jz      short loc_180021D88
0x180021d47  mov     rax, rdx
0x180021d4a  sub     rax, [rbx]
0x180021d4d  cmp     rax, 2
0x180021d51  jbe     short loc_180021D79
0x180021d53  mov     r8, [rbx]
0x180021d56  cmp     byte ptr [r8], 0FFh
0x180021d5a  jnz     short loc_180021D79
0x180021d5c  cmp     byte ptr [r8+1], 0FEh
0x180021d61  jnz     short loc_180021D79
0x180021d63  lea     rcx, [r8+2]; Src
0x180021d67  cmp     r8, rcx
0x180021d6a  jz      short loc_180021D79
0x180021d6c  call    ??$_Copy_memmove@PEAV?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@PEAV12@@std@@YAPEAV?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@PEAV12@00@Z; std::_Copy_memmove<Pal::EventHandlerAndId<Core::EventHandler<>> *,Pal::EventHandlerAndId<Core::EventHandler<>> *>(Pal::EventHandlerAndId<Core::EventHandler<>> *,Pal::EventHandlerAndId<Core::EventHandler<>> *,Pal::EventHandlerAndId<Core::EventHandler<>> *)
0x180021d71  mov     [rbx+8], rax
0x180021d75  mov     rbx, [rbp+57h+var_68]
0x180021d79  mov     rdx, rbx
0x180021d7c  mov     rcx, rdi; this
0x180021d7f  call    ?processOverridesCache@ConfigurationManager@MapControl@@AEAA_NAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; MapControl::ConfigurationManager::processOverridesCache(std::vector<uchar> const &)
0x180021d84  test    al, al
0x180021d86  jnz     short loc_180021DD5
0x180021d88  mov     ebx, [rdi+190h]
0x180021d8e  lea     rdx, aOverridesJson; "overrides.json"
0x180021d95  lea     rcx, [rbp+57h+var_58]
0x180021d99  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021d9e  nop
0x180021d9f  mov     edx, ebx
0x180021da1  lea     rcx, [rbp+57h+var_58]
0x180021da5  call    ?deleteFile@IO@Pal@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FileLocation@2@@Z; Pal::IO::deleteFile(std::wstring const &,Pal::FileLocation)
0x180021daa  nop
0x180021dab  lea     rcx, [rbp+57h+var_58]
0x180021daf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021db4  xor     edx, edx
0x180021db6  lea     rcx, [rbp+57h+var_58]
0x180021dba  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x180021dbf  nop
0x180021dc0  mov     rdx, rax; struct Json::Value *
0x180021dc3  mov     rcx, rdi; this
0x180021dc6  call    ?initializeClientBucket@ConfigurationManager@MapControl@@AEAAXAEBVValue@Json@@@Z; MapControl::ConfigurationManager::initializeClientBucket(Json::Value const &)
0x180021dcb  nop
0x180021dcc  lea     rcx, [rbp+57h+var_58]; this
0x180021dd0  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x180021dd5  mov     rcx, rdi; this
0x180021dd8  call    ?fetchOverridesForAllConfigurations@ConfigurationManager@MapControl@@AEAAXXZ; MapControl::ConfigurationManager::fetchOverridesForAllConfigurations(void)
0x180021ddd  nop
0x180021dde  mov     rcx, [rbp+57h+var_60]; this
0x180021de2  test    rcx, rcx
0x180021de5  jz      short loc_180021DEC
0x180021de7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021dec  mov     rcx, [rbp+57h+var_10]
0x180021df0  xor     rcx, rsp; StackCookie
0x180021df3  call    __security_check_cookie
0x180021df8  lea     r11, [rsp+0A0h+var_s0]
0x180021e00  mov     rbx, [r11+18h]
0x180021e04  mov     rdi, [r11+20h]
0x180021e08  mov     rsp, r11
0x180021e0b  pop     rbp
0x180021e0c  retn
```
