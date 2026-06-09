# Appx::Packaging::CreateTempFileStream(ushort const *,ushort const *,IStream * *)

- ea: `0x180087cb4`
- end: `0x180087dbc`
- name: `?CreateTempFileStream@Packaging@Appx@@YAJPEBG0PEAPEAUIStream@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(Appx::Packaging *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IStream **)`
- caller_count: `13`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180050604`
- `0x18007ef00`
- `0x1800872ac`
- `0x180087b68`
- `0x180087bec`
- `0x18008972c`
- `0x1800b7f58`
- `0x1800b9b44`
- `0x1800be410`
- `0x1800c021c`
- `0x1800c0f54`
- `0x1800d1bac`
- `0x1800ea0bc`

## callees

- `0x180071f50`
- `0x180087cb4`
- `0x18008851c`

## import_xrefs

- `OpcServices!__imp_CreateTempFileName` at `0x180087ce5`
- `OpcServices!__imp_CreateTempFileName` at `0x180087ce5`
- `OpcServices!__imp_CreateStreamOnFileHandle` at `0x180087d59`
- `OpcServices!__imp_CreateStreamOnFileHandle` at `0x180087d59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087da2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087da2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180087d3e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180087d3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::CreateTempFileStream(
        Appx::Packaging *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IStream **a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  HANDLE FileW; // rax
  int StreamOnFileHandle; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-38h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPCWSTR lpFileName; // [rsp+70h] [rbp+18h] BYREF
  __int64 v14; // [rsp+78h] [rbp+20h] BYREF

  *(_QWORD *)a3 = 0;
  lpFileName = 0;
  v5 = CreateTempFileName(this, a2, L".tmp", &lpFileName);
  v6 = v5;
  if ( v5 >= 0 )
  {
    FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 2u, 0x4000100u, 0);
    v14 = 0;
    StreamOnFileHandle = CreateStreamOnFileHandle(FileW, a3);
    v6 = StreamOnFileHandle;
    if ( StreamOnFileHandle < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\streamhelper.cpp",
        (const char *)(unsigned int)StreamOnFileHandle,
        dwCreationDispositiona);
    Common::AutoBaseHandle<void *,&void Common::CloseHandleHelper(void *)>::~AutoBaseHandle<void *,&void Common::CloseHandleHelper(void *)>(&v14);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\streamhelper.cpp",
      (const char *)(unsigned int)v5,
      dwCreationDisposition);
  }
  CoTaskMemFree((LPVOID)lpFileName);
  return v6;
}

```

## disassembly

```asm
0x180087cb4  mov     rax, rsp
0x180087cb7  push    rdi
0x180087cb8  sub     rsp, 50h
0x180087cbc  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x180087cc4  mov     [rax+8], rbx
0x180087cc8  mov     rdi, r8
0x180087ccb  mov     qword ptr [r8], 0
0x180087cd2  mov     qword ptr [rax+18h], 0
0x180087cda  lea     r9, [rax+18h]
0x180087cde  lea     r8, aTmp; ".tmp"
0x180087ce5  call    cs:__imp_CreateTempFileName
0x180087cec  nop     dword ptr [rax+rax+00h]
0x180087cf1  mov     ebx, eax
0x180087cf3  mov     rcx, [rsp+58h]; this
0x180087cf8  test    eax, eax
0x180087cfa  jns     short loc_180087D15
0x180087cfc  mov     r9d, eax; char *
0x180087cff  lea     r8, aOnecorePrintsc_75; "onecore\\printscan\\appxpackaging\\lib"...
0x180087d06  mov     edx, 55h ; 'U'; void *
0x180087d0b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180087d10  jmp     loc_180087D9D
0x180087d15  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180087d1e  mov     [rsp+58h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x180087d26  mov     [rsp+58h+dwCreationDisposition], 2; int
0x180087d2e  xor     r9d, r9d; lpSecurityAttributes
0x180087d31  xor     r8d, r8d; dwShareMode
0x180087d34  mov     edx, 0C0000000h; dwDesiredAccess
0x180087d39  mov     rcx, [rsp+58h+lpFileName]; lpFileName
0x180087d3e  call    cs:__imp_CreateFileW
0x180087d45  nop     dword ptr [rax+rax+00h]
0x180087d4a  mov     [rsp+58h+arg_18], 0
0x180087d53  mov     rdx, rdi
0x180087d56  mov     rcx, rax
0x180087d59  call    cs:__imp_CreateStreamOnFileHandle
0x180087d60  nop     dword ptr [rax+rax+00h]
0x180087d65  mov     ebx, eax
0x180087d67  mov     rcx, [rsp+58h]; this
0x180087d6c  test    eax, eax
0x180087d6e  jns     short loc_180087D92
0x180087d70  mov     r9d, eax; char *
0x180087d73  lea     r8, aOnecorePrintsc_75; "onecore\\printscan\\appxpackaging\\lib"...
0x180087d7a  mov     edx, 62h ; 'b'; void *
0x180087d7f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180087d84  nop
0x180087d85  lea     rcx, [rsp+58h+arg_18]
0x180087d8a  call    ??1?$AutoBaseHandle@PEAX$1?CloseHandleHelper@Common@@YAXPEAX@Z@Common@@QEAA@XZ; Common::AutoBaseHandle<void *,&Common::CloseHandleHelper(void *)>::~AutoBaseHandle<void *,&Common::CloseHandleHelper(void *)>(void)
0x180087d8f  nop
0x180087d90  jmp     short loc_180087D9D
0x180087d92  lea     rcx, [rsp+58h+arg_18]
0x180087d97  call    ??1?$AutoBaseHandle@PEAX$1?CloseHandleHelper@Common@@YAXPEAX@Z@Common@@QEAA@XZ; Common::AutoBaseHandle<void *,&Common::CloseHandleHelper(void *)>::~AutoBaseHandle<void *,&Common::CloseHandleHelper(void *)>(void)
0x180087d9c  nop
0x180087d9d  mov     rcx, [rsp+58h+lpFileName]; pv
0x180087da2  call    cs:__imp_CoTaskMemFree
0x180087da9  nop     dword ptr [rax+rax+00h]
0x180087dae  mov     eax, ebx
0x180087db0  mov     rbx, [rsp+58h+arg_0]
0x180087db5  add     rsp, 50h
0x180087db9  pop     rdi
0x180087dba  retn
```
