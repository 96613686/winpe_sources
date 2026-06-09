# CMetadataPngTextReaderWriter::EnsureLoadedValues(void)

- ea: `0x18004df60`
- end: `0x18004e236`
- name: `?EnsureLoadedValues@CMetadataPngTextReaderWriter@@EEAAJXZ`
- size: `726`
- prototype: `__int64 __fastcall(CMetadataPngTextReaderWriter *__hidden this)`
- caller_count: `12`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004dc20`
- `0x18004dd70`
- `0x18004de00`
- `0x18004fa00`
- `0x1800b8090`
- `0x1800b85d0`
- `0x1800cf530`
- `0x1800cf5e0`
- `0x1801ad730`
- `0x1801ad8d4`
- `0x1801ad970`
- `0x1801adab0`

## callees

- `0x180046a78`
- `0x18004df60`
- `0x18004f000`
- `0x18004f894`
- `0x18004f900`
- `0x18004fab0`
- `0x180055880`
- `0x1800bd9d4`
- `0x18017e438`
- `0x18017e450`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004e1b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004e1b4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004e064`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004e064`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e0e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e156`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e0e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e156`

## pseudocode

```c
__int64 __fastcall CMetadataPngTextReaderWriter::EnsureLoadedValues(CMetadataPngTextReaderWriter *this)
{
  __int64 v2; // rcx
  char *v3; // r15
  HRESULT v4; // eax
  unsigned int v5; // ebx
  CExternalStream *v6; // rcx
  char *v7; // rax
  unsigned int v8; // eax
  ULONGLONG *v9; // rsi
  SIZE_T v10; // rcx
  char *v11; // rax
  unsigned __int64 v12; // rdx
  SIZE_T *v13; // r14
  SIZE_T v14; // rcx
  void *v15; // rax
  size_t v16; // r8
  char *v17; // rdx
  int v19; // ecx
  size_t Size; // [rsp+60h] [rbp+40h] BYREF
  size_t ullMinuend; // [rsp+68h] [rbp+48h] BYREF
  char Buf1; // [rsp+70h] [rbp+50h] BYREF

  LODWORD(Size) = 0;
  LODWORD(ullMinuend) = 0;
  if ( *((_DWORD *)this + 54) )
  {
    v2 = *((_QWORD *)this + 15);
    v3 = 0;
    if ( !v2 )
    {
      v5 = -2147024809;
      goto LABEL_25;
    }
    v4 = CStreamBase::Seek((CStreamBase *)(v2 + 16), (union _LARGE_INTEGER)*((unsigned int *)this + 34), 0, 0);
    v5 = v4;
    if ( v4 < 0 )
      goto LABEL_28;
    v4 = CExternalStream::Read(
           (CExternalStream *)(*((_QWORD *)this + 15) + 16LL),
           &ullMinuend,
           4u,
           (unsigned int *)&Size);
    v5 = v4;
    if ( v4 < 0 )
      goto LABEL_28;
    if ( (_DWORD)Size == 4 )
    {
      v6 = (CExternalStream *)(*((_QWORD *)this + 15) + 16LL);
      LODWORD(ullMinuend) = ((((_DWORD)ullMinuend << 16) | ullMinuend & 0xFF00) << 8)
                          | ((WORD1(ullMinuend) | ullMinuend & 0xFF0000) >> 8);
      v4 = CExternalStream::Read(v6, &Buf1, 4u, (unsigned int *)&Size);
      v5 = v4;
      if ( v4 < 0 )
        goto LABEL_28;
      if ( (_DWORD)Size == 4 )
      {
        if ( memcmp_0(&Buf1, "tEXt", 4u) )
        {
          v5 = -2003292317;
          goto LABEL_25;
        }
        v7 = (char *)malloc((unsigned int)ullMinuend);
        v3 = v7;
        if ( !v7 )
          goto LABEL_36;
        v4 = CExternalStream::Read(
               (CExternalStream *)(*((_QWORD *)this + 15) + 16LL),
               v7,
               ullMinuend,
               (unsigned int *)&Size);
        v5 = v4;
        if ( v4 < 0 )
          goto LABEL_28;
        if ( (_DWORD)Size == (_DWORD)ullMinuend )
        {
          v8 = 80;
          v9 = (ULONGLONG *)((char *)this + 176);
          if ( (unsigned int)ullMinuend < 0x50 )
            v8 = ullMinuend;
          v4 = StringCbLengthA(v3, v8, (unsigned __int64 *)this + 22);
          v5 = v4;
          if ( v4 < 0 )
            goto LABEL_28;
          v10 = *v9 + 1;
          if ( v10 < *v9 )
          {
            *v9 = -1;
LABEL_24:
            v5 = -2147024362;
LABEL_25:
            if ( !(_DWORD)g_doStackCaptures )
            {
LABEL_26:
              CMetadataPngTextReaderWriter::ClearFields(this);
              goto LABEL_22;
            }
            v19 = v5;
LABEL_30:
            DoStackCapture(v19);
            goto LABEL_26;
          }
          *v9 = v10;
          v11 = (char *)CoTaskMemAlloc(v10);
          *((_QWORD *)this + 20) = v11;
          if ( v11 )
          {
            v12 = *v9;
            *((_WORD *)this + 76) = 30;
            v4 = StringCchCopyA(v11, v12, v3);
            v5 = v4;
            if ( v4 >= 0 )
            {
              v13 = (SIZE_T *)((char *)this + 208);
              v4 = ULongLongSub((unsigned int)ullMinuend, *v9, (ULONGLONG *)this + 26);
              v5 = v4;
              if ( v4 >= 0 )
              {
                v14 = *v13 + 1;
                if ( v14 >= *v13 )
                {
                  *v13 = v14;
                  v15 = CoTaskMemAlloc(v14);
                  *((_QWORD *)this + 24) = v15;
                  if ( v15 )
                  {
                    v5 = 0;
                    v16 = *v13 - 1;
                    v17 = &v3[*v9];
                    *((_WORD *)this + 92) = 30;
                    memcpy_0(v15, v17, v16);
                    *(_BYTE *)(*v13 + *((_QWORD *)this + 24) - 1) = 0;
                    *((_DWORD *)this + 55) = 1;
                    *((_DWORD *)this + 54) = 0;
LABEL_22:
                    free(v3);
                    return v5;
                  }
                  goto LABEL_36;
                }
                *v13 = -1;
                goto LABEL_24;
              }
            }
LABEL_28:
            if ( !(_DWORD)g_doStackCaptures )
              goto LABEL_26;
            v19 = v4;
            goto LABEL_30;
          }
LABEL_36:
          v5 = -2147024882;
          goto LABEL_25;
        }
      }
    }
    v5 = -2003292304;
    goto LABEL_25;
  }
  return 0;
}

