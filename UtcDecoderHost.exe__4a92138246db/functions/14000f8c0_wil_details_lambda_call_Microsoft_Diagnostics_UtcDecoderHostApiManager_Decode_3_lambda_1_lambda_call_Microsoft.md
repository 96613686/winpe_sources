# wil::details::lambda_call__Microsoft::Diagnostics::UtcDecoderHostApiManager::Decode_::_3_::_lambda_1___::_lambda_call__Microsoft::Diagnostics::UtcDecoderHostApiManager::Decode_::_3_::_lambda_1___

- ea: `0x14000f8c0`
- end: `0x14000f90f`
- name: `wil::details::lambda_call__Microsoft::Diagnostics::UtcDecoderHostApiManager::Decode_::_3_::_lambda_1___::_lambda_call__Microsoft::Diagnostics::UtcDecoderHostApiManager::Decode_::_3_::_lambda_1___`
- size: `79`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400176fa`

## callees

- `0x14000f8c0`
- `0x1400116c0`
- `0x140018010`

## string_xrefs

- `0x14000f8f8`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapimanager.cpp`

## pseudocode

```c
void __fastcall wil::details::lambda_call__Microsoft::Diagnostics::UtcDecoderHostApiManager::Decode_::_3_::_lambda_1___::_lambda_call__Microsoft::Diagnostics::UtcDecoderHostApiManager::Decode_::_3_::_lambda_1___(
        __int64 a1)
{
  int v1; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    if ( **(_QWORD **)a1 )
    {
      v1 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(**(_QWORD **)a1);
      if ( v1 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8F,
          (__int64)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapimanager.cpp",
          (const char *)(unsigned int)v1);
    }
  }
}

```

## disassembly

```asm
0x14000f8c0  sub     rsp, 28h
0x14000f8c4  cmp     byte ptr [rcx+10h], 0
0x14000f8c8  jz      short loc_14000F90A
0x14000f8ca  mov     byte ptr [rcx+10h], 0
0x14000f8ce  mov     rax, [rcx]
0x14000f8d1  mov     r8, [rax]
0x14000f8d4  test    r8, r8
0x14000f8d7  jz      short loc_14000F90A
0x14000f8d9  mov     rax, [rcx+8]
0x14000f8dd  mov     rdx, [rax]
0x14000f8e0  mov     rcx, r8
0x14000f8e3  mov     rax, [rdx+8]
0x14000f8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f8ec  mov     rcx, [rsp+28h]; this
0x14000f8f1  test    eax, eax
0x14000f8f3  jns     short loc_14000F90A
0x14000f8f5  mov     r9d, eax; char *
0x14000f8f8  lea     r8, aOnecoreBaseTel_1; "onecore\\base\\telemetry\\utc\\service"...
0x14000f8ff  mov     edx, 8Fh; void *
0x14000f904  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000f909  nop
0x14000f90a  add     rsp, 28h
0x14000f90e  retn
```
