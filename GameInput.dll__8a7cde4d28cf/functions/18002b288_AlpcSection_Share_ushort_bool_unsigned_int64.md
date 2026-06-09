# AlpcSection::Share(ushort,bool,unsigned __int64 *)

- ea: `0x18002b288`
- end: `0x18002b525`
- name: `?Share@AlpcSection@@QEAAJG_NPEA_K@Z`
- size: `669`
- prototype: `__int64 __fastcall(AlpcSection *__hidden this, unsigned __int16, bool, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18002b580`

## callees

- `0x18002b108`
- `0x18002b288`
- `0x18004c8e0`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x18002b498`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18002b498`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b31b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b31b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b3c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b4cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b4f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b3c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b4cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b39f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b3d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b39f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b3d2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002b38f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002b38f`

## pseudocode

```c
__int64 __fastcall AlpcSection::Share(AlpcSection *this, __int16 a2, char a3, unsigned __int64 *a4)
{
  __int64 FileW; // rbx
  signed int v10; // eax
  unsigned int v11; // edi
  signed int LastError; // eax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // esi
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int64 InBuffer; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v20; // [rsp+58h] [rbp-A8h]
  char v21; // [rsp+5Ah] [rbp-A6h]
  BOOL v22; // [rsp+5Bh] [rbp-A5h]
  char v23; // [rsp+5Fh] [rbp-A1h]
  _OWORD v24[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h]
  __int64 v26; // [rsp+88h] [rbp-78h]
  _QWORD v27[9]; // [rsp+1D0h] [rbp+D0h] BYREF

  if ( a4 )
    *a4 = 0;
  if ( *((_DWORD *)this + 22) )
    return 2147500037LL;
  FileW = -1;
  if ( *((_QWORD *)this + 14) )
  {
    if ( !a2 && !a3 )
      goto LABEL_22;
    FileW = (__int64)CreateFileW(L"\\\\.\\XVmCtrl", 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( FileW == -1 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = -2147418113;
      if ( LastError < 0 )
        return (unsigned int)LastError;
      return v11;
    }
    InBuffer = *((_QWORD *)this + 14);
    v23 = 0;
    v20 = a2;
    v21 = a2 != 0 ? 3 : 0;
    BytesReturned = 0;
    v22 = a3 != 0;
    if ( !DeviceIoControl((HANDLE)FileW, 0x150270u, &InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      v11 = -2147418113;
      if ( v10 < 0 )
        v11 = v10;
      CloseHandle((HANDLE)FileW);
      return v11;
    }
  }
  if ( a2 )
  {
    v13 = *((_QWORD *)this + 14);
    goto LABEL_23;
  }
LABEL_22:
  v13 = 0;
LABEL_23:
  v26 = v13;
  v27[2] = *((_QWORD *)this + 13);
  v14 = *((_QWORD *)this + 4);
  v27[0] = 0;
  v27[3] = v14;
  v27[4] = *((_QWORD *)this + 5);
  v25 = 0;
  v15 = *((_QWORD *)this + 12);
  memset(v24, 0, sizeof(v24));
  LODWORD(v27[0]) = 1610612736;
  LODWORD(v24[0]) = 3145736;
  *(_QWORD *)((char *)v27 + 4) = 0x40000000;
  v18 = 0;
  v16 = NtAlpcSendWaitReceivePort(v15, 0x10000, v24, v27, 0, 0, 0, &v18);
  if ( v16 < 0 )
  {
    if ( FileW != -1 )
    {
      AlpcSection::SendXvmmDisconnect(*((_QWORD *)this + 14));
      CloseHandle((HANDLE)FileW);
    }
    return v16 | 0x10000000u;
  }
  else
  {
    if ( a4 && a3 )
      *a4 = *((_QWORD *)this + 14);
    *((_QWORD *)this + 14) = 0;
    *((_DWORD *)this + 22) = 1;
    if ( FileW != -1 )
      CloseHandle((HANDLE)FileW);
    return 0;
  }
}

```

## disassembly

```asm
0x18002b288  push    rbp
0x18002b28a  push    rbx
0x18002b28b  push    rsi
0x18002b28c  push    rdi
0x18002b28d  push    r12
0x18002b28f  push    r14
0x18002b291  push    r15
0x18002b293  lea     rbp, [rsp-120h]
0x18002b29b  sub     rsp, 220h
0x18002b2a2  mov     rax, cs:__security_cookie
0x18002b2a9  xor     rax, rsp
0x18002b2ac  mov     [rbp+150h+var_38], rax
0x18002b2b3  xor     r12d, r12d
0x18002b2b6  mov     r14, r9
0x18002b2b9  mov     r15b, r8b
0x18002b2bc  movzx   esi, dx
0x18002b2bf  mov     rdi, rcx
0x18002b2c2  test    r9, r9
0x18002b2c5  jz      short loc_18002B2CA
0x18002b2c7  mov     [r9], r12
0x18002b2ca  cmp     [rcx+58h], r12d
0x18002b2ce  jz      short loc_18002B2DA
0x18002b2d0  mov     eax, 80004005h
0x18002b2d5  jmp     loc_18002B503
0x18002b2da  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002b2de  cmp     [rcx+70h], r12
0x18002b2e2  jz      loc_18002B3FB
0x18002b2e8  test    si, si
0x18002b2eb  jnz     short loc_18002B2F6
0x18002b2ed  test    r15b, r15b
0x18002b2f0  jz      loc_18002B406
0x18002b2f6  mov     eax, 3
0x18002b2fb  mov     [rsp+250h+hTemplateFile], r12; hTemplateFile
0x18002b300  mov     r8d, eax; dwShareMode
0x18002b303  mov     [rsp+250h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18002b308  xor     r9d, r9d; lpSecurityAttributes
0x18002b30b  mov     [rsp+250h+dwCreationDisposition], eax; dwCreationDisposition
0x18002b30f  mov     edx, 0C0000000h; dwDesiredAccess
0x18002b314  lea     rcx, aXvmctrl; "\\\\.\\XVmCtrl"
0x18002b31b  call    cs:__imp_CreateFileW
0x18002b322  nop     dword ptr [rax+rax+00h]
0x18002b327  mov     rbx, rax
0x18002b32a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b32e  jz      loc_18002B3D2
0x18002b334  mov     rax, [rdi+70h]
0x18002b338  lea     r8, [rsp+250h+InBuffer]; lpInBuffer
0x18002b33d  mov     [rsp+250h+InBuffer], rax
0x18002b342  mov     r9d, 10h; nInBufferSize
0x18002b348  mov     [rsp+250h+lpOverlapped], r12; lpOverlapped
0x18002b34d  movzx   eax, si
0x18002b350  neg     ax
0x18002b353  mov     [rsp+250h+var_1F4], r12d
0x18002b358  lea     rax, [rsp+250h+BytesReturned]
0x18002b35d  mov     [rsp+250h+var_1F8], si
0x18002b362  sbb     cl, cl
0x18002b364  mov     [rsp+250h+hTemplateFile], rax; lpBytesReturned
0x18002b369  and     cl, 3
0x18002b36c  mov     [rsp+250h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x18002b371  mov     [rsp+250h+var_1F6], cl
0x18002b375  test    r15b, r15b
0x18002b378  mov     edx, 150270h; dwIoControlCode
0x18002b37d  mov     [rsp+250h+BytesReturned], r12d
0x18002b382  mov     rcx, rbx; hDevice
0x18002b385  mov     qword ptr [rsp+250h+dwCreationDisposition], r12; lpOutBuffer
0x18002b38a  setnz   [rsp+250h+var_1F5]
0x18002b38f  call    cs:__imp_DeviceIoControl
0x18002b396  nop     dword ptr [rax+rax+00h]
0x18002b39b  test    eax, eax
0x18002b39d  jnz     short loc_18002B3FB
0x18002b39f  call    cs:__imp_GetLastError
0x18002b3a6  nop     dword ptr [rax+rax+00h]
0x18002b3ab  test    eax, eax
0x18002b3ad  jle     short loc_18002B3B7
0x18002b3af  movzx   eax, ax
0x18002b3b2  or      eax, 80070000h
0x18002b3b7  test    eax, eax
0x18002b3b9  mov     edi, 8000FFFFh
0x18002b3be  mov     rcx, rbx; hObject
0x18002b3c1  cmovs   edi, eax
0x18002b3c4  call    cs:__imp_CloseHandle
0x18002b3cb  nop     dword ptr [rax+rax+00h]
0x18002b3d0  jmp     short loc_18002B3F4
0x18002b3d2  call    cs:__imp_GetLastError
0x18002b3d9  nop     dword ptr [rax+rax+00h]
0x18002b3de  test    eax, eax
0x18002b3e0  jle     short loc_18002B3EA
0x18002b3e2  movzx   eax, ax
0x18002b3e5  or      eax, 80070000h
0x18002b3ea  test    eax, eax
0x18002b3ec  mov     edi, 8000FFFFh
0x18002b3f1  cmovs   edi, eax
0x18002b3f4  mov     eax, edi
0x18002b3f6  jmp     loc_18002B503
0x18002b3fb  test    si, si
0x18002b3fe  jz      short loc_18002B406
0x18002b400  mov     rax, [rdi+70h]
0x18002b404  jmp     short loc_18002B409
0x18002b406  mov     rax, r12
0x18002b409  mov     [rbp+150h+var_1C8], rax
0x18002b40d  lea     r9, [rbp+150h+var_80]
0x18002b414  mov     rax, [rdi+68h]
0x18002b418  lea     r8, [rsp+250h+var_1F0]
0x18002b41d  mov     [rbp+150h+var_70], rax
0x18002b424  xor     ecx, ecx
0x18002b426  mov     rax, [rdi+20h]
0x18002b42a  xorps   xmm0, xmm0
0x18002b42d  mov     qword ptr [rbp+150h+var_80], rcx
0x18002b434  mov     edx, 10000h
0x18002b439  mov     [rbp+150h+var_68], rax
0x18002b440  mov     rax, [rdi+28h]
0x18002b444  mov     [rbp+150h+var_60], rax
0x18002b44b  lea     rax, [rsp+250h+var_208]
0x18002b450  mov     [rsp+250h+lpOverlapped], rax
0x18002b455  mov     [rsp+250h+hTemplateFile], r12
0x18002b45a  mov     [rbp+150h+var_1D0], rcx
0x18002b45e  mov     rcx, [rdi+60h]
0x18002b462  movups  [rsp+250h+var_1F0], xmm0
0x18002b467  mov     qword ptr [rsp+250h+dwFlagsAndAttributes], r12
0x18002b46c  mov     qword ptr [rsp+250h+dwCreationDisposition], r12
0x18002b471  movups  [rsp+250h+var_1E0], xmm0
0x18002b476  mov     dword ptr [rbp+150h+var_80], 60000000h
0x18002b480  mov     dword ptr [rsp+250h+var_1F0], 300008h
0x18002b488  mov     qword ptr [rbp+150h+var_80+4], 40000000h
0x18002b493  mov     [rsp+250h+var_208], r12
0x18002b498  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18002b49f  nop     dword ptr [rax+rax+00h]
0x18002b4a4  mov     esi, eax
0x18002b4a6  test    eax, eax
0x18002b4a8  js      short loc_18002B4DF
0x18002b4aa  test    r14, r14
0x18002b4ad  jz      short loc_18002B4BB
0x18002b4af  test    r15b, r15b
0x18002b4b2  jz      short loc_18002B4BB
0x18002b4b4  mov     rax, [rdi+70h]
0x18002b4b8  mov     [r14], rax
0x18002b4bb  mov     [rdi+70h], r12
0x18002b4bf  mov     dword ptr [rdi+58h], 1
0x18002b4c6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002b4ca  jz      short loc_18002B4DB
0x18002b4cc  mov     rcx, rbx; hObject
0x18002b4cf  call    cs:__imp_CloseHandle
0x18002b4d6  nop     dword ptr [rax+rax+00h]
0x18002b4db  xor     eax, eax
0x18002b4dd  jmp     short loc_18002B503
0x18002b4df  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002b4e3  jz      short loc_18002B4FD
0x18002b4e5  mov     rcx, [rdi+70h]; unsigned __int64
0x18002b4e9  call    ?SendXvmmDisconnect@AlpcSection@@CAJ_K@Z; AlpcSection::SendXvmmDisconnect(unsigned __int64)
0x18002b4ee  mov     rcx, rbx; hObject
0x18002b4f1  call    cs:__imp_CloseHandle
0x18002b4f8  nop     dword ptr [rax+rax+00h]
0x18002b4fd  bts     esi, 1Ch
0x18002b501  mov     eax, esi
0x18002b503  mov     rcx, [rbp+150h+var_38]
0x18002b50a  xor     rcx, rsp; StackCookie
0x18002b50d  call    __security_check_cookie
0x18002b512  add     rsp, 220h
0x18002b519  pop     r15
0x18002b51b  pop     r14
0x18002b51d  pop     r12
0x18002b51f  pop     rdi
0x18002b520  pop     rsi
0x18002b521  pop     rbx
0x18002b522  pop     rbp
0x18002b523  retn
```
