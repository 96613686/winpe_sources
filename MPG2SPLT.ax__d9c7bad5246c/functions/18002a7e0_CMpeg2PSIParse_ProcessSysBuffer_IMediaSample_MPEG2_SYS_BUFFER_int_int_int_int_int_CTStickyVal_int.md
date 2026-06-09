# CMpeg2PSIParse::ProcessSysBuffer(IMediaSample *,MPEG2_SYS_BUFFER *,int,int,int,int,int,CTStickyVal<int> *)

- ea: `0x18002a7e0`
- end: `0x18002a997`
- name: `?ProcessSysBuffer@CMpeg2PSIParse@@UEAAJPEAUIMediaSample@@PEAUMPEG2_SYS_BUFFER@@HHHHHPEAV?$CTStickyVal@H@@@Z`
- size: `439`
- prototype: `__int64 __usercall@<rax>(CCopyFrameParser *this@<rcx>, int, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002d710`

## callees

- `0x180028b18`
- `0x180029b4c`
- `0x18002a7e0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMpeg2PSIParse::ProcessSysBuffer(
        CCopyFrameParser *this,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        _DWORD *a9)
{
  __int64 v9; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  bool v15; // zf
  unsigned __int8 *v16; // rcx
  __int64 v17; // rsi
  int v18; // edx
  struct IMediaSampleVtbl *v19; // r8
  __int64 v21; // [rsp+20h] [rbp-10h] BYREF
  int v22; // [rsp+50h] [rbp+20h] BYREF
  struct IMediaSample v23; // [rsp+60h] [rbp+30h] BYREF

  v9 = *((_QWORD *)this + 48);
  v21 = -1;
  v13 = *(_QWORD *)(v9 + 16);
  if ( v13 && *((_DWORD *)this + 95) )
    ++*(_QWORD *)(v13 + 264);
  if ( !*(_DWORD *)(a3 + 24) )
    return 0;
  if ( (*(_DWORD *)(a3 + 28) & 0x8000) != 0
    && *(_DWORD *)(a3 + 8) == 188
    && (!*(_QWORD *)(a3 + 16) || *(_QWORD *)(a3 + 16) >= (unsigned __int64)(*(_QWORD *)a3 + 4LL))
    && *(int *)(a3 + 24) <= 184 )
  {
    *((_DWORD *)this + 24) = *(_DWORD *)(a3 + 48);
    *((_BYTE *)this + 100) = *(_BYTE *)(a3 + 52) & 3;
  }
  v14 = *((_QWORD *)this + 51);
  if ( v14 )
    (*(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 48LL))(
      v14,
      *((unsigned int *)this + 24),
      &v21);
  v15 = a5 == 0;
  *((_QWORD *)this + 13) = v21;
  if ( !v15 || a4 )
    CMpeg2PSIParse::AbortPSICollection_(this);
  if ( !a7 )
  {
    if ( (unsigned int)(*((_DWORD *)this + 101) - 1) <= 1 )
    {
      v18 = *(_DWORD *)(a3 + 24);
      v19 = *(struct IMediaSampleVtbl **)(a3 + 16);
      goto LABEL_32;
    }
    if ( *((_DWORD *)this + 95) )
      *(_DWORD *)(a3 + 28) |= 0x2000u;
    return 0;
  }
  v16 = *(unsigned __int8 **)(a3 + 16);
  v17 = *v16;
  if ( (unsigned int)v17 < *(_DWORD *)(a3 + 24) - 1 )
  {
    if ( (unsigned int)(*((_DWORD *)this + 101) - 1) <= 1 )
    {
      if ( !(_BYTE)v17
        || (v23.lpVtbl = (struct IMediaSampleVtbl *)(v16 + 1),
            v22 = v17,
            CMpeg2PSIParse::ProcessBuffer_(this, &v23, &v22, a9),
            (unsigned int)(*((_DWORD *)this + 101) - 1) <= 1) )
      {
        CMpeg2PSIParse::AbortPSICollection_(this);
      }
    }
    v18 = *(_DWORD *)(a3 + 24) - v17 - 1;
    v19 = (struct IMediaSampleVtbl *)(v17 + *(_QWORD *)(a3 + 16) + 1LL);
LABEL_32:
    v23.lpVtbl = v19;
    v22 = v18;
    while ( (unsigned int)CMpeg2PSIParse::ProcessBuffer_(this, &v23, &v22, a9) )
    {
      if ( v22 <= 0 || LOBYTE(v23.lpVtbl->QueryInterface) == 0xFF )
        return 0;
    }
    goto LABEL_24;
  }
  CMpeg2PSIParse::AbortPSICollection_(this);
LABEL_24:
  if ( *((_DWORD *)this + 95) )
    *(_DWORD *)(a3 + 28) |= 0x2000u;
  return 2147500037LL;
}

```

