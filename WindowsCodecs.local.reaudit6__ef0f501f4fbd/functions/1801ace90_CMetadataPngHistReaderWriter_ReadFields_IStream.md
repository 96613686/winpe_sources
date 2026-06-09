# CMetadataPngHistReaderWriter::ReadFields(IStream *)

- ea: `0x1801ace90`
- end: `0x1801ad059`
- name: `?ReadFields@CMetadataPngHistReaderWriter@@MEAAJPEAUIStream@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(CMetadataPngHistReaderWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800542e8`
- `0x1800bd9d4`
- `0x18017e450`
- `0x1801ace90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801acf92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801acf92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801acf82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801acf82`

## pseudocode

```c
__int64 __fastcall CMetadataPngHistReaderWriter::ReadFields(CMetadataPngHistReaderWriter *this, struct IStream *a2)
{
  __int64 v2; // rax
  int FullBufferFromStream; // eax
  unsigned int v5; // ebx
  int v6; // ecx
  unsigned int v7; // edx
  int v8; // esi
  bool v9; // zf
  void *v10; // rcx
  LPVOID v11; // rax
  unsigned int v12; // esi
  __int64 v13; // rbp
  SIZE_T cb; // [rsp+40h] [rbp+8h] BYREF
  char Buf1; // [rsp+50h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 15);
  LODWORD(cb) = 0;
  FullBufferFromStream = ReadFullBufferFromStream((struct IStream *)((v2 + 16) & -(__int64)(v2 != 0)), &cb, 4u);
  v5 = FullBufferFromStream;
  if ( FullBufferFromStream >= 0 )
  {
    v7 = ((((_DWORD)cb << 16) | cb & 0xFF00) << 8) | ((WORD1(cb) | cb & 0xFF0000) >> 8);
    LODWORD(cb) = v7;
    if ( v7 < 2 || (v7 & 1) != 0 )
    {
      v9 = (_DWORD)g_doStackCaptures == 0;
    }
    else
    {
      FullBufferFromStream = ReadFullBufferFromStream(
                               (struct IStream *)((*((_QWORD *)this + 15) + 16LL)
                                                & -(__int64)(*((_QWORD *)this + 15) != 0)),
                               &Buf1,
                               4u);
      v8 = (int)g_doStackCaptures;
      v5 = FullBufferFromStream;
      if ( FullBufferFromStream < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          return v5;
        goto LABEL_3;
      }
      if ( !memcmp_0(&Buf1, "hISTwil", 4u) )
      {
        v10 = (void *)*((_QWORD *)this + 20);
        if ( v10 )
          CoTaskMemFree(v10);
        v11 = CoTaskMemAlloc((unsigned int)cb);
        *((_QWORD *)this + 20) = v11;
        if ( v11 )
        {
          v12 = 0;
          v9 = (unsigned int)cb >> 1 == 0;
          *((_DWORD *)this + 38) = (unsigned int)cb >> 1;
          if ( !v9 )
          {
            while ( 1 )
            {
              v13 = v12;
              FullBufferFromStream = ReadFullBufferFromStream(
                                       (struct IStream *)((*((_QWORD *)this + 15) + 16LL)
                                                        & -(__int64)(*((_QWORD *)this + 15) != 0)),
                                       (void *)(*((_QWORD *)this + 20) + 2LL * v12),
                                       2u);
              v5 = FullBufferFromStream;
              if ( FullBufferFromStream < 0 )
                break;
              ++v12;
              *(_WORD *)(*((_QWORD *)this + 20) + 2 * v13) = (*(_WORD *)(*((_QWORD *)this + 20) + 2 * v13) << 8)
                                                           | *(unsigned __int8 *)(*((_QWORD *)this + 20) + 2 * v13 + 1);
              if ( v12 >= *((_DWORD *)this + 38) )
                return v5;
            }
            if ( (_DWORD)g_doStackCaptures )
              goto LABEL_3;
          }
          return v5;
        }
        v9 = (_DWORD)g_doStackCaptures == 0;
        v5 = -2147024882;
LABEL_23:
        if ( !v9 )
        {
          v6 = v5;
          goto LABEL_25;
        }
        return v5;
      }
      v9 = v8 == 0;
    }
    v5 = -2003292317;
    goto LABEL_23;
  }
  if ( (_DWORD)g_doStackCaptures )
  {
LABEL_3:
    v6 = FullBufferFromStream;
LABEL_25:
    DoStackCapture(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x1801ace90  mov     [rsp+arg_8], rbx
0x1801ace95  push    rbp
0x1801ace96  push    rsi
0x1801ace97  push    rdi
0x1801ace98  sub     rsp, 20h
0x1801ace9c  mov     rax, [rcx+78h]
0x1801acea0  mov     rdi, rcx
0x1801acea3  mov     ebp, 4
0x1801acea8  mov     dword ptr [rsp+38h+cb], 0
0x1801aceb0  mov     r8d, ebp; unsigned int
0x1801aceb3  lea     rdx, [rax+10h]
0x1801aceb7  neg     rax
0x1801aceba  sbb     rcx, rcx
0x1801acebd  and     rcx, rdx; struct IStream *
0x1801acec0  lea     rdx, [rsp+38h+cb]; void *
0x1801acec5  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1801aceca  mov     ebx, eax
0x1801acecc  test    eax, eax
0x1801acece  jns     short loc_1801ACEE4
0x1801aced0  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801aced7  jz      loc_1801AD049
0x1801acedd  mov     ecx, eax
0x1801acedf  jmp     loc_1801AD044
0x1801acee4  mov     ecx, dword ptr [rsp+38h+cb]
0x1801acee8  mov     edx, ecx
0x1801aceea  and     edx, 0FF0000h
0x1801acef0  mov     eax, ecx
0x1801acef2  shr     eax, 10h
0x1801acef5  or      edx, eax
0x1801acef7  mov     eax, ecx
0x1801acef9  and     eax, 0FF00h
0x1801acefe  shl     ecx, 10h
0x1801acf01  or      eax, ecx
0x1801acf03  shr     edx, 8
0x1801acf06  shl     eax, 8
0x1801acf09  or      edx, eax
0x1801acf0b  mov     dword ptr [rsp+38h+cb], edx
0x1801acf0f  cmp     edx, 2
0x1801acf12  jb      loc_1801AD034
0x1801acf18  test    dl, 1
0x1801acf1b  jnz     loc_1801AD034
0x1801acf21  mov     rax, [rdi+78h]
0x1801acf25  mov     r8d, ebp; unsigned int
0x1801acf28  lea     rdx, [rax+10h]
0x1801acf2c  neg     rax
0x1801acf2f  sbb     rcx, rcx
0x1801acf32  and     rcx, rdx; struct IStream *
0x1801acf35  lea     rdx, [rsp+38h+Buf1]; void *
0x1801acf3a  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1801acf3f  mov     esi, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801acf45  mov     ebx, eax
0x1801acf47  test    eax, eax
0x1801acf49  jns     short loc_1801ACF57
0x1801acf4b  test    esi, esi
0x1801acf4d  jnz     short loc_1801ACEDD
0x1801acf4f  test    eax, eax
0x1801acf51  js      loc_1801AD049
0x1801acf57  mov     r8, rbp; Size
0x1801acf5a  lea     rdx, aHistwil; "hISTwil"
0x1801acf61  lea     rcx, [rsp+38h+Buf1]; Buf1
0x1801acf66  call    memcmp_0
0x1801acf6b  test    eax, eax
0x1801acf6d  jz      short loc_1801ACF76
0x1801acf6f  test    esi, esi
0x1801acf71  jmp     loc_1801AD03B
0x1801acf76  mov     rcx, [rdi+0A0h]; pv
0x1801acf7d  test    rcx, rcx
0x1801acf80  jz      short loc_1801ACF8E
0x1801acf82  call    cs:__imp_CoTaskMemFree
0x1801acf89  nop     dword ptr [rax+rax+00h]
0x1801acf8e  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x1801acf92  call    cs:__imp_CoTaskMemAlloc
0x1801acf99  nop     dword ptr [rax+rax+00h]
0x1801acf9e  mov     [rdi+0A0h], rax
0x1801acfa5  test    rax, rax
0x1801acfa8  jnz     short loc_1801ACFBA
0x1801acfaa  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1801acfb0  mov     ebx, 8007000Eh
0x1801acfb5  jmp     loc_1801AD040
0x1801acfba  mov     eax, dword ptr [rsp+38h+cb]
0x1801acfbe  mov     esi, 0
0x1801acfc3  shr     eax, 1
0x1801acfc5  mov     [rdi+98h], eax
0x1801acfcb  jz      short loc_1801AD049
0x1801acfcd  mov     rax, [rdi+0A0h]
0x1801acfd4  mov     r8d, 2; unsigned int
0x1801acfda  mov     rcx, [rdi+78h]
0x1801acfde  mov     ebp, esi
0x1801acfe0  lea     rdx, [rax+rbp*2]; void *
0x1801acfe4  lea     rax, [rcx+10h]
0x1801acfe8  neg     rcx
0x1801acfeb  sbb     rcx, rcx
0x1801acfee  and     rcx, rax; struct IStream *
0x1801acff1  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1801acff6  mov     ebx, eax
0x1801acff8  test    eax, eax
0x1801acffa  jns     short loc_1801AD00D
0x1801acffc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801ad003  jnz     loc_1801ACEDD
0x1801ad009  test    eax, eax
0x1801ad00b  js      short loc_1801AD049
0x1801ad00d  mov     rdx, [rdi+0A0h]
0x1801ad014  inc     esi
0x1801ad016  movzx   eax, word ptr [rdx+rbp*2]
0x1801ad01a  movzx   ecx, byte ptr [rdx+rbp*2+1]
0x1801ad01f  shl     ax, 8
0x1801ad023  or      cx, ax
0x1801ad026  mov     [rdx+rbp*2], cx
0x1801ad02a  cmp     esi, [rdi+98h]
0x1801ad030  jb      short loc_1801ACFCD
0x1801ad032  jmp     short loc_1801AD049
0x1801ad034  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801ad03b  mov     ebx, 88982F63h
0x1801ad040  jz      short loc_1801AD049
0x1801ad042  mov     ecx, ebx; int
0x1801ad044  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801ad049  mov     eax, ebx
0x1801ad04b  mov     rbx, [rsp+38h+arg_8]
0x1801ad050  add     rsp, 20h
0x1801ad054  pop     rdi
0x1801ad055  pop     rsi
0x1801ad056  pop     rbp
0x1801ad057  retn
```
