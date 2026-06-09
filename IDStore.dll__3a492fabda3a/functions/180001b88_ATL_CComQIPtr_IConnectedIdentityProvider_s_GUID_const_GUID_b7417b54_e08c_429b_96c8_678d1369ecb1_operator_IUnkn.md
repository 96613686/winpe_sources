# ATL::CComQIPtr<IConnectedIdentityProvider,&__s_GUID const _GUID_b7417b54_e08c_429b_96c8_678d1369ecb1>::operator=(IUnknown *)

- ea: `0x180001b88`
- end: `0x180001bed`
- name: `??4?$CComQIPtr@UIConnectedIdentityProvider@@$1?_GUID_b7417b54_e08c_429b_96c8_678d1369ecb1@@3U__s_GUID@@B@ATL@@QEAAPEAUIConnectedIdentityProvider@@PEAUIUnknown@@@Z`
- size: `101`
- prototype: `void (__fastcall ***__fastcall(__int64 *, void (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(_QWORD, GUID *, __int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001808`
- `0x180012b10`
- `0x180013430`
- `0x180013b40`

## callees

- `0x180001b88`
- `0x18001b010`

## pseudocode

```c
void (__fastcall ***__fastcall ATL::CComQIPtr<IConnectedIdentityProvider,&__s_GUID const _GUID_b7417b54_e08c_429b_96c8_678d1369ecb1>::operator=(
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
    (**a2)(a2, &GUID_b7417b54_e08c_429b_96c8_678d1369ecb1, a1);
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
0x180001b88  mov     [rsp+arg_0], rbx
0x180001b8d  push    rdi
0x180001b8e  sub     rsp, 20h
0x180001b92  mov     r9, rdx
0x180001b95  mov     rdi, rcx
0x180001b98  mov     rbx, [rcx]
0x180001b9b  cmp     rbx, rdx
0x180001b9e  jz      short loc_180001BE8
0x180001ba0  mov     qword ptr [rcx], 0
0x180001ba7  test    rdx, rdx
0x180001baa  jz      short loc_180001BC4
0x180001bac  mov     rax, [rdx]
0x180001baf  mov     r8, rcx
0x180001bb2  lea     rdx, _GUID_b7417b54_e08c_429b_96c8_678d1369ecb1
0x180001bb9  mov     rcx, r9
0x180001bbc  mov     rax, [rax]
0x180001bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bc4  test    rbx, rbx
0x180001bc7  jnz     short loc_180001BD7
0x180001bc9  mov     rax, [rdi]
0x180001bcc  mov     rbx, [rsp+28h+arg_0]
0x180001bd1  add     rsp, 20h
0x180001bd5  pop     rdi
0x180001bd6  retn
0x180001bd7  mov     rax, [rbx]
0x180001bda  mov     rcx, rbx
0x180001bdd  mov     rax, [rax+10h]
0x180001be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001be6  jmp     short loc_180001BC9
0x180001be8  mov     rax, rbx
0x180001beb  jmp     short loc_180001BCC
```
