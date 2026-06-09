# _archive_read_data_block_0

- ea: `0x1800bce30`
- end: `0x1800bd085`
- name: `_archive_read_data_block_0`
- size: `597`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000523c`
- `0x180006c00`
- `0x1800149c0`
- `0x1800bce30`
- `0x1800be07c`
- `0x1800be0b8`
- `0x1800bf1c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bcfea`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bcfea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcfdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcfdd`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800bcfcf`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800bcfcf`

## string_xrefs

- `0x1800bce5e`: `archive_read_data_block`
- `0x1800bd00f`: `Reading file truncated`

## pseudocode

```c
__int64 __fastcall archive_read_data_block_0(__int64 a1, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v4; // rbx
  unsigned int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rdx
  __int64 v13; // rsi
  DWORD v14; // eax
  __int64 v15; // rax
  bool v16; // zf
  DWORD LastError; // eax
  unsigned int *v18; // rax
  DWORD NumberOfBytesTransferred; // [rsp+60h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 160);
  NumberOfBytesTransferred = 0;
  if ( (unsigned int)_archive_check_magic(a1, 195932357, 4, "archive_read_data_block") == -30 )
    return 4294967266LL;
  if ( *(_DWORD *)(v4 + 928) || *(__int64 *)(v4 + 936) <= 0 )
  {
    v11 = 1;
    goto LABEL_26;
  }
  if ( !*(_DWORD *)(v4 + 960) )
  {
    while ( 1 )
    {
      v10 = start_next_async_read(a1, v4);
      v11 = v10;
      if ( v10 == -30 )
        goto LABEL_26;
      if ( !*(_DWORD *)(v4 + 1628) || v10 || *(int *)(v4 + 960) >= 8 )
        goto LABEL_12;
    }
  }
  v11 = start_next_async_read(a1, v4);
  if ( v11 != -30 )
  {
LABEL_12:
    v12 = *(int *)(v4 + 956);
    v13 = v4 + 80 * v12 + 984;
    *(_DWORD *)(v4 + 956) = ((int)v12 + 1) % 8;
    if ( *(_QWORD *)(v13 + 72) )
    {
      NumberOfBytesTransferred = *(_DWORD *)(v13 + 72);
    }
    else if ( !GetOverlappedResult(*(HANDLE *)(v4 + 920), (LPOVERLAPPED)v13, &NumberOfBytesTransferred, 1) )
    {
      LastError = GetLastError();
      _la_dosmaperr(LastError);
      v18 = (unsigned int *)_o__errno();
      archive_set_error(a1, *v18, "GetOverlappedResult failed");
LABEL_23:
      *(_DWORD *)(a1 + 4) = 0x8000;
      v11 = -30;
      goto LABEL_26;
    }
    ++*(_DWORD *)(v4 + 964);
    v14 = NumberOfBytesTransferred;
    if ( NumberOfBytesTransferred && *(_QWORD *)(v13 + 64) == NumberOfBytesTransferred )
    {
      *a2 = *(_QWORD *)(v13 + 40);
      *a3 = v14;
      *a4 = *(_QWORD *)(v13 + 56);
      v15 = *(_QWORD *)(v4 + 944);
      if ( *(_QWORD *)(v13 + 56) > v15 )
        *(_QWORD *)(v4 + 936) += v15 - *(_QWORD *)(v13 + 56);
      *(_QWORD *)(v4 + 944) = *a3 + *(_QWORD *)(v13 + 56);
      v16 = *(_QWORD *)(v4 + 936) == *a3;
      *(_QWORD *)(v4 + 936) -= *a3;
      if ( v16 )
      {
        close_and_restore_time(*(void **)(v4 + 920), v4, (__int64 *)(v4 + 824));
        *(_QWORD *)(v4 + 920) = -1;
        *(_DWORD *)(v4 + 928) = 1;
      }
      return 0;
    }
    archive_set_error(a1, 0xFFFFFFFFLL, "Reading file truncated");
    goto LABEL_23;
  }
LABEL_26:
  *a2 = 0;
  *a3 = 0;
  *a4 = *(_QWORD *)(v4 + 944);
  if ( *(_QWORD *)(v4 + 920) != -1 )
  {
    cancel_async(v4);
    close_and_restore_time(*(void **)(v4 + 920), v4, (__int64 *)(v4 + 824));
    *(_QWORD *)(v4 + 920) = -1;
  }
  return v11;
}

```

