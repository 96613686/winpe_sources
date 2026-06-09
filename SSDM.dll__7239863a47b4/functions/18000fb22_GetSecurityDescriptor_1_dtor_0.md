# _GetSecurityDescriptor_::_1_::dtor$0

- ea: `0x18000fb22`
- end: `0x18000fb48`
- name: `_GetSecurityDescriptor_::_1_::dtor$0`
- size: `38`
- prototype: `HLOCAL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000cfb0`
- `0x18000fb22`

## pseudocode

```c
HLOCAL __fastcall GetSecurityDescriptor_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  HLOCAL result; // rax

  result = (HLOCAL)(*(_DWORD *)(a2 + 32) & 1);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(*(HLOCAL **)(a2 + 80));
  }
  return result;
}

```

## disassembly

```asm
0x18000fb22  push    rbp
0x18000fb24  sub     rsp, 20h
0x18000fb28  mov     rbp, rdx
0x18000fb2b  mov     eax, [rbp+20h]
0x18000fb2e  and     eax, 1
0x18000fb31  test    eax, eax
0x18000fb33  jz      short loc_18000FB42
0x18000fb35  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000fb39  mov     rcx, [rbp+50h]
0x18000fb3d  call    ??1?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x18000fb42  add     rsp, 20h
0x18000fb46  pop     rbp
0x18000fb47  retn
```
