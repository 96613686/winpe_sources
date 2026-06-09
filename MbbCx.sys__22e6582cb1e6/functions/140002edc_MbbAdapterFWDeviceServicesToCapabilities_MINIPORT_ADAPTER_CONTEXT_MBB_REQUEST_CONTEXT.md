# MbbAdapterFWDeviceServicesToCapabilities(_MINIPORT_ADAPTER_CONTEXT *,_MBB_REQUEST_CONTEXT *)

- ea: `0x140002edc`
- end: `0x1400030d0`
- name: `?MbbAdapterFWDeviceServicesToCapabilities@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_MBB_REQUEST_CONTEXT@@@Z`
- size: `500`
- prototype: `__int64 __fastcall(KSPIN_LOCK *, struct _MBB_REQUEST_CONTEXT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x14002e9c4`

## callees

- `0x140002edc`
- `0x140003d30`
- `0x1400051ac`
- `0x14001eca4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140003029`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400030ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003029`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400030ab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000300e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000304f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000300e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000304f`

## pseudocode

```c
__int64 __fastcall MbbAdapterFWDeviceServicesToCapabilities(KSPIN_LOCK *a1, struct _MBB_REQUEST_CONTEXT *a2)
{
  struct _MBB_REQUEST_CONTEXT *v2; // rbp
  int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  int v7; // r9d
  unsigned int MultiCarrierDsCidList; // eax
  unsigned int v9; // esi
  KIRQL v10; // al
  struct _MBB_DS *DeviceService; // r14
  KIRQL v12; // al
  unsigned int i; // r9d

  v2 = a2;
  if ( (*(_DWORD *)(*((_QWORD *)a2 + 99) + 104LL) & 0x20) != 0 )
  {
    v4 = *((_DWORD *)a2 + 195);
    if ( (v4 & 1) != 0 )
    {
      v6 = 0;
      if ( (v4 & 2) == 0 )
      {
        MultiCarrierDsCidList = MbbAdapterQueryMultiCarrierDsCidList(a1, &MBB_UUID_AUTH, a2);
        v6 = MultiCarrierDsCidList;
        if ( MultiCarrierDsCidList )
        {
          if ( MultiCarrierDsCidList != 259 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
LABEL_15:
              v9 = v6;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(a2) = 2;
                WPP_RECORDER_SF_DD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  (_DWORD)a2,
                  3,
                  76,
                  (__int64)WPP_94691144733c3f1d26776b6e97df90bb_Traceguids,
                  *((_DWORD *)v2 + 4),
                  v6);
              }
              return v9;
            }
            v7 = 75;
LABEL_7:
            LOBYTE(a2) = 2;
            WPP_RECORDER_SF_DD(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)a2,
              3,
              v7,
              (__int64)WPP_94691144733c3f1d26776b6e97df90bb_Traceguids,
              *((_DWORD *)v2 + 4),
              v6);
            goto LABEL_15;
          }
        }
      }
    }
    else
    {
      v5 = MbbAdapterQueryMultiCarrierDsCidList(a1, &MBB_UUID_USSD, a2);
      v6 = v5;
      if ( v5 && v5 != 259 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_15;
        v7 = 74;
        goto LABEL_7;
      }
    }
    if ( !v6 || v6 == 259 )
      return v6;
    goto LABEL_15;
  }
  v9 = 0;
  if ( MbbUtilFindDeviceService((struct _MINIPORT_ADAPTER_CONTEXT *)a1, (struct _GUID *)&MBB_UUID_USSD) )
  {
    v10 = KeAcquireSpinLockRaiseToDpc(a1);
    *((_DWORD *)a1 + 272) |= 2u;
    *((_BYTE *)a1 + 8) = v10;
    KeReleaseSpinLock(a1, v10);
  }
  DeviceService = MbbUtilFindDeviceService((struct _MINIPORT_ADAPTER_CONTEXT *)a1, (struct _GUID *)&MBB_UUID_AUTH);
  if ( DeviceService )
  {
    v12 = KeAcquireSpinLockRaiseToDpc(a1);
    *((_BYTE *)a1 + 8) = v12;
    for ( i = 0; i < *((_DWORD *)DeviceService + 6); ++i )
    {
      switch ( *(_DWORD *)(*((_QWORD *)DeviceService + 4) + 4LL * i) )
      {
        case 1:
          *((_DWORD *)a1 + 272) |= 8u;
          break;
        case 2:
          *((_DWORD *)a1 + 272) |= 0x10u;
          break;
        case 3:
          *((_DWORD *)a1 + 272) |= 4u;
          break;
      }
    }
    KeReleaseSpinLock(a1, v12);
  }
  *((_DWORD *)v2 + 195) |= 3u;
  return v9;
}

```

