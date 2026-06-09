# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009eb0`
- end: `0x180009fdf`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEditionUpgradeBroker@@UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `303`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009ff0`
- `0x18000a000`
- `0x18000a010`

## callees

- `0x180009eb0`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v3; // ebx
  __int64 v4; // rcx

  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -15086641
      && a2[1] == *(_DWORD *)&GUID_ff19cbcf_9455_4937_b872_6b7929a460af.Data2
      && a2[2] == *(_DWORD *)GUID_ff19cbcf_9455_4937_b872_6b7929a460af.Data4
      && a2[3] == *(_DWORD *)&GUID_ff19cbcf_9455_4937_b872_6b7929a460af.Data4[4] )
    {
      goto LABEL_10;
    }
    goto LABEL_11;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
LABEL_11:
    a1 += 8;
    if ( *a2 != -1255868097
      || a2[1] != *(_DWORD *)&GUID_b524f93f_80d5_4ec7_ae9e_d66e93ade1fa.Data2
      || a2[2] != *(_DWORD *)GUID_b524f93f_80d5_4ec7_ae9e_d66e93ade1fa.Data4
      || a2[3] != *(_DWORD *)&GUID_b524f93f_80d5_4ec7_ae9e_d66e93ade1fa.Data4[4] )
    {
      v4 = a1 + 8;
      if ( *a2 == -1013364496 )
      {
        if ( a2[1] == *(_DWORD *)&GUID_c39948f0_6142_44fd_98ca_e1681a8d68b5.Data2
          && a2[2] == *(_DWORD *)GUID_c39948f0_6142_44fd_98ca_e1681a8d68b5.Data4
          && a2[3] == *(_DWORD *)&GUID_c39948f0_6142_44fd_98ca_e1681a8d68b5.Data4[4] )
        {
          *a3 = v4;
LABEL_20:
          v3 = 0;
          goto LABEL_27;
        }
      }
      else if ( *a2 == 1029586209
             && a2[1] == *(_DWORD *)&GUID_3d5e3d21_bd41_4c2a_a669_b17ce87fb50b.Data2
             && a2[2] == *(_DWORD *)GUID_3d5e3d21_bd41_4c2a_a669_b17ce87fb50b.Data4
             && a2[3] == *(_DWORD *)&GUID_3d5e3d21_bd41_4c2a_a669_b17ce87fb50b.Data4[4] )
      {
        *a3 = v4 + 8;
        goto LABEL_20;
      }
      v3 = -2147467262;
LABEL_27:
      if ( v3 < 0 )
        return (unsigned int)v3;
LABEL_28:
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
      return (unsigned int)v3;
    }
LABEL_10:
    *a3 = a1;
    v3 = 0;
    goto LABEL_28;
  }
  *a3 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x180009eb0  push    rbx
0x180009eb2  sub     rsp, 20h
0x180009eb6  mov     qword ptr [r8], 0
0x180009ebd  cmp     dword ptr [rdx], 0
0x180009ec0  jnz     short loc_180009EF9
0x180009ec2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180009ec8  cmp     [rdx+4], eax
0x180009ecb  jnz     short loc_180009F2C
0x180009ecd  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180009ed3  cmp     [rdx+8], eax
0x180009ed6  jnz     short loc_180009F2C
0x180009ed8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180009ede  cmp     [rdx+0Ch], eax
0x180009ee1  jnz     short loc_180009F2C
0x180009ee3  mov     [r8], rcx
0x180009ee6  mov     rax, [rcx]
0x180009ee9  mov     rax, [rax+8]
0x180009eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ef2  xor     ebx, ebx
0x180009ef4  jmp     loc_180009FD7
0x180009ef9  cmp     dword ptr [rdx], 0FF19CBCFh
0x180009eff  jnz     short loc_180009F2C
0x180009f01  mov     eax, dword ptr cs:_GUID_ff19cbcf_9455_4937_b872_6b7929a460af.Data2
0x180009f07  cmp     [rdx+4], eax
0x180009f0a  jnz     short loc_180009F2C
0x180009f0c  mov     eax, dword ptr cs:_GUID_ff19cbcf_9455_4937_b872_6b7929a460af.Data4
0x180009f12  cmp     [rdx+8], eax
0x180009f15  jnz     short loc_180009F2C
0x180009f17  mov     eax, dword ptr cs:_GUID_ff19cbcf_9455_4937_b872_6b7929a460af.Data4+4
0x180009f1d  cmp     [rdx+0Ch], eax
0x180009f20  jnz     short loc_180009F2C
0x180009f22  mov     [r8], rcx
0x180009f25  xor     ebx, ebx
0x180009f27  jmp     loc_180009FC8
0x180009f2c  add     rcx, 8
0x180009f30  cmp     dword ptr [rdx], 0B524F93Fh
0x180009f36  jnz     short loc_180009F59
0x180009f38  mov     eax, dword ptr cs:_GUID_b524f93f_80d5_4ec7_ae9e_d66e93ade1fa.Data2
0x180009f3e  cmp     [rdx+4], eax
0x180009f41  jnz     short loc_180009F59
0x180009f43  mov     eax, dword ptr cs:_GUID_b524f93f_80d5_4ec7_ae9e_d66e93ade1fa.Data4
0x180009f49  cmp     [rdx+8], eax
0x180009f4c  jnz     short loc_180009F59
0x180009f4e  mov     eax, dword ptr cs:_GUID_b524f93f_80d5_4ec7_ae9e_d66e93ade1fa.Data4+4
0x180009f54  cmp     [rdx+0Ch], eax
0x180009f57  jz      short loc_180009F22
0x180009f59  add     rcx, 8
0x180009f5d  cmp     dword ptr [rdx], 0C39948F0h
0x180009f63  jnz     short loc_180009F8D
0x180009f65  mov     eax, dword ptr cs:_GUID_c39948f0_6142_44fd_98ca_e1681a8d68b5.Data2
0x180009f6b  cmp     [rdx+4], eax
0x180009f6e  jnz     short loc_180009FBF
0x180009f70  mov     eax, dword ptr cs:_GUID_c39948f0_6142_44fd_98ca_e1681a8d68b5.Data4
0x180009f76  cmp     [rdx+8], eax
0x180009f79  jnz     short loc_180009FBF
0x180009f7b  mov     eax, dword ptr cs:_GUID_c39948f0_6142_44fd_98ca_e1681a8d68b5.Data4+4
0x180009f81  cmp     [rdx+0Ch], eax
0x180009f84  jnz     short loc_180009FBF
0x180009f86  mov     [r8], rcx
0x180009f89  xor     ebx, ebx
0x180009f8b  jmp     short loc_180009FC4
0x180009f8d  cmp     dword ptr [rdx], 3D5E3D21h
0x180009f93  jnz     short loc_180009FBF
0x180009f95  mov     eax, dword ptr cs:_GUID_3d5e3d21_bd41_4c2a_a669_b17ce87fb50b.Data2
0x180009f9b  cmp     [rdx+4], eax
0x180009f9e  jnz     short loc_180009FBF
0x180009fa0  mov     eax, dword ptr cs:_GUID_3d5e3d21_bd41_4c2a_a669_b17ce87fb50b.Data4
0x180009fa6  cmp     [rdx+8], eax
0x180009fa9  jnz     short loc_180009FBF
0x180009fab  mov     eax, dword ptr cs:_GUID_3d5e3d21_bd41_4c2a_a669_b17ce87fb50b.Data4+4
0x180009fb1  cmp     [rdx+0Ch], eax
0x180009fb4  jnz     short loc_180009FBF
0x180009fb6  lea     rax, [rcx+8]
0x180009fba  mov     [r8], rax
0x180009fbd  jmp     short loc_180009F89
0x180009fbf  mov     ebx, 80004002h
0x180009fc4  test    ebx, ebx
0x180009fc6  js      short loc_180009FD7
0x180009fc8  mov     rcx, [r8]
0x180009fcb  mov     rdx, [rcx]
0x180009fce  mov     rax, [rdx+8]
0x180009fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fd7  mov     eax, ebx
0x180009fd9  add     rsp, 20h
0x180009fdd  pop     rbx
0x180009fde  retn
```
