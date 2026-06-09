# PimIMService::CollectWobTickets(ulong,__MIDL___MIDL_itf_unistore_0000_0000_0009 const * const * const)

- ea: `0x180005528`
- end: `0x180005686`
- name: `?CollectWobTickets@PimIMService@@AEAAXKQEBQEBU__MIDL___MIDL_itf_unistore_0000_0000_0009@@@Z`
- size: `350`
- prototype: `void __fastcall(PimIMService *this, __int64, const struct __MIDL___MIDL_itf_unistore_0000_0000_0009 *const *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180008ab0`

## callees

- `0x1800018f4`
- `0x180002da8`
- `0x1800047a4`
- `0x180005528`
- `0x18000c5c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005548`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005548`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000567f`

## string_xrefs

- `0x180005643`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
void __fastcall PimIMService::CollectWobTickets(
        PimIMService *this,
        __int64 a2,
        const struct __MIDL___MIDL_itf_unistore_0000_0000_0009 *const *const a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  _DWORD *v6; // rax
  int v7; // ecx
  __int64 **v8; // rsi
  int v9; // edx
  int v10; // r9d
  __int64 *v11; // r8
  __int64 *v12; // r14
  _QWORD *v13; // rax
  __int64 **v14; // rbx
  __int64 *v15; // rax
  _QWORD *v16; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v17[20]; // [rsp+38h] [rbp-20h]

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 648);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 648));
  v6 = *a3;
  if ( **(_DWORD **)a3 != 0x40000000 && v6[8] && v6[9] )
  {
    v7 = v6[2];
    v8 = (__int64 **)((char *)this + 624);
    v9 = v6[3];
    v10 = v6[4];
    v11 = (__int64 *)*((_QWORD *)this + 78);
    *(_QWORD *)&v17[12] = *((_QWORD *)v6 + 4);
    *(_DWORD *)&v17[8] = v7;
    *(_DWORD *)&v17[4] = v9;
    *(_DWORD *)v17 = v10;
    while ( v11 != (__int64 *)v8 )
    {
      if ( *((_DWORD *)v11 + 6) == v7 && *((_DWORD *)v11 + 5) == v9 && *((_DWORD *)v11 + 4) == v10 )
      {
        *(_QWORD *)&v17[12] = *(__int64 *)((char *)v11 + 28);
        if ( v11 == *v8 )
          goto LABEL_19;
        utl::list<PimIMService::WobTicketInfo,utl::allocator<PimIMService::WobTicketInfo>>::erase(
          (char *)this + 624,
          &v16);
        break;
      }
      v11 = (__int64 *)*v11;
    }
    v12 = *v8;
    v13 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v16 = v13;
    v14 = (__int64 **)v13;
    if ( v13 )
    {
      v16 = 0;
      *((_OWORD *)v13 + 1) = *(_OWORD *)v17;
      *((_DWORD *)v13 + 8) = *(_DWORD *)&v17[16];
      v15 = (__int64 *)v12[1];
      v14[1] = v15;
      *v14 = v12;
      *v15 = (__int64)v14;
      v12[1] = (__int64)v14;
      ++*((_QWORD *)this + 80);
    }
    else
    {
      v14 = 0;
    }
    utl::_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<unsigned long const,SyncPartnerData>>>>::~_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<unsigned long const,SyncPartnerData>>>>(&v16);
    if ( !v14 )
      Log_HREvent(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        3629);
    if ( *((_QWORD *)this + 80) > 0x64u )
      utl::list<PimIMService::WobTicketInfo,utl::allocator<PimIMService::WobTicketInfo>>::erase(
        (char *)this + 624,
        &v16);
  }
LABEL_19:
  LeaveCriticalSection(v3);
}

