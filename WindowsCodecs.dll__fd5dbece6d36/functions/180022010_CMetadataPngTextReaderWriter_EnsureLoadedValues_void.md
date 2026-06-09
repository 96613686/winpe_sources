# CMetadataPngTextReaderWriter::EnsureLoadedValues(void)

- ea: `0x180022010`
- end: `0x1800222c9`
- name: `?EnsureLoadedValues@CMetadataPngTextReaderWriter@@EEAAJXZ`
- size: `697`
- prototype: `__int64 __fastcall(CMetadataPngTextReaderWriter *__hidden this)`
- caller_count: `12`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020a50`
- `0x180020c80`
- `0x180021eb0`
- `0x1800add00`
- `0x1800b5fc0`
- `0x1800b6460`
- `0x1800ccf90`
- `0x1800cd040`
- `0x1801aa1f0`
- `0x1801aa390`
- `0x1801aa430`
- `0x1801aa570`

## callees

- `0x180020d30`
- `0x180020dac`
- `0x180020e14`
- `0x180020e7c`
- `0x180022010`
- `0x180023050`
- `0x1800257d0`
- `0x1800bb784`
- `0x18017b528`
- `0x18017b540`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002224e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002224e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180022114`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180022114`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002218d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800221f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002218d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800221f6`

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
        if ( memcmp_0(&Buf1, &dword_1801EFBB4, 4u) )
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
0x180022010  mov     [rsp-38h+arg_18], rbx
0x180022015  push    rbp
0x180022016  push    rsi
0x180022017  push    rdi
0x180022018  push    r12
0x18002201a  push    r13
0x18002201c  push    r14
0x18002201e  push    r15
0x180022020  mov     rbp, rsp
0x180022023  sub     rsp, 20h
0x180022027  xor     r12d, r12d
0x18002202a  mov     rdi, rcx
0x18002202d  mov     dword ptr [rbp+Size], r12d
0x180022031  mov     dword ptr [rbp+ullMinuend], r12d
0x180022035  cmp     [rcx+0D8h], r12d
0x18002203c  jz      loc_1800222A5
0x180022042  mov     rcx, [rcx+78h]
0x180022046  mov     r15d, r12d
0x180022049  test    rcx, rcx
0x18002204c  jz      loc_1800222B4
0x180022052  mov     edx, [rdi+88h]; union _LARGE_INTEGER
0x180022058  add     rcx, 10h; this
0x18002205c  xor     r9d, r9d; union _ULARGE_INTEGER *
0x18002205f  xor     r8d, r8d; unsigned int
0x180022062  call    ?Seek@CStreamBase@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CStreamBase::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x180022067  mov     ebx, eax
0x180022069  test    eax, eax
0x18002206b  js      loc_180022293
0x180022071  mov     rcx, [rdi+78h]
0x180022075  lea     esi, [r12+4]
0x18002207a  add     rcx, 10h; this
0x18002207e  lea     r9, [rbp+Size]; unsigned int *
0x180022082  mov     r8d, esi; unsigned int
0x180022085  lea     rdx, [rbp+ullMinuend]; void *
0x180022089  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x18002208e  mov     ebx, eax
0x180022090  test    eax, eax
0x180022092  js      loc_180022293
0x180022098  cmp     dword ptr [rbp+Size], esi
0x18002209b  jnz     loc_1800222A9
0x1800220a1  mov     ecx, dword ptr [rbp+ullMinuend]
0x1800220a4  lea     r9, [rbp+Size]; unsigned int *
0x1800220a8  mov     edx, ecx
0x1800220aa  mov     eax, ecx
0x1800220ac  shr     eax, 10h
0x1800220af  and     edx, 0FF0000h
0x1800220b5  or      edx, eax
0x1800220b7  mov     r8d, esi; unsigned int
0x1800220ba  mov     eax, ecx
0x1800220bc  shr     edx, 8
0x1800220bf  shl     ecx, 10h
0x1800220c2  and     eax, 0FF00h
0x1800220c7  or      eax, ecx
0x1800220c9  mov     rcx, [rdi+78h]
0x1800220cd  shl     eax, 8
0x1800220d0  add     rcx, 10h; this
0x1800220d4  or      edx, eax
0x1800220d6  mov     dword ptr [rbp+ullMinuend], edx
0x1800220d9  lea     rdx, [rbp+Buf1]; void *
0x1800220dd  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1800220e2  mov     ebx, eax
0x1800220e4  test    eax, eax
0x1800220e6  js      loc_180022293
0x1800220ec  cmp     dword ptr [rbp+Size], esi
0x1800220ef  jnz     loc_1800222A9
0x1800220f5  mov     r8d, dword ptr [rbp+Size]; Size
0x1800220f9  lea     rdx, dword_1801EFBB4; Buf2
0x180022100  lea     rcx, [rbp+Buf1]; Buf1
0x180022104  call    memcmp_0
0x180022109  test    eax, eax
0x18002210b  jnz     loc_1800222BB
0x180022111  mov     ecx, dword ptr [rbp+ullMinuend]; Size
0x180022114  call    cs:__imp_malloc
0x18002211a  mov     r15, rax
0x18002211d  test    rax, rax
0x180022120  jz      loc_1800222C2
0x180022126  mov     rcx, [rdi+78h]
0x18002212a  lea     r9, [rbp+Size]; unsigned int *
0x18002212e  mov     r8d, dword ptr [rbp+ullMinuend]; unsigned int
0x180022132  add     rcx, 10h; this
0x180022136  mov     rdx, rax; void *
0x180022139  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x18002213e  mov     ebx, eax
0x180022140  test    eax, eax
0x180022142  js      loc_180022293
0x180022148  mov     ecx, dword ptr [rbp+ullMinuend]
0x18002214b  cmp     dword ptr [rbp+Size], ecx
0x18002214e  jnz     loc_1800222A9
0x180022154  lea     eax, [rsi+4Ch]
0x180022157  cmp     ecx, eax
0x180022159  lea     rsi, [rdi+0B0h]
0x180022160  mov     r8, rsi; unsigned __int64 *
0x180022163  cmovb   eax, ecx
0x180022166  mov     rcx, r15; char *
0x180022169  mov     edx, eax; unsigned __int64
0x18002216b  call    ?StringCbLengthA@@YAJPEBD_KPEA_K@Z; StringCbLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180022170  mov     ebx, eax
0x180022172  test    eax, eax
0x180022174  js      loc_180022293
0x18002217a  mov     rax, [rsi]
0x18002217d  lea     rcx, [rax+1]; cb
0x180022181  cmp     rcx, rax
0x180022184  jb      loc_18002228A
0x18002218a  mov     [rsi], rcx
0x18002218d  call    cs:__imp_CoTaskMemAlloc
0x180022193  mov     [rdi+0A0h], rax
0x18002219a  test    rax, rax
0x18002219d  jz      loc_1800222C2
0x1800221a3  mov     rdx, [rsi]; unsigned __int64
0x1800221a6  lea     r13d, [r12+1Eh]
0x1800221ab  mov     r8, r15; char *
0x1800221ae  mov     [rdi+98h], r13w
0x1800221b6  mov     rcx, rax; char *
0x1800221b9  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800221be  mov     ebx, eax
0x1800221c0  test    eax, eax
0x1800221c2  js      loc_180022293
0x1800221c8  mov     ecx, dword ptr [rbp+ullMinuend]; ullMinuend
0x1800221cb  lea     r14, [rdi+0D0h]
0x1800221d2  mov     rdx, [rsi]; ullSubtrahend
0x1800221d5  mov     r8, r14; pullResult
0x1800221d8  call    ULongLongSub
0x1800221dd  mov     ebx, eax
0x1800221df  test    eax, eax
0x1800221e1  js      loc_180022293
0x1800221e7  mov     rax, [r14]
0x1800221ea  lea     rcx, [rax+1]; cb
0x1800221ee  cmp     rcx, rax
0x1800221f1  jb      short loc_18002226B
0x1800221f3  mov     [r14], rcx
0x1800221f6  call    cs:__imp_CoTaskMemAlloc
0x1800221fc  mov     [rdi+0C0h], rax
0x180022203  mov     rcx, rax; void *
0x180022206  test    rax, rax
0x180022209  jz      loc_1800222C2
0x18002220f  mov     r8, [r14]
0x180022212  mov     ebx, r12d
0x180022215  mov     rdx, [rsi]
0x180022218  dec     r8; Size
0x18002221b  add     rdx, r15; Src
0x18002221e  mov     [rdi+0B8h], r13w
0x180022226  call    memcpy_0
0x18002222b  mov     rcx, [r14]
0x18002222e  mov     rax, [rdi+0C0h]
0x180022235  mov     [rcx+rax-1], r12b
0x18002223a  mov     dword ptr [rdi+0DCh], 1
0x180022244  mov     [rdi+0D8h], r12d
0x18002224b  mov     rcx, r15; Block
0x18002224e  call    cs:__imp_free
0x180022254  mov     eax, ebx
0x180022256  mov     rbx, [rsp+20h+arg_18]
0x18002225b  add     rsp, 20h
0x18002225f  pop     r15
0x180022261  pop     r14
0x180022263  pop     r13
0x180022265  pop     r12
0x180022267  pop     rdi
0x180022268  pop     rsi
0x180022269  pop     rbp
0x18002226a  retn
0x18002226b  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180022272  mov     ebx, 80070216h
0x180022277  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18002227e  jnz     short loc_1800222B0
0x180022280  mov     rcx, rdi; this
0x180022283  call    ?ClearFields@CMetadataPngTextReaderWriter@@EEAAJXZ; CMetadataPngTextReaderWriter::ClearFields(void)
0x180022288  jmp     short loc_18002224B
0x18002228a  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180022291  jmp     short loc_180022272
0x180022293  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18002229a  jz      short loc_180022280
0x18002229c  mov     ecx, eax; int
0x18002229e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800222a3  jmp     short loc_180022280
0x1800222a5  xor     eax, eax
0x1800222a7  jmp     short loc_180022256
0x1800222a9  mov     ebx, 88982F70h
0x1800222ae  jmp     short loc_180022277
0x1800222b0  mov     ecx, ebx
0x1800222b2  jmp     short loc_18002229E
0x1800222b4  mov     ebx, 80070057h
0x1800222b9  jmp     short loc_180022277
0x1800222bb  mov     ebx, 88982F63h
0x1800222c0  jmp     short loc_180022277
0x1800222c2  mov     ebx, 8007000Eh
0x1800222c7  jmp     short loc_180022277
```
