# winrt::to_hresult(void)

- ea: `0x180001d30`
- end: `0x180001d88`
- name: `?to_hresult@winrt@@YA?AUhresult@1@XZ`
- size: `88`
- prototype: `_DWORD *__fastcall(_DWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c8b9`
- `0x18000c8f0`
- `0x18000c920`
- `0x18000c950`

## callees

- `0x180001d30`
- `0x180008e5c`
- `0x18000b930`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
_DWORD *__fastcall winrt::to_hresult(_DWORD *a1)
{
  _DWORD *; // rax
  volatile signed __int32 **v3; // rbp
  __int64 v4; // rax
  const CHAR *v5; // rdi
  __int64 v6; // rbx
  const char *v7; // rdx
  unsigned int v8; // r14d
  struct winrt::impl::shared_hstring_header *v9; // rsi
  OLECHAR *v10; // rcx
  volatile signed __int32 **v11; // rbp
  __int64 v12; // rax
  const CHAR *v13; // rdi
  __int64 v14; // rbx
  const char *v15; // rdx
  unsigned int v16; // r14d
  struct winrt::impl::shared_hstring_header *v17; // rsi
  OLECHAR *v18; // rcx
  volatile signed __int32 **v19; // rbp
  __int64 v20; // rax
  const CHAR *v21; // rdi
  __int64 v22; // rbx
  const char *v23; // rdx
  unsigned int v24; // r14d
  struct winrt::impl::shared_hstring_header *v25; // rsi
  OLECHAR *v26; // rcx
  _QWORD *v27; // rdx
  _QWORD *v28; // rdx
  volatile signed __int32 **v29; // rdx
  volatile signed __int32 **v30; // rdx
  volatile signed __int32 **v31; // rdx
  _QWORD v32[6]; // [rsp+0h] [rbp-88h] BYREF
  _DWORD *v33; // [rsp+30h] [rbp-58h]
  const winrt::hresult_error *v34; // [rsp+60h] [rbp-28h] BYREF
  const std::out_of_range *v35; // [rsp+68h] [rbp-20h] BYREF
  const std::invalid_argument *v36; // [rsp+70h] [rbp-18h] BYREF
  const std::exception *v37; // [rsp+78h] [rbp-10h] BYREF

  if ( winrt_to_hresult_handler )
    goto LABEL_2;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    throw;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &winrt::hresult_error `RTTI Type Descriptor', &v34) )
    {
      v27 = v32;
      winrt::hresult_error::to_abi(v27[12], (_DWORD *)v27[6]);
       = v33;
      __eh34_try_continuation(0, &winrt::hresult_error `RTTI Type Descriptor', &loc_180001D69);
      goto LABEL_48;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v28 = v32;
      *(_DWORD *)v28[6] = -2147024882;
       = v33;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180001D77);
      goto LABEL_48;
    }
    if ( __eh34_catch_type(0, &std::out_of_range `RTTI Type Descriptor', &v35) )
    {
      v29 = (volatile signed __int32 **)v32;
      v3 = v29;
      v4 = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29[13] + 8LL))(v29[13]);
      v5 = (const CHAR *)v4;
      v6 = -1;
      do
        ++v6;
      while ( *(_BYTE *)(v4 + v6) );
      v8 = MultiByteToWideChar_0(0xFDE9u, 0, v5, v6, 0, 0);
      if ( v8 )
      {
        v9 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v8, v7);
        MultiByteToWideChar_0(0xFDE9u, 0, v5, v6, *((LPWSTR *)v9 + 2), v8);
        v3[11] = 0;
        v3[7] = (volatile signed __int32 *)v9;
        winrt::handle_type<winrt::impl::hstring_traits>::~handle_type<winrt::impl::hstring_traits>(v3 + 11);
      }
      else
      {
        v3[7] = 0;
        v9 = 0;
      }
      v3[8] = 0;
      *((_DWORD *)v3 + 18) = -1430532899;
      *((_DWORD *)v3 + 19) = -2147483637;
      v3[10] = 0;
      winrt::hresult_error::originate((__int64)(v3 + 8), 0x8000000B, (__int64)v9);
      winrt::hresult_error::to_abi((__int64)(v3 + 8), v3[6]);
      if ( v3[10] )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)v3 + 10);
      v10 = (OLECHAR *)v3[8];
      if ( v10 )
        WINRT_IMPL_SysFreeString(v10);
      winrt::handle_type<winrt::impl::hstring_traits>::~handle_type<winrt::impl::hstring_traits>(v3 + 7);
       = v33;
      __eh34_try_continuation(0, &std::out_of_range `RTTI Type Descriptor', &loc_180001D79);
      goto LABEL_48;
    }
    if ( __eh34_catch_type(0, &std::invalid_argument `RTTI Type Descriptor', &v36) )
    {
      v30 = (volatile signed __int32 **)v32;
      v11 = v30;
      v12 = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30[14] + 8LL))(v30[14]);
      v13 = (const CHAR *)v12;
      v14 = -1;
      do
        ++v14;
      while ( *(_BYTE *)(v12 + v14) );
      v16 = MultiByteToWideChar_0(0xFDE9u, 0, v13, v14, 0, 0);
      if ( v16 )
      {
        v17 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v16, v15);
        MultiByteToWideChar_0(0xFDE9u, 0, v13, v14, *((LPWSTR *)v17 + 2), v16);
        v11[11] = 0;
        v11[7] = (volatile signed __int32 *)v17;
        winrt::handle_type<winrt::impl::hstring_traits>::~handle_type<winrt::impl::hstring_traits>(v11 + 11);
      }
      else
      {
        v11[7] = 0;
        v17 = 0;
      }
      v11[8] = 0;
      *((_DWORD *)v11 + 18) = -1430532899;
      *((_DWORD *)v11 + 19) = -2147024809;
      v11[10] = 0;
      winrt::hresult_error::originate((__int64)(v11 + 8), 0x80070057, (__int64)v17);
      winrt::hresult_error::to_abi((__int64)(v11 + 8), v11[6]);
      if ( v11[10] )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)v11 + 10);
      v18 = (OLECHAR *)v11[8];
      if ( v18 )
        WINRT_IMPL_SysFreeString(v18);
      winrt::handle_type<winrt::impl::hstring_traits>::~handle_type<winrt::impl::hstring_traits>(v11 + 7);
       = v33;
      __eh34_try_continuation(0, &std::invalid_argument `RTTI Type Descriptor', &loc_180001D7B);
      goto LABEL_48;
    }
    if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v37) )
    {
      v31 = (volatile signed __int32 **)v32;
      v19 = v31;
      v20 = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31[15] + 8LL))(v31[15]);
      v21 = (const CHAR *)v20;
      v22 = -1;
      do
        ++v22;
      while ( *(_BYTE *)(v20 + v22) );
      v24 = MultiByteToWideChar_0(0xFDE9u, 0, v21, v22, 0, 0);
      if ( v24 )
      {
        v25 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v24, v23);
        MultiByteToWideChar_0(0xFDE9u, 0, v21, v22, *((LPWSTR *)v25 + 2), v24);
        v19[11] = 0;
        v19[7] = (volatile signed __int32 *)v25;
        winrt::handle_type<winrt::impl::hstring_traits>::~handle_type<winrt::impl::hstring_traits>(v19 + 11);
      }
      else
      {
        v19[7] = 0;
        v25 = 0;
      }
      v19[8] = 0;
      *((_DWORD *)v19 + 18) = -1430532899;
      *((_DWORD *)v19 + 19) = -2147467259;
      v19[10] = 0;
      winrt::hresult_error::originate((__int64)(v19 + 8), 0x80004005, (__int64)v25);
      winrt::hresult_error::to_abi((__int64)(v19 + 8), v19[6]);
      if ( v19[10] )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)v19 + 10);
      v26 = (OLECHAR *)v19[8];
      if ( v26 )
        WINRT_IMPL_SysFreeString(v26);
      winrt::handle_type<winrt::impl::hstring_traits>::~handle_type<winrt::impl::hstring_traits>(v19 + 7);
       = v33;
      __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_180001D69);
