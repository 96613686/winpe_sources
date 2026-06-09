# CFileStream::HrGetPosition(_ULARGE_INTEGER *)

- ea: `0x1800a4620`
- end: `0x1800a4710`
- name: `?HrGetPosition@CFileStream@@UEAAJPEAT_ULARGE_INTEGER@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800a4620`
- `0x1800bd9d4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a46ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a46ca`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a466e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a466e`

## pseudocode

```c
__int64 __fastcall CFileStream::HrGetPosition(CFileStream *this, union _ULARGE_INTEGER *a2)
{
  char *v2; // rsi
  void *v5; // rcx
  DWORD v6; // ebp
  int v7; // eax
  LONG v8; // ecx
  signed int v9; // ebx
  bool v11; // zf
  signed int LastError; // eax
  LONG DistanceToMoveHigh; // [rsp+50h] [rbp+8h] BYREF

  v2 = (char *)this + 16;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 112LL))((char *)this + 16);
  DistanceToMoveHigh = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
    goto LABEL_18;
  }
  v5 = (void *)*((_QWORD *)this + 15);
  if ( v5 == (void *)-1LL )
  {
    v9 = -2003292404;
LABEL_18:
    v11 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_9;
  }
  v6 = SetFilePointer(v5, 0, &DistanceToMoveHigh, 1u);
  if ( v6 == -1 && (LastError = GetLastError(), (v9 = LastError) != 0) )
  {
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v7 = (int)g_doStackCaptures;
    if ( v9 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_7;
      goto LABEL_10;
    }
  }
  else
  {
    v7 = (int)g_doStackCaptures;
  }
  v8 = DistanceToMoveHigh;
  a2->LowPart = v6;
  if ( v8 >= 0 )
  {
    v9 = 0;
    a2->HighPart = v8;
    goto LABEL_7;
  }
  v9 = -2147024362;
  a2->HighPart = -1;
  v11 = v7 == 0;
LABEL_9:
  if ( !v11 )
LABEL_10:
    DoStackCapture(v9);
LABEL_7:
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 120LL))(v2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800a4620  push    rbx
0x1800a4622  push    rbp
0x1800a4623  push    rsi
0x1800a4624  push    rdi
0x1800a4625  sub     rsp, 28h
0x1800a4629  lea     rsi, [rcx+10h]
0x1800a462d  mov     rbx, rcx
0x1800a4630  mov     rax, [rsi]
0x1800a4633  mov     rcx, rsi
0x1800a4636  mov     rdi, rdx
0x1800a4639  mov     rax, [rax+70h]
0x1800a463d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4642  mov     [rsp+48h+DistanceToMoveHigh], 0
0x1800a464a  test    rdi, rdi
0x1800a464d  jz      loc_1800A4709
0x1800a4653  mov     rcx, [rbx+78h]; hFile
0x1800a4657  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a465b  jz      loc_1800A46FB
0x1800a4661  mov     r9d, 1; dwMoveMethod
0x1800a4667  lea     r8, [rsp+48h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1800a466c  xor     edx, edx; lDistanceToMove
0x1800a466e  call    cs:__imp_SetFilePointer
0x1800a4675  nop     dword ptr [rax+rax+00h]
0x1800a467a  mov     ebp, eax
0x1800a467c  cmp     eax, 0FFFFFFFFh
0x1800a467f  jz      short loc_1800A46CA
0x1800a4681  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800a4687  mov     ecx, [rsp+48h+DistanceToMoveHigh]
0x1800a468b  mov     [rdi], ebp
0x1800a468d  test    ecx, ecx
0x1800a468f  js      short loc_1800A46B1
0x1800a4691  xor     ebx, ebx
0x1800a4693  mov     [rdi+4], ecx
0x1800a4696  mov     rdx, [rsi]
0x1800a4699  mov     rcx, rsi
0x1800a469c  mov     rax, [rdx+78h]
0x1800a46a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a46a5  mov     eax, ebx
0x1800a46a7  add     rsp, 28h
0x1800a46ab  pop     rdi
0x1800a46ac  pop     rsi
0x1800a46ad  pop     rbp
0x1800a46ae  pop     rbx
0x1800a46af  retn
0x1800a46b1  mov     ebx, 80070216h
0x1800a46b6  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x1800a46bd  test    eax, eax
0x1800a46bf  jz      short loc_1800A4696
0x1800a46c1  mov     ecx, ebx; int
0x1800a46c3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800a46c8  jmp     short loc_1800A4696
0x1800a46ca  call    cs:__imp_GetLastError
0x1800a46d1  nop     dword ptr [rax+rax+00h]
0x1800a46d6  mov     ebx, eax
0x1800a46d8  test    eax, eax
0x1800a46da  jz      short loc_1800A4681
0x1800a46dc  jle     short loc_1800A46E7
0x1800a46de  movzx   ebx, ax
0x1800a46e1  or      ebx, 80070000h
0x1800a46e7  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800a46ed  test    ebx, ebx
0x1800a46ef  jns     short loc_1800A4687
0x1800a46f1  test    eax, eax
0x1800a46f3  jnz     short loc_1800A46C1
0x1800a46f5  test    ebx, ebx
0x1800a46f7  jns     short loc_1800A4687
0x1800a46f9  jmp     short loc_1800A4696
0x1800a46fb  mov     ebx, 88982F0Ch
0x1800a4700  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800a4707  jmp     short loc_1800A46BF
0x1800a4709  mov     ebx, 80070057h
0x1800a470e  jmp     short loc_1800A4700
```
