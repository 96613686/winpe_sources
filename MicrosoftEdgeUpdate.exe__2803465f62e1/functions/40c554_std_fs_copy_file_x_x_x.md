# __std_fs_copy_file(x,x,x)

- ea: `0x40c554`
- end: `0x40c67d`
- name: `___std_fs_copy_file@12`
- size: `297`
- prototype: `int __stdcall(LPCWSTR lpFileName, LPCWSTR, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x409923`

## callees

- `0x40c3c1`
- `0x40c473`
- `0x40c4a8`
- `0x40c554`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40c5a9`
- `KERNEL32!GetLastError` at `0x40c5e7`
- `KERNEL32!GetLastError` at `0x40c5a9`
- `KERNEL32!GetLastError` at `0x40c5e7`
- `KERNEL32!CreateFileW` at `0x40c59c`
- `KERNEL32!CreateFileW` at `0x40c5da`
- `KERNEL32!CreateFileW` at `0x40c59c`
- `KERNEL32!CreateFileW` at `0x40c5da`

## pseudocode

```c
int __stdcall __std_fs_copy_file(LPCWSTR lpFileName, LPCWSTR a2, char a3)
{
  int v3; // ebx
  int result; // eax
  int v5; // edx
  HANDLE FileW; // edi
  HANDLE v7; // esi
  int v8; // esi
  __int64 v9; // [esp+Ch] [ebp-10h] BYREF
  __int64 v10; // [esp+14h] [ebp-8h] BYREF

  v3 = a3 & 0xF;
  if ( v3 == 2 )
    return `anonymous namespace'::__vcp_Copyfile(lpFileName, a2, 0);
  result = `anonymous namespace'::__vcp_Copyfile(lpFileName, a2, 1u);
  if ( v5 == 80 && (a3 & 0xF) != 0 )
  {
    FileW = CreateFileW(lpFileName, 0x81u, 0, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1 && GetLastError() )
    {
      LOBYTE(v9) = 0;
      __std_fs_close_handle((HANDLE)0xFFFFFFFF);
      return v9;
    }
    v7 = CreateFileW(a2, 0x82u, 0, 0, 3u, 0, 0);
    if ( v7 == (HANDLE)-1 )
    {
      HIDWORD(v10) = GetLastError();
      if ( HIDWORD(v10) )
      {
        LOBYTE(v9) = 0;
        __std_fs_close_handle((HANDLE)0xFFFFFFFF);
LABEL_17:
        v8 = v9;
        __std_fs_close_handle(FileW);
        return v8;
      }
    }
    if ( v3 == 1 )
      goto LABEL_15;
    if ( `anonymous namespace'::_Get_last_write_time_by_handle(FileW, &v10)
      || `anonymous namespace'::_Get_last_write_time_by_handle(v7, &v9) )
    {
      LOBYTE(v9) = 0;
LABEL_16:
      __std_fs_close_handle(v7);
      goto LABEL_17;
    }
    if ( v10 <= v9 )
    {
LABEL_15:
      LOBYTE(v9) = 0;
      goto LABEL_16;
    }
    __std_fs_close_handle(v7);
    __std_fs_close_handle(FileW);
    return `anonymous namespace'::__vcp_Copyfile(lpFileName, a2, 0);
  }
  return result;
}

```

## disassembly

```asm
0x40c554  push    ebp
0x40c555  mov     ebp, esp
0x40c557  sub     esp, 10h
0x40c55a  xor     eax, eax
0x40c55c  push    ebx
0x40c55d  mov     ebx, [ebp+arg_8]
0x40c560  and     ebx, 0Fh
0x40c563  push    esi
0x40c564  push    edi
0x40c565  cmp     ebx, 2
0x40c568  jz      loc_40C66A
0x40c56e  push    1
0x40c570  push    [ebp+arg_4]
0x40c573  push    [ebp+lpFileName]
0x40c576  call    ?__vcp_Copyfile@?A0x42551d01@@YG?AU__std_fs_copy_file_result@@QB_W0_N@Z
0x40c57b  cmp     edx, 50h ; 'P'
0x40c57e  jnz     loc_40C676
0x40c584  test    ebx, ebx
0x40c586  jz      loc_40C676
0x40c58c  xor     eax, eax
0x40c58e  push    eax; hTemplateFile
0x40c58f  push    eax; dwFlagsAndAttributes
0x40c590  push    3; dwCreationDisposition
0x40c592  push    eax; lpSecurityAttributes
0x40c593  push    eax; dwShareMode
0x40c594  push    81h; dwDesiredAccess
0x40c599  push    [ebp+lpFileName]; lpFileName
0x40c59c  call    ds:CreateFileW
0x40c5a2  mov     edi, eax
0x40c5a4  cmp     edi, 0FFFFFFFFh
0x40c5a7  jnz     short loc_40C5CA
0x40c5a9  call    ds:GetLastError
0x40c5af  mov     esi, eax
0x40c5b1  test    esi, esi
0x40c5b3  jz      short loc_40C5CA
0x40c5b5  xor     eax, eax
0x40c5b7  push    edi; hObject
0x40c5b8  mov     byte ptr [ebp+var_10], al
0x40c5bb  call    ___std_fs_close_handle@4
0x40c5c0  mov     eax, dword ptr [ebp+var_10]
0x40c5c3  mov     edx, esi
0x40c5c5  jmp     loc_40C676
0x40c5ca  xor     eax, eax
0x40c5cc  push    eax; hTemplateFile
0x40c5cd  push    eax; dwFlagsAndAttributes
0x40c5ce  push    3; dwCreationDisposition
0x40c5d0  push    eax; lpSecurityAttributes
0x40c5d1  push    eax; dwShareMode
0x40c5d2  push    82h; dwDesiredAccess
0x40c5d7  push    [ebp+arg_4]; lpFileName
0x40c5da  call    ds:CreateFileW
0x40c5e0  mov     esi, eax
0x40c5e2  cmp     esi, 0FFFFFFFFh
0x40c5e5  jnz     short loc_40C604
0x40c5e7  call    ds:GetLastError
0x40c5ed  mov     dword ptr [ebp+var_8+4], eax
0x40c5f0  test    eax, eax
0x40c5f2  jz      short loc_40C604
0x40c5f4  xor     eax, eax
0x40c5f6  push    esi; hObject
0x40c5f7  mov     byte ptr [ebp+var_10], al
0x40c5fa  call    ___std_fs_close_handle@4
0x40c5ff  mov     ebx, dword ptr [ebp+var_8+4]
0x40c602  jmp     short loc_40C64D
0x40c604  cmp     ebx, 1
0x40c607  jz      short loc_40C642
0x40c609  lea     eax, [ebp+var_8]
0x40c60c  push    eax
0x40c60d  push    edi
0x40c60e  call    ?_Get_last_write_time_by_handle@?A0xfc2c848a@@YG?AW4__std_win_error@@QAXQA_J@Z
0x40c613  mov     ebx, eax
0x40c615  test    ebx, ebx
0x40c617  jz      short loc_40C620
0x40c619  xor     eax, eax
0x40c61b  mov     byte ptr [ebp+var_10], al
0x40c61e  jmp     short loc_40C647
0x40c620  lea     eax, [ebp+var_10]
0x40c623  push    eax
0x40c624  push    esi
0x40c625  call    ?_Get_last_write_time_by_handle@?A0xfc2c848a@@YG?AW4__std_win_error@@QAXQA_J@Z
0x40c62a  mov     ebx, eax
0x40c62c  test    ebx, ebx
0x40c62e  jnz     short loc_40C619
0x40c630  mov     eax, dword ptr [ebp+var_8+4]
0x40c633  cmp     eax, dword ptr [ebp+var_10+4]
0x40c636  jg      short loc_40C65C
0x40c638  jl      short loc_40C642
0x40c63a  mov     eax, dword ptr [ebp+var_8]
0x40c63d  cmp     eax, dword ptr [ebp+var_10]
0x40c640  ja      short loc_40C65C
0x40c642  xor     ebx, ebx
0x40c644  mov     byte ptr [ebp+var_10], bl
0x40c647  push    esi; hObject
0x40c648  call    ___std_fs_close_handle@4
0x40c64d  mov     esi, dword ptr [ebp+var_10]
0x40c650  push    edi; hObject
0x40c651  call    ___std_fs_close_handle@4
0x40c656  mov     eax, esi
0x40c658  mov     edx, ebx
0x40c65a  jmp     short loc_40C676
0x40c65c  push    esi; hObject
0x40c65d  call    ___std_fs_close_handle@4
0x40c662  push    edi; hObject
0x40c663  call    ___std_fs_close_handle@4
0x40c668  xor     eax, eax
0x40c66a  push    eax
0x40c66b  push    [ebp+arg_4]
0x40c66e  push    [ebp+lpFileName]
0x40c671  call    ?__vcp_Copyfile@?A0x42551d01@@YG?AU__std_fs_copy_file_result@@QB_W0_N@Z
0x40c676  pop     edi
0x40c677  pop     esi
0x40c678  pop     ebx
0x40c679  leave
0x40c67a  retn    0Ch
```
