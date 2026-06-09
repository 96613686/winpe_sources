# CRegUtils::CreateKey(ATL::CRegKey &,ATL::CRegKey &,ushort const *)

- ea: `0x180011670`
- end: `0x18001172c`
- name: `?CreateKey@CRegUtils@@SAJAEAVCRegKey@ATL@@0PEBG@Z`
- size: `188`
- prototype: `static int(struct ATL::CRegKey *, struct ATL::CRegKey *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000936c`
- `0x18000e858`
- `0x18000ea88`
- `0x18000fd38`
- `0x180013ab4`

## callees

- `0x180011670`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800116d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800116d9`

## pseudocode

```c
__int64 __fastcall CRegUtils::CreateKey(HKEY *a1, HKEY *a2, const unsigned __int16 *a3)
{
  LSTATUS v4; // ebx
  HKEY v5; // rcx
  LSTATUS v6; // edx
  DWORD dwDisposition; // [rsp+70h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+20h] BYREF

  if ( !a3 )
    return (unsigned int)-2147024809;
  v5 = *a1;
  dwDisposition = 0;
  phkResult = 0;
  v4 = RegCreateKeyExW(v5, a3, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
  if ( v4 )
    goto LABEL_8;
  v6 = 0;
  if ( *a2 )
    v6 = RegCloseKey(*a2);
  *a2 = phkResult;
  if ( v6 )
  {
    v4 = v6;
LABEL_8:
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180011670  mov     [rsp+arg_0], rbx
0x180011675  push    rdi
0x180011676  sub     rsp, 50h
0x18001167a  mov     rax, r8
0x18001167d  mov     rdi, rdx
0x180011680  test    r8, r8
0x180011683  jnz     short loc_18001168F
0x180011685  mov     ebx, 80070057h
0x18001168a  jmp     loc_18001171E
0x18001168f  mov     rcx, [rcx]; hKey
0x180011692  lea     rdx, [rsp+58h+dwDisposition]
0x180011697  mov     [rsp+58h+lpdwDisposition], rdx; lpdwDisposition
0x18001169c  xor     r9d, r9d; lpClass
0x18001169f  lea     rdx, [rsp+58h+arg_18]
0x1800116a4  mov     [rsp+58h+dwDisposition], 0
0x1800116ac  mov     [rsp+58h+phkResult], rdx; phkResult
0x1800116b1  xor     r8d, r8d; Reserved
0x1800116b4  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800116bd  mov     rdx, rax; lpSubKey
0x1800116c0  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1800116c8  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800116d0  mov     [rsp+58h+arg_18], 0
0x1800116d9  call    cs:__imp_RegCreateKeyExW
0x1800116e0  nop     dword ptr [rax+rax+00h]
0x1800116e5  mov     ebx, eax
0x1800116e7  test    eax, eax
0x1800116e9  jnz     short loc_180011711
0x1800116eb  mov     rcx, [rdi]; hKey
0x1800116ee  xor     edx, edx
0x1800116f0  test    rcx, rcx
0x1800116f3  jz      short loc_180011703
0x1800116f5  call    cs:__imp_RegCloseKey
0x1800116fc  nop     dword ptr [rax+rax+00h]
0x180011701  mov     edx, eax
0x180011703  mov     rax, [rsp+58h+arg_18]
0x180011708  mov     [rdi], rax
0x18001170b  test    edx, edx
0x18001170d  jz      short loc_18001171E
0x18001170f  mov     ebx, edx
0x180011711  test    ebx, ebx
0x180011713  jle     short loc_18001171E
0x180011715  movzx   ebx, bx
0x180011718  or      ebx, 80070000h
0x18001171e  mov     eax, ebx
0x180011720  mov     rbx, [rsp+58h+arg_0]
0x180011725  add     rsp, 50h
0x180011729  pop     rdi
0x18001172a  retn
```
