# CMetadataJpegXLAnimFrameReaderWriter::ReadFields(IStream *)

- ea: `0x1801a66b0`
- end: `0x1801a67eb`
- name: `?ReadFields@CMetadataJpegXLAnimFrameReaderWriter@@MEAAJPEAUIStream@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(CMetadataJpegXLAnimFrameReaderWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180023050`
- `0x1800bb784`
- `0x1801a66b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a6762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a6762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a671d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a671d`

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
0x1801a66b0  mov     rax, rsp
0x1801a66b3  mov     [rax+10h], rbx
0x1801a66b7  mov     [rax+18h], rsi
0x1801a66bb  push    rdi
0x1801a66bc  sub     rsp, 20h
0x1801a66c0  lea     rsi, [rcx+98h]
0x1801a66c7  mov     dword ptr [rax+8], 0
0x1801a66ce  mov     rdi, rcx
0x1801a66d1  lea     r9, [rax+8]; unsigned int *
0x1801a66d5  mov     rcx, [rcx+78h]
0x1801a66d9  mov     r8d, 10h; unsigned int
0x1801a66df  add     rcx, 10h; this
0x1801a66e3  mov     rdx, rsi; void *
0x1801a66e6  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801a66eb  mov     ebx, eax
0x1801a66ed  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801a66f3  test    ebx, ebx
0x1801a66f5  jns     short loc_1801A66FF
0x1801a66f7  test    eax, eax
0x1801a66f9  jnz     short loc_1801A670F
0x1801a66fb  test    ebx, ebx
0x1801a66fd  js      short loc_1801A6716
0x1801a66ff  cmp     [rsp+28h+arg_0], 10h
0x1801a6704  jz      short loc_1801A6740
0x1801a6706  mov     ebx, 88982F70h
0x1801a670b  test    eax, eax
0x1801a670d  jz      short loc_1801A6716
0x1801a670f  mov     ecx, ebx; int
0x1801a6711  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801a6716  mov     rcx, [rdi+0B0h]; pv
0x1801a671d  call    cs:__imp_CoTaskMemFree
0x1801a6723  mov     qword ptr [rdi+0B0h], 0
0x1801a672e  mov     rsi, [rsp+28h+arg_10]
0x1801a6733  mov     eax, ebx
0x1801a6735  mov     rbx, [rsp+28h+arg_8]
0x1801a673a  add     rsp, 20h
0x1801a673e  pop     rdi
0x1801a673f  retn
0x1801a6740  cmp     byte ptr [rsi], 30h ; '0'
0x1801a6743  jz      short loc_1801A674C
0x1801a6745  mov     ebx, 88982F63h
0x1801a674a  jmp     short loc_1801A670B
0x1801a674c  mov     ecx, [rdi+0A4h]; cb
0x1801a6752  mov     byte ptr [rdi+0A8h], 1
0x1801a6759  test    ecx, ecx
0x1801a675b  jz      short loc_1801A672E
0x1801a675d  test    cl, 1
0x1801a6760  jnz     short loc_1801A6706
0x1801a6762  call    cs:__imp_CoTaskMemAlloc
0x1801a6768  mov     [rdi+0B0h], rax
0x1801a676f  test    rax, rax
0x1801a6772  jnz     short loc_1801A6781
0x1801a6774  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1801a677a  mov     ebx, 8007000Eh
0x1801a677f  jmp     short loc_1801A670D
0x1801a6781  mov     rcx, [rdi+78h]
0x1801a6785  lea     r9, [rsp+28h+arg_0]; unsigned int *
0x1801a678a  mov     r8d, [rdi+0A4h]; unsigned int
0x1801a6791  add     rcx, 10h; this
0x1801a6795  mov     rdx, rax; void *
0x1801a6798  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801a679d  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801a67a3  mov     ebx, eax
0x1801a67a5  test    eax, eax
0x1801a67a7  jns     short loc_1801A67BC
0x1801a67a9  test    ecx, ecx
0x1801a67ab  jz      short loc_1801A67B4
0x1801a67ad  mov     ecx, eax
0x1801a67af  jmp     loc_1801A6711
0x1801a67b4  test    eax, eax
0x1801a67b6  js      loc_1801A6716
0x1801a67bc  mov     eax, [rdi+0A4h]
0x1801a67c2  cmp     [rsp+28h+arg_0], eax
0x1801a67c6  jz      short loc_1801A67D4
0x1801a67c8  mov     ebx, 88982F70h
0x1801a67cd  test    ecx, ecx
0x1801a67cf  jmp     loc_1801A670D
0x1801a67d4  mov     rcx, [rdi+0B0h]
0x1801a67db  shr     eax, 1
0x1801a67dd  lea     edx, [rax-1]
0x1801a67e0  xor     eax, eax
0x1801a67e2  mov     [rcx+rdx*2], ax
0x1801a67e6  jmp     loc_1801A672E
```
