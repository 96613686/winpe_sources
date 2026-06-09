# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CloudExperienceHostBroker::Account::ILocalAccountManager,IInspectable,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180024250`
- end: `0x1800242ba`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UILocalAccountManager@Account@CloudExperienceHostBroker@@UIInspectable@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800242c0`

## callees

- `0x18001e018`
- `0x180024250`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024272`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024272`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CloudExperienceHostBroker::Account::ILocalAccountManager,IInspectable,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_7e71d877_44af_4314_9aab_539fadaf61b5;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180024250  mov     [rsp+arg_0], rbx
0x180024255  push    rdi
0x180024256  sub     rsp, 20h
0x18002425a  mov     qword ptr [r8], 0
0x180024261  mov     ecx, 30h ; '0'; cb
0x180024266  mov     dword ptr [rdx], 0
0x18002426c  mov     rbx, r8
0x18002426f  mov     rdi, rdx
0x180024272  call    cs:__imp_CoTaskMemAlloc
0x180024278  mov     r8, rax
0x18002427b  test    rax, rax
0x18002427e  jnz     short loc_180024287
0x180024280  mov     eax, 8007000Eh
0x180024285  jmp     short loc_1800242AF
0x180024287  movups  xmm0, xmmword ptr cs:_GUID_7e71d877_44af_4314_9aab_539fadaf61b5.Data1
0x18002428e  lea     rdx, [rsp+28h+arg_8]
0x180024293  mov     [rsp+28h+arg_8], 1
0x18002429b  movdqu  xmmword ptr [rax], xmm0
0x18002429f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIInspectable@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800242a4  mov     dword ptr [rdi], 3
0x1800242aa  xor     eax, eax
0x1800242ac  mov     [rbx], r8
0x1800242af  mov     rbx, [rsp+28h+arg_0]
0x1800242b4  add     rsp, 20h
0x1800242b8  pop     rdi
0x1800242b9  retn
```
