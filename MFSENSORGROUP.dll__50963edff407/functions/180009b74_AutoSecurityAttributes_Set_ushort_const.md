# AutoSecurityAttributes::Set(ushort const *)

- ea: `0x180009b74`
- end: `0x180009be9`
- name: `?Set@AutoSecurityAttributes@@QEAAJPEBG@Z`
- size: `117`
- prototype: `__int64 __fastcall(AutoSecurityAttributes *__hidden this, LPCWSTR StringSecurityDescriptor)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009ed0`
- `0x18000c6d8`
- `0x18004ba04`
- `0x18004bc70`

## callees

- `0x180009600`
- `0x180009b74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bc6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180009baa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180009baa`

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
0x180009b74  mov     [rsp+arg_0], rbx
0x180009b79  mov     [rsp+arg_8], rsi
0x180009b7e  push    rdi
0x180009b7f  sub     rsp, 20h
0x180009b83  mov     rbx, rdx
0x180009b86  mov     rsi, rcx
0x180009b89  xor     edi, edi
0x180009b8b  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x180009b90  lea     r8, [rsi+10h]; SecurityDescriptor
0x180009b94  mov     dword ptr [rsi+8], 18h
0x180009b9b  xor     r9d, r9d; SecurityDescriptorSize
0x180009b9e  mov     [r8], rdi
0x180009ba1  lea     edx, [rdi+1]; StringSDRevision
0x180009ba4  mov     [rsi+18h], edi
0x180009ba7  mov     rcx, rbx; StringSecurityDescriptor
0x180009baa  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180009bb0  test    eax, eax
0x180009bb2  jz      short loc_180009BC6
0x180009bb4  mov     rbx, [rsp+28h+arg_0]
0x180009bb9  mov     eax, edi
0x180009bbb  mov     rsi, [rsp+28h+arg_8]
0x180009bc0  add     rsp, 20h
0x180009bc4  pop     rdi
0x180009bc5  retn
0x180009bc6  call    cs:__imp_GetLastError
0x180009bcc  mov     edi, eax
0x180009bce  test    eax, eax
0x180009bd0  jle     short loc_180009BDB
0x180009bd2  movzx   edi, ax
0x180009bd5  or      edi, 80070000h
0x180009bdb  test    edi, edi
0x180009bdd  jns     short loc_180009BB4
0x180009bdf  mov     rcx, rsi; this
0x180009be2  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x180009be7  jmp     short loc_180009BB4
```
