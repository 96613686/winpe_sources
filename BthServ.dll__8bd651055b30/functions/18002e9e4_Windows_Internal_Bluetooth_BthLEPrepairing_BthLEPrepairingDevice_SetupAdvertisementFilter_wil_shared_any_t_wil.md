# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::SetupAdvertisementFilter(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)

- ea: `0x18002e9e4`
- end: `0x18002ecb2`
- name: `?SetupAdvertisementFilter@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `718`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18002b4d4`

## callees

- `0x180011194`
- `0x18001140c`
- `0x18002aec0`
- `0x18002c278`
- `0x18002e9e4`
- `0x18002efa0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002ec30`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002ec30`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::SetupAdvertisementFilter(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *this,
        __int64 *a2,
        __int64 a3)
{
  __int64 *v3; // rbx
  char v5; // si
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  volatile signed __int32 *v9; // rbx
  int v10; // edx
  int v11; // r8d
  int v12; // ebx
  _BYTE *v13; // rcx
  int v14; // eax
  bool v15; // cf
  bool v16; // dl
  int v17; // eax
  bool v18; // cf
  int v20; // [rsp+20h] [rbp-49h]
  int v21; // [rsp+28h] [rbp-41h]
  _QWORD v22[12]; // [rsp+60h] [rbp-9h] BYREF
  int v23; // [rsp+D0h] [rbp+67h] BYREF
  int v24; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v25; // [rsp+E0h] [rbp+77h] BYREF
  char *v26; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = a2;
  v5 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_BYTE)a2,
      a3,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v6 = v3[1];
  if ( v6 )
    _InterlockedAdd((volatile signed __int32 *)(v6 + 8), 1u);
  v7 = v3[1];
  v8 = *v3;
  v9 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  *(_QWORD *)this = v8;
  *((_QWORD *)this + 1) = v7;
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64 *, __int64))v9)(v9, a2, a3);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  *((_DWORD *)this + 34) = 5023;
  v26 = (char *)this + 88;
  v25 = *((_QWORD *)this + 16);
  v24 = 45;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_BYTE)a2,
      a3,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v22[0] = this;
  v22[1] = &v25;
  v22[2] = &v24;
  v22[3] = &v26;
  v22[4] = &v23;
  v23 = wil::ResultFromException__lambda_fe7b844e9001a84485ac6c4cb501e51d___(v22, a2, a3);
  v12 = v23;
  if ( v23 >= 0 )
    goto LABEL_29;
  v13 = WPP_GLOBAL_Control;
  LOBYTE(v10) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v20,
      v21,
      24,
      (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    v12 = v23;
LABEL_29:
    v13 = WPP_GLOBAL_Control;
  }
  v14 = 0;
  if ( v12 )
    v15 = v13[25] < 2u;
  else
    v15 = v13[25] < 5u;
  v16 = 0;
  if ( v13 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v14) = !v15;
    if ( v14 )
      v16 = 1;
  }
  if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_sqd(
      *((_QWORD *)v13 + 2),
      v16,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v13 + 5),
      v20,
      v21,
      25,
      (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    v13 = WPP_GLOBAL_Control;
    v12 = v23;
  }
  if ( v12 >= 0 )
  {
    if ( !v12 )
    {
      v17 = 0;
      v18 = v13[25] < 5u;
      goto LABEL_43;
    }
  }
  else
  {
    SetEvent(*((HANDLE *)this + 15));
    Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop(this);
    v13 = WPP_GLOBAL_Control;
  }
  v17 = 0;
  v18 = v13[25] < 2u;
LABEL_43:
  if ( v13 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v17) = !v18, !v17) )
    v5 = 0;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sqd(
      *((_QWORD *)v13 + 2),
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v13 + 5),
      v20,
      v21,
      20,
      (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002e9e4  push    rbp
0x18002e9e6  push    rbx
0x18002e9e7  push    rsi
0x18002e9e8  push    rdi
0x18002e9e9  push    r12
0x18002e9eb  push    r13
0x18002e9ed  push    r14
0x18002e9ef  lea     rbp, [rsp-27h]
0x18002e9f4  sub     rsp, 90h
0x18002e9fb  mov     rbx, rdx
0x18002e9fe  mov     rdi, rcx
0x18002ea01  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea08  lea     r12, WPP_GLOBAL_Control
0x18002ea0f  mov     esi, 1
0x18002ea14  cmp     rcx, r12
0x18002ea17  jz      short loc_18002EA24
0x18002ea19  cmp     byte ptr [rcx+19h], 5
0x18002ea1d  jb      short loc_18002EA24
0x18002ea1f  mov     dl, sil
0x18002ea22  jmp     short loc_18002EA26
0x18002ea24  xor     dl, dl
0x18002ea26  lea     r13, WPP_RECORDER_INITIALIZED
0x18002ea2d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002ea34  lea     r14, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002ea3b  setnz   r8b
0x18002ea3f  test    dl, dl
0x18002ea41  jnz     short loc_18002EA48
0x18002ea43  test    r8b, r8b
0x18002ea46  jz      short loc_18002EA66
0x18002ea48  mov     r9, [rcx+28h]
0x18002ea4c  mov     rcx, [rcx+10h]
0x18002ea50  mov     [rsp+0C0h+var_78], rdi
0x18002ea55  mov     [rsp+0C0h+var_88], r14
0x18002ea5a  mov     [rsp+0C0h+var_90], 13h
0x18002ea61  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002ea66  mov     rax, [rbx+8]
0x18002ea6a  test    rax, rax
0x18002ea6d  jz      short loc_18002EA73
0x18002ea6f  lock add [rax+8], esi
0x18002ea73  mov     rcx, [rbx+8]
0x18002ea77  mov     rax, [rbx]
0x18002ea7a  mov     rbx, [rdi+8]
0x18002ea7e  mov     [rdi], rax
0x18002ea81  mov     [rdi+8], rcx
0x18002ea85  test    rbx, rbx
0x18002ea88  jz      short loc_18002EACC
0x18002ea8a  or      r14d, 0FFFFFFFFh
0x18002ea8e  mov     eax, r14d
0x18002ea91  lock xadd [rbx+8], eax
0x18002ea96  add     eax, r14d
0x18002ea99  jnz     short loc_18002EAC5
0x18002ea9b  mov     rax, [rbx]
0x18002ea9e  mov     rcx, rbx
0x18002eaa1  mov     rax, [rax]
0x18002eaa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eaa9  mov     eax, r14d
0x18002eaac  lock xadd [rbx+0Ch], eax
0x18002eab1  add     eax, r14d
0x18002eab4  jnz     short loc_18002EAC5
0x18002eab6  mov     rax, [rbx]
0x18002eab9  mov     rcx, rbx
0x18002eabc  mov     rax, [rax+8]
0x18002eac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eac5  lea     r14, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002eacc  lea     rax, [rdi+58h]
0x18002ead0  mov     dword ptr [rdi+88h], 139Fh
0x18002eada  mov     [rbp+57h+arg_18], rax
0x18002eade  mov     rax, [rdi+80h]
0x18002eae5  mov     [rbp+57h+arg_10], rax
0x18002eae9  mov     [rbp+57h+arg_8], 2Dh ; '-'
0x18002eaf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eaf7  cmp     rcx, r12
0x18002eafa  jz      short loc_18002EB07
0x18002eafc  cmp     byte ptr [rcx+19h], 5
0x18002eb00  jb      short loc_18002EB07
0x18002eb02  mov     dl, sil
0x18002eb05  jmp     short loc_18002EB09
0x18002eb07  xor     dl, dl
0x18002eb09  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002eb10  setnz   r8b
0x18002eb14  test    dl, dl
0x18002eb16  jnz     short loc_18002EB1D
0x18002eb18  test    r8b, r8b
0x18002eb1b  jz      short loc_18002EB3B
0x18002eb1d  mov     r9, [rcx+28h]
0x18002eb21  mov     rcx, [rcx+10h]
0x18002eb25  mov     [rsp+0C0h+var_78], rdi
0x18002eb2a  mov     [rsp+0C0h+var_88], r14
0x18002eb2f  mov     [rsp+0C0h+var_90], 17h
0x18002eb36  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002eb3b  lea     rax, [rbp+57h+arg_10]
0x18002eb3f  mov     [rbp+57h+var_60], rdi
0x18002eb43  mov     [rbp+57h+var_58], rax
0x18002eb47  lea     rcx, [rbp+57h+var_60]
0x18002eb4b  lea     rax, [rbp+57h+arg_8]
0x18002eb4f  mov     [rbp+57h+var_50], rax
0x18002eb53  lea     rax, [rbp+57h+arg_18]
0x18002eb57  mov     [rbp+57h+var_48], rax
0x18002eb5b  lea     rax, [rbp+57h+arg_0]
0x18002eb5f  mov     [rbp+57h+var_40], rax
0x18002eb63  call    wil__ResultFromException__lambda_fe7b844e9001a84485ac6c4cb501e51d___
0x18002eb68  mov     [rbp+57h+arg_0], eax
0x18002eb6b  mov     ebx, eax
0x18002eb6d  test    eax, eax
0x18002eb6f  jns     short loc_18002EBBE
0x18002eb71  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb78  cmp     rcx, r12
0x18002eb7b  jz      short loc_18002EB88
0x18002eb7d  cmp     byte ptr [rcx+19h], 5
0x18002eb81  jb      short loc_18002EB88
0x18002eb83  mov     dl, sil
0x18002eb86  jmp     short loc_18002EB8A
0x18002eb88  xor     dl, dl
0x18002eb8a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002eb91  setnz   r8b
0x18002eb95  test    dl, dl
0x18002eb97  jnz     short loc_18002EB9E
0x18002eb99  test    r8b, r8b
0x18002eb9c  jz      short loc_18002EBC5
0x18002eb9e  mov     r9, [rcx+28h]
0x18002eba2  mov     rcx, [rcx+10h]
0x18002eba6  mov     dword ptr [rsp+0C0h+var_78], eax
0x18002ebaa  mov     [rsp+0C0h+var_88], r14
0x18002ebaf  mov     [rsp+0C0h+var_90], 18h
0x18002ebb6  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002ebbb  mov     ebx, [rbp+57h+arg_0]
0x18002ebbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebc5  xor     eax, eax
0x18002ebc7  test    ebx, ebx
0x18002ebc9  jnz     short loc_18002EBD1
0x18002ebcb  cmp     byte ptr [rcx+19h], 5
0x18002ebcf  jmp     short loc_18002EBD5
0x18002ebd1  cmp     byte ptr [rcx+19h], 2
0x18002ebd5  setnb   al
0x18002ebd8  cmp     rcx, r12
0x18002ebdb  jz      short loc_18002EBE6
0x18002ebdd  test    eax, eax
0x18002ebdf  jz      short loc_18002EBE6
0x18002ebe1  mov     dl, sil
0x18002ebe4  jmp     short loc_18002EBE8
0x18002ebe6  xor     dl, dl
0x18002ebe8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002ebef  setnz   r8b
0x18002ebf3  test    dl, dl
0x18002ebf5  jnz     short loc_18002EBFC
0x18002ebf7  test    r8b, r8b
0x18002ebfa  jz      short loc_18002EC28
0x18002ebfc  mov     r9, [rcx+28h]
0x18002ec00  mov     rcx, [rcx+10h]
0x18002ec04  mov     [rsp+0C0h+var_70], ebx
0x18002ec08  mov     [rsp+0C0h+var_78], rdi
0x18002ec0d  mov     [rsp+0C0h+var_88], r14
0x18002ec12  mov     [rsp+0C0h+var_90], 19h
0x18002ec19  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002ec1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec25  mov     ebx, [rbp+57h+arg_0]
0x18002ec28  test    ebx, ebx
0x18002ec2a  jns     short loc_18002ECA8
0x18002ec2c  mov     rcx, [rdi+78h]; hEvent
0x18002ec30  call    cs:__imp_SetEvent
0x18002ec36  mov     rcx, rdi; this
0x18002ec39  call    ?Stop@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop(void)
0x18002ec3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec45  xor     eax, eax
0x18002ec47  cmp     byte ptr [rcx+19h], 2
0x18002ec4b  setnb   al
0x18002ec4e  cmp     rcx, r12
0x18002ec51  jz      short loc_18002EC57
0x18002ec53  test    eax, eax
0x18002ec55  jnz     short loc_18002EC5A
0x18002ec57  xor     sil, sil
0x18002ec5a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002ec61  setnz   r8b
0x18002ec65  test    sil, sil
0x18002ec68  jnz     short loc_18002EC6F
0x18002ec6a  test    r8b, r8b
0x18002ec6d  jz      short loc_18002EC94
0x18002ec6f  mov     r9, [rcx+28h]
0x18002ec73  mov     dl, sil
0x18002ec76  mov     rcx, [rcx+10h]
0x18002ec7a  mov     [rsp+0C0h+var_70], ebx
0x18002ec7e  mov     [rsp+0C0h+var_78], rdi
0x18002ec83  mov     [rsp+0C0h+var_88], r14
0x18002ec88  mov     [rsp+0C0h+var_90], 14h
0x18002ec8f  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002ec94  mov     eax, ebx
0x18002ec96  add     rsp, 90h
0x18002ec9d  pop     r14
0x18002ec9f  pop     r13
0x18002eca1  pop     r12
0x18002eca3  pop     rdi
0x18002eca4  pop     rsi
0x18002eca5  pop     rbx
0x18002eca6  pop     rbp
0x18002eca7  retn
0x18002eca8  jnz     short loc_18002EC45
0x18002ecaa  xor     eax, eax
0x18002ecac  cmp     byte ptr [rcx+19h], 5
0x18002ecb0  jmp     short loc_18002EC4B
```
