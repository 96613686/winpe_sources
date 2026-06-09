# CSceneAnalyzedEventArgsImpl::GetIids(ulong *,_GUID * *)

- ea: `0x1800b44e0`
- end: `0x1800b453f`
- name: `?GetIids@CSceneAnalyzedEventArgsImpl@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(CSceneAnalyzedEventArgsImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800b4364`
- `0x1800b44e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4502`

## pseudocode

```c
__int64 __fastcall CSceneAnalyzedEventArgsImpl::GetIids(
        CSceneAnalyzedEventArgsImpl *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Media::Core::ISceneAnalyzedEventArgs,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x1800b44e0  mov     [rsp+arg_0], rbx
0x1800b44e5  push    rdi
0x1800b44e6  sub     rsp, 20h
0x1800b44ea  mov     qword ptr [r8], 0
0x1800b44f1  mov     ecx, 20h ; ' '; cb
0x1800b44f6  mov     dword ptr [rdx], 0
0x1800b44fc  mov     rbx, r8
0x1800b44ff  mov     rdi, rdx
0x1800b4502  call    cs:__imp_CoTaskMemAlloc
0x1800b4508  mov     r8, rax
0x1800b450b  test    rax, rax
0x1800b450e  jnz     short loc_1800B4517
0x1800b4510  mov     eax, 8007000Eh
0x1800b4515  jmp     short loc_1800B4534
0x1800b4517  lea     rdx, [rsp+28h+arg_8]
0x1800b451c  mov     [rsp+28h+arg_8], 0
0x1800b4524  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UISceneAnalyzedEventArgs@Core@Media@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Media::Core::ISceneAnalyzedEventArgs,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800b4529  mov     dword ptr [rdi], 2
0x1800b452f  xor     eax, eax
0x1800b4531  mov     [rbx], r8
0x1800b4534  mov     rbx, [rsp+28h+arg_0]
0x1800b4539  add     rsp, 20h
0x1800b453d  pop     rdi
0x1800b453e  retn
```
