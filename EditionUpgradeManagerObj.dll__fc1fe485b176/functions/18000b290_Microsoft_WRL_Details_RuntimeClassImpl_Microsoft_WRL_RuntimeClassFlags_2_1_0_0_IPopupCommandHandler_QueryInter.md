# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommandHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000b290`
- end: `0x18000b304`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPopupCommandHandler@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b290`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommandHandler>::QueryInterface(
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
    if ( *a2 != 1302534674
      || a2[1] != *(_DWORD *)&GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data2
      || a2[2] != *(_DWORD *)GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data4[4];
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
0x18000b290  push    rbx
0x18000b292  sub     rsp, 20h
0x18000b296  xor     ebx, ebx
0x18000b298  mov     [r8], rbx
0x18000b29b  cmp     [rdx], ebx
0x18000b29d  jnz     short loc_18000B2D1
0x18000b29f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000b2a5  cmp     [rdx+4], eax
0x18000b2a8  jnz     short loc_18000B2F7
0x18000b2aa  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000b2b0  cmp     [rdx+8], eax
0x18000b2b3  jnz     short loc_18000B2F7
0x18000b2b5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000b2bb  cmp     [rdx+0Ch], eax
0x18000b2be  jnz     short loc_18000B2F7
0x18000b2c0  mov     [r8], rcx
0x18000b2c3  mov     rax, [rcx]
0x18000b2c6  mov     rax, [rax+8]
0x18000b2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2cf  jmp     short loc_18000B2FC
0x18000b2d1  cmp     dword ptr [rdx], 4DA31A12h
0x18000b2d7  jnz     short loc_18000B2F7
0x18000b2d9  mov     eax, dword ptr cs:_GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data2
0x18000b2df  cmp     [rdx+4], eax
0x18000b2e2  jnz     short loc_18000B2F7
0x18000b2e4  mov     eax, dword ptr cs:_GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data4
0x18000b2ea  cmp     [rdx+8], eax
0x18000b2ed  jnz     short loc_18000B2F7
0x18000b2ef  mov     eax, dword ptr cs:_GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data4+4
0x18000b2f5  jmp     short loc_18000B2BB
0x18000b2f7  mov     ebx, 80004002h
0x18000b2fc  mov     eax, ebx
0x18000b2fe  add     rsp, 20h
0x18000b302  pop     rbx
0x18000b303  retn
```
