# BluetoothSignal::Impl::AddDeviceToListAsync(std::shared_ptr<BluetoothSignal::Impl>)

- ea: `0x180033fa0`
- end: `0x180034589`
- name: `?AddDeviceToListAsync@Impl@BluetoothSignal@@SAXV?$shared_ptr@VImpl@BluetoothSignal@@@std@@@Z`
- size: `1513`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180004170`
- `0x180005140`
- `0x18000a7d0`
- `0x18000a7f8`
- `0x18000b5b0`
- `0x18000b5d0`
- `0x18000d258`
- `0x18000d37c`
- `0x180011e1c`
- `0x1800129e8`
- `0x180012b50`
- `0x180017648`
- `0x18001aa2c`
- `0x18001b758`
- `0x18002dd18`
- `0x18002dfc0`
- `0x180032908`
- `0x180032a2c`
- `0x180032b34`
- `0x180033158`
- `0x180033944`
- `0x180033fa0`
- `0x18003495c`
- `0x1800350f8`
- `0x180036590`
- `0x180036ee8`
- `0x180037580`
- `0x180037614`
- `0x1800382d0`
- `0x180041a18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180033ff3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800340ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180034145`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180033ff3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800340ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180034145`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180034218`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180034218`

## string_xrefs

- `0x1800341cf`: `inside`
- `0x1800341c8`: `outside`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall BluetoothSignal::Impl::AddDeviceToListAsync(__int64 a1)
{
  int v2; // r12d
  RTL_SRWLOCK *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // ebx
  RTL_SRWLOCK *v7; // rbx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  char v10; // di
  RTL_SRWLOCK *v11; // rbx
  _QWORD *v12; // rax
  __int64 v13; // r8
  _QWORD *v14; // rax
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // r10
  char IsDeviceInRange; // di
  const char *v19; // r9
  _QWORD *v20; // rax
  RTL_SRWLOCK *v21; // rbx
  int DeviceInfo; // eax
  _QWORD *v23; // rax
  __int64 v24; // r9
  __int64 v25; // r10
  _OWORD *v26; // rax
  _OWORD *v27; // rcx
  __int64 v28; // rdx
  _OWORD *v29; // rcx
  _OWORD *v30; // rax
  __int64 v31; // rdx
  char *v32; // rcx
  _QWORD *v33; // rax
  std::_Ref_count_base *v34; // rcx
  char v35[8]; // [rsp+30h] [rbp-D0h] BYREF
  RTL_SRWLOCK *v36; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v37[2]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hDevice; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE *p_hDevice; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v40; // [rsp+60h] [rbp-A0h] BYREF
  char v41; // [rsp+68h] [rbp-98h]
  _BYTE v42[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v43[24]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v44; // [rsp+98h] [rbp-68h]
  __int64 v45; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v49; // [rsp+E0h] [rbp-20h] BYREF
  char v50; // [rsp+F0h] [rbp-10h] BYREF
  char v51; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v52[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v53[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v54[832]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v55; // [rsp+480h] [rbp+380h]
  char v56; // [rsp+488h] [rbp+388h]
  int v57; // [rsp+489h] [rbp+389h]
  __int16 v58; // [rsp+48Dh] [rbp+38Dh]
  char v59; // [rsp+48Fh] [rbp+38Fh]
  _BYTE v60[832]; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v61[32]; // [rsp+7D0h] [rbp+6D0h] BYREF
  _DWORD v62[136]; // [rsp+7F0h] [rbp+6F0h] BYREF

  v44 = a1;
  v2 = 0;
  v37[0] = 0;
  BluetoothSignal::Spec::Spec((BluetoothSignal::Spec *)v42);
  hDevice = 0;
  v3 = *(RTL_SRWLOCK **)a1;
  AcquireSRWLockShared(*(PSRWLOCK *)a1);
  v36 = v3;
  BluetoothSignal::Spec::operator=(v42, *(_QWORD *)a1 + 8LL);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v36);
  p_hDevice = &hDevice;
  v40 = 0;
  v41 = 1;
  v6 = BthDevnodeOpenInterfaceHandle(v5, v4, &v40);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hDevice);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids,
        (unsigned int)v6);
    goto LABEL_43;
  }
  while ( 1 )
  {
    v37[0] = 0;
    v35[0] = 0x80;
    memset_0(v62, 0, 0x214u);
    v7 = *(RTL_SRWLOCK **)a1;
    AcquireSRWLockShared(*(PSRWLOCK *)a1);
    v36 = v7;
    v8 = *(_QWORD *)(*(_QWORD *)a1 + 104LL);
    if ( v8 == *(_QWORD *)v8 )
      break;
    v37[0] = *(_QWORD *)(*(_QWORD *)v8 + 32LL);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v36);
    if ( (unsigned __int8)std::_Atomic_storage<bool,1>::load(*(_QWORD *)a1 + 128LL)
      && !*(_QWORD *)(*(_QWORD *)a1 + 96LL) )
    {
      v62[0] = 2;
      v9 = std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
             &v45,
             (_QWORD *)a1);
      BluetoothSignal::Impl::PublishWnf(v9, v62);
    }
    std::_Integral_to_string<unsigned short,unsigned __int64>(v61, v37[0]);
    v10 = v43[16];
    v11 = *(RTL_SRWLOCK **)a1;
    AcquireSRWLockShared(*(PSRWLOCK *)a1);
    v36 = v11;
    std::wstring::wstring(v52, v61);
    v12 = std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
            &v46,
            (_QWORD *)a1);
    BluetoothSignal::Impl::FoundInRegistry(v12, v13);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v36);
    v14 = std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
            &v47,
            (_QWORD *)a1);
    LOBYTE(v15) = v10;
    IsDeviceInRange = BluetoothSignal::Impl::IsDeviceInRange(v14, v17, v16, v15, v35);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v19 = "inside";
      if ( !IsDeviceInRange )
        v19 = "outside";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids, v19);
    }
    v20 = std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
            &v48,
            (_QWORD *)a1);
    if ( (unsigned __int8)BluetoothSignal::Impl::ShouldAbort(v20) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids);
      std::wstring::_Tidy_deallocate(v61);
      goto LABEL_43;
    }
    v2 |= 1u;
    v21 = *(RTL_SRWLOCK **)a1;
    AcquireSRWLockExclusive(*(PSRWLOCK *)a1);
    v36 = v21;
    if ( std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::erase(
           *(_QWORD *)a1 + 104LL,
           v37) )
    {
      if ( IsDeviceInRange )
      {
        memset_0(v60, 0, sizeof(v60));
        DeviceInfo = GetDeviceInfo(hDevice);
        if ( DeviceInfo >= 0 )
        {
          std::wstring::wstring(v52, v61);
          v23 = std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
                  &v49,
                  (_QWORD *)a1);
          LOBYTE(v21) = v35[0];
          LOBYTE(v24) = v43[17];
          BluetoothSignal::Impl::WriteToRegistry(v23, v25, (unsigned int)((_DWORD)v21 - 10), v24);
          v26 = v54;
          v27 = v60;
          v28 = 6;
          do
          {
            *v26 = *v27;
            v26[1] = v27[1];
            v26[2] = v27[2];
            v26[3] = v27[3];
            v26[4] = v27[4];
            v26[5] = v27[5];
            v26[6] = v27[6];
            v26[7] = v27[7];
            v26 += 8;
            v27 += 8;
            --v28;
          }
          while ( v28 );
          *v26 = *v27;
          v26[1] = v27[1];
          v26[2] = v27[2];
          v26[3] = v27[3];
          v55 = *(_QWORD *)std::map<std::wstring,RssiValue>::_Try_emplace<std::wstring const &,>(
                             *(_QWORD *)a1 + 72LL,
                             v53,
                             v61)
              + 64LL;
          v56 = (char)v21;
          v57 = 0;
          v58 = 0;
          v59 = 0;
          v29 = (_OWORD *)(*(_QWORD *)std::map<unsigned __int64,DeviceInfo>::_Try_emplace<unsigned __int64 const &,>(
                                        *(_QWORD *)a1 + 88LL,
                                        &p_hDevice,
                                        v37)
                         + 40LL);
          v30 = v54;
          v31 = 6;
          do
          {
            *v29 = *v30;
            v29[1] = v30[1];
            v29[2] = v30[2];
            v29[3] = v30[3];
            v29[4] = v30[4];
            v29[5] = v30[5];
            v29[6] = v30[6];
            v29[7] = v30[7];
            v29 += 8;
            v30 += 8;
            --v31;
          }
          while ( v31 );
          *v29 = *v30;
          v29[1] = v30[1];
          v29[2] = v30[2];
          v29[3] = v30[3];
          v29[4] = v30[4];
          v62[0] = 6;
          v32 = &v50;
          goto LABEL_33;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            65,
            &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids,
            (unsigned int)DeviceInfo);
      }
      else if ( (unsigned __int8)std::_Atomic_storage<bool,1>::load(*(_QWORD *)a1 + 128LL)
             && !*(_QWORD *)(*(_QWORD *)a1 + 96LL) )
      {
        v62[0] = 5;
        v32 = &v51;
LABEL_33:
        v33 = std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
                v32,
                (_QWORD *)a1);
        BluetoothSignal::Impl::PublishWnf(v33, v62);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids, v37[0]);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v36);
    std::wstring::_Tidy_deallocate(v61);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v36);
