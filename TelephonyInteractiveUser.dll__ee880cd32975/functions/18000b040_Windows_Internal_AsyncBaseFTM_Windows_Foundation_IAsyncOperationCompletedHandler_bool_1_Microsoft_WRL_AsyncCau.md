# Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::GetOnComplete

- ea: `0x18000b040`
- end: `0x18000b136`
- name: `Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::GetOnComplete`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011100`

## callees

- `0x180001dc0`
- `0x18000b040`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b08b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b08b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::GetOnComplete(
        __int64 a1,
        _QWORD *a2)
{
  signed __int32 v3; // edx
  unsigned int v5; // edi
  signed __int32 v6; // eax
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  signed __int32 v11[8]; // [rsp+0h] [rbp-38h] BYREF
  signed __int32 v12; // [rsp+20h] [rbp-18h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)(a1 + 56);
  v12 = -2;
  _InterlockedCompareExchange(&v12, v3, -2);
  if ( v12 == 4 )
  {
    v5 = -2147483634;
    RoOriginateError(2147483662LL);
  }
  else
  {
    v6 = *(_DWORD *)(a1 + 136);
    v5 = 0;
    while ( v6 > 0 )
    {
      if ( v6 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 136), v6 + 1, v6) )
      {
        v7 = *(_QWORD *)(a1 + 120);
        *a2 = 0;
        if ( v7 )
        {
          v8 = *(_QWORD *)(a1 + 120);
          if ( v8 )
            v5 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v8 + 24LL))(
                   v8,
                   &GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a);
        }
        else
        {
          v5 = -2147024809;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 136), 0xFFFFFFFF) == 1 )
        {
          _InterlockedOr(v11, 0);
          v9 = *(_QWORD *)(a1 + 120);
          *(_QWORD *)(a1 + 120) = 0;
          if ( v9 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        return v5;
      }
      v6 = *(_DWORD *)(a1 + 136);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000b040  mov     [rsp+arg_10], rbx
0x18000b045  push    rdi
0x18000b046  sub     rsp, 30h
0x18000b04a  mov     rax, cs:__security_cookie
0x18000b051  xor     rax, rsp
0x18000b054  mov     [rsp+38h+var_10], rax
0x18000b059  mov     r8, rdx
0x18000b05c  mov     qword ptr [rdx], 0
0x18000b063  mov     edx, [rcx+38h]
0x18000b066  mov     rbx, rcx
0x18000b069  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x18000b071  mov     eax, [rsp+38h+var_18]
0x18000b075  lock cmpxchg [rsp+38h+var_18], edx
0x18000b07b  cmp     [rsp+38h+var_18], 4
0x18000b080  jnz     short loc_18000B096
0x18000b082  mov     edi, 8000000Eh
0x18000b087  xor     edx, edx
0x18000b089  mov     ecx, edi
0x18000b08b  call    cs:__imp_RoOriginateError
0x18000b091  jmp     loc_18000B11C
0x18000b096  mov     eax, [rcx+88h]
0x18000b09c  xor     edi, edi
0x18000b09e  jmp     short loc_18000B0B3
0x18000b0a0  lea     ecx, [rax+1]
0x18000b0a3  lock cmpxchg [rbx+88h], ecx
0x18000b0ab  jz      short loc_18000B0B9
0x18000b0ad  mov     eax, [rbx+88h]
0x18000b0b3  test    eax, eax
0x18000b0b5  jg      short loc_18000B0A0
0x18000b0b7  jmp     short loc_18000B11C
0x18000b0b9  mov     rax, [rbx+78h]
0x18000b0bd  mov     [r8], rdi
0x18000b0c0  test    rax, rax
0x18000b0c3  jz      short loc_18000B0E5
0x18000b0c5  mov     rcx, [rbx+78h]
0x18000b0c9  test    rcx, rcx
0x18000b0cc  jz      short loc_18000B0EA
0x18000b0ce  mov     rax, [rcx]
0x18000b0d1  lea     rdx, _GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a
0x18000b0d8  mov     rax, [rax+18h]
0x18000b0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0e1  mov     edi, eax
0x18000b0e3  jmp     short loc_18000B0EA
0x18000b0e5  mov     edi, 80070057h
0x18000b0ea  or      eax, 0FFFFFFFFh
0x18000b0ed  lock xadd [rbx+88h], eax
0x18000b0f5  cmp     eax, 1
0x18000b0f8  jnz     short loc_18000B11C
0x18000b0fa  lock or [rsp+38h+var_38], 0
0x18000b0ff  mov     rcx, [rbx+78h]
0x18000b103  mov     qword ptr [rbx+78h], 0
0x18000b10b  test    rcx, rcx
0x18000b10e  jz      short loc_18000B11C
0x18000b110  mov     rdx, [rcx]
0x18000b113  mov     rax, [rdx+10h]
0x18000b117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b11c  mov     eax, edi
0x18000b11e  mov     rcx, [rsp+38h+var_10]
0x18000b123  xor     rcx, rsp; StackCookie
0x18000b126  call    __security_check_cookie
0x18000b12b  mov     rbx, [rsp+38h+arg_10]
0x18000b130  add     rsp, 30h
0x18000b134  pop     rdi
0x18000b135  retn
```