## disassembly

```asm
0x18002a7e0  mov     [rsp-18h+arg_8], rbx
0x18002a7e5  push    rbp
0x18002a7e6  push    rsi
0x18002a7e7  push    rdi
0x18002a7e8  mov     rbp, rsp
0x18002a7eb  sub     rsp, 30h
0x18002a7ef  mov     rax, [rcx+180h]
0x18002a7f6  mov     rdi, rcx
0x18002a7f9  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x18002a801  mov     esi, r9d
0x18002a804  mov     rbx, r8
0x18002a807  mov     rcx, [rax+10h]
0x18002a80b  test    rcx, rcx
0x18002a80e  jz      short loc_18002A820
0x18002a810  cmp     dword ptr [rdi+17Ch], 0
0x18002a817  jz      short loc_18002A820
0x18002a819  inc     qword ptr [rcx+108h]
0x18002a820  cmp     dword ptr [r8+18h], 0
0x18002a825  jz      loc_18002A951
0x18002a82b  test    dword ptr [r8+1Ch], 8000h
0x18002a833  jz      short loc_18002A86D
0x18002a835  cmp     dword ptr [r8+8], 0BCh
0x18002a83d  jnz     short loc_18002A86D
0x18002a83f  cmp     qword ptr [r8+10h], 0
0x18002a844  jz      short loc_18002A853
0x18002a846  mov     rax, [r8]
0x18002a849  add     rax, 4
0x18002a84d  cmp     [r8+10h], rax
0x18002a851  jb      short loc_18002A86D
0x18002a853  cmp     dword ptr [r8+18h], 0B8h
0x18002a85b  jg      short loc_18002A86D
0x18002a85d  mov     eax, [r8+30h]
0x18002a861  mov     [rdi+60h], eax
0x18002a864  mov     al, [r8+34h]
0x18002a868  and     al, 3
0x18002a86a  mov     [rdi+64h], al
0x18002a86d  mov     rcx, [rdi+198h]
0x18002a874  test    rcx, rcx
0x18002a877  jz      short loc_18002A88C
0x18002a879  mov     rax, [rcx]
0x18002a87c  lea     r8, [rbp+var_10]
0x18002a880  mov     edx, [rdi+60h]
0x18002a883  mov     rax, [rax+30h]
0x18002a887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a88c  cmp     [rbp+arg_20], 0
0x18002a890  mov     rax, [rbp+var_10]
0x18002a894  mov     [rdi+68h], rax
0x18002a898  jnz     short loc_18002A89E
0x18002a89a  test    esi, esi
0x18002a89c  jz      short loc_18002A8A6
0x18002a89e  mov     rcx, rdi; this
0x18002a8a1  call    ?AbortPSICollection_@CMpeg2PSIParse@@AEAAXXZ; CMpeg2PSIParse::AbortPSICollection_(void)
0x18002a8a6  cmp     [rbp+arg_30], 0
0x18002a8aa  jz      loc_18002A936
0x18002a8b0  mov     rcx, [rbx+10h]
0x18002a8b4  mov     eax, [rbx+18h]
0x18002a8b7  dec     eax
0x18002a8b9  movzx   esi, byte ptr [rcx]
0x18002a8bc  cmp     esi, eax
0x18002a8be  jnb     short loc_18002A919
0x18002a8c0  mov     eax, [rdi+194h]
0x18002a8c6  dec     eax
0x18002a8c8  cmp     eax, 1
0x18002a8cb  ja      short loc_18002A906
0x18002a8cd  test    sil, sil
0x18002a8d0  jz      short loc_18002A8FE
0x18002a8d2  mov     r9, [rbp+arg_40]
0x18002a8d6  lea     rax, [rcx+1]
0x18002a8da  mov     rcx, rdi; this
0x18002a8dd  mov     [rbp+arg_10], rax
0x18002a8e1  lea     r8, [rbp+arg_0]
0x18002a8e5  mov     [rbp+arg_0], esi
0x18002a8e8  lea     rdx, [rbp+arg_10]
0x18002a8ec  call    ?ProcessBuffer_@CMpeg2PSIParse@@AEAAHPEAPEAEPEAHPEAV?$CTStickyVal@H@@@Z; CMpeg2PSIParse::ProcessBuffer_(uchar * *,int *,CTStickyVal<int> *)
0x18002a8f1  mov     eax, [rdi+194h]
0x18002a8f7  dec     eax
0x18002a8f9  cmp     eax, 1
0x18002a8fc  ja      short loc_18002A906
0x18002a8fe  mov     rcx, rdi; this
0x18002a901  call    ?AbortPSICollection_@CMpeg2PSIParse@@AEAAXXZ; CMpeg2PSIParse::AbortPSICollection_(void)
0x18002a906  mov     edx, [rbx+18h]
0x18002a909  mov     r8, [rbx+10h]
0x18002a90d  sub     edx, esi
0x18002a90f  dec     edx
0x18002a911  inc     r8
0x18002a914  add     r8, rsi
0x18002a917  jmp     short loc_18002A967
0x18002a919  mov     rcx, rdi; this
0x18002a91c  call    ?AbortPSICollection_@CMpeg2PSIParse@@AEAAXXZ; CMpeg2PSIParse::AbortPSICollection_(void)
0x18002a921  cmp     dword ptr [rdi+17Ch], 0
0x18002a928  jz      short loc_18002A92F
0x18002a92a  bts     dword ptr [rbx+1Ch], 0Dh
0x18002a92f  mov     eax, 80004005h
0x18002a934  jmp     short loc_18002A953
0x18002a936  mov     eax, [rdi+194h]
0x18002a93c  dec     eax
0x18002a93e  cmp     eax, 1
0x18002a941  jbe     short loc_18002A960
0x18002a943  cmp     dword ptr [rdi+17Ch], 0
0x18002a94a  jz      short loc_18002A951
0x18002a94c  bts     dword ptr [rbx+1Ch], 0Dh
0x18002a951  xor     eax, eax
0x18002a953  mov     rbx, [rsp+30h+arg_8]
0x18002a958  add     rsp, 30h
0x18002a95c  pop     rdi
0x18002a95d  pop     rsi
0x18002a95e  pop     rbp
0x18002a95f  retn
0x18002a960  mov     edx, [rbx+18h]
0x18002a963  mov     r8, [rbx+10h]
0x18002a967  mov     [rbp+arg_10], r8
0x18002a96b  mov     [rbp+arg_0], edx
0x18002a96e  mov     r9, [rbp+arg_40]
0x18002a972  lea     r8, [rbp+arg_0]
0x18002a976  lea     rdx, [rbp+arg_10]
0x18002a97a  mov     rcx, rdi; this
0x18002a97d  call    ?ProcessBuffer_@CMpeg2PSIParse@@AEAAHPEAPEAEPEAHPEAV?$CTStickyVal@H@@@Z; CMpeg2PSIParse::ProcessBuffer_(uchar * *,int *,CTStickyVal<int> *)
0x18002a982  test    eax, eax
0x18002a984  jz      short loc_18002A921
0x18002a986  cmp     [rbp+arg_0], 0
0x18002a98a  jle     short loc_18002A951
0x18002a98c  mov     rax, [rbp+arg_10]
0x18002a990  cmp     byte ptr [rax], 0FFh
0x18002a993  jnz     short loc_18002A96E
0x18002a995  jmp     short loc_18002A951
```
