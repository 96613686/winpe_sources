# ServiceManager::ServiceManager(void)

- ea: `0x180011d8c`
- end: `0x180012031`
- name: `??0ServiceManager@@AEAA@XZ`
- size: `677`
- prototype: `ServiceManager *__fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002ef0`

## callees

- `0x180003410`
- `0x18000828c`
- `0x18000e5a8`
- `0x180011af8`
- `0x180011b38`
- `0x180011bd4`
- `0x180012038`
- `0x18001e910`
- `0x18001eaec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011e43`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011e43`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180011ead`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180011f08`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180011ead`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180011f08`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180011e36`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180011e36`

## pseudocode

```c
ServiceManager *__fastcall ServiceManager::ServiceManager(ServiceManager *this)
{
  _BYTE v2[16]; // [rsp+30h] [rbp-9h] BYREF
  __int64 (__fastcall **v3)(); // [rsp+40h] [rbp+7h] BYREF
  __int64 v4; // [rsp+48h] [rbp+Fh]
  __int64 (__fastcall ***v5)(); // [rsp+78h] [rbp+3Fh]

  dword_180035680 = 0;
  qword_180036368 = 0;
  byte_180036370 = 0;
  dword_180036374 = 0;
  qword_180036378 = 0;
  qword_180036380 = 0;
  byte_180036388 = 0;
  dword_18003638C = 0;
  byte_180036390 = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>(qword_180036398);
  ServiceManager::sm_svcmgr = &ServiceManager::`vftable'{for `IServiceManager'};
  qword_180035678 = (__int64)&ServiceManager::`vftable'{for `MigrationEngine'};
  qword_1800363B0 = 0;
  InitializeConditionVariable(&ConditionVariable);
  InitializeCriticalSection(&CriticalSection);
  dword_1800363E8 = -2080374773;
  qword_1800363F0 = 0;
  qword_1800363F8 = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>(qword_180036400);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>(qword_180036418);
  xmmword_180036430 = 0;
  PackageManager::PackageManager((PackageManager *)qword_180036460);
  ClientsTracker::ClientsTracker((ClientsTracker *)qword_180036558);
  InitializeCriticalSectionEx(&stru_1800365D8, 0, 0);
  TimerQueue::TimerQueue((TimerQueue *)qword_180036600);
  qword_180036658 = 0;
  qword_180036660 = 0;
  qword_180036668 = 0;
  dword_180036670 = 0;
  byte_180036674 = 0;
  qword_180036678 = 0;
  qword_1800366B8 = 0;
  TimerQueue::TimerQueue((TimerQueue *)qword_1800366C0);
  InitializeCriticalSectionEx(&stru_1800366E0, 0, 0);
  byte_180036708 = 0;
  TimerQueue::TimerQueue((TimerQueue *)qword_180036728);
  dword_180036748 = 0;
  byte_18003674C = 0;
  std::atomic<bool>::atomic<bool>(&word_18003674E);
  qword_180036750 = 0;
  dword_180036758 = 0;
  qword_18003675C = 0;
  qword_180036768 = 0;
  qword_180036770 = 0;
  dword_180036778 = -1;
  qword_180036780 = 0;
  qword_180036440 = 0;
  qword_180036448 = 0;
  qword_180036450 = 0;
  qword_180036458 = 0;
  v5 = 0;
  v3 = off_180026188;
  v4 = *(_QWORD *)lambda_96873d20a43b66a1d08c6deb4cd10618_::_lambda_96873d20a43b66a1d08c6deb4cd10618_(v2);
  v5 = &v3;
  std::function<void (bool,unsigned int)>::operator=(qword_180036620, &v3);
  std::_Func_class<void,bool,unsigned int>::_Tidy(&v3);
  v5 = 0;
  v3 = off_180026158;
  v4 = *(_QWORD *)lambda_96873d20a43b66a1d08c6deb4cd10618_::_lambda_96873d20a43b66a1d08c6deb4cd10618_(v2);
  v5 = &v3;
  std::function<void (bool,unsigned int)>::operator=(qword_180036680, &v3);
  std::_Func_class<void,bool,unsigned int>::_Tidy(&v3);
  return (ServiceManager *)&ServiceManager::sm_svcmgr;
}

