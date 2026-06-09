# Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServices(void)

- ea: `0x18001d3b0`
- end: `0x18001d57e`
- name: `?RefreshBrServices@BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@AEAAXXZ`
- size: `462`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001d590`

## callees

- `0x180001b60`
- `0x180001b9c`
- `0x1800110fc`
- `0x18001d3b0`
- `0x18001d5a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d4b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d4b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d44c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d44c`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServices(PSRWLOCK SRWLock)
{
  char v2; // bp
  bool v3; // dl
  _QWORD *v4; // rsi
  _QWORD *Ptr; // rdi
  PSRWLOCK v6; // r14
  _QWORD *v7; // rcx
  _QWORD *v8; // rbx
  Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *v9; // rcx
  _QWORD *i; // rbx
  _QWORD *v11; // rcx
  _QWORD *v12; // rbx
  _QWORD *v13; // [rsp+50h] [rbp-58h] BYREF
  PVOID v14; // [rsp+58h] [rbp-50h]
  _QWORD v15[9]; // [rsp+60h] [rbp-48h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v14 = 0;
  v4 = operator new(0x20u);
  *v4 = v4;
  v4[1] = v4;
  Ptr = v4;
  v13 = v4;
  AcquireSRWLockExclusive(SRWLock);
  v6 = SRWLock + 2;
  if ( &v13 != (_QWORD **)&SRWLock[2] )
  {
    *(_QWORD *)v4[1] = 0;
    v7 = (_QWORD *)*v4;
    if ( *v4 )
    {
      do
      {
        v8 = (_QWORD *)*v7;
        operator delete(v7, (const struct std::nothrow_t *)0x20);
        v7 = v8;
      }
      while ( v8 );
    }
    *v4 = v4;
    v4[1] = v4;
    Ptr = v6->Ptr;
    v13 = v6->Ptr;
    v6->Ptr = v4;
    v14 = SRWLock[3].Ptr;
    SRWLock[3].Ptr = 0;
  }
  LOBYTE(SRWLock[1].Ptr) = 0;
  ReleaseSRWLockExclusive(SRWLock);
  for ( i = (_QWORD *)*Ptr; i != Ptr; i = (_QWORD *)*i )
  {
    v15[1] = i[3];
    v15[0] = &Microsoft::Bluetooth::BluetoothBRAddress::`vftable';
    Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServicesForDevice(
      v9,
      (const struct Microsoft::Bluetooth::BluetoothBRAddress *)v15);
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  *(_QWORD *)Ptr[1] = 0;
  v11 = (_QWORD *)*Ptr;
  if ( *Ptr )
  {
    do
    {
      v12 = (_QWORD *)*v11;
      operator delete(v11, (const struct std::nothrow_t *)0x20);
      v11 = v12;
    }
    while ( v12 );
  }
  operator delete(Ptr, (const struct std::nothrow_t *)0x20);
}

