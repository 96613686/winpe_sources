# CRegistration::~CRegistration(void)

- ea: `0x18003385c`
- end: `0x18003396f`
- name: `??1CRegistration@@QEAA@XZ`
- size: `275`
- prototype: `void __fastcall(CRegistration *this, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012320`

## callees

- `0x180003f50`
- `0x1800069f0`
- `0x18000d84c`
- `0x18003385c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800338c3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800338c3`
- `ntdll!NtDeleteWnfStateName` at `0x18003387e`
- `ntdll!NtDeleteWnfStateName` at `0x18003387e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRegistration::~CRegistration(CRegistration *this, __int64 a2)
{
  __int64 v3; // rcx
  _QWORD *v4; // rdi
  void *v5; // rcx
  __int64 v6; // rcx

  if ( !*((_DWORD *)this + 54) )
    NtDeleteWnfStateName((char *)this + 208);
  v3 = *((_QWORD *)this + 53);
  if ( v3 )
  {
    LOBYTE(a2) = v3 != (_QWORD)this + 368;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, a2);
    *((_QWORD *)this + 53) = 0;
  }
  *((_QWORD *)this + 38) = &Windows::Sms::Common::recursive_mutex::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  v4 = *(_QWORD **)(*((_QWORD *)this + 31) + 8LL);
  while ( !*((_BYTE *)v4 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<SmsServiceCallContext *>>::_Erase_tree<std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>>>(
      (__int64)this + 248,
      (__int64)this + 248,
      v4[2]);
    v5 = v4;
    v4 = (_QWORD *)*v4;
    operator delete(v5);
  }
  operator delete(*((void **)this + 31));
  v6 = *((_QWORD *)this + 30);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  std::wstring::~wstring((char **)this + 22);
  std::wstring::~wstring((char **)this + 18);
  std::wstring::~wstring((char **)this + 14);
  std::wstring::~wstring((char **)this + 10);
  std::wstring::~wstring((char **)this + 6);
  std::wstring::~wstring((char **)this);
}

```

## disassembly

```asm
0x18003385c  mov     [rsp+arg_0], rbx
0x180033861  mov     [rsp+arg_8], rsi
0x180033866  push    rdi
0x180033867  sub     rsp, 20h
0x18003386b  mov     rbx, rcx
0x18003386e  cmp     dword ptr [rcx+0D8h], 0
0x180033875  jnz     short loc_180033884
0x180033877  add     rcx, 0D0h
0x18003387e  call    cs:__imp_NtDeleteWnfStateName
0x180033884  lea     rdi, [rbx+170h]
0x18003388b  mov     rcx, [rdi+38h]
0x18003388f  test    rcx, rcx
0x180033892  jz      short loc_1800338AE
0x180033894  mov     rax, [rcx]
0x180033897  cmp     rcx, rdi
0x18003389a  setnz   dl
0x18003389d  mov     rax, [rax+20h]
0x1800338a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338a6  mov     qword ptr [rdi+38h], 0
0x1800338ae  lea     rax, ??_7recursive_mutex@Common@Sms@Windows@@6B@; const Windows::Sms::Common::recursive_mutex::`vftable'
0x1800338b5  mov     [rbx+130h], rax
0x1800338bc  lea     rcx, [rbx+138h]; lpCriticalSection
0x1800338c3  call    cs:__imp_DeleteCriticalSection
0x1800338c9  lea     rsi, [rbx+0F8h]
0x1800338d0  mov     rax, [rsi]
0x1800338d3  mov     rdi, [rax+8]
0x1800338d7  jmp     short loc_1800338F8
0x1800338d9  mov     r8, [rdi+10h]
0x1800338dd  mov     rdx, rsi
0x1800338e0  mov     rcx, rsi
0x1800338e3  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEAUSmsServiceCallContext@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEAUSmsServiceCallContext@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEAUSmsServiceCallContext@@PEAX@std@@@1@PEAU?$_Tree_node@PEAUSmsServiceCallContext@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<SmsServiceCallContext *>>::_Erase_tree<std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>>>(std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>> &,std::_Tree_node<SmsServiceCallContext *,void *> *)
0x1800338e8  mov     rcx, rdi; Block
0x1800338eb  mov     rdi, [rdi]
0x1800338ee  mov     edx, 28h ; '('
0x1800338f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800338f8  cmp     byte ptr [rdi+19h], 0
0x1800338fc  jz      short loc_1800338D9
0x1800338fe  mov     edx, 28h ; '('
0x180033903  mov     rcx, [rsi]; Block
0x180033906  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003390b  nop
0x18003390c  mov     rcx, [rbx+0F0h]
0x180033913  test    rcx, rcx
0x180033916  jz      short loc_180033925
0x180033918  mov     rax, [rcx]
0x18003391b  mov     rax, [rax+10h]
0x18003391f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033924  nop
0x180033925  lea     rcx, [rbx+0B0h]; void *
0x18003392c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033931  lea     rcx, [rbx+90h]; void *
0x180033938  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003393d  lea     rcx, [rbx+70h]; void *
0x180033941  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033946  lea     rcx, [rbx+50h]; void *
0x18003394a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003394f  lea     rcx, [rbx+30h]; void *
0x180033953  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033958  mov     rcx, rbx; void *
0x18003395b  mov     rbx, [rsp+28h+arg_0]
0x180033960  mov     rsi, [rsp+28h+arg_8]
0x180033965  add     rsp, 20h
0x180033969  pop     rdi
0x18003396a  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
