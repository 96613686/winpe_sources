# BdeSvcIsMediaPresent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18003cd14`
- end: `0x18003cf14`
- name: `?BdeSvcIsMediaPresent@@YAHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180007d90`

## callees

- `0x18001d2a0`
- `0x18002a774`
- `0x18003017c`
- `0x180034070`
- `0x18003cd14`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cece`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cece`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ce1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ce1e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003ce67`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003ceaa`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003ce67`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003ceaa`

## pseudocode

```c
__int64 __fastcall BdeSvcIsMediaPresent(__int64 a1)
{
  unsigned int v2; // ebx
  LPCWSTR *v3; // rax
  __int64 v4; // rdx
  LPCWSTR *v5; // rcx
  const WCHAR *v6; // rcx
  HANDLE FileW; // rdi
  DWORD BytesReturned; // [rsp+48h] [rbp-38h] BYREF
  __int64 OutBuffer; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v12; // [rsp+68h] [rbp-18h]
  unsigned __int64 v13; // [rsp+70h] [rbp-10h]

  v2 = 0;
  BytesReturned = 0;
  std::wstring::wstring(lpFileName, a1);
  OutBuffer = 0;
  if ( v12 )
  {
    v3 = lpFileName;
    if ( v13 > 7 )
      v3 = (LPCWSTR *)lpFileName[0];
    if ( *((_WORD *)v3 + v12 - 1) == 92 )
    {
      v4 = --v12;
      v5 = lpFileName;
      if ( v13 > 7 )
        v5 = (LPCWSTR *)lpFileName[0];
      *((_WORD *)v5 + v4) = 0;
    }
  }
  v6 = (const WCHAR *)lpFileName;
  if ( v13 > 7 )
    v6 = lpFileName[0];
  FileW = CreateFileW(v6, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    v2 = DeviceIoControl(FileW, 0x2D0800u, 0, 0, 0, 0, &BytesReturned, 0);
    if ( v2 )
    {
      v2 = DeviceIoControl(FileW, 0x7405Cu, 0, 0, &OutBuffer, 8u, &BytesReturned, 0);
      if ( v2 )
      {
        if ( BytesReturned < 8 || OutBuffer <= 0 )
          v2 = 0;
      }
    }
    CloseHandle(FileW);
  }
  std::wstring::~wstring((__int64)lpFileName);
  std::wstring::~wstring(a1);
  return v2;
}

```

## disassembly

