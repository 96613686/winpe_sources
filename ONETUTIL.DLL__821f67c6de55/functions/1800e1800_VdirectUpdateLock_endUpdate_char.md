# VdirectUpdateLock::endUpdate(char)

- ea: `0x1800e1800`
- end: `0x1800e19be`
- name: `?endUpdate@VdirectUpdateLock@@UEAAPEAVVstatus@@D@Z`
- size: `446`
- prototype: `struct Vstatus *__fastcall(VdirectUpdateLock *__hidden this, char)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180052658`
- `0x180068c00`
- `0x1800cd7fc`

## callees

- `0x180047c50`
- `0x1800838f0`
- `0x1800e1800`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x1800e18f8`
- `KERNEL32!SetEndOfFile` at `0x1800e18f8`
- `KERNEL32!WriteFile` at `0x1800e18d2`
- `KERNEL32!WriteFile` at `0x1800e18d2`
- `KERNEL32!SetFilePointer` at `0x1800e18a5`
- `KERNEL32!SetFilePointer` at `0x1800e18a5`
- `KERNEL32!CloseHandle` at `0x1800e1909`
- `KERNEL32!CloseHandle` at `0x1800e1909`
- `KERNEL32!GetLastError` at `0x1800e191a`
- `KERNEL32!GetLastError` at `0x1800e194c`
- `KERNEL32!GetLastError` at `0x1800e191a`
- `KERNEL32!GetLastError` at `0x1800e194c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800e198a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800e1995`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800e198a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800e1995`

## string_xrefs

- `0x1800e1834`: `VdirectUpdateLock::endUpdate, InFilePath = %s, Locked = %d\n`

## pseudocode

