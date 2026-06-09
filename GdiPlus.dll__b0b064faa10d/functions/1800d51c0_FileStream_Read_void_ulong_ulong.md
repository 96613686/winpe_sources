# FileStream::Read(void *,ulong,ulong *)

- ea: `0x1800d51c0`
- end: `0x1800d52d2`
- name: `?Read@FileStream@@UEAAJPEAXKPEAK@Z`
- size: `274`
- prototype: `int(FileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800d51c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d51fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d51fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d5273`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d5273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d528f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d52a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d528f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d52a1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800d521e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800d521e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800d5244`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800d5244`

## pseudocode

```c
__int64 __fastcall FileStream::Read(FileStream *this, void *a2, DWORD a3, unsigned int *a4)
{
  void *v8; // rcx
  signed int v9; // ebx
  DWORD v10; // eax
  signed int LastError; // eax
  signed int v13; // eax
  LONG lDistanceToMove; // [rsp+30h] [rbp-48h]
  LONG DistanceToMoveHigh; // [rsp+34h] [rbp-44h] BYREF
  __int64 v16; // [rsp+38h] [rbp-40h]
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  lDistanceToMove = *((_DWORD *)this + 22);
  DistanceToMoveHigh = *((_DWORD *)this + 23);
  if ( DistanceToMoveHigh < 0 )
    return 2147649733LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v8 = (void *)*((_QWORD *)this + 9);
  if ( v8 == (void *)-1LL )
  {
    v9 = -2147286782;
  }
  else
  {
    v9 = 0;
    if ( SetFilePointer(v8, lDistanceToMove, &DistanceToMoveHigh, 0) != -1 )
      goto LABEL_15;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
    {
LABEL_15:
      if ( ReadFile(*((HANDLE *)this + 9), a2, a3, &NumberOfBytesRead, 0) )
        goto LABEL_5;
      v13 = GetLastError();
      v9 = v13;
      if ( v13 > 0 )
        v9 = (unsigned __int16)v13 | 0x80070000;
      if ( v9 >= 0 )
      {
LABEL_5:
        v10 = NumberOfBytesRead;
        v16 = NumberOfBytesRead;
        *((_QWORD *)this + 11) += NumberOfBytesRead;
        if ( a4 )
          *a4 = v10;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800d51c0  mov     rax, rsp
0x1800d51c3  push    rbx
0x1800d51c4  push    rbp
0x1800d51c5  push    rsi
0x1800d51c6  push    rdi
0x1800d51c7  push    r14
0x1800d51c9  push    r15
0x1800d51cb  sub     rsp, 48h
0x1800d51cf  mov     dword ptr [rax+8], 0
0x1800d51d6  mov     rsi, r9
0x1800d51d9  mov     eax, [rcx+58h]
0x1800d51dc  mov     r14d, r8d
0x1800d51df  mov     [rsp+78h+lDistanceToMove], eax
0x1800d51e3  mov     r15, rdx
0x1800d51e6  mov     eax, [rcx+5Ch]
0x1800d51e9  mov     rdi, rcx
0x1800d51ec  mov     [rsp+78h+DistanceToMoveHigh], eax
0x1800d51f0  test    eax, eax
0x1800d51f2  js      loc_1800D5288
0x1800d51f8  add     rcx, 8; lpCriticalSection
0x1800d51fc  call    cs:__imp_EnterCriticalSection
0x1800d5202  mov     rcx, [rdi+48h]; hFile
0x1800d5206  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800d520a  jz      loc_1800D52BC
0x1800d5210  mov     edx, [rsp+78h+lDistanceToMove]; lDistanceToMove
0x1800d5214  lea     r8, [rsp+78h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1800d5219  xor     r9d, r9d; dwMoveMethod
0x1800d521c  xor     ebx, ebx
0x1800d521e  call    cs:__imp_SetFilePointer
0x1800d5224  cmp     eax, 0FFFFFFFFh
0x1800d5227  jz      short loc_1800D528F
0x1800d5229  mov     rcx, [rdi+48h]; hFile
0x1800d522d  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800d5235  mov     r8d, r14d; nNumberOfBytesToRead
0x1800d5238  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800d5241  mov     rdx, r15; lpBuffer
0x1800d5244  call    cs:__imp_ReadFile
0x1800d524a  test    eax, eax
0x1800d524c  jz      short loc_1800D52A1
0x1800d524e  mov     eax, [rsp+78h+NumberOfBytesRead]
0x1800d5255  mov     dword ptr [rsp+78h+var_40], eax
0x1800d5259  mov     dword ptr [rsp+78h+var_40+4], 0
0x1800d5261  mov     rdx, [rsp+78h+var_40]
0x1800d5266  add     [rdi+58h], rdx
0x1800d526a  test    rsi, rsi
0x1800d526d  jnz     short loc_1800D52CE
0x1800d526f  lea     rcx, [rdi+8]; lpCriticalSection
0x1800d5273  call    cs:__imp_LeaveCriticalSection
0x1800d5279  mov     eax, ebx
0x1800d527b  add     rsp, 48h
0x1800d527f  pop     r15
0x1800d5281  pop     r14
0x1800d5283  pop     rdi
0x1800d5284  pop     rsi
0x1800d5285  pop     rbp
0x1800d5286  pop     rbx
0x1800d5287  retn
0x1800d5288  mov     eax, 800288C5h
0x1800d528d  jmp     short loc_1800D527B
0x1800d528f  call    cs:__imp_GetLastError
0x1800d5295  mov     ebx, eax
0x1800d5297  test    eax, eax
0x1800d5299  jg      short loc_1800D52C3
0x1800d529b  test    ebx, ebx
0x1800d529d  jns     short loc_1800D5229
0x1800d529f  jmp     short loc_1800D526F
0x1800d52a1  call    cs:__imp_GetLastError
0x1800d52a7  mov     ebx, eax
0x1800d52a9  test    eax, eax
0x1800d52ab  jle     short loc_1800D52B6
0x1800d52ad  movzx   ebx, ax
0x1800d52b0  or      ebx, 80070000h
0x1800d52b6  test    ebx, ebx
0x1800d52b8  js      short loc_1800D526F
0x1800d52ba  jmp     short loc_1800D524E
0x1800d52bc  mov     ebx, 80030102h
0x1800d52c1  jmp     short loc_1800D526F
0x1800d52c3  movzx   ebx, ax
0x1800d52c6  or      ebx, 80070000h
0x1800d52cc  jmp     short loc_1800D529B
0x1800d52ce  mov     [rsi], eax
0x1800d52d0  jmp     short loc_1800D526F
```
