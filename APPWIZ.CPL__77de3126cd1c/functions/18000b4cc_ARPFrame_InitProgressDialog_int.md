# ARPFrame::InitProgressDialog(int)

- ea: `0x18000b4cc`
- end: `0x18000b5bc`
- name: `?InitProgressDialog@ARPFrame@@QEAAXH@Z`
- size: `240`
- prototype: `void __fastcall(ARPFrame *__hidden this, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c4a4`

## callees

- `0x18000ab38`
- `0x18000af14`
- `0x18000b4cc`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b54b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b54b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b52a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b52a`

## pseudocode

```c
void __fastcall ARPFrame::InitProgressDialog(LPVOID *this, int a2)
{
  _QWORD *v4; // rdi
  __int64 v5; // rdi
  void (__fastcall *v6)(__int64, HWND, _QWORD, __int64, _QWORD); // rbx
  HWND HostWindow; // rax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  ARPFrame::EndProgressDialog((ARPFrame *)this);
  *((_DWORD *)this + 96) = a2;
  v4 = this + 47;
  *((_DWORD *)this + 97) = 0;
  if ( CoCreateInstance(&CLSID_ProgressDialog, 0, 1u, &GUID_ebbc7c04_315e_11d2_b62f_006097df5bd4, this + 47) >= 0 )
  {
    LoadStringW(g_hinst, 0x62u, Buffer, 260);
    (*(void (__fastcall **)(_QWORD, WCHAR *))(*(_QWORD *)*v4 + 40LL))(*v4, Buffer);
    v5 = *v4;
    v6 = *(void (__fastcall **)(__int64, HWND, _QWORD, __int64, _QWORD))(*(_QWORD *)v5 + 24LL);
    HostWindow = ARPFrame::GetHostWindow((ARPFrame *)this);
    v6(v5, HostWindow, 0, 13, 0);
  }
}

```

## disassembly

```asm
0x18000b4cc  mov     [rsp+arg_8], rbx
0x18000b4d1  mov     [rsp+arg_10], rsi
0x18000b4d6  push    rdi
0x18000b4d7  sub     rsp, 250h
0x18000b4de  mov     rax, cs:__security_cookie
0x18000b4e5  xor     rax, rsp
0x18000b4e8  mov     [rsp+258h+var_18], rax
0x18000b4f0  mov     ebx, edx
0x18000b4f2  mov     rsi, rcx
0x18000b4f5  call    ?EndProgressDialog@ARPFrame@@QEAAXXZ; ARPFrame::EndProgressDialog(void)
0x18000b4fa  xor     edx, edx; pUnkOuter
0x18000b4fc  mov     [rsi+180h], ebx
0x18000b502  lea     rdi, [rsi+178h]
0x18000b509  mov     dword ptr [rsi+184h], 0
0x18000b513  lea     r9, _GUID_ebbc7c04_315e_11d2_b62f_006097df5bd4; riid
0x18000b51a  mov     [rsp+258h+ppv], rdi; ppv
0x18000b51f  lea     rcx, CLSID_ProgressDialog; rclsid
0x18000b526  lea     r8d, [rdx+1]; dwClsContext
0x18000b52a  call    cs:__imp_CoCreateInstance
0x18000b530  test    eax, eax
0x18000b532  js      short loc_18000B597
0x18000b534  mov     rcx, cs:g_hinst; hInstance
0x18000b53b  lea     r8, [rsp+258h+Buffer]; lpBuffer
0x18000b540  mov     r9d, 104h; cchBufferMax
0x18000b546  mov     edx, 62h ; 'b'; uID
0x18000b54b  call    cs:__imp_LoadStringW
0x18000b551  mov     rcx, [rdi]
0x18000b554  lea     rdx, [rsp+258h+Buffer]
0x18000b559  mov     rax, [rcx]
0x18000b55c  mov     rax, [rax+28h]
0x18000b560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b565  mov     rdi, [rdi]
0x18000b568  mov     rcx, rsi; this
0x18000b56b  mov     rax, [rdi]
0x18000b56e  mov     rbx, [rax+18h]
0x18000b572  call    ?GetHostWindow@ARPFrame@@QEAAPEAUHWND__@@XZ; ARPFrame::GetHostWindow(void)
0x18000b577  mov     rdx, rax
0x18000b57a  mov     [rsp+258h+ppv], 0
0x18000b583  mov     rax, rbx
0x18000b586  mov     r9d, 0Dh
0x18000b58c  xor     r8d, r8d
0x18000b58f  mov     rcx, rdi
0x18000b592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b597  mov     rcx, [rsp+258h+var_18]
0x18000b59f  xor     rcx, rsp; StackCookie
0x18000b5a2  call    __security_check_cookie
0x18000b5a7  lea     r11, [rsp+258h+var_8]
0x18000b5af  mov     rbx, [r11+18h]
0x18000b5b3  mov     rsi, [r11+20h]
0x18000b5b7  mov     rsp, r11
0x18000b5ba  pop     rdi
0x18000b5bb  retn
```