LABEL_43:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hDevice);
  std::_Tree_val<std::_Tree_simple_types<unsigned __int64>>::_Erase_head<std::allocator<std::_Tree_node<unsigned __int64,void *>>>(
    v43,
    v43);
  v34 = *(std::_Ref_count_base **)(a1 + 8);
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
}

```

## disassembly

```asm
0x180033fa0  push    rbp
0x180033fa2  push    rbx
0x180033fa3  push    rsi
0x180033fa4  push    rdi
0x180033fa5  push    r12
0x180033fa7  push    r15
0x180033fa9  lea     rbp, [rsp-928h]
0x180033fb1  sub     rsp, 0A28h
0x180033fb8  mov     rax, cs:__security_cookie
0x180033fbf  xor     rax, rsp
0x180033fc2  mov     [rbp+950h+var_40], rax
0x180033fc9  mov     rsi, rcx
0x180033fcc  mov     [rbp+950h+var_9B8], rcx
0x180033fd0  xor     r12d, r12d
0x180033fd3  mov     dword ptr [rsp+0A50h+var_A10], r12d
0x180033fd8  mov     [rsp+0A50h+var_A10], r12
0x180033fdd  lea     rcx, [rsp+0A50h+var_9E0]; this
0x180033fe2  call    ??0Spec@BluetoothSignal@@QEAA@XZ; BluetoothSignal::Spec::Spec(void)
0x180033fe7  nop
0x180033fe8  mov     [rsp+0A50h+hDevice], r12
0x180033fed  mov     rbx, [rsi]
0x180033ff0  mov     rcx, rbx; SRWLock
0x180033ff3  call    cs:__imp_AcquireSRWLockShared
0x180033ff9  mov     [rsp+0A50h+var_A18], rbx
0x180033ffe  mov     rdx, [rsi]
0x180034001  add     rdx, 8
0x180034005  lea     rcx, [rsp+0A50h+var_9E0]
0x18003400a  call    ??4Spec@BluetoothSignal@@QEAAAEAU01@AEBU01@@Z; BluetoothSignal::Spec::operator=(BluetoothSignal::Spec const &)
0x18003400f  nop
0x180034010  lea     rcx, [rsp+0A50h+var_A18]
0x180034015  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003401a  lea     rax, [rsp+0A50h+hDevice]
0x18003401f  mov     [rsp+0A50h+var_9F8], rax
0x180034024  mov     [rsp+0A50h+var_9F0], r12
0x180034029  mov     [rsp+0A50h+var_9E8], 1
0x18003402e  lea     r8, [rsp+0A50h+var_9F0]
0x180034033  call    BthDevnodeOpenInterfaceHandle
0x180034038  mov     ebx, eax
0x18003403a  lea     rcx, [rsp+0A50h+var_9F8]
0x18003403f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180034044  test    ebx, ebx
0x180034046  jns     short loc_180034086
0x180034048  lea     r15, WPP_GLOBAL_Control
0x18003404f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034056  cmp     rcx, r15
0x180034059  jz      loc_180034543
0x18003405f  test    byte ptr [rcx+1Ch], 4
0x180034063  jz      loc_180034543
0x180034069  lea     edx, [r12+3Ch]
0x18003406e  mov     r9d, ebx
0x180034071  lea     r8, WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids
0x180034078  mov     rcx, [rcx+10h]
0x18003407c  call    WPP_SF_d
0x180034081  jmp     loc_180034543
0x180034086  lea     r15, WPP_GLOBAL_Control
0x18003408d  mov     edi, 80h
0x180034092  mov     [rsp+0A50h+var_A10], 0
0x18003409b  mov     [rsp+0A50h+var_A20], 80h
0x1800340a0  xor     edx, edx; Val
0x1800340a2  mov     r8d, 214h; Size
0x1800340a8  lea     rcx, [rbp+950h+var_260]; void *
0x1800340af  call    memset_0
0x1800340b4  mov     rbx, [rsi]
0x1800340b7  mov     rcx, rbx; SRWLock
0x1800340ba  call    cs:__imp_AcquireSRWLockShared
0x1800340c0  mov     [rsp+0A50h+var_A18], rbx
0x1800340c5  mov     rax, [rsi]
0x1800340c8  mov     rcx, [rax+68h]
0x1800340cc  mov     rax, [rcx]
0x1800340cf  cmp     rcx, rax
0x1800340d2  jz      loc_180034511
0x1800340d8  mov     rax, [rax+20h]
0x1800340dc  mov     [rsp+0A50h+var_A10], rax
0x1800340e1  lea     rcx, [rsp+0A50h+var_A18]
0x1800340e6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800340eb  mov     rcx, [rsi]
0x1800340ee  add     rcx, rdi
0x1800340f1  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x1800340f6  test    al, al
0x1800340f8  jz      short loc_180034129
0x1800340fa  mov     rax, [rsi]
0x1800340fd  cmp     qword ptr [rax+60h], 0
0x180034102  ja      short loc_180034129
0x180034104  mov     [rbp+950h+var_260], 2
0x18003410e  mov     rdx, rsi
0x180034111  lea     rcx, [rbp+950h+var_9B0]
0x180034115  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18003411a  lea     rdx, [rbp+950h+var_260]
0x180034121  mov     rcx, rax
0x180034124  call    ?PublishWnf@Impl@BluetoothSignal@@SAXV?$shared_ptr@VImpl@BluetoothSignal@@@std@@PEAUNA_SIGNAL_TYPE_INFO_BLUETOOTH_STATUS_AND_DEVICE_INFO@@@Z; BluetoothSignal::Impl::PublishWnf(std::shared_ptr<BluetoothSignal::Impl>,NA_SIGNAL_TYPE_INFO_BLUETOOTH_STATUS_AND_DEVICE_INFO *)
0x180034129  mov     rdx, [rsp+0A50h+var_A10]
0x18003412e  lea     rcx, [rbp+950h+var_280]
0x180034135  call    ??$_Integral_to_string@G_K@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_K@Z; std::_Integral_to_string<ushort,unsigned __int64>(unsigned __int64)
0x18003413a  nop
0x18003413b  mov     dil, [rbp+950h+var_9C0]
0x18003413f  mov     rbx, [rsi]
0x180034142  mov     rcx, rbx; SRWLock
0x180034145  call    cs:__imp_AcquireSRWLockShared
0x18003414b  mov     [rsp+0A50h+var_A18], rbx
0x180034150  lea     rdx, [rbp+950h+var_280]
0x180034157  lea     rcx, [rbp+950h+var_940]
0x18003415b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034160  mov     r8, rax
0x180034163  mov     rdx, rsi
0x180034166  lea     rcx, [rbp+950h+var_9A0]
0x18003416a  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18003416f  mov     rdx, r8
0x180034172  mov     rcx, rax
0x180034175  call    ?FoundInRegistry@Impl@BluetoothSignal@@CA_NV?$shared_ptr@VImpl@BluetoothSignal@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; BluetoothSignal::Impl::FoundInRegistry(std::shared_ptr<BluetoothSignal::Impl>,std::wstring)
0x18003417a  nop
0x18003417b  lea     rcx, [rsp+0A50h+var_A18]
0x180034180  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180034185  mov     r8, [rsp+0A50h+var_A10]
0x18003418a  mov     r10, [rsp+0A50h+hDevice]
0x18003418f  mov     rdx, rsi
0x180034192  lea     rcx, [rbp+950h+var_990]
0x180034196  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18003419b  lea     rcx, [rsp+0A50h+var_A20]
0x1800341a0  mov     [rsp+0A50h+var_A30], rcx
0x1800341a5  mov     r9b, dil
0x1800341a8  mov     rdx, r10
0x1800341ab  mov     rcx, rax
0x1800341ae  call    ?IsDeviceInRange@Impl@BluetoothSignal@@SA_NV?$shared_ptr@VImpl@BluetoothSignal@@@std@@PEAX_KCPEAC@Z; BluetoothSignal::Impl::IsDeviceInRange(std::shared_ptr<BluetoothSignal::Impl>,void *,unsigned __int64,signed char,signed char *)
0x1800341b3  mov     dil, al
0x1800341b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800341bd  cmp     rcx, r15
0x1800341c0  jz      short loc_1800341F2
0x1800341c2  test    byte ptr [rcx+1Ch], 4
0x1800341c6  jz      short loc_1800341F2
0x1800341c8  lea     rax, aOutside; "outside"
0x1800341cf  lea     r9, aInside; "inside"
0x1800341d6  test    dil, dil
0x1800341d9  cmovz   r9, rax
0x1800341dd  mov     edx, 3Eh ; '>'
0x1800341e2  lea     r8, WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids
0x1800341e9  mov     rcx, [rcx+10h]
0x1800341ed  call    WPP_SF_s
0x1800341f2  mov     rdx, rsi
0x1800341f5  lea     rcx, [rbp+950h+var_980]
0x1800341f9  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x1800341fe  mov     rcx, rax
0x180034201  call    ?ShouldAbort@Impl@BluetoothSignal@@SA_NV?$shared_ptr@VImpl@BluetoothSignal@@@std@@@Z; BluetoothSignal::Impl::ShouldAbort(std::shared_ptr<BluetoothSignal::Impl>)
0x180034206  test    al, al
0x180034208  jnz     loc_1800344DB
0x18003420e  or      r12d, 1
0x180034212  mov     rbx, [rsi]
0x180034215  mov     rcx, rbx; SRWLock
0x180034218  call    cs:__imp_AcquireSRWLockExclusive
0x18003421e  mov     [rsp+0A50h+var_A18], rbx
0x180034223  mov     rcx, [rsi]
0x180034226  add     rcx, 68h ; 'h'
0x18003422a  lea     rdx, [rsp+0A50h+var_A10]
0x18003422f  call    ?erase@?$_Tree@V?$_Tset_traits@_KU?$less@_K@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA_KAEB_K@Z; std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::erase(unsigned __int64 const &)
0x180034234  test    rax, rax
0x180034237  jnz     short loc_180034280
0x180034239  mov     rcx, cs:WPP_GLOBAL_Control
0x180034240  cmp     rcx, r15
0x180034243  jz      short loc_180034264
0x180034245  test    byte ptr [rcx+1Ch], 4
0x180034249  jz      short loc_180034264
0x18003424b  lea     edx, [rax+40h]
0x18003424e  mov     r9, [rsp+0A50h+var_A10]
0x180034253  lea     r8, WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids
0x18003425a  mov     rcx, [rcx+10h]
0x18003425e  call    WPP_SF_i
0x180034263  nop
0x180034264  lea     rcx, [rsp+0A50h+var_A18]
0x180034269  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003426e  nop
0x18003426f  lea     rcx, [rbp+950h+var_280]
0x180034276  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003427b  jmp     loc_18003408D
0x180034280  test    dil, dil
0x180034283  jz      loc_18003447B
0x180034289  xor     edx, edx; Val
0x18003428b  mov     r8d, 340h; Size
0x180034291  lea     rcx, [rbp+950h+var_5C0]; void *
0x180034298  call    memset_0
0x18003429d  lea     r8, [rbp+950h+var_5C0]
0x1800342a4  mov     rdx, [rsp+0A50h+var_A10]
0x1800342a9  mov     rcx, [rsp+0A50h+hDevice]; hDevice
0x1800342ae  call    GetDeviceInfo
0x1800342b3  test    eax, eax
0x1800342b5  jns     short loc_1800342E3
0x1800342b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342be  cmp     rcx, r15
0x1800342c1  jz      short loc_180034264
0x1800342c3  test    byte ptr [rcx+1Ch], 1
0x1800342c7  jz      short loc_180034264
0x1800342c9  mov     edx, 41h ; 'A'
0x1800342ce  mov     r9d, eax
0x1800342d1  lea     r8, WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids
0x1800342d8  mov     rcx, [rcx+10h]
0x1800342dc  call    WPP_SF_d
0x1800342e1  jmp     short loc_180034264
0x1800342e3  lea     rdx, [rbp+950h+var_280]
0x1800342ea  lea     rcx, [rbp+950h+var_940]
0x1800342ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800342f3  mov     r10, rax
0x1800342f6  mov     rdx, rsi
0x1800342f9  lea     rcx, [rbp+950h+var_970]
0x1800342fd  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x180034302  mov     bl, [rsp+0A50h+var_A20]
0x180034306  lea     r8d, [rbx-0Ah]
0x18003430a  mov     r9b, [rbp+950h+var_9BF]
0x18003430e  mov     rdx, r10
0x180034311  mov     rcx, rax
0x180034314  call    ?WriteToRegistry@Impl@BluetoothSignal@@CAXV?$shared_ptr@VImpl@BluetoothSignal@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@CC@Z; BluetoothSignal::Impl::WriteToRegistry(std::shared_ptr<BluetoothSignal::Impl>,std::wstring,signed char,signed char)
0x180034319  lea     rax, [rbp+950h+var_910]
0x18003431d  lea     rcx, [rbp+950h+var_5C0]
0x180034324  mov     edx, 6
0x180034329  lea     edi, [rdx+7Ah]
0x18003432c  movups  xmm0, xmmword ptr [rcx]
0x18003432f  movups  xmmword ptr [rax], xmm0
0x180034332  movups  xmm1, xmmword ptr [rcx+10h]
0x180034336  movups  xmmword ptr [rax+10h], xmm1
0x18003433a  movups  xmm0, xmmword ptr [rcx+20h]
0x18003433e  movups  xmmword ptr [rax+20h], xmm0
0x180034342  movups  xmm1, xmmword ptr [rcx+30h]
0x180034346  movups  xmmword ptr [rax+30h], xmm1
0x18003434a  movups  xmm0, xmmword ptr [rcx+40h]
0x18003434e  movups  xmmword ptr [rax+40h], xmm0
0x180034352  movups  xmm1, xmmword ptr [rcx+50h]
0x180034356  movups  xmmword ptr [rax+50h], xmm1
0x18003435a  movups  xmm0, xmmword ptr [rcx+60h]
0x18003435e  movups  xmmword ptr [rax+60h], xmm0
0x180034362  movups  xmm1, xmmword ptr [rcx+70h]
0x180034366  movups  xmmword ptr [rax+70h], xmm1
0x18003436a  add     rax, rdi
0x18003436d  add     rcx, rdi
0x180034370  sub     rdx, 1
0x180034374  jnz     short loc_18003432C
0x180034376  movups  xmm0, xmmword ptr [rcx]
0x180034379  movups  xmmword ptr [rax], xmm0
0x18003437c  movups  xmm1, xmmword ptr [rcx+10h]
0x180034380  movups  xmmword ptr [rax+10h], xmm1
0x180034384  movups  xmm0, xmmword ptr [rcx+20h]
0x180034388  movups  xmmword ptr [rax+20h], xmm0
0x18003438c  movups  xmm1, xmmword ptr [rcx+30h]
0x180034390  movups  xmmword ptr [rax+30h], xmm1
0x180034394  mov     rcx, [rsi]
0x180034397  add     rcx, 48h ; 'H'
0x18003439b  lea     r8, [rbp+950h+var_280]
0x1800343a2  lea     rdx, [rbp+950h+var_920]
0x1800343a6  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URssiValue@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URssiValue@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URssiValue@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,RssiValue>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800343ab  mov     rcx, [rax]
0x1800343ae  add     rcx, 40h ; '@'
0x1800343b2  mov     [rbp+950h+var_5D0], rcx
0x1800343b9  mov     [rbp+950h+var_5C8], bl
0x1800343bf  xor     eax, eax
0x1800343c1  mov     [rbp+950h+var_5C7], eax
0x1800343c7  mov     [rbp+950h+var_5C3], ax
0x1800343ce  mov     [rbp+950h+var_5C1], al
0x1800343d4  mov     rcx, [rsi]
0x1800343d7  add     rcx, 58h ; 'X'
0x1800343db  lea     r8, [rsp+0A50h+var_A10]
0x1800343e0  lea     rdx, [rsp+0A50h+var_9F8]
0x1800343e5  call    ??$_Try_emplace@AEB_K$$V@?$map@_KUDeviceInfo@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUDeviceInfo@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KUDeviceInfo@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::map<unsigned __int64,DeviceInfo>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x1800343ea  mov     rcx, [rax]
0x1800343ed  add     rcx, 28h ; '('
0x1800343f1  lea     rax, [rbp+950h+var_910]
0x1800343f5  mov     r8d, 6
0x1800343fb  mov     edx, r8d
0x1800343fe  movups  xmm0, xmmword ptr [rax]
0x180034401  movups  xmmword ptr [rcx], xmm0
0x180034404  movups  xmm1, xmmword ptr [rax+10h]
0x180034408  movups  xmmword ptr [rcx+10h], xmm1
0x18003440c  movups  xmm0, xmmword ptr [rax+20h]
0x180034410  movups  xmmword ptr [rcx+20h], xmm0
0x180034414  movups  xmm1, xmmword ptr [rax+30h]
0x180034418  movups  xmmword ptr [rcx+30h], xmm1
0x18003441c  movups  xmm0, xmmword ptr [rax+40h]
0x180034420  movups  xmmword ptr [rcx+40h], xmm0
0x180034424  movups  xmm1, xmmword ptr [rax+50h]
0x180034428  movups  xmmword ptr [rcx+50h], xmm1
0x18003442c  movups  xmm0, xmmword ptr [rax+60h]
0x180034430  movups  xmmword ptr [rcx+60h], xmm0
0x180034434  movups  xmm1, xmmword ptr [rax+70h]
0x180034438  movups  xmmword ptr [rcx+70h], xmm1
0x18003443c  add     rcx, rdi
0x18003443f  add     rax, rdi
0x180034442  sub     rdx, 1
0x180034446  jnz     short loc_1800343FE
0x180034448  movups  xmm0, xmmword ptr [rax]
0x18003444b  movups  xmmword ptr [rcx], xmm0
0x18003444e  movups  xmm1, xmmword ptr [rax+10h]
0x180034452  movups  xmmword ptr [rcx+10h], xmm1
0x180034456  movups  xmm0, xmmword ptr [rax+20h]
0x18003445a  movups  xmmword ptr [rcx+20h], xmm0
0x18003445e  movups  xmm1, xmmword ptr [rax+30h]
0x180034462  movups  xmmword ptr [rcx+30h], xmm1
0x180034466  movups  xmm0, xmmword ptr [rax+40h]
0x18003446a  movups  xmmword ptr [rcx+40h], xmm0
0x18003446e  mov     [rbp+950h+var_260], r8d
0x180034475  lea     rcx, [rbp+950h+var_960]
0x180034479  jmp     short loc_1800344A7
0x18003447b  mov     rcx, [rsi]
0x18003447e  mov     edi, 80h
0x180034483  add     rcx, rdi
0x180034486  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
  ... truncated ...
```
