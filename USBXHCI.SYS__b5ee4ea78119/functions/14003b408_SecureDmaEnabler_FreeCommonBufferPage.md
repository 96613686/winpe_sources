# SecureDmaEnabler_FreeCommonBufferPage

- ea: `0x14003b408`
- end: `0x14003b48d`
- name: `SecureDmaEnabler_FreeCommonBufferPage`
- size: `133`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005a6c`
- `0x14002c5b0`
- `0x140035e4c`
- `0x14003b238`
- `0x14003b364`

## callees

- `0x140010d40`
- `0x1400110e0`
- `0x14003b408`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14003b445`
- `ntoskrnl!IoFreeMdl` at `0x14003b445`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003b421`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003b421`

## pseudocode

```c
__int64 __fastcall SecureDmaEnabler_FreeCommonBufferPage(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rbx
  char v4; // si
  struct _MDL *v5; // rcx
  __int64 result; // rax

  v3 = (_QWORD *)(a1 + 8);
  v4 = 0;
  if ( KeGetCurrentIrql() == 2 )
  {
    Controller_LowerAndTrackIrql(*v3);
    v4 = 1;
  }
  v5 = *(struct _MDL **)(a2 + 88);
  if ( v5 )
    IoFreeMdl(v5);
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 1664))(
             WdfDriverGlobals,
             *(_QWORD *)(a2 + 16));
  if ( v4 )
    return Controller_RaiseAndTrackIrql(*v3);
  return result;
}

```

## disassembly

```asm
0x14003b408  mov     [rsp+arg_0], rbx
0x14003b40d  mov     [rsp+arg_8], rsi
0x14003b412  push    rdi
0x14003b413  sub     rsp, 20h
0x14003b417  mov     rdi, rdx
0x14003b41a  lea     rbx, [rcx+8]
0x14003b41e  xor     sil, sil
0x14003b421  call    cs:__imp_KeGetCurrentIrql
0x14003b428  nop     dword ptr [rax+rax+00h]
0x14003b42d  cmp     al, 2
0x14003b42f  jnz     short loc_14003B43C
0x14003b431  mov     rcx, [rbx]
0x14003b434  call    Controller_LowerAndTrackIrql
0x14003b439  mov     sil, 1
0x14003b43c  mov     rcx, [rdi+58h]; Mdl
0x14003b440  test    rcx, rcx
0x14003b443  jz      short loc_14003B451
0x14003b445  call    cs:__imp_IoFreeMdl
0x14003b44c  nop     dword ptr [rax+rax+00h]
0x14003b451  mov     rax, cs:WdfFunctions_01033
0x14003b458  mov     rdx, [rdi+10h]
0x14003b45c  mov     rcx, cs:WdfDriverGlobals
0x14003b463  mov     rax, [rax+680h]
0x14003b46a  call    _guard_dispatch_icall
0x14003b46f  test    sil, sil
0x14003b472  jz      short loc_14003B47C
0x14003b474  mov     rcx, [rbx]
0x14003b477  call    Controller_RaiseAndTrackIrql
0x14003b47c  mov     rbx, [rsp+28h+arg_0]
0x14003b481  mov     rsi, [rsp+28h+arg_8]
0x14003b486  add     rsp, 20h
0x14003b48a  pop     rdi
0x14003b48b  retn
```