```

## disassembly

```asm
0x18004df60  mov     [rsp-38h+arg_18], rbx
0x18004df65  push    rbp
0x18004df66  push    rsi
0x18004df67  push    rdi
0x18004df68  push    r12
0x18004df6a  push    r13
0x18004df6c  push    r14
0x18004df6e  push    r15
0x18004df70  mov     rbp, rsp
0x18004df73  sub     rsp, 20h
0x18004df77  xor     r12d, r12d
0x18004df7a  mov     rdi, rcx
0x18004df7d  mov     dword ptr [rbp+Size], r12d
0x18004df81  mov     dword ptr [rbp+ullMinuend], r12d
0x18004df85  cmp     [rcx+0D8h], r12d
0x18004df8c  jz      loc_18004E212
0x18004df92  mov     rcx, [rcx+78h]
0x18004df96  mov     r15d, r12d
0x18004df99  test    rcx, rcx
0x18004df9c  jz      loc_18004E221
0x18004dfa2  mov     edx, [rdi+88h]; union _LARGE_INTEGER
0x18004dfa8  add     rcx, 10h; this
0x18004dfac  xor     r9d, r9d; union _ULARGE_INTEGER *
0x18004dfaf  xor     r8d, r8d; unsigned int
0x18004dfb2  call    ?Seek@CStreamBase@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CStreamBase::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x18004dfb7  mov     ebx, eax
0x18004dfb9  test    eax, eax
0x18004dfbb  js      loc_18004E200
0x18004dfc1  mov     rcx, [rdi+78h]
0x18004dfc5  lea     esi, [r12+4]
0x18004dfca  add     rcx, 10h; this
0x18004dfce  lea     r9, [rbp+Size]; unsigned int *
0x18004dfd2  mov     r8d, esi; unsigned int
0x18004dfd5  lea     rdx, [rbp+ullMinuend]; void *
0x18004dfd9  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x18004dfde  mov     ebx, eax
0x18004dfe0  test    eax, eax
0x18004dfe2  js      loc_18004E200
0x18004dfe8  cmp     dword ptr [rbp+Size], esi
0x18004dfeb  jnz     loc_18004E216
0x18004dff1  mov     ecx, dword ptr [rbp+ullMinuend]
0x18004dff4  lea     r9, [rbp+Size]; unsigned int *
0x18004dff8  mov     edx, ecx
0x18004dffa  mov     eax, ecx
0x18004dffc  shr     eax, 10h
0x18004dfff  and     edx, 0FF0000h
0x18004e005  or      edx, eax
0x18004e007  mov     r8d, esi; unsigned int
0x18004e00a  mov     eax, ecx
0x18004e00c  shr     edx, 8
0x18004e00f  shl     ecx, 10h
0x18004e012  and     eax, 0FF00h
0x18004e017  or      eax, ecx
0x18004e019  mov     rcx, [rdi+78h]
0x18004e01d  shl     eax, 8
0x18004e020  add     rcx, 10h; this
0x18004e024  or      edx, eax
0x18004e026  mov     dword ptr [rbp+ullMinuend], edx
0x18004e029  lea     rdx, [rbp+Buf1]; void *
0x18004e02d  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x18004e032  mov     ebx, eax
0x18004e034  test    eax, eax
0x18004e036  js      loc_18004E200
0x18004e03c  cmp     dword ptr [rbp+Size], esi
0x18004e03f  jnz     loc_18004E216
0x18004e045  mov     r8d, dword ptr [rbp+Size]; Size
0x18004e049  lea     rdx, aText_0; "tEXt"
0x18004e050  lea     rcx, [rbp+Buf1]; Buf1
0x18004e054  call    memcmp_0
0x18004e059  test    eax, eax
0x18004e05b  jnz     loc_18004E228
0x18004e061  mov     ecx, dword ptr [rbp+ullMinuend]; Size
0x18004e064  call    cs:__imp_malloc
0x18004e06b  nop     dword ptr [rax+rax+00h]
0x18004e070  mov     r15, rax
0x18004e073  test    rax, rax
0x18004e076  jz      loc_18004E22F
0x18004e07c  mov     rcx, [rdi+78h]
0x18004e080  lea     r9, [rbp+Size]; unsigned int *
0x18004e084  mov     r8d, dword ptr [rbp+ullMinuend]; unsigned int
0x18004e088  add     rcx, 10h; this
0x18004e08c  mov     rdx, rax; void *
0x18004e08f  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x18004e094  mov     ebx, eax
0x18004e096  test    eax, eax
0x18004e098  js      loc_18004E200
0x18004e09e  mov     ecx, dword ptr [rbp+ullMinuend]
0x18004e0a1  cmp     dword ptr [rbp+Size], ecx
0x18004e0a4  jnz     loc_18004E216
0x18004e0aa  lea     eax, [rsi+4Ch]
0x18004e0ad  cmp     ecx, eax
0x18004e0af  lea     rsi, [rdi+0B0h]
0x18004e0b6  mov     r8, rsi; unsigned __int64 *
0x18004e0b9  cmovb   eax, ecx
0x18004e0bc  mov     rcx, r15; char *
0x18004e0bf  mov     edx, eax; unsigned __int64
0x18004e0c1  call    ?StringCbLengthA@@YAJPEBD_KPEA_K@Z; StringCbLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18004e0c6  mov     ebx, eax
0x18004e0c8  test    eax, eax
0x18004e0ca  js      loc_18004E200
0x18004e0d0  mov     rax, [rsi]
0x18004e0d3  lea     rcx, [rax+1]; cb
0x18004e0d7  cmp     rcx, rax
0x18004e0da  jb      loc_18004E1F7
0x18004e0e0  mov     [rsi], rcx
0x18004e0e3  call    cs:__imp_CoTaskMemAlloc
0x18004e0ea  nop     dword ptr [rax+rax+00h]
0x18004e0ef  mov     [rdi+0A0h], rax
0x18004e0f6  test    rax, rax
0x18004e0f9  jz      loc_18004E22F
0x18004e0ff  mov     rdx, [rsi]; unsigned __int64
0x18004e102  lea     r13d, [r12+1Eh]
0x18004e107  mov     r8, r15; char *
0x18004e10a  mov     [rdi+98h], r13w
0x18004e112  mov     rcx, rax; char *
0x18004e115  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18004e11a  mov     ebx, eax
0x18004e11c  test    eax, eax
0x18004e11e  js      loc_18004E200
0x18004e124  mov     ecx, dword ptr [rbp+ullMinuend]; ullMinuend
0x18004e127  lea     r14, [rdi+0D0h]
0x18004e12e  mov     rdx, [rsi]; ullSubtrahend
0x18004e131  mov     r8, r14; pullResult
0x18004e134  call    ULongLongSub
0x18004e139  mov     ebx, eax
0x18004e13b  test    eax, eax
0x18004e13d  js      loc_18004E200
0x18004e143  mov     rax, [r14]
0x18004e146  lea     rcx, [rax+1]; cb
0x18004e14a  cmp     rcx, rax
0x18004e14d  jb      loc_18004E1D8
0x18004e153  mov     [r14], rcx
0x18004e156  call    cs:__imp_CoTaskMemAlloc
0x18004e15d  nop     dword ptr [rax+rax+00h]
0x18004e162  mov     [rdi+0C0h], rax
0x18004e169  mov     rcx, rax; void *
0x18004e16c  test    rax, rax
0x18004e16f  jz      loc_18004E22F
0x18004e175  mov     r8, [r14]
0x18004e178  mov     ebx, r12d
0x18004e17b  mov     rdx, [rsi]
0x18004e17e  dec     r8; Size
0x18004e181  add     rdx, r15; Src
0x18004e184  mov     [rdi+0B8h], r13w
0x18004e18c  call    memcpy_0
0x18004e191  mov     rcx, [r14]
0x18004e194  mov     rax, [rdi+0C0h]
0x18004e19b  mov     [rcx+rax-1], r12b
0x18004e1a0  mov     dword ptr [rdi+0DCh], 1
0x18004e1aa  mov     [rdi+0D8h], r12d
0x18004e1b1  mov     rcx, r15; Block
0x18004e1b4  call    cs:__imp_free
0x18004e1bb  nop     dword ptr [rax+rax+00h]
0x18004e1c0  mov     eax, ebx
0x18004e1c2  mov     rbx, [rsp+20h+arg_18]
0x18004e1c7  add     rsp, 20h
0x18004e1cb  pop     r15
0x18004e1cd  pop     r14
0x18004e1cf  pop     r13
0x18004e1d1  pop     r12
0x18004e1d3  pop     rdi
0x18004e1d4  pop     rsi
0x18004e1d5  pop     rbp
0x18004e1d6  retn
0x18004e1d8  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18004e1df  mov     ebx, 80070216h
0x18004e1e4  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18004e1eb  jnz     short loc_18004E21D
0x18004e1ed  mov     rcx, rdi; this
0x18004e1f0  call    ?ClearFields@CMetadataPngTextReaderWriter@@EEAAJXZ; CMetadataPngTextReaderWriter::ClearFields(void)
0x18004e1f5  jmp     short loc_18004E1B1
0x18004e1f7  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18004e1fe  jmp     short loc_18004E1DF
0x18004e200  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18004e207  jz      short loc_18004E1ED
0x18004e209  mov     ecx, eax; int
0x18004e20b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004e210  jmp     short loc_18004E1ED
0x18004e212  xor     eax, eax
0x18004e214  jmp     short loc_18004E1C2
0x18004e216  mov     ebx, 88982F70h
0x18004e21b  jmp     short loc_18004E1E4
0x18004e21d  mov     ecx, ebx
0x18004e21f  jmp     short loc_18004E20B
0x18004e221  mov     ebx, 80070057h
0x18004e226  jmp     short loc_18004E1E4
0x18004e228  mov     ebx, 88982F63h
0x18004e22d  jmp     short loc_18004E1E4
0x18004e22f  mov     ebx, 8007000Eh
0x18004e234  jmp     short loc_18004E1E4
```
