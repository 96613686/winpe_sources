# ByteSliceManager::ReadFrom(_iobuf *)

- ea: `0x18009cbc0`
- end: `0x18009cd66`
- name: `?ReadFrom@ByteSliceManager@@UEAAXPEAU_iobuf@@@Z`
- size: `422`
- prototype: `void __fastcall(ByteSliceManager *__hidden this, FILE *Stream)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18004ad5c`
- `0x1800619a8`
- `0x180062344`
- `0x18009cbc0`
- `0x18009ce30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18009ccf3`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18009ccf3`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18009cc2a`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18009cc91`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18009cc2a`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18009cc91`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x18009cc80`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x18009cc80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cc34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cc9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cc34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cc9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ByteSliceManager::ReadFrom(ByteSliceManager *this, FILE *Stream)
{
  unsigned int SizeOf; // eax
  unsigned __int64 v5; // rsi
  void **v6; // rdi
  signed int LastError; // eax
  signed int v8; // eax
  size_t v9; // rax
  __int64 v10; // rdx
  int v11; // ecx
  void **pExceptionObject; // [rsp+20h] [rbp-58h] BYREF
  int v13; // [rsp+28h] [rbp-50h]
  __int128 v14; // [rsp+30h] [rbp-48h]
  int v15; // [rsp+40h] [rbp-38h]
  int v16; // [rsp+50h] [rbp-28h]
  __int128 v17; // [rsp+58h] [rbp-20h]
  __int64 v18; // [rsp+68h] [rbp-10h]

  SizeOf = ByteSliceManager::ReadSizeOf(Stream, (bool)Stream);
  v5 = SizeOf;
  v6 = (void **)((char *)this + 16);
  if ( *((_DWORD *)this + 2) < SizeOf || !*v6 )
  {
    ByteSliceManager::ReleaseBuffer(this);
    if ( *((_DWORD *)this + 2) < (unsigned int)v5 )
      *((_DWORD *)this + 2) = v5;
    *((_DWORD *)this + 3) = 0;
    *v6 = operator new[](v5);
    *((_DWORD *)this + 3) = v5;
    *((_BYTE *)this + 28) = 1;
  }
  if ( !*((_DWORD *)this + 3) )
  {
    if ( fseek(Stream, 0, 2) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = LastError;
      v14 = 0;
      pExceptionObject = &CNLException::`vftable';
      v15 = LastError;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      throw (CNLException *)&pExceptionObject;
    }
    *((_DWORD *)this + 3) = _o_ftell(Stream);
    if ( fseek(Stream, 0, 0) )
    {
      v8 = GetLastError();
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      v13 = v8;
      v14 = 0;
      pExceptionObject = &CNLException::`vftable';
      v15 = v8;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      throw (CNLException *)&pExceptionObject;
    }
  }
  v9 = fread(*v6, 1u, *((unsigned int *)this + 3), Stream);
  v10 = *((unsigned int *)this + 3);
  if ( v9 != v10 )
  {
    v13 = -2147467259;
    v14 = 0;
    pExceptionObject = &CNLException::`vftable';
    v15 = -2147467259;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    throw (CNLException *)&pExceptionObject;
  }
  v11 = 8;
  if ( (unsigned int)(*((_DWORD *)this + 2) - v10) <= 0xFF )
    v11 = 4;
  *((_DWORD *)this + 3) = v10 - v11;
}

```

## disassembly

```asm
0x18009cbc0  push    rbp
0x18009cbc2  push    rbx
0x18009cbc3  push    rsi
0x18009cbc4  push    rdi
0x18009cbc5  push    r14
0x18009cbc7  push    r15
0x18009cbc9  mov     rbp, rsp
0x18009cbcc  sub     rsp, 78h
0x18009cbd0  mov     r14, rdx
0x18009cbd3  mov     rbx, rcx
0x18009cbd6  mov     rcx, rdx; Stream
0x18009cbd9  call    ?ReadSizeOf@ByteSliceManager@@SAKPEAU_iobuf@@_N@Z; ByteSliceManager::ReadSizeOf(_iobuf *,bool)
0x18009cbde  mov     esi, eax
0x18009cbe0  lea     rdi, [rbx+10h]
0x18009cbe4  xor     r15d, r15d
0x18009cbe7  cmp     [rbx+8], eax
0x18009cbea  jb      short loc_18009CBF1
0x18009cbec  cmp     [rdi], r15
0x18009cbef  jnz     short loc_18009CC17
0x18009cbf1  mov     rcx, rbx; this
0x18009cbf4  call    ?ReleaseBuffer@ByteSliceManager@@QEAAXXZ; ByteSliceManager::ReleaseBuffer(void)
0x18009cbf9  cmp     [rbx+8], esi
0x18009cbfc  jnb     short loc_18009CC01
0x18009cbfe  mov     [rbx+8], esi
0x18009cc01  mov     [rbx+0Ch], r15d
0x18009cc05  mov     rcx, rsi; unsigned __int64
0x18009cc08  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18009cc0d  mov     [rdi], rax
0x18009cc10  mov     [rbx+0Ch], esi
0x18009cc13  mov     byte ptr [rbx+1Ch], 1
0x18009cc17  cmp     [rbx+0Ch], r15d
0x18009cc1b  jnz     loc_18009CCE4
0x18009cc21  xor     edx, edx; Offset
0x18009cc23  lea     r8d, [rdx+2]; Origin
0x18009cc27  mov     rcx, r14; Stream
0x18009cc2a  call    cs:__imp_fseek
0x18009cc30  test    eax, eax
0x18009cc32  jz      short loc_18009CC7D
0x18009cc34  call    cs:__imp_GetLastError
0x18009cc3a  test    eax, eax
0x18009cc3c  jle     short loc_18009CC46
0x18009cc3e  movzx   eax, ax
0x18009cc41  or      eax, 80070000h
0x18009cc46  mov     [rbp+var_50], eax
0x18009cc49  xorps   xmm0, xmm0
0x18009cc4c  movdqu  [rbp+var_48], xmm0
0x18009cc51  lea     rcx, ??_7CNLException@@6B@; const CNLException::`vftable'
0x18009cc58  mov     [rbp+pExceptionObject], rcx
0x18009cc5c  mov     [rbp+var_38], eax
0x18009cc5f  mov     [rbp+var_28], r15d
0x18009cc63  movdqu  [rbp+var_20], xmm0
0x18009cc68  mov     [rbp+var_10], r15
0x18009cc6c  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18009cc73  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cc77  call    _CxxThrowException_0
0x18009cc7d  mov     rcx, r14
0x18009cc80  call    cs:__imp__o_ftell
0x18009cc86  mov     [rbx+0Ch], eax
0x18009cc89  xor     r8d, r8d; Origin
0x18009cc8c  xor     edx, edx; Offset
0x18009cc8e  mov     rcx, r14; Stream
0x18009cc91  call    cs:__imp_fseek
0x18009cc97  test    eax, eax
0x18009cc99  jz      short loc_18009CCE4
0x18009cc9b  call    cs:__imp_GetLastError
0x18009cca1  test    eax, eax
0x18009cca3  jle     short loc_18009CCAD
0x18009cca5  movzx   eax, ax
0x18009cca8  or      eax, 80070000h
0x18009ccad  mov     [rbp+var_50], eax
0x18009ccb0  xorps   xmm0, xmm0
0x18009ccb3  movdqu  [rbp+var_48], xmm0
0x18009ccb8  lea     rcx, ??_7CNLException@@6B@; const CNLException::`vftable'
0x18009ccbf  mov     [rbp+pExceptionObject], rcx
0x18009ccc3  mov     [rbp+var_38], eax
0x18009ccc6  mov     [rbp+var_28], r15d
0x18009ccca  movdqu  [rbp+var_20], xmm0
0x18009cccf  mov     [rbp+var_10], r15
0x18009ccd3  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18009ccda  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009ccde  call    _CxxThrowException_0
0x18009cce4  mov     r8d, [rbx+0Ch]; ElementCount
0x18009cce8  mov     r9, r14; Stream
0x18009cceb  mov     edx, 1; ElementSize
0x18009ccf0  mov     rcx, [rdi]; Buffer
0x18009ccf3  call    cs:__imp_fread
0x18009ccf9  mov     edx, [rbx+0Ch]
0x18009ccfc  cmp     rax, rdx
0x18009ccff  jz      short loc_18009CD3D
0x18009cd01  mov     eax, 80004005h
0x18009cd06  mov     [rbp+var_50], eax
0x18009cd09  xorps   xmm0, xmm0
0x18009cd0c  movdqu  [rbp+var_48], xmm0
0x18009cd11  lea     rcx, ??_7CNLException@@6B@; const CNLException::`vftable'
0x18009cd18  mov     [rbp+pExceptionObject], rcx
0x18009cd1c  mov     [rbp+var_38], eax
0x18009cd1f  mov     [rbp+var_28], r15d
0x18009cd23  movdqu  [rbp+var_20], xmm0
0x18009cd28  mov     [rbp+var_10], r15
0x18009cd2c  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18009cd33  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cd37  call    _CxxThrowException_0
0x18009cd3d  mov     eax, [rbx+8]
0x18009cd40  sub     eax, edx
0x18009cd42  mov     ecx, 8
0x18009cd47  lea     r8d, [rcx-4]
0x18009cd4b  cmp     eax, 0FFh
0x18009cd50  cmovbe  ecx, r8d
0x18009cd54  sub     edx, ecx
0x18009cd56  mov     [rbx+0Ch], edx
0x18009cd59  add     rsp, 78h
0x18009cd5d  pop     r15
0x18009cd5f  pop     r14
0x18009cd61  pop     rdi
0x18009cd62  pop     rsi
0x18009cd63  pop     rbx
0x18009cd64  pop     rbp
0x18009cd65  retn
```
