# RawInputWatcher::FindOrCreatePnpDeviceRouterDeviceId(void *,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> *)

- ea: `0x180049fa4`
- end: `0x18004a052`
- name: `?FindOrCreatePnpDeviceRouterDeviceId@RawInputWatcher@@AEAAKPEAXPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@@Z`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18004b340`

## callees

- `0x18000c11c`
- `0x180049df4`
- `0x180049fa4`
- `0x18004a07c`

## pseudocode

```c
__int64 __fastcall RawInputWatcher::FindOrCreatePnpDeviceRouterDeviceId(
        _QWORD *a1,
        const struct std::nothrow_t *a2,
        void **a3)
{
  _QWORD *v5; // rsi
  PVOID v6; // rbx
  __int64 v8; // rcx
  const unsigned __int16 *v9; // rdx
  const struct std::nothrow_t *v10; // rdx
  void *v11; // rcx
  PVOID v12; // rax
  PVOID P; // [rsp+40h] [rbp+18h] BYREF

  v5 = a1;
  if ( a3 )
  {
    a1 = *a3;
    *a3 = 0;
    if ( a1 )
      operator delete(a1, a2);
  }
  P = 0;
  RawInputWatcher::GetRawInputDeviceName(a1, a2, &P);
  v6 = P;
  if ( !P )
    return 0;
  v8 = v5[1];
  v9 = (const unsigned __int16 *)P;
  LODWORD(P) = 0;
  PnpInterfaceWatcher::FindOrAddPnpDevice(*(PnpInterfaceWatcher **)(v8 + 104), v9, (unsigned int *)&P);
  if ( a3 )
  {
    v11 = *a3;
    v12 = v6;
    v6 = 0;
    *a3 = v12;
    if ( v11 )
      operator delete(v11, v10);
  }
  if ( v6 )
    operator delete(v6, v10);
  return (unsigned int)P;
}

```

## disassembly

```asm
0x180049fa4  mov     [rsp+arg_0], rbx
0x180049fa9  mov     [rsp+arg_8], rsi
0x180049fae  push    rdi
0x180049faf  sub     rsp, 20h
0x180049fb3  mov     rdi, r8
0x180049fb6  mov     rbx, rdx
0x180049fb9  mov     rsi, rcx
0x180049fbc  test    r8, r8
0x180049fbf  jz      short loc_180049FD5
0x180049fc1  mov     rcx, [r8]; P
0x180049fc4  mov     qword ptr [r8], 0
0x180049fcb  test    rcx, rcx
0x180049fce  jz      short loc_180049FD5
0x180049fd0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180049fd5  lea     r8, [rsp+28h+P]
0x180049fda  mov     [rsp+28h+P], 0
0x180049fe3  mov     rdx, rbx
0x180049fe6  call    ?GetRawInputDeviceName@RawInputWatcher@@AEAAXQEAXPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@@Z; RawInputWatcher::GetRawInputDeviceName(void * const,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> *)
0x180049feb  mov     rbx, [rsp+28h+P]
0x180049ff0  test    rbx, rbx
0x180049ff3  jnz     short loc_180049FF9
0x180049ff5  xor     eax, eax
0x180049ff7  jmp     short loc_18004A041
0x180049ff9  mov     rcx, [rsi+8]
0x180049ffd  lea     r8, [rsp+28h+P]; unsigned int *
0x18004a002  mov     rdx, rbx; unsigned __int16 *
0x18004a005  mov     dword ptr [rsp+28h+P], 0
0x18004a00d  mov     rcx, [rcx+68h]; this
0x18004a011  call    ?FindOrAddPnpDevice@PnpInterfaceWatcher@@AEAAXQEBGPEAK@Z; PnpInterfaceWatcher::FindOrAddPnpDevice(ushort const * const,ulong *)
0x18004a016  test    rdi, rdi
0x18004a019  jz      short loc_18004A030
0x18004a01b  mov     rcx, [rdi]; P
0x18004a01e  mov     rax, rbx
0x18004a021  xor     ebx, ebx
0x18004a023  mov     [rdi], rax
0x18004a026  test    rcx, rcx
0x18004a029  jz      short loc_18004A030
0x18004a02b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a030  test    rbx, rbx
0x18004a033  jz      short loc_18004A03D
0x18004a035  mov     rcx, rbx; P
0x18004a038  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a03d  mov     eax, dword ptr [rsp+28h+P]
0x18004a041  mov     rbx, [rsp+28h+arg_0]
0x18004a046  mov     rsi, [rsp+28h+arg_8]
0x18004a04b  add     rsp, 20h
0x18004a04f  pop     rdi
0x18004a050  retn
```
