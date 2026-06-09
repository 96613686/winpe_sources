# CMetadataXMPReaderWriter::SaveFastEncode(int)

- ea: `0x180017af0`
- end: `0x180017d39`
- name: `?SaveFastEncode@CMetadataXMPReaderWriter@@MEAAJH@Z`
- size: `585`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180012280`
- `0x180012afc`
- `0x180015684`
- `0x1800171c4`
- `0x180017af0`
- `0x1800215e8`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::SaveFastEncode(CMetadataXMPReaderWriter *this, unsigned int a2)
{
  union _LARGE_INTEGER v4; // rdx
  CStreamBase *v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // ecx
  _DWORD *v9; // rax
  _DWORD *v10; // rdi
  HRESULT v11; // eax
  __int64 v12; // rcx
  int v13; // ecx
  __int128 v15; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h]
  ULONG ulSubtrahend; // [rsp+80h] [rbp+30h] BYREF
  ULONG pulResult; // [rsp+90h] [rbp+40h] BYREF
  ULONG v19; // [rsp+98h] [rbp+48h] BYREF

  ulSubtrahend = 0;
  v4.QuadPart = *((unsigned int *)this + 34);
  v5 = (CStreamBase *)(*((_QWORD *)this + 15) + 16LL);
  pulResult = 0;
  v19 = 0;
  v15 = 0;
  v6 = CStreamBase::Seek(v5, v4, 0, 0);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, _QWORD))(*(_QWORD *)this + 352LL))(this, a2);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, _QWORD))(*(_QWORD *)this + 400LL))(
             this,
             *((unsigned int *)this + 36));
      v7 = v6;
      if ( v6 >= 0 )
      {
        v9 = operator new(0x38u);
        v10 = v9;
        if ( v9 )
        {
          v9[2] = 0;
          *(_QWORD *)v9 = &CMILCOMBase::`vftable';
          _InterlockedIncrement(&g_cActiveObjects);
          *((_QWORD *)v9 + 4) = 0;
          *(_QWORD *)v9 = &CEncodingStream::`vftable'{for `CMILCOMBase'};
          *((_QWORD *)v9 + 2) = &CEncodingStream::`vftable'{for `IStream'};
          *((_QWORD *)v9 + 3) = 0;
          *((_QWORD *)v9 + 5) = 0;
          *((_QWORD *)v9 + 6) = 0;
          CEncodingStream::AddRef((CEncodingStream *)v9);
          v11 = (*(__int64 (__fastcall **)(_DWORD *, __int64, _QWORD, __int64, int))(*(_QWORD *)v10 + 40LL))(
                  v10,
                  (*((_QWORD *)this + 15) + 16LL) & -(__int64)(*((_QWORD *)this + 15) != 0),
                  *((unsigned int *)this + 36),
                  1,
                  1);
          v7 = v11;
          if ( v11 >= 0 )
          {
            v12 = *((_QWORD *)this + 23);
            v16 = 0;
            LOWORD(v15) = 13;
            *((_QWORD *)&v15 + 1) = v10 + 4;
            v11 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v12 + 528LL))(v12, &v15);
            v7 = v11;
            if ( v11 >= 0 )
            {
              if ( v11 )
              {
                v7 = -2147467259;
                goto LABEL_11;
              }
              v11 = (*(__int64 (__fastcall **)(_DWORD *, ULONG *, __int64))(*(_QWORD *)v10 + 56LL))(
                      v10,
                      &ulSubtrahend,
                      1);
              v7 = v11;
              if ( v11 >= 0 )
              {
                v11 = ULongLongToULong(*((_QWORD *)this + 22), &pulResult);
                v7 = v11;
                if ( v11 >= 0 )
                {
                  if ( ulSubtrahend > pulResult )
                  {
                    v7 = -2003292276;
LABEL_11:
                    if ( g_doStackCaptures )
                    {
                      v13 = v7;
LABEL_21:
                      DoStackCapture(v13);
                      goto LABEL_22;
                    }
                    goto LABEL_22;
                  }
                  v11 = ULongSub(pulResult, ulSubtrahend, &v19);
                  v7 = v11;
                  if ( v11 >= 0 )
                  {
                    v11 = (*(__int64 (__fastcall **)(_DWORD *, _QWORD))(*(_QWORD *)v10 + 48LL))(v10, v19);
                    v7 = v11;
                    if ( v11 >= 0 )
                      goto LABEL_22;
                  }
                }
              }
            }
          }
          if ( g_doStackCaptures )
          {
            v13 = v11;
            goto LABEL_21;
          }
