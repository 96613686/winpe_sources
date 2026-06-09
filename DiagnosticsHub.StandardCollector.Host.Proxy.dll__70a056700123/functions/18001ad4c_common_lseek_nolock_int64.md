# common_lseek_nolock___int64_

- ea: `0x18001ad4c`
- end: `0x18001adfb`
- name: `common_lseek_nolock___int64_`
- size: `175`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001aba0`
- `0x18001b0e8`
- `0x18001b184`

## callees

- `0x180007740`
- `0x180014618`
- `0x18001ad4c`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x18001ad9e`
- `KERNEL32!SetFilePointerEx` at `0x18001ad9e`
- `KERNEL32!GetLastError` at `0x18001ada8`
- `KERNEL32!GetLastError` at `0x18001ada8`

## pseudocode

```c
LARGE_INTEGER __fastcall common_lseek_nolock___int64_(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  __int64 v4; // rdi
  void *osfhandle; // rax
  LARGE_INTEGER result; // rax
  DWORD LastError; // eax
  LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-18h] BYREF

  v4 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return (LARGE_INTEGER)-1LL;
  }
  NewFilePointer.QuadPart = 0;
  if ( !SetFilePointerEx(osfhandle, a2, &NewFilePointer, a3) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error_ptd(LastError, a4);
    return (LARGE_INTEGER)-1LL;
  }
  result = NewFilePointer;
  if ( NewFilePointer.QuadPart == -1 )
    return (LARGE_INTEGER)-1LL;
  *(_BYTE *)(_pioinfo[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x18001ad4c  mov     [rsp+arg_0], rbx
0x18001ad51  mov     [rsp+arg_8], rbp
0x18001ad56  mov     [rsp+arg_10], rsi
0x18001ad5b  push    rdi
0x18001ad5c  sub     rsp, 30h
0x18001ad60  movsxd  rdi, ecx
0x18001ad63  mov     rbx, r9
0x18001ad66  mov     ecx, edi; FileHandle
0x18001ad68  mov     esi, r8d
0x18001ad6b  mov     rbp, rdx
0x18001ad6e  call    _get_osfhandle
0x18001ad73  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ad77  jnz     short loc_18001AD8A
0x18001ad79  mov     byte ptr [rbx+30h], 1
0x18001ad7d  mov     dword ptr [rbx+2Ch], 9
0x18001ad84  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ad88  jmp     short loc_18001ADE6
0x18001ad8a  and     qword ptr [rsp+38h+NewFilePointer], 0
0x18001ad90  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x18001ad95  mov     r9d, esi; dwMoveMethod
0x18001ad98  mov     rdx, rbp; liDistanceToMove
0x18001ad9b  mov     rcx, rax; hFile
0x18001ad9e  call    cs:__imp_SetFilePointerEx
0x18001ada4  test    eax, eax
0x18001ada6  jnz     short loc_18001ADBA
0x18001ada8  call    cs:__imp_GetLastError
0x18001adae  mov     ecx, eax
0x18001adb0  mov     rdx, rbx
0x18001adb3  call    __acrt_errno_map_os_error_ptd
0x18001adb8  jmp     short loc_18001AD84
0x18001adba  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x18001adbf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001adc3  jz      short loc_18001AD84
0x18001adc5  mov     rdx, rdi
0x18001adc8  lea     r8, __pioinfo
0x18001adcf  and     edx, 3Fh
0x18001add2  mov     rcx, rdi
0x18001add5  sar     rcx, 6
0x18001add9  lea     rdx, [rdx+rdx*8]
0x18001addd  mov     rcx, [r8+rcx*8]
0x18001ade1  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x18001ade6  mov     rbx, [rsp+38h+arg_0]
0x18001adeb  mov     rbp, [rsp+38h+arg_8]
0x18001adf0  mov     rsi, [rsp+38h+arg_10]
0x18001adf5  add     rsp, 30h
0x18001adf9  pop     rdi
0x18001adfa  retn
```