```c
struct Vstatus *__fastcall VdirectUpdateLock::endUpdate(VdirectUpdateLock *this, char a2)
{
  struct Vstatus *result; // rax
  void *v5; // rcx
  char *v6; // rbx
  DWORD LastError; // eax
  unsigned int v8; // ecx
  void *v9; // rcx
  struct Vstatus *v10; // rbx
  void *v11; // rcx
  int lpOverlapped; // [rsp+20h] [rbp-38h]
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  LOWORD(lpOverlapped) = 3;
  (*(void (**)(void *, __int64, __int64, _QWORD, int, const char *, ...))(off_1802AB3C8 + 80LL))(
    &off_1802AB3C8,
    946564404,
    117141511,
    0,
    lpOverlapped,
    "VdirectUpdateLock::endUpdate, InFilePath = %s, Locked = %d\n",
    *((_QWORD *)this + 14),
    *((char *)this + 8));
  if ( *((_DWORD *)this + 62)
    || (result = (struct Vstatus *)(*(__int64 (__fastcall **)(VdirectUpdateLock *, _QWORD))(*(_QWORD *)this + 40LL))(
                                     this,
                                     a2 != 0 ? 8 : 0)) == 0 )
  {
    v5 = (void *)*((_QWORD *)this + 52);
    if ( v5 != (void *)-1LL )
    {
      if ( SetFilePointer(v5, 0, 0, 0)
        || !WriteFile(
              *((HANDLE *)this + 52),
              *((LPCVOID *)this + 50),
              *((_DWORD *)this + 107),
              &NumberOfBytesWritten,
              0)
        || NumberOfBytesWritten != *((_DWORD *)this + 107)
        || !*((_BYTE *)this + 424) && !SetEndOfFile(*((HANDLE *)this + 52)) )
      {
        v6 = (char *)*((_QWORD *)this + 19);
        LastError = GetLastError();
        v8 = 131084;
        goto LABEL_15;
      }
      if ( !CloseHandle(*((HANDLE *)this + 52)) )
      {
        v6 = (char *)*((_QWORD *)this + 19);
        LastError = GetLastError();
        v8 = 131078;
LABEL_15:
        v10 = (struct Vstatus *)sub_180047C50(v8, LastError, v6);
        (*(void (__fastcall **)(VdirectUpdateLock *))(*(_QWORD *)this + 16LL))(this);
        v11 = (void *)*((_QWORD *)this + 50);
        if ( dword_1802B0018 )
          COWSAllocator::Free(v11);
        else
          free(v11);
        result = v10;
LABEL_21:
        *((_QWORD *)this + 50) = 0;
        return result;
      }
      *((_QWORD *)this + 52) = -1;
    }
    v9 = (void *)*((_QWORD *)this + 50);
    if ( dword_1802B0018 )
      COWSAllocator::Free(v9);
    else
      free(v9);
    *((_BYTE *)this + 8) = 0;
    result = 0;
    *((_DWORD *)this + 62) = 0;
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x1800e1800  mov     r11, rsp
0x1800e1803  mov     [r11+10h], rbx
0x1800e1807  mov     [r11+18h], rsi
0x1800e180b  push    rdi
0x1800e180c  sub     rsp, 50h
0x1800e1810  movsx   r8d, byte ptr [rcx+8]
0x1800e1815  mov     rdi, rcx
0x1800e1818  mov     rax, cs:off_1802AB3C8
0x1800e181f  mov     bl, dl
0x1800e1821  mov     [r11-20h], r8d
0x1800e1825  mov     edx, 3
0x1800e182a  mov     r8, [rcx+70h]
0x1800e182e  xor     esi, esi
0x1800e1830  mov     [r11-28h], r8
0x1800e1834  lea     rcx, aVdirectupdatel_2; "VdirectUpdateLock::endUpdate, InFilePat"...
0x1800e183b  mov     rax, [rax+50h]
0x1800e183f  mov     r8d, 6FB7007h
0x1800e1845  mov     [r11-30h], rcx
0x1800e1849  lea     rcx, off_1802AB3C8
0x1800e1850  mov     word ptr [rsp+58h+lpOverlapped], dx
0x1800e1855  mov     edx, 386B6D34h
0x1800e185a  movzx   r9d, si
0x1800e185e  call    cs:__guard_dispatch_icall_fptr
0x1800e1864  cmp     [rdi+0F8h], esi
0x1800e186a  jnz     short loc_1800E188C
0x1800e186c  mov     rax, [rdi]
0x1800e186f  neg     bl
0x1800e1871  mov     rcx, rdi
0x1800e1874  sbb     edx, edx
0x1800e1876  and     edx, 8
0x1800e1879  mov     rax, [rax+28h]
0x1800e187d  call    cs:__guard_dispatch_icall_fptr
0x1800e1883  test    rax, rax
0x1800e1886  jnz     loc_1800E19AE
0x1800e188c  mov     rcx, [rdi+1A0h]; hFile
0x1800e1893  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800e1897  jz      loc_1800E192F
0x1800e189d  xor     r9d, r9d; dwMoveMethod
0x1800e18a0  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800e18a3  xor     edx, edx; lDistanceToMove
0x1800e18a5  call    cs:SetFilePointer
0x1800e18ab  test    eax, eax
0x1800e18ad  jnz     loc_1800E1945
0x1800e18b3  mov     r8d, [rdi+1ACh]; nNumberOfBytesToWrite
0x1800e18ba  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800e18bf  mov     rdx, [rdi+190h]; lpBuffer
0x1800e18c6  mov     rcx, [rdi+1A0h]; hFile
0x1800e18cd  mov     qword ptr [rsp+58h+lpOverlapped], rsi; lpOverlapped
0x1800e18d2  call    cs:WriteFile
0x1800e18d8  test    eax, eax
0x1800e18da  jz      short loc_1800E1945
0x1800e18dc  mov     eax, [rdi+1ACh]
0x1800e18e2  cmp     [rsp+58h+NumberOfBytesWritten], eax
0x1800e18e6  jnz     short loc_1800E1945
0x1800e18e8  cmp     [rdi+1A8h], sil
0x1800e18ef  jnz     short loc_1800E1902
0x1800e18f1  mov     rcx, [rdi+1A0h]; hFile
0x1800e18f8  call    cs:SetEndOfFile
0x1800e18fe  test    eax, eax
0x1800e1900  jz      short loc_1800E1945
0x1800e1902  mov     rcx, [rdi+1A0h]; hObject
0x1800e1909  call    cs:CloseHandle
0x1800e190f  test    eax, eax
0x1800e1911  jnz     short loc_1800E1927
0x1800e1913  mov     rbx, [rdi+98h]
0x1800e191a  call    cs:GetLastError
0x1800e1920  mov     ecx, 20006h
0x1800e1925  jmp     short loc_1800E1957
0x1800e1927  or      qword ptr [rdi+1A0h], 0FFFFFFFFFFFFFFFFh
0x1800e192f  cmp     cs:dword_1802B0018, esi
0x1800e1935  mov     rcx, [rdi+190h]; void *
0x1800e193c  jz      short loc_1800E1995
0x1800e193e  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800e1943  jmp     short loc_1800E199B
0x1800e1945  mov     rbx, [rdi+98h]
0x1800e194c  call    cs:GetLastError
0x1800e1952  mov     ecx, 2000Ch
0x1800e1957  mov     r8, rbx
0x1800e195a  mov     edx, eax
0x1800e195c  call    sub_180047C50
0x1800e1961  mov     rbx, rax
0x1800e1964  mov     rax, [rdi]
0x1800e1967  mov     rcx, rdi
0x1800e196a  mov     rax, [rax+10h]
0x1800e196e  call    cs:__guard_dispatch_icall_fptr
0x1800e1974  cmp     cs:dword_1802B0018, esi
0x1800e197a  mov     rcx, [rdi+190h]; void *
0x1800e1981  jz      short loc_1800E198A
0x1800e1983  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800e1988  jmp     short loc_1800E1990
0x1800e198a  call    cs:free
0x1800e1990  mov     rax, rbx
0x1800e1993  jmp     short loc_1800E19A7
0x1800e1995  call    cs:free
0x1800e199b  mov     [rdi+8], sil
0x1800e199f  xor     eax, eax
0x1800e19a1  mov     [rdi+0F8h], esi
0x1800e19a7  mov     [rdi+190h], rsi
0x1800e19ae  mov     rbx, [rsp+58h+arg_8]
0x1800e19b3  mov     rsi, [rsp+58h+arg_10]
0x1800e19b8  add     rsp, 50h
0x1800e19bc  pop     rdi
0x1800e19bd  retn
```
