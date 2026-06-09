# DiagHubCommon::PeHelper::CreateFromFile(ushort const *,std::unique_ptr<DiagHubCommon::PeHelper,std::default_delete<DiagHubCommon::PeHelper>> &,bool)

- ea: `0x180043860`
- end: `0x180043a5a`
- name: `?CreateFromFile@PeHelper@DiagHubCommon@@SAJPEBGAEAV?$unique_ptr@VPeHelper@DiagHubCommon@@U?$default_delete@VPeHelper@DiagHubCommon@@@std@@@std@@_N@Z`
- size: `506`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180038f48`

## callees

- `0x180043774`
- `0x180043860`
- `0x180043a5c`
- `0x18004a03c`
- `0x18004ad26`
- `0x18004b640`

## import_xrefs

- `KERNEL32!GetFileSize` at `0x180043902`
- `KERNEL32!GetFileSize` at `0x180043902`
- `KERNEL32!CreateFileMappingW` at `0x180043934`
- `KERNEL32!CreateFileMappingW` at `0x180043934`
- `KERNEL32!MapViewOfFile` at `0x180043959`
- `KERNEL32!MapViewOfFile` at `0x180043959`
- `KERNEL32!CreateFileW` at `0x1800438ed`
- `KERNEL32!CreateFileW` at `0x1800438ed`
- `KERNEL32!CloseHandle` at `0x180043a40`
- `KERNEL32!CloseHandle` at `0x180043a40`
- `KERNEL32!GetLastError` at `0x180043968`
- `KERNEL32!GetLastError` at `0x180043968`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DiagHubCommon::PeHelper::CreateFromFile(LPCWSTR lpFileName, DiagHubCommon::PeHelper **a2)
{
  _OWORD *v4; // r14
  void (__fastcall ***v5)(_QWORD, __int64); // rdi
  HANDLE FileW; // rax
  DWORD FileSize; // ebx
  void *v8; // rcx
  HANDLE FileMappingW; // rax
  LPVOID v10; // rax
  signed int LastError; // eax
  signed int v12; // esi
  void *v13; // rbx
  DiagHubCommon::PeHelper *v14; // rbp
  DiagHubCommon::PeHelper *v15; // rbx
  DiagHubCommon::PeHelper *v16; // rcx
  DiagHubCommon::PeHelper *v18; // [rsp+40h] [rbp-38h] BYREF
  _OWORD *v19; // [rsp+48h] [rbp-30h]

  v4 = operator new(0x28u);
  *v4 = 0;
  v4[1] = 0;
  *((_QWORD *)v4 + 1) = 0;
  *((_DWORD *)v4 + 4) = 0;
  *((_BYTE *)v4 + 20) = 1;
  *(_QWORD *)v4 = &DiagHubCommon::PeHelper::OnDiskPeHelperDataSource::`vftable';
  *((_QWORD *)v4 + 3) = 0;
  *((_QWORD *)v4 + 4) = 0;
  v5 = (void (__fastcall ***)(_QWORD, __int64))v4;
  v19 = v4;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_5;
  *((_QWORD *)v4 + 3) = FileW;
  FileSize = GetFileSize(FileW, 0);
  v8 = (void *)*((_QWORD *)v4 + 3);
  if ( FileSize - 1 <= 0xFFFFFFFD )
  {
    FileMappingW = CreateFileMappingW(v8, 0, 2u, 0, 0, 0);
    if ( FileMappingW )
    {
      *((_QWORD *)v4 + 4) = FileMappingW;
      v10 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      *((_QWORD *)v4 + 1) = v10;
      if ( v10 )
      {
LABEL_9:
        v13 = operator new(0x78u);
        memset_0(v13, 0, 0x78u);
        v5 = 0;
        v19 = 0;
        v18 = (DiagHubCommon::PeHelper *)v4;
        v14 = (DiagHubCommon::PeHelper *)DiagHubCommon::PeHelper::PeHelper(v13, &v18);
        v15 = v14;
        v18 = v14;
        v12 = DiagHubCommon::PeHelper::Initialize(v14);
        if ( v12 >= 0 )
        {
          v15 = 0;
          v16 = *a2;
          *a2 = v14;
          if ( v16 )
            (**(void (__fastcall ***)(DiagHubCommon::PeHelper *, __int64))v16)(v16, 1);
          v12 = 0;
          v14 = 0;
        }
        if ( v14 )
          (**(void (__fastcall ***)(DiagHubCommon::PeHelper *, __int64))v15)(v15, 1);
        goto LABEL_15;
      }
    }
    goto LABEL_5;
  }
  CloseHandle(v8);
  if ( FileSize )
  {
LABEL_5:
    LastError = GetLastError();
    goto LABEL_6;
  }
  LastError = 193;
