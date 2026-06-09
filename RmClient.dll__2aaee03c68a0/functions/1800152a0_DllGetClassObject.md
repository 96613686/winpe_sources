# DllGetClassObject

- ea: `0x1800152a0`
- end: `0x1800152e0`
- name: `DllGetClassObject`
- size: `64`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000dc80`
- `0x180014b48`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 *v4; // rax

  v4 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  return Microsoft::WRL::Details::GetClassObject<1>((Microsoft::WRL::Details *)v4, ppv);
}

```

## disassembly

```asm
0x1800152a0  mov     [rsp+arg_0], rbx
0x1800152a5  mov     [rsp+arg_8], rsi
0x1800152aa  push    rdi
0x1800152ab  sub     rsp, 30h
0x1800152af  mov     rbx, r8
0x1800152b2  mov     rdi, rdx
0x1800152b5  mov     rsi, rcx
0x1800152b8  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800152bd  mov     r9, rdi
0x1800152c0  mov     [rsp+38h+var_18], rbx; PVOID
0x1800152c5  mov     r8, rsi
0x1800152c8  mov     rcx, rax; this
0x1800152cb  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x1800152d0  mov     rbx, [rsp+38h+arg_0]
0x1800152d5  mov     rsi, [rsp+38h+arg_8]
0x1800152da  add     rsp, 30h
0x1800152de  pop     rdi
0x1800152df  retn
```
