# GetTokenInformation_HeapFree<_TOKEN_GROUPS>(void *,void *,_TOKEN_INFORMATION_CLASS,_TOKEN_GROUPS * *)

- ea: `0x18000c22c`
- end: `0x18000c32e`
- name: `??$GetTokenInformation_HeapFree@U_TOKEN_GROUPS@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_GROUPS@@@Z`
- size: `258`
- prototype: `__int64 __fastcall(HANDLE hHeap, HANDLE TokenHandle, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010350`

## callees

- `0x18000c22c`
- `0x18000ceb8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000c2ed`
- `KERNEL32!HeapFree` at `0x18000c2ed`
- `KERNEL32!GetLastError` at `0x18000c277`
- `KERNEL32!GetLastError` at `0x18000c277`
- `KERNEL32!HeapAlloc` at `0x18000c28e`
- `KERNEL32!HeapAlloc` at `0x18000c28e`
- `ADVAPI32!GetTokenInformation` at `0x18000c269`
- `ADVAPI32!GetTokenInformation` at `0x18000c2b4`
- `ADVAPI32!GetTokenInformation` at `0x18000c269`
- `ADVAPI32!GetTokenInformation` at `0x18000c2b4`

## pseudocode

```c
__int64 __fastcall GetTokenInformation_HeapFree<_TOKEN_GROUPS>(
        HANDLE hHeap,
        HANDLE TokenHandle,
        __int64 a3,
        _QWORD *a4)
{
  signed int LastError; // eax
  unsigned int LastErrorError; // ebx
  void *v9; // rdi
  SIZE_T dwBytes; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(dwBytes) = 0;
  if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, (PDWORD)&dwBytes) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    LastError = GetLastError();
    LastErrorError = LastError;
    if ( LastError == 122 )
    {
      v9 = HeapAlloc(hHeap, 0, (unsigned int)dwBytes);
      if ( v9 )
      {
        if ( GetTokenInformation(TokenHandle, TokenGroups, v9, dwBytes, (PDWORD)&dwBytes) )
        {
          *a4 = v9;
          return 0;
        }
        else
        {
          if ( (int)GetLastErrorError() > 0 )
            LastErrorError = (unsigned __int16)GetLastErrorError() | 0x80070000;
          else
            LastErrorError = GetLastErrorError();
          HeapFree(hHeap, 0, v9);
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else if ( LastError )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return LastErrorError;
}

```

## disassembly

```asm
0x18000c22c  mov     rax, rsp
0x18000c22f  mov     [rax+8], rbx
0x18000c233  mov     [rax+10h], rbp
0x18000c237  mov     [rax+18h], r8d
0x18000c23b  push    rsi
0x18000c23c  push    rdi
0x18000c23d  push    r14
0x18000c23f  sub     rsp, 30h
0x18000c243  mov     rbp, rdx
0x18000c246  mov     dword ptr [rax+18h], 0
0x18000c24d  mov     r14, r9
0x18000c250  lea     rax, [rax+18h]
0x18000c254  xor     r9d, r9d; TokenInformationLength
0x18000c257  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000c25c  mov     rsi, rcx
0x18000c25f  xor     r8d, r8d; TokenInformation
0x18000c262  mov     rcx, rbp; TokenHandle
0x18000c265  lea     edx, [r9+2]; TokenInformationClass
0x18000c269  call    cs:__imp_GetTokenInformation
0x18000c26f  test    eax, eax
0x18000c271  jnz     loc_18000C314
0x18000c277  call    cs:__imp_GetLastError
0x18000c27d  mov     ebx, eax
0x18000c27f  cmp     eax, 7Ah ; 'z'
0x18000c282  jnz     short loc_18000C2FC
0x18000c284  mov     r8d, dword ptr [rsp+48h+dwBytes]; dwBytes
0x18000c289  xor     edx, edx; dwFlags
0x18000c28b  mov     rcx, rsi; hHeap
0x18000c28e  call    cs:__imp_HeapAlloc
0x18000c294  mov     rdi, rax
0x18000c297  test    rax, rax
0x18000c29a  jz      short loc_18000C2F5
0x18000c29c  mov     r9d, dword ptr [rsp+48h+dwBytes]; TokenInformationLength
0x18000c2a1  lea     rax, [rsp+48h+dwBytes]
0x18000c2a6  mov     r8, rdi; TokenInformation
0x18000c2a9  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000c2ae  lea     edx, [rbx-78h]; TokenInformationClass
0x18000c2b1  mov     rcx, rbp; TokenHandle
0x18000c2b4  call    cs:__imp_GetTokenInformation
0x18000c2ba  test    eax, eax
0x18000c2bc  jz      short loc_18000C2C5
0x18000c2be  mov     [r14], rdi
0x18000c2c1  xor     ebx, ebx
0x18000c2c3  jmp     short loc_18000C319
0x18000c2c5  call    ?GetLastErrorError@@YAKXZ; GetLastErrorError(void)
0x18000c2ca  test    eax, eax
0x18000c2cc  jg      short loc_18000C2D7
0x18000c2ce  call    ?GetLastErrorError@@YAKXZ; GetLastErrorError(void)
0x18000c2d3  mov     ebx, eax
0x18000c2d5  jmp     short loc_18000C2E5
0x18000c2d7  call    ?GetLastErrorError@@YAKXZ; GetLastErrorError(void)
0x18000c2dc  movzx   ebx, ax
0x18000c2df  or      ebx, 80070000h
0x18000c2e5  mov     r8, rdi; lpMem
0x18000c2e8  xor     edx, edx; dwFlags
0x18000c2ea  mov     rcx, rsi; hHeap
0x18000c2ed  call    cs:__imp_HeapFree
0x18000c2f3  jmp     short loc_18000C319
0x18000c2f5  mov     ebx, 8007000Eh
0x18000c2fa  jmp     short loc_18000C319
0x18000c2fc  test    eax, eax
0x18000c2fe  jz      short loc_18000C30D
0x18000c300  jle     short loc_18000C319
0x18000c302  movzx   ebx, ax
0x18000c305  or      ebx, 80070000h
0x18000c30b  jmp     short loc_18000C319
0x18000c30d  mov     ebx, 80070057h
0x18000c312  jmp     short loc_18000C319
0x18000c314  mov     ebx, 8000FFFFh
0x18000c319  mov     rbp, [rsp+48h+arg_8]
0x18000c31e  mov     eax, ebx
0x18000c320  mov     rbx, [rsp+48h+arg_0]
0x18000c325  add     rsp, 30h
0x18000c329  pop     r14
0x18000c32b  pop     rdi
0x18000c32c  pop     rsi
0x18000c32d  retn
```
