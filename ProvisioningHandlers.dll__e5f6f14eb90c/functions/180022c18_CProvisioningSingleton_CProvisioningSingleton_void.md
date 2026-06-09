# CProvisioningSingleton::~CProvisioningSingleton(void)

- ea: `0x180022c18`
- end: `0x180022d0c`
- name: `??1CProvisioningSingleton@@UEAA@XZ`
- size: `244`
- prototype: `void __fastcall(CProvisioningSingleton *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180022ef0`
- `0x18002b6d0`

## callees

- `0x18001ecc0`
- `0x18001fbfc`
- `0x18001fc64`
- `0x180022ae4`
- `0x180022c18`
- `0x180024408`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180022c4a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180022c96`
- `msvcrt!??3@YAXPEAX@Z` at `0x180022c4a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180022c96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022ce7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022ce7`

## pseudocode

```c
void __fastcall CProvisioningSingleton::~CProvisioningSingleton(CProvisioningSingleton *this)
{
  __int64 v2; // rdx
  __int64 v3; // rdx
  __int64 v4; // rdx

  *(_QWORD *)this = &CProvisioningSingleton::`vftable';
  v2 = *((_QWORD *)this + 46);
  if ( v2 )
  {
    std::vector<std::unique_ptr<ProvPackageInfo>>::_Destroy(this, v2, *((_QWORD *)this + 47));
    operator delete(*((void **)this + 46));
    *((_QWORD *)this + 46) = 0;
    *((_QWORD *)this + 47) = 0;
    *((_QWORD *)this + 48) = 0;
  }
  v3 = *((_QWORD *)this + 43);
  if ( v3 )
  {
    std::vector<std::unique_ptr<ProvPackageInfo>>::_Destroy(this, v3, *((_QWORD *)this + 44));
    operator delete(*((void **)this + 43));
    *((_QWORD *)this + 43) = 0;
    *((_QWORD *)this + 44) = 0;
    *((_QWORD *)this + 45) = 0;
  }
  std::vector<std::wstring>::_Tidy((char *)this + 320);
  LOBYTE(v4) = 1;
  std::wstring::_Tidy((char *)this + 288, v4, 0);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  std::unique_ptr<PluginEngine>::_Delete((char *)this + 232);
  SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::~CSingletonHelper<ProvisioniongNotificationItem &>((__int64)this);
}

```

## disassembly

```asm
0x180022c18  push    rbx
0x180022c1a  sub     rsp, 20h
0x180022c1e  lea     rax, ??_7CProvisioningSingleton@@6B@; const CProvisioningSingleton::`vftable'
0x180022c25  mov     rbx, rcx
0x180022c28  mov     [rcx], rax
0x180022c2b  mov     rdx, [rcx+170h]
0x180022c32  test    rdx, rdx
0x180022c35  jz      short loc_180022C77
0x180022c37  mov     r8, [rcx+178h]
0x180022c3e  call    ?_Destroy@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@2@0@Z; std::vector<std::unique_ptr<ProvPackageInfo>>::_Destroy(std::unique_ptr<ProvPackageInfo> *,std::unique_ptr<ProvPackageInfo> *)
0x180022c43  mov     rcx, [rbx+170h]
0x180022c4a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180022c51  nop     dword ptr [rax+rax+00h]
0x180022c56  mov     qword ptr [rbx+170h], 0
0x180022c61  mov     qword ptr [rbx+178h], 0
0x180022c6c  mov     qword ptr [rbx+180h], 0
0x180022c77  mov     rdx, [rbx+158h]
0x180022c7e  test    rdx, rdx
0x180022c81  jz      short loc_180022CC3
0x180022c83  mov     r8, [rbx+160h]
0x180022c8a  call    ?_Destroy@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@2@0@Z; std::vector<std::unique_ptr<ProvPackageInfo>>::_Destroy(std::unique_ptr<ProvPackageInfo> *,std::unique_ptr<ProvPackageInfo> *)
0x180022c8f  mov     rcx, [rbx+158h]
0x180022c96  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180022c9d  nop     dword ptr [rax+rax+00h]
0x180022ca2  mov     qword ptr [rbx+158h], 0
0x180022cad  mov     qword ptr [rbx+160h], 0
0x180022cb8  mov     qword ptr [rbx+168h], 0
0x180022cc3  lea     rcx, [rbx+140h]
0x180022cca  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180022ccf  lea     rcx, [rbx+120h]
0x180022cd6  xor     r8d, r8d
0x180022cd9  mov     dl, 1
0x180022cdb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180022ce0  lea     rcx, [rbx+0F8h]; lpCriticalSection
0x180022ce7  call    cs:__imp_DeleteCriticalSection
0x180022cee  nop     dword ptr [rax+rax+00h]
0x180022cf3  lea     rcx, [rbx+0E8h]
0x180022cfa  call    ?_Delete@?$unique_ptr@VPluginEngine@@U?$default_delete@VPluginEngine@@@std@@@std@@AEAAXXZ; std::unique_ptr<PluginEngine>::_Delete(void)
0x180022cff  mov     rcx, rbx
0x180022d02  add     rsp, 20h
0x180022d06  pop     rbx
0x180022d07  jmp     ??1?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::~CSingletonHelper<ProvisioniongNotificationItem &>(void)
```
