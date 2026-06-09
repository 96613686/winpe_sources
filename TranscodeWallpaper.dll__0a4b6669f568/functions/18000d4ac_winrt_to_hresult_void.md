# winrt::to_hresult(void)

- ea: `0x18000d4ac`
- end: `0x18000d4f5`
- name: `?to_hresult@winrt@@YA?AUhresult@1@XZ`
- size: `73`
- prototype: `_DWORD *__fastcall(_DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e839`
- `0x18000e88f`
- `0x18000ec12`

## callees

- `0x180002cc0`
- `0x18000d4ac`
- `0x18000f010`

## pseudocode

```c
_DWORD *__fastcall winrt::to_hresult(_DWORD *a1)
{
  _DWORD *; // rax
  _BYTE *v3; // rbp
  __int64 *v4; // rax
  OLECHAR *v5; // rcx
  volatile signed __int32 *v6; // rbx
  int v7; // eax
  HANDLE ProcessHeap; // rax
  _BYTE *v9; // rbp
  __int64 *v10; // rax
  OLECHAR *v11; // rcx
  volatile signed __int32 *v12; // rbx
  int v13; // eax
  HANDLE v14; // rax
  _BYTE *v15; // rbp
  __int64 *v16; // rax
  OLECHAR *v17; // rcx
  volatile signed __int32 *v18; // rbx
  int v19; // eax
  HANDLE v20; // rax
  _BYTE *v21; // rdx
  _BYTE *v22; // rdx
  _BYTE *v23; // rdx
  _BYTE *v24; // rdx
  _BYTE *v25; // rdx
  _BYTE v26[32]; // [rsp+0h] [rbp-78h] BYREF
  const winrt::hresult_error *v27; // [rsp+20h] [rbp-58h] BYREF
  const std::out_of_range *v28; // [rsp+28h] [rbp-50h] BYREF
  const std::invalid_argument *v29; // [rsp+30h] [rbp-48h] BYREF
  const std::exception *v30; // [rsp+38h] [rbp-40h] BYREF
  void *retaddr; // [rsp+78h] [rbp+0h]
  _DWORD *v32; // [rsp+80h] [rbp+8h]

  if ( winrt_to_hresult_handler )
    goto LABEL_2;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    throw;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &winrt::hresult_error `RTTI Type Descriptor', &v27) )
    {
      v21 = v26;
      winrt::hresult_error::to_abi(*((_QWORD *)v21 + 4), *((_DWORD **)v21 + 16));
       = v32;
      __eh34_try_continuation(0, &winrt::hresult_error `RTTI Type Descriptor', &loc_18000D4D6);
      goto LABEL_49;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v22 = v26;
      **((_DWORD **)v22 + 16) = -2147024882;
       = v32;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000D4E4);
      goto LABEL_49;
    }
    if ( __eh34_catch_type(0, &std::out_of_range `RTTI Type Descriptor', &v28) )
    {
      v23 = v26;
      v3 = v23;
      *((_DWORD *)v23 + 22) = 0;
      *((_OWORD *)v23 + 6) = 0;
      *((_QWORD *)v23 + 17) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v23 + 5) + 8LL))(*((_QWORD *)v23 + 5));
      v4 = (__int64 *)winrt::to_hstring<char const *,0>(
                        (struct winrt::impl::shared_hstring_header **)v3 + 18,
                        (const CHAR **)v3 + 17);
      *((_QWORD *)v3 + 8) = 0;
      *((_DWORD *)v3 + 18) = -1430532899;
      *((_DWORD *)v3 + 19) = -2147483637;
      *((_QWORD *)v3 + 10) = 0;
      winrt::hresult_error::originate((__int64)(v3 + 64), 0x8000000B, *v4, (unsigned int *)v3 + 22);
      winrt::hresult_error::to_abi((__int64)(v3 + 64), *((_DWORD **)v3 + 16));
      if ( *((_QWORD *)v3 + 10) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)v3 + 10);
      v5 = (OLECHAR *)*((_QWORD *)v3 + 8);
      if ( v5 )
        WINRT_IMPL_SysFreeString(v5);
      v6 = (volatile signed __int32 *)*((_QWORD *)v3 + 18);
      if ( v6 )
      {
        v7 = _InterlockedDecrement(v6 + 6);
        if ( v7 )
        {
          if ( v7 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v6);
        }
      }
       = v32;
      __eh34_try_continuation(0, &std::out_of_range `RTTI Type Descriptor', &loc_18000D4E6);
      goto LABEL_49;
    }
    if ( __eh34_catch_type(0, &std::invalid_argument `RTTI Type Descriptor', &v29) )
    {
      v24 = v26;
      v9 = v24;
      *((_DWORD *)v24 + 22) = 0;
      *((_OWORD *)v24 + 6) = 0;
      *((_QWORD *)v24 + 17) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v24 + 6) + 8LL))(*((_QWORD *)v24 + 6));
      v10 = (__int64 *)winrt::to_hstring<char const *,0>(
                         (struct winrt::impl::shared_hstring_header **)v9 + 18,
                         (const CHAR **)v9 + 17);
      *((_QWORD *)v9 + 8) = 0;
      *((_DWORD *)v9 + 18) = -1430532899;
      *((_DWORD *)v9 + 19) = -2147024809;
      *((_QWORD *)v9 + 10) = 0;
      winrt::hresult_error::originate((__int64)(v9 + 64), 0x80070057, *v10, (unsigned int *)v9 + 22);
      winrt::hresult_error::to_abi((__int64)(v9 + 64), *((_DWORD **)v9 + 16));
      if ( *((_QWORD *)v9 + 10) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)v9 + 10);
      v11 = (OLECHAR *)*((_QWORD *)v9 + 8);
      if ( v11 )
        WINRT_IMPL_SysFreeString(v11);
      v12 = (volatile signed __int32 *)*((_QWORD *)v9 + 18);
      if ( v12 )
      {
        v13 = _InterlockedDecrement(v12 + 6);
        if ( v13 )
        {
          if ( v13 < 0 )
            abort();
        }
        else
        {
          v14 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v14, 0, (LPVOID)v12);
        }
      }
       = v32;
      __eh34_try_continuation(0, &std::invalid_argument `RTTI Type Descriptor', &loc_18000D4E8);
      goto LABEL_49;
    }
    if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v30) )
    {
      v25 = v26;
      v15 = v25;
      *((_DWORD *)v25 + 22) = 0;
      *((_OWORD *)v25 + 6) = 0;
      *((_QWORD *)v25 + 17) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v25 + 7) + 8LL))(*((_QWORD *)v25 + 7));
      v16 = (__int64 *)winrt::to_hstring<char const *,0>(
                         (struct winrt::impl::shared_hstring_header **)v15 + 18,
                         (const CHAR **)v15 + 17);
      *((_QWORD *)v15 + 8) = 0;
      *((_DWORD *)v15 + 18) = -1430532899;
      *((_DWORD *)v15 + 19) = -2147467259;
      *((_QWORD *)v15 + 10) = 0;
      winrt::hresult_error::originate((__int64)(v15 + 64), 0x80004005, *v16, (unsigned int *)v15 + 22);
      winrt::hresult_error::to_abi((__int64)(v15 + 64), *((_DWORD **)v15 + 16));
      if ( *((_QWORD *)v15 + 10) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)v15 + 10);
      v17 = (OLECHAR *)*((_QWORD *)v15 + 8);
      if ( v17 )
        WINRT_IMPL_SysFreeString(v17);
      v18 = (volatile signed __int32 *)*((_QWORD *)v15 + 18);
      if ( v18 )
      {
        v19 = _InterlockedDecrement(v18 + 6);
        if ( v19 )
        {
          if ( v19 < 0 )
            abort();
        }
        else
        {
          v20 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v20, 0, (LPVOID)v18);
        }
      }
       = v32;
      __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_18000D4D6);
LABEL_49:
      ;
    }
  }
LABEL_2:
  *a1 = winrt_to_hresult_handler(retaddr);
   = a1;
  goto LABEL_49;
}

```

## disassembly

```asm
0x18000d4ac  mov     [rsp+arg_0], rcx
0x18000d4b1  push    rbx
0x18000d4b2  sub     rsp, 70h
0x18000d4b6  mov     rbx, rcx
0x18000d4b9  mov     rax, cs:?winrt_to_hresult_handler@@3P6AHPEAX@_EEA
0x18000d4c0  test    rax, rax
0x18000d4c3  jz      short loc_18000D4EA
0x18000d4c5  mov     rcx, [rsp+78h]
0x18000d4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4cf  mov     [rbx], eax
0x18000d4d1  mov     rax, rbx
0x18000d4d4  jmp     short loc_18000D4DE
0x18000d4d6  mov     rax, [rsp+78h+arg_0]
0x18000d4de  add     rsp, 70h
0x18000d4e2  pop     rbx
0x18000d4e3  retn
0x18000d4e4  jmp     short loc_18000D4D6
0x18000d4e6  jmp     short loc_18000D4D6
0x18000d4e8  jmp     short loc_18000D4D6
0x18000d4ea  xor     edx, edx; pThrowInfo
0x18000d4ec  xor     ecx, ecx; pExceptionObject
0x18000d4ee  call    _CxxThrowException_0
```
