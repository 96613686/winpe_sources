# AutoSecurityAttributes::Set(ushort const *)

- ea: `0x18000c684`
- end: `0x18000c6f7`
- name: `?Set@AutoSecurityAttributes@@QEAAJPEBG@Z`
- size: `115`
- prototype: `__int64 __fastcall(AutoSecurityAttributes *__hidden this, LPCWSTR StringSecurityDescriptor)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007c84`
- `0x180009090`
- `0x18001fb2c`
- `0x180020a0c`
- `0x1800265ac`

## callees

- `0x18000b388`
- `0x18000c684`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6c4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000c6ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000c6ba`

## pseudocode

```c
__int64 __fastcall AutoSecurityAttributes::Set(PSECURITY_DESCRIPTOR *this, LPCWSTR StringSecurityDescriptor)
{
  signed int v4; // edi
  signed int LastError; // eax

  v4 = 0;
  AutoSecurityAttributes::Reset((AutoSecurityAttributes *)this);
  *((_DWORD *)this + 2) = 24;
  this[2] = 0;
  *((_DWORD *)this + 6) = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, this + 2, 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
      AutoSecurityAttributes::Reset((AutoSecurityAttributes *)this);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c684  mov     [rsp+arg_0], rbx
0x18000c689  mov     [rsp+arg_8], rsi
0x18000c68e  push    rdi
0x18000c68f  sub     rsp, 20h
0x18000c693  mov     rbx, rdx
0x18000c696  mov     rsi, rcx
0x18000c699  xor     edi, edi
0x18000c69b  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18000c6a0  lea     r8, [rsi+10h]; SecurityDescriptor
0x18000c6a4  mov     dword ptr [rsi+8], 18h
0x18000c6ab  xor     r9d, r9d; SecurityDescriptorSize
0x18000c6ae  mov     [r8], rdi
0x18000c6b1  lea     edx, [rdi+1]; StringSDRevision
0x18000c6b4  mov     [rsi+18h], edi
0x18000c6b7  mov     rcx, rbx; StringSecurityDescriptor
0x18000c6ba  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000c6c0  test    eax, eax
0x18000c6c2  jnz     short loc_18000C6E5
0x18000c6c4  call    cs:__imp_GetLastError
0x18000c6ca  mov     edi, eax
0x18000c6cc  test    eax, eax
0x18000c6ce  jle     short loc_18000C6D9
0x18000c6d0  movzx   edi, ax
0x18000c6d3  or      edi, 80070000h
0x18000c6d9  test    edi, edi
0x18000c6db  jns     short loc_18000C6E5
0x18000c6dd  mov     rcx, rsi; this
0x18000c6e0  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18000c6e5  mov     rbx, [rsp+28h+arg_0]
0x18000c6ea  mov     eax, edi
0x18000c6ec  mov     rsi, [rsp+28h+arg_8]
0x18000c6f1  add     rsp, 20h
0x18000c6f5  pop     rdi
0x18000c6f6  retn
```
