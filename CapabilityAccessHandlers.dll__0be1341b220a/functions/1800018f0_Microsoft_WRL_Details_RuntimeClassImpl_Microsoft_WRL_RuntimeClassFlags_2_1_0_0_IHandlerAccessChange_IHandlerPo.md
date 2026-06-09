# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800018f0`
- end: `0x1800019b8`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessChange@@UIHandlerPolicy@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(__int64, int *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008c60`

## callees

- `0x1800018f0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>::QueryInterface(
        __int64 a1,
        int *a2,
        _QWORD *a3)
{
  int v3; // eax
  unsigned int v5; // ebx

  *a3 = 0;
  v3 = *a2;
  if ( !*a2 )
  {
    if ( a2[1] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      && a2[2] == *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
      && a2[3] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
    {
      *a3 = a1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      return 0;
    }
    return (unsigned int)-2147467262;
  }
  if ( v3 == -1786446289 )
  {
    if ( a2[1] == *(_DWORD *)&GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data2
      && a2[2] == *(_DWORD *)GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data4
      && a2[3] == *(_DWORD *)&GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data4[4] )
    {
      *a3 = a1;
LABEL_13:
      v5 = 0;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
      return v5;
    }
  }
  else if ( v3 == 294524428
         && a2[1] == *(_DWORD *)&GUID_118e160c_bc9e_4b19_946c_39cae38e3ae0.Data2
         && a2[2] == *(_DWORD *)GUID_118e160c_bc9e_4b19_946c_39cae38e3ae0.Data4
         && a2[3] == *(_DWORD *)&GUID_118e160c_bc9e_4b19_946c_39cae38e3ae0.Data4[4] )
  {
    *a3 = a1 + 8;
    goto LABEL_13;
  }
  return (unsigned int)-2147467262;
}

```

## disassembly

```asm
0x1800018f0  push    rbx
0x1800018f2  sub     rsp, 20h
0x1800018f6  mov     qword ptr [r8], 0
0x1800018fd  mov     eax, [rdx]
0x1800018ff  test    eax, eax
0x180001901  jnz     short loc_180001948
0x180001903  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180001909  cmp     [rdx+4], eax
0x18000190c  jnz     short loc_18000193B
0x18000190e  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180001914  cmp     [rdx+8], eax
0x180001917  jnz     short loc_18000193B
0x180001919  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000191f  cmp     [rdx+0Ch], eax
0x180001922  jnz     short loc_18000193B
0x180001924  mov     [r8], rcx
0x180001927  mov     rax, [rcx]
0x18000192a  mov     rax, [rax+8]
0x18000192e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001933  xor     eax, eax
0x180001935  add     rsp, 20h
0x180001939  pop     rbx
0x18000193a  retn
0x18000193b  mov     ebx, 80004002h
0x180001940  mov     eax, ebx
0x180001942  add     rsp, 20h
0x180001946  pop     rbx
0x180001947  retn
0x180001948  cmp     eax, 9584FE2Fh
0x18000194d  jnz     short loc_180001986
0x18000194f  mov     eax, dword ptr cs:_GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data2
0x180001955  cmp     [rdx+4], eax
0x180001958  jnz     short loc_18000193B
0x18000195a  mov     eax, dword ptr cs:_GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data4
0x180001960  cmp     [rdx+8], eax
0x180001963  jnz     short loc_18000193B
0x180001965  mov     eax, dword ptr cs:_GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data4+4
0x18000196b  cmp     [rdx+0Ch], eax
0x18000196e  jnz     short loc_18000193B
0x180001970  mov     [r8], rcx
0x180001973  xor     ebx, ebx
0x180001975  mov     rcx, [r8]
0x180001978  mov     rax, [rcx]
0x18000197b  mov     rax, [rax+8]
0x18000197f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001984  jmp     short loc_180001940
0x180001986  cmp     eax, 118E160Ch
0x18000198b  jnz     short loc_18000193B
0x18000198d  mov     eax, dword ptr cs:_GUID_118e160c_bc9e_4b19_946c_39cae38e3ae0.Data2
0x180001993  cmp     [rdx+4], eax
0x180001996  jnz     short loc_18000193B
0x180001998  mov     eax, dword ptr cs:_GUID_118e160c_bc9e_4b19_946c_39cae38e3ae0.Data4
0x18000199e  cmp     [rdx+8], eax
0x1800019a1  jnz     short loc_18000193B
0x1800019a3  mov     eax, dword ptr cs:_GUID_118e160c_bc9e_4b19_946c_39cae38e3ae0.Data4+4
0x1800019a9  cmp     [rdx+0Ch], eax
0x1800019ac  jnz     short loc_18000193B
0x1800019ae  lea     rax, [rcx+8]
0x1800019b2  mov     [r8], rax
0x1800019b5  jmp     short loc_180001973
```
