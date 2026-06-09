# EapQueryStringValue

- ea: `0x18000a9f8`
- end: `0x18000aa6f`
- name: `EapQueryStringValue`
- size: `119`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009d38`
- `0x180009ff0`
- `0x18000a414`

## callees

- `0x18000a528`
- `0x18000a9f8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000aa1b`
- `ntdll!RtlInitUnicodeString` at `0x18000aa1b`

## pseudocode

```c
__int64 __fastcall EapQueryStringValue(
        HANDLE KeyHandle,
        const WCHAR *a2,
        __int64 a3,
        struct _UNICODE_STRING *a4,
        __int64 a5)
{
  int Buffer; // edx
  USHORT v9; // cx

  if ( a4 )
  {
    RtlInitUnicodeString(a4, 0);
    Buffer = EapQueryBuffer(KeyHandle, a2, 1, a5);
    if ( Buffer < 0 )
      return (unsigned int)Buffer;
    if ( *(_DWORD *)(*(_QWORD *)a5 + 12LL) <= 0xFFFFu )
    {
      a4->Buffer = (PWSTR)(*(_QWORD *)a5 + *(unsigned int *)(*(_QWORD *)a5 + 8LL));
      v9 = *(_WORD *)(*(_QWORD *)a5 + 12LL);
      a4->MaximumLength = v9;
      a4->Length = v9;
      return (unsigned int)Buffer;
    }
  }
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x18000a9f8  push    rbx
0x18000a9fa  push    rbp
0x18000a9fb  push    rsi
0x18000a9fc  push    rdi
0x18000a9fd  sub     rsp, 28h
0x18000aa01  mov     rbx, r9
0x18000aa04  mov     rsi, rdx
0x18000aa07  mov     rbp, rcx
0x18000aa0a  test    r9, r9
0x18000aa0d  jnz     short loc_18000AA16
0x18000aa0f  mov     edx, 0C000000Dh
0x18000aa14  jmp     short loc_18000AA64
0x18000aa16  xor     edx, edx; SourceString
0x18000aa18  mov     rcx, rbx; DestinationString
0x18000aa1b  call    cs:__imp_RtlInitUnicodeString
0x18000aa21  mov     rdi, [rsp+48h+arg_20]
0x18000aa26  mov     r8d, 1
0x18000aa2c  mov     r9, rdi
0x18000aa2f  mov     rdx, rsi
0x18000aa32  mov     rcx, rbp; KeyHandle
0x18000aa35  call    EapQueryBuffer
0x18000aa3a  mov     edx, eax
0x18000aa3c  test    eax, eax
0x18000aa3e  js      short loc_18000AA64
0x18000aa40  mov     rcx, [rdi]
0x18000aa43  cmp     dword ptr [rcx+0Ch], 0FFFFh
0x18000aa4a  ja      short loc_18000AA0F
0x18000aa4c  mov     eax, [rcx+8]
0x18000aa4f  add     rax, rcx
0x18000aa52  mov     [rbx+8], rax
0x18000aa56  mov     rax, [rdi]
0x18000aa59  movzx   ecx, word ptr [rax+0Ch]
0x18000aa5d  mov     [rbx+2], cx
0x18000aa61  mov     [rbx], cx
0x18000aa64  mov     eax, edx
0x18000aa66  add     rsp, 28h
0x18000aa6a  pop     rdi
0x18000aa6b  pop     rsi
0x18000aa6c  pop     rbp
0x18000aa6d  pop     rbx
0x18000aa6e  retn
```
