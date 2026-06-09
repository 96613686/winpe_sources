# HeartbeatEventManager::Initialize(void)

- ea: `0x180077250`
- end: `0x18007734d`
- name: `?Initialize@HeartbeatEventManager@@UEAAJXZ`
- size: `253`
- prototype: `__int64 __fastcall(HeartbeatEventManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800771b0`

## callees

- `0x180077250`
- `0x180077360`
- `0x180078410`
- `0x1800edfd8`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077278`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077278`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007729f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800772e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007729f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800772e6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800772fd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800772fd`

## string_xrefs

- `0x1800772cc`: `onecoreuap\base\appmodel\search\common\screenonsession\screenoneventmanager.cpp`
- `0x18007732a`: `onecoreuap\base\appmodel\search\common\screenonsession\screenoneventmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HeartbeatEventManager::Initialize(HeartbeatEventManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v3; // eax
  unsigned int v4; // edi
  HRESULT v6; // eax
  unsigned int v7; // esi
  int v8[2]; // [rsp+20h] [rbp-28h] BYREF
  GUID pguid; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  *(_QWORD *)v8 = v2;
  if ( !*((_BYTE *)this + 97) )
  {
    pguid = 0;
    v6 = CoCreateGuid(&pguid);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\screenonsession\\screenoneventmanager.cpp",
        (const char *)(unsigned int)v6,
        v8[0]);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v8);
      return v7;
    }
    (*(void (__fastcall **)(HeartbeatEventManager *, GUID *))(*(_QWORD *)this + 24LL))(this, &pguid);
  }
  v3 = EventManager::Initialize(this);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\screenonsession\\screenoneventmanager.cpp",
      (const char *)(unsigned int)v3,
      v8[0]);
    if ( v2 )
      LeaveCriticalSection(v2);
    return v4;
  }
  else
  {
    if ( v2 )
      LeaveCriticalSection(v2);
    return 0;
  }
}

```

## disassembly

```asm
0x180077250  mov     [rsp+arg_8], rbx
0x180077255  mov     [rsp+arg_10], rsi
0x18007725a  push    rdi
0x18007725b  sub     rsp, 40h
0x18007725f  mov     rax, cs:__security_cookie
0x180077266  xor     rax, rsp
0x180077269  mov     [rsp+48h+var_10], rax
0x18007726e  mov     rdi, rcx
0x180077271  lea     rbx, [rcx+38h]
0x180077275  mov     rcx, rbx; lpCriticalSection
0x180077278  call    cs:__imp_EnterCriticalSection
0x18007727e  mov     qword ptr [rsp+48h+var_28], rbx; int
0x180077283  cmp     byte ptr [rdi+61h], 0
0x180077287  jz      short loc_1800772F0
0x180077289  mov     rcx, rdi; this
0x18007728c  call    ?Initialize@EventManager@@UEAAJXZ; EventManager::Initialize(void)
0x180077291  mov     edi, eax
0x180077293  test    eax, eax
0x180077295  js      short loc_1800772C4
0x180077297  test    rbx, rbx
0x18007729a  jz      short loc_1800772A5
0x18007729c  mov     rcx, rbx; lpCriticalSection
0x18007729f  call    cs:__imp_LeaveCriticalSection
0x1800772a5  xor     eax, eax
0x1800772a7  mov     rcx, [rsp+48h+var_10]
0x1800772ac  xor     rcx, rsp; StackCookie
0x1800772af  call    __security_check_cookie
0x1800772b4  mov     rbx, [rsp+48h+arg_8]
0x1800772b9  mov     rsi, [rsp+48h+arg_10]
0x1800772be  add     rsp, 40h
0x1800772c2  pop     rdi
0x1800772c3  retn
0x1800772c4  mov     rcx, [rsp+48h]; this
0x1800772c9  mov     r9d, edi; char *
0x1800772cc  lea     r8, aOnecoreuapBase_175; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800772d3  mov     edx, 0DAh; void *
0x1800772d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800772dd  nop
0x1800772de  test    rbx, rbx
0x1800772e1  jz      short loc_1800772EC
0x1800772e3  mov     rcx, rbx; lpCriticalSection
0x1800772e6  call    cs:__imp_LeaveCriticalSection
0x1800772ec  mov     eax, edi
0x1800772ee  jmp     short loc_1800772A7
0x1800772f0  xorps   xmm0, xmm0
0x1800772f3  movups  xmmword ptr [rsp+48h+pguid.Data1], xmm0
0x1800772f8  lea     rcx, [rsp+48h+pguid]; pguid
0x1800772fd  call    cs:__imp_CoCreateGuid
0x180077303  mov     esi, eax
0x180077305  test    eax, eax
0x180077307  js      short loc_180077322
0x180077309  mov     rax, [rdi]
0x18007730c  lea     rdx, [rsp+48h+pguid]
0x180077311  mov     rcx, rdi
0x180077314  mov     rax, [rax+18h]
0x180077318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007731d  jmp     loc_180077289
0x180077322  mov     rcx, [rsp+48h]; this
0x180077327  mov     r9d, esi; char *
0x18007732a  lea     r8, aOnecoreuapBase_175; "onecoreuap\\base\\appmodel\\search\\com"...
0x180077331  mov     edx, 0D4h; void *
0x180077336  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007733b  nop
0x18007733c  lea     rcx, [rsp+48h+var_28]
0x180077341  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180077346  mov     eax, esi
0x180077348  jmp     loc_1800772A7
```
