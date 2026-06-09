# UpdateReserveManager::QueryReserveAreaInternal(_STORAGE_RESERVE_ID,Windows::AutoNewArrayPtr<uchar> *)

- ea: `0x18001ce74`
- end: `0x18001cfde`
- name: `?QueryReserveAreaInternal@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@PEAV?$AutoNewArrayPtr@E@Windows@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(HANDLE *, int, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180015b34`
- `0x18001cb28`

## callees

- `0x180003870`
- `0x180003c84`
- `0x1800044e0`
- `0x180015ad0`
- `0x18001ce74`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18001cf46`
- `ntdll!NtFsControlFile` at `0x18001cf46`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::QueryReserveAreaInternal(HANDLE *a1, int a2, void **a3)
{
  __int64 result; // rax
  ULONG InputBufferLength; // r14d
  ULONG v8; // r15d
  _DWORD *OutputBuffer; // rax
  _DWORD *v10; // rbx
  NTSTATUS v11; // edi
  int v12; // ecx
  unsigned int v13; // r12d
  int v14; // edi
  void *v15; // rcx
  __int128 InputBuffer; // [rsp+68h] [rbp-9h] BYREF
  int v17; // [rsp+78h] [rbp+7h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+Fh] BYREF

  result = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)a1);
  if ( (int)result >= 0 )
  {
    InputBuffer = 0;
    v17 = 0;
    if ( a2 )
    {
      *(_QWORD *)&InputBuffer = 1;
      *((_QWORD *)&InputBuffer + 1) = 0x100000010LL;
      v17 = a2;
      InputBufferLength = 20;
    }
    else
    {
      InputBufferLength = 0;
    }
    v8 = 32;
    OutputBuffer = operator new[](0x20u);
    IoStatusBlock = 0;
    while ( 1 )
    {
      v10 = OutputBuffer;
      v11 = NtFsControlFile(
              a1[16],
              0,
              0,
              0,
              &IoStatusBlock,
              0x90414u,
              &InputBuffer,
              InputBufferLength,
              OutputBuffer,
              v8);
      if ( v11 != -2147483643 )
        break;
      v12 = 1;
      if ( v10[1] > 1u )
        v12 = v10[1];
      v13 = 24 * v12 + 8;
      if ( v13 <= v8 )
        break;
      operator delete(v10);
      OutputBuffer = operator new[](v13);
      v8 = v13;
    }
    v14 = v11 | 0x10000000;
    if ( v14 >= 0 )
    {
      v15 = *a3;
      *a3 = v10;
      if ( v15 )
        operator delete(v15);
      return 0;
    }
    else
    {
      operator delete(v10);
      return (unsigned int)v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ce74  mov     rax, rsp
0x18001ce77  push    rbp
0x18001ce78  push    rsi
0x18001ce79  push    rdi
0x18001ce7a  push    r12
0x18001ce7c  push    r13
0x18001ce7e  push    r14
0x18001ce80  push    r15
0x18001ce82  lea     rbp, [rax-5Fh]
0x18001ce86  sub     rsp, 90h
0x18001ce8d  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x18001ce95  mov     [rax+10h], rbx
0x18001ce99  mov     rax, cs:__security_cookie
0x18001cea0  xor     rax, rsp
0x18001cea3  mov     [rbp+57h+var_38], rax
0x18001cea7  mov     rsi, r8
0x18001ceaa  mov     ebx, edx
0x18001ceac  mov     r13, rcx
0x18001ceaf  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001ceb4  test    eax, eax
0x18001ceb6  js      loc_18001CFB7
0x18001cebc  xorps   xmm0, xmm0
0x18001cebf  xor     eax, eax
0x18001cec1  movups  [rbp+57h+var_60], xmm0
0x18001cec5  mov     [rbp+57h+var_50], eax
0x18001cec8  mov     eax, 1
0x18001cecd  test    ebx, ebx
0x18001cecf  jz      short loc_18001CEE8
0x18001ced1  mov     qword ptr [rbp+57h+var_60], rax
0x18001ced5  mov     dword ptr [rbp+57h+var_60+8], 10h
0x18001cedc  mov     dword ptr [rbp+57h+var_60+0Ch], eax
0x18001cedf  mov     [rbp+57h+var_50], ebx
0x18001cee2  lea     r14d, [rax+13h]
0x18001cee6  jmp     short loc_18001CEEB
0x18001cee8  xor     r14d, r14d
0x18001ceeb  mov     [rbp+57h+var_70], 0
0x18001cef3  mov     r15d, 20h ; ' '
0x18001cef9  mov     ecx, r15d; unsigned __int64
0x18001cefc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001cf01  xorps   xmm0, xmm0
0x18001cf04  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x18001cf08  mov     r12, rax
0x18001cf0b  mov     rbx, rax
0x18001cf0e  mov     [rsp+48h], r15d; OutputBufferLength
0x18001cf13  mov     [rsp+0C0h+OutputBuffer], rax; OutputBuffer
0x18001cf18  mov     [rsp+0C0h+InputBufferLength], r14d; InputBufferLength
0x18001cf1d  lea     rax, [rbp+57h+var_60]
0x18001cf21  mov     [rsp+0C0h+InputBuffer], rax; InputBuffer
0x18001cf26  mov     [rsp+0C0h+FsControlCode], 90414h; FsControlCode
0x18001cf2e  lea     rax, [rbp+57h+var_48]
0x18001cf32  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x18001cf37  xor     r9d, r9d; ApcContext
0x18001cf3a  xor     r8d, r8d; ApcRoutine
0x18001cf3d  xor     edx, edx; Event
0x18001cf3f  mov     rcx, [r13+80h]; FileHandle
0x18001cf46  call    cs:__imp_NtFsControlFile
0x18001cf4c  mov     edi, eax
0x18001cf4e  cmp     eax, 80000005h
0x18001cf53  jnz     short loc_18001CF91
0x18001cf55  mov     ecx, 1
0x18001cf5a  cmp     [rbx+4], ecx
0x18001cf5d  cmova   ecx, [rbx+4]
0x18001cf61  lea     ecx, [rcx+rcx*2]
0x18001cf64  lea     r12d, ds:8[rcx*8]
0x18001cf6c  cmp     r12d, r15d
0x18001cf6f  jbe     short loc_18001CF91
0x18001cf71  mov     rcx, rbx; void *
0x18001cf74  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cf79  mov     [rbp+57h+var_70], 0
0x18001cf81  mov     ecx, r12d; unsigned __int64
0x18001cf84  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001cf89  mov     r15d, r12d
0x18001cf8c  jmp     loc_18001CF08
0x18001cf91  or      edi, 10000000h
0x18001cf97  jge     short loc_18001CFA5
0x18001cf99  mov     rcx, rbx; void *
0x18001cf9c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cfa1  mov     eax, edi
0x18001cfa3  jmp     short loc_18001CFB7
0x18001cfa5  mov     rcx, [rsi]; void *
0x18001cfa8  mov     [rsi], rbx
0x18001cfab  test    rcx, rcx
0x18001cfae  jz      short loc_18001CFB5
0x18001cfb0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cfb5  xor     eax, eax
0x18001cfb7  mov     rcx, [rbp+57h+var_38]
0x18001cfbb  xor     rcx, rsp; StackCookie
0x18001cfbe  call    __security_check_cookie
0x18001cfc3  mov     rbx, [rsp+0C0h+arg_8]
0x18001cfcb  add     rsp, 90h
0x18001cfd2  pop     r15
0x18001cfd4  pop     r14
0x18001cfd6  pop     r13
0x18001cfd8  pop     r12
0x18001cfda  pop     rdi
0x18001cfdb  pop     rsi
0x18001cfdc  pop     rbp
0x18001cfdd  retn
```
