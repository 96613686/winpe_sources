# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IDiagnosticRunner,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001f400`
- end: `0x18001f45f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIDiagnosticRunner@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001f3d0`
- `0x18001f400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f422`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f422`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IDiagnosticRunner,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,IDiagnosticRunner,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18001f400  mov     [rsp+arg_0], rbx
0x18001f405  push    rdi
0x18001f406  sub     rsp, 20h
0x18001f40a  mov     qword ptr [r8], 0
0x18001f411  mov     ecx, 20h ; ' '; cb
0x18001f416  mov     dword ptr [rdx], 0
0x18001f41c  mov     rbx, r8
0x18001f41f  mov     rdi, rdx
0x18001f422  call    cs:__imp_CoTaskMemAlloc
0x18001f428  mov     r8, rax
0x18001f42b  test    rax, rax
0x18001f42e  jnz     short loc_18001F437
0x18001f430  mov     eax, 8007000Eh
0x18001f435  jmp     short loc_18001F454
0x18001f437  lea     rdx, [rsp+28h+arg_8]
0x18001f43c  mov     [rsp+28h+arg_8], 0
0x18001f444  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIDiagnosticRunner@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,IDiagnosticRunner,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001f449  mov     dword ptr [rdi], 2
0x18001f44f  xor     eax, eax
0x18001f451  mov     [rbx], r8
0x18001f454  mov     rbx, [rsp+28h+arg_0]
0x18001f459  add     rsp, 20h
0x18001f45d  pop     rdi
0x18001f45e  retn
```
