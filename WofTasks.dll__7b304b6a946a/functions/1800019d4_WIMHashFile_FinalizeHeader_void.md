# WIMHashFile::FinalizeHeader(void)

- ea: `0x1800019d4`
- end: `0x180001c18`
- name: `?FinalizeHeader@WIMHashFile@@AEAAJXZ`
- size: `580`
- prototype: `__int64 __fastcall(WIMHashFile *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002474`

## callees

- `0x1800019d4`
- `0x180001c20`
- `0x1800027c4`
- `0x1800029bc`
- `0x1800029fc`
- `0x180002a88`
- `0x180004434`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180001be1`
- `KERNEL32!HeapFree` at `0x180001be1`
- `KERNEL32!HeapAlloc` at `0x180001aaa`
- `KERNEL32!HeapAlloc` at `0x180001aaa`
- `KERNEL32!GetProcessHeap` at `0x180001a99`
- `KERNEL32!GetProcessHeap` at `0x180001bd3`
- `KERNEL32!GetProcessHeap` at `0x180001a99`
- `KERNEL32!GetProcessHeap` at `0x180001bd3`
- `KERNEL32!GetFileSizeEx` at `0x180001a18`
- `KERNEL32!GetFileSizeEx` at `0x180001a18`
- `KERNEL32!GetLastError` at `0x180001a22`
- `KERNEL32!GetLastError` at `0x180001a22`
- `bcrypt!BCryptFinishHash` at `0x180001b60`
- `bcrypt!BCryptFinishHash` at `0x180001b60`
- `bcrypt!BCryptDestroyHash` at `0x180001bf7`
- `bcrypt!BCryptDestroyHash` at `0x180001bf7`
- `bcrypt!BCryptHashData` at `0x180001b2f`
- `bcrypt!BCryptHashData` at `0x180001b2f`
- `bcrypt!BCryptCreateHash` at `0x180001a72`
- `bcrypt!BCryptCreateHash` at `0x180001a72`

## pseudocode

```c
__int64 __fastcall WIMHashFile::FinalizeHeader(WIMHashFile *this)
{
  unsigned int v2; // edi
  signed int LastError; // eax
  __int64 v4; // rbp
  __int64 v5; // r14
  NTSTATUS v6; // edi
  union _LARGE_INTEGER v7; // rbx
  HANDLE ProcessHeap; // rax
  void *v9; // r15
  __int64 v10; // rbp
  __int64 v11; // r14
  __int64 v12; // rbx
  NTSTATUS v13; // edi
  __int64 v14; // r8
  HANDLE v15; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+78h] [rbp+10h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+80h] [rbp+18h] BYREF

  FileSize.QuadPart = 0;
  phHash = 0;
  v2 = File::Flush(this);
  if ( !v2 )
  {
    if ( GetFileSizeEx(*(HANDLE *)this, &FileSize) )
      goto LABEL_6;
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( !v2 )
    {
LABEL_6:
      v4 = *((_QWORD *)this + 7);
      v5 = *((unsigned int *)this + 16);
      v6 = BCryptCreateHash(*((BCRYPT_ALG_HANDLE *)this + 20), &phHash, 0, 0, 0, 0, 0);
      if ( v6 >= 0 )
      {
        v7.QuadPart = *((unsigned int *)this + 16);
        v2 = File::MoveFilePointer(this, v7);
        if ( v2 )
          goto LABEL_28;
        ProcessHeap = GetProcessHeap();
        v9 = HeapAlloc(ProcessHeap, 0, 0x400000u);
        if ( !v9 )
        {
          v2 = -2147024882;
          goto LABEL_28;
        }
        v10 = v5 + 16 * ((__int64)((v4 + 4095) & 0xFFFFFFFFFFFFF000uLL) / 4096) - v7.QuadPart;
LABEL_18:
        if ( v10 > 0 )
        {
          v11 = 0x400000;
          if ( (unsigned __int64)v10 <= 0x400000 )
            v11 = (unsigned int)v10;
          v2 = File::Read(this, v9, v11, 0);
          if ( v2 )
            goto LABEL_26;
          v12 = 0;
          while ( 1 )
          {
            v13 = BCryptHashData(phHash, (PUCHAR)v9 + v12, 0x10u, 0);
            if ( v13 < 0 )
              break;
            v12 += 16;
            if ( v12 >= v11 )
            {
              v10 -= v11;
              goto LABEL_18;
            }
          }
        }
        else
        {
          v13 = BCryptFinishHash(phHash, (PUCHAR)this + 68, 0x20u, 0);
          if ( v13 >= 0 )
          {
            v2 = WIMHashFile::Hash(this, (unsigned __int8 *)this + 16, v14, (unsigned __int8 *)this + 100);
            if ( !v2 )
            {
              v2 = File::MoveFilePointer(this, 0);
              if ( !v2 )
              {
                v2 = File::Write(this, (char *)this + 16, 0x74u);
                if ( !v2 )
                {
                  v2 = File::Flush(this);
                  if ( !v2 )
                    LogFile(
                      &WofTaskCompleteHashFileEventId,
                      *((const unsigned __int16 **)this + 18),
                      *((const unsigned __int16 **)this + 1));
                }
              }
            }
            goto LABEL_26;
          }
        }
        v2 = v13 | 0x10000000;
LABEL_26:
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v9);
        goto LABEL_28;
      }
      v2 = v6 | 0x10000000;
    }
  }
