# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180012400`
- end: `0x180012466`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180011de4`
- `0x180012400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012422`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012422`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<SystemSettings::DataModel::ISettingItem *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180012400  mov     [rsp+arg_0], rbx
0x180012405  push    rdi
0x180012406  sub     rsp, 20h
0x18001240a  mov     qword ptr [r8], 0
0x180012411  mov     ecx, 20h ; ' '; cb
0x180012416  mov     dword ptr [rdx], 0
0x18001241c  mov     rbx, r8
0x18001241f  mov     rdi, rdx
0x180012422  call    cs:__imp_CoTaskMemAlloc
0x180012429  nop     dword ptr [rax+rax+00h]
0x18001242e  mov     r8, rax
0x180012431  test    rax, rax
0x180012434  jnz     short loc_18001243D
0x180012436  mov     eax, 8007000Eh
0x18001243b  jmp     short loc_18001245A
0x18001243d  lea     rdx, [rsp+28h+arg_8]
0x180012442  mov     [rsp+28h+arg_8], 0
0x18001244a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IIterator@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<SystemSettings::DataModel::ISettingItem *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001244f  mov     dword ptr [rdi], 2
0x180012455  xor     eax, eax
0x180012457  mov     [rbx], r8
0x18001245a  mov     rbx, [rsp+28h+arg_0]
0x18001245f  add     rsp, 20h
0x180012463  pop     rdi
0x180012464  retn
```
