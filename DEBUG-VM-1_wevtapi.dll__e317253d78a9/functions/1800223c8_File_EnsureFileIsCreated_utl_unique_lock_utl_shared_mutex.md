# File::EnsureFileIsCreated(utl::unique_lock<utl::shared_mutex> &)

- ea: `0x1800223c8`
- end: `0x1800225a2`
- name: `?EnsureFileIsCreated@File@@AEAAKAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(File *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1800227b4`
- `0x18003409c`

## callees

- `0x1800223c8`
- `0x180022d7c`
- `0x180023548`
- `0x180032794`
- `0x180034874`
- `0x1800349f0`
- `0x180034a94`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x1800224c7`
- `ntdll!NtSetInformationFile` at `0x1800224c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022435`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022417`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022417`

## pseudocode

```c
__int64 __fastcall File::EnsureFileIsCreated(LPCWSTR *this)
{
  void **v2; // rbx
  HANDLE FileW; // rax
  void *v4; // rcx
  DWORD LastError; // ebp
  int v6; // r8d
  NTSTATUS v8; // eax
  int v9; // edx
  int v10; // r8d
  DWORD v11; // eax
  int v12; // edx
  int v13; // r8d
  bool v14; // zf
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-38h] BYREF
  int FileInformation; // [rsp+80h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 832) )
  {
    v2 = (void **)(this + 84);
    FileW = CreateFileW(this[85], 0xC0000000, 1u, 0, 4u, 0, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset(v2, FileW);
    v4 = *v2;
    if ( (unsigned __int64)*v2 + 1 <= 1 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, v6, LastError, (__int64)this[85]);
      }
      return LastError;
    }
    if ( (*((_BYTE *)this + 825) & 8) == 0 )
    {
      FileInformation = 2;
      IoStatusBlock = 0;
      v8 = NtSetInformationFile(v4, &IoStatusBlock, &FileInformation, 4u, FileRenameInformation|0x40);
      if ( v8 < 0
        && WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, (unsigned int)this[85], v8);
      }
    }
    *((_BYTE *)this + 832) = 0;
    v11 = File::InitializeEmptyFile((File *)this);
    LastError = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v11);
      }
      return LastError;
    }
    v14 = (*((_BYTE *)this + 825) & 8) == 0;
    *((_BYTE *)this + 829) = 1;
    if ( v14
      && WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, (unsigned int)this[89], (__int64)this[85]);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800223c8  push    rbx
