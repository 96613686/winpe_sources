# common_lseek_do_seek_nolock

- ea: `0x1400717c4`
- end: `0x140071886`
- name: `common_lseek_do_seek_nolock`
- size: `194`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140071688`

## callees

- `0x14005afb4`
- `0x1400717c4`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x1400717ff`
- `KERNEL32!SetFilePointerEx` at `0x140071837`
- `KERNEL32!SetFilePointerEx` at `0x14007185a`
- `KERNEL32!SetFilePointerEx` at `0x1400717ff`
- `KERNEL32!SetFilePointerEx` at `0x140071837`
- `KERNEL32!SetFilePointerEx` at `0x14007185a`
- `KERNEL32!GetLastError` at `0x140071809`
- `KERNEL32!GetLastError` at `0x140071809`

## pseudocode

```c
__int64 __fastcall common_lseek_do_seek_nolock(HANDLE hFile, int a2, DWORD a3, __int64 a4)
{
  LARGE_INTEGER v6; // rbp
  DWORD LastError; // eax
  union _LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-18h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+28h] [rbp-10h] BYREF

  NewFilePointer.QuadPart = 0;
  liDistanceToMove.QuadPart = 0;
  v6.QuadPart = a2;
  if ( !SetFilePointerEx(hFile, 0, &liDistanceToMove, 1u)
    || (NewFilePointer.QuadPart = 0, !SetFilePointerEx(hFile, v6, &NewFilePointer, a3)) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error_ptd(LastError, a4);
    return 0xFFFFFFFFLL;
  }
  if ( NewFilePointer.QuadPart > 0x7FFFFFFF )
  {
    SetFilePointerEx(hFile, liDistanceToMove, 0, 0);
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 22;
    return 0xFFFFFFFFLL;
  }
  return NewFilePointer.LowPart;
}

```

## disassembly

```asm
0x1400717c4  mov     r11, rsp
0x1400717c7  mov     [r11+8], rbx
0x1400717cb  mov     [r11+10h], rbp
0x1400717cf  mov     [r11+18h], rsi
0x1400717d3  push    rdi
0x1400717d4  sub     rsp, 30h
0x1400717d8  and     dword ptr [rsp+38h+NewFilePointer], 0
0x1400717dd  xor     eax, eax
0x1400717df  and     [r11-10h], rax
0x1400717e3  mov     rbx, r9
0x1400717e6  mov     esi, r8d
0x1400717e9  movsxd  rbp, edx
0x1400717ec  mov     dword ptr [rsp+38h+NewFilePointer+4], eax
0x1400717f0  lea     r8, [r11-10h]; lpNewFilePointer
0x1400717f4  mov     rdx, [r11-18h]; liDistanceToMove
0x1400717f8  lea     r9d, [rax+1]; dwMoveMethod
0x1400717fc  mov     rdi, rcx
0x1400717ff  call    cs:__imp_SetFilePointerEx
0x140071805  test    eax, eax
0x140071807  jnz     short loc_14007181E
0x140071809  call    cs:__imp_GetLastError
0x14007180f  mov     ecx, eax
0x140071811  mov     rdx, rbx
0x140071814  call    __acrt_errno_map_os_error_ptd
0x140071819  or      eax, 0FFFFFFFFh
0x14007181c  jmp     short loc_140071871
0x14007181e  and     dword ptr [rsp+38h+NewFilePointer], 0
0x140071823  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x140071828  xor     eax, eax
0x14007182a  mov     rdx, rbp; liDistanceToMove
0x14007182d  mov     r9d, esi; dwMoveMethod
0x140071830  mov     dword ptr [rsp+38h+NewFilePointer+4], eax
0x140071834  mov     rcx, rdi; hFile
0x140071837  call    cs:__imp_SetFilePointerEx
0x14007183d  test    eax, eax
0x14007183f  jz      short loc_140071809
0x140071841  cmp     qword ptr [rsp+38h+NewFilePointer], 7FFFFFFFh
0x14007184a  jle     short loc_14007186D
0x14007184c  mov     rdx, qword ptr [rsp+38h+liDistanceToMove]; liDistanceToMove
0x140071851  xor     r9d, r9d; dwMoveMethod
0x140071854  xor     r8d, r8d; lpNewFilePointer
0x140071857  mov     rcx, rdi; hFile
0x14007185a  call    cs:__imp_SetFilePointerEx
0x140071860  mov     byte ptr [rbx+30h], 1
0x140071864  mov     dword ptr [rbx+2Ch], 16h
0x14007186b  jmp     short loc_140071819
0x14007186d  mov     eax, dword ptr [rsp+38h+NewFilePointer]
0x140071871  mov     rbx, [rsp+38h+arg_0]
0x140071876  mov     rbp, [rsp+38h+arg_8]
0x14007187b  mov     rsi, [rsp+38h+arg_10]
0x140071880  add     rsp, 30h
0x140071884  pop     rdi
0x140071885  retn
```
