# Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x180003d80`
- end: `0x180003e4f`
- name: `?QueryInterface@?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `207`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003e60`
- `0x180003e70`

## callees

- `0x180003d80`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
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
    if ( *a2 != -1350114592 )
    {
      if ( *a2 == 53 )
      {
        if ( a2[1] != *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data2
          || a2[2] != *(_DWORD *)GUID_00000035_0000_0000_c000_000000000046.Data4
          || a2[3] != *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data4[4] )
        {
          return (unsigned int)-2147467262;
        }
      }
      else
      {
        if ( *a2 != -1288957124
          || a2[1] != *(_DWORD *)&GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data2
          || a2[2] != *(_DWORD *)GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data4
          || a2[3] != *(_DWORD *)&GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data4[4] )
        {
          return (unsigned int)-2147467262;
        }
        a1 += 8;
      }
      *a3 = a1;
      goto LABEL_11;
    }
    if ( a2[1] != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
      || a2[2] != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4];
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
  *a3 = a1;
LABEL_11:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x180003d80  push    rbx
0x180003d82  sub     rsp, 20h
0x180003d86  xor     ebx, ebx
0x180003d88  mov     [r8], rbx
0x180003d8b  cmp     [rdx], ebx
0x180003d8d  jnz     short loc_180003DAD
0x180003d8f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180003d95  cmp     [rdx+4], eax
0x180003d98  jnz     short loc_180003E0D
0x180003d9a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180003da0  cmp     [rdx+8], eax
0x180003da3  jnz     short loc_180003E0D
0x180003da5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180003dab  jmp     short loc_180003DD1
0x180003dad  cmp     dword ptr [rdx], 0AF86E2E0h
0x180003db3  jnz     short loc_180003DE7
0x180003db5  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x180003dbb  cmp     [rdx+4], eax
0x180003dbe  jnz     short loc_180003E0D
0x180003dc0  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x180003dc6  cmp     [rdx+8], eax
0x180003dc9  jnz     short loc_180003E0D
0x180003dcb  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x180003dd1  cmp     [rdx+0Ch], eax
0x180003dd4  jnz     short loc_180003E0D
0x180003dd6  mov     [r8], rcx
0x180003dd9  mov     rax, [rcx]
0x180003ddc  mov     rax, [rax+8]
0x180003de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003de5  jmp     short loc_180003E12
0x180003de7  cmp     dword ptr [rdx], 35h ; '5'
0x180003dea  jnz     short loc_180003E1A
0x180003dec  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x180003df2  cmp     [rdx+4], eax
0x180003df5  jnz     short loc_180003E0D
0x180003df7  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x180003dfd  cmp     [rdx+8], eax
0x180003e00  jnz     short loc_180003E0D
0x180003e02  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x180003e08  cmp     [rdx+0Ch], eax
0x180003e0b  jz      short loc_180003E47
0x180003e0d  mov     ebx, 80004002h
0x180003e12  mov     eax, ebx
0x180003e14  add     rsp, 20h
0x180003e18  pop     rbx
0x180003e19  retn
0x180003e1a  cmp     dword ptr [rdx], 0B32C133Ch
0x180003e20  jnz     short loc_180003E0D
0x180003e22  mov     eax, dword ptr cs:_GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data2
0x180003e28  cmp     [rdx+4], eax
0x180003e2b  jnz     short loc_180003E0D
0x180003e2d  mov     eax, dword ptr cs:_GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data4
0x180003e33  cmp     [rdx+8], eax
0x180003e36  jnz     short loc_180003E0D
0x180003e38  mov     eax, dword ptr cs:_GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data4+4
0x180003e3e  cmp     [rdx+0Ch], eax
0x180003e41  jnz     short loc_180003E0D
0x180003e43  add     rcx, 8
0x180003e47  mov     rax, rcx
0x180003e4a  mov     [r8], rcx
0x180003e4d  jmp     short loc_180003DD9
```
