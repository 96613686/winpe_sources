# CDsmRefreshTask::Start(IUnknown *,ushort *)

- ea: `0x18000d170`
- end: `0x18000d245`
- name: `?Start@CDsmRefreshTask@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `213`
- prototype: `__int64 __fastcall(CDsmRefreshTask *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800092c0`
- `0x18000d0d8`
- `0x18000d170`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall CDsmRefreshTask::Start(CDsmRefreshTask *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  unsigned int refreshed; // edi
  int v5; // ebx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_50c5148a0e7b32a321fc647e1a8da8e2_Traceguids);
  refreshed = RefreshAllDevices();
  v7 = 0;
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         &v7);
  if ( v5 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_50c5148a0e7b32a321fc647e1a8da8e2_Traceguids);
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 32LL))(v7, refreshed);
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d170  mov     [rsp+arg_0], rbx
0x18000d175  mov     [rsp+arg_10], rsi
0x18000d17a  push    rdi
0x18000d17b  sub     rsp, 20h
0x18000d17f  mov     rbx, rdx
0x18000d182  lea     rsi, WPP_GLOBAL_Control
0x18000d189  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d190  cmp     rcx, rsi
0x18000d193  jz      short loc_18000D1B0
0x18000d195  test    byte ptr [rcx+1Ch], 1
0x18000d199  jz      short loc_18000D1B0
0x18000d19b  mov     edx, 0Bh
0x18000d1a0  lea     r8, WPP_50c5148a0e7b32a321fc647e1a8da8e2_Traceguids
0x18000d1a7  mov     rcx, [rcx+10h]
0x18000d1ab  call    WPP_SF_
0x18000d1b0  call    ?RefreshAllDevices@@YAJXZ; RefreshAllDevices(void)
0x18000d1b5  mov     edi, eax
0x18000d1b7  mov     [rsp+28h+arg_8], 0
0x18000d1c0  mov     rcx, [rbx]
0x18000d1c3  mov     rax, [rcx]
0x18000d1c6  lea     r8, [rsp+28h+arg_8]
0x18000d1cb  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000d1d2  mov     rcx, rbx
0x18000d1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1da  mov     ebx, eax
0x18000d1dc  test    eax, eax
0x18000d1de  js      short loc_18000D21C
0x18000d1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1e7  cmp     rcx, rsi
0x18000d1ea  jz      short loc_18000D207
0x18000d1ec  test    byte ptr [rcx+1Ch], 1
0x18000d1f0  jz      short loc_18000D207
0x18000d1f2  mov     edx, 0Ch
0x18000d1f7  lea     r8, WPP_50c5148a0e7b32a321fc647e1a8da8e2_Traceguids
0x18000d1fe  mov     rcx, [rcx+10h]
0x18000d202  call    WPP_SF_
0x18000d207  mov     rcx, [rsp+28h+arg_8]
0x18000d20c  mov     rax, [rcx]
0x18000d20f  mov     edx, edi
0x18000d211  mov     rax, [rax+20h]
0x18000d215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d21a  mov     ebx, eax
0x18000d21c  mov     rcx, [rsp+28h+arg_8]
0x18000d221  test    rcx, rcx
0x18000d224  jz      short loc_18000D233
0x18000d226  mov     rax, [rcx]
0x18000d229  mov     rax, [rax+10h]
0x18000d22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d232  nop
0x18000d233  mov     eax, ebx
0x18000d235  mov     rbx, [rsp+28h+arg_0]
0x18000d23a  mov     rsi, [rsp+28h+arg_10]
0x18000d23f  add     rsp, 20h
0x18000d243  pop     rdi
0x18000d244  retn
```
