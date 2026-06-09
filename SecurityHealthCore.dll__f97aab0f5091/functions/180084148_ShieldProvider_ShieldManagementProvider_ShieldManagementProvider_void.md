# ShieldProvider::ShieldManagementProvider::~ShieldManagementProvider(void)

- ea: `0x180084148`
- end: `0x1800842bd`
- name: `??1ShieldManagementProvider@ShieldProvider@@EEAA@XZ`
- size: `373`
- prototype: `void __fastcall(ShieldProvider::ShieldManagementProvider *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800842d0`

## callees

- `0x180004710`
- `0x18000f02c`
- `0x18000f094`
- `0x180016d08`
- `0x180017194`
- `0x18001e128`
- `0x180046e44`
- `0x180084048`
- `0x1800840a4`
- `0x180084148`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800de2d8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180084243`
- `KERNEL32!CloseHandle` at `0x180084243`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18008425a`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180084271`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18008425a`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180084271`
- `KERNEL32!UnregisterWaitEx` at `0x180084231`
- `KERNEL32!UnregisterWaitEx` at `0x180084231`

## pseudocode

```c
void __fastcall ShieldProvider::ShieldManagementProvider::~ShieldManagementProvider(
        ShieldProvider::ShieldManagementProvider *this)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rdx
  void *v7; // rdx
  _BYTE v8[16]; // [rsp+20h] [rbp-148h] BYREF
  char v9; // [rsp+30h] [rbp-138h]
  _BYTE v10[240]; // [rsp+40h] [rbp-128h] BYREF

  *(_QWORD *)this = &ShieldProvider::ShieldManagementProvider::`vftable';
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v8,
    (char *)this + 16);
  v2 = *((_QWORD *)this + 27);
  v9 = 1;
  while ( v2 != *((_QWORD *)this + 28) )
  {
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v10,
      0x3E8u,
      L"ShieldProvider::ShieldManagementProvider::~ShieldManagementProvider");
    CommonUtil::AutoRef<IHardwareNotificationsSink3>::operator=(v2 + 8, 0);
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v10);
    v2 += 16;
  }
  v9 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v8);
  v3 = *((_QWORD *)this + 27);
  if ( v3 )
  {
    std::_Destroy_range<std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink>>(v3, *((_QWORD *)this + 28));
    std::_Deallocate<16>(
      *((_QWORD *)this + 27),
      (*((_QWORD *)this + 29) - *((_QWORD *)this + 27)) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 27) = 0;
    *((_QWORD *)this + 28) = 0;
    *((_QWORD *)this + 29) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 24);
  if ( v4 )
    UnregisterWaitEx(v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v5 = (void *)*((_QWORD *)this + 23);
  if ( v5 )
    CloseHandle(v5);
  v6 = (void *)*((_QWORD *)this + 21);
  if ( v6 )
    DeleteTimerQueueTimer(0, v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v7 = (void *)*((_QWORD *)this + 20);
  if ( v7 )
    DeleteTimerQueueTimer(0, v7, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>((char *)this + 144);
  CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>((char *)this + 136);
  std::_Hash<std::_Umap_traits<unsigned long,ShieldProvider::tagShieldConfig,std::_Uhash_compare<unsigned long,stdext::hash_compare<unsigned long,std::equal_to<unsigned long>>,stdext::hash_compare<unsigned long,std::equal_to<unsigned long>>>,std::allocator<std::pair<unsigned long const,ShieldProvider::tagShieldConfig>>,0>>::~_Hash<std::_Umap_traits<unsigned long,ShieldProvider::tagShieldConfig,std::_Uhash_compare<unsigned long,stdext::hash_compare<unsigned long,std::equal_to<unsigned long>>,stdext::hash_compare<unsigned long,std::equal_to<unsigned long>>>,std::allocator<std::pair<unsigned long const,ShieldProvider::tagShieldConfig>>,0>>((char *)this + 56);
  CommonUtil::CMpCriticalSection::~CMpCriticalSection((ShieldProvider::ShieldManagementProvider *)((char *)this + 16));
}

```

## disassembly

