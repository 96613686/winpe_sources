# CReference<float>::GetIids(ulong *,_GUID * *)

- ea: `0x1800b4390`
- end: `0x1800b43ef`
- name: `?GetIids@?$CReference@M@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800b42f8`
- `0x1800b4390`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b43b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b43b2`

## pseudocode

```c
__int64 __fastcall CReference<float>::GetIids(__int64 a1, _DWORD *a2, _QWORD *a3)
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::IReference<float>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x1800b4390  mov     [rsp+arg_0], rbx
0x1800b4395  push    rdi
0x1800b4396  sub     rsp, 20h
0x1800b439a  mov     qword ptr [r8], 0
0x1800b43a1  mov     ecx, 20h ; ' '; cb
0x1800b43a6  mov     dword ptr [rdx], 0
0x1800b43ac  mov     rbx, r8
0x1800b43af  mov     rdi, rdx
0x1800b43b2  call    cs:__imp_CoTaskMemAlloc
0x1800b43b8  mov     r8, rax
0x1800b43bb  test    rax, rax
0x1800b43be  jnz     short loc_1800B43C7
0x1800b43c0  mov     eax, 8007000Eh
0x1800b43c5  jmp     short loc_1800B43E4
0x1800b43c7  lea     rdx, [rsp+28h+arg_8]
0x1800b43cc  mov     [rsp+28h+arg_8], 0
0x1800b43d4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IReference@M@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::IReference<float>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800b43d9  mov     dword ptr [rdi], 2
0x1800b43df  xor     eax, eax
0x1800b43e1  mov     [rbx], r8
0x1800b43e4  mov     rbx, [rsp+28h+arg_0]
0x1800b43e9  add     rsp, 20h
0x1800b43ed  pop     rdi
0x1800b43ee  retn
```