LABEL_22:
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v10 + 16LL))(v10);
          return v7;
        }
        v7 = -2147024882;
        if ( !g_doStackCaptures )
          return v7;
        v8 = -2147024882;
LABEL_25:
        DoStackCapture(v8);
        return v7;
      }
    }
  }
  if ( g_doStackCaptures )
  {
    v8 = v6;
    goto LABEL_25;
  }
  return v7;
}

```

## disassembly

```asm
0x180017af0  mov     [rsp-28h+arg_8], rbx
0x180017af5  push    rbp
0x180017af6  push    rsi
0x180017af7  push    rdi
0x180017af8  push    r12
0x180017afa  push    r14
0x180017afc  mov     rbp, rsp
0x180017aff  sub     rsp, 50h
0x180017b03  mov     rsi, rcx
0x180017b06  xor     r14d, r14d
0x180017b09  mov     edi, edx
0x180017b0b  mov     [rbp+ulSubtrahend], r14d
0x180017b0f  mov     edx, [rcx+88h]; union _LARGE_INTEGER
0x180017b15  xorps   xmm0, xmm0
0x180017b18  mov     rcx, [rcx+78h]
0x180017b1c  xor     r9d, r9d; union _ULARGE_INTEGER *
0x180017b1f  add     rcx, 10h; this
0x180017b23  mov     [rbp+pulResult], r14d
0x180017b27  xor     r8d, r8d; unsigned int
0x180017b2a  mov     [rbp+arg_18], r14d
0x180017b2e  xor     r12d, r12d
0x180017b31  movups  [rbp+var_20], xmm0
0x180017b35  call    ?Seek@CStreamBase@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CStreamBase::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x180017b3a  mov     ebx, eax
0x180017b3c  test    eax, eax
0x180017b3e  jns     short loc_180017B54
0x180017b40  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180017b47  jz      loc_180017D23
0x180017b4d  mov     ecx, eax
0x180017b4f  jmp     loc_180017D1E
0x180017b54  mov     rax, [rsi]
0x180017b57  mov     edx, edi
0x180017b59  mov     rcx, rsi
0x180017b5c  mov     rax, [rax+160h]
0x180017b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b68  mov     ebx, eax
0x180017b6a  test    eax, eax
0x180017b6c  js      short loc_180017B40
0x180017b6e  mov     rax, [rsi]
0x180017b71  mov     rcx, rsi
0x180017b74  mov     edx, [rsi+90h]
0x180017b7a  mov     rax, [rax+190h]
0x180017b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b86  mov     ebx, eax
0x180017b88  test    eax, eax
0x180017b8a  js      short loc_180017B40
0x180017b8c  mov     ecx, 38h ; '8'; Size
0x180017b91  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017b96  mov     rdi, rax
0x180017b99  test    rax, rax
0x180017b9c  jz      loc_180017D0E
0x180017ba2  lea     rax, ??_7CMILCOMBase@@6B@; const CMILCOMBase::`vftable'
0x180017ba9  mov     [rdi+8], r14d
0x180017bad  mov     [rdi], rax
0x180017bb0  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180017bb7  lea     rdx, ??_7CEncodingStream@@6BCMILCOMBase@@@; const CEncodingStream::`vftable'{for `CMILCOMBase'}
0x180017bbe  mov     [rdi+20h], r14
0x180017bc2  lea     rax, ??_7CEncodingStream@@6BIStream@@@; const CEncodingStream::`vftable'{for `IStream'}
0x180017bc9  mov     [rdi], rdx
0x180017bcc  mov     [rdi+10h], rax
0x180017bd0  mov     rcx, rdi
0x180017bd3  mov     rax, [rdx+8]
0x180017bd7  mov     [rdi+18h], r14
0x180017bdb  mov     [rdi+28h], r14
0x180017bdf  mov     [rdi+30h], r14
0x180017be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017be8  mov     rcx, [rsi+78h]
0x180017bec  mov     r9d, 1
0x180017bf2  mov     r8, [rdi]
0x180017bf5  mov     [rsp+50h+var_30], 1
0x180017bfd  lea     rax, [rcx+10h]
0x180017c01  neg     rcx
0x180017c04  mov     rcx, rdi
0x180017c07  sbb     rdx, rdx
0x180017c0a  and     rdx, rax
0x180017c0d  mov     rax, [r8+28h]
0x180017c11  mov     r8d, [rsi+90h]
0x180017c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c1d  mov     ebx, eax
0x180017c1f  test    eax, eax
0x180017c21  js      loc_180017CED
0x180017c27  mov     rcx, [rsi+0B8h]
0x180017c2e  lea     rdx, [rbp+var_20]
0x180017c32  mov     eax, 0Dh
0x180017c37  mov     [rbp+var_10], r12
0x180017c3b  mov     word ptr [rbp+var_20], ax
0x180017c3f  lea     rax, [rdi+10h]
0x180017c43  mov     qword ptr [rbp+var_20+8], rax
0x180017c47  mov     rax, [rcx]
0x180017c4a  movups  xmm0, [rbp+var_20]
0x180017c4e  mov     rax, [rax+210h]
0x180017c55  movaps  [rbp+var_20], xmm0
0x180017c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c5e  mov     ebx, eax
0x180017c60  test    eax, eax
0x180017c62  js      loc_180017CED
0x180017c68  jz      short loc_180017C80
0x180017c6a  mov     ebx, 80004005h
0x180017c6f  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180017c76  jz      loc_180017CFD
0x180017c7c  mov     ecx, ebx
0x180017c7e  jmp     short loc_180017CF8
0x180017c80  mov     rax, [rdi]
0x180017c83  lea     rdx, [rbp+ulSubtrahend]
0x180017c87  mov     r8d, 1
0x180017c8d  mov     rcx, rdi
0x180017c90  mov     rax, [rax+38h]
0x180017c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c99  mov     ebx, eax
0x180017c9b  test    eax, eax
0x180017c9d  js      short loc_180017CED
0x180017c9f  mov     rcx, [rsi+0B0h]; ullOperand
0x180017ca6  lea     rdx, [rbp+pulResult]; pulResult
0x180017caa  call    ULongLongToULong
0x180017caf  mov     ebx, eax
0x180017cb1  test    eax, eax
0x180017cb3  js      short loc_180017CED
0x180017cb5  mov     edx, [rbp+ulSubtrahend]; ulSubtrahend
0x180017cb8  mov     ecx, [rbp+pulResult]; ulMinuend
0x180017cbb  cmp     edx, ecx
0x180017cbd  jbe     short loc_180017CC6
0x180017cbf  mov     ebx, 88982F8Ch
0x180017cc4  jmp     short loc_180017C6F
0x180017cc6  lea     r8, [rbp+arg_18]; pulResult
0x180017cca  call    ULongSub
0x180017ccf  mov     ebx, eax
0x180017cd1  test    eax, eax
0x180017cd3  js      short loc_180017CED
0x180017cd5  mov     rax, [rdi]
0x180017cd8  mov     rcx, rdi
0x180017cdb  mov     edx, [rbp+arg_18]
0x180017cde  mov     rax, [rax+30h]
0x180017ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ce7  mov     ebx, eax
0x180017ce9  test    eax, eax
0x180017ceb  jns     short loc_180017CFD
0x180017ced  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180017cf4  jz      short loc_180017CFD
0x180017cf6  mov     ecx, eax; int
0x180017cf8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180017cfd  mov     rax, [rdi]
0x180017d00  mov     rcx, rdi
0x180017d03  mov     rax, [rax+10h]
0x180017d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d0c  jmp     short loc_180017D23
0x180017d0e  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180017d15  mov     ebx, 8007000Eh
0x180017d1a  jz      short loc_180017D23
0x180017d1c  mov     ecx, ebx; int
0x180017d1e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180017d23  mov     eax, ebx
0x180017d25  mov     rbx, [rsp+50h+arg_8]
0x180017d2d  add     rsp, 50h
0x180017d31  pop     r14
0x180017d33  pop     r12
0x180017d35  pop     rdi
0x180017d36  pop     rsi
0x180017d37  pop     rbp
0x180017d38  retn
```
