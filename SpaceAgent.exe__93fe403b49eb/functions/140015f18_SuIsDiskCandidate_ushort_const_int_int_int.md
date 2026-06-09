# SuIsDiskCandidate(ushort const *,int *,int *,int *)

- ea: `0x140015f18`
- end: `0x140016000`
- name: `?SuIsDiskCandidate@@YAHPEBGPEAH11@Z`
- size: `232`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140015e10`

## callees

- `0x140015f18`
- `0x140016008`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140015fa5`
- `KERNEL32!CloseHandle` at `0x140015fa5`
- `KERNEL32!SetLastError` at `0x140015feb`
- `KERNEL32!SetLastError` at `0x140015feb`
- `KERNEL32!GetLastError` at `0x140015f77`
- `KERNEL32!GetLastError` at `0x140015f9a`
- `KERNEL32!GetLastError` at `0x140015fb1`
- `KERNEL32!GetLastError` at `0x140015f77`
- `KERNEL32!GetLastError` at `0x140015f9a`
- `KERNEL32!GetLastError` at `0x140015fb1`
- `KERNEL32!CreateFileW` at `0x140015f66`
- `KERNEL32!CreateFileW` at `0x140015f66`

## pseudocode

```c
__int64 __fastcall SuIsDiskCandidate(const unsigned __int16 *a1, int *a2, int *a3, int *a4)
{
  HANDLE FileW; // rax
  void *v8; // rbx
  unsigned int v9; // ebx
  DWORD LastError; // edi
  int IsDiskCandidateByHandle; // ebp
  int v13; // [rsp+40h] [rbp-48h] BYREF
  int v14; // [rsp+44h] [rbp-44h] BYREF
  int v15[16]; // [rsp+48h] [rbp-40h] BYREF

  v13 = 0;
  v14 = 0;
  v15[0] = 0;
  FileW = CreateFileW(a1, 0x20000u, 3u, 0, 3u, 0, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v9 = 0;
    LastError = GetLastError();
    goto LABEL_7;
  }
  IsDiskCandidateByHandle = SuIsDiskCandidateByHandle(FileW, &v13, &v14, v15);
  LastError = GetLastError();
  v9 = CloseHandle(v8);
  if ( !IsDiskCandidateByHandle )
  {
    v9 = 0;
    goto LABEL_7;
  }
  LastError = GetLastError();
  if ( !v9 )
  {
LABEL_7:
    *a2 = 0;
    *a3 = 0;
    *a4 = 0;
    goto LABEL_8;
  }
  *a2 = v13;
  *a3 = v14;
  *a4 = v15[0];
LABEL_8:
  SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x140015f18  mov     rax, rsp
0x140015f1b  push    rbx
0x140015f1c  push    rbp
0x140015f1d  push    rsi
0x140015f1e  push    rdi
0x140015f1f  push    r14
0x140015f21  push    r15
0x140015f23  sub     rsp, 58h
0x140015f27  mov     qword ptr [rax-58h], 0
0x140015f2f  mov     r14, r8
0x140015f32  mov     r8d, 3; dwShareMode
0x140015f38  mov     dword ptr [rax-60h], 0
0x140015f3f  mov     rsi, r9
0x140015f42  mov     [rax-68h], r8d
0x140015f46  mov     r15, rdx
0x140015f49  mov     dword ptr [rax-48h], 0
0x140015f50  xor     r9d, r9d; lpSecurityAttributes
0x140015f53  mov     dword ptr [rax-44h], 0
0x140015f5a  mov     edx, 20000h; dwDesiredAccess
0x140015f5f  mov     dword ptr [rax-40h], 0
0x140015f66  call    cs:__imp_CreateFileW
0x140015f6c  mov     rbx, rax
0x140015f6f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140015f73  jnz     short loc_140015F81
0x140015f75  xor     ebx, ebx
0x140015f77  call    cs:__imp_GetLastError
0x140015f7d  mov     edi, eax
0x140015f7f  jmp     short loc_140015FD5
0x140015f81  lea     r9, [rsp+88h+var_40]; int *
0x140015f86  mov     rcx, rbx; void *
0x140015f89  lea     r8, [rsp+88h+var_44]; int *
0x140015f8e  lea     rdx, [rsp+88h+var_48]; int *
0x140015f93  call    ?SuIsDiskCandidateByHandle@@YAHPEAXPEAH11@Z; SuIsDiskCandidateByHandle(void *,int *,int *,int *)
0x140015f98  mov     ebp, eax
0x140015f9a  call    cs:__imp_GetLastError
0x140015fa0  mov     rcx, rbx; hObject
0x140015fa3  mov     edi, eax
0x140015fa5  call    cs:__imp_CloseHandle
0x140015fab  mov     ebx, eax
0x140015fad  test    ebp, ebp
0x140015faf  jz      short loc_140015FD3
0x140015fb1  call    cs:__imp_GetLastError
0x140015fb7  mov     edi, eax
0x140015fb9  test    ebx, ebx
0x140015fbb  jz      short loc_140015FD5
0x140015fbd  mov     eax, [rsp+88h+var_48]
0x140015fc1  mov     [r15], eax
0x140015fc4  mov     eax, [rsp+88h+var_44]
0x140015fc8  mov     [r14], eax
0x140015fcb  mov     eax, [rsp+88h+var_40]
0x140015fcf  mov     [rsi], eax
0x140015fd1  jmp     short loc_140015FE9
0x140015fd3  mov     ebx, ebp
0x140015fd5  mov     dword ptr [r15], 0
0x140015fdc  mov     dword ptr [r14], 0
0x140015fe3  mov     dword ptr [rsi], 0
0x140015fe9  mov     ecx, edi; dwErrCode
0x140015feb  call    cs:__imp_SetLastError
0x140015ff1  mov     eax, ebx
0x140015ff3  add     rsp, 58h
0x140015ff7  pop     r15
0x140015ff9  pop     r14
0x140015ffb  pop     rdi
0x140015ffc  pop     rsi
0x140015ffd  pop     rbp
0x140015ffe  pop     rbx
0x140015fff  retn
```