```asm
0x18003cd14  mov     [rsp-18h+arg_8], rbx
0x18003cd19  mov     [rsp-18h+arg_10], rsi
0x18003cd1e  push    rbp
0x18003cd1f  push    rdi
0x18003cd20  push    r15
0x18003cd22  mov     rbp, rsp
0x18003cd25  sub     rsp, 80h
0x18003cd2c  mov     rax, cs:__security_cookie
0x18003cd33  xor     rax, rsp
0x18003cd36  mov     [rbp+var_8], rax
0x18003cd3a  mov     rsi, rcx
0x18003cd3d  mov     [rbp+var_40], rcx
0x18003cd41  xor     ebx, ebx
0x18003cd43  mov     [rbp+BytesReturned], ebx
0x18003cd46  mov     rdx, rcx
0x18003cd49  lea     rcx, [rbp+lpFileName]
0x18003cd4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003cd52  nop
0x18003cd53  mov     rcx, [rbp+var_18]
0x18003cd57  mov     [rbp+OutBuffer], rbx
0x18003cd5b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003cd5f  test    rcx, rcx
0x18003cd62  jz      loc_18003CDEC
0x18003cd68  mov     r8, [rbp+var_10]
0x18003cd6c  lea     rax, [rbp+lpFileName]
0x18003cd70  cmp     r8, 7
0x18003cd74  cmova   rax, [rbp+lpFileName]
0x18003cd79  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18003cd7f  jnz     short loc_18003CDEC
0x18003cd81  lea     rdx, [rcx-1]
0x18003cd85  cmp     rdx, rcx
0x18003cd88  ja      short loc_18003CDA3
0x18003cd8a  mov     [rbp+var_18], rdx
0x18003cd8e  lea     rcx, [rbp+lpFileName]
0x18003cd92  cmp     r8, 7
0x18003cd96  cmova   rcx, [rbp+lpFileName]
0x18003cd9b  xor     eax, eax
0x18003cd9d  mov     [rcx+rdx*2], ax
0x18003cda1  jmp     short loc_18003CDEC
0x18003cda3  mov     rax, r8
0x18003cda6  sub     rax, rcx
0x18003cda9  cmp     rax, r15
0x18003cdac  jb      short loc_18003CDDD
0x18003cdae  mov     [rbp+var_18], rdx
0x18003cdb2  lea     r9, [rbp+lpFileName]
0x18003cdb6  cmp     r8, 7
0x18003cdba  cmova   r9, [rbp+lpFileName]
0x18003cdbf  lea     r8, [r9+rcx*2]
0x18003cdc3  mov     rcx, r15
0x18003cdc6  xor     eax, eax
0x18003cdc8  mov     [r8], ax
0x18003cdcc  lea     r8, [r8+2]
0x18003cdd0  sub     rcx, 1
0x18003cdd4  jnz     short loc_18003CDC6
0x18003cdd6  mov     [r9+rdx*2], ax
0x18003cddb  jmp     short loc_18003CDEC
0x18003cddd  mov     r9, r15
0x18003cde0  mov     rdx, r15
0x18003cde3  lea     rcx, [rbp+lpFileName]
0x18003cde7  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x18003cdec  lea     rcx, [rbp+lpFileName]
0x18003cdf0  cmp     [rbp+var_10], 7
0x18003cdf5  cmova   rcx, [rbp+lpFileName]; lpFileName
0x18003cdfa  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18003ce03  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003ce0b  mov     r8d, 3; dwShareMode
0x18003ce11  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x18003ce16  xor     r9d, r9d; lpSecurityAttributes
0x18003ce19  mov     edx, 80000000h; dwDesiredAccess
0x18003ce1e  call    cs:__imp_CreateFileW
0x18003ce25  nop     dword ptr [rax+rax+00h]
0x18003ce2a  mov     rdi, rax
0x18003ce2d  cmp     rax, r15
0x18003ce30  jz      loc_18003CEDB
0x18003ce36  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x18003ce3f  lea     rax, [rbp+BytesReturned]
0x18003ce43  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x18003ce48  mov     [rsp+80h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18003ce50  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOutBuffer
0x18003ce59  xor     r9d, r9d; nInBufferSize
0x18003ce5c  xor     r8d, r8d; lpInBuffer
0x18003ce5f  mov     edx, 2D0800h; dwIoControlCode
0x18003ce64  mov     rcx, rdi; hDevice
0x18003ce67  call    cs:__imp_DeviceIoControl
0x18003ce6e  nop     dword ptr [rax+rax+00h]
0x18003ce73  mov     ebx, eax
0x18003ce75  test    eax, eax
0x18003ce77  jz      short loc_18003CECB
0x18003ce79  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x18003ce82  lea     rax, [rbp+BytesReturned]
0x18003ce86  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x18003ce8b  mov     [rsp+80h+dwFlagsAndAttributes], 8; nOutBufferSize
0x18003ce93  lea     rax, [rbp+OutBuffer]
0x18003ce97  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; lpOutBuffer
0x18003ce9c  xor     r9d, r9d; nInBufferSize
0x18003ce9f  xor     r8d, r8d; lpInBuffer
0x18003cea2  mov     edx, 7405Ch; dwIoControlCode
0x18003cea7  mov     rcx, rdi; hDevice
0x18003ceaa  call    cs:__imp_DeviceIoControl
0x18003ceb1  nop     dword ptr [rax+rax+00h]
0x18003ceb6  mov     ebx, eax
0x18003ceb8  test    eax, eax
0x18003ceba  jz      short loc_18003CECB
0x18003cebc  cmp     [rbp+BytesReturned], 8
0x18003cec0  jb      short loc_18003CEC9
0x18003cec2  cmp     [rbp+OutBuffer], 0
0x18003cec7  jg      short loc_18003CECB
0x18003cec9  xor     ebx, ebx
0x18003cecb  mov     rcx, rdi; hObject
0x18003cece  call    cs:__imp_CloseHandle
0x18003ced5  nop     dword ptr [rax+rax+00h]
0x18003ceda  nop
0x18003cedb  lea     rcx, [rbp+lpFileName]
0x18003cedf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cee4  nop
0x18003cee5  mov     rcx, rsi
0x18003cee8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003ceed  mov     eax, ebx
0x18003ceef  mov     rcx, [rbp+var_8]
0x18003cef3  xor     rcx, rsp; StackCookie
0x18003cef6  call    __security_check_cookie
0x18003cefb  lea     r11, [rsp+80h+var_s0]
0x18003cf03  mov     rbx, [r11+28h]
0x18003cf07  mov     rsi, [r11+30h]
0x18003cf0b  mov     rsp, r11
0x18003cf0e  pop     r15
0x18003cf10  pop     rdi
0x18003cf11  pop     rbp
0x18003cf12  retn
```
