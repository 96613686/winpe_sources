# ATL::CComQIPtr<IConnectedUser,&__s_GUID const _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d>::operator=(IUnknown *)

- ea: `0x1800081f0`
- end: `0x180008255`
- name: `??4?$CComQIPtr@UIConnectedUser@@$1?_GUID_9d5f2149_de8c_45f2_b313_6587a04f771d@@3U__s_GUID@@B@ATL@@QEAAPEAUIConnectedUser@@PEAUIUnknown@@@Z`
- size: `101`
- prototype: `void (__fastcall ***__fastcall(__int64 *, void (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(_QWORD, GUID *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800074dc`

## callees

- `0x1800081f0`
- `0x18001b010`

## pseudocode

```c
void (__fastcall ***__fastcall ATL::CComQIPtr<IConnectedUser,&__s_GUID const _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d>::operator=(
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
    (**a2)(a2, &GUID_9d5f2149_de8c_45f2_b313_6587a04f771d, a1);
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
0x1800081f0  mov     [rsp+arg_0], rbx
0x1800081f5  push    rdi
0x1800081f6  sub     rsp, 20h
0x1800081fa  mov     r9, rdx
0x1800081fd  mov     rdi, rcx
0x180008200  mov     rbx, [rcx]
0x180008203  cmp     rbx, rdx
0x180008206  jz      short loc_180008250
0x180008208  mov     qword ptr [rcx], 0
0x18000820f  test    rdx, rdx
0x180008212  jz      short loc_18000822C
0x180008214  mov     rax, [rdx]
0x180008217  mov     r8, rcx
0x18000821a  lea     rdx, _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d
0x180008221  mov     rcx, r9
0x180008224  mov     rax, [rax]
0x180008227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000822c  test    rbx, rbx
0x18000822f  jnz     short loc_18000823F
0x180008231  mov     rax, [rdi]
0x180008234  mov     rbx, [rsp+28h+arg_0]
0x180008239  add     rsp, 20h
0x18000823d  pop     rdi
0x18000823e  retn
0x18000823f  mov     rax, [rbx]
0x180008242  mov     rcx, rbx
0x180008245  mov     rax, [rax+10h]
0x180008249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000824e  jmp     short loc_180008231
0x180008250  mov     rax, rbx
0x180008253  jmp     short loc_180008234
```
