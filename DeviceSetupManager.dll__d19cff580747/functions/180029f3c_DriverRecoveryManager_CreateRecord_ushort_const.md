# DriverRecoveryManager::_CreateRecord(ushort const *)

- ea: `0x180029f3c`
- end: `0x18002a0a3`
- name: `?_CreateRecord@DriverRecoveryManager@@AEAA?AV?$shared_ptr@VDriverRecoveryRecord@@@std@@PEBG@Z`
- size: `359`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800295d4`

## callees

- `0x180012d54`
- `0x1800137fc`
- `0x180013864`
- `0x180013c1c`
- `0x180013d38`
- `0x180015474`
- `0x1800195b4`
- `0x18001af70`
- `0x18001baa8`
- `0x180028dc0`
- `0x180029104`
- `0x180029f3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029fa6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029fa6`

## string_xrefs

- `0x180029f91`: `onecoreuap\base\devices\setup\dsm\service\driverrecovery.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall DriverRecoveryManager::_CreateRecord(PSRWLOCK SRWLock, _QWORD *a2, const unsigned __int16 *a3)
{
  char v6; // al
  PSRWLOCK v7; // r12
  struct HDRIVERSTORE__ *Ptr; // rbx
  _DWORD *v9; // rsi
  _QWORD *v10; // rax
  _QWORD v12[2]; // [rsp+20h] [rbp-49h] BYREF
  PSRWLOCK v13[2]; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v15[32]; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v12[0] = a2;
  if ( !a3 || (v6 = 0, !*a3) )
    v6 = 1;
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AF,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\driverrecovery.cpp",
      (const char *)0x80070057LL,
      v12[0]);
  AcquireSRWLockExclusive(SRWLock);
  v13[0] = SRWLock;
  v7 = SRWLock + 3;
  std::wstring::wstring(v14, a3);
  std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<DriverRecoveryRecord>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DriverRecoveryRecord>>>,0>>::find(
    &SRWLock[3],
    v12,
    v14);
  std::wstring::~wstring(v14);
  if ( (PVOID)v12[0] == SRWLock[4].Ptr )
  {
    Ptr = (struct HDRIVERSTORE__ *)SRWLock[2].Ptr;
    v9 = operator new(0xA0u);
    v12[0] = v9;
    *(_OWORD *)v9 = 0;
    v9[2] = 1;
    v9[3] = 1;
    *(_QWORD *)v9 = &std::_Ref_count_obj2<DriverRecoveryRecord>::`vftable';
    DriverRecoveryRecord::DriverRecoveryRecord((DriverRecoveryRecord *)(v9 + 4), Ptr, a3);
    v12[0] = v9 + 4;
    v12[1] = v9;
    std::wstring::wstring(v15, a3);
    v10 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<DriverRecoveryRecord>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DriverRecoveryRecord>>>,0>>::_Try_emplace<std::wstring,>(
                      v7,
                      v14,
                      v15);
    std::shared_ptr<DriverRecoveryRecord>::operator=(*v10 + 48LL, v12);
    std::wstring::~wstring(v15);
    *a2 = v9 + 4;
    a2[1] = v9;
  }
  else
  {
    std::shared_ptr<Container>::shared_ptr<Container>(a2, v12[0] + 48LL);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v13);
  return a2;
}

```

## disassembly

```asm
0x180029f3c  push    rbp
0x180029f3e  push    rbx
0x180029f3f  push    rsi
0x180029f40  push    rdi
0x180029f41  push    r12
0x180029f43  push    r14
0x180029f45  push    r15
0x180029f47  lea     rbp, [rsp-27h]
0x180029f4c  sub     rsp, 90h
0x180029f53  mov     rax, cs:__security_cookie
0x180029f5a  xor     rax, rsp
0x180029f5d  mov     [rbp+57h+var_40], rax
0x180029f61  mov     r15, r8
0x180029f64  mov     r14, rdx
0x180029f67  mov     rbx, rcx
0x180029f6a  mov     [rbp+57h+var_A0], rdx
0x180029f6e  xor     edx, edx
0x180029f70  lea     edi, [rdx+1]
0x180029f73  test    r8, r8
0x180029f76  jz      short loc_180029F80
0x180029f78  cmp     [r8], dx
0x180029f7c  mov     al, dl
0x180029f7e  jnz     short loc_180029F83
0x180029f80  mov     al, dil
0x180029f83  mov     rcx, [rbp+5Fh]; this
0x180029f87  test    al, al
0x180029f89  jz      short loc_180029FA3
0x180029f8b  mov     r9d, 80070057h; char *
0x180029f91  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180029f98  mov     edx, 1AFh; void *
0x180029f9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029fa3  mov     rcx, rbx; SRWLock
0x180029fa6  call    cs:__imp_AcquireSRWLockExclusive
0x180029fac  mov     [rbp+57h+var_90], rbx
0x180029fb0  lea     r12, [rbx+18h]
0x180029fb4  mov     rdx, r15
0x180029fb7  lea     rcx, [rbp+57h+var_80]
0x180029fbb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029fc0  lea     r8, [rbp+57h+var_80]
0x180029fc4  lea     rdx, [rbp+57h+var_A0]
0x180029fc8  mov     rcx, r12
0x180029fcb  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<DriverRecoveryRecord>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DriverRecoveryRecord>>>,0>>::find(std::wstring const &)
0x180029fd0  lea     rcx, [rbp+57h+var_80]
0x180029fd4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029fd9  mov     rdx, [rbp+57h+var_A0]
0x180029fdd  cmp     rdx, [r12+8]
0x180029fe2  jz      short loc_180029FF5
0x180029fe4  add     rdx, 30h ; '0'
0x180029fe8  mov     rcx, r14
0x180029feb  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x180029ff0  jmp     loc_18002A079
0x180029ff5  mov     rbx, [rbx+10h]
0x180029ff9  mov     ecx, 0A0h; Size
0x180029ffe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a003  mov     rsi, rax
0x18002a006  mov     [rbp+57h+var_A0], rax
0x18002a00a  xorps   xmm0, xmm0
0x18002a00d  movups  xmmword ptr [rax], xmm0
0x18002a010  mov     [rax+8], edi
0x18002a013  mov     [rax+0Ch], edi
0x18002a016  lea     rax, ??_7?$_Ref_count_obj2@VDriverRecoveryRecord@@@std@@6B@; const std::_Ref_count_obj2<DriverRecoveryRecord>::`vftable'
0x18002a01d  mov     [rsi], rax
0x18002a020  lea     rdi, [rsi+10h]
0x18002a024  mov     r8, r15; unsigned __int16 *
0x18002a027  mov     rdx, rbx; struct HDRIVERSTORE__ *
0x18002a02a  mov     rcx, rdi; this
0x18002a02d  call    ??0DriverRecoveryRecord@@QEAA@PEAUHDRIVERSTORE__@@PEBG@Z; DriverRecoveryRecord::DriverRecoveryRecord(HDRIVERSTORE__ *,ushort const *)
0x18002a032  nop
0x18002a033  mov     [rbp+57h+var_A0], rdi
0x18002a037  mov     [rbp+57h+var_98], rsi
0x18002a03b  mov     rdx, r15
0x18002a03e  lea     rcx, [rbp+57h+var_60]
0x18002a042  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a047  nop
0x18002a048  lea     r8, [rbp+57h+var_60]
0x18002a04c  lea     rdx, [rbp+57h+var_80]
0x18002a050  mov     rcx, r12
0x18002a053  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<DriverRecoveryRecord>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DriverRecoveryRecord>>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18002a058  mov     rcx, [rax]
0x18002a05b  add     rcx, 30h ; '0'
0x18002a05f  lea     rdx, [rbp+57h+var_A0]
0x18002a063  call    ??4?$shared_ptr@VDriverRecoveryRecord@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<DriverRecoveryRecord>::operator=(std::shared_ptr<DriverRecoveryRecord> const &)
0x18002a068  nop
0x18002a069  lea     rcx, [rbp+57h+var_60]
0x18002a06d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a072  mov     [r14], rdi
0x18002a075  mov     [r14+8], rsi
0x18002a079  lea     rcx, [rbp+57h+var_90]
0x18002a07d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002a082  mov     rax, r14
0x18002a085  mov     rcx, [rbp+57h+var_40]
0x18002a089  xor     rcx, rsp; StackCookie
0x18002a08c  call    __security_check_cookie
0x18002a091  add     rsp, 90h
0x18002a098  pop     r15
0x18002a09a  pop     r14
0x18002a09c  pop     r12
0x18002a09e  pop     rdi
0x18002a09f  pop     rsi
0x18002a0a0  pop     rbx
0x18002a0a1  pop     rbp
0x18002a0a2  retn
```
