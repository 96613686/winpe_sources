# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::QueryInterface(_GUID const &,void * *)

- ea: `0x180017950`
- end: `0x1800179c5`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180017950`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180017950  push    rbx
0x180017952  sub     rsp, 20h
0x180017956  xor     ebx, ebx
0x180017958  mov     [r8], rbx
0x18001795b  cmp     [rdx], ebx
0x18001795d  jnz     short loc_180017991
0x18001795f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180017965  cmp     [rdx+4], eax
0x180017968  jnz     short loc_1800179B7
0x18001796a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180017970  cmp     [rdx+8], eax
0x180017973  jnz     short loc_1800179B7
0x180017975  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18001797b  cmp     [rdx+0Ch], eax
0x18001797e  jnz     short loc_1800179B7
0x180017980  mov     [r8], rcx
0x180017983  mov     rax, [rcx]
0x180017986  mov     rax, [rax+8]
0x18001798a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001798f  jmp     short loc_1800179BC
0x180017991  cmp     dword ptr [rdx], 7668A704h
0x180017997  jnz     short loc_1800179B7
0x180017999  mov     eax, dword ptr cs:_GUID_7668a704_244e_5e12_8dcb_92a3299eba26.Data2
0x18001799f  cmp     [rdx+4], eax
0x1800179a2  jnz     short loc_1800179B7
0x1800179a4  mov     eax, dword ptr cs:_GUID_7668a704_244e_5e12_8dcb_92a3299eba26.Data4
0x1800179aa  cmp     [rdx+8], eax
0x1800179ad  jnz     short loc_1800179B7
0x1800179af  mov     eax, dword ptr cs:_GUID_7668a704_244e_5e12_8dcb_92a3299eba26.Data4+4
0x1800179b5  jmp     short loc_18001797B
0x1800179b7  mov     ebx, 80004002h
0x1800179bc  mov     eax, ebx
0x1800179be  add     rsp, 20h
0x1800179c2  pop     rbx
0x1800179c3  retn
```
