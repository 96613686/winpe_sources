# XgcJoblessPrinting::XgcJoblessPrinting(ulong,IWritePrinterCallback *)

- ea: `0x180015de0`
- end: `0x180015e6b`
- name: `??0XgcJoblessPrinting@@QEAA@KPEAUIWritePrinterCallback@@@Z`
- size: `139`
- prototype: `XgcJoblessPrinting *__fastcall(XgcJoblessPrinting *__hidden this, unsigned int, struct IWritePrinterCallback *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f560`

## callees

- `0x180015de0`
- `0x180037278`
- `0x18004a010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180015e0d`
- `KERNEL32!LoadLibraryW` at `0x180015e0d`
- `KERNEL32!GetProcAddress` at `0x180015e22`
- `KERNEL32!GetProcAddress` at `0x180015e22`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
XgcJoblessPrinting *__fastcall XgcJoblessPrinting::XgcJoblessPrinting(
        XgcJoblessPrinting *this,
        int a2,
        struct IWritePrinterCallback *a3)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v8; // eax
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  _DWORD v13[2]; // [rsp+20h] [rbp-18h] BYREF
  struct IWritePrinterCallback *v14; // [rsp+28h] [rbp-10h]

  *(_QWORD *)this = &XgcJoblessPrinting::`vftable';
  LibraryW = LoadLibraryW(L"winspool.drv");
  *((_QWORD *)this + 1) = LibraryW;
  *((_DWORD *)this + 4) = a2;
  ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x101);
  *((_QWORD *)this + 3) = ProcAddress;
  v13[1] = 0;
  v13[0] = *((_DWORD *)this + 4);
  v14 = a3;
  v8 = ((__int64 (__fastcall *)(_QWORD, _DWORD *))ProcAddress)(0, v13);
  if ( v8 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v8, v9, v10, v11);
  return this;
}

```

## disassembly

```asm
0x180015de0  mov     [rsp+arg_8], rbx
0x180015de5  mov     [rsp+arg_10], rsi
0x180015dea  mov     [rsp+arg_0], rcx
0x180015def  push    rdi
0x180015df0  sub     rsp, 30h
0x180015df4  mov     rdi, r8
0x180015df7  mov     ebx, edx
0x180015df9  mov     rsi, rcx
0x180015dfc  lea     rax, ??_7XgcJoblessPrinting@@6B@; const XgcJoblessPrinting::`vftable'
0x180015e03  mov     [rcx], rax
0x180015e06  lea     rcx, LibFileName; "winspool.drv"
0x180015e0d  call    cs:__imp_LoadLibraryW
0x180015e13  mov     [rsi+8], rax
0x180015e17  mov     [rsi+10h], ebx
0x180015e1a  mov     edx, 101h; lpProcName
0x180015e1f  mov     rcx, rax; hModule
0x180015e22  call    cs:__imp_GetProcAddress
0x180015e28  mov     [rsi+18h], rax
0x180015e2c  mov     [rsp+38h+var_14], 0
0x180015e34  mov     ecx, [rsi+10h]
0x180015e37  mov     [rsp+38h+var_18], ecx
0x180015e3b  mov     [rsp+38h+var_10], rdi
0x180015e40  lea     rdx, [rsp+38h+var_18]
0x180015e45  xor     ecx, ecx
0x180015e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e4c  test    eax, eax
0x180015e4e  jns     short loc_180015E58
0x180015e50  mov     ecx, eax; this
0x180015e52  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180015e58  mov     rax, rsi
0x180015e5b  mov     rbx, [rsp+38h+arg_8]
0x180015e60  mov     rsi, [rsp+38h+arg_10]
0x180015e65  add     rsp, 30h
0x180015e69  pop     rdi
0x180015e6a  retn
```
