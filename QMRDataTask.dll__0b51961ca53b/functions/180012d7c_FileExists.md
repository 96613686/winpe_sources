# FileExists

- ea: `0x180012d7c`
- end: `0x180012e15`
- name: `FileExists`
- size: `153`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006a60`
- `0x180007490`
- `0x18000a520`
- `0x18000ace0`
- `0x18000b290`
- `0x18000c5b0`
- `0x180010400`

## callees

- `0x180012d7c`
- `0x18001331c`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180012dab`
- `KERNEL32!GetFileAttributesW` at `0x180012dab`
- `KERNEL32!GetLastError` at `0x180012dc6`
- `KERNEL32!GetLastError` at `0x180012de4`
- `KERNEL32!GetLastError` at `0x180012dc6`
- `KERNEL32!GetLastError` at `0x180012de4`
- `KERNEL32!GetProcessHeap` at `0x180012dce`
- `KERNEL32!GetProcessHeap` at `0x180012dce`
- `KERNEL32!HeapFree` at `0x180012ddc`
- `KERNEL32!HeapFree` at `0x180012ddc`
- `KERNEL32!SetLastError` at `0x180012dee`
- `KERNEL32!SetLastError` at `0x180012dfd`
- `KERNEL32!SetLastError` at `0x180012dee`
- `KERNEL32!SetLastError` at `0x180012dfd`

## pseudocode

```c
__int64 __fastcall FileExists(const wchar_t *a1)
{
  unsigned int v1; // esi
  const WCHAR *v2; // rax
  WCHAR *v3; // rdi
  DWORD FileAttributesW; // eax
  int v5; // eax
  int LastError; // ebx
  HANDLE ProcessHeap; // rax

  if ( a1 && *a1 )
  {
    v1 = 0;
    v2 = (const WCHAR *)PrepareUnicodePathEx(a1);
    v3 = (WCHAR *)v2;
    if ( v2 )
    {
      FileAttributesW = GetFileAttributesW(v2);
      if ( FileAttributesW == -1 )
      {
        LastError = GetLastError();
      }
      else
      {
        v5 = FileAttributesW & 0x10;
        LOBYTE(v1) = v5 == 0;
        LastError = v5 != 0 ? 2 : 0;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
    }
    else
    {
      LastError = GetLastError();
    }
    SetLastError(LastError);
    return v1;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x180012d7c  mov     [rsp+arg_0], rbx
0x180012d81  mov     [rsp+arg_8], rsi
0x180012d86  push    rdi
0x180012d87  sub     rsp, 20h
0x180012d8b  test    rcx, rcx
0x180012d8e  jz      short loc_180012DF8
0x180012d90  xor     eax, eax
0x180012d92  cmp     ax, [rcx]
0x180012d95  jz      short loc_180012DF8
0x180012d97  xor     edx, edx
0x180012d99  xor     esi, esi
0x180012d9b  call    PrepareUnicodePathEx
0x180012da0  mov     rdi, rax
0x180012da3  test    rax, rax
0x180012da6  jz      short loc_180012DE4
0x180012da8  mov     rcx, rax; lpFileName
0x180012dab  call    cs:__imp_GetFileAttributesW
0x180012db1  cmp     eax, 0FFFFFFFFh
0x180012db4  jz      short loc_180012DC6
0x180012db6  and     eax, 10h
0x180012db9  setz    sil
0x180012dbd  neg     eax
0x180012dbf  sbb     ebx, ebx
0x180012dc1  and     ebx, 2
0x180012dc4  jmp     short loc_180012DCE
0x180012dc6  call    cs:__imp_GetLastError
0x180012dcc  mov     ebx, eax
0x180012dce  call    cs:__imp_GetProcessHeap
0x180012dd4  mov     r8, rdi; lpMem
0x180012dd7  xor     edx, edx; dwFlags
0x180012dd9  mov     rcx, rax; hHeap
0x180012ddc  call    cs:__imp_HeapFree
0x180012de2  jmp     short loc_180012DEC
0x180012de4  call    cs:__imp_GetLastError
0x180012dea  mov     ebx, eax
0x180012dec  mov     ecx, ebx; dwErrCode
0x180012dee  call    cs:__imp_SetLastError
0x180012df4  mov     eax, esi
0x180012df6  jmp     short loc_180012E05
0x180012df8  mov     ecx, 57h ; 'W'; dwErrCode
0x180012dfd  call    cs:__imp_SetLastError
0x180012e03  xor     eax, eax
0x180012e05  mov     rbx, [rsp+28h+arg_0]
0x180012e0a  mov     rsi, [rsp+28h+arg_8]
0x180012e0f  add     rsp, 20h
0x180012e13  pop     rdi
0x180012e14  retn
```
