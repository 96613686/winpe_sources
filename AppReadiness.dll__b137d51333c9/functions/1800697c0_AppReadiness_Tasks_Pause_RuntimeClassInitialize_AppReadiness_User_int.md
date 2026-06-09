# AppReadiness::Tasks::Pause::RuntimeClassInitialize(AppReadiness::User *,int)

- ea: `0x1800697c0`
- end: `0x180069944`
- name: `?RuntimeClassInitialize@Pause@Tasks@AppReadiness@@QEAAJPEAVUser@3@H@Z`
- size: `388`
- prototype: `__int64 __fastcall(AppReadiness::Tasks::Pause *__hidden this, struct AppReadiness::User *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003928c`

## callees

- `0x180005580`
- `0x18000e4a0`
- `0x180019cfc`
- `0x180027a4c`
- `0x18002ecbc`
- `0x18002edec`
- `0x18003e210`
- `0x18003ecb4`
- `0x1800697c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006985a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006985a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800697fe`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800697fe`

## string_xrefs

- `0x180069826`: `CoCreateGuid(&guid)`
- `0x180069813`: `onecoreuap\shell\appreadiness\src\tasks\pause.cpp`
- `0x18006986c`: `onecoreuap\shell\appreadiness\src\tasks\pause.cpp`
- `0x18006981f`: `AppReadiness::Tasks::Pause::RuntimeClassInitialize`
- `0x180069878`: `AppReadiness::Tasks::Pause::RuntimeClassInitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppReadiness::Tasks::Pause::RuntimeClassInitialize(
        AppReadiness::Tasks::Pause *this,
        struct AppReadiness::User *a2,
        int a3)
{
  HRESULT v6; // eax
  int v7; // eax
  __int64 v8; // r8
  unsigned int v9; // ebx
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-D0h] BYREF
  GUID pguid; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE Src[40]; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR sz[64]; // [rsp+90h] [rbp-70h] BYREF

  pguid = 0;
  v6 = CoCreateGuid(&pguid);
  if ( v6 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v6,
      "CoCreateGuid(&guid)",
      "AppReadiness::Tasks::Pause::RuntimeClassInitialize",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\pause.cpp",
      27);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v7 = StringFromGUID2(&pguid, sz, 64);
  if ( v7 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v7,
      "StringFromGUID2(guid, buffer, _countof(buffer))",
      "AppReadiness::Tasks::Pause::RuntimeClassInitialize",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\pause.cpp",
      29);
    throw (Windows::HResultException *)pExceptionObject;
  }
  std::wstring::wstring((__int64)Src);
  std::wstring::reserve(Src, 74);
  std::wstring::_Append<unsigned short>(Src);
  v8 = -1;
  do
    ++v8;
  while ( sz[v8] );
  std::wstring::_Append<unsigned short>(Src);
  *((_DWORD *)this + 72) = a3;
  v9 = AppReadiness::Impl::BaseTask::RuntimeClassInitialize((char *)this + 32, a2, Src, 2);
  std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(Src);
  return v9;
}