0x1800223ca  push    rbp
0x1800223cb  push    rsi
0x1800223cc  push    rdi
0x1800223cd  sub     rsp, 58h
0x1800223d1  cmp     byte ptr [rcx+340h], 0
0x1800223d8  mov     rbp, rdx
0x1800223db  mov     rdi, rcx
0x1800223de  jz      loc_180022597
0x1800223e4  xor     r9d, r9d; lpSecurityAttributes
0x1800223e7  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1800223f0  lea     rbx, [rcx+2A0h]
0x1800223f7  mov     [rsp+78h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800223ff  mov     rcx, [rcx+2A8h]; lpFileName
0x180022406  mov     edx, 0C0000000h; dwDesiredAccess
0x18002240b  mov     [rsp+78h+dwCreationDisposition], 4; dwCreationDisposition
0x180022413  lea     r8d, [r9+1]; dwShareMode
0x180022417  call    cs:__imp_CreateFileW
0x18002241d  mov     rdx, rax
0x180022420  mov     rcx, rbx
0x180022423  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180022428  mov     rcx, [rbx]; FileHandle
0x18002242b  lea     rax, [rcx+1]
0x18002242f  cmp     rax, 1
0x180022433  ja      short loc_180022484
0x180022435  call    cs:__imp_GetLastError
0x18002243b  mov     ebp, eax
0x18002243d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022444  lea     rsi, WPP_GLOBAL_Control
0x18002244b  cmp     rcx, rsi
0x18002244e  jz      short loc_18002247D
0x180022450  mov     ebx, 8000h
0x180022455  test    [rcx+1Ch], ebx
0x180022458  jz      short loc_18002247D
0x18002245a  cmp     byte ptr [rcx+19h], 2
0x18002245e  jb      short loc_18002247D
0x180022460  mov     rax, [rdi+2A8h]
0x180022467  mov     edx, 20h ; ' '
0x18002246c  mov     rcx, [rcx+10h]
0x180022470  mov     r9d, ebp
0x180022473  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x180022478  call    WPP_SF_DS
0x18002247d  mov     eax, ebp
0x18002247f  jmp     loc_180022599
0x180022484  test    byte ptr [rdi+339h], 8
0x18002248b  lea     rsi, WPP_GLOBAL_Control
0x180022492  mov     ebx, 8000h
0x180022497  jnz     short loc_1800224FC
0x180022499  xorps   xmm0, xmm0
0x18002249c  mov     [rsp+78h+FileInformation], 2
0x1800224a7  mov     r9d, 4; Length
0x1800224ad  mov     [rsp+78h+dwCreationDisposition], 4Ah ; 'J'; FileInformationClass
0x1800224b5  lea     r8, [rsp+78h+FileInformation]; FileInformation
0x1800224bd  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x1800224c2  movups  xmmword ptr [rsp+78h+IoStatusBlock], xmm0
0x1800224c7  call    cs:__imp_NtSetInformationFile
0x1800224cd  test    eax, eax
0x1800224cf  jns     short loc_1800224FC
0x1800224d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224d8  cmp     rcx, rsi
0x1800224db  jz      short loc_1800224FC
0x1800224dd  test    [rcx+1Ch], ebx
0x1800224e0  jz      short loc_1800224FC
0x1800224e2  cmp     byte ptr [rcx+19h], 2
0x1800224e6  jb      short loc_1800224FC
0x1800224e8  mov     r9, [rdi+2A8h]
0x1800224ef  mov     rcx, [rcx+10h]
0x1800224f3  mov     [rsp+78h+dwCreationDisposition], eax
0x1800224f7  call    WPP_SF_Sd
0x1800224fc  mov     r8, rbp
0x1800224ff  mov     byte ptr [rdi+340h], 0
0x180022506  mov     rcx, rdi; this
0x180022509  call    ?InitializeEmptyFile@File@@AEAAK_KAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::InitializeEmptyFile(unsigned __int64,utl::unique_lock<utl::shared_mutex> &)
0x18002250e  mov     ebp, eax
0x180022510  test    eax, eax
0x180022512  jz      short loc_180022554
0x180022514  mov     rcx, cs:WPP_GLOBAL_Control
0x18002251b  cmp     rcx, rsi
0x18002251e  jz      loc_18002247D
0x180022524  test    [rcx+1Ch], ebx
0x180022527  jz      loc_18002247D
0x18002252d  cmp     byte ptr [rcx+19h], 2
0x180022531  jb      loc_18002247D
0x180022537  mov     rcx, [rcx+10h]
0x18002253b  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180022542  mov     edx, 22h ; '"'
0x180022547  mov     r9d, eax
0x18002254a  call    WPP_SF_D
0x18002254f  jmp     loc_18002247D
0x180022554  test    byte ptr [rdi+339h], 8
0x18002255b  mov     byte ptr [rdi+33Dh], 1
0x180022562  jnz     short loc_180022597
0x180022564  mov     rcx, cs:WPP_GLOBAL_Control
0x18002256b  cmp     rcx, rsi
0x18002256e  jz      short loc_180022597
0x180022570  test    [rcx+1Ch], ebx
0x180022573  jz      short loc_180022597
0x180022575  cmp     byte ptr [rcx+19h], 4
0x180022579  jb      short loc_180022597
0x18002257b  mov     rax, [rdi+2A8h]
0x180022582  mov     r9, [rdi+2C8h]
0x180022589  mov     rcx, [rcx+10h]
0x18002258d  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x180022592  call    WPP_SF_SS
0x180022597  xor     eax, eax
0x180022599  add     rsp, 58h
0x18002259d  pop     rdi
0x18002259e  pop     rsi
0x18002259f  pop     rbp
0x1800225a0  pop     rbx
0x1800225a1  retn
```
