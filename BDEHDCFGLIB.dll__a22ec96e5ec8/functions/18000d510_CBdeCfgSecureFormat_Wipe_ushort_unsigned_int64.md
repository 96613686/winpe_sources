# CBdeCfgSecureFormat::Wipe(ushort *,unsigned __int64)

- ea: `0x18000d510`
- end: `0x18000d777`
- name: `?Wipe@CBdeCfgSecureFormat@@AEAAJPEAG_K@Z`
- size: `615`
- prototype: `__int64 __fastcall(CBdeCfgSecureFormat *this, unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000d084`
- `0x18000d29c`

## callees

- `0x180008b00`
- `0x18000d510`
- `0x18000e300`
- `0x18000eb40`
- `0x18001358e`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18000d664`
- `KERNEL32!WriteFile` at `0x18000d664`
- `KERNEL32!VirtualFree` at `0x18000d755`
- `KERNEL32!VirtualFree` at `0x18001423d`
- `KERNEL32!VirtualFree` at `0x18000d755`
- `KERNEL32!VirtualFree` at `0x18001423d`
- `KERNEL32!GetLastError` at `0x18000d5c1`
- `KERNEL32!GetLastError` at `0x18000d70a`
- `KERNEL32!GetLastError` at `0x18000d5c1`
- `KERNEL32!GetLastError` at `0x18000d70a`
- `KERNEL32!CreateFileW` at `0x18000d5ad`
- `KERNEL32!CreateFileW` at `0x18000d5ad`
- `KERNEL32!CloseHandle` at `0x18000d73f`
- `KERNEL32!CloseHandle` at `0x18001421e`
- `KERNEL32!CloseHandle` at `0x18000d73f`
- `KERNEL32!CloseHandle` at `0x18001421e`
- `KERNEL32!VirtualAlloc` at `0x18000d55b`
- `KERNEL32!VirtualAlloc` at `0x18000d55b`

## pseudocode

```c
__int64 __fastcall CBdeCfgSecureFormat::Wipe(CBdeCfgSecureFormat *this, unsigned __int16 *a2, __int64 a3)
{
  __int64 v6; // rdi
  void *v7; // rax
  void *v8; // r12
  unsigned int v9; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  __int64 v12; // rdx
  int v13; // eax
  DWORD v14; // edx
  __int64 v15; // rsi
  unsigned __int64 v16; // r14
  DWORD v17; // r8d
  double v18; // xmm0_8
  double v19; // xmm1_8
  int v20; // eax
  signed int v21; // eax
  DWORD NumberOfBytesWritten; // [rsp+A8h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  v6 = -1;
  v7 = VirtualAlloc(0, 0x500000u, 0x3000u, 4u);
  v8 = v7;
  if ( !v7 )
  {
    v9 = -2147024882;
    goto LABEL_35;
  }
  memset_0(v7, 0, 0x500000u);
  FileW = CreateFileW(a2, 0xC0000000, 3u, 0, 3u, 0x20000000u, 0);
  v6 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = (unsigned int)LastError;
    goto LABEL_7;
  }
  if ( (int)BdeCfgpDeviceIoControl(FileW, 0x90018u) < 0 )
    BdeCfgLogWarning(0x80A00037);
  v13 = BdeCfgpDeviceIoControl((void *)v6, 0x90020u);
  v9 = v13;
  if ( v13 < 0 )
  {
    v12 = (unsigned int)v13;
LABEL_7:
    BdeCfgLogError(3, v12);
    v9 = -1063256048;
    goto LABEL_35;
  }
  v14 = a3;
  v15 = 0;
  *((_DWORD *)this + 3) = 0;
  v16 = a3;
  while ( !*((_BYTE *)this + 16) && v16 )
  {
    v17 = 5242880;
    if ( v16 < 0x500000 )
      v17 = v14;
    if ( !WriteFile((HANDLE)v6, v8, v17, &NumberOfBytesWritten, 0) || !NumberOfBytesWritten )
    {
      v21 = GetLastError();
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      v12 = (unsigned int)v21;
      goto LABEL_7;
    }
    v16 -= NumberOfBytesWritten;
    v14 = v16;
    v15 += NumberOfBytesWritten;
    if ( v15 < 0 )
      v18 = (double)(int)(v15 & 1 | ((unsigned __int64)v15 >> 1))
          + (double)(int)(v15 & 1 | ((unsigned __int64)v15 >> 1));
    else
      v18 = (double)(int)v15;
    if ( a3 < 0 )
      v19 = (double)(int)(a3 & 1 | ((unsigned __int64)a3 >> 1)) + (double)(int)(a3 & 1 | ((unsigned __int64)a3 >> 1));
    else
      v19 = (double)(int)a3;
    v20 = (int)(v18 / v19 * 100.0);
    if ( v20 )
    {
      if ( v20 == 100 )
        v20 = 99;
    }
    else
    {
      v20 = 1;
    }
    *((_DWORD *)this + 3) = v20;
  }
  if ( *((_BYTE *)this + 16) )
    v9 = -1063256047;
