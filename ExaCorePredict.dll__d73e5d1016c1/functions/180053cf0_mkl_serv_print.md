# mkl_serv_print

- ea: `0x180053cf0`
- end: `0x180053fa0`
- name: `mkl_serv_print`
- size: `688`
- prototype: ``
- caller_count: `82`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000d9c0`
- `0x18000db50`
- `0x18000dd00`
- `0x180040d00`
- `0x1800410f0`
- `0x180041480`
- `0x180041820`
- `0x180041c10`
- `0x180041ff0`
- `0x18004c100`
- `0x18004c240`
- `0x18004f8d0`
- `0x18004fa10`
- `0x18004fb50`
- `0x1800540e0`
- `0x18005449c`
- `0x180054750`
- `0x180054af0`
- `0x180054eac`
- `0x180055160`
- `0x180055500`
- `0x1800558f0`
- `0x180061390`
- `0x180061fcc`
- `0x1800640a0`
- `0x18006448c`
- `0x180066570`
- `0x180066cb2`
- `0x180067006`
- `0x180067260`
- `0x180071030`
- `0x180071a8c`
- `0x180073aa0`
- `0x180073e8c`
- `0x180075f20`
- `0x180076662`
- `0x1800769b6`
- `0x180076c10`
- `0x1800779d0`
- `0x180078620`
- `0x1800ba900`
- `0x1800d3920`
- `0x180125ef4`
- `0x18012bb00`
- `0x18012d290`
- `0x1801b7a04`
- `0x1801ea950`
- `0x18044a010`
- `0x18044a150`
- `0x18044a290`

## callees

- `0x18000de50`
- `0x18000e590`
- `0x18000e970`
- `0x180053cf0`
- `0x180055e50`
- `0x180056180`
- `0x1832ce3b0`
- `0x1832dbf80`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180053e2a`
- `KERNEL32!LocalFree` at `0x180053e2a`
- `KERNEL32!FormatMessageA` at `0x180053e04`
- `KERNEL32!FormatMessageA` at `0x180053e04`
- `KERNEL32!GetThreadLocale` at `0x180053d43`
- `KERNEL32!GetThreadLocale` at `0x180053d43`
- `KERNEL32!LoadLibraryA` at `0x180053d75`
- `KERNEL32!LoadLibraryA` at `0x180053d75`

## string_xrefs

- `0x180053d60`: `mkl_msg.dll`

## pseudocode

```c
int mkl_serv_print(__int64 a1, int a2, __int64 a3, ...)
{
  LCID ThreadLocale; // eax
  char *v5; // r13
  char *v6; // r12
  DWORD v7; // eax
  HLOCAL v8; // r8
  __int64 v9; // r15
  int v10; // r12d
  int v11; // r12d
  HLOCAL hMem; // [rsp+40h] [rbp-B8h] BYREF
  va_list v14; // [rsp+48h] [rbp-B0h]
  CHAR LibFileName[128]; // [rsp+50h] [rbp-A8h] BYREF
  va_list va; // [rsp+118h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( !a2 )
    goto LABEL_15;
  if ( dword_1836E2004 )
  {
    dword_1836E2004 = 0;
    ThreadLocale = GetThreadLocale();
    mkl_serv_sprintf_s((__int64)LibFileName, 128, (__int64)"%lu/%s", ThreadLocale, "mkl_msg.dll");
    lpSource = LoadLibraryA(LibFileName);
    if ( lpSource )
    {
      dword_1836E2008 = 0;
      v5 = (&off_1833EFA48)[2 * a2];
      goto LABEL_6;
    }
  }
  v5 = (&off_1833EFA48)[2 * a2];
  if ( !dword_1836E2008 )
  {
LABEL_6:
    v6 = 0;
    v7 = FormatMessageA(0x900u, lpSource, a2 + 0x80000000, 0x409u, (LPSTR)&hMem, 0x200u, 0);
    if ( !v7 )
      goto LABEL_10;
    v8 = hMem;
    if ( v7 > 1 )
    {
      v9 = v7 - 2;
      if ( *((_BYTE *)hMem + v9) == 13 && *((_BYTE *)hMem + v7 - 1) == 10 )
      {
        mkl_serv_strncpy_s(byte_1836E8FA0, 512, hMem, v9 + 1);
        v6 = byte_1836E8FA0;
        v8 = hMem;
        byte_1836E8FA0[v9] = 0;
      }
    }
    LocalFree(v8);
    if ( !v6 )
LABEL_10:
      v6 = v5;
    v5 = v6;
  }
  va_copy(v14, va);
  mkl_serv_vsprintf_s((__int64)byte_1836E91A0, 512, (__int64)v5, (__int64)va);
  v14 = 0;
  v10 = mkl_serv_strnlen_s(byte_1836E91A0, 512) - 1;
  if ( v10 > 512 )
  {
    mkl_serv_printf_s((__int64)"\nMKL INTERNAL ERROR: message buffer overflow.");
    mkl_serv_printf_s((__int64)"\n       Lenght: %d   Buffer size: %d\n", v10, 512);
    fflush_0(0);
  }
  mkl_serv_printf_s((__int64)"%s", byte_1836E91A0);
  fflush_0(0);
LABEL_15:
  v11 = mkl_serv_strnlen_s("\n", 512) - 1;
  if ( v11 > 512 )
  {
    mkl_serv_printf_s((__int64)"\nMKL INTERNAL ERROR: message buffer overflow.");
    mkl_serv_printf_s((__int64)"\n       Lenght: %d   Buffer size: %d\n", v11, 512);
    fflush_0(0);
  }
  mkl_serv_printf_s((__int64)"%s", "\n");
  return fflush_0(0);
}

```

