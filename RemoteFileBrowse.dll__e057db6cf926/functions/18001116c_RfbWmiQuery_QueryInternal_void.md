# RfbWmiQuery::QueryInternal(void)

- ea: `0x18001116c`
- end: `0x180011364`
- name: `?QueryInternal@RfbWmiQuery@@AEAAXXZ`
- size: `504`
- prototype: `void __fastcall(RfbWmiQuery *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011e60`

## callees

- `0x180009520`
- `0x18000cd18`
- `0x18000d5c4`
- `0x18000e61c`
- `0x18000ee58`
- `0x18001116c`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112c0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011339`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011339`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800112a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001132f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800112a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001132f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001125b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001131a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001125b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001131a`

## pseudocode

```c
void __fastcall RfbWmiQuery::QueryInternal(RfbWmiQuery *this)
{
  __int64 v2; // rdi
  __int64 v3; // r15
  const unsigned __int16 *v4; // rdx
  const struct _MI_Instance *OperationInstance; // rdx
  void **v6; // rdx
  LPVOID v7; // rax
  void *v8; // rcx
  __int64 v9; // r8
  const char *v10; // r9
  RfbServer *v11; // [rsp+20h] [rbp-48h]
  volatile signed __int32 *v12; // [rsp+28h] [rbp-40h]
  struct _MI_Operation v13; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LPVOID pv; // [rsp+78h] [rbp+10h] BYREF
  char *v16; // [rsp+80h] [rbp+18h]

  RfbServerRegistrar::GetWmiConnection(*((PSRWLOCK *)this + 22));
  if ( v11 )
  {
    (*(void (__fastcall **)(RfbWmiQuery *))(*(_QWORD *)this + 24LL))(this);
    v2 = *((_QWORD *)this + 9);
    v3 = *((_QWORD *)this + 10);
    while ( v2 != v3 )
    {
      memset(&v13, 0, sizeof(v13));
      if ( *(_QWORD *)(v2 + 24) <= 7u )
        v4 = (const unsigned __int16 *)v2;
      else
        v4 = *(const unsigned __int16 **)v2;
      RfbServer::ExecQuery(v11, v4, &v13);
      while ( 1 )
      {
        OperationInstance = GetOperationInstance(&v13);
        if ( !OperationInstance )
          break;
        pv = 0;
        (*(void (__fastcall **)(RfbWmiQuery *, const struct _MI_Instance *, LPVOID *))(*(_QWORD *)this + 32LL))(
          this,
          OperationInstance,
          &pv);
        if ( pv )
        {
          AcquireSRWLockExclusive((PSRWLOCK)this + 3);
          v16 = (char *)this + 24;
          v6 = (void **)*((_QWORD *)this + 5);
          if ( v6 == *((void ***)this + 6) )
          {
            std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Emplace_reallocate<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
              (void ***)this + 4,
              v6,
              (__int64 *)&pv);
          }
          else
          {
            v7 = pv;
            pv = 0;
            *v6 = v7;
            *((_QWORD *)this + 5) += 8LL;
          }
          if ( this != (RfbWmiQuery *)-24LL )
            ReleaseSRWLockExclusive((PSRWLOCK)this + 3);
        }
        v8 = pv;
        pv = 0;
        if ( v8 )
          CoTaskMemFree(v8);
      }
      if ( v13.ft )
        ((void (__fastcall *)(struct _MI_Operation *, _QWORD))v13.ft->Close)(&v13, 0);
      v2 += 32;
    }
  }
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)())v12)();
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)())(*(_QWORD *)v12 + 8LL))();
    }
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 1);
  *((_DWORD *)this + 4) = 2;
  if ( this != (RfbWmiQuery *)-8LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 1);
  if ( !SetEvent(*((HANDLE *)this + 7)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v9, v10);
}

