# sub_14000FCAC

- ea: `0x14000fcac`
- end: `0x14000fee0`
- name: `sub_14000FCAC`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000e120`

## callees

- `0x14000fcac`
- `0x140010154`
- `0x1400101b8`
- `0x140050a9c`
- `0x14005a8a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000fd91`
- `KERNEL32!GetLastError` at `0x14000fe2c`
- `KERNEL32!GetLastError` at `0x14000fd91`
- `KERNEL32!GetLastError` at `0x14000fe2c`
- `KERNEL32!CloseHandle` at `0x14000fe92`
- `KERNEL32!CloseHandle` at `0x14000fea0`
- `KERNEL32!CloseHandle` at `0x14000feae`
- `KERNEL32!CloseHandle` at `0x14000fe92`
- `KERNEL32!CloseHandle` at `0x14000fea0`
- `KERNEL32!CloseHandle` at `0x14000feae`
- `KERNEL32!ReleaseSemaphore` at `0x14000fe5e`
- `KERNEL32!ReleaseSemaphore` at `0x14000fe84`
- `KERNEL32!ReleaseSemaphore` at `0x14000fe5e`
- `KERNEL32!ReleaseSemaphore` at `0x14000fe84`

## string_xrefs

- `0x14000fce6`: `_RwLockReaderSem`
- `0x14000fdb2`: `_RwLockWriterSem`

## pseudocode

```c
__int64 __fastcall sub_14000FCAC(__int64 a1, volatile __int32 *a2, __int64 a3)
{
  __int64 v4; // rsi
  void *v5; // rbx
  void *v6; // rdi
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdx
  HANDLE v12; // r13
  unsigned int v13; // esi
  HANDLE v14; // r14
  signed int v15; // eax
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  HANDLE v20; // r12
  signed int LastError; // eax
  LONG v22; // edx
  LONG v23; // edx
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+28h] [rbp-D8h]
  int v27; // [rsp+28h] [rbp-D8h]
  HANDLE hSemaphore; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v29; // [rsp+48h] [rbp-B8h] BYREF
  int PreviousCount; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h]
  char v32[1024]; // [rsp+60h] [rbp-A0h] BYREF

  v31 = a3;
  PreviousCount = 0;
  v4 = a3;
  v5 = 0;
  hSemaphore = 0;
  v6 = 0;
  v29 = 0;
  _InterlockedExchange(a2 + 6, 1);
  _InterlockedExchange(a2 + 2, 0);
  v8 = sub_1400101B8(v32, a2, *(_QWORD *)(a1 + 1080), "_RwLockReaderSem", *(_DWORD *)(a1 + 44));
  sub_140010154(&v32[v8], 1024 - v8, v4);
  if ( !(unsigned int)sub_140050A9C(
                        &hSemaphore,
                        v32,
                        v9,
                        v10,
                        &v29,
                        v26,
                        *((_DWORD *)&qword_140064C90 + *(int *)(a1 + 44))) )
    goto LABEL_2;
  v14 = hSemaphore;
  if ( hSemaphore )
  {
LABEL_8:
    v16 = *(_QWORD *)(a1 + 1080);
    v25 = *(_DWORD *)(a1 + 44);
    hSemaphore = 0;
    v17 = sub_1400101B8(v32, v11, v16, "_RwLockWriterSem", v25);
    sub_140010154(&v32[v17], 1024 - v17, v4);
    if ( (unsigned int)sub_140050A9C(
                         &hSemaphore,
                         v32,
                         v18,
                         v19,
                         &v29,
                         v27,
                         *((_DWORD *)&qword_140064C90 + *(int *)(a1 + 44))) )
    {
      v20 = hSemaphore;
      v13 = 0;
      if ( !hSemaphore )
      {
        LastError = GetLastError();
        v13 = (unsigned __int16)LastError | 0x80070000;
        v5 = v14;
        if ( LastError <= 0 )
          v13 = LastError;
        if ( v13 )
          goto LABEL_24;
      }
      v12 = 0;
      if ( *a2 )
      {
        v22 = _InterlockedExchange(a2, 0);
        if ( v22 )
          ReleaseSemaphore(v14, v22, &PreviousCount);
      }
      v5 = v14;
      v6 = v20;
      if ( !*((_DWORD *)a2 + 1) || (v23 = _InterlockedExchange(a2 + 1, 0)) == 0 )
      {
LABEL_22:
        if ( v6 )
          CloseHandle(v6);
LABEL_24:
        if ( v5 )
          CloseHandle(v5);
        return v13;
      }
      ReleaseSemaphore(v20, v23, &PreviousCount);
LABEL_20:
      if ( v12 )
        CloseHandle(v12);
      goto LABEL_22;
    }
    v5 = v14;
LABEL_2:
    v12 = hSemaphore;
    v13 = -2147467259;
    goto LABEL_20;
  }
  v15 = GetLastError();
  v13 = (unsigned __int16)v15 | 0x80070000;
  if ( v15 <= 0 )
    v13 = v15;
  if ( !v13 )
  {
    v4 = v31;
    goto LABEL_8;
  }
  return v13;
}

