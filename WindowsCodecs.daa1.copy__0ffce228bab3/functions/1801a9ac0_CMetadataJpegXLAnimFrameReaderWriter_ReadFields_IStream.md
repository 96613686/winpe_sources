# CMetadataJpegXLAnimFrameReaderWriter::ReadFields(IStream *)

- ea: `0x1801a9ac0`
- end: `0x1801a9c0b`
- name: `?ReadFields@CMetadataJpegXLAnimFrameReaderWriter@@MEAAJPEAUIStream@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(CMetadataJpegXLAnimFrameReaderWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18004f000`
- `0x1800bd9d4`
- `0x1801a9ac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a9b79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a9b79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9b2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9b2d`

## pseudocode

```c
__int64 __fastcall CMetadataJpegXLAnimFrameReaderWriter::ReadFields(
        CMetadataJpegXLAnimFrameReaderWriter *this,
        struct IStream *a2)
{
  _BYTE *v2; // rsi
  unsigned int v4; // ebx
  int v5; // eax
  bool v6; // zf
  int v7; // ecx
  SIZE_T v9; // rcx
  void *v10; // rax
  int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // [rsp+30h] [rbp+8h] BYREF

  v2 = (char *)this + 152;
  v13 = 0;
  v4 = CExternalStream::Read((CExternalStream *)(*((_QWORD *)this + 15) + 16LL), (char *)this + 152, 0x10u, &v13);
  v5 = (int)g_doStackCaptures;
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_10;
    goto LABEL_8;
  }
  if ( v13 != 16 )
    goto LABEL_5;
  if ( *v2 != 48 )
  {
    v4 = -2003292317;
    goto LABEL_6;
  }
  v9 = *((unsigned int *)this + 41);
  *((_BYTE *)this + 168) = 1;
  if ( !(_DWORD)v9 )
    return v4;
  if ( (v9 & 1) != 0 )
  {
LABEL_5:
    v4 = -2003292304;
LABEL_6:
    v6 = v5 == 0;
    goto LABEL_7;
  }
  v10 = CoTaskMemAlloc(v9);
  *((_QWORD *)this + 22) = v10;
  if ( v10 )
  {
    v11 = CExternalStream::Read((CExternalStream *)(*((_QWORD *)this + 15) + 16LL), v10, *((_DWORD *)this + 41), &v13);
    v4 = v11;
    if ( v11 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_10;
      v7 = v11;
      goto LABEL_9;
    }
    v12 = *((_DWORD *)this + 41);
    if ( v13 == v12 )
    {
      *(_WORD *)(*((_QWORD *)this + 22) + 2LL * ((v12 >> 1) - 1)) = 0;
      return v4;
    }
    v4 = -2003292304;
    v6 = (_DWORD)g_doStackCaptures == 0;
  }
  else
  {
    v6 = (_DWORD)g_doStackCaptures == 0;
    v4 = -2147024882;
  }
LABEL_7:
  if ( !v6 )
  {
LABEL_8:
    v7 = v4;
LABEL_9:
    DoStackCapture(v7);
  }
LABEL_10:
  CoTaskMemFree(*((LPVOID *)this + 22));
  *((_QWORD *)this + 22) = 0;
  return v4;
}

```

## disassembly