LABEL_6:
  v12 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v12 = LastError;
  if ( v12 >= 0 )
    goto LABEL_9;
LABEL_15:
  if ( v5 )
    (**v5)(v5, 1);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180043860  mov     [rsp+arg_10], rbx
0x180043865  push    rbp
0x180043866  push    rsi
0x180043867  push    rdi
0x180043868  push    r14
0x18004386a  push    r15
0x18004386c  sub     rsp, 50h
0x180043870  mov     r15, rdx
0x180043873  mov     rbx, rcx
0x180043876  mov     ecx, 28h ; '('; Size
0x18004387b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043880  mov     r14, rax
0x180043883  mov     [rsp+78h+var_30], rax
0x180043888  xorps   xmm0, xmm0
0x18004388b  xor     eax, eax
0x18004388d  movups  xmmword ptr [r14], xmm0
0x180043891  movups  xmmword ptr [r14+10h], xmm0
0x180043896  mov     [r14+8], rax
0x18004389a  mov     [r14+10h], eax
0x18004389e  mov     byte ptr [r14+14h], 1
0x1800438a3  lea     rax, ??_7OnDiskPeHelperDataSource@PeHelper@DiagHubCommon@@6B@; const DiagHubCommon::PeHelper::OnDiskPeHelperDataSource::`vftable'
0x1800438aa  mov     [r14], rax
0x1800438ad  mov     qword ptr [r14+18h], 0
0x1800438b5  mov     qword ptr [r14+20h], 0
0x1800438bd  mov     rdi, r14
0x1800438c0  mov     [rsp+78h+var_30], r14
0x1800438c5  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1800438ce  mov     [rsp+78h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800438d6  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x1800438de  xor     r9d, r9d; lpSecurityAttributes
0x1800438e1  mov     edx, 80000000h; dwDesiredAccess
0x1800438e6  lea     r8d, [r9+1]; dwShareMode
0x1800438ea  mov     rcx, rbx; lpFileName
0x1800438ed  call    cs:__imp_CreateFileW
0x1800438f3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800438f7  jz      short loc_180043968
0x1800438f9  mov     [r14+18h], rax
0x1800438fd  xor     edx, edx; lpFileSizeHigh
0x1800438ff  mov     rcx, rax; hFile
0x180043902  call    cs:__imp_GetFileSize
0x180043908  mov     ebx, eax
0x18004390a  lea     ecx, [rax-1]
0x18004390d  cmp     ecx, 0FFFFFFFDh
0x180043910  mov     rcx, [r14+18h]; hObject
0x180043914  ja      loc_180043A40
0x18004391a  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpName
0x180043923  mov     [rsp+78h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18004392b  xor     r9d, r9d; dwMaximumSizeHigh
0x18004392e  xor     edx, edx; lpFileMappingAttributes
0x180043930  lea     r8d, [r9+2]; flProtect
0x180043934  call    cs:__imp_CreateFileMappingW
0x18004393a  test    rax, rax
0x18004393d  jz      short loc_180043968
0x18004393f  mov     [r14+20h], rax
0x180043943  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18004394c  xor     r9d, r9d; dwFileOffsetLow
0x18004394f  xor     r8d, r8d; dwFileOffsetHigh
0x180043952  lea     edx, [r9+4]; dwDesiredAccess
0x180043956  mov     rcx, rax; hFileMappingObject
0x180043959  call    cs:__imp_MapViewOfFile
0x18004395f  mov     [r14+8], rax
0x180043963  test    rax, rax
0x180043966  jnz     short loc_180043984
0x180043968  call    cs:__imp_GetLastError
0x18004396e  movzx   esi, ax
0x180043971  or      esi, 80070000h
0x180043977  test    eax, eax
0x180043979  cmovle  esi, eax
0x18004397c  test    esi, esi
0x18004397e  js      loc_180043A11
0x180043984  mov     edi, 78h ; 'x'
0x180043989  mov     ecx, edi; Size
0x18004398b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043990  mov     rbx, rax
0x180043993  mov     [rsp+78h+var_30], rax
0x180043998  mov     r8d, edi; Size
0x18004399b  xor     edx, edx; Val
0x18004399d  mov     rcx, rax; void *
0x1800439a0  call    memset_0
0x1800439a5  xor     edi, edi
0x1800439a7  mov     [rsp+78h+var_30], rdi
0x1800439ac  mov     [rsp+78h+var_38], r14
0x1800439b1  lea     rdx, [rsp+78h+var_38]
0x1800439b6  mov     rcx, rbx
0x1800439b9  call    ??0PeHelper@DiagHubCommon@@QEAA@V?$unique_ptr@VPeHelperDataSource@PeHelper@DiagHubCommon@@U?$default_delete@VPeHelperDataSource@PeHelper@DiagHubCommon@@@std@@@std@@@Z; DiagHubCommon::PeHelper::PeHelper(std::unique_ptr<DiagHubCommon::PeHelper::PeHelperDataSource>)
0x1800439be  mov     rbp, rax
0x1800439c1  mov     rbx, rax
0x1800439c4  mov     [rsp+78h+var_38], rax
0x1800439c9  mov     rcx, rax; this
0x1800439cc  call    ?Initialize@PeHelper@DiagHubCommon@@AEAAJXZ; DiagHubCommon::PeHelper::Initialize(void)
0x1800439d1  mov     esi, eax
0x1800439d3  test    eax, eax
0x1800439d5  js      short loc_1800439F7
0x1800439d7  xor     ebx, ebx
0x1800439d9  mov     rcx, [r15]
0x1800439dc  mov     [r15], rbp
0x1800439df  test    rcx, rcx
0x1800439e2  jz      short loc_1800439F3
0x1800439e4  mov     rax, [rcx]
0x1800439e7  lea     edx, [rdi+1]
0x1800439ea  mov     rax, [rax]
0x1800439ed  call    cs:__guard_dispatch_icall_fptr
0x1800439f3  xor     esi, esi
0x1800439f5  xor     ebp, ebp
0x1800439f7  test    rbp, rbp
0x1800439fa  jz      short loc_180043A11
0x1800439fc  mov     rax, [rbx]
0x1800439ff  mov     edx, 1
0x180043a04  mov     rcx, rbx
0x180043a07  mov     rax, [rax]
0x180043a0a  call    cs:__guard_dispatch_icall_fptr
0x180043a10  nop
0x180043a11  test    rdi, rdi
0x180043a14  jz      short loc_180043A2A
0x180043a16  mov     rcx, [rdi]
0x180043a19  mov     rax, [rcx]
0x180043a1c  mov     edx, 1
0x180043a21  mov     rcx, rdi
0x180043a24  call    cs:__guard_dispatch_icall_fptr
0x180043a2a  mov     eax, esi
0x180043a2c  mov     rbx, [rsp+78h+arg_10]
0x180043a34  add     rsp, 50h
0x180043a38  pop     r15
0x180043a3a  pop     r14
0x180043a3c  pop     rdi
0x180043a3d  pop     rsi
0x180043a3e  pop     rbp
0x180043a3f  retn
0x180043a40  call    cs:__imp_CloseHandle
0x180043a46  nop
0x180043a47  test    ebx, ebx
0x180043a49  jnz     loc_180043968
0x180043a4f  mov     eax, 0C1h
0x180043a54  jmp     loc_18004396E
```
