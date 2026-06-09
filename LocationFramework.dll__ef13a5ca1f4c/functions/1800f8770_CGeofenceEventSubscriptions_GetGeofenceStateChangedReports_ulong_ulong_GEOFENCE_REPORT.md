# CGeofenceEventSubscriptions::GetGeofenceStateChangedReports(ulong,ulong *,GEOFENCE_REPORT * *)

- ea: `0x1800f8770`
- end: `0x1800f893f`
- name: `?GetGeofenceStateChangedReports@CGeofenceEventSubscriptions@@UEAAJKPEAKPEAPEAUGEOFENCE_REPORT@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(CGeofenceEventSubscriptions *__hidden this, unsigned int, unsigned int *, struct GEOFENCE_REPORT **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012194`
- `0x18001233c`
- `0x1800123c0`
- `0x18004f898`
- `0x1800646d4`
- `0x180096720`
- `0x1800f7d98`
- `0x1800f8770`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f883a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f883a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f88fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8913`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f88fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8913`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CGeofenceEventSubscriptions::GetGeofenceStateChangedReports(
        CGeofenceEventSubscriptions *this,
        unsigned int a2,
        unsigned int *a3,
        struct GEOFENCE_REPORT **a4)
{
  int v8; // ebx
  __int64 v9; // rbx
  __int64 v10; // rdx
  char *v11; // rcx
  _QWORD *v12; // rax
  void *v13; // r9
  _OWORD *v14; // rdx
  _OWORD *v15; // r8
  __int64 v16; // r10
  __int128 v17; // xmm1
  SIZE_T cb; // [rsp+20h] [rbp-20h] BYREF
  __int64 v20; // [rsp+28h] [rbp-18h] BYREF
  _BYTE v21[16]; // [rsp+30h] [rbp-10h] BYREF

  LODWORD(cb) = a2;
  if ( a3 && a4 )
  {
    *a3 = 0;
    *a4 = 0;
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
      v21,
      (char *)this + 112);
    v8 = CGeofenceEventSubscriptions::CheckPermissions(this, a2);
    if ( v8 < 0 )
    {
LABEL_20:
      ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v21);
      return (unsigned int)v8;
    }
    v20 = 0;
    std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<CGeofenceBackgroundEvent>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<CGeofenceBackgroundEvent>>>,0>>::find(
      (char *)this + 200,
      &v20,
      &cb);
    v9 = v20;
    if ( v20 != *((_QWORD *)this + 25) )
    {
      v10 = *(_QWORD *)(v20 + 48);
      if ( v10 )
      {
        cb = 0;
        if ( (int)ATL::AtlMultiply<unsigned __int64>(&cb, v10, 384) < 0 || cb > 0x7FFFFFFF )
        {
          v11 = 0;
LABEL_10:
          CoTaskMemFree(v11);
          v8 = -2147024882;
          goto LABEL_20;
        }
        v11 = (char *)CoTaskMemAlloc((unsigned int)cb);
        if ( !v11 )
          goto LABEL_10;
        v12 = *(_QWORD **)(v9 + 40);
        v13 = v11;
        while ( 1 )
        {
          v12 = (_QWORD *)*v12;
          if ( v12 == *(_QWORD **)(v9 + 40) )
            break;
          v14 = v11;
          v15 = v12 + 2;
          v16 = 3;
          do
          {
            *v14 = *v15;
            v14[1] = v15[1];
            v14[2] = v15[2];
            v14[3] = v15[3];
            v14[4] = v15[4];
            v14[5] = v15[5];
            v14[6] = v15[6];
            v17 = v15[7];
            v15 += 8;
            v14[7] = v17;
            v14 += 8;
            --v16;
          }
          while ( v16 );
          v11 += 384;
        }
        if ( *(_QWORD *)(v9 + 48) > 0xFFFFFFFF )
        {
          CoTaskMemFree(v13);
          v8 = -2147418113;
          goto LABEL_20;
        }
        *a3 = *(_DWORD *)(v9 + 48);
        *a4 = (struct GEOFENCE_REPORT *)v13;
        std::list<GEOFENCE_REPORT>::clear(v9 + 40);
        CGeofenceEventSubscriptions::CancelEvents(this, a2);
        CoTaskMemFree(0);
      }
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v21);
    return 0;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800f8770  push    rbp
