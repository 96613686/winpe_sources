# Streaming::staging_operations::create_file(void const *,ulong,void *,ulong,ulong &)

- ea: `0x140010c64`
- end: `0x140010ded`
- name: `?create_file@staging_operations@Streaming@@YAJPEBXKPEAXKAEAK@Z`
- size: `393`
- prototype: `__int64 __fastcall(Streaming::staging_operations *this, const void *, _DWORD *, void *, union _LARGE_INTEGER)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013f68`

## callees

- `0x1400084b0`
- `0x140008bdc`
- `0x140010c64`

## pseudocode

```c
__int64 __fastcall Streaming::staging_operations::create_file(
        Streaming::staging_operations *this,
        const void *a2,
        _DWORD *a3,
        void *a4,
        union _LARGE_INTEGER a5)
{
  _DWORD *QuadPart; // r14
  int v6; // r15d
  int v8; // r9d
  int v9; // r10d
  unsigned int v10; // r8d
  __int64 v11; // r11
  __int64 v12; // rbx
  __int64 v13; // rdi
  char *v14; // rdx
  __int16 v15; // r9
  int v16; // r10d
  unsigned __int8 v17; // r10
  bool v18; // zf
  struct _UNICODE_STRING *v19; // r8
  __int64 result; // rax
  struct _FILE_OBJECT *v21; // r8
  __int128 v22; // [rsp+20h] [rbp-30h] BYREF
  struct _UNICODE_STRING v23; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING v24; // [rsp+40h] [rbp-10h] BYREF

  QuadPart = (_DWORD *)a5.QuadPart;
  *(_DWORD *)(&v24.MaximumLength + 1) = 0;
  *(_DWORD *)(&v23.MaximumLength + 1) = 0;
  v6 = (int)a4;
  *(_DWORD *)a5.QuadPart = 0;
  v22 = 0;
  if ( !this )
    return 3221225485LL;
  if ( (unsigned int)a2 < 0x30 )
    return 3221225485LL;
  if ( (unsigned int)a2 < *((_DWORD *)this + 1) )
    return 3221225485LL;
  v8 = *((unsigned __int16 *)this + 12);
  if ( !(_WORD)v8 )
    return 3221225485LL;
  v9 = *((unsigned __int16 *)this + 16);
  if ( !(_WORD)v9 )
    return 3221225485LL;
  v10 = *((unsigned __int16 *)this + 20);
  if ( v10 > 0x18 )
    return 3221225485LL;
  v11 = *((unsigned int *)this + 5);
  if ( (int)v11 + v8 > (unsigned int)a2 )
    return 3221225485LL;
  v12 = *((unsigned int *)this + 7);
  if ( (int)v12 + v9 > (unsigned int)a2 )
    return 3221225485LL;
  v13 = *((unsigned int *)this + 9);
  if ( (unsigned int)v13 + v10 > (unsigned int)a2 )
    return 3221225485LL;
  v24.Length = *((_WORD *)this + 12);
  v24.Buffer = (PWSTR)((char *)this + v11);
  v23.Buffer = (PWSTR)((char *)this + v12);
  v24.MaximumLength = v8;
  v23.Length = v9;
  v23.MaximumLength = v9;
  if ( (_WORD)v10 )
  {
    v15 = v10;
    LOWORD(v22) = v10;
    WORD1(v22) = v10;
    v14 = (char *)this + v13;
  }
  else
  {
    v14 = 0;
    LODWORD(v22) = 0;
    LOWORD(v10) = 0;
    v15 = 0;
  }
  v16 = *((_DWORD *)this + 4);
  a5 = *(union _LARGE_INTEGER *)((char *)this + 8);
  *((_QWORD *)&v22 + 1) = v14;
  if ( (v16 & 1) != 0 )
  {
    v17 = (v16 & 2) != 0;
    if ( !v14 || !v15 || (v18 = (_WORD)v10 == 0, v19 = (struct _UNICODE_STRING *)&v22, v18) )
      v19 = 0;
    result = Streaming::Messaging::PackageLoader::CreateStagingDirectory(&v24, &v23, v19, v17);
  }
  else
  {
    if ( !v14 || !v15 || (v18 = (_WORD)v10 == 0, v21 = (struct _FILE_OBJECT *)&v22, v18) )
      v21 = 0;
    result = Streaming::Messaging::PackageLoader::CreateStreamableFile(&v24, &v23, v21, &a5);
  }
  if ( v6 != 4 || !a3 )
    return 3221225485LL;
  *a3 = result;
  *QuadPart = 4;
  return result;
}

```

## disassembly

