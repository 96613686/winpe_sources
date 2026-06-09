# LUAGetUserType

- ea: `0x180043940`
- end: `0x180043a25`
- name: `LUAGetUserType`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002a1d8`

## callees

- `0x18001959c`
- `0x180043940`
- `0x180043a78`

## import_xrefs

- `ntdll!NtClose` at `0x180043a09`
- `ntdll!NtClose` at `0x180043a09`
- `ntdll!NtOpenThreadToken` at `0x180043977`
- `ntdll!NtOpenThreadToken` at `0x180043977`
- `ntdll!NtOpenProcessToken` at `0x180043996`
- `ntdll!NtOpenProcessToken` at `0x180043996`

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
0x180043940  mov     [rsp-18h+arg_8], rbx
0x180043945  mov     [rsp-18h+TokenHandle], rcx
0x18004394a  push    rbp
0x18004394b  push    rsi
0x18004394c  push    rdi
0x18004394d  mov     rbp, rsp
0x180043950  sub     rsp, 30h
0x180043954  xor     esi, esi
0x180043956  mov     rdi, rdx
0x180043959  and     [rbp+arg_10], esi
0x18004395c  and     [rbp+arg_18], esi
0x18004395f  and     [rbp+var_10], esi
0x180043962  test    rcx, rcx
0x180043965  jnz     short loc_1800439AF
0x180043967  lea     esi, [rcx+8]
0x18004396a  xor     r8d, r8d; OpenAsSelf
0x18004396d  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180043971  mov     edx, esi; DesiredAccess
0x180043973  lea     rcx, [r8-2]; ThreadHandle
0x180043977  call    cs:__imp_NtOpenThreadToken
0x18004397e  nop     dword ptr [rax+rax+00h]
0x180043983  mov     ebx, eax
0x180043985  cmp     eax, 0C000007Ch
0x18004398a  jnz     short loc_1800439A4
0x18004398c  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180043990  mov     edx, esi; DesiredAccess
0x180043992  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180043996  call    cs:__imp_NtOpenProcessToken
0x18004399d  nop     dword ptr [rax+rax+00h]
0x1800439a2  mov     ebx, eax
0x1800439a4  test    ebx, ebx
0x1800439a6  js      short loc_180043A15
0x1800439a8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800439ac  mov     rsi, rcx
0x1800439af  lea     r8, [rbp+arg_18]
0x1800439b3  lea     rdx, [rbp+arg_10]
0x1800439b7  call    LUAIsElevatedToken
0x1800439bc  mov     ebx, eax
0x1800439be  test    eax, eax
0x1800439c0  js      short loc_180043A01
0x1800439c2  cmp     [rbp+arg_10], 0
0x1800439c6  jz      short loc_1800439CD
0x1800439c8  and     dword ptr [rdi], 0
0x1800439cb  jmp     short loc_1800439D9
0x1800439cd  mov     eax, [rbp+arg_18]
0x1800439d0  neg     eax
0x1800439d2  sbb     ecx, ecx
0x1800439d4  add     ecx, 2
0x1800439d7  mov     [rdi], ecx
0x1800439d9  mov     rcx, [rbp+TokenHandle]
0x1800439dd  lea     rdx, [rbp+var_10]
0x1800439e1  call    LUAIsUIAToken
0x1800439e6  mov     ebx, eax
0x1800439e8  test    eax, eax
0x1800439ea  js      short loc_180043A01
0x1800439ec  cmp     [rbp+var_10], 0
0x1800439f0  jz      short loc_180043A01
0x1800439f2  mov     ecx, [rdi]
0x1800439f4  lea     eax, [rcx-10h]
0x1800439f7  cmp     eax, 2
0x1800439fa  jbe     short loc_1800439FF
0x1800439fc  add     ecx, 10h
0x1800439ff  mov     [rdi], ecx
0x180043a01  test    rsi, rsi
0x180043a04  jz      short loc_180043A15
0x180043a06  mov     rcx, rsi; Handle
0x180043a09  call    cs:__imp_NtClose
0x180043a10  nop     dword ptr [rax+rax+00h]
0x180043a15  mov     eax, ebx
0x180043a17  mov     rbx, [rsp+30h+arg_8]
0x180043a1c  add     rsp, 30h
0x180043a20  pop     rdi
0x180043a21  pop     rsi
0x180043a22  pop     rbp
0x180043a23  retn
```