## disassembly

```asm
0x140002edc  push    rbx
0x140002ede  push    rbp
0x140002edf  push    rsi
0x140002ee0  push    rdi
0x140002ee1  push    r12
0x140002ee3  push    r14
0x140002ee5  push    r15
0x140002ee7  sub     rsp, 40h
0x140002eeb  mov     rax, [rdx+318h]
0x140002ef2  mov     rbp, rdx
0x140002ef5  mov     rdi, rcx
0x140002ef8  mov     r8d, [rax+68h]
0x140002efc  test    r8b, 20h
0x140002f00  jz      loc_140002FF8
0x140002f06  mov     eax, [rdx+30Ch]
0x140002f0c  lea     r15, WPP_RECORDER_INITIALIZED
0x140002f13  lea     r12, WPP_94691144733c3f1d26776b6e97df90bb_Traceguids
0x140002f1a  mov     r14d, 103h
0x140002f20  test    al, 1
0x140002f22  jnz     short loc_140002F77
0x140002f24  mov     r8, rdx; struct _MBB_REQUEST_CONTEXT *
0x140002f27  lea     rdx, MBB_UUID_USSD; struct _GUID *
0x140002f2e  call    ?MbbAdapterQueryMultiCarrierDsCidList@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@PEBU_GUID@@PEAU_MBB_REQUEST_CONTEXT@@@Z; MbbAdapterQueryMultiCarrierDsCidList(_MINIPORT_ADAPTER_CONTEXT *,_GUID const *,_MBB_REQUEST_CONTEXT *)
0x140002f33  mov     ebx, eax
0x140002f35  test    eax, eax
0x140002f37  jz      short loc_140002FA8
0x140002f39  cmp     eax, r14d
0x140002f3c  jz      short loc_140002FA8
0x140002f3e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140002f45  jz      short loc_140002FB1
0x140002f47  mov     r9d, 4Ah ; 'J'
0x140002f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f54  mov     r8d, 3
0x140002f5a  mov     eax, [rbp+10h]
0x140002f5d  mov     dl, 2
0x140002f5f  mov     [rsp+78h+var_48], ebx
0x140002f63  mov     [rsp+78h+var_50], eax
0x140002f67  mov     rcx, [rcx+40h]
0x140002f6b  mov     [rsp+78h+var_58], r12
0x140002f70  call    WPP_RECORDER_SF_DD
0x140002f75  jmp     short loc_140002FB1
0x140002f77  xor     esi, esi
0x140002f79  mov     ebx, esi
0x140002f7b  test    al, 2
0x140002f7d  jnz     short loc_140002FA8
0x140002f7f  mov     r8, rbp; struct _MBB_REQUEST_CONTEXT *
0x140002f82  lea     rdx, MBB_UUID_AUTH; struct _GUID *
0x140002f89  call    ?MbbAdapterQueryMultiCarrierDsCidList@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@PEBU_GUID@@PEAU_MBB_REQUEST_CONTEXT@@@Z; MbbAdapterQueryMultiCarrierDsCidList(_MINIPORT_ADAPTER_CONTEXT *,_GUID const *,_MBB_REQUEST_CONTEXT *)
0x140002f8e  mov     ebx, eax
0x140002f90  test    eax, eax
0x140002f92  jz      short loc_140002FA8
0x140002f94  cmp     eax, r14d
0x140002f97  jz      short loc_140002FA8
0x140002f99  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140002fa0  jz      short loc_140002FB1
0x140002fa2  lea     r9d, [rsi+4Bh]
0x140002fa6  jmp     short loc_140002F4D
0x140002fa8  test    ebx, ebx
0x140002faa  jz      short loc_140002FF1
0x140002fac  cmp     ebx, r14d
0x140002faf  jz      short loc_140002FF1
0x140002fb1  mov     esi, ebx
0x140002fb3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140002fba  jz      loc_1400030BE
0x140002fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fc7  mov     r9d, 4Ch ; 'L'
0x140002fcd  mov     eax, [rbp+10h]
0x140002fd0  mov     dl, 2
0x140002fd2  mov     [rsp+78h+var_48], ebx
0x140002fd6  mov     [rsp+78h+var_50], eax
0x140002fda  mov     rcx, [rcx+40h]
0x140002fde  lea     r8d, [r9-49h]
0x140002fe2  mov     [rsp+78h+var_58], r12
0x140002fe7  call    WPP_RECORDER_SF_DD
0x140002fec  jmp     loc_1400030BE
0x140002ff1  mov     esi, ebx
0x140002ff3  jmp     loc_1400030BE
0x140002ff8  lea     rdx, MBB_UUID_USSD; struct _GUID *
0x140002fff  call    ?MbbUtilFindDeviceService@@YAPEAU_MBB_DS@@PEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_GUID@@@Z; MbbUtilFindDeviceService(_MINIPORT_ADAPTER_CONTEXT *,_GUID *)
0x140003004  xor     esi, esi
0x140003006  test    rax, rax
0x140003009  jz      short loc_140003035
0x14000300b  mov     rcx, rdi; SpinLock
0x14000300e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003015  nop     dword ptr [rax+rax+00h]
0x14000301a  or      dword ptr [rdi+440h], 2
0x140003021  mov     rcx, rdi; SpinLock
0x140003024  mov     dl, al; NewIrql
0x140003026  mov     [rdi+8], al
0x140003029  call    cs:__imp_KeReleaseSpinLock
0x140003030  nop     dword ptr [rax+rax+00h]
0x140003035  lea     rdx, MBB_UUID_AUTH; struct _GUID *
0x14000303c  mov     rcx, rdi; struct _MINIPORT_ADAPTER_CONTEXT *
0x14000303f  call    ?MbbUtilFindDeviceService@@YAPEAU_MBB_DS@@PEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_GUID@@@Z; MbbUtilFindDeviceService(_MINIPORT_ADAPTER_CONTEXT *,_GUID *)
0x140003044  mov     r14, rax
0x140003047  test    rax, rax
0x14000304a  jz      short loc_1400030B7
0x14000304c  mov     rcx, rdi; SpinLock
0x14000304f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003056  nop     dword ptr [rax+rax+00h]
0x14000305b  mov     [rdi+8], al
0x14000305e  mov     r9d, esi
0x140003061  cmp     [r14+18h], esi
0x140003065  jbe     short loc_1400030A6
0x140003067  mov     rcx, [r14+20h]
0x14000306b  mov     edx, r9d
0x14000306e  mov     r8d, [rcx+rdx*4]
0x140003072  sub     r8d, 1
0x140003076  jz      short loc_140003096
0x140003078  sub     r8d, 1
0x14000307c  jz      short loc_14000308D
0x14000307e  cmp     r8d, 1
0x140003082  jnz     short loc_14000309D
0x140003084  or      dword ptr [rdi+440h], 4
0x14000308b  jmp     short loc_14000309D
0x14000308d  or      dword ptr [rdi+440h], 10h
0x140003094  jmp     short loc_14000309D
0x140003096  or      dword ptr [rdi+440h], 8
0x14000309d  inc     r9d
0x1400030a0  cmp     r9d, [r14+18h]
0x1400030a4  jb      short loc_140003067
0x1400030a6  mov     dl, al; NewIrql
0x1400030a8  mov     rcx, rdi; SpinLock
0x1400030ab  call    cs:__imp_KeReleaseSpinLock
0x1400030b2  nop     dword ptr [rax+rax+00h]
0x1400030b7  or      dword ptr [rbp+30Ch], 3
0x1400030be  mov     eax, esi
0x1400030c0  add     rsp, 40h
0x1400030c4  pop     r15
0x1400030c6  pop     r14
0x1400030c8  pop     r12
0x1400030ca  pop     rdi
0x1400030cb  pop     rsi
0x1400030cc  pop     rbp
0x1400030cd  pop     rbx
0x1400030ce  retn
```
