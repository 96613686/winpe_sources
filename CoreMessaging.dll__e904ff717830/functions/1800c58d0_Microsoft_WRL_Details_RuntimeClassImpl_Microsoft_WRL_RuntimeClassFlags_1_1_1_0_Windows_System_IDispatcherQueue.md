# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IDispatcherQueueTimer,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800c58d0`
- end: `0x1800c592f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIDispatcherQueueTimer@System@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800c5630`
- `0x1800c58d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c58f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c58f2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IDispatcherQueueTimer,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::System::IDispatcherQueueTimer,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800c58d0  mov     [rsp+arg_0], rbx
0x1800c58d5  push    rdi
0x1800c58d6  sub     rsp, 20h
0x1800c58da  mov     qword ptr [r8], 0
0x1800c58e1  mov     ecx, 20h ; ' '; cb
0x1800c58e6  mov     dword ptr [rdx], 0
0x1800c58ec  mov     rbx, r8
0x1800c58ef  mov     rdi, rdx
0x1800c58f2  call    cs:__imp_CoTaskMemAlloc
0x1800c58f8  mov     r8, rax
0x1800c58fb  test    rax, rax
0x1800c58fe  jnz     short loc_1800C5907
0x1800c5900  mov     eax, 8007000Eh
0x1800c5905  jmp     short loc_1800C5924
0x1800c5907  lea     rdx, [rsp+28h+arg_8]
0x1800c590c  mov     [rsp+28h+arg_8], 0
0x1800c5914  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIDispatcherQueueTimer@System@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::System::IDispatcherQueueTimer,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800c5919  mov     dword ptr [rdi], 2
0x1800c591f  xor     eax, eax
0x1800c5921  mov     [rbx], r8
0x1800c5924  mov     rbx, [rsp+28h+arg_0]
0x1800c5929  add     rsp, 20h
0x1800c592d  pop     rdi
0x1800c592e  retn
```
