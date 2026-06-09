# ValidateFile(ushort const *,ulong,ulong,void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1401b87a0`
- end: `0x1401b89d0`
- name: `?ValidateFile@@YAHPEBGKKPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `560`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1401b9d30`

## callees

- `0x140030100`
- `0x140031c88`
- `0x140132940`
- `0x1401b6bf8`
- `0x1401b87a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1401b899f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1401b899f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b8852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b88cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b8905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b8852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b88cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b8905`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b896a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b896a`
- `ntdll!RtlAllocateHeap` at `0x1401b887a`
- `ntdll!RtlAllocateHeap` at `0x1401b887a`
- `ntdll!RtlFreeHeap` at `0x1401b898d`
- `ntdll!RtlFreeHeap` at `0x1401b898d`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1401b88f5`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1401b88f5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1401b88b1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1401b88b1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1401b8838`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1401b8838`

## pseudocode

```c
__int64 __fastcall ValidateFile(const WCHAR *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // r14d
  HANDLE FileW; // rsi
  DWORD LastError; // ebx
  WCHAR *Heap; // rdi
  int v9; // ebx
  DWORD FinalPathNameByHandleW; // eax
  __int64 v11; // r15
  __int64 v12; // rax
  DWORD dwFlags[8]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+78h] [rbp-90h]
  __int64 v16; // [rsp+88h] [rbp-80h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+90h] [rbp-78h] BYREF

  v5 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  v15 = 0;
  v16 = 0;
  dwFlags[0] = 0;
  dwFlags[1] = 1;
  dwFlags[2] = 8;
  dwFlags[3] = 9;
  dwFlags[4] = 10;
  FileW = CreateFileW(a1, 0x80u, 7u, 0, 3u, 0x100080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
  }
  else
  {
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xFFFEu);
    if ( Heap )
    {
      v9 = 0;
      while ( 1 )
      {
        FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, Heap, 0x7FFFu, dwFlags[v9]);
        v11 = FinalPathNameByHandleW;
        if ( FinalPathNameByHandleW )
          break;
        if ( (unsigned int)++v9 >= 5 )
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 2;
          goto LABEL_14;
        }
      }
      if ( GetFileInformationByHandle(FileW, &FileInformation) )
      {
        if ( (FileInformation.dwFileAttributes & 0x10) != 0 )
        {
          LastError = 267;
        }
        else
        {
          try
          {
            v12 = std::wstring::wstring(dwFlags, Heap, v11);
            std::wstring::operator=(a5, v12);
            std::wstring::_Tidy_deallocate(dwFlags);
            LastError = 0;
            v5 = 1;
          }
          catch ( std::bad_alloc )
          {
            LastError = 14;
            v5 = 0;
          }
        }
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = 14;
    }
LABEL_14:
    CloseHandle(FileW);
    if ( Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
  if ( LastError )
    SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x1401b87a0  mov     r11, rsp
0x1401b87a3  push    rbx
0x1401b87a4  push    rsi
0x1401b87a5  push    rdi
0x1401b87a6  push    r12
0x1401b87a8  push    r14
0x1401b87aa  push    r15
0x1401b87ac  sub     rsp, 0D8h
0x1401b87b3  mov     rax, cs:__security_cookie
0x1401b87ba  xor     rax, rsp
0x1401b87bd  mov     [rsp+108h+var_40], rax
0x1401b87c5  mov     r12, [rsp+108h+arg_20]
0x1401b87cd  xor     r14d, r14d
0x1401b87d0  mov     [rsp+108h+var_C4], r14d
0x1401b87d5  xorps   xmm0, xmm0
0x1401b87d8  xor     eax, eax
0x1401b87da  movups  xmmword ptr [r11-78h], xmm0
0x1401b87df  movups  xmmword ptr [r11-68h], xmm0
0x1401b87e4  movups  xmmword ptr [r11-58h], xmm0
0x1401b87e9  mov     [r11-48h], eax
0x1401b87ed  movups  [rsp+108h+var_90], xmm0
0x1401b87f2  mov     [r11-80h], rax
0x1401b87f6  mov     [rsp+108h+dwFlags], eax
0x1401b87fa  mov     [rsp+108h+var_AC], 1
0x1401b8802  lea     ebx, [rax+8]
0x1401b8805  mov     [rsp+108h+var_A8], ebx
0x1401b8809  mov     [rsp+108h+var_A4], 9
0x1401b8811  mov     [rsp+108h+var_A0], 0Ah
0x1401b8819  mov     [rsp+108h+hTemplateFile], rax; hTemplateFile
0x1401b881e  mov     [rsp+108h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1401b8826  mov     [rsp+108h+dwCreationDisposition], 3; dwCreationDisposition
0x1401b882e  xor     r9d, r9d; lpSecurityAttributes
0x1401b8831  lea     edx, [rbx+78h]; dwDesiredAccess
0x1401b8834  lea     r8d, [r14+7]; dwShareMode
0x1401b8838  call    cs:__imp_CreateFileW
0x1401b883f  nop     dword ptr [rax+rax+00h]
0x1401b8844  mov     rsi, rax
0x1401b8847  mov     [rsp+108h+var_C0], rax
0x1401b884c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401b8850  jnz     short loc_1401B8865
0x1401b8852  call    cs:__imp_GetLastError
0x1401b8859  nop     dword ptr [rax+rax+00h]
0x1401b885e  mov     ebx, eax
0x1401b8860  jmp     loc_1401B8999
0x1401b8865  mov     rcx, gs:60h
0x1401b886e  mov     r8d, 0FFFEh; Size
0x1401b8874  mov     edx, ebx; Flags
0x1401b8876  mov     rcx, [rcx+30h]; HeapHandle
0x1401b887a  call    cs:__imp_RtlAllocateHeap
0x1401b8881  nop     dword ptr [rax+rax+00h]
0x1401b8886  mov     rdi, rax
0x1401b8889  mov     [rsp+108h+var_B8], rax
0x1401b888e  test    rax, rax
0x1401b8891  jnz     short loc_1401B889B
0x1401b8893  lea     ebx, [rax+0Eh]
0x1401b8896  jmp     loc_1401B8967
0x1401b889b  xor     ebx, ebx
0x1401b889d  movsxd  r9, ebx
0x1401b88a0  mov     r9d, [rsp+r9*4+108h+dwFlags]; dwFlags
0x1401b88a5  mov     r8d, 7FFFh; cchFilePath
0x1401b88ab  mov     rdx, rdi; lpszFilePath
0x1401b88ae  mov     rcx, rsi; hFile
0x1401b88b1  call    cs:__imp_GetFinalPathNameByHandleW
0x1401b88b8  nop     dword ptr [rax+rax+00h]
0x1401b88bd  mov     r15d, eax
0x1401b88c0  test    eax, eax
0x1401b88c2  jnz     short loc_1401B88EA
0x1401b88c4  inc     ebx
0x1401b88c6  cmp     ebx, 5
0x1401b88c9  jb      short loc_1401B889D
0x1401b88cb  test    eax, eax
0x1401b88cd  jnz     short loc_1401B88EA
0x1401b88cf  call    cs:__imp_GetLastError
0x1401b88d6  nop     dword ptr [rax+rax+00h]
0x1401b88db  mov     ebx, eax
0x1401b88dd  test    eax, eax
0x1401b88df  jnz     loc_1401B8967
0x1401b88e5  lea     ebx, [rax+2]
0x1401b88e8  jmp     short loc_1401B8967
0x1401b88ea  lea     rdx, [rsp+108h+FileInformation]; lpFileInformation
0x1401b88f2  mov     rcx, rsi; hFile
0x1401b88f5  call    cs:__imp_GetFileInformationByHandle
0x1401b88fc  nop     dword ptr [rax+rax+00h]
0x1401b8901  test    eax, eax
0x1401b8903  jnz     short loc_1401B8915
0x1401b8905  call    cs:__imp_GetLastError
0x1401b890c  nop     dword ptr [rax+rax+00h]
0x1401b8911  mov     ebx, eax
0x1401b8913  jmp     short loc_1401B8967
0x1401b8915  test    byte ptr [rsp+108h+FileInformation.dwFileAttributes], 10h
0x1401b891d  jz      short loc_1401B8926
0x1401b891f  mov     ebx, 10Bh
0x1401b8924  jmp     short loc_1401B8967
0x1401b8926  mov     r8, r15
0x1401b8929  mov     rdx, rdi
0x1401b892c  lea     rcx, [rsp+108h+dwFlags]
0x1401b8931  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1401b8936  mov     rdx, rax
0x1401b8939  mov     rcx, r12
0x1401b893c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1401b8941  lea     rcx, [rsp+108h+dwFlags]
0x1401b8946  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1401b894b  nop
0x1401b894c  xor     ebx, ebx
0x1401b894e  lea     r14d, [rbx+1]
0x1401b8952  jmp     short loc_1401B8967
0x1401b8954  mov     ebx, [rsp+108h+var_C8]
0x1401b8958  mov     r14d, [rsp+108h+var_C4]
0x1401b895d  mov     rsi, [rsp+108h+var_C0]
0x1401b8962  mov     rdi, [rsp+108h+var_B8]
0x1401b8967  mov     rcx, rsi; hObject
0x1401b896a  call    cs:__imp_CloseHandle
0x1401b8971  nop     dword ptr [rax+rax+00h]
0x1401b8976  test    rdi, rdi
0x1401b8979  jz      short loc_1401B8999
0x1401b897b  mov     rcx, gs:60h
0x1401b8984  mov     r8, rdi; P
0x1401b8987  xor     edx, edx; Flags
0x1401b8989  mov     rcx, [rcx+30h]; HeapHandle
0x1401b898d  call    cs:__imp_RtlFreeHeap
0x1401b8994  nop     dword ptr [rax+rax+00h]
0x1401b8999  test    ebx, ebx
0x1401b899b  jz      short loc_1401B89AB
0x1401b899d  mov     ecx, ebx; dwErrCode
0x1401b899f  call    cs:__imp_SetLastError
0x1401b89a6  nop     dword ptr [rax+rax+00h]
0x1401b89ab  mov     eax, r14d
0x1401b89ae  mov     rcx, [rsp+108h+var_40]
0x1401b89b6  xor     rcx, rsp; StackCookie
0x1401b89b9  call    __security_check_cookie
0x1401b89be  add     rsp, 0D8h
0x1401b89c5  pop     r15
0x1401b89c7  pop     r14
0x1401b89c9  pop     r12
0x1401b89cb  pop     rdi
0x1401b89cc  pop     rsi
0x1401b89cd  pop     rbx
0x1401b89ce  retn
```
