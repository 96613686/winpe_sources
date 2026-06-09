# sub_1404FADA8

- ea: `0x1404fada8`
- end: `0x1404faef0`
- name: `sub_1404FADA8`
- size: `328`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1404fb128`

## callees

- `0x1404fada8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1404faeb9`
- `KERNEL32!HeapFree` at `0x1404faed2`
- `KERNEL32!HeapFree` at `0x1404faeb9`
- `KERNEL32!HeapFree` at `0x1404faed2`
- `KERNEL32!HeapAlloc` at `0x1404fae05`
- `KERNEL32!HeapAlloc` at `0x1404fae7c`
- `KERNEL32!HeapAlloc` at `0x1404fae05`
- `KERNEL32!HeapAlloc` at `0x1404fae7c`
- `KERNEL32!GetProcessHeap` at `0x1404fadf7`
- `KERNEL32!GetProcessHeap` at `0x1404fae6e`
- `KERNEL32!GetProcessHeap` at `0x1404faeab`
- `KERNEL32!GetProcessHeap` at `0x1404faec4`
- `KERNEL32!GetProcessHeap` at `0x1404fadf7`
- `KERNEL32!GetProcessHeap` at `0x1404fae6e`
- `KERNEL32!GetProcessHeap` at `0x1404faeab`
- `KERNEL32!GetProcessHeap` at `0x1404faec4`
- `KERNEL32!GetLastError` at `0x1404fade4`
- `KERNEL32!GetLastError` at `0x1404fade4`
- `ADVAPI32!GetTokenInformation` at `0x1404fadda`
- `ADVAPI32!GetTokenInformation` at `0x1404fae31`
- `ADVAPI32!GetTokenInformation` at `0x1404fadda`
- `ADVAPI32!GetTokenInformation` at `0x1404fae31`
- `ADVAPI32!GetLengthSid` at `0x1404fae62`
- `ADVAPI32!GetLengthSid` at `0x1404fae62`
- `ADVAPI32!CopySid` at `0x1404fae9a`
- `ADVAPI32!CopySid` at `0x1404fae9a`

## pseudocode

```c
char __fastcall sub_1404FADA8(HANDLE TokenHandle, __int64 a2)
{
  char v2; // di
  DWORD v4; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v6; // rsi
  unsigned int i; // ecx
  __int64 v8; // rbp
  DWORD LengthSid; // ebx
  HANDLE v10; // rax
  void *v11; // rax
  void *v12; // rbx
  HANDLE v13; // rax
  HANDLE v14; // rax
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
        for ( i = 0; i < *v6; ++i )
        {
          v8 = 2LL * i;
          if ( (v6[4 * i + 4] & 0xC0000000) == 0xC0000000 )
          {
            LengthSid = GetLengthSid(*(PSID *)&v6[4 * i + 2]);
            dwBytes = LengthSid;
            v10 = GetProcessHeap();
            v11 = HeapAlloc(v10, 0, LengthSid);
            lpMem = v11;
            if ( !v11 )
              goto LABEL_13;
            if ( !CopySid(dwBytes, v11, *(PSID *)&v6[2 * v8 + 2]) )
            {
              v12 = lpMem;
              v13 = GetProcessHeap();
              HeapFree(v13, 0, v12);
              goto LABEL_13;
            }
            break;
          }
        }
        v2 = 1;
      }