0x1800f8772  push    rbx
0x1800f8773  push    rsi
0x1800f8774  push    rdi
0x1800f8775  push    r12
0x1800f8777  push    r14
0x1800f8779  push    r15
0x1800f877b  mov     rbp, rsp
0x1800f877e  sub     rsp, 40h
0x1800f8782  mov     dword ptr [rbp+cb], edx
0x1800f8785  mov     r14, r9
0x1800f8788  mov     r12, r8
0x1800f878b  mov     r15d, edx
0x1800f878e  mov     rsi, rcx
0x1800f8791  test    r8, r8
0x1800f8794  jz      loc_1800F892B
0x1800f879a  test    r9, r9
0x1800f879d  jz      loc_1800F892B
0x1800f87a3  lea     rdx, [rcx+70h]
0x1800f87a7  mov     dword ptr [r8], 0
0x1800f87ae  lea     rcx, [rbp+var_10]
0x1800f87b2  mov     qword ptr [r9], 0
0x1800f87b9  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800f87be  mov     edx, r15d; unsigned int
0x1800f87c1  mov     rcx, rsi; this
0x1800f87c4  call    ?CheckPermissions@CGeofenceEventSubscriptions@@AEAAJK@Z; CGeofenceEventSubscriptions::CheckPermissions(ulong)
0x1800f87c9  mov     ebx, eax
0x1800f87cb  test    eax, eax
0x1800f87cd  js      loc_1800F891E
0x1800f87d3  lea     rdi, [rsi+0C8h]
0x1800f87da  mov     [rbp+var_18], 0
0x1800f87e2  mov     rcx, rdi
0x1800f87e5  lea     r8, [rbp+cb]
0x1800f87e9  lea     rdx, [rbp+var_18]
0x1800f87ed  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VCGeofenceBackgroundEvent@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VCGeofenceBackgroundEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VCGeofenceBackgroundEvent@@@std@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<CGeofenceBackgroundEvent>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<CGeofenceBackgroundEvent>>>,0>>::find(ulong const &)
0x1800f87f2  mov     rbx, [rbp+var_18]
0x1800f87f6  cmp     rbx, [rdi]
0x1800f87f9  jz      loc_1800F8903
0x1800f87ff  mov     rdx, [rbx+30h]
0x1800f8803  test    rdx, rdx
0x1800f8806  jz      loc_1800F8903
0x1800f880c  mov     edi, 180h
0x1800f8811  mov     [rbp+cb], 0
0x1800f8819  mov     r8d, edi
0x1800f881c  lea     rcx, [rbp+cb]
0x1800f8820  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x1800f8825  test    eax, eax
0x1800f8827  jns     short loc_1800F882D
0x1800f8829  xor     ecx, ecx
0x1800f882b  jmp     short loc_1800F8848
0x1800f882d  cmp     [rbp+cb], 7FFFFFFFh
0x1800f8835  ja      short loc_1800F8829
0x1800f8837  mov     ecx, dword ptr [rbp+cb]; cb
0x1800f883a  call    cs:__imp_CoTaskMemAlloc
0x1800f8840  mov     rcx, rax; pv
0x1800f8843  test    rax, rax
0x1800f8846  jnz     short loc_1800F8858
0x1800f8848  call    cs:__imp_CoTaskMemFree
0x1800f884e  mov     ebx, 8007000Eh
0x1800f8853  jmp     loc_1800F891E
0x1800f8858  mov     rax, [rbx+28h]
0x1800f885c  mov     r9, rcx
0x1800f885f  mov     r11d, 80h
0x1800f8865  mov     rax, [rax]
0x1800f8868  cmp     rax, [rbx+28h]
0x1800f886c  jz      short loc_1800F88D2
0x1800f886e  mov     rdx, rcx
0x1800f8871  lea     r8, [rax+10h]
0x1800f8875  mov     r10d, 3
0x1800f887b  movups  xmm0, xmmword ptr [r8]
0x1800f887f  movups  xmmword ptr [rdx], xmm0
0x1800f8882  movups  xmm1, xmmword ptr [r8+10h]
0x1800f8887  movups  xmmword ptr [rdx+10h], xmm1
0x1800f888b  movups  xmm0, xmmword ptr [r8+20h]
0x1800f8890  movups  xmmword ptr [rdx+20h], xmm0
0x1800f8894  movups  xmm1, xmmword ptr [r8+30h]
0x1800f8899  movups  xmmword ptr [rdx+30h], xmm1
0x1800f889d  movups  xmm0, xmmword ptr [r8+40h]
0x1800f88a2  movups  xmmword ptr [rdx+40h], xmm0
0x1800f88a6  movups  xmm1, xmmword ptr [r8+50h]
0x1800f88ab  movups  xmmword ptr [rdx+50h], xmm1
0x1800f88af  movups  xmm0, xmmword ptr [r8+60h]
0x1800f88b4  movups  xmmword ptr [rdx+60h], xmm0
0x1800f88b8  movups  xmm1, xmmword ptr [r8+70h]
0x1800f88bd  add     r8, r11
0x1800f88c0  movups  xmmword ptr [rdx+70h], xmm1
0x1800f88c4  add     rdx, r11
0x1800f88c7  sub     r10, 1
0x1800f88cb  jnz     short loc_1800F887B
0x1800f88cd  add     rcx, rdi
0x1800f88d0  jmp     short loc_1800F8865
0x1800f88d2  mov     eax, 0FFFFFFFFh
0x1800f88d7  cmp     [rbx+30h], rax
0x1800f88db  ja      short loc_1800F8910
0x1800f88dd  mov     eax, [rbx+30h]
0x1800f88e0  lea     rcx, [rbx+28h]
0x1800f88e4  mov     [r12], eax
0x1800f88e8  mov     [r14], r9
0x1800f88eb  call    ?clear@?$list@UGEOFENCE_REPORT@@V?$allocator@UGEOFENCE_REPORT@@@std@@@std@@QEAAXXZ; std::list<GEOFENCE_REPORT>::clear(void)
0x1800f88f0  mov     edx, r15d
0x1800f88f3  mov     rcx, rsi
0x1800f88f6  call    ?CancelEvents@CGeofenceEventSubscriptions@@AEAAXKW4LOCATION_TRIGGER_TYPE@@@Z; CGeofenceEventSubscriptions::CancelEvents(ulong,LOCATION_TRIGGER_TYPE)
0x1800f88fb  xor     ecx, ecx; pv
0x1800f88fd  call    cs:__imp_CoTaskMemFree
0x1800f8903  lea     rcx, [rbp+var_10]
0x1800f8907  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800f890c  xor     eax, eax
0x1800f890e  jmp     short loc_1800F8930
0x1800f8910  mov     rcx, r9; pv
0x1800f8913  call    cs:__imp_CoTaskMemFree
0x1800f8919  mov     ebx, 8000FFFFh
0x1800f891e  lea     rcx, [rbp+var_10]
0x1800f8922  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800f8927  mov     eax, ebx
0x1800f8929  jmp     short loc_1800F8930
0x1800f892b  mov     eax, 80070057h
0x1800f8930  add     rsp, 40h
0x1800f8934  pop     r15
0x1800f8936  pop     r14
0x1800f8938  pop     r12
0x1800f893a  pop     rdi
0x1800f893b  pop     rsi
0x1800f893c  pop     rbx
0x1800f893d  pop     rbp
0x1800f893e  retn
```
