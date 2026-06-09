# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800155b0`
- end: `0x18001568d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800156a0`

## callees

- `0x1800155b0`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == 159843635
      && a2[1] == *(_DWORD *)&GUID_09870533_f7cb_569c_b797_dcb48debd709.Data2
      && a2[2] == *(_DWORD *)GUID_09870533_f7cb_569c_b797_dcb48debd709.Data4
      && a2[3] == *(_DWORD *)&GUID_09870533_f7cb_569c_b797_dcb48debd709.Data4[4] )
    {
      *a3 = a1;
LABEL_22:
      a1 = *a3;
      goto LABEL_6;
    }
LABEL_12:
    v4 = a1 + 8;
    if ( *a2 == -1796592748 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
        || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
    }
    else
    {
      if ( *a2 != 3
        || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
        || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
    }
    if ( a2[3] == v5 )
    {
      *a3 = v4;
      goto LABEL_22;
    }
    return (unsigned int)-2147467262;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_12;
  }
  *a3 = a1;
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x1800155b0  push    rbx
0x1800155b2  sub     rsp, 20h
0x1800155b6  xor     ebx, ebx
0x1800155b8  mov     [r8], rbx
0x1800155bb  cmp     [rdx], ebx
0x1800155bd  jnz     short loc_1800155F4
0x1800155bf  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x1800155c5  cmp     [rdx+4], eax
0x1800155c8  jnz     short loc_180015622
0x1800155ca  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1800155d0  cmp     [rdx+8], eax
0x1800155d3  jnz     short loc_180015622
0x1800155d5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1800155db  cmp     [rdx+0Ch], eax
0x1800155de  jnz     short loc_180015622
0x1800155e0  mov     [r8], rcx
0x1800155e3  mov     rax, [rcx]
0x1800155e6  mov     rax, [rax+8]
0x1800155ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155ef  jmp     loc_180015685
0x1800155f4  cmp     dword ptr [rdx], 9870533h
0x1800155fa  jnz     short loc_180015622
0x1800155fc  mov     eax, dword ptr cs:_GUID_09870533_f7cb_569c_b797_dcb48debd709.Data2
0x180015602  cmp     [rdx+4], eax
0x180015605  jnz     short loc_180015622
0x180015607  mov     eax, dword ptr cs:_GUID_09870533_f7cb_569c_b797_dcb48debd709.Data4
0x18001560d  cmp     [rdx+8], eax
0x180015610  jnz     short loc_180015622
0x180015612  mov     eax, dword ptr cs:_GUID_09870533_f7cb_569c_b797_dcb48debd709.Data4+4
0x180015618  cmp     [rdx+0Ch], eax
0x18001561b  jnz     short loc_180015622
0x18001561d  mov     [r8], rcx
0x180015620  jmp     short loc_180015678
0x180015622  add     rcx, 8
0x180015626  cmp     dword ptr [rdx], 94EA2B94h
0x18001562c  jnz     short loc_18001564C
0x18001562e  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x180015634  cmp     [rdx+4], eax
0x180015637  jnz     short loc_180015680
0x180015639  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x18001563f  cmp     [rdx+8], eax
0x180015642  jnz     short loc_180015680
0x180015644  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18001564a  jmp     short loc_18001566D
0x18001564c  cmp     dword ptr [rdx], 3
0x18001564f  jnz     short loc_180015680
0x180015651  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180015657  cmp     [rdx+4], eax
0x18001565a  jnz     short loc_180015680
0x18001565c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180015662  cmp     [rdx+8], eax
0x180015665  jnz     short loc_180015680
0x180015667  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18001566d  cmp     [rdx+0Ch], eax
0x180015670  jnz     short loc_180015680
0x180015672  mov     rax, r8
0x180015675  mov     [rax], rcx
0x180015678  mov     rcx, [r8]
0x18001567b  jmp     loc_1800155E3
0x180015680  mov     ebx, 80004002h
0x180015685  mov     eax, ebx
0x180015687  add     rsp, 20h
0x18001568b  pop     rbx
0x18001568c  retn
```
