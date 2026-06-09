# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006a70`
- end: `0x180006b4e`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006b60`

## callees

- `0x180006a70`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -1121677709
      && a2[1] == *(_DWORD *)&GUID_bd248e73_f05f_574c_ae3d_9b95c4bf282a.Data2
      && a2[2] == *(_DWORD *)GUID_bd248e73_f05f_574c_ae3d_9b95c4bf282a.Data4
      && a2[3] == *(_DWORD *)&GUID_bd248e73_f05f_574c_ae3d_9b95c4bf282a.Data4[4] )
    {
      *a3 = a1;
LABEL_22:
      a1 = *a3;
      goto LABEL_6;
    }
LABEL_12:
    v4 = a1 + 8;
    if ( *a2 == -1796592748 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
        || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
    }
    else
    {
      if ( *a2 != 3
        || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
        || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
    }
    if ( a2[3] == v5 )
    {
      *a3 = v4;
      goto LABEL_22;
    }
    return (unsigned int)-2147467262;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_12;
  }
  *a3 = a1;
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x180006a70  push    rbx
0x180006a72  sub     rsp, 20h
0x180006a76  xor     ebx, ebx
0x180006a78  mov     [r8], rbx
0x180006a7b  cmp     [rdx], ebx
0x180006a7d  jnz     short loc_180006AB4
0x180006a7f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180006a85  cmp     [rdx+4], eax
0x180006a88  jnz     short loc_180006AE2
0x180006a8a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180006a90  cmp     [rdx+8], eax
0x180006a93  jnz     short loc_180006AE2
0x180006a95  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180006a9b  cmp     [rdx+0Ch], eax
0x180006a9e  jnz     short loc_180006AE2
0x180006aa0  mov     [r8], rcx
0x180006aa3  mov     rax, [rcx]
0x180006aa6  mov     rax, [rax+8]
0x180006aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aaf  jmp     loc_180006B45
0x180006ab4  cmp     dword ptr [rdx], 0BD248E73h
0x180006aba  jnz     short loc_180006AE2
0x180006abc  mov     eax, dword ptr cs:_GUID_bd248e73_f05f_574c_ae3d_9b95c4bf282a.Data2
0x180006ac2  cmp     [rdx+4], eax
0x180006ac5  jnz     short loc_180006AE2
0x180006ac7  mov     eax, dword ptr cs:_GUID_bd248e73_f05f_574c_ae3d_9b95c4bf282a.Data4
0x180006acd  cmp     [rdx+8], eax
0x180006ad0  jnz     short loc_180006AE2
0x180006ad2  mov     eax, dword ptr cs:_GUID_bd248e73_f05f_574c_ae3d_9b95c4bf282a.Data4+4
0x180006ad8  cmp     [rdx+0Ch], eax
0x180006adb  jnz     short loc_180006AE2
0x180006add  mov     [r8], rcx
0x180006ae0  jmp     short loc_180006B38
0x180006ae2  add     rcx, 8
0x180006ae6  cmp     dword ptr [rdx], 94EA2B94h
0x180006aec  jnz     short loc_180006B0C
0x180006aee  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x180006af4  cmp     [rdx+4], eax
0x180006af7  jnz     short loc_180006B40
0x180006af9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x180006aff  cmp     [rdx+8], eax
0x180006b02  jnz     short loc_180006B40
0x180006b04  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x180006b0a  jmp     short loc_180006B2D
0x180006b0c  cmp     dword ptr [rdx], 3
0x180006b0f  jnz     short loc_180006B40
0x180006b11  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180006b17  cmp     [rdx+4], eax
0x180006b1a  jnz     short loc_180006B40
0x180006b1c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180006b22  cmp     [rdx+8], eax
0x180006b25  jnz     short loc_180006B40
0x180006b27  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x180006b2d  cmp     [rdx+0Ch], eax
0x180006b30  jnz     short loc_180006B40
0x180006b32  mov     rax, r8
0x180006b35  mov     [rax], rcx
0x180006b38  mov     rcx, [r8]
0x180006b3b  jmp     loc_180006AA3
0x180006b40  mov     ebx, 80004002h
0x180006b45  mov     eax, ebx
0x180006b47  add     rsp, 20h
0x180006b4b  pop     rbx
0x180006b4c  retn
```
