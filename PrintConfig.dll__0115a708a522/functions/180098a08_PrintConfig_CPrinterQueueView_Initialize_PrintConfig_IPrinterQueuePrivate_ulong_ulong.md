# PrintConfig::CPrinterQueueView::Initialize(PrintConfig::IPrinterQueuePrivate *,ulong,ulong)

- ea: `0x180098a08`
- end: `0x180098b5d`
- name: `?Initialize@CPrinterQueueView@PrintConfig@@AEAAJPEAUIPrinterQueuePrivate@2@KK@Z`
- size: `341`
- prototype: `__int64 __fastcall(PrintConfig::CPrinterQueueView *__hidden this, struct PrintConfig::IPrinterQueuePrivate *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800570e0`

## callees

- `0x180098a08`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180098a90`
- `KERNEL32!CloseHandle` at `0x180098afa`
- `KERNEL32!CloseHandle` at `0x180098a90`
- `KERNEL32!CloseHandle` at `0x180098afa`
- `KERNEL32!GetLastError` at `0x180098ab1`
- `KERNEL32!GetLastError` at `0x180098b19`
- `KERNEL32!GetLastError` at `0x180098ab1`
- `KERNEL32!GetLastError` at `0x180098b19`
- `KERNEL32!CreateEventW` at `0x180098a70`
- `KERNEL32!CreateEventW` at `0x180098ada`
- `KERNEL32!CreateEventW` at `0x180098a70`
- `KERNEL32!CreateEventW` at `0x180098ada`

## pseudocode

```c
__int64 __fastcall PrintConfig::CPrinterQueueView::Initialize(
        PrintConfig::CPrinterQueueView *this,
        struct PrintConfig::IPrinterQueuePrivate *a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v9; // rcx
  char *EventW; // rax
  char *v11; // rcx
  char *v12; // rbx
  signed int v13; // ebx
  signed int LastError; // eax
  HANDLE v15; // rax
  char *v16; // rcx
  HANDLE v17; // rsi
  signed int v18; // eax

  if ( !a2 )
    return 2147942487LL;
  if ( *((struct PrintConfig::IPrinterQueuePrivate **)this + 21) != a2 )
  {
    (*(void (__fastcall **)(struct PrintConfig::IPrinterQueuePrivate *))(*(_QWORD *)a2 + 8LL))(a2);
    v9 = *((_QWORD *)this + 21);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 21) = a2;
  }
  EventW = (char *)CreateEventW(0, 0, 1, 0);
  v11 = (char *)*((_QWORD *)this + 22);
  v12 = EventW;
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v11);
  *((_QWORD *)this + 22) = v12;
  if ( (unsigned __int64)(v12 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( v13 < 0 )
      return (unsigned int)v13;
  }
  else
  {
    v13 = 0;
  }
  v15 = CreateEventW(0, 0, 0, 0);
  v16 = (char *)*((_QWORD *)this + 23);
  v17 = v15;
  if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v16);
  *((_QWORD *)this + 23) = v17;
  if ( (((unsigned __int64)v17 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v18 = GetLastError();
    v13 = v18;
    if ( v18 > 0 )
      v13 = (unsigned __int16)v18 | 0x80070000;
  }
  if ( v13 >= 0 )
    return (unsigned int)(*(__int64 (__fastcall **)(PrintConfig::CPrinterQueueView *, _QWORD, _QWORD))(*(_QWORD *)this + 56LL))(
                           this,
                           a3,
                           a4);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180098a08  push    rbx
0x180098a0a  push    rbp
0x180098a0b  push    rsi
0x180098a0c  push    rdi
0x180098a0d  push    r14
0x180098a0f  sub     rsp, 20h
0x180098a13  mov     ebp, r9d
0x180098a16  mov     r14d, r8d
0x180098a19  mov     rbx, rdx
0x180098a1c  mov     rdi, rcx
0x180098a1f  test    rdx, rdx
0x180098a22  jnz     short loc_180098A2E
0x180098a24  mov     eax, 80070057h
0x180098a29  jmp     loc_180098B51
0x180098a2e  cmp     [rcx+0A8h], rbx
0x180098a35  jz      short loc_180098A65
0x180098a37  mov     rax, [rdx]
0x180098a3a  mov     rcx, rbx
0x180098a3d  mov     rax, [rax+8]
0x180098a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098a46  mov     rcx, [rdi+0A8h]
0x180098a4d  test    rcx, rcx
0x180098a50  jz      short loc_180098A5E
0x180098a52  mov     rax, [rcx]
0x180098a55  mov     rax, [rax+10h]
0x180098a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098a5e  mov     [rdi+0A8h], rbx
0x180098a65  xor     r9d, r9d; lpName
0x180098a68  xor     edx, edx; bManualReset
0x180098a6a  xor     ecx, ecx; lpEventAttributes
0x180098a6c  lea     r8d, [r9+1]; bInitialState
0x180098a70  call    cs:__imp_CreateEventW
0x180098a77  nop     dword ptr [rax+rax+00h]
0x180098a7c  mov     rcx, [rdi+0B0h]; hObject
0x180098a83  mov     rbx, rax
0x180098a86  lea     rdx, [rcx-1]
0x180098a8a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180098a8e  ja      short loc_180098A9C
0x180098a90  call    cs:__imp_CloseHandle
0x180098a97  nop     dword ptr [rax+rax+00h]
0x180098a9c  lea     rax, [rbx-1]
0x180098aa0  mov     [rdi+0B0h], rbx
0x180098aa7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180098aab  ja      short loc_180098AB1
0x180098aad  xor     ebx, ebx
0x180098aaf  jmp     short loc_180098AD0
0x180098ab1  call    cs:__imp_GetLastError
0x180098ab8  nop     dword ptr [rax+rax+00h]
0x180098abd  mov     ebx, eax
0x180098abf  test    eax, eax
0x180098ac1  jle     short loc_180098ACC
0x180098ac3  movzx   ebx, ax
0x180098ac6  or      ebx, 80070000h
0x180098acc  test    ebx, ebx
0x180098ace  js      short loc_180098B4F
0x180098ad0  xor     r9d, r9d; lpName
0x180098ad3  xor     r8d, r8d; bInitialState
0x180098ad6  xor     edx, edx; bManualReset
0x180098ad8  xor     ecx, ecx; lpEventAttributes
0x180098ada  call    cs:__imp_CreateEventW
0x180098ae1  nop     dword ptr [rax+rax+00h]
0x180098ae6  mov     rcx, [rdi+0B8h]; hObject
0x180098aed  mov     rsi, rax
0x180098af0  lea     rdx, [rcx-1]
0x180098af4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180098af8  ja      short loc_180098B06
0x180098afa  call    cs:__imp_CloseHandle
0x180098b01  nop     dword ptr [rax+rax+00h]
0x180098b06  lea     rax, [rsi+1]
0x180098b0a  mov     [rdi+0B8h], rsi
0x180098b11  test    rax, 0FFFFFFFFFFFFFFFEh
0x180098b17  jnz     short loc_180098B34
0x180098b19  call    cs:__imp_GetLastError
0x180098b20  nop     dword ptr [rax+rax+00h]
0x180098b25  mov     ebx, eax
0x180098b27  test    eax, eax
0x180098b29  jle     short loc_180098B34
0x180098b2b  movzx   ebx, ax
0x180098b2e  or      ebx, 80070000h
0x180098b34  test    ebx, ebx
0x180098b36  js      short loc_180098B4F
0x180098b38  mov     rax, [rdi]
0x180098b3b  mov     r8d, ebp
0x180098b3e  mov     edx, r14d
0x180098b41  mov     rcx, rdi
0x180098b44  mov     rax, [rax+38h]
0x180098b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098b4d  mov     ebx, eax
0x180098b4f  mov     eax, ebx
0x180098b51  add     rsp, 20h
0x180098b55  pop     r14
0x180098b57  pop     rdi
0x180098b58  pop     rsi
0x180098b59  pop     rbp
0x180098b5a  pop     rbx
0x180098b5b  retn
```
