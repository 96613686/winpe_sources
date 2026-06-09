# CRsopContext::InitializeContext(void *)

- ea: `0x1800298f4`
- end: `0x1800299b7`
- name: `?InitializeContext@CRsopContext@@QEAAXPEAX@Z`
- size: `195`
- prototype: `void __fastcall(CRsopContext *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800114b4`

## callees

- `0x1800297b4`
- `0x1800298f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002996b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002996b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029978`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029978`

## pseudocode

```c
void __fastcall CRsopContext::InitializeContext(CRsopContext *this, void *a2)
{
  bool v2; // zf
  HKEY *phkResult; // rsi
  int RsopNamespaceKeyPath; // ebx
  int *v6; // rax
  LPCWSTR lpSubKey; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 9) == 1;
  lpSubKey = 0;
  if ( !v2 )
  {
    phkResult = (HKEY *)((char *)this + 72);
    if ( !*((_QWORD *)this + 9) )
    {
      RsopNamespaceKeyPath = CRsopContext::GetRsopNamespaceKeyPath(this, a2, (unsigned __int16 **)&lpSubKey);
      if ( RsopNamespaceKeyPath
        || (RsopNamespaceKeyPath = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, phkResult, 0),
            LocalFree((HLOCAL)lpSubKey),
            RsopNamespaceKeyPath) )
      {
        if ( RsopNamespaceKeyPath > 0 )
          RsopNamespaceKeyPath = (unsigned __int16)RsopNamespaceKeyPath | 0x80070000;
        if ( *((_DWORD *)this + 8) )
        {
          v6 = (int *)*((_QWORD *)this + 5);
          if ( v6 )
            *v6 = RsopNamespaceKeyPath;
        }
        *((_DWORD *)this + 8) = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1800298f4  mov     rax, rsp
0x1800298f7  mov     [rax+10h], rbx
0x1800298fb  mov     [rax+18h], rsi
0x1800298ff  push    rdi
0x180029900  sub     rsp, 50h
0x180029904  cmp     dword ptr [rcx+24h], 1
0x180029908  mov     rdi, rcx
0x18002990b  mov     qword ptr [rax+8], 0
0x180029913  jz      loc_1800299A7
0x180029919  lea     rsi, [rcx+48h]
0x18002991d  cmp     qword ptr [rsi], 0
0x180029921  jnz     loc_1800299A7
0x180029927  lea     r8, [rax+8]; unsigned __int16 **
0x18002992b  call    ?GetRsopNamespaceKeyPath@CRsopContext@@QEAAJPEAXPEAPEAG@Z; CRsopContext::GetRsopNamespaceKeyPath(void *,ushort * *)
0x180029930  mov     ebx, eax
0x180029932  test    eax, eax
0x180029934  jnz     short loc_180029982
0x180029936  mov     rdx, [rsp+58h+lpSubKey]; lpSubKey
0x18002993b  xor     r9d, r9d; lpClass
0x18002993e  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180029947  xor     r8d, r8d; Reserved
0x18002994a  mov     [rsp+58h+phkResult], rsi; phkResult
0x18002994f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029956  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002995f  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180029967  mov     [rsp+58h+dwOptions], eax; dwOptions
0x18002996b  call    cs:__imp_RegCreateKeyExW
0x180029971  mov     rcx, [rsp+58h+lpSubKey]; hMem
0x180029976  mov     ebx, eax
0x180029978  call    cs:__imp_LocalFree
0x18002997e  test    ebx, ebx
0x180029980  jz      short loc_1800299A7
0x180029982  test    ebx, ebx
0x180029984  jle     short loc_18002998F
0x180029986  movzx   ebx, bx
0x180029989  or      ebx, 80070000h
0x18002998f  cmp     dword ptr [rdi+20h], 0
0x180029993  jz      short loc_1800299A0
0x180029995  mov     rax, [rdi+28h]
0x180029999  test    rax, rax
0x18002999c  jz      short loc_1800299A0
0x18002999e  mov     [rax], ebx
0x1800299a0  mov     dword ptr [rdi+20h], 0
0x1800299a7  mov     rbx, [rsp+58h+arg_8]
0x1800299ac  mov     rsi, [rsp+58h+arg_10]
0x1800299b1  add     rsp, 50h
0x1800299b5  pop     rdi
0x1800299b6  retn
```
