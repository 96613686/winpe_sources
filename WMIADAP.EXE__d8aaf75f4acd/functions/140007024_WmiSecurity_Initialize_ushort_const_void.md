# WmiSecurity::Initialize(ushort const *,void * *)

- ea: `0x140007024`
- end: `0x140007061`
- name: `?Initialize@WmiSecurity@@AEAAJPEBGPEAPEAX@Z`
- size: `61`
- prototype: `__int64 __fastcall(WmiSecurity *this, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000653c`

## callees

- `0x140007024`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140007043`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140007043`

## pseudocode

```c
__int64 __fastcall WmiSecurity::Initialize(WmiSecurity *this, const unsigned __int16 *a2, void **a3)
{
  unsigned int v3; // ebx

  if ( !a3 || *a3 )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    v3 = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(a2, 1u, a3, 0) )
      return (unsigned int)-2147467259;
  }
  return v3;
}

```

## disassembly

```asm
0x140007024  push    rbx
0x140007026  sub     rsp, 20h
0x14000702a  mov     rax, rdx
0x14000702d  test    r8, r8
0x140007030  jz      short loc_140007054
0x140007032  cmp     qword ptr [r8], 0
0x140007036  jnz     short loc_140007054
0x140007038  xor     ebx, ebx
0x14000703a  xor     r9d, r9d; SecurityDescriptorSize
0x14000703d  mov     rcx, rax; StringSecurityDescriptor
0x140007040  lea     edx, [rbx+1]; StringSDRevision
0x140007043  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140007049  test    eax, eax
0x14000704b  jnz     short loc_140007059
0x14000704d  mov     ebx, 80004005h
0x140007052  jmp     short loc_140007059
0x140007054  mov     ebx, 8000FFFFh
0x140007059  mov     eax, ebx
0x14000705b  add     rsp, 20h
0x14000705f  pop     rbx
0x140007060  retn
```
