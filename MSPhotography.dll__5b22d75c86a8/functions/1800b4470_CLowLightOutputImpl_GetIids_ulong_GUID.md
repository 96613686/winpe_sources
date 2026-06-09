# CLowLightOutputImpl::GetIids(ulong *,_GUID * *)

- ea: `0x1800b4470`
- end: `0x1800b44cf`
- name: `?GetIids@CLowLightOutputImpl@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(CLowLightOutputImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800b4340`
- `0x1800b4470`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4492`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4492`

## pseudocode

```c
__int64 __fastcall CLowLightOutputImpl::GetIids(CLowLightOutputImpl *this, unsigned int *a2, struct _GUID **a3)
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Media::Core::ILowLightOutputInternal,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x1800b4470  mov     [rsp+arg_0], rbx
0x1800b4475  push    rdi
0x1800b4476  sub     rsp, 20h
0x1800b447a  mov     qword ptr [r8], 0
0x1800b4481  mov     ecx, 20h ; ' '; cb
0x1800b4486  mov     dword ptr [rdx], 0
0x1800b448c  mov     rbx, r8
0x1800b448f  mov     rdi, rdx
0x1800b4492  call    cs:__imp_CoTaskMemAlloc
0x1800b4498  mov     r8, rax
0x1800b449b  test    rax, rax
0x1800b449e  jnz     short loc_1800B44A7
0x1800b44a0  mov     eax, 8007000Eh
0x1800b44a5  jmp     short loc_1800B44C4
0x1800b44a7  lea     rdx, [rsp+28h+arg_8]
0x1800b44ac  mov     [rsp+28h+arg_8], 0
0x1800b44b4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UILowLightOutputInternal@Core@Media@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Media::Core::ILowLightOutputInternal,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800b44b9  mov     dword ptr [rdi], 2
0x1800b44bf  xor     eax, eax
0x1800b44c1  mov     [rbx], r8
0x1800b44c4  mov     rbx, [rsp+28h+arg_0]
0x1800b44c9  add     rsp, 20h
0x1800b44cd  pop     rdi
0x1800b44ce  retn
```
