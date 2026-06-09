# LUAGetUserType

- ea: `0x18004610c`
- end: `0x1800461e1`
- name: `LUAGetUserType`
- size: `213`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002ed98`

## callees

- `0x18001b558`
- `0x18004610c`
- `0x18004622c`

## import_xrefs

- `ntdll!NtClose` at `0x1800461cc`
- `ntdll!NtClose` at `0x1800461cc`
- `ntdll!NtOpenThreadToken` at `0x180046143`
- `ntdll!NtOpenThreadToken` at `0x180046143`
- `ntdll!NtOpenProcessToken` at `0x18004615c`
- `ntdll!NtOpenProcessToken` at `0x18004615c`

## pseudocode

```c
__int64 __fastcall LUAGetUserType(void *a1, int *a2)
{
  void *v2; // rsi
  NTSTATUS v4; // ebx
  int v5; // ecx
  _DWORD v7[4]; // [rsp+20h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+20h] BYREF
  int v9; // [rsp+60h] [rbp+30h] BYREF
  int v10; // [rsp+68h] [rbp+38h] BYREF

  TokenHandle = a1;
  v2 = 0;
  v9 = 0;
  v10 = 0;
  v7[0] = 0;
  if ( a1 )
  {
LABEL_6:
    v4 = LUAIsElevatedToken(a1, &v9, &v10);
    if ( v4 >= 0 )
    {
      *a2 = v9 ? 0 : 2 - (v10 != 0);
      v4 = LUAIsUIAToken(TokenHandle, v7);
      if ( v4 >= 0 )
      {
        if ( v7[0] )
        {
          v5 = *a2;
          if ( (unsigned int)(*a2 - 16) > 2 )
            v5 += 16;
          *a2 = v5;
        }
      }
    }
    if ( v2 )
      NtClose(v2);
    return (unsigned int)v4;
  }
  v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
  if ( v4 == -1073741700 )
    v4 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( v4 >= 0 )
  {
    a1 = TokenHandle;
    v2 = TokenHandle;
    goto LABEL_6;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004610c  mov     [rsp-18h+arg_8], rbx
0x180046111  mov     [rsp-18h+TokenHandle], rcx
0x180046116  push    rbp
0x180046117  push    rsi
0x180046118  push    rdi
0x180046119  mov     rbp, rsp
0x18004611c  sub     rsp, 30h
0x180046120  xor     esi, esi
0x180046122  mov     rdi, rdx
0x180046125  mov     [rbp+arg_10], esi
0x180046128  mov     [rbp+arg_18], esi
0x18004612b  mov     [rbp+var_10], esi
0x18004612e  test    rcx, rcx
0x180046131  jnz     short loc_18004616F
0x180046133  lea     esi, [rcx+8]
0x180046136  xor     r8d, r8d; OpenAsSelf
0x180046139  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004613d  mov     edx, esi; DesiredAccess
0x18004613f  lea     rcx, [r8-2]; ThreadHandle
0x180046143  call    cs:__imp_NtOpenThreadToken
0x180046149  mov     ebx, eax
0x18004614b  cmp     eax, 0C000007Ch
0x180046150  jnz     short loc_180046164
0x180046152  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180046156  mov     edx, esi; DesiredAccess
0x180046158  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004615c  call    cs:__imp_NtOpenProcessToken
0x180046162  mov     ebx, eax
0x180046164  test    ebx, ebx
0x180046166  js      short loc_1800461D2
0x180046168  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004616c  mov     rsi, rcx
0x18004616f  lea     r8, [rbp+arg_18]
0x180046173  lea     rdx, [rbp+arg_10]
0x180046177  call    LUAIsElevatedToken
0x18004617c  mov     ebx, eax
0x18004617e  test    eax, eax
0x180046180  js      short loc_1800461C4
0x180046182  cmp     [rbp+arg_10], 0
0x180046186  jz      short loc_180046190
0x180046188  mov     dword ptr [rdi], 0
0x18004618e  jmp     short loc_18004619C
0x180046190  mov     eax, [rbp+arg_18]
0x180046193  neg     eax
0x180046195  sbb     ecx, ecx
0x180046197  add     ecx, 2
0x18004619a  mov     [rdi], ecx
0x18004619c  mov     rcx, [rbp+TokenHandle]
0x1800461a0  lea     rdx, [rbp+var_10]
0x1800461a4  call    LUAIsUIAToken
0x1800461a9  mov     ebx, eax
0x1800461ab  test    eax, eax
0x1800461ad  js      short loc_1800461C4
0x1800461af  cmp     [rbp+var_10], 0
0x1800461b3  jz      short loc_1800461C4
0x1800461b5  mov     ecx, [rdi]
0x1800461b7  lea     eax, [rcx-10h]
0x1800461ba  cmp     eax, 2
0x1800461bd  jbe     short loc_1800461C2
0x1800461bf  add     ecx, 10h
0x1800461c2  mov     [rdi], ecx
0x1800461c4  test    rsi, rsi
0x1800461c7  jz      short loc_1800461D2
0x1800461c9  mov     rcx, rsi; Handle
0x1800461cc  call    cs:__imp_NtClose
0x1800461d2  mov     eax, ebx
0x1800461d4  mov     rbx, [rsp+30h+arg_8]
0x1800461d9  add     rsp, 30h
0x1800461dd  pop     rdi
0x1800461de  pop     rsi
0x1800461df  pop     rbp
0x1800461e0  retn
```
