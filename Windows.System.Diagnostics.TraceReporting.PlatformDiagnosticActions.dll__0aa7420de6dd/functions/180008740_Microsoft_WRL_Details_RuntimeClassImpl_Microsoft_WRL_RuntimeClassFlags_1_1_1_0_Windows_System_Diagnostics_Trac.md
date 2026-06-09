# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticTraceInfo>::QueryInterface(_GUID const &,void * *)

- ea: `0x180008740`
- end: `0x180008810`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIPlatformDiagnosticTraceInfo@TraceReporting@Diagnostics@System@Windows@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `208`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008820`
- `0x1800089d0`

## callees

- `0x180008740`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticTraceInfo>::QueryInterface(
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
      if ( *a2 == -126816873 )
      {
        if ( a2[1] != *(_DWORD *)&GUID_f870ed97_d597_4bf7_88dc_cf5c7dc2a1d2.Data2
          || a2[2] != *(_DWORD *)GUID_f870ed97_d597_4bf7_88dc_cf5c7dc2a1d2.Data4
          || a2[3] != *(_DWORD *)&GUID_f870ed97_d597_4bf7_88dc_cf5c7dc2a1d2.Data4[4] )
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
0x180008740  push    rbx
0x180008742  sub     rsp, 20h
0x180008746  xor     ebx, ebx
0x180008748  mov     [r8], rbx
0x18000874b  cmp     [rdx], ebx
0x18000874d  jnz     short loc_18000876D
0x18000874f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180008755  cmp     [rdx+4], eax
0x180008758  jnz     short loc_1800087D0
0x18000875a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180008760  cmp     [rdx+8], eax
0x180008763  jnz     short loc_1800087D0
0x180008765  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000876b  jmp     short loc_180008791
0x18000876d  cmp     dword ptr [rdx], 0AF86E2E0h
0x180008773  jnz     short loc_1800087A7
0x180008775  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000877b  cmp     [rdx+4], eax
0x18000877e  jnz     short loc_1800087D0
0x180008780  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x180008786  cmp     [rdx+8], eax
0x180008789  jnz     short loc_1800087D0
0x18000878b  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x180008791  cmp     [rdx+0Ch], eax
0x180008794  jnz     short loc_1800087D0
0x180008796  mov     [r8], rcx
0x180008799  mov     rax, [rcx]
0x18000879c  mov     rax, [rax+8]
0x1800087a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087a5  jmp     short loc_1800087D5
0x1800087a7  cmp     dword ptr [rdx], 0F870ED97h
0x1800087ad  jnz     short loc_1800087DD
0x1800087af  mov     eax, dword ptr cs:_GUID_f870ed97_d597_4bf7_88dc_cf5c7dc2a1d2.Data2
0x1800087b5  cmp     [rdx+4], eax
0x1800087b8  jnz     short loc_1800087D0
0x1800087ba  mov     eax, dword ptr cs:_GUID_f870ed97_d597_4bf7_88dc_cf5c7dc2a1d2.Data4
0x1800087c0  cmp     [rdx+8], eax
0x1800087c3  jnz     short loc_1800087D0
0x1800087c5  mov     eax, dword ptr cs:_GUID_f870ed97_d597_4bf7_88dc_cf5c7dc2a1d2.Data4+4
0x1800087cb  cmp     [rdx+0Ch], eax
0x1800087ce  jz      short loc_180008807
0x1800087d0  mov     ebx, 80004002h
0x1800087d5  mov     eax, ebx
0x1800087d7  add     rsp, 20h
0x1800087db  pop     rbx
0x1800087dc  retn
0x1800087dd  cmp     dword ptr [rdx], 38h ; '8'
0x1800087e0  jnz     short loc_1800087D0
0x1800087e2  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x1800087e8  cmp     [rdx+4], eax
0x1800087eb  jnz     short loc_1800087D0
0x1800087ed  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x1800087f3  cmp     [rdx+8], eax
0x1800087f6  jnz     short loc_1800087D0
0x1800087f8  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x1800087fe  cmp     [rdx+0Ch], eax
0x180008801  jnz     short loc_1800087D0
0x180008803  add     rcx, 8
0x180008807  mov     rax, rcx
0x18000880a  mov     [r8], rcx
0x18000880d  jmp     short loc_180008799
```
