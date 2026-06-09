# _IsUserTaskPresent(void)

- ea: `0x180035dd8`
- end: `0x180035e9a`
- name: `?_IsUserTaskPresent@@YA_NXZ`
- size: `194`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003598c`
- `0x180035ba8`

## callees

- `0x18000e098`
- `0x180035dd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035e2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035e2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035e88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035e88`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180035e0b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180035e0b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180035e6b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180035e6b`

## string_xrefs

- `0x180035e01`: `%SystemRoot%\system32\DsmUserTask.Exe`

## pseudocode

```c
bool _IsUserTaskPresent(void)
{
  bool v0; // di
  WCHAR *v1; // rbx
  DWORD i; // ebp
  DWORD v3; // esi
  signed int LastError; // eax
  bool v5; // sf
  LPWSTR lpDst; // [rsp+50h] [rbp+8h] BYREF

  lpDst = 0;
  v0 = 0;
  CCoMemString::Clear((CCoMemString *)&lpDst);
  v1 = lpDst;
  for ( i = 0; ; i = v3 )
  {
    v3 = ExpandEnvironmentStringsW(L"%SystemRoot%\\system32\\DsmUserTask.Exe", v1, i);
    if ( !v3 )
      break;
    if ( v3 <= i )
      goto LABEL_10;
    CCoMemString::Clear((CCoMemString *)&lpDst);
    lpDst = (LPWSTR)CoTaskMemAlloc(2LL * v3);
    v1 = lpDst;
    if ( !lpDst )
      goto LABEL_9;
  }
  LastError = GetLastError();
  v5 = LastError < 0;
  if ( LastError > 0 )
    v5 = 1;
  if ( v5 )
  {
LABEL_9:
    CCoMemString::Clear((CCoMemString *)&lpDst);
    v1 = lpDst;
    goto LABEL_11;
  }
LABEL_10:
  v0 = GetFileAttributesW(v1) != -1;
LABEL_11:
  if ( v1 )
    CoTaskMemFree(v1);
  return v0;
}

```

## disassembly

```asm
0x180035dd8  push    rbx
0x180035dda  push    rbp
0x180035ddb  push    rsi
0x180035ddc  push    rdi
0x180035ddd  sub     rsp, 28h
0x180035de1  lea     rcx, [rsp+48h+lpDst]; this
0x180035de6  mov     [rsp+48h+lpDst], 0
0x180035def  xor     dil, dil
0x180035df2  call    ?Clear@CCoMemString@@QEAAXXZ; CCoMemString::Clear(void)
0x180035df7  mov     rbx, [rsp+48h+lpDst]
0x180035dfc  xor     ebp, ebp
0x180035dfe  mov     r8d, ebp; nSize
0x180035e01  lea     rcx, Src; "%SystemRoot%\\system32\\DsmUserTask.Exe"
0x180035e08  mov     rdx, rbx; lpDst
0x180035e0b  call    cs:__imp_ExpandEnvironmentStringsW
0x180035e11  mov     esi, eax
0x180035e13  test    eax, eax
0x180035e15  jz      short loc_180035E41
0x180035e17  cmp     esi, ebp
0x180035e19  jbe     short loc_180035E68
0x180035e1b  lea     rcx, [rsp+48h+lpDst]; this
0x180035e20  call    ?Clear@CCoMemString@@QEAAXXZ; CCoMemString::Clear(void)
0x180035e25  mov     ecx, esi
0x180035e27  add     rcx, rcx; cb
0x180035e2a  call    cs:__imp_CoTaskMemAlloc
0x180035e30  mov     [rsp+48h+lpDst], rax
0x180035e35  mov     rbx, rax
0x180035e38  test    rax, rax
0x180035e3b  jz      short loc_180035E57
0x180035e3d  mov     ebp, esi
0x180035e3f  jmp     short loc_180035DFE
0x180035e41  call    cs:__imp_GetLastError
0x180035e47  test    eax, eax
0x180035e49  jle     short loc_180035E55
0x180035e4b  movzx   eax, ax
0x180035e4e  or      eax, 80070000h
0x180035e53  test    eax, eax
0x180035e55  jns     short loc_180035E68
0x180035e57  lea     rcx, [rsp+48h+lpDst]; this
0x180035e5c  call    ?Clear@CCoMemString@@QEAAXXZ; CCoMemString::Clear(void)
0x180035e61  mov     rbx, [rsp+48h+lpDst]
0x180035e66  jmp     short loc_180035E80
0x180035e68  mov     rcx, rbx; lpFileName
0x180035e6b  call    cs:__imp_GetFileAttributesW
0x180035e71  movzx   edi, dil
0x180035e75  mov     ecx, 1
0x180035e7a  cmp     eax, 0FFFFFFFFh
0x180035e7d  cmovnz  edi, ecx
0x180035e80  test    rbx, rbx
0x180035e83  jz      short loc_180035E8E
0x180035e85  mov     rcx, rbx; pv
0x180035e88  call    cs:__imp_CoTaskMemFree
0x180035e8e  mov     al, dil
0x180035e91  add     rsp, 28h
0x180035e95  pop     rdi
0x180035e96  pop     rsi
0x180035e97  pop     rbp
0x180035e98  pop     rbx
0x180035e99  retn
```
