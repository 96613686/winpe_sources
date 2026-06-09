# VerifyChunk(FileView const &)

- ea: `0x180034e38`
- end: `0x180034f83`
- name: `?VerifyChunk@@YA_NAEBVFileView@@@Z`
- size: `331`
- prototype: `bool __fastcall(const struct FileView *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031564`
- `0x180032bb8`
- `0x180033258`

## callees

- `0x180029234`
- `0x180034ba4`
- `0x180034d08`
- `0x180034e38`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x180034f0d`
- `ntdll!RtlComputeCrc32` at `0x180034f0d`

## pseudocode

```c
char __fastcall VerifyChunk(const struct FileView *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  LastErrInfo *v5; // rcx
  __int64 v6; // rdx
  ULONG v7; // eax
  __int64 v8; // r8

  if ( IsChunkHeaderValid(*(const struct ChunkHeader **)a1) )
  {
    if ( (unsigned int)(*(_DWORD *)(v3 + 48) - 512) > 0xFE00 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        return 0;
      }
      v6 = 18;
    }
    else
    {
      if ( (*(_BYTE *)(v3 + 120) & 4) != 0 )
        return 1;
      v7 = CalcGeneralHeaderCRC((PUCHAR)v3, v2, v4, 512);
      v8 = *(_QWORD *)a1;
      if ( v7 != *(_DWORD *)(*(_QWORD *)a1 + 124LL) )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          return 0;
        }
        v6 = 19;
        goto LABEL_24;
      }
      if ( *(_QWORD *)(v8 + 16) == -1
        || *(_DWORD *)(*(_QWORD *)a1 + 52LL) == RtlComputeCrc32(
                                                  0,
                                                  (PUCHAR)(*((_QWORD *)a1 + 2) + 512LL),
                                                  *(_DWORD *)(v8 + 48) - 512) )
      {
        return 1;
      }
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        return 0;
      }
      v6 = 20;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      return 0;
    }
    v6 = 17;
  }
LABEL_24:
  WPP_SF_(*((_QWORD *)v5 + 2), v6, &WPP_f9efb118310932df1b6c7c37b5e7929e_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180034e38  push    rbx
0x180034e3a  sub     rsp, 20h
0x180034e3e  mov     rbx, rcx
0x180034e41  mov     rcx, [rcx]; struct ChunkHeader *
0x180034e44  call    ?IsChunkHeaderValid@@YA_NPEBUChunkHeader@@@Z; IsChunkHeaderValid(ChunkHeader const *)
0x180034e49  test    al, al
0x180034e4b  jnz     short loc_180034E85
0x180034e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e54  lea     rax, WPP_GLOBAL_Control
0x180034e5b  cmp     rcx, rax
0x180034e5e  jz      loc_180034F7B
0x180034e64  test    dword ptr [rcx+1Ch], 8000h
0x180034e6b  jz      loc_180034F7B
0x180034e71  cmp     byte ptr [rcx+19h], 4
0x180034e75  jb      loc_180034F7B
0x180034e7b  mov     edx, 11h
0x180034e80  jmp     loc_180034F6B
0x180034e85  mov     eax, [rcx+30h]
0x180034e88  mov     r9d, 200h; unsigned int
0x180034e8e  sub     eax, r9d
0x180034e91  cmp     eax, 0FE00h
0x180034e96  ja      loc_180034F44
0x180034e9c  test    byte ptr [rcx+78h], 4
0x180034ea0  jnz     short loc_180034EEF
0x180034ea2  call    ?CalcGeneralHeaderCRC@@YAKPEBEKKK@Z; CalcGeneralHeaderCRC(uchar const *,ulong,ulong,ulong)
0x180034ea7  mov     r8, [rbx]
0x180034eaa  cmp     eax, [r8+7Ch]
0x180034eae  jz      short loc_180034EE8
0x180034eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180034eb7  lea     rax, WPP_GLOBAL_Control
0x180034ebe  cmp     rcx, rax
0x180034ec1  jz      loc_180034F7B
0x180034ec7  test    dword ptr [rcx+1Ch], 8000h
0x180034ece  jz      loc_180034F7B
0x180034ed4  cmp     byte ptr [rcx+19h], 4
0x180034ed8  jb      loc_180034F7B
0x180034ede  mov     edx, 13h
0x180034ee3  jmp     loc_180034F6B
0x180034ee8  cmp     qword ptr [r8+10h], 0FFFFFFFFFFFFFFFFh
0x180034eed  jnz     short loc_180034EF6
0x180034eef  mov     al, 1
0x180034ef1  jmp     loc_180034F7D
0x180034ef6  mov     rax, [rbx+10h]
0x180034efa  xor     ecx, ecx; InitialCrc
0x180034efc  mov     r8d, [r8+30h]
0x180034f00  lea     rdx, [rax+200h]; Buffer
0x180034f07  sub     r8d, edx
0x180034f0a  add     r8d, eax; Length
0x180034f0d  call    cs:__imp_RtlComputeCrc32
0x180034f13  mov     rcx, [rbx]
0x180034f16  cmp     [rcx+34h], eax
0x180034f19  jz      short loc_180034EEF
0x180034f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f22  lea     rax, WPP_GLOBAL_Control
0x180034f29  cmp     rcx, rax
0x180034f2c  jz      short loc_180034F7B
0x180034f2e  test    dword ptr [rcx+1Ch], 8000h
0x180034f35  jz      short loc_180034F7B
0x180034f37  cmp     byte ptr [rcx+19h], 4
0x180034f3b  jb      short loc_180034F7B
0x180034f3d  mov     edx, 14h
0x180034f42  jmp     short loc_180034F6B
0x180034f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f4b  lea     rax, WPP_GLOBAL_Control
0x180034f52  cmp     rcx, rax
0x180034f55  jz      short loc_180034F7B
0x180034f57  test    dword ptr [rcx+1Ch], 8000h
0x180034f5e  jz      short loc_180034F7B
0x180034f60  cmp     byte ptr [rcx+19h], 4
0x180034f64  jb      short loc_180034F7B
0x180034f66  mov     edx, 12h
0x180034f6b  mov     rcx, [rcx+10h]
0x180034f6f  lea     r8, WPP_f9efb118310932df1b6c7c37b5e7929e_Traceguids
0x180034f76  call    WPP_SF_
0x180034f7b  xor     al, al
0x180034f7d  add     rsp, 20h
0x180034f81  pop     rbx
0x180034f82  retn
```
