# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000b350`
- end: `0x18000b3fd`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMidiTransportConfigurationManager@@UIMidiServicePluginMetadataReporter@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b410`

## callees

- `0x18000b350`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -241314238 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data2
        || a2[2] != *(_DWORD *)GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4
        || a2[3] != *(_DWORD *)&GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4[4] )
      {
        return (unsigned int)-2147467262;
      }
    }
    else
    {
      if ( *a2 != 1184659234
        || a2[1] != *(_DWORD *)&GUID_469c7722_f779_40c3_b648_52620f75dcee.Data2
        || a2[2] != *(_DWORD *)GUID_469c7722_f779_40c3_b648_52620f75dcee.Data4
        || a2[3] != *(_DWORD *)&GUID_469c7722_f779_40c3_b648_52620f75dcee.Data4[4] )
      {
        return (unsigned int)-2147467262;
      }
      a1 += 8;
    }
    *a3 = a1;
    goto LABEL_6;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    return (unsigned int)-2147467262;
  }
  *a3 = a1;
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x18000b350  push    rbx
0x18000b352  sub     rsp, 20h
0x18000b356  xor     ebx, ebx
0x18000b358  mov     [r8], rbx
0x18000b35b  cmp     [rdx], ebx
0x18000b35d  jnz     short loc_18000B391
0x18000b35f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000b365  cmp     [rdx+4], eax
0x18000b368  jnz     short loc_18000B3BA
0x18000b36a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000b370  cmp     [rdx+8], eax
0x18000b373  jnz     short loc_18000B3BA
0x18000b375  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000b37b  cmp     [rdx+0Ch], eax
0x18000b37e  jnz     short loc_18000B3BA
0x18000b380  mov     [r8], rcx
0x18000b383  mov     rax, [rcx]
0x18000b386  mov     rax, [rax+8]
0x18000b38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b38f  jmp     short loc_18000B3BF
0x18000b391  cmp     dword ptr [rdx], 0F19DD642h
0x18000b397  jnz     short loc_18000B3C7
0x18000b399  mov     eax, dword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data2
0x18000b39f  cmp     [rdx+4], eax
0x18000b3a2  jnz     short loc_18000B3BA
0x18000b3a4  mov     eax, dword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4
0x18000b3aa  cmp     [rdx+8], eax
0x18000b3ad  jnz     short loc_18000B3BA
0x18000b3af  mov     eax, dword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4+4
0x18000b3b5  cmp     [rdx+0Ch], eax
0x18000b3b8  jz      short loc_18000B3F4
0x18000b3ba  mov     ebx, 80004002h
0x18000b3bf  mov     eax, ebx
0x18000b3c1  add     rsp, 20h
0x18000b3c5  pop     rbx
0x18000b3c6  retn
0x18000b3c7  cmp     dword ptr [rdx], 469C7722h
0x18000b3cd  jnz     short loc_18000B3BA
0x18000b3cf  mov     eax, dword ptr cs:_GUID_469c7722_f779_40c3_b648_52620f75dcee.Data2
0x18000b3d5  cmp     [rdx+4], eax
0x18000b3d8  jnz     short loc_18000B3BA
0x18000b3da  mov     eax, dword ptr cs:_GUID_469c7722_f779_40c3_b648_52620f75dcee.Data4
0x18000b3e0  cmp     [rdx+8], eax
0x18000b3e3  jnz     short loc_18000B3BA
0x18000b3e5  mov     eax, dword ptr cs:_GUID_469c7722_f779_40c3_b648_52620f75dcee.Data4+4
0x18000b3eb  cmp     [rdx+0Ch], eax
0x18000b3ee  jnz     short loc_18000B3BA
0x18000b3f0  add     rcx, 8
0x18000b3f4  mov     rax, rcx
0x18000b3f7  mov     [r8], rcx
0x18000b3fa  jmp     short loc_18000B383
```