LABEL_35:
  if ( v6 != -1 )
    CloseHandle((HANDLE)v6);
  if ( v8 )
    VirtualFree(v8, 0, 0x8000u);
  return v9;
}

```

## disassembly

```asm
0x18000d510  mov     rax, rsp
0x18000d513  mov     [rax+8], rbx
0x18000d517  mov     [rax+10h], rsi
0x18000d51b  push    rdi
0x18000d51c  push    r12
0x18000d51e  push    r13
0x18000d520  push    r14
0x18000d522  push    r15
0x18000d524  sub     rsp, 60h
0x18000d528  mov     r15, r8
0x18000d52b  mov     rbx, rdx
0x18000d52e  mov     r13, rcx
0x18000d531  mov     qword ptr [rax-40h], 0
0x18000d539  mov     dword ptr [rax+20h], 0
0x18000d540  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000d544  mov     [rax-48h], rdi
0x18000d548  mov     esi, 500000h
0x18000d54d  lea     r9d, [rdi+5]; flProtect
0x18000d551  mov     r8d, 3000h; flAllocationType
0x18000d557  mov     edx, esi; dwSize
0x18000d559  xor     ecx, ecx; lpAddress
0x18000d55b  call    cs:__imp_VirtualAlloc
0x18000d561  mov     r12, rax
0x18000d564  mov     [rsp+88h+var_40], rax
0x18000d569  test    rax, rax
0x18000d56c  jnz     short loc_18000D578
0x18000d56e  mov     ebx, 8007000Eh
0x18000d573  jmp     loc_18000D736
0x18000d578  mov     r8, rsi; Size
0x18000d57b  xor     edx, edx; Val
0x18000d57d  mov     rcx, r12; void *
0x18000d580  call    memset_0
0x18000d585  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18000d58e  mov     [rsp+88h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x18000d596  mov     esi, 3
0x18000d59b  mov     [rsp+88h+dwCreationDisposition], esi; dwCreationDisposition
0x18000d59f  xor     r9d, r9d; lpSecurityAttributes
0x18000d5a2  mov     r8d, esi; dwShareMode
0x18000d5a5  mov     edx, 0C0000000h; dwDesiredAccess
0x18000d5aa  mov     rcx, rbx; lpFileName
0x18000d5ad  call    cs:__imp_CreateFileW
0x18000d5b3  mov     rdi, rax
0x18000d5b6  mov     [rsp+88h+var_48], rax
0x18000d5bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d5bf  jnz     short loc_18000D5E6
0x18000d5c1  call    cs:__imp_GetLastError
0x18000d5c7  test    eax, eax
0x18000d5c9  jle     short loc_18000D5D3
0x18000d5cb  movzx   eax, ax
0x18000d5ce  or      eax, 80070000h
0x18000d5d3  mov     edx, eax
0x18000d5d5  mov     ecx, esi
0x18000d5d7  call    BdeCfgLogError
0x18000d5dc  mov     ebx, 0C0A00010h
0x18000d5e1  jmp     loc_18000D736
0x18000d5e6  mov     edx, 90018h; unsigned int
0x18000d5eb  mov     rcx, rdi; void *
0x18000d5ee  call    ?BdeCfgpDeviceIoControl@@YAJPEAXK@Z; BdeCfgpDeviceIoControl(void *,ulong)
0x18000d5f3  test    eax, eax
0x18000d5f5  jns     short loc_18000D601
0x18000d5f7  mov     ecx, 80A00037h; dwMessageId
0x18000d5fc  call    BdeCfgLogWarning
0x18000d601  mov     edx, 90020h; unsigned int
0x18000d606  mov     rcx, rdi; void *
0x18000d609  call    ?BdeCfgpDeviceIoControl@@YAJPEAXK@Z; BdeCfgpDeviceIoControl(void *,ulong)
0x18000d60e  mov     ebx, eax
0x18000d610  test    eax, eax
0x18000d612  jns     short loc_18000D618
0x18000d614  mov     edx, eax
0x18000d616  jmp     short loc_18000D5D5
0x18000d618  mov     edx, r15d
0x18000d61b  xor     esi, esi
0x18000d61d  mov     [rsp+88h+var_38], rsi
0x18000d622  mov     [r13+0Ch], esi
0x18000d626  mov     r14, r15
0x18000d629  mov     al, [r13+10h]
0x18000d62d  test    al, al
0x18000d62f  jnz     loc_18000D728
0x18000d635  test    r14, r14
0x18000d638  jz      loc_18000D728
0x18000d63e  mov     eax, 500000h
0x18000d643  mov     r8d, eax
0x18000d646  cmp     r14, rax
0x18000d649  cmovb   r8d, edx; nNumberOfBytesToWrite
0x18000d64d  mov     qword ptr [rsp+88h+dwCreationDisposition], 0; lpOverlapped
0x18000d656  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000d65e  mov     rdx, r12; lpBuffer
0x18000d661  mov     rcx, rdi; hFile
0x18000d664  call    cs:__imp_WriteFile
0x18000d66a  test    eax, eax
0x18000d66c  jz      loc_18000D70A
0x18000d672  mov     eax, [rsp+88h+NumberOfBytesWritten]
0x18000d679  test    eax, eax
0x18000d67b  jz      loc_18000D70A
0x18000d681  sub     r14, rax
0x18000d684  mov     rdx, r14
0x18000d687  add     rsi, rax
0x18000d68a  mov     [rsp+88h+var_38], rsi
0x18000d68f  xorps   xmm0, xmm0
0x18000d692  js      short loc_18000D69B
0x18000d694  cvtsi2sd xmm0, rsi
0x18000d699  jmp     short loc_18000D6B3
0x18000d69b  mov     rcx, rsi
0x18000d69e  shr     rcx, 1
0x18000d6a1  mov     rax, rsi
0x18000d6a4  and     eax, 1
0x18000d6a7  or      rcx, rax
0x18000d6aa  cvtsi2sd xmm0, rcx
0x18000d6af  addsd   xmm0, xmm0
0x18000d6b3  xorps   xmm1, xmm1
0x18000d6b6  test    r15, r15
0x18000d6b9  js      short loc_18000D6C2
0x18000d6bb  cvtsi2sd xmm1, r15
0x18000d6c0  jmp     short loc_18000D6DA
0x18000d6c2  mov     rcx, r15
0x18000d6c5  shr     rcx, 1
0x18000d6c8  mov     rax, r15
0x18000d6cb  and     eax, 1
0x18000d6ce  or      rcx, rax
0x18000d6d1  cvtsi2sd xmm1, rcx
0x18000d6d6  addsd   xmm1, xmm1
0x18000d6da  divsd   xmm0, xmm1
0x18000d6de  mulsd   xmm0, cs:__real@4059000000000000
0x18000d6e6  cvttsd2si rax, xmm0
0x18000d6eb  test    eax, eax
0x18000d6ed  jnz     short loc_18000D6F6
0x18000d6ef  mov     eax, 1
0x18000d6f4  jmp     short loc_18000D701
0x18000d6f6  mov     ecx, 63h ; 'c'
0x18000d6fb  cmp     eax, 64h ; 'd'
0x18000d6fe  cmovz   eax, ecx
0x18000d701  mov     [r13+0Ch], eax
0x18000d705  jmp     loc_18000D629
0x18000d70a  call    cs:__imp_GetLastError
0x18000d710  test    eax, eax
0x18000d712  jle     short loc_18000D71C
0x18000d714  movzx   eax, ax
0x18000d717  or      eax, 80070000h
0x18000d71c  mov     edx, eax
0x18000d71e  mov     ecx, 3
0x18000d723  jmp     loc_18000D5D7
0x18000d728  mov     al, [r13+10h]
0x18000d72c  mov     ecx, 0C0A00011h
0x18000d731  test    al, al
0x18000d733  cmovnz  ebx, ecx
0x18000d736  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000d73a  jz      short loc_18000D745
0x18000d73c  mov     rcx, rdi; hObject
0x18000d73f  call    cs:__imp_CloseHandle
0x18000d745  test    r12, r12
0x18000d748  jz      short loc_18000D75B
0x18000d74a  xor     edx, edx; dwSize
0x18000d74c  mov     r8d, 8000h; dwFreeType
0x18000d752  mov     rcx, r12; lpAddress
0x18000d755  call    cs:__imp_VirtualFree
0x18000d75b  mov     eax, ebx
0x18000d75d  lea     r11, [rsp+88h+var_28]
0x18000d762  mov     rbx, [r11+30h]
0x18000d766  mov     rsi, [r11+38h]
0x18000d76a  mov     rsp, r11
0x18000d76d  pop     r15
0x18000d76f  pop     r14
0x18000d771  pop     r13
0x18000d773  pop     r12
0x18000d775  pop     rdi
0x18000d776  retn
0x18001420b  push    rbp
0x18001420d  sub     rsp, 40h
0x180014211  mov     rbp, rdx
0x180014214  mov     rcx, [rbp+40h]; hObject
0x180014218  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001421c  jz      short loc_18001422C
0x18001421e  call    cs:__imp_CloseHandle
0x180014224  mov     qword ptr [rbp+40h], 0FFFFFFFFFFFFFFFFh
0x18001422c  mov     rcx, [rbp+48h]; lpAddress
0x180014230  test    rcx, rcx
0x180014233  jz      short loc_180014244
0x180014235  xor     edx, edx; dwSize
0x180014237  mov     r8d, 8000h; dwFreeType
0x18001423d  call    cs:__imp_VirtualFree
0x180014243  nop
0x180014244  add     rsp, 40h
0x180014248  pop     rbp
0x180014249  retn
```