LABEL_13:
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v6);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1404fada8  mov     rax, rsp
0x1404fadab  mov     [rax+8], rbx
0x1404fadaf  mov     [rax+18h], rbp
0x1404fadb3  mov     [rax+20h], rsi
0x1404fadb7  mov     [rax+10h], rdx
0x1404fadbb  push    rdi
0x1404fadbc  sub     rsp, 30h
0x1404fadc0  xor     edi, edi
0x1404fadc2  xor     r9d, r9d; TokenInformationLength
0x1404fadc5  mov     [rax+10h], edi
0x1404fadc8  lea     rax, [rax+10h]
0x1404fadcc  xor     r8d, r8d; TokenInformation
0x1404fadcf  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1404fadd4  mov     rbp, rcx
0x1404fadd7  lea     edx, [rdi+2]; TokenInformationClass
0x1404fadda  call    cs:GetTokenInformation
0x1404fade0  test    eax, eax
0x1404fade2  jnz     short loc_1404FADF3
0x1404fade4  call    cs:__imp_GetLastError
0x1404fadea  cmp     eax, 7Ah ; 'z'
0x1404faded  jnz     loc_1404FAED8
0x1404fadf3  mov     ebx, dword ptr [rsp+38h+dwBytes]
0x1404fadf7  call    cs:__imp_GetProcessHeap
0x1404fadfd  mov     r8d, ebx; dwBytes
0x1404fae00  xor     edx, edx; dwFlags
0x1404fae02  mov     rcx, rax; hHeap
0x1404fae05  call    cs:__imp_HeapAlloc
0x1404fae0b  mov     rsi, rax
0x1404fae0e  test    rax, rax
0x1404fae11  jz      loc_1404FAED8
0x1404fae17  mov     r9d, dword ptr [rsp+38h+dwBytes]; TokenInformationLength
0x1404fae1c  lea     rax, [rsp+38h+dwBytes]
0x1404fae21  mov     r8, rsi; TokenInformation
0x1404fae24  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1404fae29  mov     edx, 2; TokenInformationClass
0x1404fae2e  mov     rcx, rbp; TokenHandle
0x1404fae31  call    cs:GetTokenInformation
0x1404fae37  test    eax, eax
0x1404fae39  jz      loc_1404FAEC4
0x1404fae3f  mov     ecx, edi
0x1404fae41  mov     edx, 0C0000000h
0x1404fae46  cmp     ecx, [rsi]
0x1404fae48  jnb     short loc_1404FAEC1
0x1404fae4a  mov     ebp, ecx
0x1404fae4c  add     rbp, rbp
0x1404fae4f  mov     eax, [rsi+rbp*8+10h]
0x1404fae53  and     eax, edx
0x1404fae55  cmp     eax, edx
0x1404fae57  jz      short loc_1404FAE5D
0x1404fae59  inc     ecx
0x1404fae5b  jmp     short loc_1404FAE46
0x1404fae5d  mov     rcx, [rsi+rbp*8+8]; pSid
0x1404fae62  call    cs:GetLengthSid
0x1404fae68  mov     ebx, eax
0x1404fae6a  mov     dword ptr [rsp+38h+dwBytes], ebx
0x1404fae6e  call    cs:__imp_GetProcessHeap
0x1404fae74  mov     r8d, ebx; dwBytes
0x1404fae77  xor     edx, edx; dwFlags
0x1404fae79  mov     rcx, rax; hHeap
0x1404fae7c  call    cs:__imp_HeapAlloc
0x1404fae82  mov     cs:lpMem, rax
0x1404fae89  test    rax, rax
0x1404fae8c  jz      short loc_1404FAEC4
0x1404fae8e  mov     r8, [rsi+rbp*8+8]; pSourceSid
0x1404fae93  mov     rdx, rax; pDestinationSid
0x1404fae96  mov     ecx, dword ptr [rsp+38h+dwBytes]; nDestinationSidLength
0x1404fae9a  call    cs:CopySid
0x1404faea0  test    eax, eax
0x1404faea2  jnz     short loc_1404FAEC1
0x1404faea4  mov     rbx, cs:lpMem
0x1404faeab  call    cs:__imp_GetProcessHeap
0x1404faeb1  mov     r8, rbx; lpMem
0x1404faeb4  xor     edx, edx; dwFlags
0x1404faeb6  mov     rcx, rax; hHeap
0x1404faeb9  call    cs:__imp_HeapFree
0x1404faebf  jmp     short loc_1404FAEC4
0x1404faec1  mov     dil, 1
0x1404faec4  call    cs:__imp_GetProcessHeap
0x1404faeca  mov     r8, rsi; lpMem
0x1404faecd  xor     edx, edx; dwFlags
0x1404faecf  mov     rcx, rax; hHeap
0x1404faed2  call    cs:__imp_HeapFree
0x1404faed8  mov     rbx, [rsp+38h+arg_0]
0x1404faedd  mov     al, dil
0x1404faee0  mov     rbp, [rsp+38h+arg_10]
0x1404faee5  mov     rsi, [rsp+38h+arg_18]
0x1404faeea  add     rsp, 30h
0x1404faeee  pop     rdi
0x1404faeef  retn
```
