# Microsoft::WRL::ComPtr<IWICBitmap>::As<IWICBitmapSource>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWICBitmapSource>>)

- ea: `0x1800a4024`
- end: `0x1800a4078`
- name: `??$As@UIWICBitmapSource@@@?$ComPtr@UIWICBitmap@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@@Details@12@@Z`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800a7520`
- `0x1800a8df0`

## callees

- `0x18009c44c`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IWICBitmap>::As<IWICBitmapSource>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        __int64 *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(a2);
  return v4(v3, &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94, a2);
}

```

## disassembly

```asm
0x1800a4024  push    rdi
0x1800a4026  sub     rsp, 30h
0x1800a402a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800a4033  mov     [rsp+38h+arg_0], rbx
0x1800a4038  mov     [rsp+38h+arg_8], rsi
0x1800a403d  mov     rbx, rdx
0x1800a4040  mov     rsi, [rcx]
0x1800a4043  mov     rax, [rsi]
0x1800a4046  mov     rdi, [rax]
0x1800a4049  mov     rcx, rdx
0x1800a404c  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a4051  mov     r8, rbx
0x1800a4054  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x1800a405b  mov     rcx, rsi
0x1800a405e  mov     rax, rdi
0x1800a4061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4066  nop
0x1800a4067  mov     rbx, [rsp+38h+arg_0]
0x1800a406c  mov     rsi, [rsp+38h+arg_8]
0x1800a4071  add     rsp, 30h
0x1800a4075  pop     rdi
0x1800a4076  retn
```
