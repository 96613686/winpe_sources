# StackLockFileWin32Writer::WriteVer(std::filesystem::path const &,unsigned __int64)

- ea: `0x18000bf10`
- end: `0x18000c0cf`
- name: `?WriteVer@StackLockFileWin32Writer@@UEAA_NAEBVpath@filesystem@std@@_K@Z`
- size: `447`
- prototype: `bool __fastcall(StackLockFileWin32Writer *__hidden this, const struct std::filesystem::path *, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x180015af8`

## callees

- `0x180006614`
- `0x180008af0`
- `0x18000bf10`
- `0x18000f908`
- `0x180025610`
- `0x180026a00`
- `0x180026cd8`
- `0x180028514`
- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000bff6`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000bff6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000bfd2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000bfd2`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000bf6b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000bf6b`

## string_xrefs

- `0x18000c0b1`: `UUS version file wasn't updated with the right amount of data (expected=%u, actual=%lu).`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall StackLockFileWin32Writer::WriteVer(
        StackLockFileWin32Writer *this,
        const struct std::filesystem::path *a2,
        __int64 a3)
{
  void *v5; // rcx
  const char *v6; // r9
  LPCVOID *v7; // rdx
  const char *v8; // r9
  const char *v9; // r9
  __int64 v11; // rax
  unsigned int v12; // eax
  int v13; // r8d
  int v14; // edx
  int lpOverlapped; // [rsp+20h] [rbp-60h]
  char *v16; // [rsp+28h] [rbp-58h]
  int v17; // [rsp+30h] [rbp-50h]
  _QWORD v18[2]; // [rsp+40h] [rbp-40h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+50h] [rbp-30h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+58h] [rbp-28h] BYREF
  DWORD nNumberOfBytesToWrite[2]; // [rsp+68h] [rbp-18h]
  unsigned __int64 v22; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 == (void *)-1LL || !v5 )
    return 0;
  liDistanceToMove.QuadPart = 0;
  if ( !SetFilePointerEx(v5, 0, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x77,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFileWin32.hpp",
      v6);
  v18[0] = &UusVersion::`vftable';
  v18[1] = a3;
  UusVersion::GetStringA(v18, lpBuffer);
  if ( nNumberOfBytesToWrite[0] != *(_QWORD *)nNumberOfBytesToWrite )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFileWin32.hpp",
      (const char *)0x80070216LL,
      lpOverlapped);
  liDistanceToMove.LowPart = 0;
  v7 = lpBuffer;
  if ( v22 > 0xF )
    v7 = (LPCVOID *)lpBuffer[0];
  if ( !WriteFile(*((HANDLE *)this + 1), v7, nNumberOfBytesToWrite[0], (LPDWORD)&liDistanceToMove, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x7F,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFileWin32.hpp",
      v8);
  if ( liDistanceToMove.LowPart != *(_QWORD *)nNumberOfBytesToWrite )
  {
    v11 = std::string::length(lpBuffer);
    v12 = wil::verify_hresult<long>(2147549183LL, v11);
    v17 = v13;
    LODWORD(v16) = v14;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x82,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFileWin32.hpp",
      (const char *)v12,
      (int)"UUS version file wasn't updated with the right amount of data (expected=%u, actual=%lu).",
      v16,
      v17);
  }
  if ( !SetEndOfFile(*((HANDLE *)this + 1)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x86,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFileWin32.hpp",
      v9);
  std::string::~string(lpBuffer);
  return 1;
}

```

## disassembly

```asm
0x18000bf10  mov     [rsp-8+arg_8], rbx
0x18000bf15  mov     [rsp-8+arg_10], rsi
0x18000bf1a  mov     [rsp-8+arg_18], rdi
0x18000bf1f  push    rbp
0x18000bf20  mov     rbp, rsp
0x18000bf23  sub     rsp, 80h
0x18000bf2a  mov     rax, cs:__security_cookie
0x18000bf31  xor     rax, rsp
0x18000bf34  mov     [rbp+var_8], rax
0x18000bf38  mov     rsi, r8
0x18000bf3b  mov     rbx, rcx
0x18000bf3e  mov     rcx, [rcx+8]; hFile
0x18000bf42  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000bf46  jz      loc_18000C00D
0x18000bf4c  test    rcx, rcx
0x18000bf4f  jz      loc_18000C00D
0x18000bf55  mov     qword ptr [rbp+liDistanceToMove], 0
0x18000bf5d  mov     rdi, [rbp+8]
0x18000bf61  xor     r9d, r9d; dwMoveMethod
0x18000bf64  xor     r8d, r8d; lpNewFilePointer
0x18000bf67  mov     rdx, qword ptr [rbp+liDistanceToMove]; liDistanceToMove
0x18000bf6b  call    cs:__imp_SetFilePointerEx
0x18000bf71  test    eax, eax
0x18000bf73  jz      loc_18000C049
0x18000bf79  lea     rax, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x18000bf80  mov     [rbp+var_40], rax
0x18000bf84  mov     [rbp+var_38], rsi
0x18000bf88  lea     rdx, [rbp+lpBuffer]
0x18000bf8c  lea     rcx, [rbp+var_40]
0x18000bf90  call    ?GetStringA@UusVersion@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; UusVersion::GetStringA(void)
0x18000bf95  nop
0x18000bf96  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18000bf9a  mov     rcx, [rbp+8]; this
0x18000bf9e  cmp     r8, qword ptr [rbp+nNumberOfBytesToWrite]
0x18000bfa2  jnz     loc_18000C05E
0x18000bfa8  mov     dword ptr [rbp+liDistanceToMove], 0
0x18000bfaf  lea     rdx, [rbp+lpBuffer]
0x18000bfb3  cmp     [rbp+var_10], 0Fh
0x18000bfb8  cmova   rdx, [rbp+lpBuffer]; lpBuffer
0x18000bfbd  mov     rdi, [rbp+8]
0x18000bfc1  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x18000bfca  lea     r9, [rbp+liDistanceToMove]; lpNumberOfBytesWritten
0x18000bfce  mov     rcx, [rbx+8]; hFile
0x18000bfd2  call    cs:__imp_WriteFile
0x18000bfd8  test    eax, eax
0x18000bfda  jz      loc_18000C076
0x18000bfe0  mov     r8d, dword ptr [rbp+liDistanceToMove]
0x18000bfe4  cmp     r8, qword ptr [rbp+nNumberOfBytesToWrite]
0x18000bfe8  jnz     loc_18000C08B
0x18000bfee  mov     rdi, [rbp+8]
0x18000bff2  mov     rcx, [rbx+8]; hFile
0x18000bff6  call    cs:__imp_SetEndOfFile
0x18000bffc  test    eax, eax
0x18000bffe  jz      short loc_18000C034
0x18000c000  lea     rcx, [rbp+lpBuffer]
0x18000c004  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000c009  mov     al, 1
0x18000c00b  jmp     short loc_18000C00F
0x18000c00d  xor     al, al
0x18000c00f  mov     rcx, [rbp+var_8]
0x18000c013  xor     rcx, rsp; StackCookie
0x18000c016  call    __security_check_cookie
0x18000c01b  lea     r11, [rsp+80h+var_s0]
0x18000c023  mov     rbx, [r11+18h]
0x18000c027  mov     rsi, [r11+20h]
0x18000c02b  mov     rdi, [r11+28h]
0x18000c02f  mov     rsp, r11
0x18000c032  pop     rbp
0x18000c033  retn
0x18000c034  lea     r8, aCW1SSrcBrainLi_5; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x18000c03b  mov     edx, 86h; void *
0x18000c040  mov     rcx, rdi; this
0x18000c043  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c049  lea     r8, aCW1SSrcBrainLi_5; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x18000c050  mov     edx, 77h ; 'w'; void *
0x18000c055  mov     rcx, rdi; this
0x18000c058  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c05e  mov     r9d, 80070216h; char *
0x18000c064  lea     r8, aCW1SSrcBrainLi_5; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x18000c06b  mov     edx, 7Bh ; '{'; void *
0x18000c070  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c076  lea     r8, aCW1SSrcBrainLi_5; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x18000c07d  mov     edx, 7Fh; void *
0x18000c082  mov     rcx, rdi; this
0x18000c085  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c08b  lea     rcx, [rbp+lpBuffer]
0x18000c08f  call    ?length@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA_KXZ; std::string::length(void)
0x18000c094  mov     rdx, rax
0x18000c097  mov     ecx, 8000FFFFh
0x18000c09c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000c0a1  mov     r9d, eax; char *
0x18000c0a4  mov     rcx, [rbp+8]; this
0x18000c0a8  mov     [rsp+80h+var_50], r8d
0x18000c0ad  mov     dword ptr [rsp+80h+var_58], edx; char *
0x18000c0b1  lea     rax, aUusVersionFile_0; "UUS version file wasn't updated with th"...
0x18000c0b8  mov     [rsp+80h+lpOverlapped], rax; int
0x18000c0bd  lea     r8, aCW1SSrcBrainLi_5; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x18000c0c4  mov     edx, 82h; void *
0x18000c0c9  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
