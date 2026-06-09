# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)

- ea: `0x1800035fc`
- end: `0x180003692`
- name: `?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002ba0`
- `0x180003f50`

## callees

- `0x1800035fc`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 result; // rax
  __int64 v4; // rcx

  if ( *a2 == 53
    && a2[1] == *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000035_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data4[4] )
  {
    *a3 = a1;
    return 0;
  }
  v4 = a1 + 8;
  if ( *a2 == 1230592208 )
  {
    if ( a2[1] == *(_DWORD *)&GUID_495958d0_37b1_494b_90a4_07258caf648f.Data2
      && a2[2] == *(_DWORD *)GUID_495958d0_37b1_494b_90a4_07258caf648f.Data4
      && a2[3] == *(_DWORD *)&GUID_495958d0_37b1_494b_90a4_07258caf648f.Data4[4] )
    {
      result = 0;
LABEL_16:
      *a3 = v4;
      return result;
    }
  }
  else if ( *a2 == 1407391799
         && a2[1] == *(_DWORD *)&GUID_53e31837_6600_4a81_9395_75cffe746f94.Data2
         && a2[2] == *(_DWORD *)GUID_53e31837_6600_4a81_9395_75cffe746f94.Data4
         && a2[3] == *(_DWORD *)&GUID_53e31837_6600_4a81_9395_75cffe746f94.Data4[4] )
  {
    result = 0;
    v4 += 8;
    goto LABEL_16;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x1800035fc  cmp     dword ptr [rdx], 35h ; '5'
0x1800035ff  jnz     short loc_180003628
0x180003601  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x180003607  cmp     [rdx+4], eax
0x18000360a  jnz     short loc_180003628
0x18000360c  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x180003612  cmp     [rdx+8], eax
0x180003615  jnz     short loc_180003628
0x180003617  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x18000361d  cmp     [rdx+0Ch], eax
0x180003620  jnz     short loc_180003628
0x180003622  mov     [r8], rcx
0x180003625  xor     eax, eax
0x180003627  retn
0x180003628  add     rcx, 8
0x18000362c  cmp     dword ptr [rdx], 495958D0h
0x180003632  jnz     short loc_180003659
0x180003634  mov     eax, dword ptr cs:_GUID_495958d0_37b1_494b_90a4_07258caf648f.Data2
0x18000363a  cmp     [rdx+4], eax
0x18000363d  jnz     short loc_18000368C
0x18000363f  mov     eax, dword ptr cs:_GUID_495958d0_37b1_494b_90a4_07258caf648f.Data4
0x180003645  cmp     [rdx+8], eax
0x180003648  jnz     short loc_18000368C
0x18000364a  mov     eax, dword ptr cs:_GUID_495958d0_37b1_494b_90a4_07258caf648f.Data4+4
0x180003650  cmp     [rdx+0Ch], eax
0x180003653  jnz     short loc_18000368C
0x180003655  xor     eax, eax
0x180003657  jmp     short loc_180003688
0x180003659  cmp     dword ptr [rdx], 53E31837h
0x18000365f  jnz     short loc_18000368C
0x180003661  mov     eax, dword ptr cs:_GUID_53e31837_6600_4a81_9395_75cffe746f94.Data2
0x180003667  cmp     [rdx+4], eax
0x18000366a  jnz     short loc_18000368C
0x18000366c  mov     eax, dword ptr cs:_GUID_53e31837_6600_4a81_9395_75cffe746f94.Data4
0x180003672  cmp     [rdx+8], eax
0x180003675  jnz     short loc_18000368C
0x180003677  mov     eax, dword ptr cs:_GUID_53e31837_6600_4a81_9395_75cffe746f94.Data4+4
0x18000367d  cmp     [rdx+0Ch], eax
0x180003680  jnz     short loc_18000368C
0x180003682  xor     eax, eax
0x180003684  add     rcx, 8
0x180003688  mov     [r8], rcx
0x18000368b  retn
0x18000368c  mov     eax, 80004002h
0x180003691  retn
```
