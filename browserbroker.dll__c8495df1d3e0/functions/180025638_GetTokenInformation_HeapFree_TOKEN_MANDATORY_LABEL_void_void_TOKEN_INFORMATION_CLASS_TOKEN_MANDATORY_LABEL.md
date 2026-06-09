# GetTokenInformation_HeapFree<_TOKEN_MANDATORY_LABEL>(void *,void *,_TOKEN_INFORMATION_CLASS,_TOKEN_MANDATORY_LABEL * *)

- ea: `0x180025638`
- end: `0x1800256fe`
- name: `??$GetTokenInformation_HeapFree@U_TOKEN_MANDATORY_LABEL@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_MANDATORY_LABEL@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(HANDLE hHeap, HANDLE TokenHandle, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025704`

## callees

- `0x18000a2dc`
- `0x180020658`
- `0x180025638`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025677`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002568c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002568c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800256d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800256d4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002566d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800256b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002566d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800256b4`

## pseudocode

```c
__int64 __fastcall GetTokenInformation_HeapFree<_TOKEN_MANDATORY_LABEL>(
        HANDLE hHeap,
        HANDLE TokenHandle,
        __int64 a3,
        _QWORD *a4)
{
  DWORD LastError; // eax
  void *v8; // rdi
  unsigned int ErrorError; // ebx
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v8 = HeapAlloc(hHeap, 0, TokenInformationLength);
      if ( v8 )
      {
        if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v8, TokenInformationLength, &TokenInformationLength) )
        {
          *a4 = v8;
          return 0;
        }
        else
        {
          ErrorError = HRESULTFromLastErrorError();
          HeapFree(hHeap, 0, v8);
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)HRESULTFromWin32ErrorError(LastError);
    }
  }
  return ErrorError;
}

```

## disassembly

```asm
0x180025638  mov     [rsp+TokenInformationLength], r8d
0x18002563d  push    rbx
0x18002563e  push    rbp
0x18002563f  push    rsi
0x180025640  push    rdi
0x180025641  sub     rsp, 38h
0x180025645  mov     rbp, rdx
0x180025648  mov     [rsp+58h+TokenInformationLength], 0
0x180025650  mov     rbx, r9
0x180025653  lea     rax, [rsp+58h+TokenInformationLength]
0x180025658  xor     r9d, r9d; TokenInformationLength
0x18002565b  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180025660  mov     rsi, rcx
0x180025663  xor     r8d, r8d; TokenInformation
0x180025666  mov     rcx, rbp; TokenHandle
0x180025669  lea     edx, [r9+19h]; TokenInformationClass
0x18002566d  call    cs:__imp_GetTokenInformation
0x180025673  test    eax, eax
0x180025675  jnz     short loc_1800256EE
0x180025677  call    cs:__imp_GetLastError
0x18002567d  cmp     eax, 7Ah ; 'z'
0x180025680  jnz     short loc_1800256E3
0x180025682  mov     r8d, [rsp+58h+TokenInformationLength]; dwBytes
0x180025687  xor     edx, edx; dwFlags
0x180025689  mov     rcx, rsi; hHeap
0x18002568c  call    cs:__imp_HeapAlloc
0x180025692  mov     rdi, rax
0x180025695  test    rax, rax
0x180025698  jz      short loc_1800256DC
0x18002569a  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18002569f  lea     rax, [rsp+58h+TokenInformationLength]
0x1800256a4  mov     r8, rdi; TokenInformation
0x1800256a7  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800256ac  mov     edx, 19h; TokenInformationClass
0x1800256b1  mov     rcx, rbp; TokenHandle
0x1800256b4  call    cs:__imp_GetTokenInformation
0x1800256ba  test    eax, eax
0x1800256bc  jz      short loc_1800256C5
0x1800256be  mov     [rbx], rdi
0x1800256c1  xor     ebx, ebx
0x1800256c3  jmp     short loc_1800256F3
0x1800256c5  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x1800256ca  mov     r8, rdi; lpMem
0x1800256cd  xor     edx, edx; dwFlags
0x1800256cf  mov     rcx, rsi; hHeap
0x1800256d2  mov     ebx, eax
0x1800256d4  call    cs:__imp_HeapFree
0x1800256da  jmp     short loc_1800256F3
0x1800256dc  mov     ebx, 8007000Eh
0x1800256e1  jmp     short loc_1800256F3
0x1800256e3  mov     ecx, eax; unsigned int
0x1800256e5  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x1800256ea  mov     ebx, eax
0x1800256ec  jmp     short loc_1800256F3
0x1800256ee  mov     ebx, 8000FFFFh
0x1800256f3  mov     eax, ebx
0x1800256f5  add     rsp, 38h
0x1800256f9  pop     rdi
0x1800256fa  pop     rsi
0x1800256fb  pop     rbp
0x1800256fc  pop     rbx
0x1800256fd  retn
```
