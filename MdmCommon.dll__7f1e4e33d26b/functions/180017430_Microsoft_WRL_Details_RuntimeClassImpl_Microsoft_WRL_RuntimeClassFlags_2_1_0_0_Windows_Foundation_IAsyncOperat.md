# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::QueryInterface(_GUID const &,void * *)

- ea: `0x180017430`
- end: `0x1800174a4`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180017430`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::QueryInterface(
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
    if ( *a2 != 1986569988
      || a2[1] != *(_DWORD *)&GUID_7668a704_244e_5e12_8dcb_92a3299eba26.Data2
      || a2[2] != *(_DWORD *)GUID_7668a704_244e_5e12_8dcb_92a3299eba26.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_7668a704_244e_5e12_8dcb_92a3299eba26.Data4[4];
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
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x180017430  push    rbx
0x180017432  sub     rsp, 20h
0x180017436  xor     ebx, ebx
0x180017438  mov     [r8], rbx
0x18001743b  cmp     [rdx], ebx
0x18001743d  jnz     short loc_180017471
0x18001743f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180017445  cmp     [rdx+4], eax
0x180017448  jnz     short loc_180017497
0x18001744a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180017450  cmp     [rdx+8], eax
0x180017453  jnz     short loc_180017497
0x180017455  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18001745b  cmp     [rdx+0Ch], eax
0x18001745e  jnz     short loc_180017497
0x180017460  mov     [r8], rcx
0x180017463  mov     rax, [rcx]
0x180017466  mov     rax, [rax+8]
0x18001746a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001746f  jmp     short loc_18001749C
0x180017471  cmp     dword ptr [rdx], 7668A704h
0x180017477  jnz     short loc_180017497
0x180017479  mov     eax, dword ptr cs:_GUID_7668a704_244e_5e12_8dcb_92a3299eba26.Data2
0x18001747f  cmp     [rdx+4], eax
0x180017482  jnz     short loc_180017497
0x180017484  mov     eax, dword ptr cs:_GUID_7668a704_244e_5e12_8dcb_92a3299eba26.Data4
0x18001748a  cmp     [rdx+8], eax
0x18001748d  jnz     short loc_180017497
0x18001748f  mov     eax, dword ptr cs:_GUID_7668a704_244e_5e12_8dcb_92a3299eba26.Data4+4
0x180017495  jmp     short loc_18001745B
0x180017497  mov     ebx, 80004002h
0x18001749c  mov     eax, ebx
0x18001749e  add     rsp, 20h
0x1800174a2  pop     rbx
0x1800174a3  retn
```
