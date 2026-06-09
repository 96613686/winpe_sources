# CKernelReport::~CKernelReport(void)

- ea: `0x140034ed8`
- end: `0x14003500d`
- name: `??1CKernelReport@@QEAA@XZ`
- size: `309`
- prototype: `void __fastcall(CKernelReport *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14003494c`
- `0x14005c10c`

## callees

- `0x140002728`
- `0x140034d9c`
- `0x140034ed8`
- `0x14004655c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140034f3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140034ffd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140034f3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140034ffd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140034f51`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140034f51`

## string_xrefs

- `0x140034efb`: `Reporting not cancelled during destructor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CKernelReport::~CKernelReport(CKernelReport *this)
{
  void *v2; // rcx
  CPluginList *v3; // rcx
  char *v4; // rcx
  CPluginList *v5; // rcx
  __int64 **v6; // rsi
  __int64 *v7; // rdi
  __int64 *v8; // rdx
  __int64 v9; // rax
  __int64 *v10; // rcx
  void *v11; // rcx
  wil::details *v12; // [rsp+20h] [rbp-38h]
  const char *v13; // [rsp+30h] [rbp-28h]
  wil::details::in1diag4 *retaddr; // [rsp+58h] [rbp+0h]

  if ( (unsigned __int64)(*((_QWORD *)this + 81) + 1LL) > 1 )
  {
    LODWORD(v12) = 0x80000000;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::~CKernelReport",
      v12,
      (int)"Reporting not cancelled during destructor",
      v13);
    v2 = (void *)*((_QWORD *)this + 81);
    *((_QWORD *)this + 81) = 0;
    if ( (unsigned __int64)v2 + 1 > 1 )
      CloseHandle(v2);
  }
  if ( *((_WORD *)this + 64) )
    DeleteFileW((LPCWSTR)this + 64);
  v3 = (CPluginList *)*((_QWORD *)this + 85);
  *((_QWORD *)this + 85) = 0;
  if ( v3 )
    WerPluginsDestroy(v3);
  v4 = (char *)*((_QWORD *)this + 86);
  if ( v4 != (char *)this + 704 )
    operator delete(v4, (const struct std::nothrow_t *)&std::nothrow);
  v5 = (CPluginList *)*((_QWORD *)this + 85);
  if ( v5 )
    WerPluginsDestroy(v5);
  v6 = (__int64 **)((char *)this + 656);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == (__int64 *)v6 )
      break;
    v8 = (__int64 *)v7[1];
    v9 = *v7;
    *v8 = *v7;
    *(_QWORD *)(v9 + 8) = v8;
    v10 = (__int64 *)v7[2];
    if ( v10 != v7 + 4 )
      operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
    operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
  }
  *((_QWORD *)this + 84) = 0;
  v11 = (void *)*((_QWORD *)this + 81);
  if ( (unsigned __int64)v11 + 1 > 1 )
    CloseHandle(v11);
}

```

## disassembly

```asm
0x140034ed8  push    rbx
0x140034eda  push    rbp
0x140034edb  push    rsi
0x140034edc  push    rdi
0x140034edd  sub     rsp, 38h
0x140034ee1  mov     rbx, rcx
0x140034ee4  mov     rax, [rcx+288h]
0x140034eeb  inc     rax
0x140034eee  xor     ebp, ebp
0x140034ef0  cmp     rax, 1
0x140034ef4  jbe     short loc_140034F45
0x140034ef6  mov     rcx, [rsp+58h]; this
0x140034efb  lea     rax, aReportingNotCa; "Reporting not cancelled during destruct"...
0x140034f02  mov     qword ptr [rsp+58h+var_30], rax; int
0x140034f07  mov     dword ptr [rsp+58h+var_38], 80000000h; wil::details *
0x140034f0f  lea     r9, aCkernelreportC_4; "CKernelReport::~CKernelReport"
0x140034f16  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140034f1d  mov     edx, 167h; void *
0x140034f22  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140034f27  mov     rcx, [rbx+288h]; hObject
0x140034f2e  mov     [rbx+288h], rbp
0x140034f35  lea     rax, [rcx+1]
0x140034f39  cmp     rax, 1
0x140034f3d  jbe     short loc_140034F45
0x140034f3f  call    cs:__imp_CloseHandle
0x140034f45  lea     rcx, [rbx+80h]; lpFileName
0x140034f4c  cmp     [rcx], bp
0x140034f4f  jz      short loc_140034F57
0x140034f51  call    cs:__imp_DeleteFileW
0x140034f57  mov     rcx, [rbx+2A8h]; this
0x140034f5e  mov     [rbx+2A8h], rbp
0x140034f65  test    rcx, rcx
0x140034f68  jz      short loc_140034F70
0x140034f6a  call    ?WerPluginsDestroy@@YAJPEAX@Z; WerPluginsDestroy(void *)
0x140034f6f  nop
0x140034f70  mov     rcx, [rbx+2B0h]; void *
0x140034f77  lea     rax, [rbx+2C0h]
0x140034f7e  cmp     rcx, rax
0x140034f81  jz      short loc_140034F8F
0x140034f83  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140034f8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140034f8f  mov     rcx, [rbx+2A8h]; this
0x140034f96  test    rcx, rcx
0x140034f99  jz      short loc_140034FA1
0x140034f9b  call    ?WerPluginsDestroy@@YAJPEAX@Z; WerPluginsDestroy(void *)
0x140034fa0  nop
0x140034fa1  lea     rsi, [rbx+290h]
0x140034fa8  mov     rdi, [rsi]
0x140034fab  cmp     rdi, rsi
0x140034fae  jz      short loc_140034FE8
0x140034fb0  mov     rdx, [rdi+8]
0x140034fb4  mov     rax, [rdi]
0x140034fb7  mov     [rdx], rax
0x140034fba  mov     [rax+8], rdx
0x140034fbe  mov     rcx, [rdi+10h]; void *
0x140034fc2  lea     rax, [rdi+20h]
0x140034fc6  cmp     rcx, rax
0x140034fc9  jz      short loc_140034FD7
0x140034fcb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140034fd2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140034fd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140034fde  mov     rcx, rdi; void *
0x140034fe1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140034fe6  jmp     short loc_140034FA8
0x140034fe8  mov     [rsi+10h], rbp
0x140034fec  mov     rcx, [rbx+288h]; hObject
0x140034ff3  lea     rax, [rcx+1]
0x140034ff7  cmp     rax, 1
0x140034ffb  jbe     short loc_140035004
0x140034ffd  call    cs:__imp_CloseHandle
0x140035003  nop
0x140035004  add     rsp, 38h
0x140035008  pop     rdi
0x140035009  pop     rsi
0x14003500a  pop     rbp
0x14003500b  pop     rbx
0x14003500c  retn
```