## disassembly

```asm
0x1800bce30  mov     [rsp+arg_8], rbx
0x1800bce35  mov     [rsp+arg_10], rbp
0x1800bce3a  push    rsi
0x1800bce3b  push    rdi
0x1800bce3c  push    r12
0x1800bce3e  push    r14
0x1800bce40  push    r15
0x1800bce42  sub     rsp, 30h
0x1800bce46  mov     rbx, [rcx+0A0h]
0x1800bce4d  mov     r15, r9
0x1800bce50  mov     r14, r8
0x1800bce53  mov     [rsp+58h+NumberOfBytesTransferred], 0
0x1800bce5b  mov     r12, rdx
0x1800bce5e  lea     r9, aArchiveReadDat_4; "archive_read_data_block"
0x1800bce65  mov     edx, 0BADB0C5h
0x1800bce6a  mov     r8d, 4
0x1800bce70  mov     rbp, rcx
0x1800bce73  call    __archive_check_magic
0x1800bce78  mov     esi, 0FFFFFFE2h
0x1800bce7d  cmp     eax, esi
0x1800bce7f  jnz     short loc_1800BCE88
0x1800bce81  mov     eax, esi
0x1800bce83  jmp     loc_1800BD06E
0x1800bce88  cmp     dword ptr [rbx+3A0h], 0
0x1800bce8f  jnz     loc_1800BD01B
0x1800bce95  cmp     qword ptr [rbx+3A8h], 0
0x1800bce9d  jle     loc_1800BD01B
0x1800bcea3  cmp     dword ptr [rbx+3C0h], 0
0x1800bceaa  jnz     short loc_1800BCED9
0x1800bceac  mov     rdx, rbx
0x1800bceaf  mov     rcx, rbp
0x1800bceb2  call    start_next_async_read
0x1800bceb7  mov     edi, eax
0x1800bceb9  cmp     eax, esi
0x1800bcebb  jz      loc_1800BD020
0x1800bcec1  cmp     dword ptr [rbx+65Ch], 0
0x1800bcec8  jz      short loc_1800BCEEE
0x1800bceca  test    eax, eax
0x1800bcecc  jnz     short loc_1800BCEEE
0x1800bcece  cmp     dword ptr [rbx+3C0h], 8
0x1800bced5  jl      short loc_1800BCEAC
0x1800bced7  jmp     short loc_1800BCEEE
0x1800bced9  mov     rdx, rbx
0x1800bcedc  mov     rcx, rbp
0x1800bcedf  call    start_next_async_read
0x1800bcee4  mov     edi, eax
0x1800bcee6  cmp     eax, esi
0x1800bcee8  jz      loc_1800BD020
0x1800bceee  movsxd  rdx, dword ptr [rbx+3BCh]
0x1800bcef5  mov     ecx, 8
0x1800bcefa  lea     rsi, [rdx+rdx*4]
0x1800bcefe  lea     eax, [rdx+1]
0x1800bcf01  shl     rsi, 4
0x1800bcf05  cdq
0x1800bcf06  lea     edi, [rcx-7]
0x1800bcf09  idiv    ecx
0x1800bcf0b  add     rsi, 3D8h
0x1800bcf12  add     rsi, rbx
0x1800bcf15  mov     [rbx+3BCh], edx
0x1800bcf1b  cmp     qword ptr [rsi+48h], 0
0x1800bcf20  jz      loc_1800BCFBD
0x1800bcf26  mov     eax, [rsi+48h]
0x1800bcf29  mov     [rsp+58h+NumberOfBytesTransferred], eax
0x1800bcf2d  add     [rbx+3C4h], edi
0x1800bcf33  mov     eax, [rsp+58h+NumberOfBytesTransferred]
0x1800bcf37  test    eax, eax
0x1800bcf39  jz      loc_1800BD00F
0x1800bcf3f  mov     ecx, eax
0x1800bcf41  cmp     [rsi+40h], rax
0x1800bcf45  jnz     loc_1800BD00F
0x1800bcf4b  mov     rax, [rsi+28h]
0x1800bcf4f  mov     [r12], rax
0x1800bcf53  mov     [r14], rcx
0x1800bcf56  mov     rax, [rsi+38h]
0x1800bcf5a  mov     [r15], rax
0x1800bcf5d  mov     rax, [rbx+3B0h]
0x1800bcf64  cmp     [rsi+38h], rax
0x1800bcf68  jle     short loc_1800BCF75
0x1800bcf6a  sub     rax, [rsi+38h]
0x1800bcf6e  add     [rbx+3A8h], rax
0x1800bcf75  mov     rax, [rsi+38h]
0x1800bcf79  add     rax, [r14]
0x1800bcf7c  mov     [rbx+3B0h], rax
0x1800bcf83  mov     rax, [r14]
0x1800bcf86  sub     [rbx+3A8h], rax
0x1800bcf8d  jnz     short loc_1800BCFB6
0x1800bcf8f  mov     rcx, [rbx+398h]
0x1800bcf96  lea     r8, [rbx+338h]
0x1800bcf9d  mov     rdx, rbx
0x1800bcfa0  call    close_and_restore_time
0x1800bcfa5  mov     qword ptr [rbx+398h], 0FFFFFFFFFFFFFFFFh
0x1800bcfb0  mov     [rbx+3A0h], edi
0x1800bcfb6  xor     eax, eax
0x1800bcfb8  jmp     loc_1800BD06E
0x1800bcfbd  mov     rcx, [rbx+398h]; hFile
0x1800bcfc4  lea     r8, [rsp+58h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800bcfc9  mov     r9d, edi; bWait
0x1800bcfcc  mov     rdx, rsi; lpOverlapped
0x1800bcfcf  call    cs:__imp_GetOverlappedResult
0x1800bcfd5  test    eax, eax
0x1800bcfd7  jnz     loc_1800BCF2D
0x1800bcfdd  call    cs:__imp_GetLastError
0x1800bcfe3  mov     ecx, eax
0x1800bcfe5  call    __la_dosmaperr
0x1800bcfea  call    cs:__imp__o__errno
0x1800bcff0  lea     r8, aGetoverlappedr; "GetOverlappedResult failed"
0x1800bcff7  mov     edx, [rax]
0x1800bcff9  mov     rcx, rbp
0x1800bcffc  call    archive_set_error
0x1800bd001  mov     dword ptr [rbp+4], 8000h
0x1800bd008  mov     edi, 0FFFFFFE2h
0x1800bd00d  jmp     short loc_1800BD020
0x1800bd00f  lea     r8, aReadingFileTru; "Reading file truncated"
0x1800bd016  or      edx, 0FFFFFFFFh
0x1800bd019  jmp     short loc_1800BCFF9
0x1800bd01b  mov     edi, 1
0x1800bd020  mov     qword ptr [r12], 0
0x1800bd028  mov     qword ptr [r14], 0
0x1800bd02f  mov     rax, [rbx+3B0h]
0x1800bd036  mov     [r15], rax
0x1800bd039  cmp     qword ptr [rbx+398h], 0FFFFFFFFFFFFFFFFh
0x1800bd041  jz      short loc_1800BD06C
0x1800bd043  mov     rcx, rbx
0x1800bd046  call    cancel_async
0x1800bd04b  mov     rcx, [rbx+398h]
0x1800bd052  lea     r8, [rbx+338h]
0x1800bd059  mov     rdx, rbx
0x1800bd05c  call    close_and_restore_time
0x1800bd061  mov     qword ptr [rbx+398h], 0FFFFFFFFFFFFFFFFh
0x1800bd06c  mov     eax, edi
0x1800bd06e  mov     rbx, [rsp+58h+arg_8]
0x1800bd073  mov     rbp, [rsp+58h+arg_10]
0x1800bd078  add     rsp, 30h
0x1800bd07c  pop     r15
0x1800bd07e  pop     r14
0x1800bd080  pop     r12
0x1800bd082  pop     rdi
0x1800bd083  pop     rsi
0x1800bd084  retn
```