LABEL_28:
  if ( phHash )
    BCryptDestroyHash(phHash);
  return v2;
}

```

## disassembly

```asm
0x1800019d4  mov     rax, rsp
0x1800019d7  mov     [rax+8], rbx
0x1800019db  mov     [rax+20h], rbp
0x1800019df  push    rsi
0x1800019e0  push    rdi
0x1800019e1  push    r13
0x1800019e3  push    r14
0x1800019e5  push    r15
0x1800019e7  sub     rsp, 40h
0x1800019eb  mov     rsi, rcx
0x1800019ee  mov     qword ptr [rax+18h], 0
0x1800019f6  mov     qword ptr [rax+10h], 0
0x1800019fe  call    ?Flush@File@@QEAAJXZ; File::Flush(void)
0x180001a03  mov     edi, eax
0x180001a05  test    eax, eax
0x180001a07  jnz     loc_180001BED
0x180001a0d  mov     rcx, [rsi]; hFile
0x180001a10  lea     rdx, [rsp+68h+FileSize]; lpFileSize
0x180001a18  call    cs:__imp_GetFileSizeEx
0x180001a1e  test    eax, eax
0x180001a20  jnz     short loc_180001A3F
0x180001a22  call    cs:__imp_GetLastError
0x180001a28  mov     edi, eax
0x180001a2a  test    eax, eax
0x180001a2c  jle     short loc_180001A37
0x180001a2e  movzx   edi, ax
0x180001a31  or      edi, 80070000h
0x180001a37  test    edi, edi
0x180001a39  jnz     loc_180001BED
0x180001a3f  mov     rcx, [rsi+0A0h]; hAlgorithm
0x180001a46  lea     rdx, [rsp+68h+phHash]; phHash
0x180001a4b  mov     rbp, [rsi+38h]
0x180001a4f  xor     r9d, r9d; cbHashObject
0x180001a52  mov     r14d, [rsi+40h]
0x180001a56  xor     r8d, r8d; pbHashObject
0x180001a59  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180001a61  mov     [rsp+68h+cbSecret], 0; cbSecret
0x180001a69  mov     [rsp+68h+pbSecret], 0; pbSecret
0x180001a72  call    cs:__imp_BCryptCreateHash
0x180001a78  mov     edi, eax
0x180001a7a  test    eax, eax
0x180001a7c  js      loc_180001BE9
0x180001a82  mov     ebx, [rsi+40h]
0x180001a85  mov     rcx, rsi; this
0x180001a88  mov     edx, ebx; union _LARGE_INTEGER
0x180001a8a  call    ?MoveFilePointer@File@@QEAAJT_LARGE_INTEGER@@@Z; File::MoveFilePointer(_LARGE_INTEGER)
0x180001a8f  mov     edi, eax
0x180001a91  test    eax, eax
0x180001a93  jnz     loc_180001BED
0x180001a99  call    cs:__imp_GetProcessHeap
0x180001a9f  xor     edx, edx; dwFlags
0x180001aa1  mov     r8d, 400000h; dwBytes
0x180001aa7  mov     rcx, rax; hHeap
0x180001aaa  call    cs:__imp_HeapAlloc
0x180001ab0  mov     r15, rax
0x180001ab3  test    rax, rax
0x180001ab6  jnz     short loc_180001AC2
0x180001ab8  mov     edi, 8007000Eh
0x180001abd  jmp     loc_180001BED
0x180001ac2  lea     rax, [rbp+0FFFh]
0x180001ac9  and     rax, 0FFFFFFFFFFFFF000h
0x180001acf  cqo
0x180001ad1  and     edx, 0FFFh
0x180001ad7  lea     rbp, [rdx+rax]
0x180001adb  sar     rbp, 0Ch
0x180001adf  shl     rbp, 4
0x180001ae3  sub     rbp, rbx
0x180001ae6  add     rbp, r14
0x180001ae9  jmp     short loc_180001B4B
0x180001aeb  mov     r14d, 400000h
0x180001af1  cmp     rbp, 400000h
0x180001af8  ja      short loc_180001AFD
0x180001afa  mov     r14d, ebp
0x180001afd  xor     r9d, r9d; unsigned int *
0x180001b00  mov     r8d, r14d; unsigned int
0x180001b03  mov     rdx, r15; void *
0x180001b06  mov     rcx, rsi; this
0x180001b09  call    ?Read@File@@QEAAJPEAXKPEAK@Z; File::Read(void *,ulong,ulong *)
0x180001b0e  mov     edi, eax
0x180001b10  test    eax, eax
0x180001b12  jnz     loc_180001BD3
0x180001b18  xor     ebx, ebx
0x180001b1a  test    r14, r14
0x180001b1d  jz      short loc_180001B48
0x180001b1f  mov     rcx, [rsp+68h+phHash]; hHash
0x180001b24  lea     rdx, [rbx+r15]; pbInput
0x180001b28  xor     r9d, r9d; dwFlags
0x180001b2b  lea     r8d, [r9+10h]; cbInput
0x180001b2f  call    cs:__imp_BCryptHashData
0x180001b35  mov     edi, eax
0x180001b37  test    eax, eax
0x180001b39  js      loc_180001BCF
0x180001b3f  add     rbx, 10h
0x180001b43  cmp     rbx, r14
0x180001b46  jl      short loc_180001B1F
0x180001b48  sub     rbp, r14
0x180001b4b  test    rbp, rbp
0x180001b4e  jg      short loc_180001AEB
0x180001b50  mov     rcx, [rsp+68h+phHash]; hHash
0x180001b55  lea     rdx, [rsi+44h]; pbOutput
0x180001b59  xor     r9d, r9d; dwFlags
0x180001b5c  lea     r8d, [r9+20h]; cbOutput
0x180001b60  call    cs:__imp_BCryptFinishHash
0x180001b66  mov     edi, eax
0x180001b68  test    eax, eax
0x180001b6a  js      short loc_180001BCF
0x180001b6c  lea     r9, [rsi+64h]; unsigned __int8 *
0x180001b70  mov     rcx, rsi; this
0x180001b73  lea     rdx, [rsi+10h]; unsigned __int8 *
0x180001b77  call    ?Hash@WIMHashFile@@QEAAJPEAEK0@Z; WIMHashFile::Hash(uchar *,ulong,uchar *)
0x180001b7c  mov     edi, eax
0x180001b7e  test    eax, eax
0x180001b80  jnz     short loc_180001BD3
0x180001b82  xor     edx, edx; union _LARGE_INTEGER
0x180001b84  mov     rcx, rsi; this
0x180001b87  call    ?MoveFilePointer@File@@QEAAJT_LARGE_INTEGER@@@Z; File::MoveFilePointer(_LARGE_INTEGER)
0x180001b8c  mov     edi, eax
0x180001b8e  test    eax, eax
0x180001b90  jnz     short loc_180001BD3
0x180001b92  lea     r8d, [rax+74h]; unsigned int
0x180001b96  mov     rcx, rsi; this
0x180001b99  lea     rdx, [rsi+10h]; void *
0x180001b9d  call    ?Write@File@@QEAAJPEAXK@Z; File::Write(void *,ulong)
0x180001ba2  mov     edi, eax
0x180001ba4  test    eax, eax
0x180001ba6  jnz     short loc_180001BD3
0x180001ba8  mov     rcx, rsi; this
0x180001bab  call    ?Flush@File@@QEAAJXZ; File::Flush(void)
0x180001bb0  mov     edi, eax
0x180001bb2  test    eax, eax
0x180001bb4  jnz     short loc_180001BD3
0x180001bb6  mov     r8, [rsi+8]; unsigned __int16 *
0x180001bba  lea     rcx, WofTaskCompleteHashFileEventId; EventDescriptor
0x180001bc1  mov     rdx, [rsi+90h]; unsigned __int16 *
0x180001bc8  call    ?LogFile@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG1@Z; LogFile(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *)
0x180001bcd  jmp     short loc_180001BD3
0x180001bcf  bts     edi, 1Ch
0x180001bd3  call    cs:__imp_GetProcessHeap
0x180001bd9  mov     r8, r15; lpMem
0x180001bdc  xor     edx, edx; dwFlags
0x180001bde  mov     rcx, rax; hHeap
0x180001be1  call    cs:__imp_HeapFree
0x180001be7  jmp     short loc_180001BED
0x180001be9  bts     edi, 1Ch
0x180001bed  mov     rcx, [rsp+68h+phHash]; hHash
0x180001bf2  test    rcx, rcx
0x180001bf5  jz      short loc_180001BFD
0x180001bf7  call    cs:__imp_BCryptDestroyHash
0x180001bfd  lea     r11, [rsp+68h+var_28]
0x180001c02  mov     eax, edi
0x180001c04  mov     rbx, [r11+30h]
0x180001c08  mov     rbp, [r11+48h]
0x180001c0c  mov     rsp, r11
0x180001c0f  pop     r15
0x180001c11  pop     r14
0x180001c13  pop     r13
0x180001c15  pop     rdi
0x180001c16  pop     rsi
0x180001c17  retn
```
