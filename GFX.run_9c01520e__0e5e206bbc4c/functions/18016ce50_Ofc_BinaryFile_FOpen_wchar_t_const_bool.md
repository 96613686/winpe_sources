# Ofc::BinaryFile::FOpen(wchar_t const *,bool)

- ea: `0x18016ce50`
- end: `0x18016cf30`
- name: `?FOpen@BinaryFile@Ofc@@EEAA_NPEB_W_N@Z`
- size: `224`
- prototype: `bool __fastcall(Ofc::BinaryFile *__hidden this, const wchar_t *, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1800578b0`
- `0x180057e20`
- `0x1800f7ff0`
- `0x18016ce50`
- `0x18016cf30`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18016ceec`
- `KERNEL32!CloseHandle` at `0x18016cf03`
- `KERNEL32!CloseHandle` at `0x18016ceec`
- `KERNEL32!CloseHandle` at `0x18016cf03`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x18016cebc`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x18016cebc`

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
0x18016ce50  mov     [rsp+arg_10], rbx
0x18016ce55  mov     [rsp+arg_18], rsi
0x18016ce5a  push    rdi
0x18016ce5b  mov     eax, 10C0h
0x18016ce60  call    _alloca_probe
0x18016ce65  sub     rsp, rax
0x18016ce68  mov     rax, cs:__security_cookie
0x18016ce6f  xor     rax, rsp
0x18016ce72  mov     [rsp+10C8h+var_18], rax
0x18016ce7a  mov     rdi, rcx
0x18016ce7d  movzx   ebx, r8b
0x18016ce81  lea     rcx, [rsp+10C8h+var_1088]; this
0x18016ce86  mov     rsi, rdx
0x18016ce89  call    ??0LongFileName@Ofc@@QEAA@PEB_W@Z; Ofc::LongFileName::LongFileName(wchar_t const *)
0x18016ce8e  mov     [rsp+10C8h+var_1098], 0
0x18016ce97  mov     r8d, ebx
0x18016ce9a  mov     [rsp+10C8h+var_10A0], 0
0x18016cea2  mov     rcx, [rax]
0x18016cea5  mov     eax, ebx
0x18016cea7  xor     eax, 1
0x18016ceaa  lea     r9d, [rax+3]
0x18016ceae  lea     edx, [rax+2]
0x18016ceb1  mov     [rsp+10C8h+var_10A8], r9d
0x18016ceb6  xor     r9d, r9d
0x18016ceb9  shl     edx, 1Eh
0x18016cebc  call    cs:__imp_MsoCreateFileW
0x18016cec2  mov     rbx, rax
0x18016cec5  dec     rax
0x18016cec8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18016cecc  ja      short loc_18016CEF6
0x18016cece  lea     rcx, [rdi+10h]; this
0x18016ced2  mov     rdx, rsi; Ofc *
0x18016ced5  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18016ceda  mov     rcx, [rdi+18h]; hObject
0x18016cede  mov     [rdi+18h], rbx
0x18016cee2  lea     rdx, [rcx-1]
0x18016cee6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18016ceea  ja      short loc_18016CEF2
0x18016ceec  call    cs:__imp_CloseHandle
0x18016cef2  mov     al, 1
0x18016cef4  jmp     short loc_18016CF0B
0x18016cef6  lea     rax, [rbx-1]
0x18016cefa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18016cefe  ja      short loc_18016CF09
0x18016cf00  mov     rcx, rbx; hObject
0x18016cf03  call    cs:__imp_CloseHandle
0x18016cf09  xor     al, al
0x18016cf0b  mov     rcx, [rsp+10C8h+var_18]
0x18016cf13  xor     rcx, rsp; StackCookie
0x18016cf16  call    __security_check_cookie
0x18016cf1b  lea     r11, [rsp+10C8h+var_8]
0x18016cf23  mov     rbx, [r11+20h]
0x18016cf27  mov     rsi, [r11+28h]
0x18016cf2b  mov     rsp, r11
0x18016cf2e  pop     rdi
0x18016cf2f  retn
```
