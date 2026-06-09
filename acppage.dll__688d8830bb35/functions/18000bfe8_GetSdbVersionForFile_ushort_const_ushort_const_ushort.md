# GetSdbVersionForFile(ushort const *,ushort const *,ushort *)

- ea: `0x18000bfe8`
- end: `0x18000c0c7`
- name: `?GetSdbVersionForFile@@YAHPEBG0PEAG@Z`
- size: `223`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18000c630`

## callees

- `0x18000bfe8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000c026`
- `ntdll!RtlInitUnicodeString` at `0x18000c026`
- `KERNEL32!CloseHandle` at `0x18000c0af`
- `KERNEL32!CloseHandle` at `0x18000c0af`
- `KERNEL32!BasepGetExeArchType` at `0x18000c075`
- `KERNEL32!BasepGetExeArchType` at `0x18000c075`
- `KERNEL32!CreateFileW` at `0x18000c051`
- `KERNEL32!CreateFileW` at `0x18000c051`

## pseudocode

```c
_BOOL8 __fastcall GetSdbVersionForFile(LPCWSTR lpFileName, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  BOOL v5; // edi
  char *FileW; // rax
  char *v7; // rbx
  struct _UNICODE_STRING v9; // [rsp+50h] [rbp-18h] BYREF
  unsigned __int16 v10; // [rsp+88h] [rbp+20h] BYREF

  v9 = 0;
  v5 = 0;
  v10 = 332;
  RtlInitUnicodeString(&v9, a2);
  FileW = (char *)CreateFileW(lpFileName, 0x120089u, 5u, 0, 4u, 0x80u, 0);
  v7 = FileW;
  if ( FileW != (char *)-1LL )
    v5 = (int)BasepGetExeArchType(&v10, FileW, &v9) >= 0;
  *a3 = v10;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  return v5;
}

```

## disassembly

```asm
0x18000bfe8  mov     r11, rsp
0x18000bfeb  mov     [r11+8], rbx
0x18000bfef  mov     [r11+10h], rsi
0x18000bff3  mov     [r11+18h], r8
0x18000bff7  push    rdi
0x18000bff8  sub     rsp, 60h
0x18000bffc  mov     rsi, r8
0x18000bfff  mov     rbx, rcx
0x18000c002  xorps   xmm0, xmm0
0x18000c005  movups  xmmword ptr [rsp+68h+var_18.Length], xmm0
0x18000c00a  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFFh
0x18000c012  xor     edi, edi
0x18000c014  mov     [rsp+68h+var_24], edi
0x18000c018  mov     eax, 14Ch
0x18000c01d  mov     [r11+20h], ax
0x18000c022  lea     rcx, [r11-18h]; DestinationString
0x18000c026  call    cs:__imp_RtlInitUnicodeString
0x18000c02c  nop
0x18000c02d  mov     [rsp+68h+hTemplateFile], rdi; hTemplateFile
0x18000c032  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000c03a  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x18000c042  xor     r9d, r9d; lpSecurityAttributes
0x18000c045  mov     edx, 120089h; dwDesiredAccess
0x18000c04a  lea     r8d, [rdi+5]; dwShareMode
0x18000c04e  mov     rcx, rbx; lpFileName
0x18000c051  call    cs:__imp_CreateFileW
0x18000c057  mov     rbx, rax
0x18000c05a  mov     [rsp+68h+var_20], rax
0x18000c05f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c063  jz      short loc_18000C097
0x18000c065  lea     r8, [rsp+68h+var_18]
0x18000c06a  mov     rdx, rax
0x18000c06d  lea     rcx, [rsp+68h+arg_18]
0x18000c075  call    cs:__imp_BasepGetExeArchType
0x18000c07b  test    eax, eax
0x18000c07d  js      short loc_18000C097
0x18000c07f  mov     edi, 1
0x18000c084  jmp     short loc_18000C097
0x18000c086  mov     rsi, [rsp+68h+arg_10]
0x18000c08e  mov     edi, [rsp+68h+var_24]
0x18000c092  mov     rbx, [rsp+68h+var_20]
0x18000c097  movzx   ecx, [rsp+68h+arg_18]
0x18000c09f  mov     [rsi], cx
0x18000c0a2  lea     rcx, [rbx-1]
0x18000c0a6  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000c0aa  ja      short loc_18000C0B5
0x18000c0ac  mov     rcx, rbx; hObject
0x18000c0af  call    cs:__imp_CloseHandle
0x18000c0b5  mov     eax, edi
0x18000c0b7  mov     rbx, [rsp+68h+arg_0]
0x18000c0bc  mov     rsi, [rsp+68h+arg_8]
0x18000c0c1  add     rsp, 60h
0x18000c0c5  pop     rdi
0x18000c0c6  retn
0x1800166b2  push    rbp
0x1800166b4  sub     rsp, 40h
0x1800166b8  mov     rbp, rdx
0x1800166bb  mov     rax, [rcx]
0x1800166be  xor     ecx, ecx
0x1800166c0  cmp     dword ptr [rax], 0C0000006h
0x1800166c6  setz    cl
0x1800166c9  mov     [rbp+40h], ecx
0x1800166cc  mov     eax, [rbp+40h]
0x1800166cf  add     rsp, 40h
0x1800166d3  pop     rbp
0x1800166d4  retn
```
