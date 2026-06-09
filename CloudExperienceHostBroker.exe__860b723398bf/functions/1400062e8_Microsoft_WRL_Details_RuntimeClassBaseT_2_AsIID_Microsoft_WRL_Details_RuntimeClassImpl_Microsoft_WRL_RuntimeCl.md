# Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase> *,_GUID const &,void * *)

- ea: `0x1400062e8`
- end: `0x1400063ad`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCreateObjectServerTaskBase@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCreateObjectServerTaskBase@@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `197`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006788`
- `0x1400083c0`

## callees

- `0x1400062e8`
- `0x140009374`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase>>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  __int64 v6; // rcx
  _QWORD *v7; // r8
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // r9
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r9

  *a3 = 0;
  if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_839d7762_5121_4009_9234_4f0d19394f04) )
    {
      *v7 = v8;
      v9 = 0;
    }
    else
    {
      if ( (unsigned int)InlineIsEqualGUID(v6, &GUID_00000001_0000_0000_c000_000000000046) )
      {
        *v7 = v11;
        v12 = 0;
      }
      else
      {
        v9 = -2147467262;
        if ( (unsigned int)InlineIsEqualGUID(v10, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90)
          || (unsigned int)InlineIsEqualGUID(v13, &GUID_00000003_0000_0000_c000_000000000046) )
        {
          *v7 = v14;
          v12 = 0;
        }
        else
        {
          v12 = -2147467262;
        }
        if ( v12 == -2147467262 )
          return v9;
      }
      v9 = v12;
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
    return v9;
  }
  *v4 = v5;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x1400062e8  push    rbx
0x1400062ea  sub     rsp, 20h
0x1400062ee  mov     r10, rdx
0x1400062f1  mov     r9, rcx
0x1400062f4  mov     qword ptr [r8], 0
0x1400062fb  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140006302  mov     rcx, r10
0x140006305  call    InlineIsEqualGUID
0x14000630a  test    eax, eax
0x14000630c  jnz     loc_140006393
0x140006312  lea     rdx, _GUID_839d7762_5121_4009_9234_4f0d19394f04
0x140006319  call    InlineIsEqualGUID
0x14000631e  test    eax, eax
0x140006320  jz      short loc_140006329
0x140006322  mov     [r8], r9
0x140006325  xor     ebx, ebx
0x140006327  jmp     short loc_140006380
0x140006329  add     r9, 8
0x14000632d  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x140006334  call    InlineIsEqualGUID
0x140006339  test    eax, eax
0x14000633b  jz      short loc_140006344
0x14000633d  mov     [r8], r9
0x140006340  xor     eax, eax
0x140006342  jmp     short loc_14000637A
0x140006344  add     r9, 8
0x140006348  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x14000634f  call    InlineIsEqualGUID
0x140006354  mov     ebx, 80004002h
0x140006359  test    eax, eax
0x14000635b  jnz     short loc_14000636D
0x14000635d  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x140006364  call    InlineIsEqualGUID
0x140006369  test    eax, eax
0x14000636b  jz      short loc_140006374
0x14000636d  mov     [r8], r9
0x140006370  xor     eax, eax
0x140006372  jmp     short loc_140006376
0x140006374  mov     eax, ebx
0x140006376  cmp     eax, ebx
0x140006378  jz      short loc_14000638F
0x14000637a  mov     ebx, eax
0x14000637c  test    eax, eax
0x14000637e  js      short loc_14000638F
0x140006380  mov     rcx, [r8]
0x140006383  mov     rdx, [rcx]
0x140006386  mov     rax, [rdx+8]
0x14000638a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000638f  mov     eax, ebx
0x140006391  jmp     short loc_1400063A7
0x140006393  mov     [r8], r9
0x140006396  mov     rax, [r9]
0x140006399  mov     rcx, r9
0x14000639c  mov     rax, [rax+8]
0x1400063a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063a5  xor     eax, eax
0x1400063a7  add     rsp, 20h
0x1400063ab  pop     rbx
0x1400063ac  retn
```
