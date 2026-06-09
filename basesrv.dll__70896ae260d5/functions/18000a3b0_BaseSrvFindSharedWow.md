# BaseSrvFindSharedWow

- ea: `0x18000a3b0`
- end: `0x18000a4d8`
- name: `BaseSrvFindSharedWow`
- size: `296`
- prototype: `NTSTATUS __fastcall(__int64, __int64, UNICODE_STRING *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008d80`

## callees

- `0x18000a3b0`
- `0x18000b524`
- `0x18000e010`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18000a49d`
- `ntdll!RtlCompareUnicodeString` at `0x18000a49d`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000a433`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000a433`
- `CSRSRV!CsrRevertToSelf` at `0x18000a46d`
- `CSRSRV!CsrRevertToSelf` at `0x18000a46d`
- `CSRSRV!CsrImpersonateClient` at `0x18000a445`
- `CSRSRV!CsrImpersonateClient` at `0x18000a445`

## pseudocode

```c
NTSTATUS __fastcall BaseSrvFindSharedWow(__int64 a1, __int64 a2, UNICODE_STRING *a3, __int64 *a4)
{
  NTSTATUS result; // eax
  USHORT v8; // cx
  int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rbx
  struct _STRING SourceString; // [rsp+20h] [rbp-18h] BYREF

  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  if ( BaseSrvUserResolveDesktopForWow || (result = BaseSrvImportApis(), result >= 0) )
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
          CsrRevertToSelf(v10);
          if ( v9 >= 0 )
          {
            v11 = gWowHead;
            if ( !gWowHead )
              goto LABEL_14;
            do
            {
              if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(v11 + 32), a3, 1u) )
                break;
              v11 = *(_QWORD *)v11;
            }
            while ( v11 );
            if ( !v11 )
LABEL_14:
              v11 = 0;
            *a4 = v11;
            return 0;
          }
          else
          {
            a3->Buffer = 0;
            result = v9;
            *(_DWORD *)&a3->Length = 0;
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
0x18000a3b0  mov     rax, rsp
0x18000a3b3  mov     [rax+8], rbx
0x18000a3b7  mov     [rax+10h], rbp
0x18000a3bb  mov     [rax+18h], rsi
0x18000a3bf  push    rdi
0x18000a3c0  sub     rsp, 30h
0x18000a3c4  xor     ebp, ebp
0x18000a3c6  mov     rsi, r9
0x18000a3c9  cmp     cs:BaseSrvUserResolveDesktopForWow, rbp
0x18000a3d0  mov     rdi, r8
0x18000a3d3  mov     rbx, rcx
0x18000a3d6  mov     [rax-14h], ebp
0x18000a3d9  jnz     short loc_18000A3E8
0x18000a3db  call    BaseSrvImportApis
0x18000a3e0  test    eax, eax
0x18000a3e2  js      loc_18000A4C2
0x18000a3e8  cmp     [rbx+80h], ebp
0x18000a3ee  jnz     short loc_18000A3FA
0x18000a3f0  mov     eax, 0C000000Dh
0x18000a3f5  jmp     loc_18000A4C2
0x18000a3fa  mov     word ptr [rdi+2], 208h
0x18000a400  lea     rax, wszDesktopName
0x18000a407  mov     [rdi+8], rax
0x18000a40b  lea     rdx, [rsp+38h+SourceString]; SourceString
0x18000a410  movzx   ecx, word ptr [rbx+80h]
0x18000a417  xor     r8d, r8d; AllocateDestinationString
0x18000a41a  mov     rax, [rbx+78h]
0x18000a41e  mov     [rsp+38h+SourceString.Buffer], rax
0x18000a423  mov     [rsp+38h+SourceString.MaximumLength], cx
0x18000a428  lea     eax, [rcx-1]
0x18000a42b  mov     rcx, rdi; DestinationString
0x18000a42e  mov     [rsp+38h+SourceString.Length], ax
0x18000a433  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18000a43a  nop     dword ptr [rax+rax+00h]
0x18000a43f  test    eax, eax
0x18000a441  js      short loc_18000A4C2
0x18000a443  xor     ecx, ecx
0x18000a445  call    cs:__imp_CsrImpersonateClient
0x18000a44c  nop     dword ptr [rax+rax+00h]
0x18000a451  test    al, al
0x18000a453  jnz     short loc_18000A45C
0x18000a455  mov     eax, 0C00000A5h
0x18000a45a  jmp     short loc_18000A4C2
0x18000a45c  mov     rax, cs:BaseSrvUserResolveDesktopForWow
0x18000a463  mov     rcx, rdi
0x18000a466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a46b  mov     ebx, eax
0x18000a46d  call    cs:__imp_CsrRevertToSelf
0x18000a474  nop     dword ptr [rax+rax+00h]
0x18000a479  test    ebx, ebx
0x18000a47b  jns     short loc_18000A487
0x18000a47d  mov     [rdi+8], rbp
0x18000a481  mov     eax, ebx
0x18000a483  mov     [rdi], ebp
0x18000a485  jmp     short loc_18000A4C2
0x18000a487  mov     rbx, cs:gWowHead
0x18000a48e  test    rbx, rbx
0x18000a491  jz      short loc_18000A4BA
0x18000a493  lea     rcx, [rbx+20h]; String1
0x18000a497  mov     r8b, 1; CaseInsensitive
0x18000a49a  mov     rdx, rdi; String2
0x18000a49d  call    cs:__imp_RtlCompareUnicodeString
0x18000a4a4  nop     dword ptr [rax+rax+00h]
0x18000a4a9  test    eax, eax
0x18000a4ab  jz      short loc_18000A4B5
0x18000a4ad  mov     rbx, [rbx]
0x18000a4b0  test    rbx, rbx
0x18000a4b3  jnz     short loc_18000A493
0x18000a4b5  test    rbx, rbx
0x18000a4b8  jnz     short loc_18000A4BD
0x18000a4ba  mov     rbx, rbp
0x18000a4bd  mov     [rsi], rbx
0x18000a4c0  xor     eax, eax
0x18000a4c2  mov     rbx, [rsp+38h+arg_0]
0x18000a4c7  mov     rbp, [rsp+38h+arg_8]
0x18000a4cc  mov     rsi, [rsp+38h+arg_10]
0x18000a4d1  add     rsp, 30h
0x18000a4d5  pop     rdi
0x18000a4d6  retn
```
