# PrintConfig::CCancelEventHandler::InitializeEvents(ushort const *)

- ea: `0x1800bfc08`
- end: `0x1800bfcf1`
- name: `?InitializeEvents@CCancelEventHandler@PrintConfig@@IEAAJPEBG@Z`
- size: `233`
- prototype: `__int64 __fastcall(PrintConfig::CCancelEventHandler *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1800bda5c`

## callees

- `0x1800bfc08`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800bfc41`
- `KERNEL32!CloseHandle` at `0x1800bfca7`
- `KERNEL32!CloseHandle` at `0x1800bfc41`
- `KERNEL32!CloseHandle` at `0x1800bfca7`
- `KERNEL32!GetLastError` at `0x1800bfc5f`
- `KERNEL32!GetLastError` at `0x1800bfcc3`
- `KERNEL32!GetLastError` at `0x1800bfc5f`
- `KERNEL32!GetLastError` at `0x1800bfcc3`
- `KERNEL32!CreateEventW` at `0x1800bfc8a`
- `KERNEL32!CreateEventW` at `0x1800bfc8a`
- `KERNEL32!OpenEventW` at `0x1800bfc24`
- `KERNEL32!OpenEventW` at `0x1800bfc24`

## pseudocode

```c
__int64 __fastcall PrintConfig::CCancelEventHandler::InitializeEvents(
        PrintConfig::CCancelEventHandler *this,
        const unsigned __int16 *a2)
{
  char *v3; // rax
  char *v4; // rcx
  char *v5; // rbx
  unsigned int v6; // ebx
  signed int v7; // eax
  HANDLE EventW; // rax
  char *v9; // rcx
  HANDLE v10; // rsi
  signed int LastError; // eax

  v3 = (char *)OpenEventW(0x120002u, 0, a2);
  v4 = (char *)*((_QWORD *)this + 1);
  v5 = v3;
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  *((_QWORD *)this + 1) = v5;
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v6 = 0;
LABEL_8:
    EventW = CreateEventW(0, 1, 0, 0);
    v9 = (char *)*((_QWORD *)this + 2);
    v10 = EventW;
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v9);
    *((_QWORD *)this + 2) = v10;
    if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    return v6;
  }
  v7 = GetLastError();
  v6 = v7;
  if ( v7 > 0 )
    v6 = (unsigned __int16)v7 | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
    goto LABEL_8;
  return v6;
}

```

## disassembly

```asm
0x1800bfc08  mov     [rsp+arg_0], rbx
0x1800bfc0d  mov     [rsp+arg_8], rsi
0x1800bfc12  push    rdi
0x1800bfc13  sub     rsp, 20h
0x1800bfc17  mov     rdi, rcx
0x1800bfc1a  mov     r8, rdx; lpName
0x1800bfc1d  xor     edx, edx; bInheritHandle
0x1800bfc1f  mov     ecx, 120002h; dwDesiredAccess
0x1800bfc24  call    cs:__imp_OpenEventW
0x1800bfc2b  nop     dword ptr [rax+rax+00h]
0x1800bfc30  mov     rcx, [rdi+8]; hObject
0x1800bfc34  mov     rbx, rax
0x1800bfc37  lea     rdx, [rcx-1]
0x1800bfc3b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800bfc3f  ja      short loc_1800BFC4D
0x1800bfc41  call    cs:__imp_CloseHandle
0x1800bfc48  nop     dword ptr [rax+rax+00h]
0x1800bfc4d  lea     rax, [rbx-1]
0x1800bfc51  mov     [rdi+8], rbx
0x1800bfc55  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800bfc59  ja      short loc_1800BFC5F
0x1800bfc5b  xor     ebx, ebx
0x1800bfc5d  jmp     short loc_1800BFC7E
0x1800bfc5f  call    cs:__imp_GetLastError
0x1800bfc66  nop     dword ptr [rax+rax+00h]
0x1800bfc6b  mov     ebx, eax
0x1800bfc6d  test    eax, eax
0x1800bfc6f  jle     short loc_1800BFC7A
0x1800bfc71  movzx   ebx, ax
0x1800bfc74  or      ebx, 80070000h
0x1800bfc7a  test    ebx, ebx
0x1800bfc7c  js      short loc_1800BFCDE
0x1800bfc7e  xor     r9d, r9d; lpName
0x1800bfc81  xor     r8d, r8d; bInitialState
0x1800bfc84  xor     ecx, ecx; lpEventAttributes
0x1800bfc86  lea     edx, [r9+1]; bManualReset
0x1800bfc8a  call    cs:__imp_CreateEventW
0x1800bfc91  nop     dword ptr [rax+rax+00h]
0x1800bfc96  mov     rcx, [rdi+10h]; hObject
0x1800bfc9a  mov     rsi, rax
0x1800bfc9d  lea     rdx, [rcx-1]
0x1800bfca1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800bfca5  ja      short loc_1800BFCB3
0x1800bfca7  call    cs:__imp_CloseHandle
0x1800bfcae  nop     dword ptr [rax+rax+00h]
0x1800bfcb3  lea     rax, [rsi+1]
0x1800bfcb7  mov     [rdi+10h], rsi
0x1800bfcbb  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800bfcc1  jnz     short loc_1800BFCDE
0x1800bfcc3  call    cs:__imp_GetLastError
0x1800bfcca  nop     dword ptr [rax+rax+00h]
0x1800bfccf  mov     ebx, eax
0x1800bfcd1  test    eax, eax
0x1800bfcd3  jle     short loc_1800BFCDE
0x1800bfcd5  movzx   ebx, ax
0x1800bfcd8  or      ebx, 80070000h
0x1800bfcde  mov     rsi, [rsp+28h+arg_8]
0x1800bfce3  mov     eax, ebx
0x1800bfce5  mov     rbx, [rsp+28h+arg_0]
0x1800bfcea  add     rsp, 20h
0x1800bfcee  pop     rdi
0x1800bfcef  retn
```
