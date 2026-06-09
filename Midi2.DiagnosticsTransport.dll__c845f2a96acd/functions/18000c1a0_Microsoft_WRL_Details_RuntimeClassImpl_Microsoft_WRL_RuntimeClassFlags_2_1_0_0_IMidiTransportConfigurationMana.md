# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c1a0`
- end: `0x18000c214`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMidiTransportConfigurationManager@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c1a0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager>::QueryInterface(
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
    if ( *a2 != -241314238
      || a2[1] != *(_DWORD *)&GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data2
      || a2[2] != *(_DWORD *)GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4[4];
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
0x18000c1a0  push    rbx
0x18000c1a2  sub     rsp, 20h
0x18000c1a6  xor     ebx, ebx
0x18000c1a8  mov     [r8], rbx
0x18000c1ab  cmp     [rdx], ebx
0x18000c1ad  jnz     short loc_18000C1E1
0x18000c1af  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000c1b5  cmp     [rdx+4], eax
0x18000c1b8  jnz     short loc_18000C207
0x18000c1ba  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000c1c0  cmp     [rdx+8], eax
0x18000c1c3  jnz     short loc_18000C207
0x18000c1c5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000c1cb  cmp     [rdx+0Ch], eax
0x18000c1ce  jnz     short loc_18000C207
0x18000c1d0  mov     [r8], rcx
0x18000c1d3  mov     rax, [rcx]
0x18000c1d6  mov     rax, [rax+8]
0x18000c1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1df  jmp     short loc_18000C20C
0x18000c1e1  cmp     dword ptr [rdx], 0F19DD642h
0x18000c1e7  jnz     short loc_18000C207
0x18000c1e9  mov     eax, dword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data2
0x18000c1ef  cmp     [rdx+4], eax
0x18000c1f2  jnz     short loc_18000C207
0x18000c1f4  mov     eax, dword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4
0x18000c1fa  cmp     [rdx+8], eax
0x18000c1fd  jnz     short loc_18000C207
0x18000c1ff  mov     eax, dword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4+4
0x18000c205  jmp     short loc_18000C1CB
0x18000c207  mov     ebx, 80004002h
0x18000c20c  mov     eax, ebx
0x18000c20e  add     rsp, 20h
0x18000c212  pop     rbx
0x18000c213  retn
```
