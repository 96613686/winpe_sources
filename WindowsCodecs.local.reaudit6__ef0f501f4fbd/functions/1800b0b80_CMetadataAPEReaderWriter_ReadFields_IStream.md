# CMetadataAPEReaderWriter::ReadFields(IStream *)

- ea: `0x1800b0b80`
- end: `0x1800b0d61`
- name: `?ReadFields@CMetadataAPEReaderWriter@@MEAAJPEAUIStream@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(CMetadataAPEReaderWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800542e8`
- `0x1800b0b80`
- `0x1800bd9d4`
- `0x1800c75e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b0c34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b0c34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0d21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0d21`

## pseudocode

```c
__int64 __fastcall CMetadataAPEReaderWriter::ReadFields(CMetadataAPEReaderWriter *this, struct IStream *a2)
{
  int FullBufferFromStream; // eax
  unsigned int v5; // ebx
  bool v6; // cf
  int v7; // eax
  unsigned int v8; // esi
  unsigned int v9; // esi
  unsigned __int8 *v10; // rax
  unsigned __int8 *v11; // rbp
  int v12; // eax
  bool v14; // zf
  int v15; // ecx
  int v16[10]; // [rsp+20h] [rbp-28h] BYREF
  char v17; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int8 v18; // [rsp+68h] [rbp+20h] BYREF
  char v19; // [rsp+69h] [rbp+21h]
  unsigned __int8 v20; // [rsp+6Ah] [rbp+22h]

  v17 = 0;
  FullBufferFromStream = ReadFullBufferFromStream(a2, &v18, 3u);
  v5 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
    goto LABEL_21;
  v6 = v18 < 0x21u;
  if ( v18 == 33 && (v6 = v19 != -1, v19 == -1) && (v6 = v20 < 0xBu, v20 == 11) )
    v7 = 0;
  else
    v7 = v6 ? -1 : 1;
  if ( v7 )
  {
    v5 = -2003292317;
    goto LABEL_18;
  }
  FullBufferFromStream = ReadFullBufferFromStream(a2, (char *)this + 152, 0xBu);
  v5 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
  {
LABEL_21:
    if ( !(_DWORD)g_doStackCaptures )
      return v5;
    v15 = FullBufferFromStream;
LABEL_23:
    DoStackCapture(v15);
    return v5;
  }
  v8 = *((_DWORD *)this + 32) - *((_DWORD *)this + 34);
  *((_DWORD *)this + 41) = 1;
  if ( v8 < 0xF )
  {
    v5 = -2147024362;
LABEL_18:
    v14 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_19;
  }
  v9 = v8 - 15;
  v10 = (unsigned __int8 *)CoTaskMemAlloc(v9);
  v11 = v10;
  if ( !v10 )
  {
    v5 = -2147024882;
    goto LABEL_18;
  }
  v12 = ReadFullBufferFromStream(a2, v10, v9);
  v5 = v12;
  if ( v12 >= 0 )
  {
    v16[0] = 0;
    v12 = CMetadataAPEReaderWriter::HrCheckApplicationData(this, v11, v9, v16);
    v5 = v12;
    if ( v12 >= 0 )
    {
      if ( v16[0] == 1 )
        --v9;
      *((_WORD *)this + 84) = 4113;
      *((_DWORD *)this + 44) = v9;
      *((_QWORD *)this + 23) = v11;
      v5 = ReadFullBufferFromStream(a2, &v17, 1u);
      if ( (v5 & 0x80000000) != 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          return v5;
LABEL_20:
        v15 = v5;
        goto LABEL_23;
      }
      if ( !v17 )
        return v5;
      v5 = -2003292317;
      v14 = (_DWORD)g_doStackCaptures == 0;
LABEL_19:
      if ( v14 )
        return v5;
      goto LABEL_20;
    }
  }
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(v12);
  CoTaskMemFree(v11);
  return v5;
}

```

## disassembly

