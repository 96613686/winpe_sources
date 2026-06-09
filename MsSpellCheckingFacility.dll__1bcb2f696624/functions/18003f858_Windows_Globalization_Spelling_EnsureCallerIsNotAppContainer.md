# Windows::Globalization::Spelling::EnsureCallerIsNotAppContainer

- ea: `0x18003f858`
- end: `0x18003f8a8`
- name: `Windows::Globalization::Spelling::EnsureCallerIsNotAppContainer`
- size: `80`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005cf30`
- `0x18005d6f4`
- `0x18005d8ac`
- `0x1800849f0`

## callees

- `0x18003627c`
- `0x18003f858`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003f895`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003f895`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003f862`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003f862`

## pseudocode

```c
__int64 Windows::Globalization::Spelling::EnsureCallerIsNotAppContainer()
{
  HRESULT v0; // edi
  unsigned int v1; // ebx

  v0 = CoImpersonateClient();
  if ( (int)(v0 + 0x80000000) < 0 || v0 == -2147417833 )
  {
    v1 = Windows::Globalization::Spelling::IsRunningUnderAppContainer(v0 + 0x80000000) != 0 ? 0x80070005 : 0;
    if ( v0 >= 0 )
      CoRevertToSelf();
  }
  else
  {
    return (unsigned int)v0;
  }
  return v1;
}

```

## disassembly

```asm
0x18003f858  mov     [rsp+arg_0], rbx
0x18003f85d  push    rdi
0x18003f85e  sub     rsp, 20h
0x18003f862  call    cs:__imp_CoImpersonateClient
0x18003f868  mov     edi, eax
0x18003f86a  mov     eax, 80000000h
0x18003f86f  lea     ecx, [rdi+rax]
0x18003f872  test    eax, ecx
0x18003f874  jnz     short loc_18003F882
0x18003f876  cmp     edi, 80010117h
0x18003f87c  jz      short loc_18003F882
0x18003f87e  mov     ebx, edi
0x18003f880  jmp     short loc_18003F89B
0x18003f882  call    Windows__Globalization__Spelling__IsRunningUnderAppContainer
0x18003f887  neg     al
0x18003f889  sbb     ebx, ebx
0x18003f88b  and     ebx, 80070005h
0x18003f891  test    edi, edi
0x18003f893  js      short loc_18003F89B
0x18003f895  call    cs:__imp_CoRevertToSelf
0x18003f89b  mov     eax, ebx
0x18003f89d  mov     rbx, [rsp+28h+arg_0]
0x18003f8a2  add     rsp, 20h
0x18003f8a6  pop     rdi
0x18003f8a7  retn
```
