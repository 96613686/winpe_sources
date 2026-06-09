# ByteSliceManager::ReadFrom(_iobuf *)

- ea: `0x180035120`
- end: `0x180035289`
- name: `?ReadFrom@ByteSliceManager@@UEAAXPEAU_iobuf@@@Z`
- size: `361`
- prototype: `void __fastcall(ByteSliceManager *__hidden this, FILE *Stream)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180035120`
- `0x180035640`
- `0x18003e188`
- `0x18003ed6c`
- `0x18006b7b0`
- `0x18006c268`

## import_xrefs

- `msvcrt!ftell` at `0x1800351c9`
- `msvcrt!ftell` at `0x1800351c9`
- `msvcrt!fseek` at `0x180035184`
- `msvcrt!fseek` at `0x1800351da`
- `msvcrt!fseek` at `0x180035184`
- `msvcrt!fseek` at `0x1800351da`
- `msvcrt!fread` at `0x18003522d`
- `msvcrt!fread` at `0x18003522d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003518e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003518e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351e4`

## pseudocode

```c
void __fastcall ByteSliceManager::ReadFrom(ByteSliceManager *this, FILE *Stream)
{
  unsigned int SizeOf; // eax
  void **v5; // rsi
  unsigned __int64 v6; // rbx
  signed int LastError; // eax
  signed int v8; // eax
  size_t v9; // rbx
  int v10; // edx
  int v11; // ecx
  _BYTE pExceptionObject[104]; // [rsp+20h] [rbp-68h] BYREF
  const void *retaddr; // [rsp+88h] [rbp+0h]

  SizeOf = ByteSliceManager::ReadSizeOf(Stream, (bool)Stream);
  v5 = (void **)((char *)this + 16);
  v6 = SizeOf;
  if ( *((_DWORD *)this + 3) < SizeOf || !*v5 )
  {
    ByteSliceManager::ReleaseBuffer(this);
    if ( *((_DWORD *)this + 3) < (unsigned int)v6 )
      *((_DWORD *)this + 3) = v6;
    *((_DWORD *)this + 2) = 0;
    *v5 = operator new[](v6);
    *((_DWORD *)this + 2) = v6;
    *((_BYTE *)this + 28) = 1;
  }
  if ( !*((_DWORD *)this + 2) )
  {
    if ( fseek(Stream, 0, 2) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      CNLException::CNLException((CNLException *)pExceptionObject, (unsigned int)LastError, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    *((_DWORD *)this + 2) = ftell(Stream);
    if ( fseek(Stream, 0, 0) )
    {
      v8 = GetLastError();
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      CNLException::CNLException((CNLException *)pExceptionObject, (unsigned int)v8, retaddr);
      throw (CNLException *)pExceptionObject;
    }
  }
  v9 = *((unsigned int *)this + 2);
  if ( fread(*v5, 1u, v9, Stream) != v9 )
  {
    CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  v10 = *((_DWORD *)this + 2);
  v11 = 8;
  if ( (unsigned int)(*((_DWORD *)this + 3) - v10) <= 0xFF )
    v11 = 4;
  *((_DWORD *)this + 2) = v10 - v11;
}

```

## disassembly

```asm
0x180035120  push    rbx
0x180035122  push    rbp
0x180035123  push    rsi
0x180035124  push    rdi
0x180035125  sub     rsp, 68h
0x180035129  mov     rdi, rcx
0x18003512c  mov     rbp, rdx
0x18003512f  mov     rcx, rdx; Stream
0x180035132  call    ?ReadSizeOf@ByteSliceManager@@SAKPEAU_iobuf@@_N@Z; ByteSliceManager::ReadSizeOf(_iobuf *,bool)
0x180035137  lea     rsi, [rdi+10h]
0x18003513b  mov     ebx, eax
0x18003513d  cmp     [rdi+0Ch], eax
0x180035140  jb      short loc_180035148
0x180035142  cmp     qword ptr [rsi], 0
0x180035146  jnz     short loc_180035171
0x180035148  mov     rcx, rdi; this
0x18003514b  call    ?ReleaseBuffer@ByteSliceManager@@QEAAXXZ; ByteSliceManager::ReleaseBuffer(void)
0x180035150  cmp     [rdi+0Ch], ebx
0x180035153  jnb     short loc_180035158
0x180035155  mov     [rdi+0Ch], ebx
0x180035158  mov     rcx, rbx; unsigned __int64
0x18003515b  mov     dword ptr [rdi+8], 0
0x180035162  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180035167  mov     [rsi], rax
0x18003516a  mov     [rdi+8], ebx
0x18003516d  mov     byte ptr [rdi+1Ch], 1
0x180035171  cmp     dword ptr [rdi+8], 0
0x180035175  jnz     loc_18003521C
0x18003517b  xor     edx, edx; Offset
0x18003517d  mov     rcx, rbp; Stream
0x180035180  lea     r8d, [rdx+2]; Origin
0x180035184  call    cs:__imp_fseek
0x18003518a  test    eax, eax
0x18003518c  jz      short loc_1800351C6
0x18003518e  call    cs:__imp_GetLastError
0x180035194  test    eax, eax
0x180035196  jle     short loc_1800351A0
0x180035198  movzx   eax, ax
0x18003519b  or      eax, 80070000h
0x1800351a0  mov     r8, [rsp+88h]; void *
0x1800351a8  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800351ad  mov     edx, eax; int
0x1800351af  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x1800351b4  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x1800351bb  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800351c0  call    _CxxThrowException_0
0x1800351c6  mov     rcx, rbp; Stream
0x1800351c9  call    cs:__imp_ftell
0x1800351cf  xor     r8d, r8d; Origin
0x1800351d2  xor     edx, edx; Offset
0x1800351d4  mov     rcx, rbp; Stream
0x1800351d7  mov     [rdi+8], eax
0x1800351da  call    cs:__imp_fseek
0x1800351e0  test    eax, eax
0x1800351e2  jz      short loc_18003521C
0x1800351e4  call    cs:__imp_GetLastError
0x1800351ea  test    eax, eax
0x1800351ec  jle     short loc_1800351F6
0x1800351ee  movzx   eax, ax
0x1800351f1  or      eax, 80070000h
0x1800351f6  mov     r8, [rsp+88h]; void *
0x1800351fe  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180035203  mov     edx, eax; int
0x180035205  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18003520a  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180035211  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180035216  call    _CxxThrowException_0
0x18003521c  mov     ebx, [rdi+8]
0x18003521f  mov     r9, rbp; Stream
0x180035222  mov     rcx, [rsi]; Buffer
0x180035225  mov     r8d, ebx; ElementCount
0x180035228  mov     edx, 1; ElementSize
0x18003522d  call    cs:__imp_fread
0x180035233  cmp     rax, rbx
0x180035236  jz      short loc_180035261
0x180035238  mov     r8, [rsp+88h]; void *
0x180035240  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180035245  mov     edx, 80004005h; int
0x18003524a  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18003524f  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180035256  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18003525b  call    _CxxThrowException_0
0x180035261  mov     edx, [rdi+8]
0x180035264  mov     ecx, 8
0x180035269  mov     eax, [rdi+0Ch]
0x18003526c  sub     eax, edx
0x18003526e  cmp     eax, 0FFh
0x180035273  lea     r8d, [rcx-4]
0x180035277  cmovbe  ecx, r8d
0x18003527b  sub     edx, ecx
0x18003527d  mov     [rdi+8], edx
0x180035280  add     rsp, 68h
0x180035284  pop     rdi
0x180035285  pop     rsi
0x180035286  pop     rbp
0x180035287  pop     rbx
0x180035288  retn
```
