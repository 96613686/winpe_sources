# FGetLogonSID(void *,void * *)

- ea: `0x180157d8c`
- end: `0x180157ed7`
- name: `?FGetLogonSID@@YA_NPEAXPEAPEAX@Z`
- size: `331`
- prototype: `bool __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180158228`

## callees

- `0x180157d8c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180157dc8`
- `KERNEL32!GetLastError` at `0x180157dc8`
- `KERNEL32!HeapFree` at `0x180157e4c`
- `KERNEL32!HeapFree` at `0x180157ecb`
- `KERNEL32!HeapFree` at `0x180157e4c`
- `KERNEL32!HeapFree` at `0x180157ecb`
- `KERNEL32!HeapAlloc` at `0x180157de5`
- `KERNEL32!HeapAlloc` at `0x180157e8e`
- `KERNEL32!HeapAlloc` at `0x180157de5`
- `KERNEL32!HeapAlloc` at `0x180157e8e`
- `KERNEL32!GetProcessHeap` at `0x180157dd7`
- `KERNEL32!GetProcessHeap` at `0x180157e3e`
- `KERNEL32!GetProcessHeap` at `0x180157e80`
- `KERNEL32!GetProcessHeap` at `0x180157ebd`
- `KERNEL32!GetProcessHeap` at `0x180157dd7`
- `KERNEL32!GetProcessHeap` at `0x180157e3e`
- `KERNEL32!GetProcessHeap` at `0x180157e80`
- `KERNEL32!GetProcessHeap` at `0x180157ebd`
- `ADVAPI32!CopySid` at `0x180157eac`
- `ADVAPI32!CopySid` at `0x180157eac`
- `ADVAPI32!GetLengthSid` at `0x180157e74`
- `ADVAPI32!GetLengthSid` at `0x180157e74`
- `ADVAPI32!GetTokenInformation` at `0x180157dbe`
- `ADVAPI32!GetTokenInformation` at `0x180157e0d`
- `ADVAPI32!GetTokenInformation` at `0x180157dbe`
- `ADVAPI32!GetTokenInformation` at `0x180157e0d`

## pseudocode

