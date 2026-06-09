# winrt::implements<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManager,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Management::Update::IWindowsUpdateManagerFactory,winrt::Windows::Management::Update::IWindowsUpdateManagerFactory2>::GetIids(ulong *,_GUID * *)

- ea: `0x1800147d0`
- end: `0x18001484c`
- name: `?GetIids@?$implements@UWindowsUpdateManager@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@UIWindowsUpdateManagerFactory@3456@UIWindowsUpdateManagerFactory2@3456@@winrt@@QEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `124`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180014980`
- `0x1800149a0`
- `0x1800149c0`

## callees

- `0x180008df1`
- `0x180008e45`
- `0x1800147d0`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManager,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Management::Update::IWindowsUpdateManagerFactory,winrt::Windows::Management::Update::IWindowsUpdateManagerFactory2>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  unsigned int v5; // eax
  unsigned int v6; // ebx
  void *v7; // rax
  unsigned int v9; // [rsp+20h] [rbp-18h] BYREF
  void *Src; // [rsp+28h] [rbp-10h]

  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 32LL))(a1, &v9);
  v5 = v9;
  v6 = 0;
  if ( v9 )
  {
    *a2 = v9;
    v7 = WINRT_IMPL_CoTaskMemAlloc(16LL * v5);
    *a3 = v7;
    if ( v7 )
      memmove_0(v7, Src, 16LL * v9);
    else
      return (unsigned int)-2147024882;
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1800147d0  mov     [rsp+arg_0], rbx
0x1800147d5  mov     [rsp+arg_8], rsi
0x1800147da  push    rdi
0x1800147db  sub     rsp, 30h
0x1800147df  mov     rax, [rcx]
0x1800147e2  mov     rsi, rdx
0x1800147e5  lea     rdx, [rsp+38h+var_18]
0x1800147ea  mov     rdi, r8
0x1800147ed  mov     rax, [rax+20h]
0x1800147f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147f6  mov     eax, [rsp+38h+var_18]
0x1800147fa  xor     ebx, ebx
0x1800147fc  test    eax, eax
0x1800147fe  jz      short loc_180014834
0x180014800  mov     ecx, eax
0x180014802  mov     [rsi], eax
0x180014804  shl     rcx, 4; cb
0x180014808  call    WINRT_IMPL_CoTaskMemAlloc
0x18001480d  mov     [rdi], rax
0x180014810  test    rax, rax
0x180014813  jnz     short loc_18001481C
0x180014815  mov     ebx, 8007000Eh
0x18001481a  jmp     short loc_180014839
0x18001481c  mov     r8d, [rsp+38h+var_18]
0x180014821  mov     rcx, rax; void *
0x180014824  mov     rdx, [rsp+38h+Src]; Src
0x180014829  shl     r8, 4; Size
0x18001482d  call    memmove_0
0x180014832  jmp     short loc_180014839
0x180014834  mov     [rsi], ebx
0x180014836  mov     [rdi], rbx
0x180014839  mov     rsi, [rsp+38h+arg_8]
0x18001483e  mov     eax, ebx
0x180014840  mov     rbx, [rsp+38h+arg_0]
0x180014845  add     rsp, 30h
0x180014849  pop     rdi
0x18001484a  retn
```
