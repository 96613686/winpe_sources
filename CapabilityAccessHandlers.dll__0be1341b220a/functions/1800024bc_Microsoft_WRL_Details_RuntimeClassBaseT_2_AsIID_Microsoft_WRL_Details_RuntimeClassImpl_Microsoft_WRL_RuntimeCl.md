# Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange> *,_GUID const &,void * *)

- ea: `0x1800024bc`
- end: `0x1800025b7`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessCheck@@UIHandlerCustomConsent@@UIHandlerAccessChange@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessCheck@@UIHandlerCustomConsent@@UIHandlerAccessChange@@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `251`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800022c0`
- `0x180002410`
- `0x1800024b0`
- `0x18000279c`

## callees

- `0x1800024bc`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>>(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v4; // ebx

  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -975027644
      && a2[1] == *(_DWORD *)&GUID_c5e24244_3c21_4b41_8b86_7e671a675702.Data2
      && a2[2] == *(_DWORD *)GUID_c5e24244_3c21_4b41_8b86_7e671a675702.Data4
      && a2[3] == *(_DWORD *)&GUID_c5e24244_3c21_4b41_8b86_7e671a675702.Data4[4] )
    {
      goto LABEL_23;
    }
  }
  else if ( a2[1] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
         && a2[2] == *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
         && a2[3] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
  a1 += 8;
  if ( *a2 == -1923871779 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_8d540bdd_316f_4204_ac18_799fffd29f12.Data2
      || a2[2] != *(_DWORD *)GUID_8d540bdd_316f_4204_ac18_799fffd29f12.Data4
      || a2[3] != *(_DWORD *)&GUID_8d540bdd_316f_4204_ac18_799fffd29f12.Data4[4] )
    {
LABEL_14:
      v4 = -2147467262;
      goto LABEL_15;
    }
LABEL_23:
    *a3 = a1;
    v4 = 0;
    goto LABEL_16;
  }
  if ( *a2 != -1786446289
    || a2[1] != *(_DWORD *)&GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data2
    || a2[2] != *(_DWORD *)GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data4
    || a2[3] != *(_DWORD *)&GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data4[4] )
  {
    goto LABEL_14;
  }
  *a3 = a1 + 8;
  v4 = 0;
LABEL_15:
  if ( v4 >= 0 )
LABEL_16:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800024bc  push    rbx
0x1800024be  sub     rsp, 20h
0x1800024c2  mov     qword ptr [r8], 0
0x1800024c9  cmp     dword ptr [rdx], 0
0x1800024cc  jnz     short loc_180002502
0x1800024ce  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x1800024d4  cmp     [rdx+4], eax
0x1800024d7  jnz     short loc_18000252F
0x1800024d9  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1800024df  cmp     [rdx+8], eax
0x1800024e2  jnz     short loc_18000252F
0x1800024e4  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1800024ea  cmp     [rdx+0Ch], eax
0x1800024ed  jnz     short loc_18000252F
0x1800024ef  mov     [r8], rcx
0x1800024f2  mov     rax, [rcx]
0x1800024f5  mov     rax, [rax+8]
0x1800024f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024fe  xor     eax, eax
0x180002500  jmp     short loc_180002576
0x180002502  cmp     dword ptr [rdx], 0C5E24244h
0x180002508  jnz     short loc_18000252F
0x18000250a  mov     eax, dword ptr cs:_GUID_c5e24244_3c21_4b41_8b86_7e671a675702.Data2
0x180002510  cmp     [rdx+4], eax
0x180002513  jnz     short loc_18000252F
0x180002515  mov     eax, dword ptr cs:_GUID_c5e24244_3c21_4b41_8b86_7e671a675702.Data4
0x18000251b  cmp     [rdx+8], eax
0x18000251e  jnz     short loc_18000252F
0x180002520  mov     eax, dword ptr cs:_GUID_c5e24244_3c21_4b41_8b86_7e671a675702.Data4+4
0x180002526  cmp     [rdx+0Ch], eax
0x180002529  jz      loc_1800025B0
0x18000252f  add     rcx, 8
0x180002533  cmp     dword ptr [rdx], 8D540BDDh
0x180002539  jnz     short loc_18000257C
0x18000253b  mov     eax, dword ptr cs:_GUID_8d540bdd_316f_4204_ac18_799fffd29f12.Data2
0x180002541  cmp     [rdx+4], eax
0x180002544  jnz     short loc_18000255C
0x180002546  mov     eax, dword ptr cs:_GUID_8d540bdd_316f_4204_ac18_799fffd29f12.Data4
0x18000254c  cmp     [rdx+8], eax
0x18000254f  jnz     short loc_18000255C
0x180002551  mov     eax, dword ptr cs:_GUID_8d540bdd_316f_4204_ac18_799fffd29f12.Data4+4
0x180002557  cmp     [rdx+0Ch], eax
0x18000255a  jz      short loc_1800025B0
0x18000255c  mov     ebx, 80004002h
0x180002561  test    ebx, ebx
0x180002563  js      short loc_180002574
0x180002565  mov     rcx, [r8]
0x180002568  mov     rdx, [rcx]
0x18000256b  mov     rax, [rdx+8]
0x18000256f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002574  mov     eax, ebx
0x180002576  add     rsp, 20h
0x18000257a  pop     rbx
0x18000257b  retn
0x18000257c  cmp     dword ptr [rdx], 9584FE2Fh
0x180002582  jnz     short loc_18000255C
0x180002584  mov     eax, dword ptr cs:_GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data2
0x18000258a  cmp     [rdx+4], eax
0x18000258d  jnz     short loc_18000255C
0x18000258f  mov     eax, dword ptr cs:_GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data4
0x180002595  cmp     [rdx+8], eax
0x180002598  jnz     short loc_18000255C
0x18000259a  mov     eax, dword ptr cs:_GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data4+4
0x1800025a0  cmp     [rdx+0Ch], eax
0x1800025a3  jnz     short loc_18000255C
0x1800025a5  lea     rax, [rcx+8]
0x1800025a9  mov     [r8], rax
0x1800025ac  xor     ebx, ebx
0x1800025ae  jmp     short loc_180002561
0x1800025b0  mov     [r8], rcx
0x1800025b3  xor     ebx, ebx
0x1800025b5  jmp     short loc_180002565
```
