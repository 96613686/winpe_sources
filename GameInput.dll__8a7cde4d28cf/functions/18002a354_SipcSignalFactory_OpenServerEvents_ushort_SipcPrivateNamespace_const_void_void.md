# SipcSignalFactory::OpenServerEvents(ushort,SipcPrivateNamespace const &,void * *,void * *)

- ea: `0x18002a354`
- end: `0x18002a500`
- name: `?OpenServerEvents@SipcSignalFactory@@SAJGAEBVSipcPrivateNamespace@@PEAPEAX1@Z`
- size: `428`
- prototype: `__int64 __fastcall(unsigned __int16, const struct SipcPrivateNamespace *, void **, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180025520`

## callees

- `0x18002a354`
- `0x18004c8e0`

## import_xrefs

- `ntdll!swprintf_s` at `0x18002a3b7`
- `ntdll!swprintf_s` at `0x18002a3e8`
- `ntdll!swprintf_s` at `0x18002a407`
- `ntdll!swprintf_s` at `0x18002a434`
- `ntdll!swprintf_s` at `0x18002a3b7`
- `ntdll!swprintf_s` at `0x18002a3e8`
- `ntdll!swprintf_s` at `0x18002a407`
- `ntdll!swprintf_s` at `0x18002a434`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002a44c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002a493`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002a44c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002a493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a4c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a4c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4a4`

## pseudocode

```c
__int64 __fastcall SipcSignalFactory::OpenServerEvents(
        unsigned __int16 a1,
        const struct SipcPrivateNamespace *a2,
        void **a3,
        void **a4)
{
  char *v4; // rbp
  char *v7; // r9
  int v8; // ebx
  HANDLE v9; // rbx
  signed int LastError; // eax
  unsigned int v11; // edi
  HANDLE v13; // rax
  signed int v14; // eax
  __int64 v15; // [rsp+20h] [rbp-138h]
  wchar_t Buffer[56]; // [rsp+30h] [rbp-128h] BYREF
  wchar_t Name[56]; // [rsp+A0h] [rbp-B8h] BYREF

  v4 = (char *)a2 + 8;
  *a3 = 0;
  *a4 = 0;
  v7 = (char *)a2 + 8;
  if ( a1 )
  {
    v8 = a1;
    swprintf_s(Buffer, 0x38u, L"%s\\%4.4X_%s", v7, a1, L"ClientSignal");
    LODWORD(v15) = v8;
    swprintf_s(Name, 0x38u, L"%s\\%4.4X_%s", v4, v15, L"ServerSignal");
  }
  else
  {
    swprintf_s(Buffer, 0x38u, L"%s\\%s", v7, L"ClientSignal");
    swprintf_s(Name, 0x38u, L"%s\\%s", v4, L"ServerSignal");
  }
  v9 = OpenEventW(0x100002u, 0, Buffer);
  if ( !v9 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = -2147418113;
    if ( LastError < 0 )
      return (unsigned int)LastError;
    return v11;
  }
  v13 = OpenEventW(2u, 0, Name);
  if ( !v13 )
  {
    v14 = GetLastError();
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    v11 = -2147418113;
    if ( v14 < 0 )
      v11 = v14;
    CloseHandle(v9);
    return v11;
  }
  *a3 = v9;
  *a4 = v13;
  return 0;
}

```

## disassembly

