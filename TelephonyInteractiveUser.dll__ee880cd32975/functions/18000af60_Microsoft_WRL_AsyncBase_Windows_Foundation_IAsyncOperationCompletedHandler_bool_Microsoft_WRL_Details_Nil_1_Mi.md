# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetOnComplete(Windows::Foundation::IAsyncOperationCompletedHandler<bool> * *)

- ea: `0x18000af60`
- end: `0x18000b032`
- name: `?GetOnComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJPEAPEAU?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@Z`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000af60`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000afb2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000afb2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetOnComplete(
        __int64 a1,
        _QWORD *a2)
{
  signed __int32 v3; // r8d
  unsigned int v5; // edi
  __int64 result; // rax
  int v7; // ett
  __int64 v8; // rcx
  __int64 v9; // rcx
  signed __int32 v10; // [rsp+20h] [rbp-18h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)(a1 + 56);
  v10 = -2;
  _InterlockedCompareExchange(&v10, v3, -2);
  if ( v10 == 4 )
  {
    v5 = -2147483634;
    RoOriginateError(2147483662LL);
    return v5;
  }
  else
  {
    result = *(unsigned int *)(a1 + 32);
    while ( (_DWORD)result )
    {
      v7 = result;
      result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 32), result + 1, result);
      if ( v7 == (_DWORD)result )
      {
        v8 = *(_QWORD *)(a1 + 24);
        v5 = 0;
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
        *a2 = *(_QWORD *)(a1 + 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 32), 0xFFFFFFFF) == 1 )
        {
          v9 = *(_QWORD *)(a1 + 24);
          if ( v9 )
          {
            *(_QWORD *)(a1 + 24) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          }
        }
        return v5;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000af60  mov     [rsp+arg_10], rbx
0x18000af65  mov     [rsp+arg_18], rsi
0x18000af6a  push    rdi
0x18000af6b  sub     rsp, 30h
0x18000af6f  mov     rax, cs:__security_cookie
0x18000af76  xor     rax, rsp
0x18000af79  mov     [rsp+38h+var_10], rax
0x18000af7e  mov     qword ptr [rdx], 0
0x18000af85  mov     rsi, rdx
0x18000af88  mov     r8d, [rcx+38h]
0x18000af8c  mov     rbx, rcx
0x18000af8f  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x18000af97  mov     eax, [rsp+38h+var_18]
0x18000af9b  lock cmpxchg [rsp+38h+var_18], r8d
0x18000afa2  cmp     [rsp+38h+var_18], 4
0x18000afa7  jnz     short loc_18000AFBA
0x18000afa9  mov     edi, 8000000Eh
0x18000afae  xor     edx, edx
0x18000afb0  mov     ecx, edi
0x18000afb2  call    cs:__imp_RoOriginateError
0x18000afb8  jmp     short loc_18000B02E
0x18000afba  mov     eax, [rcx+20h]
0x18000afbd  jmp     short loc_18000AFC9
0x18000afbf  lea     ecx, [rax+1]
0x18000afc2  lock cmpxchg [rbx+20h], ecx
0x18000afc7  jz      short loc_18000AFEA
0x18000afc9  test    eax, eax
0x18000afcb  jnz     short loc_18000AFBF
0x18000afcd  mov     rcx, [rsp+38h+var_10]
0x18000afd2  xor     rcx, rsp; StackCookie
0x18000afd5  call    __security_check_cookie
0x18000afda  mov     rbx, [rsp+38h+arg_10]
0x18000afdf  mov     rsi, [rsp+38h+arg_18]
0x18000afe4  add     rsp, 30h
0x18000afe8  pop     rdi
0x18000afe9  retn
0x18000afea  mov     rcx, [rbx+18h]
0x18000afee  xor     edi, edi
0x18000aff0  test    rcx, rcx
0x18000aff3  jz      short loc_18000B001
0x18000aff5  mov     rax, [rcx]
0x18000aff8  mov     rax, [rax+8]
0x18000affc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b001  mov     rax, [rbx+18h]
0x18000b005  mov     [rsi], rax
0x18000b008  or      eax, 0FFFFFFFFh
0x18000b00b  lock xadd [rbx+20h], eax
0x18000b010  cmp     eax, 1
0x18000b013  jnz     short loc_18000B02E
0x18000b015  mov     rcx, [rbx+18h]
0x18000b019  test    rcx, rcx
0x18000b01c  jz      short loc_18000B02E
0x18000b01e  mov     [rbx+18h], rdi
0x18000b022  mov     rdx, [rcx]
0x18000b025  mov     rax, [rdx+10h]
0x18000b029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b02e  mov     eax, edi
0x18000b030  jmp     short loc_18000AFCD
```
