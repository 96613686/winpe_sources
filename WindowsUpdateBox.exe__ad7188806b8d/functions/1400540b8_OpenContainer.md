# OpenContainer

- ea: `0x1400540b8`
- end: `0x14005424f`
- name: `OpenContainer`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14005394c`

## callees

- `0x1400540b8`
- `0x140080d70`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140054241`
- `KERNEL32!CloseHandle` at `0x140054241`
- `KERNEL32!GetLastError` at `0x140054127`
- `KERNEL32!GetLastError` at `0x14005418b`
- `KERNEL32!GetLastError` at `0x140054127`
- `KERNEL32!GetLastError` at `0x14005418b`
- `KERNEL32!ReadFile` at `0x14005417b`
- `KERNEL32!ReadFile` at `0x14005417b`
- `KERNEL32!CreateFileW` at `0x140054112`
- `KERNEL32!CreateFileW` at `0x140054112`

## pseudocode

```c
__int64 __fastcall OpenContainer(const WCHAR *a1, int a2, _OWORD *a3, _DWORD *a4, _QWORD *a5)
{
  signed int v5; // ebx
  HANDLE FileW; // r14
  signed int v10; // eax
  signed int LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-40h] BYREF
  _OWORD Buffer[2]; // [rsp+48h] [rbp-38h] BYREF
  int v15; // [rsp+68h] [rbp-18h]

  v5 = 0;
  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    v15 = 0;
    NumberOfBytesRead = 0;
    memset(Buffer, 0, sizeof(Buffer));
    if ( !ReadFile(FileW, Buffer, 0x24u, &NumberOfBytesRead, 0) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
      goto LABEL_25;
    }
    if ( NumberOfBytesRead != 36 )
    {
      v5 = -2147024866;
LABEL_25:
      CloseHandle(FileW);
      return (unsigned int)v5;
    }
    if ( (a2 == LODWORD(Buffer[0]) || !a2 && (unsigned int)(LODWORD(Buffer[0]) + 1329266688) <= 2)
      && (!a3 || *a3 == *(_OWORD *)((char *)Buffer + 4)) )
    {
      if ( !a4 )
      {
LABEL_21:
        *a5 = FileW;
        return (unsigned int)v5;
      }
      if ( *a4 == -1 )
      {
        *a4 = DWORD1(Buffer[1]);
        goto LABEL_21;
      }
      if ( *a4 == DWORD1(Buffer[1]) )
        goto LABEL_21;
    }
    v5 = -2147024883;
    goto LABEL_25;
  }
  v10 = GetLastError();
  v5 = v10;
  if ( v10 > 0 )
    v5 = (unsigned __int16)v10 | 0x80070000;
  if ( v5 >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400540b8  mov     [rsp-28h+arg_8], rbx
0x1400540bd  mov     [rsp-28h+arg_10], rsi
0x1400540c2  push    rbp
0x1400540c3  push    rdi
0x1400540c4  push    r12
0x1400540c6  push    r14
0x1400540c8  push    r15
0x1400540ca  mov     rbp, rsp
0x1400540cd  sub     rsp, 80h
0x1400540d4  mov     rax, cs:__security_cookie
0x1400540db  xor     rax, rsp
0x1400540de  mov     [rbp+var_10], rax
0x1400540e2  mov     r12, [rbp+arg_20]
0x1400540e6  xor     ebx, ebx
0x1400540e8  mov     rdi, r9
0x1400540eb  mov     [rsp+80h+hTemplateFile], rbx; hTemplateFile
0x1400540f0  mov     rsi, r8
0x1400540f3  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400540fb  mov     r15d, edx
0x1400540fe  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x140054106  lea     r8d, [rbx+7]; dwShareMode
0x14005410a  xor     r9d, r9d; lpSecurityAttributes
0x14005410d  mov     edx, 80000000h; dwDesiredAccess
0x140054112  call    cs:__imp_CreateFileW
0x140054119  nop     dword ptr [rax+rax+00h]
0x14005411e  mov     r14, rax
0x140054121  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140054125  jnz     short loc_140054154
0x140054127  call    cs:__imp_GetLastError
0x14005412e  nop     dword ptr [rax+rax+00h]
0x140054133  mov     ebx, eax
0x140054135  test    eax, eax
0x140054137  jle     short loc_140054142
0x140054139  movzx   ebx, ax
0x14005413c  or      ebx, 80070000h
0x140054142  test    ebx, ebx
0x140054144  js      loc_140054209
0x14005414a  mov     ebx, 80004005h
0x14005414f  jmp     loc_140054209
0x140054154  xor     eax, eax
0x140054156  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x14005415a  xorps   xmm0, xmm0
0x14005415d  mov     [rbp+var_18], eax
0x140054160  lea     rdx, [rbp+Buffer]; lpBuffer
0x140054164  mov     [rbp+NumberOfBytesRead], eax
0x140054167  mov     rcx, r14; hFile
0x14005416a  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; lpOverlapped
0x14005416f  lea     r8d, [rax+24h]; nNumberOfBytesToRead
0x140054173  movups  [rbp+Buffer], xmm0
0x140054177  movups  [rbp+var_28], xmm0
0x14005417b  call    cs:__imp_ReadFile
0x140054182  nop     dword ptr [rax+rax+00h]
0x140054187  test    eax, eax
0x140054189  jnz     short loc_1400541B8
0x14005418b  call    cs:__imp_GetLastError
0x140054192  nop     dword ptr [rax+rax+00h]
0x140054197  mov     ebx, eax
0x140054199  test    eax, eax
0x14005419b  jle     short loc_1400541A6
0x14005419d  movzx   ebx, ax
0x1400541a0  or      ebx, 80070000h
0x1400541a6  test    ebx, ebx
0x1400541a8  js      loc_14005423E
0x1400541ae  mov     ebx, 80004005h
0x1400541b3  jmp     loc_14005423E
0x1400541b8  cmp     [rbp+NumberOfBytesRead], 24h ; '$'
0x1400541bc  jz      short loc_1400541C5
0x1400541be  mov     ebx, 8007001Eh
0x1400541c3  jmp     short loc_14005423E
0x1400541c5  mov     eax, dword ptr [rbp+Buffer]
0x1400541c8  cmp     r15d, eax
0x1400541cb  jz      short loc_1400541DC
0x1400541cd  test    r15d, r15d
0x1400541d0  jnz     short loc_140054239
0x1400541d2  add     eax, 4F3B0000h
0x1400541d7  cmp     eax, 2
0x1400541da  ja      short loc_140054239
0x1400541dc  test    rsi, rsi
0x1400541df  jz      short loc_1400541F4
0x1400541e1  mov     rax, [rsi]
0x1400541e4  cmp     rax, qword ptr [rbp+Buffer+4]
0x1400541e8  jnz     short loc_140054239
0x1400541ea  mov     rax, [rsi+8]
0x1400541ee  cmp     rax, qword ptr [rbp+Buffer+0Ch]
0x1400541f2  jnz     short loc_140054239
0x1400541f4  test    rdi, rdi
0x1400541f7  jz      short loc_140054205
0x1400541f9  mov     eax, [rdi]
0x1400541fb  cmp     eax, 0FFFFFFFFh
0x1400541fe  jnz     short loc_140054234
0x140054200  mov     eax, dword ptr [rbp+var_28+4]
0x140054203  mov     [rdi], eax
0x140054205  mov     [r12], r14
0x140054209  mov     eax, ebx
0x14005420b  mov     rcx, [rbp+var_10]
0x14005420f  xor     rcx, rsp; StackCookie
0x140054212  call    __security_check_cookie
0x140054217  lea     r11, [rsp+80h+var_s0]
0x14005421f  mov     rbx, [r11+38h]
0x140054223  mov     rsi, [r11+40h]
0x140054227  mov     rsp, r11
0x14005422a  pop     r15
0x14005422c  pop     r14
0x14005422e  pop     r12
0x140054230  pop     rdi
0x140054231  pop     rbp
0x140054232  retn
0x140054234  cmp     eax, dword ptr [rbp+var_28+4]
0x140054237  jz      short loc_140054205
0x140054239  mov     ebx, 8007000Dh
0x14005423e  mov     rcx, r14; hObject
0x140054241  call    cs:__imp_CloseHandle
0x140054248  nop     dword ptr [rax+rax+00h]
0x14005424d  jmp     short loc_140054209
```