```

## disassembly

```asm
0x18001116c  mov     [rsp+arg_18], rbx
0x180011171  mov     [rsp+arg_0], rcx
0x180011176  push    rsi
0x180011177  push    rdi
0x180011178  push    r15
0x18001117a  sub     rsp, 50h
0x18001117e  mov     rbx, rcx
0x180011181  lea     r8, [rcx+90h]
0x180011188  lea     rdx, [rsp+68h+var_48]
0x18001118d  mov     rcx, [rcx+0B0h]; SRWLock
0x180011194  call    ?GetWmiConnection@RfbServerRegistrar@@QEBA?AV?$shared_ptr@VRfbServer@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; RfbServerRegistrar::GetWmiConnection(std::wstring const &)
0x180011199  nop
0x18001119a  cmp     [rsp+68h+var_48], 0
0x1800111a0  jz      loc_1800112CB
0x1800111a6  mov     rax, [rbx]
0x1800111a9  mov     rdx, [rsp+68h+var_48]
0x1800111ae  mov     rcx, rbx
0x1800111b1  mov     rax, [rax+18h]
0x1800111b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111ba  mov     rdi, [rbx+48h]
0x1800111be  mov     r15, [rbx+50h]
0x1800111c2  cmp     rdi, r15
0x1800111c5  jz      loc_1800112CB
0x1800111cb  cmp     [rsp+68h+var_48], 0
0x1800111d1  jz      short loc_180011229
0x1800111d3  xorps   xmm0, xmm0
0x1800111d6  xor     eax, eax
0x1800111d8  movups  xmmword ptr [rsp+68h+var_38.reserved1], xmm0
0x1800111dd  mov     [rsp+68h+var_38.ft], rax
0x1800111e2  cmp     qword ptr [rdi+18h], 7
0x1800111e7  jbe     short loc_1800111EE
0x1800111e9  mov     rdx, [rdi]
0x1800111ec  jmp     short loc_1800111F1
0x1800111ee  mov     rdx, rdi; unsigned __int16 *
0x1800111f1  lea     r8, [rsp+68h+var_38]; struct _MI_Operation *
0x1800111f6  mov     rcx, [rsp+68h+var_48]; this
0x1800111fb  call    ?ExecQuery@RfbServer@@QEAAXPEBGPEAU_MI_Operation@@@Z; RfbServer::ExecQuery(ushort const *,_MI_Operation *)
0x180011200  lea     rcx, [rsp+68h+var_38]; struct _MI_Operation *
0x180011205  call    ?GetOperationInstance@@YAPEBU_MI_Instance@@PEAU_MI_Operation@@@Z; GetOperationInstance(_MI_Operation *)
0x18001120a  mov     rdx, rax
0x18001120d  test    rax, rax
0x180011210  jnz     short loc_18001122F
0x180011212  mov     rax, [rsp+68h+var_38.ft]
0x180011217  test    rax, rax
0x18001121a  jz      short loc_180011229
0x18001121c  lea     rcx, [rsp+68h+var_38]
0x180011221  mov     rax, [rax]
0x180011224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011229  add     rdi, 20h ; ' '
0x18001122d  jmp     short loc_1800111C2
0x18001122f  mov     [rsp+68h+pv], 0
0x180011238  mov     rax, [rbx]
0x18001123b  lea     r8, [rsp+68h+pv]
0x180011240  mov     rcx, rbx
0x180011243  mov     rax, [rax+20h]
0x180011247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001124c  cmp     [rsp+68h+pv], 0
0x180011252  jz      short loc_1800112A9
0x180011254  lea     rsi, [rbx+18h]
0x180011258  mov     rcx, rsi; SRWLock
0x18001125b  call    cs:__imp_AcquireSRWLockExclusive
0x180011261  mov     [rsp+68h+arg_10], rsi
0x180011269  lea     rcx, [rbx+20h]
0x18001126d  mov     rdx, [rcx+8]
0x180011271  cmp     rdx, [rcx+10h]
0x180011275  jz      short loc_18001128F
0x180011277  mov     rax, [rsp+68h+pv]
0x18001127c  mov     [rsp+68h+pv], 0
0x180011285  mov     [rdx], rax
0x180011288  add     qword ptr [rcx+8], 8
0x18001128d  jmp     short loc_18001129A
0x18001128f  lea     r8, [rsp+68h+pv]
0x180011294  call    ??$_Emplace_reallocate@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@?$vector@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAPEAV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAV23@$$QEAV23@@Z; std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Emplace_reallocate<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> * const,wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180011299  nop
0x18001129a  test    rsi, rsi
0x18001129d  jz      short loc_1800112A9
0x18001129f  mov     rcx, rsi; SRWLock
0x1800112a2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800112a8  nop
0x1800112a9  mov     rcx, [rsp+68h+pv]; pv
0x1800112ae  mov     [rsp+68h+pv], 0
0x1800112b7  test    rcx, rcx
0x1800112ba  jz      loc_180011200
0x1800112c0  call    cs:__imp_CoTaskMemFree
0x1800112c6  jmp     loc_180011200
0x1800112cb  mov     rdi, [rsp+68h+var_40]
0x1800112d0  test    rdi, rdi
0x1800112d3  jz      short loc_18001130C
0x1800112d5  or      esi, 0FFFFFFFFh
0x1800112d8  mov     eax, esi
0x1800112da  lock xadd [rdi+8], eax
0x1800112df  add     eax, esi
0x1800112e1  jnz     short loc_18001130C
0x1800112e3  mov     rax, [rdi]
0x1800112e6  mov     rcx, rdi
0x1800112e9  mov     rax, [rax]
0x1800112ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112f1  mov     eax, esi
0x1800112f3  lock xadd [rdi+0Ch], eax
0x1800112f8  add     eax, esi
0x1800112fa  jnz     short loc_18001130C
0x1800112fc  mov     rax, [rdi]
0x1800112ff  mov     rcx, rdi
0x180011302  mov     rax, [rax+8]
0x180011306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001130b  nop
0x18001130c  jmp     short loc_180011313
0x18001130e  mov     rbx, [rsp+68h+arg_0]
0x180011313  lea     rdi, [rbx+8]
0x180011317  mov     rcx, rdi; SRWLock
0x18001131a  call    cs:__imp_AcquireSRWLockExclusive
0x180011320  mov     dword ptr [rbx+10h], 2
0x180011327  test    rdi, rdi
0x18001132a  jz      short loc_180011335
0x18001132c  mov     rcx, rdi; SRWLock
0x18001132f  call    cs:__imp_ReleaseSRWLockExclusive
0x180011335  mov     rcx, [rbx+38h]; hEvent
0x180011339  call    cs:__imp_SetEvent
0x18001133f  test    eax, eax
0x180011341  jz      short loc_180011354
0x180011343  mov     rbx, [rsp+68h+arg_18]
0x18001134b  add     rsp, 50h
0x18001134f  pop     r15
0x180011351  pop     rdi
0x180011352  pop     rsi
0x180011353  retn
0x180011354  mov     rcx, [rsp+68h]; this
0x180011359  mov     edx, 0A01h; void *
0x18001135e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
