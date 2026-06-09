# GetTaskbarPinCount(IPinnedList *)

- ea: `0x18001a9f0`
- end: `0x18001ab0c`
- name: `?GetTaskbarPinCount@@YAHPEAUIPinnedList@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(struct IPinnedList *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800067b0`
- `0x18000e2bc`
- `0x180018b18`
- `0x18001a9f0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aaf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aaf3`

## string_xrefs

- `0x18001aa33`: `shell\inc\TaskbarDefaultPinsHelpers.h`
- `0x18001aa9c`: `shell\inc\TaskbarDefaultPinsHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetTaskbarPinCount(struct IPinnedList *a1)
{
  __int64 (*v1)(void); // rbx
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rax
  int v5; // edi
  void *v6; // rcx
  const char *v7; // r9
  __int64 result; // rax
  void *v9; // rcx
  int v10; // [rsp+20h] [rbp-38h]
  LPVOID *p_pv; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+38h] [rbp-20h] BYREF
  char v13; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID pv; // [rsp+60h] [rbp+8h] BYREF
  __int64 *v16; // [rsp+68h] [rbp+10h] BYREF

  v16 = 0;
  v1 = *(__int64 (**)(void))(*(_QWORD *)a1 + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  try
  {
    v2 = v1();
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"shell\\inc\\TaskbarDefaultPinsHelpers.h",
        (const char *)(unsigned int)v2,
        v10);
    v3 = 0;
    while ( 1 )
    {
      pv = 0;
      v4 = *v16;
      p_pv = &pv;
      v12 = 0;
      v13 = 1;
      v5 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v4 + 24))(v16, 1, &v12);
      wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x47,
          (unsigned int)"shell\\inc\\TaskbarDefaultPinsHelpers.h",
          (const char *)(unsigned int)v5,
          v10);
      if ( v5 == 1 )
        break;
      ++v3;
      v9 = pv;
      pv = 0;
      if ( v9 )
        CoTaskMemFree(v9);
    }
    v6 = pv;
    pv = 0;
    if ( v6 )
      CoTaskMemFree(v6);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
    result = v3;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x52,
      (unsigned int)"shell\\inc\\TaskbarDefaultPinsHelpers.h",
      v7);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001a9f0  mov     [rsp+arg_10], rbx
0x18001a9f5  push    rdi
0x18001a9f6  sub     rsp, 50h
0x18001a9fa  mov     rdi, rcx
0x18001a9fd  mov     [rsp+58h+arg_8], 0
0x18001aa06  mov     rax, [rcx]
0x18001aa09  mov     rbx, [rax+18h]
0x18001aa0d  lea     rcx, [rsp+58h+arg_8]
0x18001aa12  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001aa17  lea     rdx, [rsp+58h+arg_8]
0x18001aa1c  mov     rcx, rdi
0x18001aa1f  mov     rax, rbx
0x18001aa22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa27  mov     rcx, [rsp+58h]; this
0x18001aa2c  test    eax, eax
0x18001aa2e  jns     short loc_18001AA44
0x18001aa30  mov     r9d, eax; char *
0x18001aa33  lea     r8, aShellIncTaskba; "shell\\inc\\TaskbarDefaultPinsHelpers.h"
0x18001aa3a  mov     edx, 40h ; '@'; void *
0x18001aa3f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001aa44  xor     ebx, ebx
0x18001aa46  mov     [rsp+58h+pv], 0
0x18001aa4f  mov     rcx, [rsp+58h+arg_8]
0x18001aa54  mov     rax, [rcx]
0x18001aa57  lea     rdx, [rsp+58h+pv]
0x18001aa5c  mov     [rsp+58h+var_28], rdx
0x18001aa61  mov     [rsp+58h+var_20], 0
0x18001aa6a  mov     [rsp+58h+var_18], 1
0x18001aa6f  xor     r9d, r9d
0x18001aa72  lea     r8, [rsp+58h+var_20]
0x18001aa77  lea     edx, [r9+1]
0x18001aa7b  mov     rax, [rax+18h]
0x18001aa7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa84  mov     edi, eax
0x18001aa86  lea     rcx, [rsp+58h+var_28]
0x18001aa8b  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001aa90  mov     rcx, [rsp+58h]; this
0x18001aa95  test    edi, edi
0x18001aa97  jns     short loc_18001AAAD
0x18001aa99  mov     r9d, edi; char *
0x18001aa9c  lea     r8, aShellIncTaskba; "shell\\inc\\TaskbarDefaultPinsHelpers.h"
0x18001aaa3  mov     edx, 47h ; 'G'; void *
0x18001aaa8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001aaad  cmp     edi, 1
0x18001aab0  jnz     short loc_18001AADA
0x18001aab2  mov     rcx, [rsp+58h+pv]; pv
0x18001aab7  mov     [rsp+58h+pv], 0
0x18001aac0  test    rcx, rcx
0x18001aac3  jz      short loc_18001AACC
0x18001aac5  call    cs:__imp_CoTaskMemFree
0x18001aacb  nop
0x18001aacc  lea     rcx, [rsp+58h+arg_8]
0x18001aad1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001aad6  mov     eax, ebx
0x18001aad8  jmp     short loc_18001AB00
0x18001aada  inc     ebx
0x18001aadc  mov     rcx, [rsp+58h+pv]; pv
0x18001aae1  mov     [rsp+58h+pv], 0
0x18001aaea  test    rcx, rcx
0x18001aaed  jz      loc_18001AA46
0x18001aaf3  call    cs:__imp_CoTaskMemFree
0x18001aaf9  jmp     loc_18001AA46
0x18001aafe  xor     eax, eax
0x18001ab00  mov     rbx, [rsp+58h+arg_10]
0x18001ab05  add     rsp, 50h
0x18001ab09  pop     rdi
0x18001ab0a  retn
```
