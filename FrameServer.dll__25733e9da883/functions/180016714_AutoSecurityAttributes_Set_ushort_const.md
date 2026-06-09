# AutoSecurityAttributes::Set(ushort const *)

- ea: `0x180016714`
- end: `0x180016787`
- name: `?Set@AutoSecurityAttributes@@QEAAJPEBG@Z`
- size: `115`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *this, LPCWSTR StringSecurityDescriptor)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800148f4`
- `0x18004b280`
- `0x18004c470`

## callees

- `0x180015b40`
- `0x180016714`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016754`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001674a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001674a`

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
0x180016714  mov     [rsp+arg_0], rbx
0x180016719  mov     [rsp+arg_8], rsi
0x18001671e  push    rdi
0x18001671f  sub     rsp, 20h
0x180016723  mov     rbx, rdx
0x180016726  mov     rsi, rcx
0x180016729  xor     edi, edi
0x18001672b  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x180016730  lea     r8, [rsi+10h]; SecurityDescriptor
0x180016734  mov     dword ptr [rsi+8], 18h
0x18001673b  xor     r9d, r9d; SecurityDescriptorSize
0x18001673e  mov     [r8], rdi
0x180016741  lea     edx, [rdi+1]; StringSDRevision
0x180016744  mov     [rsi+18h], edi
0x180016747  mov     rcx, rbx; StringSecurityDescriptor
0x18001674a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180016750  test    eax, eax
0x180016752  jnz     short loc_180016775
0x180016754  call    cs:__imp_GetLastError
0x18001675a  mov     edi, eax
0x18001675c  test    eax, eax
0x18001675e  jle     short loc_180016769
0x180016760  movzx   edi, ax
0x180016763  or      edi, 80070000h
0x180016769  test    edi, edi
0x18001676b  jns     short loc_180016775
0x18001676d  mov     rcx, rsi; this
0x180016770  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x180016775  mov     rbx, [rsp+28h+arg_0]
0x18001677a  mov     eax, edi
0x18001677c  mov     rsi, [rsp+28h+arg_8]
0x180016781  add     rsp, 20h
0x180016785  pop     rdi
0x180016786  retn
```