```

## disassembly

```asm
0x1800697c0  mov     [rsp-8+arg_10], rbx
0x1800697c5  mov     [rsp-8+arg_18], rsi
0x1800697ca  push    rbp
0x1800697cb  push    rdi
0x1800697cc  push    r14
0x1800697ce  lea     rbp, [rsp-20h]
0x1800697d3  sub     rsp, 120h
0x1800697da  mov     rax, cs:__security_cookie
0x1800697e1  xor     rax, rsp
0x1800697e4  mov     [rbp+30h+var_20], rax
0x1800697e8  mov     edi, r8d
0x1800697eb  mov     rsi, rdx
0x1800697ee  mov     rbx, rcx
0x1800697f1  xorps   xmm0, xmm0
0x1800697f4  movups  xmmword ptr [rsp+130h+pguid.Data1], xmm0
0x1800697f9  lea     rcx, [rsp+130h+pguid]; pguid
0x1800697fe  call    cs:__imp_CoCreateGuid
0x180069804  xor     r14d, r14d
0x180069807  test    eax, eax
0x180069809  jns     short loc_18006984B
0x18006980b  mov     [rsp+130h+var_108], 1Bh; int
0x180069813  lea     rcx, aOnecoreuapShel_26; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18006981a  mov     [rsp+130h+var_110], rcx; char *
0x18006981f  lea     r9, aAppreadinessTa_25; "AppReadiness::Tasks::Pause::RuntimeClas"...
0x180069826  lea     r8, aCocreateguidGu; "CoCreateGuid(&guid)"
0x18006982d  mov     edx, eax; int
0x18006982f  lea     rcx, [rsp+130h+pExceptionObject]; this
0x180069834  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180069839  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180069840  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180069845  call    _CxxThrowException_0
0x18006984b  mov     r8d, 40h ; '@'; cchMax
0x180069851  lea     rdx, [rbp+30h+sz]; lpsz
0x180069855  lea     rcx, [rsp+130h+pguid]; rguid
0x18006985a  call    cs:__imp_StringFromGUID2
0x180069860  test    eax, eax
0x180069862  jns     short loc_1800698A4
0x180069864  mov     [rsp+130h+var_108], 1Dh; int
0x18006986c  lea     rcx, aOnecoreuapShel_26; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180069873  mov     [rsp+130h+var_110], rcx; char *
0x180069878  lea     r9, aAppreadinessTa_25; "AppReadiness::Tasks::Pause::RuntimeClas"...
0x18006987f  lea     r8, aStringfromguid; "StringFromGUID2(guid, buffer, _countof("...
0x180069886  mov     edx, eax; int
0x180069888  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18006988d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180069892  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180069899  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18006989e  call    _CxxThrowException_0
0x1800698a4  lea     rcx, [rsp+130h+Src]
0x1800698a9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800698ae  nop
0x1800698af  mov     edx, 4Ah ; 'J'
0x1800698b4  lea     rcx, [rsp+130h+Src]
0x1800698b9  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x1800698be  mov     r8d, 6
0x1800698c4  lea     rdx, aPause; "pause-"
0x1800698cb  lea     rcx, [rsp+130h+Src]; Src
0x1800698d0  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800698d5  lea     rax, [rbp+30h+sz]
0x1800698d9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800698dd  inc     r8
0x1800698e0  cmp     [rax+r8*2], r14w
0x1800698e5  jnz     short loc_1800698DD
0x1800698e7  lea     rdx, [rbp+30h+sz]
0x1800698eb  lea     rcx, [rsp+130h+Src]; Src
0x1800698f0  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800698f5  mov     [rbx+120h], edi
0x1800698fb  lea     rcx, [rbx+20h]
0x1800698ff  mov     r9d, 2
0x180069905  lea     r8, [rsp+130h+Src]
0x18006990a  mov     rdx, rsi
0x18006990d  call    ?RuntimeClassInitialize@BaseTask@Impl@AppReadiness@@IEAAJPEAVUser@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TaskPriority@3@@Z; AppReadiness::Impl::BaseTask::RuntimeClassInitialize(AppReadiness::User *,std::wstring const &,AppReadiness::TaskPriority)
0x180069912  mov     ebx, eax
0x180069914  lea     rcx, [rsp+130h+Src]
0x180069919  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18006991e  mov     eax, ebx
0x180069920  mov     rcx, [rbp+30h+var_20]
0x180069924  xor     rcx, rsp; StackCookie
0x180069927  call    __security_check_cookie
0x18006992c  lea     r11, [rsp+130h+var_10]
0x180069934  mov     rbx, [r11+30h]
0x180069938  mov     rsi, [r11+38h]
0x18006993c  mov     rsp, r11
0x18006993f  pop     r14
0x180069941  pop     rdi
0x180069942  pop     rbp
0x180069943  retn
```
