# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommandHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x140008da0`
- end: `0x140008e14`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPopupCommandHandler@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140008da0`
- `0x14000a010`

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
0x140008da0  push    rbx
0x140008da2  sub     rsp, 20h
0x140008da6  xor     ebx, ebx
0x140008da8  mov     [r8], rbx
0x140008dab  cmp     [rdx], ebx
0x140008dad  jnz     short loc_140008DE1
0x140008daf  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x140008db5  cmp     [rdx+4], eax
0x140008db8  jnz     short loc_140008E07
0x140008dba  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x140008dc0  cmp     [rdx+8], eax
0x140008dc3  jnz     short loc_140008E07
0x140008dc5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x140008dcb  cmp     [rdx+0Ch], eax
0x140008dce  jnz     short loc_140008E07
0x140008dd0  mov     [r8], rcx
0x140008dd3  mov     rax, [rcx]
0x140008dd6  mov     rax, [rax+8]
0x140008dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008ddf  jmp     short loc_140008E0C
0x140008de1  cmp     dword ptr [rdx], 4DA31A12h
0x140008de7  jnz     short loc_140008E07
0x140008de9  mov     eax, dword ptr cs:_GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data2
0x140008def  cmp     [rdx+4], eax
0x140008df2  jnz     short loc_140008E07
0x140008df4  mov     eax, dword ptr cs:_GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data4
0x140008dfa  cmp     [rdx+8], eax
0x140008dfd  jnz     short loc_140008E07
0x140008dff  mov     eax, dword ptr cs:_GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data4+4
0x140008e05  jmp     short loc_140008DCB
0x140008e07  mov     ebx, 80004002h
0x140008e0c  mov     eax, ebx
0x140008e0e  add     rsp, 20h
0x140008e12  pop     rbx
0x140008e13  retn
```