```

## disassembly

```asm
0x180005528  push    rbp
0x18000552a  push    rbx
0x18000552b  push    rsi
0x18000552c  push    rdi
0x18000552d  push    r14
0x18000552f  push    r15
0x180005531  mov     rbp, rsp
0x180005534  sub     rsp, 58h
0x180005538  lea     rdi, [rcx+288h]
0x18000553f  mov     r15, rcx
0x180005542  mov     rcx, rdi; lpCriticalSection
0x180005545  mov     rbx, r8
0x180005548  call    cs:__imp_EnterCriticalSection
0x18000554e  mov     rax, [rbx]
0x180005551  cmp     dword ptr [rax], 40000000h
0x180005557  jz      loc_180005670
0x18000555d  cmp     dword ptr [rax+20h], 0
0x180005561  jz      loc_180005670
0x180005567  cmp     dword ptr [rax+24h], 0
0x18000556b  jz      loc_180005670
0x180005571  mov     ecx, [rax+8]
0x180005574  lea     rsi, [r15+270h]
0x18000557b  mov     edx, [rax+0Ch]
0x18000557e  mov     r9d, [rax+10h]
0x180005582  mov     rax, [rax+20h]
0x180005586  mov     r8, [rsi]
0x180005589  mov     qword ptr [rbp+var_20], 0
0x180005591  mov     dword ptr [rbp+var_20+8], 0
0x180005598  mov     qword ptr [rbp+var_20+0Ch], rax
0x18000559c  mov     dword ptr [rbp+var_20+8], ecx
0x18000559f  mov     dword ptr [rbp+var_20+4], edx
0x1800055a2  mov     dword ptr [rbp+var_20], r9d
0x1800055a6  cmp     r8, rsi
0x1800055a9  jz      short loc_1800055DF
0x1800055ab  cmp     [r8+18h], ecx
0x1800055af  jnz     short loc_1800055BD
0x1800055b1  cmp     [r8+14h], edx
0x1800055b5  jnz     short loc_1800055BD
0x1800055b7  cmp     [r8+10h], r9d
0x1800055bb  jz      short loc_1800055C2
0x1800055bd  mov     r8, [r8]
0x1800055c0  jmp     short loc_1800055A6
0x1800055c2  mov     rax, [r8+1Ch]
0x1800055c6  mov     qword ptr [rbp+var_20+0Ch], rax
0x1800055ca  cmp     r8, [rsi]
0x1800055cd  jz      loc_180005670
0x1800055d3  lea     rdx, [rbp+var_28]
0x1800055d7  mov     rcx, rsi
0x1800055da  call    ?erase@?$list@UWobTicketInfo@PimIMService@@V?$allocator@UWobTicketInfo@PimIMService@@@utl@@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@UWobTicketInfo@PimIMService@@@utl@@UWobTicketInfo@PimIMService@@@2@V?$_DlistConstIt@U?$_DlistNode@UWobTicketInfo@PimIMService@@@utl@@UWobTicketInfo@PimIMService@@@2@@Z; utl::list<PimIMService::WobTicketInfo,utl::allocator<PimIMService::WobTicketInfo>>::erase(utl::_DlistConstIt<utl::_DlistNode<PimIMService::WobTicketInfo>,PimIMService::WobTicketInfo>)
0x1800055df  mov     r14, [rsi]
0x1800055e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800055e9  mov     ecx, 28h ; '('; unsigned __int64
0x1800055ee  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800055f3  mov     [rbp+var_28], rax
0x1800055f7  mov     rbx, rax
0x1800055fa  test    rax, rax
0x1800055fd  jz      short loc_18000562D
0x1800055ff  movups  xmm0, [rbp+var_20]
0x180005603  mov     [rbp+var_28], 0
0x18000560b  movups  xmmword ptr [rax+10h], xmm0
0x18000560f  mov     eax, [rbp+var_10]
0x180005612  mov     [rbx+20h], eax
0x180005615  mov     rax, [r14+8]
0x180005619  mov     [rbx+8], rax
0x18000561d  mov     [rbx], r14
0x180005620  mov     [rax], rbx
0x180005623  mov     [r14+8], rbx
0x180005627  inc     qword ptr [rsi+10h]
0x18000562b  jmp     short loc_18000562F
0x18000562d  xor     ebx, ebx
0x18000562f  lea     rcx, [rbp+var_28]
0x180005633  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_HashNode@U?$pair@$$CBKUSyncPartnerData@@@utl@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<ulong const,SyncPartnerData>>>>::~_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<ulong const,SyncPartnerData>>>>(void)
0x180005638  test    rbx, rbx
0x18000563b  jnz     short loc_180005656
0x18000563d  mov     r9d, 0E2Dh
0x180005643  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000564a  xor     edx, edx
0x18000564c  mov     ecx, 8007000Eh
0x180005651  call    Log_HREvent
0x180005656  cmp     qword ptr [r15+280h], 64h ; 'd'
0x18000565e  jbe     short loc_180005670
0x180005660  mov     r8, [rsi+8]
0x180005664  lea     rdx, [rbp+var_28]
0x180005668  mov     rcx, rsi
0x18000566b  call    ?erase@?$list@UWobTicketInfo@PimIMService@@V?$allocator@UWobTicketInfo@PimIMService@@@utl@@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@UWobTicketInfo@PimIMService@@@utl@@UWobTicketInfo@PimIMService@@@2@V?$_DlistConstIt@U?$_DlistNode@UWobTicketInfo@PimIMService@@@utl@@UWobTicketInfo@PimIMService@@@2@@Z; utl::list<PimIMService::WobTicketInfo,utl::allocator<PimIMService::WobTicketInfo>>::erase(utl::_DlistConstIt<utl::_DlistNode<PimIMService::WobTicketInfo>,PimIMService::WobTicketInfo>)
0x180005670  mov     rcx, rdi
0x180005673  add     rsp, 58h
0x180005677  pop     r15
0x180005679  pop     r14
0x18000567b  pop     rdi
0x18000567c  pop     rsi
0x18000567d  pop     rbx
0x18000567e  pop     rbp
0x18000567f  jmp     cs:__imp_LeaveCriticalSection
```