```

## disassembly

```asm
0x14000fcac  mov     [rsp-8+arg_10], rbx
0x14000fcb1  push    rbp
0x14000fcb2  push    rsi
0x14000fcb3  push    rdi
0x14000fcb4  push    r12
0x14000fcb6  push    r13
0x14000fcb8  push    r14
0x14000fcba  push    r15
0x14000fcbc  lea     rbp, [rsp-370h]
0x14000fcc4  sub     rsp, 470h
0x14000fccb  mov     rax, cs:__security_cookie
0x14000fcd2  xor     rax, rsp
0x14000fcd5  mov     [rbp+3A0h+var_40], rax
0x14000fcdc  mov     r13, rcx
0x14000fcdf  mov     [rsp+4A0h+var_450], r8
0x14000fce4  xor     ecx, ecx
0x14000fce6  lea     r9, aRwlockreaderse; "_RwLockReaderSem"
0x14000fced  mov     [rsp+4A0h+PreviousCount], ecx
0x14000fcf1  mov     rsi, r8
0x14000fcf4  mov     ebx, ecx
0x14000fcf6  mov     [rsp+4A0h+hSemaphore], rcx
0x14000fcfb  mov     edi, ecx
0x14000fcfd  mov     [rsp+4A0h+var_458], ecx
0x14000fd01  lea     eax, [rcx+1]
0x14000fd04  mov     r15, rdx
0x14000fd07  xchg    eax, [rdx+18h]
0x14000fd0a  mov     eax, ecx
0x14000fd0c  lea     rcx, [rsp+4A0h+var_440]
0x14000fd11  xchg    eax, [rdx+8]
0x14000fd14  mov     eax, [r13+2Ch]
0x14000fd18  mov     r8, [r13+438h]
0x14000fd1f  mov     dword ptr [rsp+4A0h+var_480], eax
0x14000fd23  call    sub_1400101B8
0x14000fd28  mov     r12d, 400h
0x14000fd2e  lea     rcx, [rsp+4A0h+var_440]
0x14000fd33  mov     edx, r12d
0x14000fd36  add     rcx, rax
0x14000fd39  sub     rdx, rax
0x14000fd3c  mov     r8, rsi
0x14000fd3f  call    sub_140010154
0x14000fd44  movsxd  rax, dword ptr [r13+2Ch]
0x14000fd48  lea     rcx, qword_140064C90
0x14000fd4f  lea     rdx, [rsp+4A0h+var_440]
0x14000fd54  mov     eax, [rcx+rax*4]
0x14000fd57  lea     rcx, [rsp+4A0h+hSemaphore]
0x14000fd5c  mov     [rsp+4A0h+var_470], eax
0x14000fd60  lea     rax, [rsp+4A0h+var_458]
0x14000fd65  mov     [rsp+4A0h+var_480], rax
0x14000fd6a  call    sub_140050A9C
0x14000fd6f  test    eax, eax
0x14000fd71  jnz     short loc_14000FD82
0x14000fd73  mov     r13, [rsp+4A0h+hSemaphore]
0x14000fd78  mov     esi, 80004005h
0x14000fd7d  jmp     loc_14000FE8A
0x14000fd82  mov     r14, [rsp+4A0h+hSemaphore]
0x14000fd87  mov     ebx, 80070000h
0x14000fd8c  test    r14, r14
0x14000fd8f  jnz     short loc_14000FDAE
0x14000fd91  call    cs:GetLastError
0x14000fd97  movzx   esi, ax
0x14000fd9a  or      esi, ebx
0x14000fd9c  test    eax, eax
0x14000fd9e  cmovle  esi, eax
0x14000fda1  test    esi, esi
0x14000fda3  jnz     loc_14000FEB4
0x14000fda9  mov     rsi, [rsp+4A0h+var_450]
0x14000fdae  mov     eax, [r13+2Ch]
0x14000fdb2  lea     r9, aRwlockwriterse; "_RwLockWriterSem"
0x14000fdb9  mov     r8, [r13+438h]
0x14000fdc0  lea     rcx, [rsp+4A0h+var_440]
0x14000fdc5  mov     dword ptr [rsp+4A0h+var_480], eax
0x14000fdc9  mov     [rsp+4A0h+hSemaphore], rdi
0x14000fdce  call    sub_1400101B8
0x14000fdd3  sub     r12, rax
0x14000fdd6  lea     rcx, [rsp+4A0h+var_440]
0x14000fddb  add     rcx, rax
0x14000fdde  mov     rdx, r12
0x14000fde1  mov     r8, rsi
0x14000fde4  call    sub_140010154
0x14000fde9  movsxd  rax, dword ptr [r13+2Ch]
0x14000fded  lea     rcx, qword_140064C90
0x14000fdf4  lea     rdx, [rsp+4A0h+var_440]
0x14000fdf9  mov     eax, [rcx+rax*4]
0x14000fdfc  lea     rcx, [rsp+4A0h+hSemaphore]
0x14000fe01  mov     [rsp+4A0h+var_470], eax
0x14000fe05  lea     rax, [rsp+4A0h+var_458]
0x14000fe0a  mov     [rsp+4A0h+var_480], rax
0x14000fe0f  call    sub_140050A9C
0x14000fe14  test    eax, eax
0x14000fe16  jnz     short loc_14000FE20
0x14000fe18  mov     rbx, r14
0x14000fe1b  jmp     loc_14000FD73
0x14000fe20  mov     r12, [rsp+4A0h+hSemaphore]
0x14000fe25  xor     esi, esi
0x14000fe27  test    r12, r12
0x14000fe2a  jnz     short loc_14000FE43
0x14000fe2c  call    cs:GetLastError
0x14000fe32  movzx   esi, ax
0x14000fe35  or      esi, ebx
0x14000fe37  mov     rbx, r14
0x14000fe3a  test    eax, eax
0x14000fe3c  cmovle  esi, eax
0x14000fe3f  test    esi, esi
0x14000fe41  jnz     short loc_14000FEA6
0x14000fe43  mov     eax, [r15]
0x14000fe46  xor     r13d, r13d
0x14000fe49  test    eax, eax
0x14000fe4b  jz      short loc_14000FE64
0x14000fe4d  xor     edx, edx
0x14000fe4f  xchg    edx, [r15]; lReleaseCount
0x14000fe52  test    edx, edx
0x14000fe54  jz      short loc_14000FE64
0x14000fe56  lea     r8, [rsp+4A0h+PreviousCount]; lpPreviousCount
0x14000fe5b  mov     rcx, r14; hSemaphore
0x14000fe5e  call    cs:ReleaseSemaphore
0x14000fe64  mov     eax, [r15+4]
0x14000fe68  mov     rbx, r14
0x14000fe6b  mov     rdi, r12
0x14000fe6e  test    eax, eax
0x14000fe70  jz      short loc_14000FE98
0x14000fe72  xor     edx, edx
0x14000fe74  xchg    edx, [r15+4]; lReleaseCount
0x14000fe78  test    edx, edx
0x14000fe7a  jz      short loc_14000FE98
0x14000fe7c  lea     r8, [rsp+4A0h+PreviousCount]; lpPreviousCount
0x14000fe81  mov     rcx, r12; hSemaphore
0x14000fe84  call    cs:ReleaseSemaphore
0x14000fe8a  test    r13, r13
0x14000fe8d  jz      short loc_14000FE98
0x14000fe8f  mov     rcx, r13; hObject
0x14000fe92  call    cs:CloseHandle
0x14000fe98  test    rdi, rdi
0x14000fe9b  jz      short loc_14000FEA6
0x14000fe9d  mov     rcx, rdi; hObject
0x14000fea0  call    cs:CloseHandle
0x14000fea6  test    rbx, rbx
0x14000fea9  jz      short loc_14000FEB4
0x14000feab  mov     rcx, rbx; hObject
0x14000feae  call    cs:CloseHandle
0x14000feb4  mov     eax, esi
0x14000feb6  mov     rcx, [rbp+3A0h+var_40]
0x14000febd  xor     rcx, rsp; StackCookie
0x14000fec0  call    __security_check_cookie
0x14000fec5  mov     rbx, [rsp+4A0h+arg_10]
0x14000fecd  add     rsp, 470h
0x14000fed4  pop     r15
0x14000fed6  pop     r14
0x14000fed8  pop     r13
0x14000feda  pop     r12
0x14000fedc  pop     rdi
0x14000fedd  pop     rsi
0x14000fede  pop     rbp
0x14000fedf  retn
```
