# vemgr::Uninitialize(void)

- ea: `0x18001948c`
- end: `0x18001961b`
- name: `?Uninitialize@vemgr@@YAJXZ`
- size: `399`
- prototype: `__int64 __fastcall(vemgr *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009ef0`
- `0x180015fa4`

## callees

- `0x18001948c`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x18001949f`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x18001949f`

## pseudocode

```c
__int64 __fastcall vemgr::Uninitialize(vemgr *this)
{
  _QWORD *v1; // rax
  volatile signed __int32 *v3; // rbx
  _QWORD *v4; // rax
  volatile signed __int32 *v5; // rbx
  _QWORD *v6; // rax
  volatile signed __int32 *v7; // rbx
  _QWORD *v8; // rax
  volatile signed __int32 *v9; // rbx

  PsSetCreateProcessNotifyRoutineEx(vemgr::ProcessNotifyCallbackEx, 1u);
  v1 = vemgr::g_pDeviceExtn;
  if ( !vemgr::g_pDeviceExtn )
    return 3221225626LL;
  v3 = (volatile signed __int32 *)*((_QWORD *)vemgr::g_pDeviceExtn + 7);
  *((_QWORD *)vemgr::g_pDeviceExtn + 6) = 0;
  v1[7] = 0;
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 16LL))(v3);
    }
  }
  v4 = vemgr::g_pDeviceExtn;
  v5 = (volatile signed __int32 *)*((_QWORD *)vemgr::g_pDeviceExtn + 5);
  *((_QWORD *)vemgr::g_pDeviceExtn + 4) = 0;
  v4[5] = 0;
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  v6 = vemgr::g_pDeviceExtn;
  v7 = (volatile signed __int32 *)*((_QWORD *)vemgr::g_pDeviceExtn + 3);
  *((_QWORD *)vemgr::g_pDeviceExtn + 2) = 0;
  v6[3] = 0;
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  v8 = vemgr::g_pDeviceExtn;
  v9 = (volatile signed __int32 *)*((_QWORD *)vemgr::g_pDeviceExtn + 9);
  *((_QWORD *)vemgr::g_pDeviceExtn + 8) = 0;
  v8[9] = 0;
  if ( v9 && _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18001948c  mov     [rsp+arg_0], rbx
0x180019491  push    rdi
0x180019492  sub     rsp, 20h
0x180019496  mov     dl, 1; Remove
0x180019498  lea     rcx, ?ProcessNotifyCallbackEx@vemgr@@YAXPEAU_KPROCESS@@PEAXPEAU_PS_CREATE_NOTIFY_INFO@@@Z; NotifyRoutine
0x18001949f  call    cs:__imp_PsSetCreateProcessNotifyRoutineEx
0x1800194a6  nop     dword ptr [rax+rax+00h]
0x1800194ab  mov     rax, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x1800194b2  test    rax, rax
0x1800194b5  jnz     short loc_1800194C1
0x1800194b7  mov     eax, 0C000009Ah
0x1800194bc  jmp     loc_18001960F
0x1800194c1  mov     rbx, [rax+38h]
0x1800194c5  or      edi, 0FFFFFFFFh
0x1800194c8  mov     qword ptr [rax+30h], 0
0x1800194d0  mov     qword ptr [rax+38h], 0
0x1800194d8  test    rbx, rbx
0x1800194db  jz      short loc_180019511
0x1800194dd  mov     eax, edi
0x1800194df  lock xadd [rbx+8], eax
0x1800194e4  add     eax, edi
0x1800194e6  jnz     short loc_180019511
0x1800194e8  mov     rax, [rbx]
0x1800194eb  mov     rcx, rbx
0x1800194ee  mov     rax, [rax+8]
0x1800194f2  call    _guard_dispatch_icall
0x1800194f7  mov     eax, edi
0x1800194f9  lock xadd [rbx+0Ch], eax
0x1800194fe  add     eax, edi
0x180019500  jnz     short loc_180019511
0x180019502  mov     rax, [rbx]
0x180019505  mov     rcx, rbx
0x180019508  mov     rax, [rax+10h]
0x18001950c  call    _guard_dispatch_icall
0x180019511  mov     rax, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x180019518  mov     rbx, [rax+28h]
0x18001951c  mov     qword ptr [rax+20h], 0
0x180019524  mov     qword ptr [rax+28h], 0
0x18001952c  test    rbx, rbx
0x18001952f  jz      short loc_180019565
0x180019531  mov     eax, edi
0x180019533  lock xadd [rbx+8], eax
0x180019538  add     eax, edi
0x18001953a  jnz     short loc_180019565
0x18001953c  mov     rax, [rbx]
0x18001953f  mov     rcx, rbx
0x180019542  mov     rax, [rax+8]
0x180019546  call    _guard_dispatch_icall
0x18001954b  mov     eax, edi
0x18001954d  lock xadd [rbx+0Ch], eax
0x180019552  add     eax, edi
0x180019554  jnz     short loc_180019565
0x180019556  mov     rax, [rbx]
0x180019559  mov     rcx, rbx
0x18001955c  mov     rax, [rax+10h]
0x180019560  call    _guard_dispatch_icall
0x180019565  mov     rax, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x18001956c  mov     rbx, [rax+18h]
0x180019570  mov     qword ptr [rax+10h], 0
0x180019578  mov     qword ptr [rax+18h], 0
0x180019580  test    rbx, rbx
0x180019583  jz      short loc_1800195B9
0x180019585  mov     eax, edi
0x180019587  lock xadd [rbx+8], eax
0x18001958c  add     eax, edi
0x18001958e  jnz     short loc_1800195B9
0x180019590  mov     rax, [rbx]
0x180019593  mov     rcx, rbx
0x180019596  mov     rax, [rax+8]
0x18001959a  call    _guard_dispatch_icall
0x18001959f  mov     eax, edi
0x1800195a1  lock xadd [rbx+0Ch], eax
0x1800195a6  add     eax, edi
0x1800195a8  jnz     short loc_1800195B9
0x1800195aa  mov     rax, [rbx]
0x1800195ad  mov     rcx, rbx
0x1800195b0  mov     rax, [rax+10h]
0x1800195b4  call    _guard_dispatch_icall
0x1800195b9  mov     rax, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x1800195c0  mov     rbx, [rax+48h]
0x1800195c4  mov     qword ptr [rax+40h], 0
0x1800195cc  mov     qword ptr [rax+48h], 0
0x1800195d4  test    rbx, rbx
0x1800195d7  jz      short loc_18001960D
0x1800195d9  mov     eax, edi
0x1800195db  lock xadd [rbx+8], eax
0x1800195e0  add     eax, edi
0x1800195e2  jnz     short loc_18001960D
0x1800195e4  mov     rax, [rbx]
0x1800195e7  mov     rcx, rbx
0x1800195ea  mov     rax, [rax+8]
0x1800195ee  call    _guard_dispatch_icall
0x1800195f3  mov     eax, edi
0x1800195f5  lock xadd [rbx+0Ch], eax
0x1800195fa  add     eax, edi
0x1800195fc  jnz     short loc_18001960D
0x1800195fe  mov     rax, [rbx]
0x180019601  mov     rcx, rbx
0x180019604  mov     rax, [rax+10h]
0x180019608  call    _guard_dispatch_icall
0x18001960d  xor     eax, eax
0x18001960f  mov     rbx, [rsp+28h+arg_0]
0x180019614  add     rsp, 20h
0x180019618  pop     rdi
0x180019619  retn
```
