# CMetadataPngBkgdReaderWriter::ReadFields(IStream *)

- ea: `0x1801b4c10`
- end: `0x1801b4ecb`
- name: `?ReadFields@CMetadataPngBkgdReaderWriter@@MEAAJPEAUIStream@@@Z`
- size: `699`
- prototype: `__int64 __fastcall(CMetadataPngBkgdReaderWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18004f000`
- `0x1800bd9d4`
- `0x18017e450`
- `0x1801b4c10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b4da7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b4da7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b4eaf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b4eaf`

## pseudocode

```c
__int64 __fastcall CMetadataPngBkgdReaderWriter::ReadFields(CMetadataPngBkgdReaderWriter *this, struct IStream *a2)
{
  CExternalStream *v3; // rcx
  int v4; // eax
  int v5; // ebx
  int v6; // ecx
  CExternalStream *v7; // rcx
  int v8; // esi
  bool v9; // zf
  int v10; // ecx
  unsigned __int16 v11; // ax
  unsigned __int16 v12; // cx
  LPVOID v13; // rax
  __int64 i; // rsi
  _BYTE Buf1[16]; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int16 v17; // [rsp+50h] [rbp+20h] BYREF
  size_t Size; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v19; // [rsp+68h] [rbp+38h] BYREF

  LODWORD(Size) = 0;
  v19 = 0;
  v3 = (CExternalStream *)(*((_QWORD *)this + 15) + 16LL);
  v17 = 0;
  v4 = CExternalStream::Read(v3, &v19, 4u, (unsigned int *)&Size);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
    {
LABEL_3:
      v6 = v4;
LABEL_14:
      DoStackCapture(v6);
    }
LABEL_45:
    PropVariantClear((PROPVARIANT *)this + 19);
    return (unsigned int)v5;
  }
  if ( (_DWORD)Size != 4 )
  {
    v5 = -2003292304;
LABEL_27:
    v9 = (_DWORD)g_doStackCaptures == 0;
LABEL_12:
    if ( !v9 )
    {
LABEL_13:
      v6 = v5;
      goto LABEL_14;
    }
    goto LABEL_45;
  }
  v7 = (CExternalStream *)(*((_QWORD *)this + 15) + 16LL);
  v19 = (((v19 << 16) | v19 & 0xFF00) << 8) | ((HIWORD(v19) | v19 & 0xFF0000) >> 8);
  v4 = CExternalStream::Read(v7, Buf1, 4u, (unsigned int *)&Size);
  v8 = (int)g_doStackCaptures;
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_45;
    goto LABEL_3;
  }
  if ( (_DWORD)Size != 4 )
  {
    v5 = -2003292304;
LABEL_11:
    v9 = v8 == 0;
    goto LABEL_12;
  }
  if ( memcmp_0(Buf1, "bKGD", 4u) )
  {
    v5 = -2003292317;
    goto LABEL_11;
  }
  switch ( v19 )
  {
    case 2u:
      v4 = CExternalStream::Read((CExternalStream *)(*((_QWORD *)this + 15) + 16LL), &v17, 2u, (unsigned int *)&Size);
      v10 = (int)g_doStackCaptures;
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_45;
        goto LABEL_3;
      }
      if ( (_DWORD)Size != v19 )
      {
LABEL_22:
        v5 = -2003292304;
        v9 = v10 == 0;
        goto LABEL_12;
      }
      v11 = v17;
      v12 = v17;
      *((_WORD *)this + 76) = 18;
      *((_WORD *)this + 80) = (v11 << 8) | HIBYTE(v12);
      break;
    case 6u:
      *((_WORD *)this + 76) = 4114;
      *((_DWORD *)this + 40) = 3;
      v13 = CoTaskMemAlloc(6u);
      *((_QWORD *)this + 21) = v13;
      if ( !v13 )
      {
        v5 = -2147024882;
        goto LABEL_27;
      }
      for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
      {
        v5 = CExternalStream::Read((CExternalStream *)(*((_QWORD *)this + 15) + 16LL), &v17, 2u, (unsigned int *)&Size);
        if ( v5 < 0 )
        {
          if ( (_DWORD)g_doStackCaptures )
            goto LABEL_13;
          goto LABEL_45;
        }
        if ( (_DWORD)Size != 2 )
        {
          v5 = -2003292304;
          v9 = (_DWORD)g_doStackCaptures == 0;
          goto LABEL_12;
        }
        *(_WORD *)(*((_QWORD *)this + 21) + 2 * i) = (v17 << 8) | HIBYTE(v17);
      }
      break;
    case 1u:
      v4 = CExternalStream::Read(
             (CExternalStream *)(*((_QWORD *)this + 15) + 16LL),
             (char *)this + 160,
             1u,
             (unsigned int *)&Size);
      v10 = (int)g_doStackCaptures;
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_45;
        goto LABEL_3;
      }
      if ( (_DWORD)Size != v19 )
        goto LABEL_22;
      *((_WORD *)this + 76) = 17;
      break;
    default:
      v5 = -2003292317;
      if ( v8 )
        DoStackCapture(-2003292317);
      break;
  }
  if ( v5 < 0 )
    goto LABEL_45;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801b4c10  mov     [rsp-18h+arg_8], rbx
0x1801b4c15  push    rbp
0x1801b4c16  push    rsi
0x1801b4c17  push    rdi
0x1801b4c18  mov     rbp, rsp
0x1801b4c1b  sub     rsp, 30h
0x1801b4c1f  xor     eax, eax
0x1801b4c21  mov     dword ptr [rbp+Size], 0
0x1801b4c28  mov     rdi, rcx
0x1801b4c2b  mov     [rbp+arg_18], 0
0x1801b4c32  mov     rcx, [rcx+78h]
0x1801b4c36  lea     r9, [rbp+Size]; unsigned int *
0x1801b4c3a  add     rcx, 10h; this
0x1801b4c3e  mov     [rbp+arg_0], ax
0x1801b4c42  lea     r8d, [rax+4]; unsigned int
0x1801b4c46  lea     rdx, [rbp+arg_18]; void *
0x1801b4c4a  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801b4c4f  mov     ebx, eax
0x1801b4c51  test    eax, eax
0x1801b4c53  jns     short loc_1801B4C69
0x1801b4c55  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b4c5c  jz      loc_1801B4EA8
0x1801b4c62  mov     ecx, eax
0x1801b4c64  jmp     loc_1801B4CEA
0x1801b4c69  cmp     dword ptr [rbp+Size], 4
0x1801b4c6d  jz      short loc_1801B4C79
0x1801b4c6f  mov     ebx, 88982F70h
0x1801b4c74  jmp     loc_1801B4DC4
0x1801b4c79  mov     ecx, [rbp+arg_18]
0x1801b4c7c  lea     r9, [rbp+Size]; unsigned int *
0x1801b4c80  mov     edx, ecx
0x1801b4c82  mov     eax, ecx
0x1801b4c84  shr     eax, 10h
0x1801b4c87  and     edx, 0FF0000h
0x1801b4c8d  or      edx, eax
0x1801b4c8f  mov     r8d, 4; unsigned int
0x1801b4c95  mov     eax, ecx
0x1801b4c97  shr     edx, 8
0x1801b4c9a  shl     ecx, 10h
0x1801b4c9d  and     eax, 0FF00h
0x1801b4ca2  or      eax, ecx
0x1801b4ca4  mov     rcx, [rdi+78h]
0x1801b4ca8  shl     eax, 8
0x1801b4cab  add     rcx, 10h; this
0x1801b4caf  or      edx, eax
0x1801b4cb1  mov     [rbp+arg_18], edx
0x1801b4cb4  lea     rdx, [rbp+Buf1]; void *
0x1801b4cb8  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801b4cbd  mov     esi, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801b4cc3  mov     ebx, eax
0x1801b4cc5  test    eax, eax
0x1801b4cc7  jns     short loc_1801B4CD5
0x1801b4cc9  test    esi, esi
0x1801b4ccb  jnz     short loc_1801B4C62
0x1801b4ccd  test    eax, eax
0x1801b4ccf  js      loc_1801B4EA8
0x1801b4cd5  cmp     dword ptr [rbp+Size], 4
0x1801b4cd9  jz      short loc_1801B4CF4
0x1801b4cdb  mov     ebx, 88982F70h
0x1801b4ce0  test    esi, esi
0x1801b4ce2  jz      loc_1801B4EA8
0x1801b4ce8  mov     ecx, ebx; int
0x1801b4cea  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b4cef  jmp     loc_1801B4EA8
0x1801b4cf4  mov     r8d, dword ptr [rbp+Size]; Size
0x1801b4cf8  lea     rdx, aBkgd_0; "bKGD"
0x1801b4cff  lea     rcx, [rbp+Buf1]; Buf1
0x1801b4d03  call    memcmp_0
0x1801b4d08  test    eax, eax
0x1801b4d0a  jz      short loc_1801B4D13
0x1801b4d0c  mov     ebx, 88982F63h
0x1801b4d11  jmp     short loc_1801B4CE0
0x1801b4d13  mov     eax, [rbp+arg_18]
0x1801b4d16  cmp     eax, 2
0x1801b4d19  jnz     short loc_1801B4D87
0x1801b4d1b  mov     rcx, [rdi+78h]
0x1801b4d1f  lea     r9, [rbp+Size]; unsigned int *
0x1801b4d23  add     rcx, 10h; this
0x1801b4d27  lea     rdx, [rbp+arg_0]; void *
0x1801b4d2b  mov     r8d, eax; unsigned int
0x1801b4d2e  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801b4d33  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801b4d39  mov     ebx, eax
0x1801b4d3b  test    eax, eax
0x1801b4d3d  jns     short loc_1801B4D4F
0x1801b4d3f  test    ecx, ecx
0x1801b4d41  jnz     loc_1801B4C62
0x1801b4d47  test    eax, eax
0x1801b4d49  js      loc_1801B4EA8
0x1801b4d4f  mov     eax, [rbp+arg_18]
0x1801b4d52  cmp     dword ptr [rbp+Size], eax
0x1801b4d55  jz      short loc_1801B4D60
0x1801b4d57  mov     ebx, 88982F70h
0x1801b4d5c  test    ecx, ecx
0x1801b4d5e  jmp     short loc_1801B4CE2
0x1801b4d60  movzx   eax, [rbp+arg_0]
0x1801b4d64  movzx   ecx, ax
0x1801b4d67  mov     word ptr [rdi+98h], 12h
0x1801b4d70  shr     cx, 8
0x1801b4d74  shl     ax, 8
0x1801b4d78  or      cx, ax
0x1801b4d7b  mov     [rdi+0A0h], cx
0x1801b4d82  jmp     loc_1801B4EA4
0x1801b4d87  mov     ecx, 6; cb
0x1801b4d8c  cmp     eax, ecx
0x1801b4d8e  jnz     loc_1801B4E45
0x1801b4d94  mov     word ptr [rdi+98h], 1012h
0x1801b4d9d  mov     dword ptr [rdi+0A0h], 3
0x1801b4da7  call    cs:__imp_CoTaskMemAlloc
0x1801b4dae  nop     dword ptr [rax+rax+00h]
0x1801b4db3  mov     [rdi+0A8h], rax
0x1801b4dba  test    rax, rax
0x1801b4dbd  jnz     short loc_1801B4DD0
0x1801b4dbf  mov     ebx, 8007000Eh
0x1801b4dc4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b4dcb  jmp     loc_1801B4CE2
0x1801b4dd0  xor     esi, esi
0x1801b4dd2  cmp     esi, 3
0x1801b4dd5  jnb     loc_1801B4EA4
0x1801b4ddb  mov     rcx, [rdi+78h]
0x1801b4ddf  lea     r9, [rbp+Size]; unsigned int *
0x1801b4de3  add     rcx, 10h; this
0x1801b4de7  lea     rdx, [rbp+arg_0]; void *
0x1801b4deb  mov     r8d, 2; unsigned int
0x1801b4df1  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801b4df6  mov     ebx, eax
0x1801b4df8  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801b4dfe  test    ebx, ebx
0x1801b4e00  jns     short loc_1801B4E12
0x1801b4e02  test    eax, eax
0x1801b4e04  jnz     loc_1801B4CE8
0x1801b4e0a  test    ebx, ebx
0x1801b4e0c  js      loc_1801B4EA8
0x1801b4e12  cmp     dword ptr [rbp+Size], 2
0x1801b4e16  jnz     short loc_1801B4E39
0x1801b4e18  movzx   eax, [rbp+arg_0]
0x1801b4e1c  movzx   edx, ax
0x1801b4e1f  shl     ax, 8
0x1801b4e23  shr     dx, 8
0x1801b4e27  or      dx, ax
0x1801b4e2a  mov     rax, [rdi+0A8h]
0x1801b4e31  mov     [rax+rsi*2], dx
0x1801b4e35  inc     esi
0x1801b4e37  jmp     short loc_1801B4DD2
0x1801b4e39  mov     ebx, 88982F70h
0x1801b4e3e  test    eax, eax
0x1801b4e40  jmp     loc_1801B4CE2
0x1801b4e45  cmp     eax, 1
0x1801b4e48  jnz     short loc_1801B4E94
0x1801b4e4a  mov     rcx, [rdi+78h]
0x1801b4e4e  lea     rdx, [rdi+0A0h]; void *
0x1801b4e55  add     rcx, 10h; this
0x1801b4e59  lea     r9, [rbp+Size]; unsigned int *
0x1801b4e5d  mov     r8d, eax; unsigned int
0x1801b4e60  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801b4e65  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801b4e6b  mov     ebx, eax
0x1801b4e6d  test    eax, eax
0x1801b4e6f  jns     short loc_1801B4E7D
0x1801b4e71  test    ecx, ecx
0x1801b4e73  jnz     loc_1801B4C62
0x1801b4e79  test    eax, eax
0x1801b4e7b  js      short loc_1801B4EA8
0x1801b4e7d  mov     eax, [rbp+arg_18]
0x1801b4e80  cmp     dword ptr [rbp+Size], eax
0x1801b4e83  jnz     loc_1801B4D57
0x1801b4e89  mov     word ptr [rdi+98h], 11h
0x1801b4e92  jmp     short loc_1801B4EA4
0x1801b4e94  mov     ebx, 88982F63h
0x1801b4e99  test    esi, esi
0x1801b4e9b  jz      short loc_1801B4EA4
0x1801b4e9d  mov     ecx, ebx; int
0x1801b4e9f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b4ea4  test    ebx, ebx
0x1801b4ea6  jns     short loc_1801B4EBB
0x1801b4ea8  lea     rcx, [rdi+98h]; pvar
0x1801b4eaf  call    cs:__imp_PropVariantClear
0x1801b4eb6  nop     dword ptr [rax+rax+00h]
0x1801b4ebb  mov     eax, ebx
0x1801b4ebd  mov     rbx, [rsp+30h+arg_8]
0x1801b4ec2  add     rsp, 30h
0x1801b4ec6  pop     rdi
0x1801b4ec7  pop     rsi
0x1801b4ec8  pop     rbp
0x1801b4ec9  retn
```