```asm
0x180084148  push    rbx
0x18008414a  push    rbp
0x18008414b  push    rsi
0x18008414c  push    rdi
0x18008414d  sub     rsp, 148h
0x180084154  mov     rax, cs:__security_cookie
0x18008415b  xor     rax, rsp
0x18008415e  mov     [rsp+168h+var_38], rax
0x180084166  lea     rax, ??_7ShieldManagementProvider@ShieldProvider@@6B@; const ShieldProvider::ShieldManagementProvider::`vftable'
0x18008416d  mov     rdi, rcx
0x180084170  mov     [rcx], rax
0x180084173  lea     rdx, [rcx+10h]
0x180084177  lea     rcx, [rsp+168h+var_148]
0x18008417c  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180084181  mov     rbx, [rdi+0D8h]
0x180084188  mov     [rsp+168h+var_138], 1
0x18008418d  cmp     rbx, [rdi+0E0h]
0x180084194  jz      short loc_1800841C7
0x180084196  lea     r8, aShieldprovider_40; "ShieldProvider::ShieldManagementProvide"...
0x18008419d  mov     edx, 3E8h; DueTime
0x1800841a2  lea     rcx, [rsp+168h+var_128]; this
0x1800841a7  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800841ac  lea     rcx, [rbx+8]
0x1800841b0  xor     edx, edx
0x1800841b2  call    ??4?$AutoRef@UIHardwareNotificationsSink3@@@CommonUtil@@QEAAAEAV01@PEAUIHardwareNotificationsSink3@@@Z; CommonUtil::AutoRef<IHardwareNotificationsSink3>::operator=(IHardwareNotificationsSink3 *)
0x1800841b7  lea     rcx, [rsp+168h+var_128]; this
0x1800841bc  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800841c1  add     rbx, 10h
0x1800841c5  jmp     short loc_18008418D
0x1800841c7  xor     ebx, ebx
0x1800841c9  lea     rcx, [rsp+168h+var_148]
0x1800841ce  mov     [rsp+168h+var_138], bl
0x1800841d2  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800841d7  mov     rcx, [rdi+0D8h]
0x1800841de  test    rcx, rcx
0x1800841e1  jz      short loc_18008421E
0x1800841e3  mov     rdx, [rdi+0E0h]
0x1800841ea  call    ??$_Destroy_range@V?$allocator@U_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@@std@@@std@@YAXPEAU_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@QEAU1234@AEAV?$allocator@U_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@@0@@Z; std::_Destroy_range<std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink>>(WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink *,WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink * const,std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink> &)
0x1800841ef  mov     rcx, [rdi+0D8h]
0x1800841f6  mov     rdx, [rdi+0E8h]
0x1800841fd  sub     rdx, rcx
0x180084200  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180084204  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180084209  mov     [rdi+0D8h], rbx
0x180084210  mov     [rdi+0E0h], rbx
0x180084217  mov     [rdi+0E8h], rbx
0x18008421e  mov     rcx, [rdi+0C0h]; WaitHandle
0x180084225  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180084229  test    rcx, rcx
0x18008422c  jz      short loc_180084237
0x18008422e  mov     rdx, rbp; CompletionEvent
0x180084231  call    cs:__imp_UnregisterWaitEx
0x180084237  mov     rcx, [rdi+0B8h]; hObject
0x18008423e  test    rcx, rcx
0x180084241  jz      short loc_180084249
0x180084243  call    cs:__imp_CloseHandle
0x180084249  mov     rdx, [rdi+0A8h]; Timer
0x180084250  test    rdx, rdx
0x180084253  jz      short loc_180084260
0x180084255  mov     r8, rbp; CompletionEvent
0x180084258  xor     ecx, ecx; TimerQueue
0x18008425a  call    cs:__imp_DeleteTimerQueueTimer
0x180084260  mov     rdx, [rdi+0A0h]; Timer
0x180084267  test    rdx, rdx
0x18008426a  jz      short loc_180084277
0x18008426c  mov     r8, rbp; CompletionEvent
0x18008426f  xor     ecx, ecx; TimerQueue
0x180084271  call    cs:__imp_DeleteTimerQueueTimer
0x180084277  lea     rcx, [rdi+90h]
0x18008427e  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x180084283  lea     rcx, [rdi+88h]
0x18008428a  call    ??1?$AutoRef@VNWPServiceWaitCancel@ShieldProvider@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(void)
0x18008428f  lea     rcx, [rdi+38h]
0x180084293  call    ??1?$_Hash@V?$_Umap_traits@KUtagShieldConfig@ShieldProvider@@V?$_Uhash_compare@KV?$hash_compare@KU?$equal_to@K@std@@@stdext@@V12@@std@@V?$allocator@U?$pair@$$CBKUtagShieldConfig@ShieldProvider@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<ulong,ShieldProvider::tagShieldConfig,std::_Uhash_compare<ulong,stdext::hash_compare<ulong,std::equal_to<ulong>>,stdext::hash_compare<ulong,std::equal_to<ulong>>>,std::allocator<std::pair<ulong const,ShieldProvider::tagShieldConfig>>,0>>::~_Hash<std::_Umap_traits<ulong,ShieldProvider::tagShieldConfig,std::_Uhash_compare<ulong,stdext::hash_compare<ulong,std::equal_to<ulong>>,stdext::hash_compare<ulong,std::equal_to<ulong>>>,std::allocator<std::pair<ulong const,ShieldProvider::tagShieldConfig>>,0>>(void)
0x180084298  lea     rcx, [rdi+10h]; this
0x18008429c  call    ??1CMpCriticalSection@CommonUtil@@QEAA@XZ; CommonUtil::CMpCriticalSection::~CMpCriticalSection(void)
0x1800842a1  mov     rcx, [rsp+168h+var_38]
0x1800842a9  xor     rcx, rsp; StackCookie
0x1800842ac  call    __security_check_cookie
0x1800842b1  add     rsp, 148h
0x1800842b8  pop     rdi
0x1800842b9  pop     rsi
0x1800842ba  pop     rbp
0x1800842bb  pop     rbx
0x1800842bc  retn
```
