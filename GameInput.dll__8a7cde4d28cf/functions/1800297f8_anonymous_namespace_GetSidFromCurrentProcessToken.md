# _anonymous_namespace_::GetSidFromCurrentProcessToken

- ea: `0x1800297f8`
- end: `0x1800298c1`
- name: `_anonymous_namespace_::GetSidFromCurrentProcessToken`
- size: `201`
- prototype: `__int64 __usercall@<rax>(TOKEN_INFORMATION_CLASS TokenInformationClass@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026a4c`

## callees

- `0x1800297f8`
- `0x18002bbd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029853`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002982d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002982d`

## pseudocode

```c
signed int __fastcall anonymous_namespace_::GetSidFromCurrentProcessToken(
        TOKEN_INFORMATION_CLASS TokenInformationClass,
        _QWORD *a2,
        DWORD a3,
        void *a4,
        __int64 a5)
{
  BOOL TokenInformation; // esi
  signed int result; // eax
  unsigned int v8; // ecx
  DWORD v9[6]; // [rsp+30h] [rbp-18h] BYREF

  v9[0] = 0;
  TokenInformation = GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenInformationClass, a4, a3, v9);
  if ( TokenInformation )
  {
    if ( *a2 == a5 )
      return 0;
    if ( *a2 )
    {
      SipcFailFast(2147549183LL);
      JUMPOUT(0x1800298C0LL);
    }
  }
  result = GetLastError();
  if ( result > 0 )
    v8 = (unsigned __int16)result | 0xC0070000;
  else
    v8 = result;
  if ( TokenInformation || v8 == -1073741700 )
  {
    *(_QWORD *)a5 = 257;
    *(_DWORD *)(a5 + 8) = 0;
    return 1;
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800297f8  mov     r11, rsp
0x1800297fb  mov     [r11+8], rbx
0x1800297ff  mov     [r11+10h], rsi
0x180029803  push    rdi
0x180029804  sub     rsp, 40h
0x180029808  mov     rdi, rdx
0x18002980b  mov     [rsp+48h+var_18], 0
0x180029813  lea     rdx, [r11-18h]
0x180029817  mov     rax, r9
0x18002981a  mov     [r11-28h], rdx
0x18002981e  mov     r9d, r8d; TokenInformationLength
0x180029821  mov     edx, ecx; TokenInformationClass
0x180029823  mov     r8, rax; TokenInformation
0x180029826  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x18002982d  call    cs:__imp_GetTokenInformation
0x180029834  nop     dword ptr [rax+rax+00h]
0x180029839  mov     rbx, [rsp+48h+arg_20]
0x18002983e  mov     esi, eax
0x180029840  test    eax, eax
0x180029842  jz      short loc_180029853
0x180029844  cmp     [rdi], rbx
0x180029847  jnz     short loc_18002984D
0x180029849  xor     eax, eax
0x18002984b  jmp     short loc_1800298A5
0x18002984d  cmp     qword ptr [rdi], 0
0x180029851  jnz     short loc_1800298B6
0x180029853  call    cs:__imp_GetLastError
0x18002985a  nop     dword ptr [rax+rax+00h]
0x18002985f  movzx   edx, ax
0x180029862  test    eax, eax
0x180029864  jg      short loc_18002986A
0x180029866  mov     ecx, eax
0x180029868  jmp     short loc_180029872
0x18002986a  mov     ecx, edx
0x18002986c  or      ecx, 0C0070000h
0x180029872  test    esi, esi
0x180029874  jnz     short loc_18002988B
0x180029876  cmp     ecx, 0C000007Ch
0x18002987c  jz      short loc_18002988B
0x18002987e  test    eax, eax
0x180029880  jle     short loc_1800298A5
0x180029882  mov     eax, edx
0x180029884  or      eax, 80070000h
0x180029889  jmp     short loc_1800298A5
0x18002988b  movsd   xmm0, cs:qword_180055548
0x180029893  movsd   qword ptr [rbx], xmm0
0x180029897  mov     eax, cs:dword_180055550
0x18002989d  mov     [rbx+8], eax
0x1800298a0  mov     eax, 1
0x1800298a5  mov     rbx, [rsp+48h+arg_0]
0x1800298aa  mov     rsi, [rsp+48h+arg_8]
0x1800298af  add     rsp, 40h
0x1800298b3  pop     rdi
0x1800298b4  retn
0x1800298b6  mov     ecx, 8000FFFFh
0x1800298bb  call    SipcFailFast
```