```asm
0x18002a354  push    rbx
0x18002a356  push    rbp
0x18002a357  push    rsi
0x18002a358  push    rdi
0x18002a359  push    r14
0x18002a35b  push    r15
0x18002a35d  sub     rsp, 128h
0x18002a364  mov     rax, cs:__security_cookie
0x18002a36b  xor     rax, rsp
0x18002a36e  mov     [rsp+158h+var_48], rax
0x18002a376  xor     r15d, r15d
0x18002a379  lea     rbp, [rdx+8]
0x18002a37d  mov     [r8], r15
0x18002a380  mov     rsi, r9
0x18002a383  mov     [r9], r15
0x18002a386  mov     rdi, r8
0x18002a389  lea     rax, ?ClientSignalName@SipcSignalFactory@@0QBGB; "ClientSignal"
0x18002a390  mov     r9, rbp
0x18002a393  lea     r14d, [r15+38h]
0x18002a397  mov     edx, r14d; BufferCount
0x18002a39a  test    cx, cx
0x18002a39d  jz      short loc_18002A3F6
0x18002a39f  movzx   ebx, cx
0x18002a3a2  lea     r8, aS44xS; "%s\\%4.4X_%s"
0x18002a3a9  mov     [rsp+158h+var_130], rax
0x18002a3ae  lea     rcx, [rsp+158h+Buffer]; Buffer
0x18002a3b3  mov     dword ptr [rsp+158h+var_138], ebx
0x18002a3b7  call    cs:__imp_swprintf_s
0x18002a3be  nop     dword ptr [rax+rax+00h]
0x18002a3c3  lea     rax, ?ServerSignalName@SipcSignalFactory@@0QBGB; "ServerSignal"
0x18002a3ca  mov     r9, rbp
0x18002a3cd  mov     [rsp+158h+var_130], rax
0x18002a3d2  lea     r8, aS44xS; "%s\\%4.4X_%s"
0x18002a3d9  mov     edx, r14d; BufferCount
0x18002a3dc  mov     dword ptr [rsp+158h+var_138], ebx
0x18002a3e0  lea     rcx, [rsp+158h+Name]; Buffer
0x18002a3e8  call    cs:__imp_swprintf_s
0x18002a3ef  nop     dword ptr [rax+rax+00h]
0x18002a3f4  jmp     short loc_18002A440
0x18002a3f6  lea     r8, aSS; "%s\\%s"
0x18002a3fd  mov     [rsp+158h+var_138], rax
0x18002a402  lea     rcx, [rsp+158h+Buffer]; Buffer
0x18002a407  call    cs:__imp_swprintf_s
0x18002a40e  nop     dword ptr [rax+rax+00h]
0x18002a413  lea     rax, ?ServerSignalName@SipcSignalFactory@@0QBGB; "ServerSignal"
0x18002a41a  mov     r9, rbp
0x18002a41d  lea     r8, aSS; "%s\\%s"
0x18002a424  mov     [rsp+158h+var_138], rax
0x18002a429  mov     rdx, r14; BufferCount
0x18002a42c  lea     rcx, [rsp+158h+Name]; Buffer
0x18002a434  call    cs:__imp_swprintf_s
0x18002a43b  nop     dword ptr [rax+rax+00h]
0x18002a440  lea     r8, [rsp+158h+Buffer]; lpName
0x18002a445  xor     edx, edx; bInheritHandle
0x18002a447  mov     ecx, 100002h; dwDesiredAccess
0x18002a44c  call    cs:__imp_OpenEventW
0x18002a453  nop     dword ptr [rax+rax+00h]
0x18002a458  mov     rbx, rax
0x18002a45b  test    rax, rax
0x18002a45e  jnz     short loc_18002A486
0x18002a460  call    cs:__imp_GetLastError
0x18002a467  nop     dword ptr [rax+rax+00h]
0x18002a46c  test    eax, eax
0x18002a46e  jle     short loc_18002A478
0x18002a470  movzx   eax, ax
0x18002a473  or      eax, 80070000h
0x18002a478  test    eax, eax
0x18002a47a  mov     edi, 8000FFFFh
0x18002a47f  cmovs   edi, eax
0x18002a482  mov     eax, edi
0x18002a484  jmp     short loc_18002A4DF
0x18002a486  xor     edx, edx; bInheritHandle
0x18002a488  lea     r8, [rsp+158h+Name]; lpName
0x18002a490  lea     ecx, [rdx+2]; dwDesiredAccess
0x18002a493  call    cs:__imp_OpenEventW
0x18002a49a  nop     dword ptr [rax+rax+00h]
0x18002a49f  test    rax, rax
0x18002a4a2  jnz     short loc_18002A4D7
0x18002a4a4  call    cs:__imp_GetLastError
0x18002a4ab  nop     dword ptr [rax+rax+00h]
0x18002a4b0  test    eax, eax
0x18002a4b2  jle     short loc_18002A4BC
0x18002a4b4  movzx   eax, ax
0x18002a4b7  or      eax, 80070000h
0x18002a4bc  test    eax, eax
0x18002a4be  mov     edi, 8000FFFFh
0x18002a4c3  mov     rcx, rbx; hObject
0x18002a4c6  cmovs   edi, eax
0x18002a4c9  call    cs:__imp_CloseHandle
0x18002a4d0  nop     dword ptr [rax+rax+00h]
0x18002a4d5  jmp     short loc_18002A482
0x18002a4d7  mov     [rdi], rbx
0x18002a4da  mov     [rsi], rax
0x18002a4dd  xor     eax, eax
0x18002a4df  mov     rcx, [rsp+158h+var_48]
0x18002a4e7  xor     rcx, rsp; StackCookie
0x18002a4ea  call    __security_check_cookie
0x18002a4ef  add     rsp, 128h
0x18002a4f6  pop     r15
0x18002a4f8  pop     r14
0x18002a4fa  pop     rdi
0x18002a4fb  pop     rsi
0x18002a4fc  pop     rbp
0x18002a4fd  pop     rbx
0x18002a4fe  retn
```
