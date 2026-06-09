# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticTraceRuntimeInfo>::QueryInterface(_GUID const &,void * *)

- ea: `0x180008830`
- end: `0x180008900`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIPlatformDiagnosticTraceRuntimeInfo@TraceReporting@Diagnostics@System@Windows@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `208`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008910`
- `0x1800089f0`

## callees

- `0x180008830`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticTraceRuntimeInfo>::QueryInterface(
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
      if ( *a2 == 1028480557 )
      {
        if ( a2[1] != *(_DWORD *)&GUID_3d4d5e2d_01d8_4768_8554_1eb1ca610986.Data2
          || a2[2] != *(_DWORD *)GUID_3d4d5e2d_01d8_4768_8554_1eb1ca610986.Data4
          || a2[3] != *(_DWORD *)&GUID_3d4d5e2d_01d8_4768_8554_1eb1ca610986.Data4[4] )
        {
          return (unsigned int)-2147467262;
        }
      }
      else
      {
        if ( *a2 != 56
          || a2[1] != *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data2
          || a2[2] != *(_DWORD *)GUID_00000038_0000_0000_c000_000000000046.Data4
          || a2[3] != *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data4[4] )
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
0x180008830  push    rbx
0x180008832  sub     rsp, 20h
0x180008836  xor     ebx, ebx
0x180008838  mov     [r8], rbx
0x18000883b  cmp     [rdx], ebx
0x18000883d  jnz     short loc_18000885D
0x18000883f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180008845  cmp     [rdx+4], eax
0x180008848  jnz     short loc_1800088C0
0x18000884a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180008850  cmp     [rdx+8], eax
0x180008853  jnz     short loc_1800088C0
0x180008855  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000885b  jmp     short loc_180008881
0x18000885d  cmp     dword ptr [rdx], 0AF86E2E0h
0x180008863  jnz     short loc_180008897
0x180008865  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000886b  cmp     [rdx+4], eax
0x18000886e  jnz     short loc_1800088C0
0x180008870  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x180008876  cmp     [rdx+8], eax
0x180008879  jnz     short loc_1800088C0
0x18000887b  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x180008881  cmp     [rdx+0Ch], eax
0x180008884  jnz     short loc_1800088C0
0x180008886  mov     [r8], rcx
0x180008889  mov     rax, [rcx]
0x18000888c  mov     rax, [rax+8]
0x180008890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008895  jmp     short loc_1800088C5
0x180008897  cmp     dword ptr [rdx], 3D4D5E2Dh
0x18000889d  jnz     short loc_1800088CD
0x18000889f  mov     eax, dword ptr cs:_GUID_3d4d5e2d_01d8_4768_8554_1eb1ca610986.Data2
0x1800088a5  cmp     [rdx+4], eax
0x1800088a8  jnz     short loc_1800088C0
0x1800088aa  mov     eax, dword ptr cs:_GUID_3d4d5e2d_01d8_4768_8554_1eb1ca610986.Data4
0x1800088b0  cmp     [rdx+8], eax
0x1800088b3  jnz     short loc_1800088C0
0x1800088b5  mov     eax, dword ptr cs:_GUID_3d4d5e2d_01d8_4768_8554_1eb1ca610986.Data4+4
0x1800088bb  cmp     [rdx+0Ch], eax
0x1800088be  jz      short loc_1800088F7
0x1800088c0  mov     ebx, 80004002h
0x1800088c5  mov     eax, ebx
0x1800088c7  add     rsp, 20h
0x1800088cb  pop     rbx
0x1800088cc  retn
0x1800088cd  cmp     dword ptr [rdx], 38h ; '8'
0x1800088d0  jnz     short loc_1800088C0
0x1800088d2  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x1800088d8  cmp     [rdx+4], eax
0x1800088db  jnz     short loc_1800088C0
0x1800088dd  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x1800088e3  cmp     [rdx+8], eax
0x1800088e6  jnz     short loc_1800088C0
0x1800088e8  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x1800088ee  cmp     [rdx+0Ch], eax
0x1800088f1  jnz     short loc_1800088C0
0x1800088f3  add     rcx, 8
0x1800088f7  mov     rax, rcx
0x1800088fa  mov     [r8], rcx
0x1800088fd  jmp     short loc_180008889
```
