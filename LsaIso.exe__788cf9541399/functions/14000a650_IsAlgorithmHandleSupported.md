# IsAlgorithmHandleSupported

- ea: `0x14000a650`
- end: `0x14000a7e7`
- name: `IsAlgorithmHandleSupported`
- size: `407`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x140002390`
- `0x140002620`
- `0x140008538`
- `0x14000f300`
- `0x14000fe40`
- `0x1400100d0`
- `0x140011730`

## callees

- `0x14000a650`
- `0x14000a7f0`
- `0x14000a970`
- `0x140011964`
- `0x140011e6c`
- `0x140038cde`
- `0x140038d10`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x14000a6a6`
- `bcrypt!BCryptGetProperty` at `0x14000a6a6`

## pseudocode

```c
__int64 __fastcall IsAlgorithmHandleSupported(__int64 a1, int a2, int a3)
{
  NTSTATUS Property; // ebx
  __int64 v7; // r8
  ULONG pcbResult[4]; // [rsp+30h] [rbp-448h] BYREF
  wchar_t pbOutput[512]; // [rsp+40h] [rbp-438h] BYREF

  pcbResult[0] = 0;
  Property = BCryptGetProperty(*(BCRYPT_HANDLE *)(a1 + 8), L"AlgorithmName", (PUCHAR)pbOutput, 0x400u, pcbResult, 0);
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x5Cu, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, Property);
    return (unsigned int)Property;
  }
  if ( (unsigned int)IsKeyGuardSupportedAlgorithmName(pbOutput) )
  {
    if ( !a3 )
    {
      if ( !wcscmp_0(pbOutput, L"RSA") || !wcscmp_0(pbOutput, L"RSA_SIGN") )
      {
        if ( !a2 || (a2 & 0xFFFFFFF1) != 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              0x5Eu,
              &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids,
              Property);
          return (unsigned int)-1073741637;
        }
      }
      else if ( !wcscmp_0(pbOutput, L"AES") )
      {
        return (unsigned int)IsChainModeSupported(a1);
      }
    }
    return (unsigned int)Property;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, v7, pbOutput);
  return 3221225659LL;
}

```

## disassembly

```asm
0x14000a650  push    rbx
0x14000a652  push    rbp
0x14000a653  push    rsi
0x14000a654  push    rdi
0x14000a655  sub     rsp, 458h
0x14000a65c  mov     rax, cs:__security_cookie
0x14000a663  xor     rax, rsp
0x14000a666  mov     [rsp+478h+var_38], rax
0x14000a66e  mov     ebp, r8d
0x14000a671  mov     [rsp+478h+dwFlags], 0; dwFlags
0x14000a679  mov     edi, edx
0x14000a67b  mov     [rsp+478h+var_448], 0
0x14000a683  mov     rsi, rcx
0x14000a686  lea     rax, [rsp+478h+var_448]
0x14000a68b  mov     rcx, [rcx+8]; hObject
0x14000a68f  lea     r8, [rsp+478h+pbOutput]; pbOutput
0x14000a694  lea     rdx, pszProperty; "AlgorithmName"
0x14000a69b  mov     [rsp+478h+pcbResult], rax; pcbResult
0x14000a6a0  mov     r9d, 400h; cbOutput
0x14000a6a6  call    cs:__imp_BCryptGetProperty
0x14000a6ac  mov     ebx, eax
0x14000a6ae  test    eax, eax
0x14000a6b0  jns     short loc_14000A6F0
0x14000a6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a6b9  lea     rax, WPP_GLOBAL_Control
0x14000a6c0  cmp     rcx, rax
0x14000a6c3  jz      loc_14000A7C9
0x14000a6c9  test    byte ptr [rcx+1Ch], 1
0x14000a6cd  jz      loc_14000A7C9
0x14000a6d3  mov     rcx, [rcx+10h]
0x14000a6d7  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000a6de  mov     edx, 5Ch ; '\'
0x14000a6e3  mov     r9d, ebx
0x14000a6e6  call    WPP_SF_d
0x14000a6eb  jmp     loc_14000A7C9
0x14000a6f0  lea     rcx, [rsp+478h+pbOutput]; unsigned __int16 *
0x14000a6f5  call    ?IsKeyGuardSupportedAlgorithmName@@YAHPEBG@Z; IsKeyGuardSupportedAlgorithmName(ushort const *)
0x14000a6fa  test    eax, eax
0x14000a6fc  jnz     short loc_14000A734
0x14000a6fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a705  lea     rax, WPP_GLOBAL_Control
0x14000a70c  cmp     rcx, rax
0x14000a70f  jz      short loc_14000A72A
0x14000a711  test    byte ptr [rcx+1Ch], 4
0x14000a715  jz      short loc_14000A72A
0x14000a717  mov     rcx, [rcx+10h]
0x14000a71b  lea     r9, [rsp+478h+pbOutput]
0x14000a720  mov     edx, 5Dh ; ']'
0x14000a725  call    WPP_SF_S
0x14000a72a  mov     eax, 0C00000BBh
0x14000a72f  jmp     loc_14000A7CB
0x14000a734  test    ebp, ebp
0x14000a736  jnz     loc_14000A7C9
0x14000a73c  lea     rdx, aRsa; "RSA"
0x14000a743  lea     rcx, [rsp+478h+pbOutput]; String1
0x14000a748  call    wcscmp_0
0x14000a74d  test    eax, eax
0x14000a74f  jz      short loc_14000A787
0x14000a751  lea     rdx, aRsaSign; "RSA_SIGN"
0x14000a758  lea     rcx, [rsp+478h+pbOutput]; String1
0x14000a75d  call    wcscmp_0
0x14000a762  test    eax, eax
0x14000a764  jz      short loc_14000A787
0x14000a766  lea     rdx, aAes; "AES"
0x14000a76d  lea     rcx, [rsp+478h+pbOutput]; String1
0x14000a772  call    wcscmp_0
0x14000a777  test    eax, eax
0x14000a779  jnz     short loc_14000A7C9
0x14000a77b  mov     rcx, rsi
0x14000a77e  call    IsChainModeSupported
0x14000a783  mov     ebx, eax
0x14000a785  jmp     short loc_14000A7C9
0x14000a787  test    edi, edi
0x14000a789  jz      short loc_14000A793
0x14000a78b  test    edi, 0FFFFFFF1h
0x14000a791  jz      short loc_14000A7C9
0x14000a793  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a79a  lea     rax, WPP_GLOBAL_Control
0x14000a7a1  cmp     rcx, rax
0x14000a7a4  jz      short loc_14000A7C4
0x14000a7a6  test    byte ptr [rcx+1Ch], 1
0x14000a7aa  jz      short loc_14000A7C4
0x14000a7ac  mov     rcx, [rcx+10h]
0x14000a7b0  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000a7b7  mov     edx, 5Eh ; '^'
0x14000a7bc  mov     r9d, ebx
0x14000a7bf  call    WPP_SF_d
0x14000a7c4  mov     ebx, 0C00000BBh
0x14000a7c9  mov     eax, ebx
0x14000a7cb  mov     rcx, [rsp+478h+var_38]
0x14000a7d3  xor     rcx, rsp; StackCookie
0x14000a7d6  call    __security_check_cookie
0x14000a7db  add     rsp, 458h
0x14000a7e2  pop     rdi
0x14000a7e3  pop     rsi
0x14000a7e4  pop     rbp
0x14000a7e5  pop     rbx
0x14000a7e6  retn
```
