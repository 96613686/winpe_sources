# TrackSystemEffectBehavior(ushort const *,__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003,long,bool,_GUID const &,float)

- ea: `0x14004dd7c`
- end: `0x14004de69`
- name: `?TrackSystemEffectBehavior@@YAJPEBGW4__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003@@J_NAEBU_GUID@@M@Z`
- size: `237`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001b01c`
- `0x14002ac14`
- `0x14004d5a0`
- `0x14008211c`
- `0x1400830f0`

## callees

- `0x14004dd7c`
- `0x140081d08`
- `0x1400b5010`

## import_xrefs

- `MMDevAPI!__imp_GetClassFromEndpointId` at `0x14004dda5`
- `MMDevAPI!__imp_GetClassFromEndpointId` at `0x14004dda5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004ddd2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004ddd2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TrackSystemEffectBehavior(__int64 a1, unsigned int a2, unsigned int a3, char a4)
{
  HRESULT v8; // ebx
  __int64 v9; // r9
  __int64 v11; // [rsp+30h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-30h] BYREF

  ppv = 0;
  v11 = 0;
  if ( (unsigned int)GetClassFromEndpointId(a1) == 3 )
  {
    v8 = 0;
  }
  else
  {
    v8 = CoCreateInstance(
           &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
           0,
           0x17u,
           &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
           &ppv);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, a1, &v11);
      if ( v8 >= 0 )
      {
        LOBYTE(v9) = a4;
        v8 = TrackSystemEffectBehavior(v11, a2, a3, v9);
      }
    }
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14004dd7c  push    rbx
0x14004dd7e  push    rbp
0x14004dd7f  push    rsi
0x14004dd80  push    rdi
0x14004dd81  push    r14
0x14004dd83  sub     rsp, 40h
0x14004dd87  mov     sil, r9b
0x14004dd8a  mov     ebp, r8d
0x14004dd8d  mov     r14d, edx
0x14004dd90  mov     rdi, rcx
0x14004dd93  mov     [rsp+68h+var_30], 0
0x14004dd9c  mov     [rsp+68h+var_38], 0
0x14004dda5  call    cs:__imp_GetClassFromEndpointId
0x14004ddab  cmp     eax, 3
0x14004ddae  jnz     short loc_14004DDB4
0x14004ddb0  xor     ebx, ebx
0x14004ddb2  jmp     short loc_14004DE2E
0x14004ddb4  lea     rax, [rsp+68h+var_30]
0x14004ddb9  mov     [rsp+68h+ppv], rax; ppv
0x14004ddbe  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x14004ddc5  xor     edx, edx; pUnkOuter
0x14004ddc7  lea     r8d, [rdx+17h]; dwClsContext
0x14004ddcb  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x14004ddd2  call    cs:__imp_CoCreateInstance
0x14004ddd8  mov     ebx, eax
0x14004ddda  test    eax, eax
0x14004dddc  js      short loc_14004DE2E
0x14004ddde  mov     rcx, [rsp+68h+var_30]
0x14004dde3  mov     rax, [rcx]
0x14004dde6  lea     r8, [rsp+68h+var_38]
0x14004ddeb  mov     rdx, rdi
0x14004ddee  mov     rax, [rax+28h]
0x14004ddf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ddf7  mov     ebx, eax
0x14004ddf9  test    eax, eax
0x14004ddfb  js      short loc_14004DE2E
0x14004ddfd  movss   xmm0, [rsp+68h+arg_28]
0x14004de06  movss   [rsp+68h+var_40], xmm0
0x14004de0c  mov     rax, [rsp+68h+arg_20]
0x14004de14  mov     [rsp+68h+ppv], rax
0x14004de19  mov     r9b, sil
0x14004de1c  mov     r8d, ebp
0x14004de1f  mov     edx, r14d
0x14004de22  mov     rcx, [rsp+68h+var_38]
0x14004de27  call    ?TrackSystemEffectBehavior@@YAJPEAUIMMDevice@@W4__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003@@J_NAEBU_GUID@@M@Z; TrackSystemEffectBehavior(IMMDevice *,__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003,long,bool,_GUID const &,float)
0x14004de2c  mov     ebx, eax
0x14004de2e  mov     rcx, [rsp+68h+var_38]
0x14004de33  test    rcx, rcx
0x14004de36  jz      short loc_14004DE45
0x14004de38  mov     rax, [rcx]
0x14004de3b  mov     rax, [rax+10h]
0x14004de3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004de44  nop
0x14004de45  mov     rcx, [rsp+68h+var_30]
0x14004de4a  test    rcx, rcx
0x14004de4d  jz      short loc_14004DE5C
0x14004de4f  mov     rax, [rcx]
0x14004de52  mov     rax, [rax+10h]
0x14004de56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004de5b  nop
0x14004de5c  mov     eax, ebx
0x14004de5e  add     rsp, 40h
0x14004de62  pop     r14
0x14004de64  pop     rdi
0x14004de65  pop     rsi
0x14004de66  pop     rbp
0x14004de67  pop     rbx
0x14004de68  retn
```
