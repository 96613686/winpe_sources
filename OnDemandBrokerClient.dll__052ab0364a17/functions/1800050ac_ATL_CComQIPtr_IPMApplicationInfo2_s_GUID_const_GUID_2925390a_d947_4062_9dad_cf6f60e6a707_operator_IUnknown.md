# ATL::CComQIPtr<IPMApplicationInfo2,&__s_GUID const _GUID_2925390a_d947_4062_9dad_cf6f60e6a707>::operator=(IUnknown *)

- ea: `0x1800050ac`
- end: `0x18000510f`
- name: `??4?$CComQIPtr@UIPMApplicationInfo2@@$1?_GUID_2925390a_d947_4062_9dad_cf6f60e6a707@@3U__s_GUID@@B@ATL@@QEAAPEAUIPMApplicationInfo2@@PEAUIUnknown@@@Z`
- size: `99`
- prototype: `void (__fastcall ***__fastcall(__int64 *, void (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(_QWORD, GUID *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800058f0`

## callees

- `0x1800050ac`
- `0x180007010`

## pseudocode

```c
void (__fastcall ***__fastcall ATL::CComQIPtr<IPMApplicationInfo2,&__s_GUID const _GUID_2925390a_d947_4062_9dad_cf6f60e6a707>::operator=(
        __int64 *a1,
        void (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3))(_QWORD, GUID *, __int64 *)
{
  __int64 v3; // rbx
  void (__fastcall ***v4)(_QWORD, GUID *, _QWORD); // r9

  v3 = *a1;
  v4 = (void (__fastcall ***)(_QWORD, GUID *, _QWORD))a2;
  if ( (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1 == a2 )
    return (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
  *a1 = 0;
  if ( a2 )
    (**a2)(a2, &GUID_2925390a_d947_4062_9dad_cf6f60e6a707, a1);
  if ( v3 )
    (*(void (__fastcall **)(__int64, void (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64, void (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*(_QWORD *)v3 + 16LL))(
      v3,
      a2,
      a3,
      v4);
  return (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
}

```

## disassembly

```asm
0x1800050ac  mov     [rsp+arg_0], rbx
0x1800050b1  push    rdi
0x1800050b2  sub     rsp, 20h
0x1800050b6  mov     rbx, [rcx]
0x1800050b9  mov     r9, rdx
0x1800050bc  mov     rdi, rcx
0x1800050bf  cmp     rbx, rdx
0x1800050c2  jz      short loc_180005101
0x1800050c4  mov     qword ptr [rcx], 0
0x1800050cb  test    rdx, rdx
0x1800050ce  jz      short loc_1800050E8
0x1800050d0  mov     rax, [rdx]
0x1800050d3  mov     r8, rcx
0x1800050d6  lea     rdx, _GUID_2925390a_d947_4062_9dad_cf6f60e6a707
0x1800050dd  mov     rcx, r9
0x1800050e0  mov     rax, [rax]
0x1800050e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e8  test    rbx, rbx
0x1800050eb  jz      short loc_1800050FC
0x1800050ed  mov     rax, [rbx]
0x1800050f0  mov     rcx, rbx
0x1800050f3  mov     rax, [rax+10h]
0x1800050f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050fc  mov     rax, [rdi]
0x1800050ff  jmp     short loc_180005104
0x180005101  mov     rax, rbx
0x180005104  mov     rbx, [rsp+28h+arg_0]
0x180005109  add     rsp, 20h
0x18000510d  pop     rdi
0x18000510e  retn
```
