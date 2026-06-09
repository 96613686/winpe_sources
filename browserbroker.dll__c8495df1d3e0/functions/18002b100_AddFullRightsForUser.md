# _AddFullRightsForUser

- ea: `0x18002b100`
- end: `0x18002b221`
- name: `_AddFullRightsForUser`
- size: `289`
- prototype: `__int64 __fastcall(void *Source)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002af4c`

## callees

- `0x180003788`
- `0x1800037ac`
- `0x180020bfc`
- `0x18002b100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b15a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b1da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b15a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b1da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b16b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b16b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b1e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b1e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b1ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b1ff`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b13b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b13b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18002b1b4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18002b1b4`

## pseudocode

```c
__int64 __fastcall AddFullRightsForUser(unsigned __int16 *Source, struct _ACL **a2)
{
  int CurrentUserSid; // eax
  unsigned int v5; // ebx
  PSID v6; // rsi
  DWORD LengthSid; // eax
  DWORD v8; // edx
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  struct _ACL *v11; // rax
  struct _ACL *v12; // rdi
  signed int LastError; // eax
  HANDLE v14; // rax
  PSID pSid; // [rsp+80h] [rbp+18h] BYREF

  pSid = 0;
  CurrentUserSid = GetCurrentUserSid(&pSid);
  v5 = CurrentUserSid;
  if ( CurrentUserSid )
  {
    if ( CurrentUserSid > 0 )
      return (unsigned __int16)CurrentUserSid | 0x80070000;
  }
  else
  {
    v6 = pSid;
    LengthSid = GetLengthSid(pSid);
    v8 = LengthSid + 12;
    if ( LengthSid + 12 < LengthSid || (v9 = v8 + Source[1], v9 < v8) )
    {
      v5 = -2147024362;
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v11 = (struct _ACL *)HeapAlloc(ProcessHeap, 0, v9);
      v12 = v11;
      if ( v11 )
      {
        memset_0(v11, 0, v9);
        memcpy_s(v12, v9, Source, Source[1]);
        v12->AclSize = v9;
        if ( AddAccessAllowedAceEx(v12, 4u, 3u, 0x1F01FFu, v6) )
        {
          *a2 = v12;
          v5 = 0;
        }
        else
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          v14 = GetProcessHeap();
          HeapFree(v14, 0, v12);
        }
      }
      else
      {
        v5 = -2147024882;
      }
    }
    LocalFree(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x18002b100  mov     rax, rsp
0x18002b103  push    rbx
0x18002b104  push    rbp
0x18002b105  push    rsi
0x18002b106  push    rdi
0x18002b107  push    r14
0x18002b109  push    r15
0x18002b10b  sub     rsp, 38h
0x18002b10f  mov     rbp, rcx
0x18002b112  mov     qword ptr [rax+18h], 0
0x18002b11a  lea     rcx, [rax+18h]; void **
0x18002b11e  mov     r14, rdx
0x18002b121  call    ?GetCurrentUserSid@@YAKPEAPEAX@Z; GetCurrentUserSid(void * *)
0x18002b126  mov     ebx, eax
0x18002b128  test    eax, eax
0x18002b12a  jnz     loc_18002B207
0x18002b130  mov     rsi, [rsp+68h+pSid]
0x18002b138  mov     rcx, rsi; pSid
0x18002b13b  call    cs:__imp_GetLengthSid
0x18002b141  lea     edx, [rax+0Ch]
0x18002b144  cmp     edx, eax
0x18002b146  jb      loc_18002B1F7
0x18002b14c  movzx   ebx, word ptr [rbp+2]
0x18002b150  add     ebx, edx
0x18002b152  cmp     ebx, edx
0x18002b154  jb      loc_18002B1F7
0x18002b15a  call    cs:__imp_GetProcessHeap
0x18002b160  mov     r8d, ebx; dwBytes
0x18002b163  xor     edx, edx; dwFlags
0x18002b165  mov     rcx, rax; hHeap
0x18002b168  mov     r15d, ebx
0x18002b16b  call    cs:__imp_HeapAlloc
0x18002b171  mov     rdi, rax
0x18002b174  test    rax, rax
0x18002b177  jz      short loc_18002B1F0
0x18002b179  mov     r8d, r15d; Size
0x18002b17c  xor     edx, edx; Val
0x18002b17e  mov     rcx, rax; void *
0x18002b181  call    memset_0
0x18002b186  movzx   r9d, word ptr [rbp+2]; SourceSize
0x18002b18b  mov     r8, rbp; Source
0x18002b18e  mov     edx, r15d; DestinationSize
0x18002b191  mov     rcx, rdi; Destination
0x18002b194  call    memcpy_s
0x18002b199  mov     edx, 4; dwAceRevision
0x18002b19e  mov     [rdi+2], bx
0x18002b1a2  mov     r9d, 1F01FFh; AccessMask
0x18002b1a8  mov     [rsp+68h+var_48], rsi; pSid
0x18002b1ad  mov     rcx, rdi; pAcl
0x18002b1b0  lea     r8d, [rdx-1]; AceFlags
0x18002b1b4  call    cs:__imp_AddAccessAllowedAceEx
0x18002b1ba  test    eax, eax
0x18002b1bc  jz      short loc_18002B1C5
0x18002b1be  mov     [r14], rdi
0x18002b1c1  xor     ebx, ebx
0x18002b1c3  jmp     short loc_18002B1FC
0x18002b1c5  call    cs:__imp_GetLastError
0x18002b1cb  mov     ebx, eax
0x18002b1cd  test    eax, eax
0x18002b1cf  jle     short loc_18002B1DA
0x18002b1d1  movzx   ebx, ax
0x18002b1d4  or      ebx, 80070000h
0x18002b1da  call    cs:__imp_GetProcessHeap
0x18002b1e0  mov     r8, rdi; lpMem
0x18002b1e3  xor     edx, edx; dwFlags
0x18002b1e5  mov     rcx, rax; hHeap
0x18002b1e8  call    cs:__imp_HeapFree
0x18002b1ee  jmp     short loc_18002B1FC
0x18002b1f0  mov     ebx, 8007000Eh
0x18002b1f5  jmp     short loc_18002B1FC
0x18002b1f7  mov     ebx, 80070216h
0x18002b1fc  mov     rcx, rsi; hMem
0x18002b1ff  call    cs:__imp_LocalFree
0x18002b205  jmp     short loc_18002B212
0x18002b207  jle     short loc_18002B212
0x18002b209  movzx   ebx, ax
0x18002b20c  or      ebx, 80070000h
0x18002b212  mov     eax, ebx
0x18002b214  add     rsp, 38h
0x18002b218  pop     r15
0x18002b21a  pop     r14
0x18002b21c  pop     rdi
0x18002b21d  pop     rsi
0x18002b21e  pop     rbp
0x18002b21f  pop     rbx
0x18002b220  retn
```