```

## disassembly

```asm
0x180011d8c  mov     [rsp-8+arg_0], rbx
0x180011d91  mov     [rsp-8+arg_8], rdi
0x180011d96  push    rbp
0x180011d97  lea     rbp, [rsp-57h]
0x180011d9c  sub     rsp, 90h
0x180011da3  mov     rax, cs:__security_cookie
0x180011daa  xor     rax, rsp
0x180011dad  mov     [rbp+57h+var_10], rax
0x180011db1  mov     rax, [rbp+57h+var_70]
0x180011db5  mov     [rbp+57h+var_70], rax
0x180011db9  lea     rdi, ?sm_svcmgr@ServiceManager@@0V1@A; ServiceManager ServiceManager::sm_svcmgr
0x180011dc0  mov     [rbp+57h+var_70], rdi
0x180011dc4  xor     ebx, ebx
0x180011dc6  mov     cs:dword_180035680, ebx
0x180011dcc  mov     cs:qword_180036368, rbx
0x180011dd3  mov     cs:byte_180036370, bl
0x180011dd9  mov     cs:dword_180036374, ebx
0x180011ddf  mov     cs:qword_180036378, rbx
0x180011de6  mov     cs:qword_180036380, rbx
0x180011ded  mov     cs:byte_180036388, bl
0x180011df3  mov     cs:dword_18003638C, ebx
0x180011df9  mov     cs:byte_180036390, bl
0x180011dff  lea     rcx, qword_180036398
0x180011e06  call    ??$?0AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>(std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>> const &)
0x180011e0b  nop
0x180011e0c  lea     rax, ??_7ServiceManager@@6BIServiceManager@@@; const ServiceManager::`vftable'{for `IServiceManager'}
0x180011e13  mov     cs:?sm_svcmgr@ServiceManager@@0V1@A, rax; ServiceManager ServiceManager::sm_svcmgr
0x180011e1a  lea     rax, ??_7ServiceManager@@6BMigrationEngine@@@; const ServiceManager::`vftable'{for `MigrationEngine'}
0x180011e21  mov     cs:qword_180035678, rax
0x180011e28  mov     cs:qword_1800363B0, rbx
0x180011e2f  lea     rcx, ConditionVariable; ConditionVariable
0x180011e36  call    cs:__imp_InitializeConditionVariable
0x180011e3c  lea     rcx, CriticalSection; lpCriticalSection
0x180011e43  call    cs:__imp_InitializeCriticalSection
0x180011e49  nop
0x180011e4a  mov     cs:dword_1800363E8, 8400000Bh
0x180011e54  mov     cs:qword_1800363F0, rbx
0x180011e5b  mov     cs:qword_1800363F8, rbx
0x180011e62  lea     rcx, qword_180036400
0x180011e69  call    ??$?0AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>(std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>> const &)
0x180011e6e  nop
0x180011e6f  lea     rcx, qword_180036418
0x180011e76  call    ??$?0AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>(std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>> const &)
0x180011e7b  nop
0x180011e7c  xorps   xmm0, xmm0
0x180011e7f  movdqa  cs:xmmword_180036430, xmm0
0x180011e87  lea     rcx, qword_180036460; this
0x180011e8e  call    ??0PackageManager@@QEAA@XZ; PackageManager::PackageManager(void)
0x180011e93  nop
0x180011e94  lea     rcx, qword_180036558; this
0x180011e9b  call    ??0ClientsTracker@@QEAA@XZ; ClientsTracker::ClientsTracker(void)
0x180011ea0  nop
0x180011ea1  xor     r8d, r8d; Flags
0x180011ea4  xor     edx, edx; dwSpinCount
0x180011ea6  lea     rcx, stru_1800365D8; lpCriticalSection
0x180011ead  call    cs:__imp_InitializeCriticalSectionEx
0x180011eb3  lea     rcx, qword_180036600; this
0x180011eba  call    ??0TimerQueue@@QEAA@XZ; TimerQueue::TimerQueue(void)
0x180011ebf  mov     cs:qword_180036658, rbx
0x180011ec6  mov     cs:qword_180036660, rbx
0x180011ecd  mov     cs:qword_180036668, rbx
0x180011ed4  mov     cs:dword_180036670, ebx
0x180011eda  mov     cs:byte_180036674, bl
0x180011ee0  xor     eax, eax
0x180011ee2  mov     cs:qword_180036678, rax
0x180011ee9  mov     cs:qword_1800366B8, rbx
0x180011ef0  lea     rcx, qword_1800366C0; this
0x180011ef7  call    ??0TimerQueue@@QEAA@XZ; TimerQueue::TimerQueue(void)
0x180011efc  xor     r8d, r8d; Flags
0x180011eff  xor     edx, edx; dwSpinCount
0x180011f01  lea     rcx, stru_1800366E0; lpCriticalSection
0x180011f08  call    cs:__imp_InitializeCriticalSectionEx
0x180011f0e  mov     cs:byte_180036708, bl
0x180011f14  lea     rcx, qword_180036728; this
0x180011f1b  call    ??0TimerQueue@@QEAA@XZ; TimerQueue::TimerQueue(void)
0x180011f20  nop
0x180011f21  mov     cs:dword_180036748, ebx
0x180011f27  mov     cs:byte_18003674C, bl
0x180011f2d  lea     rcx, word_18003674E
0x180011f34  call    ??0?$atomic@_N@std@@QEAA@_N@Z; std::atomic<bool>::atomic<bool>(bool)
0x180011f39  mov     cs:qword_180036750, rbx
0x180011f40  mov     cs:dword_180036758, ebx
0x180011f46  xor     eax, eax
0x180011f48  mov     cs:qword_18003675C, rax
0x180011f4f  mov     cs:qword_180036768, rbx
0x180011f56  mov     cs:qword_180036770, rbx
0x180011f5d  mov     cs:dword_180036778, 0FFFFFFFFh
0x180011f67  mov     cs:qword_180036780, rbx
0x180011f6e  mov     cs:qword_180036440, rbx
0x180011f75  mov     cs:qword_180036448, rbx
0x180011f7c  mov     cs:qword_180036450, rbx
0x180011f83  mov     cs:qword_180036458, rbx
0x180011f8a  mov     [rbp+57h+var_18], rbx
0x180011f8e  lea     rax, off_180026188
0x180011f95  mov     [rbp+57h+var_50], rax
0x180011f99  lea     rcx, [rbp+57h+var_60]
0x180011f9d  call    _lambda_96873d20a43b66a1d08c6deb4cd10618____lambda_96873d20a43b66a1d08c6deb4cd10618_
0x180011fa2  mov     rcx, [rax]
0x180011fa5  mov     [rbp+57h+var_48], rcx
0x180011fa9  lea     rax, [rbp+57h+var_50]
0x180011fad  mov     [rbp+57h+var_18], rax
0x180011fb1  lea     rdx, [rbp+57h+var_50]
0x180011fb5  lea     rcx, qword_180036620
0x180011fbc  call    ??4?$function@$$A6AX_NI@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (bool,uint)>::operator=(std::function<void (bool,uint)> const &)
0x180011fc1  nop
0x180011fc2  lea     rcx, [rbp+57h+var_50]
0x180011fc6  call    ?_Tidy@?$_Func_class@X_NI@std@@IEAAXXZ; std::_Func_class<void,bool,uint>::_Tidy(void)
0x180011fcb  mov     [rbp+57h+var_18], rbx
0x180011fcf  lea     rax, off_180026158
0x180011fd6  mov     [rbp+57h+var_50], rax
0x180011fda  lea     rcx, [rbp+57h+var_60]
0x180011fde  call    _lambda_96873d20a43b66a1d08c6deb4cd10618____lambda_96873d20a43b66a1d08c6deb4cd10618_
0x180011fe3  mov     rcx, [rax]
0x180011fe6  mov     [rbp+57h+var_48], rcx
0x180011fea  lea     rcx, [rbp+57h+var_50]
0x180011fee  mov     [rbp+57h+var_18], rcx
0x180011ff2  lea     rdx, [rbp+57h+var_50]
0x180011ff6  lea     rcx, qword_180036680
0x180011ffd  call    ??4?$function@$$A6AX_NI@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (bool,uint)>::operator=(std::function<void (bool,uint)> const &)
0x180012002  nop
0x180012003  lea     rcx, [rbp+57h+var_50]
0x180012007  call    ?_Tidy@?$_Func_class@X_NI@std@@IEAAXXZ; std::_Func_class<void,bool,uint>::_Tidy(void)
0x18001200c  nop
0x18001200d  mov     rax, rdi
0x180012010  mov     rcx, [rbp+57h+var_10]
0x180012014  xor     rcx, rsp; StackCookie
0x180012017  call    __security_check_cookie
0x18001201c  lea     r11, [rsp+90h+var_s0]
0x180012024  mov     rbx, [r11+10h]
0x180012028  mov     rdi, [r11+18h]
0x18001202c  mov     rsp, r11
0x18001202f  pop     rbp
0x180012030  retn
```
