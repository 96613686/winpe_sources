# _open_osfhandle

- ea: `0x180014690`
- end: `0x180014790`
- name: `_open_osfhandle`
- size: `256`
- prototype: `int __cdecl(intptr_t OSFileHandle, int Flags)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180007718`
- `0x180007764`
- `0x180007788`
- `0x180014334`
- `0x1800143f4`
- `0x18001441c`
- `0x180014690`

## import_xrefs

- `KERNEL32!GetFileType` at `0x1800146d2`
- `KERNEL32!GetFileType` at `0x1800146d2`
- `KERNEL32!GetLastError` at `0x1800146dc`
- `KERNEL32!GetLastError` at `0x1800146dc`

## pseudocode

```c
int __cdecl open_osfhandle(intptr_t OSFileHandle, int Flags)
{
  char v3; // r8
  char v4; // bl
  DWORD FileType; // eax
  DWORD LastError; // eax
  unsigned int v8; // eax
  __int64 v9; // rdi
  __int64 v10; // rdx

  v3 = (4 * (Flags & 8)) | 0x80;
  if ( (Flags & 0x4000) == 0 )
    v3 = 4 * (Flags & 8);
  v4 = v3 | 0x10;
  if ( (Flags & 0x80u) == 0 )
    v4 = v3;
  FileType = GetFileType((HANDLE)OSFileHandle);
  switch ( FileType )
  {
    case 0u:
      LastError = GetLastError();
      _acrt_errno_map_os_error(LastError);
      return -1;
    case 2u:
      v4 |= 0x40u;
      break;
    case 3u:
      v4 |= 8u;
      break;
  }
  v8 = alloc_osfhnd();
  v9 = (int)v8;
  if ( v8 == -1 )
  {
    *errno() = 24;
    *_doserrno() = 0;
    return -1;
  }
  _acrt_lowio_set_os_handle(v8, OSFileHandle);
  v10 = 9 * (v9 & 0x3F);
  *(_BYTE *)(_pioinfo[v9 >> 6] + 8 * v10 + 56) = v4 | 1;
  *(_BYTE *)(_pioinfo[v9 >> 6] + 8 * v10 + 57) = 0;
  *(_BYTE *)(_pioinfo[v9 >> 6] + 8 * v10 + 61) = *(_BYTE *)(_pioinfo[v9 >> 6] + 72 * (v9 & 0x3F) + 61) & 0xFE;
  _acrt_lowio_unlock_fh((unsigned int)v9);
  return v9;
}

```

## disassembly

```asm
0x180014690  mov     [rsp+arg_0], rbx
0x180014695  mov     [rsp+arg_10], rsi
0x18001469a  push    rdi
0x18001469b  sub     rsp, 30h
0x18001469f  mov     rsi, rcx
0x1800146a2  mov     al, dl
0x1800146a4  and     al, 8
0x1800146a6  shl     al, 2
0x1800146a9  movzx   r10d, al
0x1800146ad  mov     al, r10b
0x1800146b0  or      al, 80h
0x1800146b2  movzx   r8d, al
0x1800146b6  bt      edx, 0Eh
0x1800146ba  cmovnb  r8d, r10d
0x1800146be  movzx   ecx, r8b
0x1800146c2  mov     al, cl
0x1800146c4  or      al, 10h
0x1800146c6  movzx   ebx, al
0x1800146c9  test    dl, 80h
0x1800146cc  cmovz   ebx, ecx
0x1800146cf  mov     rcx, rsi; hFile
0x1800146d2  call    cs:__imp_GetFileType
0x1800146d8  test    eax, eax
0x1800146da  jnz     short loc_1800146FC
0x1800146dc  call    cs:__imp_GetLastError
0x1800146e2  mov     ecx, eax
0x1800146e4  call    __acrt_errno_map_os_error
0x1800146e9  or      eax, 0FFFFFFFFh
0x1800146ec  mov     rbx, [rsp+38h+arg_0]
0x1800146f1  mov     rsi, [rsp+38h+arg_10]
0x1800146f6  add     rsp, 30h
0x1800146fa  pop     rdi
0x1800146fb  retn
0x1800146fc  cmp     eax, 2
0x1800146ff  jnz     short loc_180014706
0x180014701  or      bl, 40h
0x180014704  jmp     short loc_18001470E
0x180014706  cmp     eax, 3
0x180014709  jnz     short loc_18001470E
0x18001470b  or      bl, 8
0x18001470e  call    _alloc_osfhnd
0x180014713  movsxd  rdi, eax
0x180014716  mov     [rsp+38h+arg_8], edi
0x18001471a  cmp     edi, 0FFFFFFFFh
0x18001471d  jnz     short loc_180014734
0x18001471f  call    _errno
0x180014724  mov     dword ptr [rax], 18h
0x18001472a  call    __doserrno
0x18001472f  and     dword ptr [rax], 0
0x180014732  jmp     short loc_1800146E9
0x180014734  mov     [rsp+38h+var_18], 0
0x180014739  mov     rdx, rsi
0x18001473c  mov     ecx, edi
0x18001473e  call    __acrt_lowio_set_os_handle
0x180014743  or      bl, 1
0x180014746  mov     rax, rdi
0x180014749  mov     rcx, rdi
0x18001474c  sar     rcx, 6
0x180014750  lea     r8, __pioinfo
0x180014757  and     eax, 3Fh
0x18001475a  lea     rdx, [rax+rax*8]
0x18001475e  mov     rax, [r8+rcx*8]
0x180014762  mov     [rax+rdx*8+38h], bl
0x180014766  mov     rax, [r8+rcx*8]
0x18001476a  mov     byte ptr [rax+rdx*8+39h], 0
0x18001476f  mov     rcx, [r8+rcx*8]
0x180014773  mov     al, [rcx+rdx*8+3Dh]
0x180014777  and     al, 0FEh
0x180014779  mov     [rcx+rdx*8+3Dh], al
0x18001477d  mov     [rsp+38h+var_18], 1
0x180014782  mov     ecx, edi
0x180014784  call    __acrt_lowio_unlock_fh
0x180014789  mov     eax, edi
0x18001478b  jmp     loc_1800146EC
0x180061262  push    rbp
0x180061264  sub     rsp, 20h
0x180061268  mov     rbp, rdx
0x18006126b  cmp     byte ptr [rbp+20h], 0
0x18006126f  jnz     short loc_1800612A9
0x180061271  movsxd  r9, dword ptr [rbp+48h]
0x180061275  mov     r8, r9
0x180061278  sar     r8, 6
0x18006127c  and     r9d, 3Fh
0x180061280  lea     rax, __pioinfo
0x180061287  lea     rcx, [r9+r9*8]
0x18006128b  mov     rax, [rax+r8*8]
0x18006128f  mov     dl, [rax+rcx*8+38h]
0x180061293  and     dl, 0FEh
0x180061296  lea     rax, __pioinfo
0x18006129d  lea     rcx, [r9+r9*8]
0x1800612a1  mov     rax, [rax+r8*8]
0x1800612a5  mov     [rax+rcx*8+38h], dl
0x1800612a9  mov     ecx, [rbp+48h]
0x1800612ac  call    __acrt_lowio_unlock_fh
0x1800612b1  nop
0x1800612b2  add     rsp, 20h
0x1800612b6  pop     rbp
0x1800612b7  retn
```
