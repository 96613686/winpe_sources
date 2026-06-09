# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000dbd0`
- end: `0x18000dc44`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000dbd0`
- `0x180019010`

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
0x18000dbd0  push    rbx
0x18000dbd2  sub     rsp, 20h
0x18000dbd6  xor     ebx, ebx
0x18000dbd8  mov     [r8], rbx
0x18000dbdb  cmp     [rdx], ebx
0x18000dbdd  jnz     short loc_18000DC11
0x18000dbdf  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000dbe5  cmp     [rdx+4], eax
0x18000dbe8  jnz     short loc_18000DC37
0x18000dbea  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000dbf0  cmp     [rdx+8], eax
0x18000dbf3  jnz     short loc_18000DC37
0x18000dbf5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000dbfb  cmp     [rdx+0Ch], eax
0x18000dbfe  jnz     short loc_18000DC37
0x18000dc00  mov     [r8], rcx
0x18000dc03  mov     rax, [rcx]
0x18000dc06  mov     rax, [rax+8]
0x18000dc0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc0f  jmp     short loc_18000DC3C
0x18000dc11  cmp     dword ptr [rdx], 47CFCC0Eh
0x18000dc17  jnz     short loc_18000DC37
0x18000dc19  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data2
0x18000dc1f  cmp     [rdx+4], eax
0x18000dc22  jnz     short loc_18000DC37
0x18000dc24  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4
0x18000dc2a  cmp     [rdx+8], eax
0x18000dc2d  jnz     short loc_18000DC37
0x18000dc2f  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4+4
0x18000dc35  jmp     short loc_18000DBFB
0x18000dc37  mov     ebx, 80004002h
0x18000dc3c  mov     eax, ebx
0x18000dc3e  add     rsp, 20h
0x18000dc42  pop     rbx
0x18000dc43  retn
```
