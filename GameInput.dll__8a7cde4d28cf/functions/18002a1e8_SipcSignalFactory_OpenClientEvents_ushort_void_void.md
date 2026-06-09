# SipcSignalFactory::OpenClientEvents(ushort,void * *,void * *)

- ea: `0x18002a1e8`
- end: `0x18002a34e`
- name: `?OpenClientEvents@SipcSignalFactory@@SAJGPEAPEAX0@Z`
- size: `358`
- prototype: `__int64 __fastcall(unsigned __int16, void **, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180026d6c`

## callees

- `0x18002a1e8`
- `0x18004c8e0`

## import_xrefs

- `ntdll!swprintf_s` at `0x18002a248`
- `ntdll!swprintf_s` at `0x18002a2c3`
- `ntdll!swprintf_s` at `0x18002a248`
- `ntdll!swprintf_s` at `0x18002a2c3`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002a25e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002a2db`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002a25e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002a2db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a311`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2ec`

## pseudocode

```c
__int64 __fastcall SipcSignalFactory::OpenClientEvents(unsigned __int16 a1, void **a2, void **a3)
{
  unsigned int v3; // ebp
  HANDLE v6; // rbx
  signed int LastError; // eax
  unsigned int v8; // edi
  HANDLE v10; // rax
  signed int v11; // eax
  __int64 v12; // [rsp+28h] [rbp-80h]
  wchar_t Buffer[20]; // [rsp+30h] [rbp-78h] BYREF
  wchar_t Name[20]; // [rsp+58h] [rbp-50h] BYREF

  *a2 = 0;
  v3 = a1;
  *a3 = 0;
  swprintf_s(Buffer, 0x14u, L"%4.4X_%s:%u", a1, L"ClientSignal", 2);
  v6 = OpenEventW(2u, 0, Buffer);
  if ( !v6 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = -2147418113;
    if ( LastError < 0 )
      return (unsigned int)LastError;
    return v8;
  }
  LODWORD(v12) = 2;
  swprintf_s(Name, 0x14u, L"%4.4X_%s:%u", v3, L"ServerSignal", v12);
  v10 = OpenEventW(0x100002u, 0, Name);
  if ( !v10 )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    v8 = -2147418113;
    if ( v11 < 0 )
      v8 = v11;
    CloseHandle(v6);
    return v8;
  }
  *a2 = v6;
  *a3 = v10;
  return 0;
}

```

## disassembly

```asm
0x18002a1e8  mov     [rsp+arg_18], rbx
0x18002a1ed  push    rbp
0x18002a1ee  push    rsi
0x18002a1ef  push    rdi
0x18002a1f0  sub     rsp, 90h
0x18002a1f7  mov     rax, cs:__security_cookie
0x18002a1fe  xor     rax, rsp
0x18002a201  mov     [rsp+0A8h+var_28], rax
0x18002a209  mov     qword ptr [rdx], 0
0x18002a210  lea     rax, ?ClientSignalName@SipcSignalFactory@@0QBGB; "ClientSignal"
0x18002a217  movzx   ebp, cx
0x18002a21a  mov     rsi, r8
0x18002a21d  mov     qword ptr [r8], 0
0x18002a224  lea     rcx, [rsp+0A8h+Buffer]; Buffer
0x18002a229  mov     rdi, rdx
0x18002a22c  mov     dword ptr [rsp+0A8h+var_80], 2
0x18002a234  mov     r9d, ebp
0x18002a237  mov     [rsp+0A8h+var_88], rax
0x18002a23c  lea     r8, a44xSU; "%4.4X_%s:%u"
0x18002a243  mov     edx, 14h; BufferCount
0x18002a248  call    cs:__imp_swprintf_s
0x18002a24f  nop     dword ptr [rax+rax+00h]
0x18002a254  xor     edx, edx; bInheritHandle
0x18002a256  lea     r8, [rsp+0A8h+Buffer]; lpName
0x18002a25b  lea     ecx, [rdx+2]; dwDesiredAccess
0x18002a25e  call    cs:__imp_OpenEventW
0x18002a265  nop     dword ptr [rax+rax+00h]
0x18002a26a  mov     rbx, rax
0x18002a26d  test    rax, rax
0x18002a270  jnz     short loc_18002A29B
0x18002a272  call    cs:__imp_GetLastError
0x18002a279  nop     dword ptr [rax+rax+00h]
0x18002a27e  test    eax, eax
0x18002a280  jle     short loc_18002A28A
0x18002a282  movzx   eax, ax
0x18002a285  or      eax, 80070000h
0x18002a28a  test    eax, eax
0x18002a28c  mov     edi, 8000FFFFh
0x18002a291  cmovs   edi, eax
0x18002a294  mov     eax, edi
0x18002a296  jmp     loc_18002A32A
0x18002a29b  lea     rax, ?ServerSignalName@SipcSignalFactory@@0QBGB; "ServerSignal"
0x18002a2a2  mov     dword ptr [rsp+0A8h+var_80], 2
0x18002a2aa  mov     r9d, ebp
0x18002a2ad  mov     [rsp+0A8h+var_88], rax
0x18002a2b2  lea     r8, a44xSU; "%4.4X_%s:%u"
0x18002a2b9  mov     edx, 14h; BufferCount
0x18002a2be  lea     rcx, [rsp+0A8h+Name]; Buffer
0x18002a2c3  call    cs:__imp_swprintf_s
0x18002a2ca  nop     dword ptr [rax+rax+00h]
0x18002a2cf  lea     r8, [rsp+0A8h+Name]; lpName
0x18002a2d4  xor     edx, edx; bInheritHandle
0x18002a2d6  mov     ecx, 100002h; dwDesiredAccess
0x18002a2db  call    cs:__imp_OpenEventW
0x18002a2e2  nop     dword ptr [rax+rax+00h]
0x18002a2e7  test    rax, rax
0x18002a2ea  jnz     short loc_18002A322
0x18002a2ec  call    cs:__imp_GetLastError
0x18002a2f3  nop     dword ptr [rax+rax+00h]
0x18002a2f8  test    eax, eax
0x18002a2fa  jle     short loc_18002A304
0x18002a2fc  movzx   eax, ax
0x18002a2ff  or      eax, 80070000h
0x18002a304  test    eax, eax
0x18002a306  mov     edi, 8000FFFFh
0x18002a30b  mov     rcx, rbx; hObject
0x18002a30e  cmovs   edi, eax
0x18002a311  call    cs:__imp_CloseHandle
0x18002a318  nop     dword ptr [rax+rax+00h]
0x18002a31d  jmp     loc_18002A294
0x18002a322  mov     [rdi], rbx
0x18002a325  mov     [rsi], rax
0x18002a328  xor     eax, eax
0x18002a32a  mov     rcx, [rsp+0A8h+var_28]
0x18002a332  xor     rcx, rsp; StackCookie
0x18002a335  call    __security_check_cookie
0x18002a33a  mov     rbx, [rsp+0A8h+arg_18]
0x18002a342  add     rsp, 90h
0x18002a349  pop     rdi
0x18002a34a  pop     rsi
0x18002a34b  pop     rbp
0x18002a34c  retn
```
