# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180030c00`
- end: `0x180030c5f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180030818`
- `0x180030c00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030c22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030c22`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,IInspectable,Microsoft::WRL::FtmBase,IWeakReferenceSource>::FillArrayWithIid(
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
0x180030c00  mov     [rsp+arg_0], rbx
0x180030c05  push    rdi
0x180030c06  sub     rsp, 20h
0x180030c0a  mov     qword ptr [r8], 0
0x180030c11  mov     ecx, 20h ; ' '; cb
0x180030c16  mov     dword ptr [rdx], 0
0x180030c1c  mov     rbx, r8
0x180030c1f  mov     rdi, rdx
0x180030c22  call    cs:__imp_CoTaskMemAlloc
0x180030c28  mov     r8, rax
0x180030c2b  test    rax, rax
0x180030c2e  jnz     short loc_180030C37
0x180030c30  mov     eax, 8007000Eh
0x180030c35  jmp     short loc_180030C54
0x180030c37  lea     rdx, [rsp+28h+arg_8]
0x180030c3c  mov     [rsp+28h+arg_8], 0
0x180030c44  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIInspectable@@VFtmBase@23@UIWeakReferenceSource@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,IInspectable,Microsoft::WRL::FtmBase,IWeakReferenceSource>::FillArrayWithIid(ulong *,_GUID *)
0x180030c49  mov     dword ptr [rdi], 2
0x180030c4f  xor     eax, eax
0x180030c51  mov     [rbx], r8
0x180030c54  mov     rbx, [rsp+28h+arg_0]
0x180030c59  add     rsp, 20h
0x180030c5d  pop     rdi
0x180030c5e  retn
```
