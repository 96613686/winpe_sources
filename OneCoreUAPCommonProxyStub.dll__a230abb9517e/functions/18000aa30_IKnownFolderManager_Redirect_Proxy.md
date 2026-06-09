# IKnownFolderManager_Redirect_Proxy

- ea: `0x18000aa30`
- end: `0x18000aab6`
- name: `IKnownFolderManager_Redirect_Proxy`
- size: `134`
- prototype: `HRESULT __stdcall(IKnownFolderManager *This, const KNOWNFOLDERID *const rfid, HWND hwnd, KF_REDIRECT_FLAGS flags, LPCWSTR pszTargetPath, UINT cFolders, const KNOWNFOLDERID *pExclusion, LPWSTR *ppszError)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000aa30`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000aa88`
- `RPCRT4!NdrClientCall3` at `0x18000aa88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aaa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aaa8`

## pseudocode

```c
HRESULT __stdcall IKnownFolderManager_Redirect_Proxy(
        IKnownFolderManager *This,
        const KNOWNFOLDERID *const rfid,
        HWND hwnd,
        KF_REDIRECT_FLAGS flags,
        LPCWSTR pszTargetPath,
        UINT cFolders,
        const KNOWNFOLDERID *pExclusion,
        LPWSTR *ppszError)
{
  HRESULT Pointer; // ebx
  LPVOID pv[3]; // [rsp+60h] [rbp-18h] BYREF

  pv[0] = 0;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&stru_1801FFB50,
                            0xCu,
                            0,
                            This,
                            rfid,
                            hwnd,
                            flags,
                            pszTargetPath,
                            cFolders,
                            pExclusion,
                            pv).Pointer;
  if ( ppszError )
    *ppszError = (LPWSTR)pv[0];
  else
    CoTaskMemFree(pv[0]);
  return Pointer;
}

```

## disassembly

```asm
0x18000aa30  mov     r11, rsp
0x18000aa33  push    rbx
0x18000aa34  sub     rsp, 70h
0x18000aa38  lea     rax, [r11-18h]
0x18000aa3c  mov     qword ptr [r11-18h], 0
0x18000aa44  mov     [r11-28h], rax
0x18000aa48  mov     rax, [rsp+78h+pExclusion]
0x18000aa50  mov     [r11-30h], rax
0x18000aa54  mov     eax, [rsp+78h+cFolders]
0x18000aa5b  mov     [rsp+78h+var_38], eax
0x18000aa5f  mov     rax, [rsp+78h+pszTargetPath]
0x18000aa67  mov     [r11-40h], rax
0x18000aa6b  mov     [r11-48h], r9d
0x18000aa6f  mov     r9, rcx
0x18000aa72  mov     [r11-50h], r8
0x18000aa76  lea     rcx, stru_1801FFB50; pProxyInfo
0x18000aa7d  xor     r8d, r8d; pReturnValue
0x18000aa80  mov     [r11-58h], rdx
0x18000aa84  lea     edx, [r8+0Ch]; nProcNum
0x18000aa88  call    cs:__imp_NdrClientCall3
0x18000aa8e  mov     rdx, [rsp+78h+ppszError]
0x18000aa96  mov     rbx, rax
0x18000aa99  mov     rcx, [rsp+78h+pv]; pv
0x18000aa9e  test    rdx, rdx
0x18000aaa1  jz      short loc_18000AAA8
0x18000aaa3  mov     [rdx], rcx
0x18000aaa6  jmp     short loc_18000AAAE
0x18000aaa8  call    cs:__imp_CoTaskMemFree
0x18000aaae  mov     eax, ebx
0x18000aab0  add     rsp, 70h
0x18000aab4  pop     rbx
0x18000aab5  retn
```
