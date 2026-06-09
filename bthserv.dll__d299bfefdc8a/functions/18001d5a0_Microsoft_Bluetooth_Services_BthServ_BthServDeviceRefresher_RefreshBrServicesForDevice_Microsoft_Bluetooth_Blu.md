# Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServicesForDevice(Microsoft::Bluetooth::BluetoothBRAddress const &)

- ea: `0x18001d5a0`
- end: `0x18001d954`
- name: `?RefreshBrServicesForDevice@BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@AEAAJAEBVBluetoothBRAddress@45@@Z`
- size: `948`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *__hidden this, const struct Microsoft::Bluetooth::BluetoothBRAddress *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001d3b0`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x18000d404`
- `0x18000f2e8`
- `0x1800110fc`
- `0x18001140c`
- `0x18001d5a0`
- `0x18001d978`
- `0x18001da88`
- `0x1800237e8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d6dd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d6dd`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServicesForDevice(
        Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *this,
        const struct Microsoft::Bluetooth::BluetoothBRAddress *a2)
{
  char v3; // bl
  bool v4; // dl
  const struct _BLUETOOTH_DEVICE_INFO *v5; // r8
  Microsoft::Bluetooth::Services::BthServ **v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  const struct _BLUETOOTH_DEVICE_INFO *v9; // r8
  int v10; // eax
  __int64 v11; // rdx
  signed int v12; // esi
  volatile signed __int32 *v13; // rdi
  bool v15; // dl
  _BYTE *v16; // rcx
  volatile signed __int32 *v17; // rdi
  Microsoft::Bluetooth::Services::BthServ **v18; // [rsp+60h] [rbp-A0h] BYREF
  volatile signed __int32 *v19; // [rsp+68h] [rbp-98h]
  __int64 InBuffer; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v22[69]; // [rsp+88h] [rbp-78h] BYREF

  v3 = 1;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v21 = 560;
  memset_0(v22, 0, sizeof(v22));
  v22[0] = *((_QWORD *)a2 + 1);
  BthServGlobals::GetSafeRadioHandle((RTL_SRWLOCK *)&Globals, (PVOID *)&v18);
  v6 = v18;
  if ( v18 && (((unsigned __int64)*v18 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpEnableAllServices(*v18, &v21, v5) )
    {
      LOBYTE(v7) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
      Sleep(0x12Cu);
      v10 = Microsoft::Bluetooth::Services::BthServ::BthpEnableAllServices(*v6, &v21, v9);
      v12 = v10;
      if ( v10 )
      {
        if ( v10 > 0 )
          v12 = (unsigned __int16)v10 | 0x80070000;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
          v3 = 0;
        LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = v3;
          WPP_RECORDER_AND_TRACE_SF_sid(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v11,
            v8,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        }
LABEL_27:
        v13 = v19;
        if ( v19 && _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64))v13)(v13, v11, v8);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
        return (unsigned int)v12;
      }
    }
    v15 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
    if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v8, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    InBuffer = *((_QWORD *)a2 + 1);
    v12 = BthServOverlappedIoctl(*v6, 0x411220u, &InBuffer, 8u, 0, 0, 0);
    if ( v12 )
    {
      v16 = WPP_GLOBAL_Control;
      LOBYTE(v11) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      if ( !(_BYTE)v11 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_48;
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sid(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v8, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v16 = WPP_GLOBAL_Control;
LABEL_48:
    if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || v16[25] < 5u )
      v3 = 0;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v16 + 2), v3, v8, *((_QWORD *)v16 + 5));
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_27;
  }
  v17 = v19;
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  return 6;
}

