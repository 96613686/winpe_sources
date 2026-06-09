# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiServiceTransportPluginMetadataProvider>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c120`
- end: `0x18000c194`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMidiServiceTransportPluginMetadataProvider@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000c120`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiServiceTransportPluginMetadataProvider>::QueryInterface(
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
    if ( *a2 != -1923864768
      || a2[1] != *(_DWORD *)&GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data2
      || a2[2] != *(_DWORD *)GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data4[4];
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
0x18000c120  push    rbx
0x18000c122  sub     rsp, 20h
0x18000c126  xor     ebx, ebx
0x18000c128  mov     [r8], rbx
0x18000c12b  cmp     [rdx], ebx
0x18000c12d  jnz     short loc_18000C161
0x18000c12f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000c135  cmp     [rdx+4], eax
0x18000c138  jnz     short loc_18000C187
0x18000c13a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000c140  cmp     [rdx+8], eax
0x18000c143  jnz     short loc_18000C187
0x18000c145  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000c14b  cmp     [rdx+0Ch], eax
0x18000c14e  jnz     short loc_18000C187
0x18000c150  mov     [r8], rcx
0x18000c153  mov     rax, [rcx]
0x18000c156  mov     rax, [rax+8]
0x18000c15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c15f  jmp     short loc_18000C18C
0x18000c161  cmp     dword ptr [rdx], 8D542740h
0x18000c167  jnz     short loc_18000C187
0x18000c169  mov     eax, dword ptr cs:_GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data2
0x18000c16f  cmp     [rdx+4], eax
0x18000c172  jnz     short loc_18000C187
0x18000c174  mov     eax, dword ptr cs:_GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data4
0x18000c17a  cmp     [rdx+8], eax
0x18000c17d  jnz     short loc_18000C187
0x18000c17f  mov     eax, dword ptr cs:_GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data4+4
0x18000c185  jmp     short loc_18000C14B
0x18000c187  mov     ebx, 80004002h
0x18000c18c  mov     eax, ebx
0x18000c18e  add     rsp, 20h
0x18000c192  pop     rbx
0x18000c193  retn
```