## disassembly

```asm
0x180053cf0  push    r12
0x180053cf2  push    r13
0x180053cf4  push    r14
0x180053cf6  push    r15
0x180053cf8  sub     rsp, 0D8h
0x180053cff  mov     r15d, edx
0x180053d02  mov     [rsp+0F8h+arg_10], r8d
0x180053d0a  mov     r14d, ecx
0x180053d0d  mov     [rsp+0F8h+arg_18], r9
0x180053d15  mov     rax, cs:__security_cookie
0x180053d1c  xor     rax, rsp
0x180053d1f  mov     [rsp+0F8h+var_28], rax
0x180053d27  test    r15d, r15d
0x180053d2a  jz      loc_180053ED0
0x180053d30  cmp     cs:dword_1836E2004, 0
0x180053d37  jz      short loc_180053DA9
0x180053d39  mov     cs:dword_1836E2004, 0
0x180053d43  call    cs:__imp_GetThreadLocale
0x180053d49  mov     r9d, eax
0x180053d4c  mov     r10, rsp
0x180053d4f  lea     rcx, [rsp+0F8h+LibFileName]
0x180053d54  mov     edx, 80h
0x180053d59  lea     r8, aLuS; "%lu/%s"
0x180053d60  lea     rax, aMklMsgDll; "mkl_msg.dll"
0x180053d67  mov     [r10+20h], rax
0x180053d6b  call    mkl_serv_sprintf_s
0x180053d70  lea     rcx, [rsp+0F8h+LibFileName]; lpLibFileName
0x180053d75  call    cs:__imp_LoadLibraryA
0x180053d7b  mov     cs:lpSource, rax
0x180053d82  test    rax, rax
0x180053d85  jz      short loc_180053DA9
0x180053d87  movsxd  rdx, r15d
0x180053d8a  lea     rax, cs:180000000h
0x180053d91  shl     rdx, 4
0x180053d95  mov     cs:dword_1836E2008, 0
0x180053d9f  mov     r13, ds:rva off_1833EFA48[rax+rdx]; "\n" ...
0x180053da7  jmp     short loc_180053DC9
0x180053da9  mov     ecx, cs:dword_1836E2008
0x180053daf  movsxd  rdx, r15d
0x180053db2  lea     rax, cs:180000000h
0x180053db9  shl     rdx, 4
0x180053dbd  test    ecx, ecx
0x180053dbf  mov     r13, ds:rva off_1833EFA48[rax+rdx]; "\n" ...
0x180053dc7  jnz     short loc_180053E3B
0x180053dc9  mov     r10, rsp
0x180053dcc  add     r15d, 80000000h
0x180053dd3  mov     rdx, cs:lpSource; lpSource
0x180053dda  mov     ecx, 900h; dwFlags
0x180053ddf  mov     r8d, r15d; dwMessageId
0x180053de2  mov     r9d, 409h; dwLanguageId
0x180053de8  xor     r12d, r12d
0x180053deb  lea     rax, [rsp+0F8h+hMem]
0x180053df0  mov     [r10+20h], rax
0x180053df4  mov     dword ptr [r10+28h], 200h
0x180053dfc  mov     qword ptr [r10+30h], 0
0x180053e04  call    cs:__imp_FormatMessageA
0x180053e0a  test    eax, eax
0x180053e0c  jz      short loc_180053E35
0x180053e0e  mov     r8, [rsp+0F8h+hMem]
0x180053e13  cmp     eax, 1
0x180053e16  jbe     short loc_180053E27
0x180053e18  lea     r15d, [rax-2]
0x180053e1c  cmp     byte ptr [r8+r15], 0Dh
0x180053e21  jz      loc_180053F56
0x180053e27  mov     rcx, r8; hMem
0x180053e2a  call    cs:__imp_LocalFree
0x180053e30  test    r12, r12
0x180053e33  jnz     short loc_180053E38
0x180053e35  mov     r12, r13
0x180053e38  mov     r13, r12
0x180053e3b  lea     rax, [rsp+0F8h+arg_18]
0x180053e43  mov     [rsp+0F8h+var_B0], rax
0x180053e48  lea     rcx, byte_1836E91A0
0x180053e4f  mov     edx, 200h
0x180053e54  mov     r8, r13
0x180053e57  mov     r9, [rsp+0F8h+var_B0]
0x180053e5c  call    mkl_serv_vsprintf_s
0x180053e61  lea     rcx, byte_1836E91A0
0x180053e68  mov     edx, 200h
0x180053e6d  mov     [rsp+0F8h+var_B0], 0
0x180053e76  call    mkl_serv_strnlen_s
0x180053e7b  dec     rax
0x180053e7e  mov     r12d, eax
0x180053e81  cmp     r12d, 200h
0x180053e88  jle     short loc_180053EB2
0x180053e8a  lea     rcx, aMklInternalErr; "\nMKL INTERNAL ERROR: message buffer ov"...
0x180053e91  call    mkl_serv_printf_s
0x180053e96  lea     rcx, aLenghtDBufferS; "\n       Lenght: %d   Buffer size: %d\n"
0x180053e9d  mov     edx, r12d
0x180053ea0  mov     r8d, 200h
0x180053ea6  call    mkl_serv_printf_s
0x180053eab  xor     ecx, ecx; Stream
0x180053ead  call    fflush_0
0x180053eb2  cmp     r14d, 1
0x180053eb6  lea     rcx, aS; "%s"
0x180053ebd  lea     rdx, byte_1836E91A0
0x180053ec4  call    mkl_serv_printf_s
0x180053ec9  xor     ecx, ecx; Stream
0x180053ecb  call    fflush_0
0x180053ed0  lea     rcx, asc_1833F52A0; "\n"
0x180053ed7  mov     edx, 200h
0x180053edc  call    mkl_serv_strnlen_s
0x180053ee1  dec     rax
0x180053ee4  mov     r12d, eax
0x180053ee7  cmp     r12d, 200h
0x180053eee  jle     short loc_180053F18
0x180053ef0  lea     rcx, aMklInternalErr; "\nMKL INTERNAL ERROR: message buffer ov"...
0x180053ef7  call    mkl_serv_printf_s
0x180053efc  lea     rcx, aLenghtDBufferS; "\n       Lenght: %d   Buffer size: %d\n"
0x180053f03  mov     edx, r12d
0x180053f06  mov     r8d, 200h
0x180053f0c  call    mkl_serv_printf_s
0x180053f11  xor     ecx, ecx; Stream
0x180053f13  call    fflush_0
0x180053f18  cmp     r14d, 1
0x180053f1c  lea     rcx, aS; "%s"
0x180053f23  lea     rdx, asc_1833F52A0; "\n"
0x180053f2a  call    mkl_serv_printf_s
0x180053f2f  xor     ecx, ecx; Stream
0x180053f31  call    fflush_0
0x180053f36  mov     rcx, [rsp+0F8h+var_28]
0x180053f3e  xor     rcx, rsp; StackCookie
0x180053f41  call    __security_check_cookie
0x180053f46  add     rsp, 0D8h
0x180053f4d  pop     r15
0x180053f4f  pop     r14
0x180053f51  pop     r13
0x180053f53  pop     r12
0x180053f55  retn
0x180053f56  dec     eax
0x180053f58  cmp     byte ptr [rax+r8], 0Ah
0x180053f5d  jnz     loc_180053E27
0x180053f63  lea     rcx, byte_1836E8FA0
0x180053f6a  lea     r9, [r15+1]
0x180053f6e  mov     edx, 200h
0x180053f73  call    mkl_serv_strncpy_s
0x180053f78  lea     rax, cs:180000000h
0x180053f7f  lea     r12, byte_1836E8FA0
0x180053f86  mov     r8, [rsp+0F8h+hMem]
0x180053f8b  mov     rva byte_1836E8FA0[rax+r15], 0
0x180053f94  jmp     loc_180053E27
```