```c
char __fastcall FGetLogonSID(HANDLE TokenHandle, void **a2)
{
  char v2; // di
  DWORD v4; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v6; // rsi
  unsigned int v7; // ecx
  _DWORD *v8; // rdx
  HANDLE v9; // rax
  __int64 v11; // rbp
  DWORD LengthSid; // ebx
  HANDLE v13; // rax
  void *v14; // rax
  void *v15; // rbx
  HANDLE v16; // rax
  DWORD dwBytes; // [rsp+48h] [rbp+10h] BYREF
  int dwBytes_4; // [rsp+4Ch] [rbp+14h]

  dwBytes_4 = HIDWORD(a2);
  v2 = 0;
  dwBytes = 0;
  if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &dwBytes) || GetLastError() == 122 )
  {
    v4 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v6 = (unsigned int *)HeapAlloc(ProcessHeap, 0, v4);
    if ( v6 )
    {
      if ( GetTokenInformation(TokenHandle, TokenGroups, v6, dwBytes, &dwBytes) )
      {
        v7 = 0;
        if ( !*v6 )
          goto LABEL_9;
        v8 = v6 + 4;
        while ( (*v8 & 0xC0000000) != 0xC0000000 )
        {
          ++v7;
          v8 += 4;
          if ( v7 >= *v6 )
            goto LABEL_9;
        }
        v11 = 2LL * v7;
        LengthSid = GetLengthSid(*(PSID *)&v6[4 * v7 + 2]);
        dwBytes = LengthSid;
        v13 = GetProcessHeap();
        v14 = HeapAlloc(v13, 0, LengthSid);
        vpLogonIdSID = v14;
        if ( !v14 )
          goto LABEL_10;
        if ( CopySid(dwBytes, v14, *(PSID *)&v6[2 * v11 + 2]) )
        {
LABEL_9:
          v2 = 1;
        }
        else
        {
          v15 = vpLogonIdSID;
          v16 = GetProcessHeap();
          HeapFree(v16, 0, v15);
        }
      }
LABEL_10:
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v6);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180157d8c  mov     rax, rsp
0x180157d8f  mov     [rax+8], rbx
0x180157d93  mov     [rax+18h], rbp
0x180157d97  mov     [rax+20h], rsi
0x180157d9b  mov     [rax+10h], rdx
0x180157d9f  push    rdi
0x180157da0  sub     rsp, 30h
0x180157da4  xor     edi, edi
0x180157da6  xor     r9d, r9d; TokenInformationLength
0x180157da9  mov     [rax+10h], edi
0x180157dac  lea     rax, [rax+10h]
0x180157db0  xor     r8d, r8d; TokenInformation
0x180157db3  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180157db8  mov     rbp, rcx
0x180157dbb  lea     edx, [rdi+2]; TokenInformationClass
0x180157dbe  call    cs:__imp_GetTokenInformation
0x180157dc4  test    eax, eax
0x180157dc6  jnz     short loc_180157DD3
0x180157dc8  call    cs:__imp_GetLastError
0x180157dce  cmp     eax, 7Ah ; 'z'
0x180157dd1  jnz     short loc_180157E52
0x180157dd3  mov     ebx, dword ptr [rsp+38h+dwBytes]
0x180157dd7  call    cs:__imp_GetProcessHeap
0x180157ddd  mov     r8d, ebx; dwBytes
0x180157de0  xor     edx, edx; dwFlags
0x180157de2  mov     rcx, rax; hHeap
0x180157de5  call    cs:__imp_HeapAlloc
0x180157deb  mov     rsi, rax
0x180157dee  test    rax, rax
0x180157df1  jz      short loc_180157E52
0x180157df3  mov     r9d, dword ptr [rsp+38h+dwBytes]; TokenInformationLength
0x180157df8  lea     rax, [rsp+38h+dwBytes]
0x180157dfd  mov     r8, rsi; TokenInformation
0x180157e00  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180157e05  mov     edx, 2; TokenInformationClass
0x180157e0a  mov     rcx, rbp; TokenHandle
0x180157e0d  call    cs:__imp_GetTokenInformation
0x180157e13  test    eax, eax
0x180157e15  jz      short loc_180157E3E
0x180157e17  mov     ecx, edi
0x180157e19  cmp     [rsi], edi
0x180157e1b  jbe     short loc_180157E3B
0x180157e1d  lea     rdx, [rsi+10h]
0x180157e21  mov     r8d, 0C0000000h
0x180157e27  mov     eax, [rdx]
0x180157e29  and     eax, r8d
0x180157e2c  cmp     eax, r8d
0x180157e2f  jz      short loc_180157E6A
0x180157e31  inc     ecx
0x180157e33  add     rdx, 10h
0x180157e37  cmp     ecx, [rsi]
0x180157e39  jb      short loc_180157E27
0x180157e3b  mov     dil, 1
0x180157e3e  call    cs:__imp_GetProcessHeap
0x180157e44  mov     r8, rsi; lpMem
0x180157e47  xor     edx, edx; dwFlags
0x180157e49  mov     rcx, rax; hHeap
0x180157e4c  call    cs:__imp_HeapFree
0x180157e52  mov     rbx, [rsp+38h+arg_0]
0x180157e57  mov     al, dil
0x180157e5a  mov     rbp, [rsp+38h+arg_10]
0x180157e5f  mov     rsi, [rsp+38h+arg_18]
0x180157e64  add     rsp, 30h
0x180157e68  pop     rdi
0x180157e69  retn
0x180157e6a  mov     ebp, ecx
0x180157e6c  add     rbp, rbp
0x180157e6f  mov     rcx, [rsi+rbp*8+8]; pSid
0x180157e74  call    cs:__imp_GetLengthSid
0x180157e7a  mov     ebx, eax
0x180157e7c  mov     dword ptr [rsp+38h+dwBytes], ebx
0x180157e80  call    cs:__imp_GetProcessHeap
0x180157e86  mov     r8d, ebx; dwBytes
0x180157e89  xor     edx, edx; dwFlags
0x180157e8b  mov     rcx, rax; hHeap
0x180157e8e  call    cs:__imp_HeapAlloc
0x180157e94  mov     cs:?vpLogonIdSID@@3PEAXEA, rax; void * vpLogonIdSID
0x180157e9b  test    rax, rax
0x180157e9e  jz      short loc_180157E3E
0x180157ea0  mov     r8, [rsi+rbp*8+8]; pSourceSid
0x180157ea5  mov     rdx, rax; pDestinationSid
0x180157ea8  mov     ecx, dword ptr [rsp+38h+dwBytes]; nDestinationSidLength
0x180157eac  call    cs:__imp_CopySid
0x180157eb2  test    eax, eax
0x180157eb4  jnz     short loc_180157E3B
0x180157eb6  mov     rbx, cs:?vpLogonIdSID@@3PEAXEA; void * vpLogonIdSID
0x180157ebd  call    cs:__imp_GetProcessHeap
0x180157ec3  mov     r8, rbx; lpMem
0x180157ec6  xor     edx, edx; dwFlags
0x180157ec8  mov     rcx, rax; hHeap
0x180157ecb  call    cs:__imp_HeapFree
0x180157ed1  jmp     loc_180157E3E
```