```

## disassembly

```asm
0x18001d3b0  push    rbx
0x18001d3b2  push    rbp
0x18001d3b3  push    rsi
0x18001d3b4  push    rdi
0x18001d3b5  push    r13
0x18001d3b7  push    r14
0x18001d3b9  push    r15
0x18001d3bb  sub     rsp, 70h
0x18001d3bf  mov     r15, rcx
0x18001d3c2  lea     rax, WPP_GLOBAL_Control
0x18001d3c9  mov     bpl, 1
0x18001d3cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3d3  cmp     rcx, rax
0x18001d3d6  jz      short loc_18001D3E3
0x18001d3d8  cmp     byte ptr [rcx+19h], 4
0x18001d3dc  jb      short loc_18001D3E3
0x18001d3de  mov     dl, bpl
0x18001d3e1  jmp     short loc_18001D3E5
0x18001d3e3  xor     dl, dl
0x18001d3e5  lea     rax, WPP_RECORDER_INITIALIZED
0x18001d3ec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001d3f3  setnz   r8b
0x18001d3f7  lea     r9, WPP_21eeecb372ac35bdc1c1ea9e0d2ef949_Traceguids
0x18001d3fe  test    dl, dl
0x18001d400  jnz     short loc_18001D407
0x18001d402  test    r8b, r8b
0x18001d405  jz      short loc_18001D420
0x18001d407  mov     [rsp+0A8h+var_70], r9
0x18001d40c  mov     [rsp+0A8h+var_78], 0Bh
0x18001d413  mov     r9, [rcx+28h]
0x18001d417  mov     rcx, [rcx+10h]
0x18001d41b  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001d420  mov     [rsp+0A8h+var_50], 0
0x18001d429  mov     r13d, 20h ; ' '
0x18001d42f  mov     ecx, r13d; Size
0x18001d432  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d437  mov     rsi, rax
0x18001d43a  mov     [rax], rax
0x18001d43d  mov     [rax+8], rax
0x18001d441  mov     rdi, rax
0x18001d444  mov     [rsp+0A8h+var_58], rax
0x18001d449  mov     rcx, r15; SRWLock
0x18001d44c  call    cs:__imp_AcquireSRWLockExclusive
0x18001d452  lea     r14, [r15+10h]
0x18001d456  lea     rax, [rsp+0A8h+var_58]
0x18001d45b  cmp     rax, r14
0x18001d45e  jz      short loc_18001D4A9
0x18001d460  mov     rax, [rdi+8]
0x18001d464  mov     qword ptr [rax], 0
0x18001d46b  mov     rcx, [rdi]; void *
0x18001d46e  test    rcx, rcx
0x18001d471  jz      short loc_18001D486
0x18001d473  mov     rbx, [rcx]
0x18001d476  mov     rdx, r13; struct std::nothrow_t *
0x18001d479  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d47e  mov     rcx, rbx
0x18001d481  test    rbx, rbx
0x18001d484  jnz     short loc_18001D473
0x18001d486  mov     [rsi], rsi
0x18001d489  mov     [rsi+8], rsi
0x18001d48d  mov     rdi, [r14]
0x18001d490  mov     [rsp+0A8h+var_58], rdi
0x18001d495  mov     [r14], rsi
0x18001d498  mov     rax, [r14+8]
0x18001d49c  mov     [rsp+0A8h+var_50], rax
0x18001d4a1  mov     qword ptr [r14+8], 0
0x18001d4a9  mov     byte ptr [r15+8], 0
0x18001d4ae  mov     rcx, r15; SRWLock
0x18001d4b1  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d4b7  mov     rbx, [rdi]
0x18001d4ba  cmp     rbx, rdi
0x18001d4bd  jz      short loc_18001D4E3
0x18001d4bf  mov     rax, [rbx+18h]
0x18001d4c3  mov     [rsp+0A8h+var_40], rax
0x18001d4c8  lea     rax, ??_7BluetoothBRAddress@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::BluetoothBRAddress::`vftable'
0x18001d4cf  mov     [rsp+0A8h+var_48], rax
0x18001d4d4  lea     rdx, [rsp+0A8h+var_48]; struct Microsoft::Bluetooth::BluetoothBRAddress *
0x18001d4d9  call    ?RefreshBrServicesForDevice@BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@AEAAJAEBVBluetoothBRAddress@45@@Z; Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServicesForDevice(Microsoft::Bluetooth::BluetoothBRAddress const &)
0x18001d4de  mov     rbx, [rbx]
0x18001d4e1  jmp     short loc_18001D4BA
0x18001d4e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4ea  lea     rax, WPP_GLOBAL_Control
0x18001d4f1  cmp     rcx, rax
0x18001d4f4  jz      short loc_18001D4FC
0x18001d4f6  cmp     byte ptr [rcx+19h], 5
0x18001d4fa  jnb     short loc_18001D4FF
0x18001d4fc  xor     bpl, bpl
0x18001d4ff  lea     rax, WPP_RECORDER_INITIALIZED
0x18001d506  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001d50d  setnz   r8b
0x18001d511  test    bpl, bpl
0x18001d514  jnz     short loc_18001D51B
0x18001d516  test    r8b, r8b
0x18001d519  jz      short loc_18001D53F
0x18001d51b  lea     rdx, WPP_21eeecb372ac35bdc1c1ea9e0d2ef949_Traceguids
0x18001d522  mov     [rsp+0A8h+var_70], rdx
0x18001d527  mov     [rsp+0A8h+var_78], 0Ch
0x18001d52e  mov     r9, [rcx+28h]
0x18001d532  mov     dl, bpl
0x18001d535  mov     rcx, [rcx+10h]
0x18001d539  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001d53e  nop
0x18001d53f  mov     rax, [rdi+8]
0x18001d543  mov     qword ptr [rax], 0
0x18001d54a  mov     rcx, [rdi]; void *
0x18001d54d  test    rcx, rcx
0x18001d550  jz      short loc_18001D565
0x18001d552  mov     rbx, [rcx]
0x18001d555  mov     rdx, r13; struct std::nothrow_t *
0x18001d558  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d55d  mov     rcx, rbx
0x18001d560  test    rbx, rbx
0x18001d563  jnz     short loc_18001D552
0x18001d565  mov     rdx, r13; struct std::nothrow_t *
0x18001d568  mov     rcx, rdi; void *
0x18001d56b  add     rsp, 70h
0x18001d56f  pop     r15
0x18001d571  pop     r14
0x18001d573  pop     r13
0x18001d575  pop     rdi
0x18001d576  pop     rsi
0x18001d577  pop     rbp
0x18001d578  pop     rbx
0x18001d579  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