```

## disassembly

```asm
0x18001d5a0  mov     [rsp-8+arg_0], rbx
0x18001d5a5  mov     [rsp-8+arg_10], rsi
0x18001d5aa  push    rbp
0x18001d5ab  push    rdi
0x18001d5ac  push    r12
0x18001d5ae  push    r13
0x18001d5b0  push    r14
0x18001d5b2  lea     rbp, [rsp-1C0h]
0x18001d5ba  sub     rsp, 2C0h
0x18001d5c1  mov     rax, cs:__security_cookie
0x18001d5c8  xor     rax, rsp
0x18001d5cb  mov     [rbp+1E0h+var_30], rax
0x18001d5d2  mov     r14, rdx
0x18001d5d5  lea     r12, WPP_GLOBAL_Control
0x18001d5dc  mov     bl, 1
0x18001d5de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5e5  cmp     rcx, r12
0x18001d5e8  jz      short loc_18001D5F4
0x18001d5ea  cmp     byte ptr [rcx+19h], 5
0x18001d5ee  jb      short loc_18001D5F4
0x18001d5f0  mov     dl, bl
0x18001d5f2  jmp     short loc_18001D5F6
0x18001d5f4  xor     dl, dl
0x18001d5f6  lea     r13, WPP_RECORDER_INITIALIZED
0x18001d5fd  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001d604  setnz   r8b
0x18001d608  lea     rsi, WPP_21eeecb372ac35bdc1c1ea9e0d2ef949_Traceguids
0x18001d60f  test    dl, dl
0x18001d611  jnz     short loc_18001D618
0x18001d613  test    r8b, r8b
0x18001d616  jz      short loc_18001D63A
0x18001d618  mov     rax, [r14+8]
0x18001d61c  mov     [rsp+2E0h+var_298], rax
0x18001d621  mov     [rsp+2E0h+var_2A8], rsi
0x18001d626  mov     word ptr [rsp+2E0h+lpNumberOfBytesTransferred], 0Dh
0x18001d62d  mov     r9, [rcx+28h]
0x18001d631  mov     rcx, [rcx+10h]
0x18001d635  call    WPP_RECORDER_AND_TRACE_SF_si
0x18001d63a  mov     [rbp+1E0h+var_260], 230h
0x18001d642  xor     edx, edx; Val
0x18001d644  mov     r8d, 228h; Size
0x18001d64a  lea     rcx, [rbp+1E0h+var_258]; void *
0x18001d64e  call    memset_0
0x18001d653  mov     rax, [r14+8]
0x18001d657  mov     [rbp+1E0h+var_258], rax
0x18001d65b  lea     rdx, [rsp+2E0h+var_280]
0x18001d660  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x18001d667  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x18001d66c  nop
0x18001d66d  mov     rdi, [rsp+2E0h+var_280]
0x18001d672  test    rdi, rdi
0x18001d675  jz      loc_18001D8E4
0x18001d67b  mov     rcx, [rdi]; this
0x18001d67e  lea     rax, [rcx+1]
0x18001d682  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001d688  jz      loc_18001D8E4
0x18001d68e  lea     rdx, [rbp+1E0h+var_260]; void *
0x18001d692  call    ?BthpEnableAllServices@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@E@Z; Microsoft::Bluetooth::Services::BthServ::BthpEnableAllServices(void *,_BLUETOOTH_DEVICE_INFO const *,uchar)
0x18001d697  test    eax, eax
0x18001d699  jz      loc_18001D79E
0x18001d69f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6a6  cmp     rcx, r12
0x18001d6a9  jz      short loc_18001D6B5
0x18001d6ab  cmp     byte ptr [rcx+19h], 3
0x18001d6af  jb      short loc_18001D6B5
0x18001d6b1  mov     dl, bl
0x18001d6b3  jmp     short loc_18001D6B7
0x18001d6b5  xor     dl, dl
0x18001d6b7  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001d6be  setnz   r8b
0x18001d6c2  test    dl, dl
0x18001d6c4  jnz     short loc_18001D6CB
0x18001d6c6  test    r8b, r8b
0x18001d6c9  jz      short loc_18001D6D8
0x18001d6cb  mov     r9, [rcx+28h]
0x18001d6cf  mov     rcx, [rcx+10h]
0x18001d6d3  call    WPP_RECORDER_AND_TRACE_SF_sddd
0x18001d6d8  mov     ecx, 12Ch; dwMilliseconds
0x18001d6dd  call    cs:__imp_Sleep
0x18001d6e3  lea     rdx, [rbp+1E0h+var_260]; void *
0x18001d6e7  mov     rcx, [rdi]; this
0x18001d6ea  call    ?BthpEnableAllServices@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@E@Z; Microsoft::Bluetooth::Services::BthServ::BthpEnableAllServices(void *,_BLUETOOTH_DEVICE_INFO const *,uchar)
0x18001d6ef  mov     esi, eax
0x18001d6f1  test    eax, eax
0x18001d6f3  jz      loc_18001D797
0x18001d6f9  jle     short loc_18001D704
0x18001d6fb  movzx   esi, ax
0x18001d6fe  or      esi, 80070000h
0x18001d704  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d70b  cmp     rcx, r12
0x18001d70e  jz      short loc_18001D716
0x18001d710  cmp     byte ptr [rcx+19h], 3
0x18001d714  jnb     short loc_18001D718
0x18001d716  xor     bl, bl
0x18001d718  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001d71f  setnz   r8b
0x18001d723  test    bl, bl
0x18001d725  jnz     short loc_18001D72C
0x18001d727  test    r8b, r8b
0x18001d72a  jz      short loc_18001D750
0x18001d72c  mov     [rsp+2E0h+var_290], esi
0x18001d730  mov     rax, [r14+8]
0x18001d734  mov     [rsp+2E0h+var_298], rax
0x18001d739  mov     word ptr [rsp+2E0h+lpNumberOfBytesTransferred], 0Fh
0x18001d740  mov     r9, [rcx+28h]
0x18001d744  mov     dl, bl
0x18001d746  mov     rcx, [rcx+10h]
0x18001d74a  call    WPP_RECORDER_AND_TRACE_SF_sid
0x18001d74f  nop
0x18001d750  mov     rdi, [rsp+2E0h+var_278]
0x18001d755  test    rdi, rdi
0x18001d758  jz      short loc_18001D790
0x18001d75a  or      ebx, 0FFFFFFFFh
0x18001d75d  mov     eax, ebx
0x18001d75f  lock xadd [rdi+8], eax
0x18001d764  add     eax, ebx
0x18001d766  jnz     short loc_18001D790
0x18001d768  mov     rax, [rdi]
0x18001d76b  mov     rcx, rdi
0x18001d76e  mov     rax, [rax]
0x18001d771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d776  mov     edx, ebx
0x18001d778  lock xadd [rdi+0Ch], edx
0x18001d77d  add     edx, ebx
0x18001d77f  jnz     short loc_18001D790
0x18001d781  mov     rdx, [rdi]
0x18001d784  mov     rcx, rdi
0x18001d787  mov     rax, [rdx+8]
0x18001d78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d790  mov     eax, esi
0x18001d792  jmp     loc_18001D929
0x18001d797  lea     rsi, WPP_21eeecb372ac35bdc1c1ea9e0d2ef949_Traceguids
0x18001d79e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7a5  cmp     rcx, r12
0x18001d7a8  jz      short loc_18001D7B4
0x18001d7aa  cmp     byte ptr [rcx+19h], 5
0x18001d7ae  jb      short loc_18001D7B4
0x18001d7b0  mov     dl, bl
0x18001d7b2  jmp     short loc_18001D7B6
0x18001d7b4  xor     dl, dl
0x18001d7b6  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001d7bd  setnz   r8b
0x18001d7c1  test    dl, dl
0x18001d7c3  jnz     short loc_18001D7CA
0x18001d7c5  test    r8b, r8b
0x18001d7c8  jz      short loc_18001D7E3
0x18001d7ca  mov     [rsp+2E0h+var_2A8], rsi
0x18001d7cf  mov     word ptr [rsp+2E0h+lpNumberOfBytesTransferred], 10h
0x18001d7d6  mov     r9, [rcx+28h]
0x18001d7da  mov     rcx, [rcx+10h]
0x18001d7de  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001d7e3  mov     rax, [r14+8]
0x18001d7e7  mov     [rsp+2E0h+InBuffer], rax
0x18001d7ec  mov     [rsp+2E0h+lpNumberOfBytesTransferred], 0; lpNumberOfBytesTransferred
0x18001d7f5  mov     [rsp+2E0h+var_2B8], 0; DWORD
0x18001d7fd  mov     [rsp+2E0h+var_2C0], 0; void *
0x18001d806  mov     r9d, 8; nInBufferSize
0x18001d80c  lea     r8, [rsp+2E0h+InBuffer]; lpInBuffer
0x18001d811  mov     edx, 411220h; dwIoControlCode
0x18001d816  mov     rcx, [rdi]; hFile
0x18001d819  call    ?BthServOverlappedIoctl@@YAKPEAXK0K0KPEAK@Z; BthServOverlappedIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x18001d81e  mov     esi, eax
0x18001d820  mov     edi, 80070000h
0x18001d825  test    eax, eax
0x18001d827  jz      short loc_18001D883
0x18001d829  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d830  cmp     rcx, r12
0x18001d833  jz      short loc_18001D83F
0x18001d835  cmp     byte ptr [rcx+19h], 3
0x18001d839  jb      short loc_18001D83F
0x18001d83b  mov     dl, bl
0x18001d83d  jmp     short loc_18001D841
0x18001d83f  xor     dl, dl
0x18001d841  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001d848  setnz   r8b
0x18001d84c  test    dl, dl
0x18001d84e  jnz     short loc_18001D855
0x18001d850  test    r8b, r8b
0x18001d853  jz      short loc_18001D88A
0x18001d855  test    esi, esi
0x18001d857  jg      short loc_18001D85D
0x18001d859  mov     eax, esi
0x18001d85b  jmp     short loc_18001D862
0x18001d85d  movzx   eax, si
0x18001d860  or      eax, edi
0x18001d862  mov     [rsp+2E0h+var_290], eax
0x18001d866  mov     rax, [r14+8]
0x18001d86a  mov     [rsp+2E0h+var_298], rax
0x18001d86f  mov     word ptr [rsp+2E0h+lpNumberOfBytesTransferred], 11h
0x18001d876  mov     r9, [rcx+28h]
0x18001d87a  mov     rcx, [rcx+10h]
0x18001d87e  call    WPP_RECORDER_AND_TRACE_SF_sid
0x18001d883  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d88a  cmp     rcx, r12
0x18001d88d  jz      short loc_18001D895
0x18001d88f  cmp     byte ptr [rcx+19h], 5
0x18001d893  jnb     short loc_18001D897
0x18001d895  xor     bl, bl
0x18001d897  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001d89e  setnz   r8b
0x18001d8a2  test    bl, bl
0x18001d8a4  jnz     short loc_18001D8AB
0x18001d8a6  test    r8b, r8b
0x18001d8a9  jz      short loc_18001D8D2
0x18001d8ab  mov     [rsp+2E0h+var_298], rsi
0x18001d8b0  lea     rax, WPP_21eeecb372ac35bdc1c1ea9e0d2ef949_Traceguids
0x18001d8b7  mov     [rsp+2E0h+var_2A8], rax
0x18001d8bc  mov     word ptr [rsp+2E0h+lpNumberOfBytesTransferred], 12h
0x18001d8c3  mov     r9, [rcx+28h]
0x18001d8c7  mov     dl, bl
0x18001d8c9  mov     rcx, [rcx+10h]
0x18001d8cd  call    WPP_RECORDER_AND_TRACE_SF_si
0x18001d8d2  test    esi, esi
0x18001d8d4  jle     loc_18001D750
0x18001d8da  movzx   esi, si
0x18001d8dd  or      esi, edi
0x18001d8df  jmp     loc_18001D750
0x18001d8e4  mov     rdi, [rsp+2E0h+var_278]
0x18001d8e9  test    rdi, rdi
0x18001d8ec  jz      short loc_18001D924
0x18001d8ee  or      ebx, 0FFFFFFFFh
0x18001d8f1  mov     eax, ebx
0x18001d8f3  lock xadd [rdi+8], eax
0x18001d8f8  add     eax, ebx
0x18001d8fa  jnz     short loc_18001D924
0x18001d8fc  mov     rax, [rdi]
0x18001d8ff  mov     rcx, rdi
0x18001d902  mov     rax, [rax]
0x18001d905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d90a  mov     eax, ebx
0x18001d90c  lock xadd [rdi+0Ch], eax
0x18001d911  add     eax, ebx
0x18001d913  jnz     short loc_18001D924
0x18001d915  mov     rax, [rdi]
0x18001d918  mov     rcx, rdi
0x18001d91b  mov     rax, [rax+8]
0x18001d91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d924  mov     eax, 6
0x18001d929  mov     rcx, [rbp+1E0h+var_30]
0x18001d930  xor     rcx, rsp; StackCookie
0x18001d933  call    __security_check_cookie
0x18001d938  lea     r11, [rsp+2E0h+var_20]
0x18001d940  mov     rbx, [r11+30h]
0x18001d944  mov     rsi, [r11+40h]
0x18001d948  mov     rsp, r11
0x18001d94b  pop     r14
0x18001d94d  pop     r13
0x18001d94f  pop     r12
0x18001d951  pop     rdi
0x18001d952  pop     rbp
0x18001d953  retn
```
