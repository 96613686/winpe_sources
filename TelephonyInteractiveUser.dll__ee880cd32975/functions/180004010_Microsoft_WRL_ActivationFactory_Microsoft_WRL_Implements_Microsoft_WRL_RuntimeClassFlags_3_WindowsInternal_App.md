# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004010`
- end: `0x1800040de`
- name: `?QueryInterface@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800032d0`
- `0x1800040f0`
- `0x1800041d0`

## callees

- `0x180004010`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  int v4; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -1350114592 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
        || a2[2] != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v4 = *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4];
    }
    else
    {
      if ( *a2 != 53 )
      {
        if ( *a2 == -621168275
          && a2[1] == *(_DWORD *)&GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data2
          && a2[2] == *(_DWORD *)GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data4
          && a2[3] == *(_DWORD *)&GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data4[4] )
        {
          a1 += 8;
          goto LABEL_10;
        }
        return (unsigned int)-2147467262;
      }
      if ( a2[1] != *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data2
        || a2[2] != *(_DWORD *)GUID_00000035_0000_0000_c000_000000000046.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v4 = *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data4[4];
    }
  }
  else
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] != v4 )
    return (unsigned int)-2147467262;
LABEL_10:
  *a3 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x180004010  push    rbx
0x180004012  sub     rsp, 20h
0x180004016  xor     ebx, ebx
0x180004018  mov     [r8], rbx
0x18000401b  cmp     [rdx], ebx
0x18000401d  jnz     short loc_180004045
0x18000401f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180004025  cmp     [rdx+4], eax
0x180004028  jnz     loc_1800040D1
0x18000402e  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180004034  cmp     [rdx+8], eax
0x180004037  jnz     loc_1800040D1
0x18000403d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180004043  jmp     short loc_180004069
0x180004045  cmp     dword ptr [rdx], 0AF86E2E0h
0x18000404b  jnz     short loc_18000407F
0x18000404d  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x180004053  cmp     [rdx+4], eax
0x180004056  jnz     short loc_1800040D1
0x180004058  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000405e  cmp     [rdx+8], eax
0x180004061  jnz     short loc_1800040D1
0x180004063  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x180004069  cmp     [rdx+0Ch], eax
0x18000406c  jnz     short loc_1800040D1
0x18000406e  mov     [r8], rcx
0x180004071  mov     rax, [rcx]
0x180004074  mov     rax, [rax+8]
0x180004078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000407d  jmp     short loc_1800040D6
0x18000407f  cmp     dword ptr [rdx], 35h ; '5'
0x180004082  jnz     short loc_1800040A2
0x180004084  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x18000408a  cmp     [rdx+4], eax
0x18000408d  jnz     short loc_1800040D1
0x18000408f  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x180004095  cmp     [rdx+8], eax
0x180004098  jnz     short loc_1800040D1
0x18000409a  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x1800040a0  jmp     short loc_180004069
0x1800040a2  cmp     dword ptr [rdx], 0DAF9B96Dh
0x1800040a8  jnz     short loc_1800040D1
0x1800040aa  mov     eax, dword ptr cs:_GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data2
0x1800040b0  cmp     [rdx+4], eax
0x1800040b3  jnz     short loc_1800040D1
0x1800040b5  mov     eax, dword ptr cs:_GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data4
0x1800040bb  cmp     [rdx+8], eax
0x1800040be  jnz     short loc_1800040D1
0x1800040c0  mov     eax, dword ptr cs:_GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data4+4
0x1800040c6  cmp     [rdx+0Ch], eax
0x1800040c9  jnz     short loc_1800040D1
0x1800040cb  add     rcx, 8
0x1800040cf  jmp     short loc_18000406E
0x1800040d1  mov     ebx, 80004002h
0x1800040d6  mov     eax, ebx
0x1800040d8  add     rsp, 20h
0x1800040dc  pop     rbx
0x1800040dd  retn
```
