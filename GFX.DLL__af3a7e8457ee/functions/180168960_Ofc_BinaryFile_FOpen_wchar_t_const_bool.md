# Ofc::BinaryFile::FOpen(wchar_t const *,bool)

- ea: `0x180168960`
- end: `0x180168a40`
- name: `?FOpen@BinaryFile@Ofc@@EEAA_NPEB_W_N@Z`
- size: `224`
- prototype: `bool __fastcall(Ofc::BinaryFile *__hidden this, const wchar_t *, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180056ee0`
- `0x1800573a0`
- `0x1800ab000`
- `0x180168960`
- `0x180168a40`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801689fc`
- `KERNEL32!CloseHandle` at `0x180168a13`
- `KERNEL32!CloseHandle` at `0x1801689fc`
- `KERNEL32!CloseHandle` at `0x180168a13`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1801689cc`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1801689cc`

## pseudocode

```c
char __fastcall Ofc::BinaryFile::FOpen(wchar_t **this, wchar_t *a2, unsigned __int8 a3)
{
  unsigned int v4; // ebx
  _QWORD *v6; // rax
  __int64 FileW; // rbx
  wchar_t *v8; // rcx
  _BYTE v10[4208]; // [rsp+40h] [rbp-1088h] BYREF

  v4 = a3;
  v6 = (_QWORD *)Ofc::LongFileName::LongFileName((Ofc::LongFileName *)v10, a2);
  FileW = MsoCreateFileW(*v6, ((v4 ^ 1) + 2) << 30, v4, 0, (v4 ^ 1) + 3, 0, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  Ofc::CStr::operator=(this + 2, (Ofc *)a2);
  v8 = this[3];
  this[3] = (wchar_t *)FileW;
  if ( (unsigned __int64)v8 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  return 1;
}

```

## disassembly

```asm
0x180168960  mov     [rsp+arg_10], rbx
0x180168965  mov     [rsp+arg_18], rsi
0x18016896a  push    rdi
0x18016896b  mov     eax, 10C0h
0x180168970  call    _alloca_probe
0x180168975  sub     rsp, rax
0x180168978  mov     rax, cs:__security_cookie
0x18016897f  xor     rax, rsp
0x180168982  mov     [rsp+10C8h+var_18], rax
0x18016898a  mov     rdi, rcx
0x18016898d  movzx   ebx, r8b
0x180168991  lea     rcx, [rsp+10C8h+var_1088]; this
0x180168996  mov     rsi, rdx
0x180168999  call    ??0LongFileName@Ofc@@QEAA@PEB_W@Z; Ofc::LongFileName::LongFileName(wchar_t const *)
0x18016899e  mov     [rsp+10C8h+var_1098], 0
0x1801689a7  mov     r8d, ebx
0x1801689aa  mov     [rsp+10C8h+var_10A0], 0
0x1801689b2  mov     rcx, [rax]
0x1801689b5  mov     eax, ebx
0x1801689b7  xor     eax, 1
0x1801689ba  lea     r9d, [rax+3]
0x1801689be  lea     edx, [rax+2]
0x1801689c1  mov     [rsp+10C8h+var_10A8], r9d
0x1801689c6  xor     r9d, r9d
0x1801689c9  shl     edx, 1Eh
0x1801689cc  call    cs:__imp_MsoCreateFileW
0x1801689d2  mov     rbx, rax
0x1801689d5  dec     rax
0x1801689d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801689dc  ja      short loc_180168A06
0x1801689de  lea     rcx, [rdi+10h]; this
0x1801689e2  mov     rdx, rsi; Ofc *
0x1801689e5  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x1801689ea  mov     rcx, [rdi+18h]; hObject
0x1801689ee  mov     [rdi+18h], rbx
0x1801689f2  lea     rdx, [rcx-1]
0x1801689f6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801689fa  ja      short loc_180168A02
0x1801689fc  call    cs:__imp_CloseHandle
0x180168a02  mov     al, 1
0x180168a04  jmp     short loc_180168A1B
0x180168a06  lea     rax, [rbx-1]
0x180168a0a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180168a0e  ja      short loc_180168A19
0x180168a10  mov     rcx, rbx; hObject
0x180168a13  call    cs:__imp_CloseHandle
0x180168a19  xor     al, al
0x180168a1b  mov     rcx, [rsp+10C8h+var_18]
0x180168a23  xor     rcx, rsp; StackCookie
0x180168a26  call    __security_check_cookie
0x180168a2b  lea     r11, [rsp+10C8h+var_8]
0x180168a33  mov     rbx, [r11+20h]
0x180168a37  mov     rsi, [r11+28h]
0x180168a3b  mov     rsp, r11
0x180168a3e  pop     rdi
0x180168a3f  retn
```