LABEL_48:
      ;
    }
  }
LABEL_2:
  *a1 = ((__int64 (__fastcall *)(_QWORD))winrt_to_hresult_handler)(v32[0]);
   = a1;
  goto LABEL_48;
}

```

## disassembly

```asm
0x180001d30  push    rbx
0x180001d32  sub     rsp, 80h
0x180001d39  mov     rbx, rcx
0x180001d3c  mov     [rsp+88h+var_58], rcx
0x180001d41  mov     rax, cs:?winrt_to_hresult_handler@@3P6AHPEAX@_EEA
0x180001d48  test    rax, rax
0x180001d4b  jz      short loc_180001D7D
0x180001d4d  mov     rcx, [rsp+88h]
0x180001d55  call    cs:__guard_dispatch_icall_fptr
0x180001d5b  mov     [rbx], eax
0x180001d5d  mov     rax, rbx
0x180001d60  add     rsp, 80h
0x180001d67  pop     rbx
0x180001d68  retn
0x180001d69  mov     rax, [rsp+arg_28]
0x180001d6e  add     rsp, 80h
0x180001d75  pop     rbx
0x180001d76  retn
0x180001d77  jmp     short loc_180001D69
0x180001d79  jmp     short loc_180001D69
0x180001d7b  jmp     short loc_180001D69
0x180001d7d  xor     edx, edx; pThrowInfo
0x180001d7f  xor     ecx, ecx; pExceptionObject
0x180001d81  call    _CxxThrowException
```
