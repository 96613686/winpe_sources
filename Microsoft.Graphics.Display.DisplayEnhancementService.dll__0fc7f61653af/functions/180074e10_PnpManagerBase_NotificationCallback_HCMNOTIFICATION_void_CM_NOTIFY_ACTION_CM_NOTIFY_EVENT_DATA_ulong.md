# PnpManagerBase::NotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)

- ea: `0x180074e10`
- end: `0x180074f9e`
- name: `?NotificationCallback@PnpManagerBase@@KAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180005860`
- `0x1800058bc`
- `0x180009050`
- `0x180009534`
- `0x180009eb0`
- `0x18000f7b0`
- `0x18000fb14`
- `0x18001ff40`
- `0x180066310`
- `0x180074adc`
- `0x180074e10`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180074ed1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180074ed1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180074f5b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180074f5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180074ef0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180074ef0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PnpManagerBase::NotificationCallback(__int64 a1, _QWORD *a2, unsigned int a3, __int64 a4)
{
  char *v8; // rbx
  PTP_WORK ThreadpoolWork; // r15
  struct _TP_WORK *v10; // r14
  __int64 v11; // rax
  __int64 v12; // rcx
  std::_Ref_count_base *v13; // rcx
  char *v15; // [rsp+20h] [rbp-78h] BYREF
  char *v16; // [rsp+28h] [rbp-70h] BYREF
  _BYTE v17[32]; // [rsp+30h] [rbp-68h] BYREF

  if ( a3 <= 5 )
  {
    std::wstring::wstring(v17, &dword_180100DC4);
    if ( !*(_DWORD *)a4 && a4 != -24 )
      std::wstring::assign(v17, a4 + 24);
    v8 = (char *)operator new(0x60u);
    v16 = v8;
    *(_QWORD *)v8 = 0;
    *((_QWORD *)v8 + 1) = 0;
    *((_OWORD *)v8 + 1) = 0;
    std::wstring::wstring(v8 + 32, &dword_180100DC4);
    *((_QWORD *)v8 + 8) = 0;
    *((_DWORD *)v8 + 18) = 10;
    *((_QWORD *)v8 + 10) = 0;
    *((_DWORD *)v8 + 22) = 0;
    v15 = v8;
    ThreadpoolWork = CreateThreadpoolWork(
                       PnpManagerBase::NotifyDeviceChangeAsync,
                       v8,
                       (PTP_CALLBACK_ENVIRON)(a2[8] + 16LL));
    v10 = (struct _TP_WORK *)*((_QWORD *)v8 + 10);
    if ( v10 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
      CloseThreadpoolWork(v10);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
    }
    *((_QWORD *)v8 + 10) = ThreadpoolWork;
    v11 = a2[11];
    if ( v11 )
    {
      v12 = a2[10];
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 12));
    }
    else
    {
      v12 = 0;
      v11 = 0;
    }
    *(_QWORD *)v8 = v12;
    v13 = (std::_Ref_count_base *)*((_QWORD *)v8 + 1);
    *((_QWORD *)v8 + 1) = v11;
    if ( v13 )
      std::_Ref_count_base::_Decwref(v13);
    *((_OWORD *)v8 + 1) = *(_OWORD *)(a4 + 8);
    std::wstring::operator=(v8 + 32);
    *((_QWORD *)v8 + 8) = a1;
    *((_DWORD *)v8 + 18) = a3;
    v15 = 0;
    SubmitThreadpoolWork(*((PTP_WORK *)v8 + 10));
    std::unique_ptr<PnpManagerBase::ThreadPoolContext>::~unique_ptr<PnpManagerBase::ThreadPoolContext>(&v15);
    std::wstring::_Tidy_deallocate(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x180074e10  mov     [rsp+arg_0], rbx
0x180074e15  push    rbp
0x180074e16  push    rsi
0x180074e17  push    rdi
0x180074e18  push    r12
0x180074e1a  push    r13
0x180074e1c  push    r14
0x180074e1e  push    r15
0x180074e20  sub     rsp, 60h
0x180074e24  mov     rax, cs:__security_cookie
0x180074e2b  xor     rax, rsp
0x180074e2e  mov     [rsp+98h+var_48], rax
0x180074e33  mov     rdi, r9
0x180074e36  mov     ebp, r8d
0x180074e39  mov     rsi, rdx
0x180074e3c  mov     r12, rcx
0x180074e3f  xor     r14d, r14d
0x180074e42  cmp     r8d, 5
0x180074e46  ja      loc_180074F77
0x180074e4c  lea     rdx, dword_180100DC4
0x180074e53  lea     rcx, [rsp+98h+var_68]
0x180074e58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180074e5d  nop
0x180074e5e  cmp     [rdi], r14d
0x180074e61  jnz     short loc_180074E76
0x180074e63  lea     rdx, [rdi+18h]
0x180074e67  test    rdx, rdx
0x180074e6a  jz      short loc_180074E76
0x180074e6c  lea     rcx, [rsp+98h+var_68]
0x180074e71  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180074e76  mov     ecx, 60h ; '`'; Size
0x180074e7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074e80  mov     rbx, rax
0x180074e83  mov     [rsp+98h+var_70], rax
0x180074e88  mov     [rax], r14
0x180074e8b  mov     [rax+8], r14
0x180074e8f  xorps   xmm0, xmm0
0x180074e92  movdqu  xmmword ptr [rax+10h], xmm0
0x180074e97  lea     rdx, dword_180100DC4
0x180074e9e  lea     rcx, [rax+20h]
0x180074ea2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180074ea7  mov     [rbx+40h], r14
0x180074eab  mov     dword ptr [rbx+48h], 0Ah
0x180074eb2  mov     [rbx+50h], r14
0x180074eb6  mov     [rbx+58h], r14d
0x180074eba  mov     [rsp+98h+var_78], rbx
0x180074ebf  mov     r8, [rsi+40h]
0x180074ec3  add     r8, 10h; pcbe
0x180074ec7  mov     rdx, rbx; pv
0x180074eca  lea     rcx, ?NotifyDeviceChangeAsync@PnpManagerBase@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180074ed1  call    cs:__imp_CreateThreadpoolWork
0x180074ed7  mov     r15, rax
0x180074eda  mov     r14, [rbx+50h]
0x180074ede  test    r14, r14
0x180074ee1  jz      short loc_180074F00
0x180074ee3  lea     rcx, [rsp+98h+var_70]; this
0x180074ee8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180074eed  mov     rcx, r14; pwk
0x180074ef0  call    cs:__imp_CloseThreadpoolWork
0x180074ef6  lea     rcx, [rsp+98h+var_70]; this
0x180074efb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180074f00  mov     [rbx+50h], r15
0x180074f04  mov     rax, [rsi+58h]
0x180074f08  test    rax, rax
0x180074f0b  jz      short loc_180074F17
0x180074f0d  mov     rcx, [rsi+50h]
0x180074f11  lock inc dword ptr [rax+0Ch]
0x180074f15  jmp     short loc_180074F1B
0x180074f17  xor     ecx, ecx
0x180074f19  xor     eax, eax
0x180074f1b  mov     [rbx], rcx
0x180074f1e  mov     rcx, [rbx+8]; this
0x180074f22  mov     [rbx+8], rax
0x180074f26  test    rcx, rcx
0x180074f29  jz      short loc_180074F30
0x180074f2b  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180074f30  movups  xmm0, xmmword ptr [rdi+8]
0x180074f34  movdqu  xmmword ptr [rbx+10h], xmm0
0x180074f39  lea     rdx, [rsp+98h+var_68]
0x180074f3e  lea     rcx, [rbx+20h]
0x180074f42  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180074f47  mov     [rbx+40h], r12
0x180074f4b  mov     [rbx+48h], ebp
0x180074f4e  mov     [rsp+98h+var_78], 0
0x180074f57  mov     rcx, [rbx+50h]; pwk
0x180074f5b  call    cs:__imp_SubmitThreadpoolWork
0x180074f61  nop
0x180074f62  lea     rcx, [rsp+98h+var_78]
0x180074f67  call    ??1?$unique_ptr@UThreadPoolContext@PnpManagerBase@@U?$default_delete@UThreadPoolContext@PnpManagerBase@@@std@@@std@@QEAA@XZ; std::unique_ptr<PnpManagerBase::ThreadPoolContext>::~unique_ptr<PnpManagerBase::ThreadPoolContext>(void)
0x180074f6c  nop
0x180074f6d  lea     rcx, [rsp+98h+var_68]
0x180074f72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180074f77  xor     eax, eax
0x180074f79  mov     rcx, [rsp+98h+var_48]
0x180074f7e  xor     rcx, rsp; StackCookie
0x180074f81  call    __security_check_cookie
0x180074f86  mov     rbx, [rsp+98h+arg_0]
0x180074f8e  add     rsp, 60h
0x180074f92  pop     r15
0x180074f94  pop     r14
0x180074f96  pop     r13
0x180074f98  pop     r12
0x180074f9a  pop     rdi
0x180074f9b  pop     rsi
0x180074f9c  pop     rbp
0x180074f9d  retn
```
