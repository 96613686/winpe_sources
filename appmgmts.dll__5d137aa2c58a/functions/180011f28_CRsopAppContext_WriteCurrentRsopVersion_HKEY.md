# CRsopAppContext::WriteCurrentRsopVersion(HKEY__ *)

- ea: `0x180011f28`
- end: `0x180011fb9`
- name: `?WriteCurrentRsopVersion@CRsopAppContext@@QEAAKPEAUHKEY__@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(CRsopAppContext *this, HKEY)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002310`
- `0x180011fc0`

## callees

- `0x180011f28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011f70`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011f9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011f70`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011f9d`

## pseudocode

```c
__int64 __fastcall CRsopAppContext::WriteCurrentRsopVersion(CRsopAppContext *this, HKEY a2)
{
  int v3; // eax
  HKEY v4; // rcx
  unsigned int v5; // ebx
  unsigned int v6; // eax
  int Data; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_DWORD *)this + 8) || *((_DWORD *)this + 9) == 1 )
    return 0;
  v3 = *((_DWORD *)this + 28);
  v4 = (HKEY)*((_QWORD *)this + 9);
  Data = v3 + 1;
  v5 = RegSetValueExW(v4, L"RsopVersion", 0, 4u, (const BYTE *)&Data, 4u);
  v6 = RegSetValueExW(a2, L"RsopVersion", 0, 4u, (const BYTE *)&Data, 4u);
  if ( !v5 )
    return v6;
  return v5;
}

```

## disassembly

```asm
0x180011f28  mov     [rsp+arg_8], rbx
0x180011f2d  push    rdi
0x180011f2e  sub     rsp, 30h
0x180011f32  cmp     dword ptr [rcx+20h], 0
0x180011f36  mov     rdi, rdx
0x180011f39  jz      short loc_180011FAC
0x180011f3b  cmp     dword ptr [rcx+24h], 1
0x180011f3f  jz      short loc_180011FAC
0x180011f41  mov     eax, [rcx+70h]
0x180011f44  lea     rdx, aRsopversion; "RsopVersion"
0x180011f4b  mov     rcx, [rcx+48h]; hKey
0x180011f4f  inc     eax
0x180011f51  mov     [rsp+38h+Data], eax
0x180011f55  mov     r9d, 4; dwType
0x180011f5b  lea     rax, [rsp+38h+Data]
0x180011f60  mov     [rsp+38h+cbData], 4; cbData
0x180011f68  xor     r8d, r8d; Reserved
0x180011f6b  mov     [rsp+38h+lpData], rax; lpData
0x180011f70  call    cs:__imp_RegSetValueExW
0x180011f76  mov     [rsp+38h+cbData], 4; cbData
0x180011f7e  lea     rdx, aRsopversion; "RsopVersion"
0x180011f85  mov     ebx, eax
0x180011f87  mov     r9d, 4; dwType
0x180011f8d  lea     rax, [rsp+38h+Data]
0x180011f92  xor     r8d, r8d; Reserved
0x180011f95  mov     rcx, rdi; hKey
0x180011f98  mov     [rsp+38h+lpData], rax; lpData
0x180011f9d  call    cs:__imp_RegSetValueExW
0x180011fa3  test    ebx, ebx
0x180011fa5  cmovz   ebx, eax
0x180011fa8  mov     eax, ebx
0x180011faa  jmp     short loc_180011FAE
0x180011fac  xor     eax, eax
0x180011fae  mov     rbx, [rsp+38h+arg_8]
0x180011fb3  add     rsp, 30h
0x180011fb7  pop     rdi
0x180011fb8  retn
```