```asm
0x140010c64  push    rbp
0x140010c66  push    rbx
0x140010c67  push    rsi
0x140010c68  push    rdi
0x140010c69  push    r12
0x140010c6b  push    r14
0x140010c6d  push    r15
0x140010c6f  mov     rbp, rsp
0x140010c72  sub     rsp, 50h
0x140010c76  mov     r14, qword ptr [rbp+arg_20]
0x140010c7a  xor     r12d, r12d
0x140010c7d  mov     dword ptr [rbp+var_10+4], r12d
0x140010c81  xorps   xmm0, xmm0
0x140010c84  mov     dword ptr [rbp+var_20+4], r12d
0x140010c88  mov     r15d, r9d
0x140010c8b  mov     rsi, r8
0x140010c8e  mov     [r14], r12d
0x140010c91  movups  [rbp+var_30], xmm0
0x140010c95  test    rcx, rcx
0x140010c98  jz      loc_140010DD8
0x140010c9e  cmp     edx, 30h ; '0'
0x140010ca1  jb      loc_140010DD8
0x140010ca7  cmp     edx, [rcx+4]
0x140010caa  jb      loc_140010DD8
0x140010cb0  movzx   r9d, word ptr [rcx+18h]
0x140010cb5  test    r9w, r9w
0x140010cb9  jz      loc_140010DD8
0x140010cbf  movzx   r10d, word ptr [rcx+20h]
0x140010cc4  test    r10w, r10w
0x140010cc8  jz      loc_140010DD8
0x140010cce  movzx   r8d, word ptr [rcx+28h]
0x140010cd3  cmp     r8d, 18h
0x140010cd7  ja      loc_140010DD8
0x140010cdd  mov     r11d, [rcx+14h]
0x140010ce1  lea     eax, [r11+r9]
0x140010ce5  cmp     eax, edx
0x140010ce7  ja      loc_140010DD8
0x140010ced  mov     ebx, [rcx+1Ch]
0x140010cf0  lea     eax, [rbx+r10]
0x140010cf4  cmp     eax, edx
0x140010cf6  ja      loc_140010DD8
0x140010cfc  mov     edi, [rcx+24h]
0x140010cff  lea     eax, [rdi+r8]
0x140010d03  cmp     eax, edx
0x140010d05  ja      loc_140010DD8
0x140010d0b  mov     [rbp+var_10.Length], r9w
0x140010d10  lea     rax, [rcx+r11]
0x140010d14  mov     [rbp+var_10.Buffer], rax
0x140010d18  lea     rax, [rcx+rbx]
0x140010d1c  mov     [rbp+var_20.Buffer], rax
0x140010d20  mov     [rbp+var_10.MaximumLength], r9w
0x140010d25  mov     [rbp+var_20.Length], r10w
0x140010d2a  mov     [rbp+var_20.MaximumLength], r10w
0x140010d2f  test    r8w, r8w
0x140010d33  jnz     short loc_140010D44
0x140010d35  mov     edx, r12d
0x140010d38  mov     dword ptr [rbp+var_30], r12d
0x140010d3c  mov     r8d, r12d
0x140010d3f  mov     r9d, r12d
0x140010d42  jmp     short loc_140010D56
0x140010d44  movzx   r9d, r8w
0x140010d48  mov     word ptr [rbp+var_30], r8w
0x140010d4d  mov     word ptr [rbp+var_30+2], r8w
0x140010d52  lea     rdx, [rcx+rdi]
0x140010d56  mov     rax, [rcx+8]
0x140010d5a  mov     r10d, [rcx+10h]
0x140010d5e  mov     qword ptr [rbp+arg_20], rax
0x140010d62  mov     qword ptr [rbp+var_30+8], rdx
0x140010d66  test    r10b, 1
0x140010d6a  jz      short loc_140010D9D
0x140010d6c  shr     r10d, 1
0x140010d6f  and     r10b, 1
0x140010d73  test    rdx, rdx
0x140010d76  jz      short loc_140010D88
0x140010d78  cmp     r12w, r9w
0x140010d7c  jz      short loc_140010D88
0x140010d7e  cmp     r12w, r8w
0x140010d82  lea     r8, [rbp+var_30]
0x140010d86  jnz     short loc_140010D8B
0x140010d88  mov     r8, r12; struct _UNICODE_STRING *
0x140010d8b  mov     r9b, r10b; unsigned __int8
0x140010d8e  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140010d92  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING *
0x140010d96  call    ?CreateStagingDirectory@PackageLoader@Messaging@Streaming@@SAJAEBU_UNICODE_STRING@@0PEAU4@E@Z; Streaming::Messaging::PackageLoader::CreateStagingDirectory(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING *,uchar)
0x140010d9b  jmp     short loc_140010DC6
0x140010d9d  test    rdx, rdx
0x140010da0  jz      short loc_140010DB2
0x140010da2  cmp     r12w, r9w
0x140010da6  jz      short loc_140010DB2
0x140010da8  cmp     r12w, r8w
0x140010dac  lea     r8, [rbp+var_30]
0x140010db0  jnz     short loc_140010DB5
0x140010db2  mov     r8, r12; struct _UNICODE_STRING *
0x140010db5  lea     r9, [rbp+arg_20]; union _LARGE_INTEGER *
0x140010db9  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140010dbd  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING *
0x140010dc1  call    ?CreateStreamableFile@PackageLoader@Messaging@Streaming@@SAJAEBU_UNICODE_STRING@@0PEAU4@AEAT_LARGE_INTEGER@@@Z; Streaming::Messaging::PackageLoader::CreateStreamableFile(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING *,_LARGE_INTEGER &)
0x140010dc6  cmp     r15d, 4
0x140010dca  jnz     short loc_140010DD8
0x140010dcc  test    rsi, rsi
0x140010dcf  jz      short loc_140010DD8
0x140010dd1  mov     [rsi], eax
0x140010dd3  mov     [r14], r15d
0x140010dd6  jmp     short loc_140010DDD
0x140010dd8  mov     eax, 0C000000Dh
0x140010ddd  add     rsp, 50h
0x140010de1  pop     r15
0x140010de3  pop     r14
0x140010de5  pop     r12
0x140010de7  pop     rdi
0x140010de8  pop     rsi
0x140010de9  pop     rbx
0x140010dea  pop     rbp
0x140010deb  retn
```
