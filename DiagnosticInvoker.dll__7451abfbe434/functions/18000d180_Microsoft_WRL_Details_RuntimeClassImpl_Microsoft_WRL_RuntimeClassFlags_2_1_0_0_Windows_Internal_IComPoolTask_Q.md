# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000d180`
- end: `0x18000d1f4`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d180`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::QueryInterface(
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
    if ( *a2 != 1204800526
      || a2[1] != *(_DWORD *)&GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data2
      || a2[2] != *(_DWORD *)GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4[4];
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
0x18000d180  push    rbx
0x18000d182  sub     rsp, 20h
0x18000d186  xor     ebx, ebx
0x18000d188  mov     [r8], rbx
0x18000d18b  cmp     [rdx], ebx
0x18000d18d  jnz     short loc_18000D1C1
0x18000d18f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000d195  cmp     [rdx+4], eax
0x18000d198  jnz     short loc_18000D1E7
0x18000d19a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000d1a0  cmp     [rdx+8], eax
0x18000d1a3  jnz     short loc_18000D1E7
0x18000d1a5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000d1ab  cmp     [rdx+0Ch], eax
0x18000d1ae  jnz     short loc_18000D1E7
0x18000d1b0  mov     [r8], rcx
0x18000d1b3  mov     rax, [rcx]
0x18000d1b6  mov     rax, [rax+8]
0x18000d1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1bf  jmp     short loc_18000D1EC
0x18000d1c1  cmp     dword ptr [rdx], 47CFCC0Eh
0x18000d1c7  jnz     short loc_18000D1E7
0x18000d1c9  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data2
0x18000d1cf  cmp     [rdx+4], eax
0x18000d1d2  jnz     short loc_18000D1E7
0x18000d1d4  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4
0x18000d1da  cmp     [rdx+8], eax
0x18000d1dd  jnz     short loc_18000D1E7
0x18000d1df  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4+4
0x18000d1e5  jmp     short loc_18000D1AB
0x18000d1e7  mov     ebx, 80004002h
0x18000d1ec  mov     eax, ebx
0x18000d1ee  add     rsp, 20h
0x18000d1f2  pop     rbx
0x18000d1f3  retn
```
