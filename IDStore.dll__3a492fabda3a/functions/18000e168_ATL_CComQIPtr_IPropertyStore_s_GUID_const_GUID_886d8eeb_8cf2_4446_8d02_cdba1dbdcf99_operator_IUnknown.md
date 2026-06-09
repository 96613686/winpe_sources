# ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>::operator=(IUnknown *)

- ea: `0x18000e168`
- end: `0x18000e1cd`
- name: `??4?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@QEAAPEAUIPropertyStore@@PEAUIUnknown@@@Z`
- size: `101`
- prototype: `void (__fastcall ***__fastcall(__int64 *, void (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(_QWORD, GUID *, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012b10`
- `0x180013430`

## callees

- `0x18000e168`
- `0x18001b010`

## pseudocode

```c
void (__fastcall ***__fastcall ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>::operator=(
        __int64 *a1,
        void (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3))(_QWORD, GUID *, __int64 *)
{
  void (__fastcall ***v3)(_QWORD, GUID *, _QWORD); // r9
  __int64 v5; // rbx

  v3 = (void (__fastcall ***)(_QWORD, GUID *, _QWORD))a2;
  v5 = *a1;
  if ( (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1 == a2 )
    return (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
  *a1 = 0;
  if ( a2 )
    (**a2)(a2, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, a1);
  if ( v5 )
    (*(void (__fastcall **)(__int64, void (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64, void (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*(_QWORD *)v5 + 16LL))(
      v5,
      a2,
      a3,
      v3);
  return (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
}

```

## disassembly

```asm
0x18000e168  mov     [rsp+arg_0], rbx
0x18000e16d  push    rdi
0x18000e16e  sub     rsp, 20h
0x18000e172  mov     r9, rdx
0x18000e175  mov     rdi, rcx
0x18000e178  mov     rbx, [rcx]
0x18000e17b  cmp     rbx, rdx
0x18000e17e  jz      short loc_18000E1C8
0x18000e180  mov     qword ptr [rcx], 0
0x18000e187  test    rdx, rdx
0x18000e18a  jz      short loc_18000E1A4
0x18000e18c  mov     rax, [rdx]
0x18000e18f  mov     r8, rcx
0x18000e192  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18000e199  mov     rcx, r9
0x18000e19c  mov     rax, [rax]
0x18000e19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1a4  test    rbx, rbx
0x18000e1a7  jnz     short loc_18000E1B7
0x18000e1a9  mov     rax, [rdi]
0x18000e1ac  mov     rbx, [rsp+28h+arg_0]
0x18000e1b1  add     rsp, 20h
0x18000e1b5  pop     rdi
0x18000e1b6  retn
0x18000e1b7  mov     rax, [rbx]
0x18000e1ba  mov     rcx, rbx
0x18000e1bd  mov     rax, [rax+10h]
0x18000e1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1c6  jmp     short loc_18000E1A9
0x18000e1c8  mov     rax, rbx
0x18000e1cb  jmp     short loc_18000E1AC
```
