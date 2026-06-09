# CMetadataPngHistReaderWriter::ReadFields(IStream *)

- ea: `0x1801a9980`
- end: `0x1801a9b3c`
- name: `?ReadFields@CMetadataPngHistReaderWriter@@MEAAJPEAUIStream@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(CMetadataPngHistReaderWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180036cb4`
- `0x1800bb784`
- `0x18017b540`
- `0x1801a9980`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a9a7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a9a7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9a72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9a72`

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
0x1801a9980  mov     [rsp+arg_8], rbx
0x1801a9985  push    rbp
0x1801a9986  push    rsi
0x1801a9987  push    rdi
0x1801a9988  sub     rsp, 20h
0x1801a998c  mov     rax, [rcx+78h]
0x1801a9990  mov     rdi, rcx
0x1801a9993  mov     ebp, 4
0x1801a9998  mov     dword ptr [rsp+38h+cb], 0
0x1801a99a0  mov     r8d, ebp; unsigned int
0x1801a99a3  lea     rdx, [rax+10h]
0x1801a99a7  neg     rax
0x1801a99aa  sbb     rcx, rcx
0x1801a99ad  and     rcx, rdx; struct IStream *
0x1801a99b0  lea     rdx, [rsp+38h+cb]; void *
0x1801a99b5  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1801a99ba  mov     ebx, eax
0x1801a99bc  test    eax, eax
0x1801a99be  jns     short loc_1801A99D4
0x1801a99c0  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801a99c7  jz      loc_1801A9B2D
0x1801a99cd  mov     ecx, eax
0x1801a99cf  jmp     loc_1801A9B28
0x1801a99d4  mov     ecx, dword ptr [rsp+38h+cb]
0x1801a99d8  mov     edx, ecx
0x1801a99da  and     edx, 0FF0000h
0x1801a99e0  mov     eax, ecx
0x1801a99e2  shr     eax, 10h
0x1801a99e5  or      edx, eax
0x1801a99e7  mov     eax, ecx
0x1801a99e9  and     eax, 0FF00h
0x1801a99ee  shl     ecx, 10h
0x1801a99f1  or      eax, ecx
0x1801a99f3  shr     edx, 8
0x1801a99f6  shl     eax, 8
0x1801a99f9  or      edx, eax
0x1801a99fb  mov     dword ptr [rsp+38h+cb], edx
0x1801a99ff  cmp     edx, 2
0x1801a9a02  jb      loc_1801A9B18
0x1801a9a08  test    dl, 1
0x1801a9a0b  jnz     loc_1801A9B18
0x1801a9a11  mov     rax, [rdi+78h]
0x1801a9a15  mov     r8d, ebp; unsigned int
0x1801a9a18  lea     rdx, [rax+10h]
0x1801a9a1c  neg     rax
0x1801a9a1f  sbb     rcx, rcx
0x1801a9a22  and     rcx, rdx; struct IStream *
0x1801a9a25  lea     rdx, [rsp+38h+Buf1]; void *
0x1801a9a2a  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1801a9a2f  mov     esi, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801a9a35  mov     ebx, eax
0x1801a9a37  test    eax, eax
0x1801a9a39  jns     short loc_1801A9A47
0x1801a9a3b  test    esi, esi
0x1801a9a3d  jnz     short loc_1801A99CD
0x1801a9a3f  test    eax, eax
0x1801a9a41  js      loc_1801A9B2D
0x1801a9a47  mov     r8, rbp; Size
0x1801a9a4a  lea     rdx, aHistwil; "hISTwil"
0x1801a9a51  lea     rcx, [rsp+38h+Buf1]; Buf1
0x1801a9a56  call    memcmp_0
0x1801a9a5b  test    eax, eax
0x1801a9a5d  jz      short loc_1801A9A66
0x1801a9a5f  test    esi, esi
0x1801a9a61  jmp     loc_1801A9B1F
0x1801a9a66  mov     rcx, [rdi+0A0h]; pv
0x1801a9a6d  test    rcx, rcx
0x1801a9a70  jz      short loc_1801A9A78
0x1801a9a72  call    cs:__imp_CoTaskMemFree
0x1801a9a78  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x1801a9a7c  call    cs:__imp_CoTaskMemAlloc
0x1801a9a82  mov     [rdi+0A0h], rax
0x1801a9a89  test    rax, rax
0x1801a9a8c  jnz     short loc_1801A9A9E
0x1801a9a8e  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1801a9a94  mov     ebx, 8007000Eh
0x1801a9a99  jmp     loc_1801A9B24
0x1801a9a9e  mov     eax, dword ptr [rsp+38h+cb]
0x1801a9aa2  mov     esi, 0
0x1801a9aa7  shr     eax, 1
0x1801a9aa9  mov     [rdi+98h], eax
0x1801a9aaf  jz      short loc_1801A9B2D
0x1801a9ab1  mov     rax, [rdi+0A0h]
0x1801a9ab8  mov     r8d, 2; unsigned int
0x1801a9abe  mov     rcx, [rdi+78h]
0x1801a9ac2  mov     ebp, esi
0x1801a9ac4  lea     rdx, [rax+rbp*2]; void *
0x1801a9ac8  lea     rax, [rcx+10h]
0x1801a9acc  neg     rcx
0x1801a9acf  sbb     rcx, rcx
0x1801a9ad2  and     rcx, rax; struct IStream *
0x1801a9ad5  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1801a9ada  mov     ebx, eax
0x1801a9adc  test    eax, eax
0x1801a9ade  jns     short loc_1801A9AF1
0x1801a9ae0  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801a9ae7  jnz     loc_1801A99CD
0x1801a9aed  test    eax, eax
0x1801a9aef  js      short loc_1801A9B2D
0x1801a9af1  mov     rdx, [rdi+0A0h]
0x1801a9af8  inc     esi
0x1801a9afa  movzx   eax, word ptr [rdx+rbp*2]
0x1801a9afe  movzx   ecx, byte ptr [rdx+rbp*2+1]
0x1801a9b03  shl     ax, 8
0x1801a9b07  or      cx, ax
0x1801a9b0a  mov     [rdx+rbp*2], cx
0x1801a9b0e  cmp     esi, [rdi+98h]
0x1801a9b14  jb      short loc_1801A9AB1
0x1801a9b16  jmp     short loc_1801A9B2D
0x1801a9b18  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801a9b1f  mov     ebx, 88982F63h
0x1801a9b24  jz      short loc_1801A9B2D
0x1801a9b26  mov     ecx, ebx; int
0x1801a9b28  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801a9b2d  mov     eax, ebx
0x1801a9b2f  mov     rbx, [rsp+38h+arg_8]
0x1801a9b34  add     rsp, 20h
0x1801a9b38  pop     rdi
0x1801a9b39  pop     rsi
0x1801a9b3a  pop     rbp
0x1801a9b3b  retn
```
