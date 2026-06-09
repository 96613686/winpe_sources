# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800269a0`
- end: `0x180026a01`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800269a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800269c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800269c2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_5be0bb6f_da1f_5236_97b2_661b298589e0;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800269a0  mov     [rsp+arg_0], rbx
0x1800269a5  push    rdi
0x1800269a6  sub     rsp, 20h
0x1800269aa  mov     qword ptr [r8], 0
0x1800269b1  mov     ecx, 20h ; ' '; cb
0x1800269b6  mov     dword ptr [rdx], 0
0x1800269bc  mov     rbx, r8
0x1800269bf  mov     rdi, rdx
0x1800269c2  call    cs:__imp_CoTaskMemAlloc
0x1800269c8  test    rax, rax
0x1800269cb  jnz     short loc_1800269D4
0x1800269cd  mov     eax, 8007000Eh
0x1800269d2  jmp     short loc_1800269F6
0x1800269d4  movups  xmm0, xmmword ptr cs:_GUID_5be0bb6f_da1f_5236_97b2_661b298589e0.Data1
0x1800269db  movdqu  xmmword ptr [rax], xmm0
0x1800269df  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800269e6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800269eb  mov     dword ptr [rdi], 2
0x1800269f1  mov     [rbx], rax
0x1800269f4  xor     eax, eax
0x1800269f6  mov     rbx, [rsp+28h+arg_0]
0x1800269fb  add     rsp, 20h
0x1800269ff  pop     rdi
0x180026a00  retn
```
