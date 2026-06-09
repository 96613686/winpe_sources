# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::ShouldPairDeviceFromMonitorEvent(_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT const *)

- ea: `0x18002bea0`
- end: `0x18002c133`
- name: `?ShouldPairDeviceFromMonitorEvent@BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAPEAVBthLEPrepairingDevice@2345@PEBU_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT@@@Z`
- size: `659`
- prototype: `struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor *__hidden this, const struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002a2f0`

## callees

- `0x180001b60`
- `0x1800105d4`
- `0x180011194`
- `0x18001140c`
- `0x18002b428`
- `0x18002ba40`
- `0x18002bc50`
- `0x18002bea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bec3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bec3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bff3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c113`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bff3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c113`

## pseudocode

```c
struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::ShouldPairDeviceFromMonitorEvent(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor *this,
        const struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *DeviceFromMonitorEvent; // rax
  struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *v5; // r13
  unsigned __int64 v6; // r14
  __int64 v7; // rdx
  __int64 v8; // r8
  char v9; // di
  int v10; // edx
  int v11; // r8d
  char *v13; // r13
  char v14; // dl
  __int64 *v15; // rcx
  __int64 *v16; // rbx
  __int64 *v17; // rax
  __int64 **v18; // rcx
  __int64 *v19; // rdx
  __int64 *i; // rax
  __int64 *j; // rcx
  void *v22; // rax
  int v23; // [rsp+20h] [rbp-88h]
  int v24; // [rsp+28h] [rbp-80h]
  _QWORD v25[11]; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v26; // [rsp+B0h] [rbp+8h] BYREF
  struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *v27; // [rsp+B8h] [rbp+10h] BYREF

  v27 = a2;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  DeviceFromMonitorEvent = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::GetDeviceFromMonitorEvent(
                             this,
                             v27);
  v5 = DeviceFromMonitorEvent;
  if ( DeviceFromMonitorEvent )
  {
    v6 = *((_QWORD *)DeviceFromMonitorEvent + 6);
    if ( *((_BYTE *)v27 + 9) )
    {
      v26 = *((_QWORD *)DeviceFromMonitorEvent + 6);
      if ( !Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::IsDeviceInRangeLocked(
              this,
              &v26) )
      {
        v9 = 1;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (LOBYTE(v7) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
        {
          LOBYTE(v7) = 0;
        }
        LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, *((_QWORD *)WPP_GLOBAL_Control + 5));
        v25[1] = this;
        v25[0] = &v27;
        if ( (int)wil::ResultFromException__lambda_b99a1f79a85fe3d31a3fa687ff12843c___(v25, v7, v8) < 0 )
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            v9 = 0;
          if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v10) = v9;
            LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v10,
              v11,
              *((_QWORD *)WPP_GLOBAL_Control + 5),
              v23,
              v24,
              14,
              (__int64)WPP_b1c3b0ca35523905939af17a791078e1_Traceguids);
          }
        }
      }
      if ( v2 )
        LeaveCriticalSection(v2);
      return v5;
    }
    v13 = (char *)this + 56;
    v14 = 0;
    v15 = (__int64 *)*((_QWORD *)this + 7);
    v16 = v15;
    v17 = (__int64 *)v15[1];
    while ( !*((_BYTE *)v17 + 25) )
    {
      if ( v17[4] >= v6 )
      {
        v16 = v17;
        v17 = (__int64 *)*v17;
      }
      else
      {
        v17 = (__int64 *)v17[2];
      }
    }
    if ( !*((_BYTE *)v16 + 25) && v6 >= v16[4] && v16 != v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        v14 = 1;
      if ( v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_si(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      operator delete((void *)v16[5], (const struct std::nothrow_t *)1);
      v18 = (__int64 **)v16[2];
      v19 = v16;
      if ( *((_BYTE *)v18 + 25) )
      {
        for ( i = (__int64 *)v16[1]; !*((_BYTE *)i + 25) && v16 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v16 = i;
      }
      else
      {
        for ( j = *v18; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          ;
      }
      v22 = (void *)std::_Tree_val<std::_Tree_simple_types<Microsoft::Bluetooth::Foundation::AsyncObjectBase *>>::_Extract(
                      v13,
                      v19);
      operator delete(v22, (const struct std::nothrow_t *)0x30);
    }
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x18002bea0  mov     [rsp+arg_10], rbx
0x18002bea5  mov     [rsp+arg_8], rdx
0x18002beaa  push    rbp
0x18002beab  push    rsi
0x18002beac  push    rdi
0x18002bead  push    r12
0x18002beaf  push    r13
0x18002beb1  push    r14
0x18002beb3  push    r15
0x18002beb5  sub     rsp, 70h
0x18002beb9  lea     rbp, [rcx+10h]
0x18002bebd  mov     rbx, rcx
0x18002bec0  mov     rcx, rbp; lpCriticalSection
0x18002bec3  call    cs:__imp_EnterCriticalSection
0x18002bec9  mov     rdx, [rsp+0A8h+arg_8]; struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *
0x18002bed1  mov     rcx, rbx; this
0x18002bed4  call    ?GetDeviceFromMonitorEvent@BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@IEAAPEAVBthLEPrepairingDevice@2345@PEBU_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT@@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::GetDeviceFromMonitorEvent(_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT const *)
0x18002bed9  xor     r15d, r15d
0x18002bedc  mov     r13, rax
0x18002bedf  test    rax, rax
0x18002bee2  jz      loc_18002C10B
0x18002bee8  mov     rdx, [rsp+0A8h+arg_8]
0x18002bef0  mov     r14, [rax+30h]
0x18002bef4  cmp     [rdx+9], r15b
0x18002bef8  jz      loc_18002C001
0x18002befe  lea     rdx, [rsp+0A8h+arg_0]; unsigned __int64 *
0x18002bf06  mov     [rsp+0A8h+arg_0], r14
0x18002bf0e  mov     rcx, rbx; this
0x18002bf11  call    ?IsDeviceInRangeLocked@BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@IEAA_NAEB_K@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::IsDeviceInRangeLocked(unsigned __int64 const &)
0x18002bf16  test    al, al
0x18002bf18  jnz     loc_18002BFEB
0x18002bf1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf25  lea     rsi, WPP_GLOBAL_Control
0x18002bf2c  lea     edi, [r15+1]
0x18002bf30  cmp     rcx, rsi
0x18002bf33  jz      short loc_18002BF3E
0x18002bf35  cmp     byte ptr [rcx+19h], 4
0x18002bf39  mov     dl, dil
0x18002bf3c  jnb     short loc_18002BF41
0x18002bf3e  mov     dl, r15b
0x18002bf41  lea     r15, WPP_RECORDER_INITIALIZED
0x18002bf48  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002bf4f  lea     r12, WPP_b1c3b0ca35523905939af17a791078e1_Traceguids
0x18002bf56  setnz   r8b
0x18002bf5a  test    dl, dl
0x18002bf5c  jnz     short loc_18002BF63
0x18002bf5e  test    r8b, r8b
0x18002bf61  jz      short loc_18002BF81
0x18002bf63  mov     r9, [rcx+28h]
0x18002bf67  mov     rcx, [rcx+10h]
0x18002bf6b  mov     [rsp+0A8h+var_60], r14
0x18002bf70  mov     [rsp+0A8h+var_70], r12
0x18002bf75  mov     [rsp+0A8h+var_78], 0Dh
0x18002bf7c  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002bf81  lea     rax, [rsp+0A8h+arg_8]
0x18002bf89  mov     [rsp+0A8h+var_50], rbx
0x18002bf8e  lea     rcx, [rsp+0A8h+var_58]
0x18002bf93  mov     [rsp+0A8h+var_58], rax
0x18002bf98  call    wil__ResultFromException__lambda_b99a1f79a85fe3d31a3fa687ff12843c___
0x18002bf9d  test    eax, eax
0x18002bf9f  jns     short loc_18002BFEB
0x18002bfa1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfa8  cmp     rcx, rsi
0x18002bfab  jz      short loc_18002BFB3
0x18002bfad  cmp     byte ptr [rcx+19h], 2
0x18002bfb1  jnb     short loc_18002BFB6
0x18002bfb3  xor     dil, dil
0x18002bfb6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002bfbd  setnz   r8b
0x18002bfc1  test    dil, dil
0x18002bfc4  jnz     short loc_18002BFCB
0x18002bfc6  test    r8b, r8b
0x18002bfc9  jz      short loc_18002BFEB
0x18002bfcb  mov     r9, [rcx+28h]
0x18002bfcf  mov     dl, dil
0x18002bfd2  mov     rcx, [rcx+10h]
0x18002bfd6  mov     dword ptr [rsp+0A8h+var_60], eax
0x18002bfda  mov     [rsp+0A8h+var_70], r12
0x18002bfdf  mov     [rsp+0A8h+var_78], 0Eh
0x18002bfe6  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002bfeb  test    rbp, rbp
0x18002bfee  jz      short loc_18002BFF9
0x18002bff0  mov     rcx, rbp; lpCriticalSection
0x18002bff3  call    cs:__imp_LeaveCriticalSection
0x18002bff9  mov     rax, r13
0x18002bffc  jmp     loc_18002C11B
0x18002c001  lea     r13, [rbx+38h]
0x18002c005  xor     edx, edx
0x18002c007  mov     rcx, [r13+0]
0x18002c00b  mov     rbx, rcx
0x18002c00e  mov     rax, [rcx+8]
0x18002c012  jmp     short loc_18002C026
0x18002c014  cmp     [rax+20h], r14
0x18002c018  jnb     short loc_18002C020
0x18002c01a  mov     rax, [rax+10h]
0x18002c01e  jmp     short loc_18002C026
0x18002c020  mov     rbx, rax
0x18002c023  mov     rax, [rax]
0x18002c026  cmp     [rax+19h], r15b
0x18002c02a  jz      short loc_18002C014
0x18002c02c  cmp     [rbx+19h], r15b
0x18002c030  jnz     loc_18002C10B
0x18002c036  cmp     r14, [rbx+20h]
0x18002c03a  jb      loc_18002C10B
0x18002c040  cmp     rbx, rcx
0x18002c043  jz      loc_18002C10B
0x18002c049  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c050  lea     rsi, WPP_GLOBAL_Control
0x18002c057  mov     edi, 1
0x18002c05c  cmp     rcx, rsi
0x18002c05f  jz      short loc_18002C06A
0x18002c061  cmp     byte ptr [rcx+19h], 4
0x18002c065  jb      short loc_18002C06A
0x18002c067  mov     dl, dil
0x18002c06a  lea     r15, WPP_RECORDER_INITIALIZED
0x18002c071  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002c078  setnz   r8b
0x18002c07c  xor     r15d, r15d
0x18002c07f  test    dl, dl
0x18002c081  jnz     short loc_18002C088
0x18002c083  test    r8b, r8b
0x18002c086  jz      short loc_18002C0AD
0x18002c088  mov     r9, [rcx+28h]
0x18002c08c  lea     r12, WPP_b1c3b0ca35523905939af17a791078e1_Traceguids
0x18002c093  mov     rcx, [rcx+10h]
0x18002c097  mov     [rsp+0A8h+var_60], r14
0x18002c09c  mov     [rsp+0A8h+var_70], r12
0x18002c0a1  mov     [rsp+0A8h+var_78], 0Fh
0x18002c0a8  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002c0ad  mov     rcx, [rbx+28h]; void *
0x18002c0b1  mov     rdx, rdi; struct std::nothrow_t *
0x18002c0b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c0b9  mov     rcx, [rbx+10h]
0x18002c0bd  mov     rdx, rbx
0x18002c0c0  cmp     [rcx+19h], r15b
0x18002c0c4  jz      short loc_18002C0E1
0x18002c0c6  mov     rax, [rbx+8]
0x18002c0ca  jmp     short loc_18002C0D9
0x18002c0cc  cmp     rbx, [rax+10h]
0x18002c0d0  jnz     short loc_18002C0F6
0x18002c0d2  mov     rbx, rax
0x18002c0d5  mov     rax, [rax+8]
0x18002c0d9  cmp     [rax+19h], r15b
0x18002c0dd  jz      short loc_18002C0CC
0x18002c0df  jmp     short loc_18002C0F6
0x18002c0e1  mov     rcx, [rcx]
0x18002c0e4  cmp     [rcx+19h], r15b
0x18002c0e8  jnz     short loc_18002C0F6
0x18002c0ea  mov     rax, [rcx]
0x18002c0ed  mov     rcx, rax
0x18002c0f0  cmp     [rax+19h], r15b
0x18002c0f4  jz      short loc_18002C0EA
0x18002c0f6  mov     rcx, r13
0x18002c0f9  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@PEAVAsyncObjectBase@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVAsyncObjectBase@Foundation@Bluetooth@Microsoft@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVAsyncObjectBase@Foundation@Bluetooth@Microsoft@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<Microsoft::Bluetooth::Foundation::AsyncObjectBase *>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<Microsoft::Bluetooth::Foundation::AsyncObjectBase *>>,std::_Iterator_base0>)
0x18002c0fe  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x18002c103  mov     rcx, rax; void *
0x18002c106  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c10b  test    rbp, rbp
0x18002c10e  jz      short loc_18002C119
0x18002c110  mov     rcx, rbp; lpCriticalSection
0x18002c113  call    cs:__imp_LeaveCriticalSection
0x18002c119  xor     eax, eax
0x18002c11b  mov     rbx, [rsp+0A8h+arg_10]
0x18002c123  add     rsp, 70h
0x18002c127  pop     r15
0x18002c129  pop     r14
0x18002c12b  pop     r13
0x18002c12d  pop     r12
0x18002c12f  pop     rdi
0x18002c130  pop     rsi
0x18002c131  pop     rbp
0x18002c132  retn
```