```asm
0x1800b0b80  mov     rax, rsp
0x1800b0b83  mov     [rax+8], rbx
0x1800b0b87  mov     [rax+10h], rbp
0x1800b0b8b  push    rsi
0x1800b0b8c  push    rdi
0x1800b0b8d  push    r14
0x1800b0b8f  sub     rsp, 30h
0x1800b0b93  mov     r14, rdx
0x1800b0b96  mov     byte ptr [rax+18h], 0
0x1800b0b9a  mov     rdi, rcx
0x1800b0b9d  lea     rdx, [rax+20h]; void *
0x1800b0ba1  mov     rcx, r14; struct IStream *
0x1800b0ba4  mov     r8d, 3; unsigned int
0x1800b0baa  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800b0baf  mov     ebx, eax
0x1800b0bb1  test    eax, eax
0x1800b0bb3  js      loc_1800B0CFC
0x1800b0bb9  mov     al, [rsp+48h+arg_18]
0x1800b0bbd  cmp     al, cs:byte_1801FBB10
0x1800b0bc3  jnz     loc_1800B0D39
0x1800b0bc9  mov     al, [rsp+48h+arg_19]
0x1800b0bcd  cmp     al, cs:byte_1801FBB11
0x1800b0bd3  jnz     loc_1800B0D39
0x1800b0bd9  mov     al, [rsp+48h+arg_1A]
0x1800b0bdd  cmp     al, cs:byte_1801FBB12
0x1800b0be3  jnz     loc_1800B0D39
0x1800b0be9  xor     eax, eax
0x1800b0beb  test    eax, eax
0x1800b0bed  jnz     loc_1800B0D43
0x1800b0bf3  lea     rdx, [rdi+98h]; void *
0x1800b0bfa  mov     rcx, r14; struct IStream *
0x1800b0bfd  lea     r8d, [rax+0Bh]; unsigned int
0x1800b0c01  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800b0c06  mov     ebx, eax
0x1800b0c08  test    eax, eax
0x1800b0c0a  js      loc_1800B0CFC
0x1800b0c10  mov     esi, [rdi+80h]
0x1800b0c16  sub     esi, [rdi+88h]
0x1800b0c1c  mov     dword ptr [rdi+0A4h], 1
0x1800b0c26  cmp     esi, 0Fh
0x1800b0c29  jb      loc_1800B0CEA
0x1800b0c2f  add     esi, 0FFFFFFF1h
0x1800b0c32  mov     ecx, esi; cb
0x1800b0c34  call    cs:__imp_CoTaskMemAlloc
0x1800b0c3b  nop     dword ptr [rax+rax+00h]
0x1800b0c40  mov     rbp, rax
0x1800b0c43  test    rax, rax
0x1800b0c46  jz      loc_1800B0D4A
0x1800b0c4c  mov     r8d, esi; unsigned int
0x1800b0c4f  mov     rdx, rax; void *
0x1800b0c52  mov     rcx, r14; struct IStream *
0x1800b0c55  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800b0c5a  mov     ebx, eax
0x1800b0c5c  test    eax, eax
0x1800b0c5e  js      loc_1800B0D0E
0x1800b0c64  lea     r9, [rsp+48h+var_28]; int *
0x1800b0c69  mov     [rsp+48h+var_28], 0
0x1800b0c71  mov     r8d, esi; unsigned int
0x1800b0c74  mov     rdx, rbp; unsigned __int8 *
0x1800b0c77  mov     rcx, rdi; this
0x1800b0c7a  call    ?HrCheckApplicationData@CMetadataAPEReaderWriter@@MEAAJPEAEIPEAH@Z; CMetadataAPEReaderWriter::HrCheckApplicationData(uchar *,uint,int *)
0x1800b0c7f  mov     ebx, eax
0x1800b0c81  test    eax, eax
0x1800b0c83  js      loc_1800B0D0E
0x1800b0c89  cmp     [rsp+48h+var_28], 1
0x1800b0c8e  jz      loc_1800B0D51
0x1800b0c94  mov     r8d, 1; unsigned int
0x1800b0c9a  mov     word ptr [rdi+0A8h], 1011h
0x1800b0ca3  lea     rdx, [rsp+48h+arg_10]; void *
0x1800b0ca8  mov     [rdi+0B0h], esi
0x1800b0cae  mov     rcx, r14; struct IStream *
0x1800b0cb1  mov     [rdi+0B8h], rbp
0x1800b0cb8  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800b0cbd  mov     ebx, eax
0x1800b0cbf  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800b0cc5  test    ebx, ebx
0x1800b0cc7  js      short loc_1800B0D2F
0x1800b0cc9  cmp     [rsp+48h+arg_10], 0
0x1800b0cce  jnz     loc_1800B0D58
0x1800b0cd4  mov     rbp, [rsp+48h+arg_8]
0x1800b0cd9  mov     eax, ebx
0x1800b0cdb  mov     rbx, [rsp+48h+arg_0]
0x1800b0ce0  add     rsp, 30h
0x1800b0ce4  pop     r14
0x1800b0ce6  pop     rdi
0x1800b0ce7  pop     rsi
0x1800b0ce8  retn
0x1800b0cea  mov     ebx, 80070216h
0x1800b0cef  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800b0cf6  jz      short loc_1800B0CD4
0x1800b0cf8  mov     ecx, ebx
0x1800b0cfa  jmp     short loc_1800B0D07
0x1800b0cfc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800b0d03  jz      short loc_1800B0CD4
0x1800b0d05  mov     ecx, eax; int
0x1800b0d07  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b0d0c  jmp     short loc_1800B0CD4
0x1800b0d0e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800b0d15  jz      short loc_1800B0D1E
0x1800b0d17  mov     ecx, eax; int
0x1800b0d19  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b0d1e  mov     rcx, rbp; pv
0x1800b0d21  call    cs:__imp_CoTaskMemFree
0x1800b0d28  nop     dword ptr [rax+rax+00h]
0x1800b0d2d  jmp     short loc_1800B0CD4
0x1800b0d2f  test    eax, eax
0x1800b0d31  jnz     short loc_1800B0CF8
0x1800b0d33  test    ebx, ebx
0x1800b0d35  jns     short loc_1800B0CC9
0x1800b0d37  jmp     short loc_1800B0CD4
0x1800b0d39  sbb     eax, eax
0x1800b0d3b  or      eax, 1
0x1800b0d3e  jmp     loc_1800B0BEB
0x1800b0d43  mov     ebx, 88982F63h
0x1800b0d48  jmp     short loc_1800B0CEF
0x1800b0d4a  mov     ebx, 8007000Eh
0x1800b0d4f  jmp     short loc_1800B0CEF
0x1800b0d51  dec     esi
0x1800b0d53  jmp     loc_1800B0C94
0x1800b0d58  mov     ebx, 88982F63h
0x1800b0d5d  test    eax, eax
0x1800b0d5f  jmp     short loc_1800B0CF6
```
