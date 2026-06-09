# ControlUserService

- ea: `0x180024e88`
- end: `0x180024f66`
- name: `ControlUserService`
- size: `222`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180022d10`
- `0x180022db0`

## callees

- `0x1800134e8`
- `0x180024e88`
- `0x180052906`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024f01`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024f01`
- `USER32!PostMessageW` at `0x180024f51`
- `USER32!PostMessageW` at `0x180024f51`
- `USER32!SendMessageW` at `0x180024f23`
- `USER32!SendMessageW` at `0x180024f23`
- `USER32!FindWindowExW` at `0x180024ed3`
- `USER32!FindWindowExW` at `0x180024f39`
- `USER32!FindWindowExW` at `0x180024ed3`
- `USER32!FindWindowExW` at `0x180024f39`

## pseudocode

```c
__int64 __fastcall ControlUserService(void *a1, int a2)
{
  unsigned int v3; // ebx
  HWND Window; // rax
  HWND v5; // rax
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = a1;
  v3 = -2147467259;
  if ( !memcmp_0(&CLSID_SyncMgrService, &CLSID_SyncMgrService, 0x10u) )
  {
    if ( a2 )
    {
      Window = FindWindowExW(HWND_MESSAGE, 0, L"SyncMgrTrayIconClass", L"SyncMgrTrayIconWindow");
      if ( Window )
      {
        SendMessageW(Window, 0x8001u, 0, 0);
      }
      else
      {
        ppv = 0;
        v3 = CoCreateInstance(&CLSID_SyncMgrp, 0, 0x15u, &GUID_fc2fdb45_bb57_44b2_a88a_4bf09b597e12, &ppv);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
      }
    }
    else
    {
      v5 = FindWindowExW(HWND_MESSAGE, 0, L"SyncCenterStubClass", L"SyncCenterStubWindow");
      if ( v5 )
        PostMessageW(v5, 0x10u, 0, 0);
      return 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180024e88  mov     [rsp+arg_8], rbx
0x180024e8d  mov     [rsp+arg_0], rcx
0x180024e92  push    rdi
0x180024e93  sub     rsp, 30h
0x180024e97  lea     rcx, CLSID_SyncMgrService; Buf1
0x180024e9e  mov     edi, edx
0x180024ea0  mov     rdx, rcx; Buf2
0x180024ea3  mov     r8d, 10h; Size
0x180024ea9  mov     ebx, 80004005h
0x180024eae  call    memcmp_0
0x180024eb3  test    eax, eax
0x180024eb5  jnz     loc_180024F59
0x180024ebb  xor     edx, edx; hWndChildAfter
0x180024ebd  lea     rcx, [rdx-3]; hWndParent
0x180024ec1  test    edi, edi
0x180024ec3  jz      short loc_180024F2B
0x180024ec5  lea     r9, szWindow; "SyncMgrTrayIconWindow"
0x180024ecc  lea     r8, szClass; "SyncMgrTrayIconClass"
0x180024ed3  call    cs:__imp_FindWindowExW
0x180024ed9  test    rax, rax
0x180024edc  jnz     short loc_180024F15
0x180024ede  xor     edx, edx; pUnkOuter
0x180024ee0  mov     [rsp+38h+arg_0], rax
0x180024ee5  lea     rax, [rsp+38h+arg_0]
0x180024eea  lea     r9, _GUID_fc2fdb45_bb57_44b2_a88a_4bf09b597e12; riid
0x180024ef1  mov     [rsp+38h+ppv], rax; ppv
0x180024ef6  lea     rcx, CLSID_SyncMgrp; rclsid
0x180024efd  lea     r8d, [rdx+15h]; dwClsContext
0x180024f01  call    cs:__imp_CoCreateInstance
0x180024f07  lea     rcx, [rsp+38h+arg_0]
0x180024f0c  mov     ebx, eax
0x180024f0e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180024f13  jmp     short loc_180024F59
0x180024f15  xor     r9d, r9d; lParam
0x180024f18  xor     r8d, r8d; wParam
0x180024f1b  mov     edx, 8001h; Msg
0x180024f20  mov     rcx, rax; hWnd
0x180024f23  call    cs:__imp_SendMessageW
0x180024f29  jmp     short loc_180024F59
0x180024f2b  lea     r9, aSynccenterstub; "SyncCenterStubWindow"
0x180024f32  lea     r8, aSynccenterstub_0; "SyncCenterStubClass"
0x180024f39  call    cs:__imp_FindWindowExW
0x180024f3f  test    rax, rax
0x180024f42  jz      short loc_180024F57
0x180024f44  xor     r9d, r9d; lParam
0x180024f47  xor     r8d, r8d; wParam
0x180024f4a  mov     rcx, rax; hWnd
0x180024f4d  lea     edx, [r9+10h]; Msg
0x180024f51  call    cs:__imp_PostMessageW
0x180024f57  xor     ebx, ebx
0x180024f59  mov     eax, ebx
0x180024f5b  mov     rbx, [rsp+38h+arg_8]
0x180024f60  add     rsp, 30h
0x180024f64  pop     rdi
0x180024f65  retn
```