```asm
0x1801a9ac0  mov     rax, rsp
0x1801a9ac3  mov     [rax+10h], rbx
0x1801a9ac7  mov     [rax+18h], rsi
0x1801a9acb  push    rdi
0x1801a9acc  sub     rsp, 20h
0x1801a9ad0  lea     rsi, [rcx+98h]
0x1801a9ad7  mov     dword ptr [rax+8], 0
0x1801a9ade  mov     rdi, rcx
0x1801a9ae1  lea     r9, [rax+8]; unsigned int *
0x1801a9ae5  mov     rcx, [rcx+78h]
0x1801a9ae9  mov     r8d, 10h; unsigned int
0x1801a9aef  add     rcx, 10h; this
0x1801a9af3  mov     rdx, rsi; void *
0x1801a9af6  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801a9afb  mov     ebx, eax
0x1801a9afd  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801a9b03  test    ebx, ebx
0x1801a9b05  jns     short loc_1801A9B0F
0x1801a9b07  test    eax, eax
0x1801a9b09  jnz     short loc_1801A9B1F
0x1801a9b0b  test    ebx, ebx
0x1801a9b0d  js      short loc_1801A9B26
0x1801a9b0f  cmp     [rsp+28h+arg_0], 10h
0x1801a9b14  jz      short loc_1801A9B57
0x1801a9b16  mov     ebx, 88982F70h
0x1801a9b1b  test    eax, eax
0x1801a9b1d  jz      short loc_1801A9B26
0x1801a9b1f  mov     ecx, ebx; int
0x1801a9b21  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801a9b26  mov     rcx, [rdi+0B0h]; pv
0x1801a9b2d  call    cs:__imp_CoTaskMemFree
0x1801a9b34  nop     dword ptr [rax+rax+00h]
0x1801a9b39  mov     qword ptr [rdi+0B0h], 0
0x1801a9b44  mov     rsi, [rsp+28h+arg_10]
0x1801a9b49  mov     eax, ebx
0x1801a9b4b  mov     rbx, [rsp+28h+arg_8]
0x1801a9b50  add     rsp, 20h
0x1801a9b54  pop     rdi
0x1801a9b55  retn
0x1801a9b57  cmp     byte ptr [rsi], 30h ; '0'
0x1801a9b5a  jz      short loc_1801A9B63
0x1801a9b5c  mov     ebx, 88982F63h
0x1801a9b61  jmp     short loc_1801A9B1B
0x1801a9b63  mov     ecx, [rdi+0A4h]; cb
0x1801a9b69  mov     byte ptr [rdi+0A8h], 1
0x1801a9b70  test    ecx, ecx
0x1801a9b72  jz      short loc_1801A9B44
0x1801a9b74  test    cl, 1
0x1801a9b77  jnz     short loc_1801A9B16
0x1801a9b79  call    cs:__imp_CoTaskMemAlloc
0x1801a9b80  nop     dword ptr [rax+rax+00h]
0x1801a9b85  mov     [rdi+0B0h], rax
0x1801a9b8c  test    rax, rax
0x1801a9b8f  jnz     short loc_1801A9BA1
0x1801a9b91  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1801a9b97  mov     ebx, 8007000Eh
0x1801a9b9c  jmp     loc_1801A9B1D
0x1801a9ba1  mov     rcx, [rdi+78h]
0x1801a9ba5  lea     r9, [rsp+28h+arg_0]; unsigned int *
0x1801a9baa  mov     r8d, [rdi+0A4h]; unsigned int
0x1801a9bb1  add     rcx, 10h; this
0x1801a9bb5  mov     rdx, rax; void *
0x1801a9bb8  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801a9bbd  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801a9bc3  mov     ebx, eax
0x1801a9bc5  test    eax, eax
0x1801a9bc7  jns     short loc_1801A9BDC
0x1801a9bc9  test    ecx, ecx
0x1801a9bcb  jz      short loc_1801A9BD4
0x1801a9bcd  mov     ecx, eax
0x1801a9bcf  jmp     loc_1801A9B21
0x1801a9bd4  test    eax, eax
0x1801a9bd6  js      loc_1801A9B26
0x1801a9bdc  mov     eax, [rdi+0A4h]
0x1801a9be2  cmp     [rsp+28h+arg_0], eax
0x1801a9be6  jz      short loc_1801A9BF4
0x1801a9be8  mov     ebx, 88982F70h
0x1801a9bed  test    ecx, ecx
0x1801a9bef  jmp     loc_1801A9B1D
0x1801a9bf4  mov     rcx, [rdi+0B0h]
0x1801a9bfb  shr     eax, 1
0x1801a9bfd  lea     edx, [rax-1]
0x1801a9c00  xor     eax, eax
0x1801a9c02  mov     [rcx+rdx*2], ax
0x1801a9c06  jmp     loc_1801A9B44
```
