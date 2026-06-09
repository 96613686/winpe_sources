# BaseSrvFindSharedWow

- ea: `0x18000a640`
- end: `0x18000a75e`
- name: `BaseSrvFindSharedWow`
- size: `286`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000905c`

## callees

- `0x18000a640`
- `0x18000b7d0`
- `0x18000e010`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18000a730`
- `ntdll!RtlCompareUnicodeString` at `0x18000a730`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000a6c3`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000a6c3`
- `CSRSRV!CsrRevertToSelf` at `0x18000a6fd`
- `CSRSRV!CsrRevertToSelf` at `0x18000a6fd`
- `CSRSRV!CsrImpersonateClient` at `0x18000a6d5`
- `CSRSRV!CsrImpersonateClient` at `0x18000a6d5`

## pseudocode

```c
NTSTATUS __fastcall BaseSrvFindSharedWow(__int64 a1, __int64 a2, UNICODE_STRING *a3, __int64 *a4)
{
  NTSTATUS result; // eax
  USHORT v8; // cx
  int v9; // ebx
  __int64 i; // rbx
  struct _STRING SourceString; // [rsp+20h] [rbp-18h] BYREF

  SourceString = 0;
  if ( BaseSrvUserResolveDesktopForWow || (result = BaseSrvImportApis(a1, a2), result >= 0) )
  {
    if ( *(_DWORD *)(a1 + 128) )
    {
      a3->MaximumLength = 520;
      a3->Buffer = (PWSTR)wszDesktopName;
      v8 = *(_WORD *)(a1 + 128);
      SourceString.Buffer = *(PCHAR *)(a1 + 120);
      SourceString.MaximumLength = v8;
      SourceString.Length = v8 - 1;
      result = RtlAnsiStringToUnicodeString(a3, &SourceString, 0);
      if ( result >= 0 )
      {
        if ( (unsigned __int8)CsrImpersonateClient(0) )
        {
          v9 = ((__int64 (__fastcall *)(UNICODE_STRING *))BaseSrvUserResolveDesktopForWow)(a3);
          CsrRevertToSelf();
          if ( v9 >= 0 )
          {
            for ( i = gWowHead; i && RtlCompareUnicodeString((PCUNICODE_STRING)(i + 32), a3, 1u); i = *(_QWORD *)i )
              ;
            *a4 = i;
            return 0;
          }
          else
          {
            a3->Buffer = 0;
            *(_DWORD *)&a3->Length = 0;
            return v9;
          }
        }
        else
        {
          return -1073741659;
        }
      }
    }
    else
    {
      return -1073741811;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a640  mov     [rsp+arg_0], rbx
0x18000a645  mov     [rsp+arg_8], rsi
0x18000a64a  push    rdi
0x18000a64b  sub     rsp, 30h
0x18000a64f  cmp     cs:BaseSrvUserResolveDesktopForWow, 0
0x18000a657  xorps   xmm0, xmm0
0x18000a65a  movups  xmmword ptr [rsp+38h+SourceString.Length], xmm0
0x18000a65f  mov     rsi, r9
0x18000a662  mov     rdi, r8
0x18000a665  mov     rbx, rcx
0x18000a668  jnz     short loc_18000A677
0x18000a66a  call    BaseSrvImportApis
0x18000a66f  test    eax, eax
0x18000a671  js      loc_18000A74D
0x18000a677  cmp     dword ptr [rbx+80h], 0
0x18000a67e  jnz     short loc_18000A68A
0x18000a680  mov     eax, 0C000000Dh
0x18000a685  jmp     loc_18000A74D
0x18000a68a  mov     word ptr [rdi+2], 208h
0x18000a690  lea     rax, wszDesktopName
0x18000a697  mov     [rdi+8], rax
0x18000a69b  lea     rdx, [rsp+38h+SourceString]; SourceString
0x18000a6a0  movzx   ecx, word ptr [rbx+80h]
0x18000a6a7  xor     r8d, r8d; AllocateDestinationString
0x18000a6aa  mov     rax, [rbx+78h]
0x18000a6ae  mov     [rsp+38h+SourceString.Buffer], rax
0x18000a6b3  mov     [rsp+38h+SourceString.MaximumLength], cx
0x18000a6b8  lea     eax, [rcx-1]
0x18000a6bb  mov     rcx, rdi; DestinationString
0x18000a6be  mov     [rsp+38h+SourceString.Length], ax
0x18000a6c3  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18000a6ca  nop     dword ptr [rax+rax+00h]
0x18000a6cf  test    eax, eax
0x18000a6d1  js      short loc_18000A74D
0x18000a6d3  xor     ecx, ecx
0x18000a6d5  call    cs:__imp_CsrImpersonateClient
0x18000a6dc  nop     dword ptr [rax+rax+00h]
0x18000a6e1  test    al, al
0x18000a6e3  jnz     short loc_18000A6EC
0x18000a6e5  mov     eax, 0C00000A5h
0x18000a6ea  jmp     short loc_18000A74D
0x18000a6ec  mov     rax, cs:BaseSrvUserResolveDesktopForWow
0x18000a6f3  mov     rcx, rdi
0x18000a6f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6fb  mov     ebx, eax
0x18000a6fd  call    cs:__imp_CsrRevertToSelf
0x18000a704  nop     dword ptr [rax+rax+00h]
0x18000a709  test    ebx, ebx
0x18000a70b  jns     short loc_18000A71D
0x18000a70d  xor     ecx, ecx
0x18000a70f  mov     qword ptr [rdi+8], 0
0x18000a717  mov     [rdi], ecx
0x18000a719  mov     eax, ebx
0x18000a71b  jmp     short loc_18000A74D
0x18000a71d  mov     rbx, cs:gWowHead
0x18000a724  jmp     short loc_18000A743
0x18000a726  lea     rcx, [rbx+20h]; String1
0x18000a72a  mov     r8b, 1; CaseInsensitive
0x18000a72d  mov     rdx, rdi; String2
0x18000a730  call    cs:__imp_RtlCompareUnicodeString
0x18000a737  nop     dword ptr [rax+rax+00h]
0x18000a73c  test    eax, eax
0x18000a73e  jz      short loc_18000A748
0x18000a740  mov     rbx, [rbx]
0x18000a743  test    rbx, rbx
0x18000a746  jnz     short loc_18000A726
0x18000a748  mov     [rsi], rbx
0x18000a74b  xor     eax, eax
0x18000a74d  mov     rbx, [rsp+38h+arg_0]
0x18000a752  mov     rsi, [rsp+38h+arg_8]
0x18000a757  add     rsp, 30h
0x18000a75b  pop     rdi
0x18000a75c  retn
```
