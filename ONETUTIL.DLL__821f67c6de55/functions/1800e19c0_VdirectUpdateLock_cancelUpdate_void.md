# VdirectUpdateLock::cancelUpdate(void)

- ea: `0x1800e19c0`
- end: `0x1800e1cde`
- name: `?cancelUpdate@VdirectUpdateLock@@UEAAXXZ`
- size: `798`
- prototype: `void __fastcall(VdirectUpdateLock *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180052658`
- `0x180068c00`
- `0x1800e1020`

## callees

- `0x180047c50`
- `0x1800838f0`
- `0x180093d10`
- `0x1800e19c0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!SetFileTime` at `0x1800e1bd2`
- `KERNEL32!SetFileTime` at `0x1800e1bd2`
- `KERNEL32!SetEndOfFile` at `0x1800e1b51`
- `KERNEL32!SetEndOfFile` at `0x1800e1b51`
- `KERNEL32!SetFilePointer` at `0x1800e1adc`
- `KERNEL32!SetFilePointer` at `0x1800e1adc`
- `KERNEL32!CloseHandle` at `0x1800e1bdf`
- `KERNEL32!CloseHandle` at `0x1800e1bdf`
- `KERNEL32!GetLastError` at `0x1800e1af1`
- `KERNEL32!GetLastError` at `0x1800e1b62`
- `KERNEL32!GetLastError` at `0x1800e1bf0`
- `KERNEL32!GetLastError` at `0x1800e1af1`
- `KERNEL32!GetLastError` at `0x1800e1b62`
- `KERNEL32!GetLastError` at `0x1800e1bf0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800e1a92`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800e1a92`

## string_xrefs

- `0x1800e19ec`: `VdirectUpdateLock::cancelUpdate, InFilePath = %s, Locked = %d\n`

## pseudocode

```c
void __fastcall VdirectUpdateLock::cancelUpdate(VdirectUpdateLock *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rax
  void (__fastcall ***v3)(_QWORD, __int64); // r8
  void (__fastcall ***v4)(_QWORD, __int64, void (__fastcall ***)(_QWORD, __int64)); // rcx
  bool v5; // zf
  void *v6; // rcx
  void *v7; // rcx
  char *v8; // rbx
  DWORD LastError; // eax
  void (__fastcall ***v10)(_QWORD, __int64); // rbx
  char *v11; // rbx
  DWORD v12; // eax
  void (__fastcall ***v13)(_QWORD, __int64); // rbx
  char *v14; // rbx
  DWORD v15; // eax
  void (__fastcall ***v16)(_QWORD, __int64); // rbx
  struct Vstatus *v17; // rax
  struct Vstatus *v18; // rax
  int v19; // [rsp+20h] [rbp-38h]
  int v20; // [rsp+38h] [rbp-20h]

  v20 = *((char *)this + 8);
  LOWORD(v19) = 3;
  (*(void (**)(void *, __int64, __int64, _QWORD, int, const char *, ...))(off_1802AB3C8 + 80LL))(
    &off_1802AB3C8,
    946564405,
    117141511,
    0,
    v19,
    "VdirectUpdateLock::cancelUpdate, InFilePath = %s, Locked = %d\n",
    *((_QWORD *)this + 14),
    v20);
  if ( *((_BYTE *)this + 8) )
  {
    v2 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 2) + 8LL))((char *)this + 16);
    v3 = v2;
    if ( v2 )
      (**v2)(v2, 1);
    v4 = (void (__fastcall ***)(_QWORD, __int64, void (__fastcall ***)(_QWORD, __int64)))*((_QWORD *)this + 49);
    if ( v4 )
      (**v4)(v4, 1, v3);
    v5 = dword_1802B0018 == 0;
    v6 = (void *)*((_QWORD *)this + 50);
    *((_QWORD *)this + 49) = 0;
    if ( v5 )
      free(v6);
    else
      COWSAllocator::Free(v6);
    *((_QWORD *)this + 50) = 0;
    *((_QWORD *)this + 18) = 0;
    if ( *((_DWORD *)this + 62) == 1 )
    {
      v7 = (void *)*((_QWORD *)this + 52);
      if ( v7 != (void *)-1LL )
      {
        if ( *((_BYTE *)this + 136) )
        {
          if ( SetFilePointer(v7, *((_DWORD *)this + 108), 0, 0) != *((_DWORD *)this + 108) )
          {
            v8 = (char *)*((_QWORD *)this + 19);
            LastError = GetLastError();
            v10 = (void (__fastcall ***)(_QWORD, __int64))sub_180047C50(0x2000Cu, LastError, v8);
            (*(void (__fastcall **)(void *, __int64, __int64, _QWORD, void (__fastcall ***)(_QWORD, __int64)))(off_1802AB3C8 + 32LL))(
              &off_1802AB3C8,
              946564406,
              117141511,
              0,
              v10);
            if ( v10 )
              (**v10)(v10, 1);
          }
          if ( !SetEndOfFile(*((HANDLE *)this + 52)) )
          {
            v11 = (char *)*((_QWORD *)this + 19);
            v12 = GetLastError();
            v13 = (void (__fastcall ***)(_QWORD, __int64))sub_180047C50(0x2000Cu, v12, v11);
            (*(void (__fastcall **)(void *, __int64, __int64, _QWORD, void (__fastcall ***)(_QWORD, __int64)))(off_1802AB3C8 + 32LL))(
              &off_1802AB3C8,
              946564407,
              117141511,
              0,
              v13);
            if ( v13 )
              (**v13)(v13, 1);
          }
          SetFileTime(
            *((HANDLE *)this + 52),
            0,
            (const FILETIME *)((char *)this + 436),
            (const FILETIME *)((char *)this + 444));
        }
        if ( !CloseHandle(*((HANDLE *)this + 52)) )
        {
          v14 = (char *)*((_QWORD *)this + 19);
          v15 = GetLastError();
          v16 = (void (__fastcall ***)(_QWORD, __int64))sub_180047C50(0x20006u, v15, v14);
          (*(void (__fastcall **)(void *, __int64, __int64, _QWORD, void (__fastcall ***)(_QWORD, __int64)))(off_1802AB3C8 + 32LL))(
            &off_1802AB3C8,
            946564408,
            117141511,
            0,
            v16);
          if ( v16 )
            (**v16)(v16, 1);
        }
        *((_QWORD *)this + 52) = -1;
        if ( !*((_BYTE *)this + 136) )
        {
          v17 = Vpath::removeFile((VdirectUpdateLock *)((char *)this + 152));
          if ( v17 )
            (**(void (__fastcall ***)(struct Vstatus *, __int64))v17)(v17, 1);
        }
      }
      if ( !*((_BYTE *)this + 408) )
        goto LABEL_30;
      *((_BYTE *)this + 408) = 0;
    }
    else if ( *((_BYTE *)this + 136) )
    {
LABEL_30:
      *((_BYTE *)this + 8) = 0;
      *((_DWORD *)this + 62) = 0;
      return;
    }
    v18 = Vpath::removeFile((VdirectUpdateLock *)((char *)this + 152));
    if ( v18 )
      (**(void (__fastcall ***)(struct Vstatus *, __int64))v18)(v18, 1);
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x1800e19c0  mov     r11, rsp
0x1800e19c3  mov     [r11+8], rbx
0x1800e19c7  mov     [r11+10h], rbp
0x1800e19cb  mov     [r11+18h], rsi
0x1800e19cf  push    rdi
0x1800e19d0  sub     rsp, 50h
0x1800e19d4  movsx   edx, byte ptr [rcx+8]
0x1800e19d8  mov     rdi, rcx
0x1800e19db  mov     rax, cs:off_1802AB3C8
0x1800e19e2  xor     esi, esi
0x1800e19e4  mov     [rsp+58h+var_20], edx
0x1800e19e8  mov     rdx, [rcx+70h]
0x1800e19ec  lea     rcx, aVdirectupdatel_3; "VdirectUpdateLock::cancelUpdate, InFile"...
0x1800e19f3  mov     [r11-28h], rdx
0x1800e19f7  mov     edx, 386B6D35h
0x1800e19fc  mov     rax, [rax+50h]
0x1800e1a00  lea     r8d, [rsi+3]
0x1800e1a04  mov     [r11-30h], rcx
0x1800e1a08  lea     rcx, off_1802AB3C8
0x1800e1a0f  mov     [r11-38h], r8w
0x1800e1a14  mov     r8d, 6FB7007h
0x1800e1a1a  movzx   r9d, si
0x1800e1a1e  call    cs:__guard_dispatch_icall_fptr
0x1800e1a24  cmp     [rdi+8], sil
0x1800e1a28  jz      loc_1800E1CC9
0x1800e1a2e  lea     rcx, [rdi+10h]
0x1800e1a32  mov     rax, [rcx]
0x1800e1a35  mov     rax, [rax+8]
0x1800e1a39  call    cs:__guard_dispatch_icall_fptr
0x1800e1a3f  lea     ebp, [rsi+1]
0x1800e1a42  mov     r8, rax
0x1800e1a45  test    rax, rax
0x1800e1a48  jz      short loc_1800E1A5B
0x1800e1a4a  mov     rcx, [rax]
0x1800e1a4d  mov     edx, ebp
0x1800e1a4f  mov     rax, [rcx]
0x1800e1a52  mov     rcx, r8
0x1800e1a55  call    cs:__guard_dispatch_icall_fptr
0x1800e1a5b  mov     rcx, [rdi+188h]
0x1800e1a62  test    rcx, rcx
0x1800e1a65  jz      short loc_1800E1A75
0x1800e1a67  mov     rax, [rcx]
0x1800e1a6a  mov     edx, ebp
0x1800e1a6c  mov     rax, [rax]
0x1800e1a6f  call    cs:__guard_dispatch_icall_fptr
0x1800e1a75  cmp     cs:dword_1802B0018, esi
0x1800e1a7b  mov     rcx, [rdi+190h]; void *
0x1800e1a82  mov     [rdi+188h], rsi
0x1800e1a89  jz      short loc_1800E1A92
0x1800e1a8b  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800e1a90  jmp     short loc_1800E1A98
0x1800e1a92  call    cs:free
0x1800e1a98  mov     [rdi+190h], rsi
0x1800e1a9f  mov     [rdi+90h], rsi
0x1800e1aa6  cmp     [rdi+0F8h], ebp
0x1800e1aac  jnz     loc_1800E1C91
0x1800e1ab2  mov     rcx, [rdi+1A0h]; hFile
0x1800e1ab9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800e1abd  jz      loc_1800E1C7F
0x1800e1ac3  cmp     [rdi+88h], sil
0x1800e1aca  jz      loc_1800E1BD8
0x1800e1ad0  mov     edx, [rdi+1B0h]; lDistanceToMove
0x1800e1ad6  xor     r9d, r9d; dwMoveMethod
0x1800e1ad9  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800e1adc  call    cs:SetFilePointer
0x1800e1ae2  cmp     eax, [rdi+1B0h]
0x1800e1ae8  jz      short loc_1800E1B4A
0x1800e1aea  mov     rbx, [rdi+98h]
0x1800e1af1  call    cs:GetLastError
0x1800e1af7  mov     r8, rbx
0x1800e1afa  mov     ecx, 2000Ch
0x1800e1aff  mov     edx, eax
0x1800e1b01  call    sub_180047C50
0x1800e1b06  mov     rcx, cs:off_1802AB3C8
0x1800e1b0d  mov     rbx, rax
0x1800e1b10  xor     r9d, r9d
0x1800e1b13  mov     qword ptr [rsp+58h+var_38], rbx
0x1800e1b18  mov     edx, 386B6D36h
0x1800e1b1d  mov     r8d, 6FB7007h
0x1800e1b23  mov     rax, [rcx+20h]
0x1800e1b27  lea     rcx, off_1802AB3C8
0x1800e1b2e  call    cs:__guard_dispatch_icall_fptr
0x1800e1b34  test    rbx, rbx
0x1800e1b37  jz      short loc_1800E1B4A
0x1800e1b39  mov     rcx, [rbx]
0x1800e1b3c  mov     edx, ebp
0x1800e1b3e  mov     rax, [rcx]
0x1800e1b41  mov     rcx, rbx
0x1800e1b44  call    cs:__guard_dispatch_icall_fptr
0x1800e1b4a  mov     rcx, [rdi+1A0h]; hFile
0x1800e1b51  call    cs:SetEndOfFile
0x1800e1b57  test    eax, eax
0x1800e1b59  jnz     short loc_1800E1BBB
0x1800e1b5b  mov     rbx, [rdi+98h]
0x1800e1b62  call    cs:GetLastError
0x1800e1b68  mov     r8, rbx
0x1800e1b6b  mov     ecx, 2000Ch
0x1800e1b70  mov     edx, eax
0x1800e1b72  call    sub_180047C50
0x1800e1b77  mov     rcx, cs:off_1802AB3C8
0x1800e1b7e  mov     rbx, rax
0x1800e1b81  xor     r9d, r9d
0x1800e1b84  mov     qword ptr [rsp+58h+var_38], rbx
0x1800e1b89  mov     edx, 386B6D37h
0x1800e1b8e  mov     r8d, 6FB7007h
0x1800e1b94  mov     rax, [rcx+20h]
0x1800e1b98  lea     rcx, off_1802AB3C8
0x1800e1b9f  call    cs:__guard_dispatch_icall_fptr
0x1800e1ba5  test    rbx, rbx
0x1800e1ba8  jz      short loc_1800E1BBB
0x1800e1baa  mov     rcx, [rbx]
0x1800e1bad  mov     edx, ebp
0x1800e1baf  mov     rax, [rcx]
0x1800e1bb2  mov     rcx, rbx
0x1800e1bb5  call    cs:__guard_dispatch_icall_fptr
0x1800e1bbb  mov     rcx, [rdi+1A0h]; hFile
0x1800e1bc2  lea     r9, [rdi+1BCh]; lpLastWriteTime
0x1800e1bc9  lea     r8, [rdi+1B4h]; lpLastAccessTime
0x1800e1bd0  xor     edx, edx; lpCreationTime
0x1800e1bd2  call    cs:SetFileTime
0x1800e1bd8  mov     rcx, [rdi+1A0h]; hObject
0x1800e1bdf  call    cs:CloseHandle
0x1800e1be5  test    eax, eax
0x1800e1be7  jnz     short loc_1800E1C49
0x1800e1be9  mov     rbx, [rdi+98h]
0x1800e1bf0  call    cs:GetLastError
0x1800e1bf6  mov     r8, rbx
0x1800e1bf9  mov     ecx, 20006h
0x1800e1bfe  mov     edx, eax
0x1800e1c00  call    sub_180047C50
0x1800e1c05  mov     rdx, cs:off_1802AB3C8
0x1800e1c0c  lea     rcx, off_1802AB3C8
0x1800e1c13  mov     rbx, rax
0x1800e1c16  xor     r9d, r9d
0x1800e1c19  mov     r8d, 6FB7007h
0x1800e1c1f  mov     qword ptr [rsp+58h+var_38], rbx
0x1800e1c24  mov     rax, [rdx+20h]
0x1800e1c28  mov     edx, 386B6D38h
0x1800e1c2d  call    cs:__guard_dispatch_icall_fptr
0x1800e1c33  test    rbx, rbx
0x1800e1c36  jz      short loc_1800E1C49
0x1800e1c38  mov     rcx, [rbx]
0x1800e1c3b  mov     edx, ebp
0x1800e1c3d  mov     rax, [rcx]
0x1800e1c40  mov     rcx, rbx
0x1800e1c43  call    cs:__guard_dispatch_icall_fptr
0x1800e1c49  or      qword ptr [rdi+1A0h], 0FFFFFFFFFFFFFFFFh
0x1800e1c51  cmp     [rdi+88h], sil
0x1800e1c58  jnz     short loc_1800E1C7F
0x1800e1c5a  lea     rcx, [rdi+98h]; this
0x1800e1c61  call    ?removeFile@Vpath@@QEAAPEAVVstatus@@XZ; Vpath::removeFile(void)
0x1800e1c66  mov     r8, rax
0x1800e1c69  test    rax, rax
0x1800e1c6c  jz      short loc_1800E1C7F
0x1800e1c6e  mov     rcx, [rax]
0x1800e1c71  mov     edx, ebp
0x1800e1c73  mov     rax, [rcx]
0x1800e1c76  mov     rcx, r8
0x1800e1c79  call    cs:__guard_dispatch_icall_fptr
0x1800e1c7f  cmp     [rdi+198h], sil
0x1800e1c86  jz      short loc_1800E1CBF
0x1800e1c88  mov     [rdi+198h], sil
0x1800e1c8f  jmp     short loc_1800E1C9A
0x1800e1c91  cmp     [rdi+88h], sil
0x1800e1c98  jnz     short loc_1800E1CBF
0x1800e1c9a  lea     rcx, [rdi+98h]; this
0x1800e1ca1  call    ?removeFile@Vpath@@QEAAPEAVVstatus@@XZ; Vpath::removeFile(void)
0x1800e1ca6  mov     r8, rax
0x1800e1ca9  test    rax, rax
0x1800e1cac  jz      short loc_1800E1CBF
0x1800e1cae  mov     rcx, [rax]
0x1800e1cb1  mov     edx, ebp
0x1800e1cb3  mov     rax, [rcx]
0x1800e1cb6  mov     rcx, r8
0x1800e1cb9  call    cs:__guard_dispatch_icall_fptr
0x1800e1cbf  mov     [rdi+8], sil
0x1800e1cc3  mov     [rdi+0F8h], esi
0x1800e1cc9  mov     rbx, [rsp+58h+arg_0]
0x1800e1cce  mov     rbp, [rsp+58h+arg_8]
0x1800e1cd3  mov     rsi, [rsp+58h+arg_10]
0x1800e1cd8  add     rsp, 50h
0x1800e1cdc  pop     rdi
0x1800e1cdd  retn
```
