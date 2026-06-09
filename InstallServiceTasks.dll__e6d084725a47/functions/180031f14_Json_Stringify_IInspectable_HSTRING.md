# Json_Stringify(IInspectable *,HSTRING__ * *)

- ea: `0x180031f14`
- end: `0x180031fda`
- name: `?Json_Stringify@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(struct IInspectable *, HSTRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800292b0`
- `0x180029a64`

## callees

- `0x18000760c`
- `0x180031f14`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031f7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031fb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031f7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031fb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Json_Stringify(struct IInspectable *a1, HSTRING *a2)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  HSTRING v8; // rax
  HSTRING v9; // rcx
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF
  __int64 v12; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v12 = 0;
  QueryInterface = a1->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v5 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         a1,
         &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e,
         &v12);
  if ( v5 >= 0 )
  {
    string = 0;
    v6 = v12;
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v5 = v7(v6, &string);
    if ( v5 < 0 )
    {
      v9 = string;
    }
    else
    {
      v8 = string;
      v9 = 0;
      string = 0;
      *a2 = v8;
    }
    WindowsDeleteString(v9);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180031f14  mov     r11, rsp
0x180031f17  mov     [r11+18h], rbx
0x180031f1b  mov     [r11+20h], rsi
0x180031f1f  push    rdi
0x180031f20  sub     rsp, 20h
0x180031f24  mov     rsi, rdx
0x180031f27  mov     rdi, rcx
0x180031f2a  mov     qword ptr [rdx], 0
0x180031f31  mov     qword ptr [r11+10h], 0
0x180031f39  mov     rax, [rcx]
0x180031f3c  mov     rbx, [rax]
0x180031f3f  lea     rcx, [r11+10h]
0x180031f43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031f48  lea     r8, [rsp+28h+arg_8]
0x180031f4d  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x180031f54  mov     rcx, rdi
0x180031f57  mov     rax, rbx
0x180031f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f5f  mov     ebx, eax
0x180031f61  test    eax, eax
0x180031f63  js      short loc_180031FBE
0x180031f65  mov     [rsp+28h+string], 0
0x180031f6e  mov     rdi, [rsp+28h+arg_8]
0x180031f73  mov     rax, [rdi]
0x180031f76  mov     rbx, [rax+38h]
0x180031f7a  xor     ecx, ecx; string
0x180031f7c  call    cs:__imp_WindowsDeleteString
0x180031f82  mov     [rsp+28h+string], 0
0x180031f8b  lea     rdx, [rsp+28h+string]
0x180031f90  mov     rcx, rdi
0x180031f93  mov     rax, rbx
0x180031f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f9b  mov     ebx, eax
0x180031f9d  test    eax, eax
0x180031f9f  js      short loc_180031FB2
0x180031fa1  mov     rax, [rsp+28h+string]
0x180031fa6  xor     ecx, ecx
0x180031fa8  mov     [rsp+28h+string], rcx
0x180031fad  mov     [rsi], rax
0x180031fb0  jmp     short loc_180031FB7
0x180031fb2  mov     rcx, [rsp+28h+string]; string
0x180031fb7  call    cs:__imp_WindowsDeleteString
0x180031fbd  nop
0x180031fbe  lea     rcx, [rsp+28h+arg_8]
0x180031fc3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031fc8  mov     eax, ebx
0x180031fca  mov     rbx, [rsp+28h+arg_10]
0x180031fcf  mov     rsi, [rsp+28h+arg_18]
0x180031fd4  add     rsp, 20h
0x180031fd8  pop     rdi
0x180031fd9  retn
```
