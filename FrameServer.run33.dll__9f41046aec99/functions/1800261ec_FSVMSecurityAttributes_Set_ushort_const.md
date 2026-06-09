# FSVMSecurityAttributes::Set(ushort const *)

- ea: `0x1800261ec`
- end: `0x18002625f`
- name: `?Set@FSVMSecurityAttributes@@QEAAJPEBG@Z`
- size: `115`
- prototype: `__int64 __fastcall(FSVMSecurityAttributes *__hidden this, LPCWSTR StringSecurityDescriptor)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024ad8`
- `0x180024e94`
- `0x1800253ac`

## callees

- `0x180015b40`
- `0x1800261ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002622c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002622c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180026222`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180026222`

## pseudocode

```c
__int64 __fastcall FSVMSecurityAttributes::Set(PSECURITY_DESCRIPTOR *this, LPCWSTR StringSecurityDescriptor)
{
  signed int v4; // edi
  signed int LastError; // eax

  v4 = 0;
  AutoSecurityAttributes::Reset((AutoSecurityAttributes *)this);
  *((_DWORD *)this + 2) = 24;
  *((_DWORD *)this + 6) = 1;
  this[2] = 0;
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
0x1800261ec  mov     [rsp+arg_0], rbx
0x1800261f1  mov     [rsp+arg_8], rsi
0x1800261f6  push    rdi
0x1800261f7  sub     rsp, 20h
0x1800261fb  mov     rbx, rdx
0x1800261fe  mov     rsi, rcx
0x180026201  xor     edi, edi
0x180026203  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x180026208  lea     edx, [rdi+1]; StringSDRevision
0x18002620b  mov     dword ptr [rsi+8], 18h
0x180026212  lea     r8, [rsi+10h]; SecurityDescriptor
0x180026216  mov     [rsi+18h], edx
0x180026219  xor     r9d, r9d; SecurityDescriptorSize
0x18002621c  mov     [r8], rdi
0x18002621f  mov     rcx, rbx; StringSecurityDescriptor
0x180026222  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180026228  test    eax, eax
0x18002622a  jnz     short loc_18002624D
0x18002622c  call    cs:__imp_GetLastError
0x180026232  mov     edi, eax
0x180026234  test    eax, eax
0x180026236  jle     short loc_180026241
0x180026238  movzx   edi, ax
0x18002623b  or      edi, 80070000h
0x180026241  test    edi, edi
0x180026243  jns     short loc_18002624D
0x180026245  mov     rcx, rsi; this
0x180026248  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18002624d  mov     rbx, [rsp+28h+arg_0]
0x180026252  mov     eax, edi
0x180026254  mov     rsi, [rsp+28h+arg_8]
0x180026259  add     rsp, 20h
0x18002625d  pop     rdi
0x18002625e  retn
```
