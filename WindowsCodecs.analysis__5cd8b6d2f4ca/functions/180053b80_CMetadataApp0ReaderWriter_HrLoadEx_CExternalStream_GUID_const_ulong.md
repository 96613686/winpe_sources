# CMetadataApp0ReaderWriter::HrLoadEx(CExternalStream *,_GUID const *,ulong)

- ea: `0x180053b80`
- end: `0x180053e0f`
- name: `?HrLoadEx@CMetadataApp0ReaderWriter@@UEAAJPEAVCExternalStream@@PEBU_GUID@@K@Z`
- size: `655`
- prototype: `__int64 __fastcall(CMetadataApp0ReaderWriter *this, struct CExternalStream *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800319d0`
- `0x1800319f0`
- `0x180052780`
- `0x180053b80`
- `0x1800542e8`
- `0x1800bd9d4`
- `0x1800e5e60`
- `0x18017e450`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053cf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053cf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053d9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053d9f`

## pseudocode

```c
__int64 __fastcall CMetadataApp0ReaderWriter::HrLoadEx(
        CMetadataApp0ReaderWriter *this,
        struct CExternalStream *a2,
        const struct _GUID *a3)
{
  CMTALock *v3; // r14
  void *v6; // rsi
  int FullBufferFromStream; // eax
  int v8; // ebx
  __int16 v9; // ax
  unsigned __int16 v10; // cx
  __int16 v11; // cx
  __int16 v12; // ax
  unsigned __int16 v13; // cx
  int v14; // edx
  __int16 v15; // cx
  unsigned __int16 v16; // ax
  __int16 v17; // cx
  int v18; // eax
  unsigned int v19; // r15d
  void *v20; // rax
  int v22; // ecx
  bool v23; // zf
  __int64 v24; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int8 v25; // [rsp+28h] [rbp-40h]
  char Buf1[8]; // [rsp+30h] [rbp-38h] BYREF

  v3 = (CMetadataApp0ReaderWriter *)((char *)this + 40);
  v24 = 0;
  v25 = 0;
  v6 = 0;
  CMTALock::Enter((CMetadataApp0ReaderWriter *)((char *)this + 40));
  FullBufferFromStream = CMetadataApp0ReaderWriter::ClearFields(this);
  v8 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_17;
    goto LABEL_15;
  }
  if ( !a2 )
    goto LABEL_7;
  if ( (unsigned int)(*((_DWORD *)this + 32) - *((_DWORD *)this + 34)) < 9 )
  {
    v8 = -2003292320;
    v23 = (_DWORD)g_doStackCaptures == 0;
LABEL_26:
    if ( v23 )
      goto LABEL_17;
    v22 = v8;
LABEL_16:
    DoStackCapture(v22);
    goto LABEL_17;
  }
  FullBufferFromStream = ReadFullBufferFromStream((struct CExternalStream *)((char *)a2 + 16), Buf1, 5u);
  v8 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_17;
    goto LABEL_15;
  }
  if ( strcmp(Buf1, "JFIF") )
  {
    v23 = (_DWORD)g_doStackCaptures == 0;
    v8 = -2003292319;
    goto LABEL_26;
  }
  FullBufferFromStream = ReadFullBufferFromStream((struct CExternalStream *)((char *)a2 + 16), &v24, 9u);
  v8 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_17;
    goto LABEL_15;
  }
LABEL_7:
  v9 = v24;
  v10 = v24;
  *((_WORD *)this + 76) = 18;
  v11 = (v9 << 8) | HIBYTE(v10);
  *((_WORD *)this + 100) = 18;
  LOBYTE(v9) = BYTE2(v24);
  *((_WORD *)this + 80) = v11;
  *((_BYTE *)this + 184) = v9;
  v12 = *(_WORD *)((char *)&v24 + 3);
  v13 = *(_WORD *)((char *)&v24 + 3);
  *((_WORD *)this + 112) = 18;
  v14 = HIBYTE(v24);
  v15 = (v12 << 8) | HIBYTE(v13);
  *((_WORD *)this + 88) = 17;
  v16 = *(_WORD *)((char *)&v24 + 5);
  *((_WORD *)this + 104) = v15;
  v17 = (v16 << 8) | HIBYTE(v16);
  *((_WORD *)this + 124) = 17;
  v18 = v25;
  *((_WORD *)this + 116) = v17;
  *((_BYTE *)this + 256) = v14;
  *((_WORD *)this + 136) = 17;
  *((_BYTE *)this + 280) = v18;
  v19 = 3 * v14 * v18;
  v20 = CoTaskMemAlloc(v19);
  v6 = v20;
  if ( !v20 )
  {
    v23 = (_DWORD)g_doStackCaptures == 0;
    v8 = -2147024882;
    goto LABEL_26;
  }
  if ( !a2
    || (FullBufferFromStream = ReadFullBufferFromStream((struct CExternalStream *)((char *)a2 + 16), v20, v19),
        v8 = FullBufferFromStream,
        FullBufferFromStream >= 0) )
  {
    *((_WORD *)this + 148) = 65;
    *((_DWORD *)this + 76) = v19;
    *((_QWORD *)this + 39) = v6;
    *((_DWORD *)this + 24) = 0;
    v6 = 0;
    if ( v8 >= 0 )
      goto LABEL_11;
    goto LABEL_17;
  }
  if ( (_DWORD)g_doStackCaptures )
  {
LABEL_15:
    v22 = FullBufferFromStream;
    goto LABEL_16;
  }
LABEL_17:
  CMetadataApp0ReaderWriter::ClearFields(this);
  if ( v6 )
    CoTaskMemFree(v6);
LABEL_11:
  if ( v3 )
    CMTALock::Leave(v3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180053b80  mov     [rsp+arg_10], rbx
0x180053b85  push    rbp
0x180053b86  push    rsi
0x180053b87  push    rdi
0x180053b88  push    r14
0x180053b8a  push    r15
0x180053b8c  sub     rsp, 40h
0x180053b90  mov     rax, cs:__security_cookie
0x180053b97  xor     rax, rsp
0x180053b9a  mov     [rsp+68h+var_30], rax
0x180053b9f  xor     eax, eax
0x180053ba1  lea     r14, [rcx+28h]
0x180053ba5  mov     rdi, rcx
0x180053ba8  mov     [rsp+68h+var_48], rax
0x180053bad  mov     rcx, r14; this
0x180053bb0  mov     [rsp+68h+var_40], al
0x180053bb4  mov     rbp, rdx
0x180053bb7  xor     esi, esi
0x180053bb9  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180053bbe  mov     rcx, rdi; this
0x180053bc1  call    ?ClearFields@CMetadataApp0ReaderWriter@@EEAAJXZ; CMetadataApp0ReaderWriter::ClearFields(void)
0x180053bc6  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180053bcc  mov     ebx, eax
0x180053bce  test    eax, eax
0x180053bd0  js      loc_180053D84
0x180053bd6  test    rbp, rbp
0x180053bd9  jz      short loc_180053C49
0x180053bdb  mov     eax, [rdi+80h]
0x180053be1  sub     eax, [rdi+88h]
0x180053be7  cmp     eax, 9
0x180053bea  jb      loc_180053DEB
0x180053bf0  mov     r8d, 5; unsigned int
0x180053bf6  lea     rdx, [rsp+68h+Buf1]; void *
0x180053bfb  lea     rcx, [rbp+10h]; struct IStream *
0x180053bff  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x180053c04  mov     ebx, eax
0x180053c06  test    eax, eax
0x180053c08  js      loc_180053DAD
0x180053c0e  mov     r8d, 5; Size
0x180053c14  lea     rdx, aJfif; "JFIF"
0x180053c1b  lea     rcx, [rsp+68h+Buf1]; Buf1
0x180053c20  call    memcmp_0
0x180053c25  test    eax, eax
0x180053c27  jnz     loc_180053DF4
0x180053c2d  lea     r8d, [rax+9]; unsigned int
0x180053c31  lea     rdx, [rsp+68h+var_48]; void *
0x180053c36  lea     rcx, [rbp+10h]; struct IStream *
0x180053c3a  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x180053c3f  mov     ebx, eax
0x180053c41  test    eax, eax
0x180053c43  js      loc_180053DB7
0x180053c49  movzx   eax, word ptr [rsp+68h+var_48]
0x180053c4e  mov     edx, 12h
0x180053c53  movzx   ecx, ax
0x180053c56  mov     [rdi+98h], dx
0x180053c5d  shr     cx, 8
0x180053c61  shl     ax, 8
0x180053c65  or      cx, ax
0x180053c68  mov     [rdi+0C8h], dx
0x180053c6f  mov     al, byte ptr [rsp+68h+var_48+2]
0x180053c73  lea     r8d, [rdx-1]
0x180053c77  mov     [rdi+0A0h], cx
0x180053c7e  mov     [rdi+0B8h], al
0x180053c84  movzx   eax, word ptr [rsp+68h+var_48+3]
0x180053c89  movzx   ecx, ax
0x180053c8c  mov     [rdi+0E0h], dx
0x180053c93  movzx   edx, byte ptr [rsp+68h+var_48+7]
0x180053c98  shr     cx, 8
0x180053c9c  shl     ax, 8
0x180053ca0  or      cx, ax
0x180053ca3  mov     [rdi+0B0h], r8w
0x180053cab  movzx   eax, word ptr [rsp+68h+var_48+5]
0x180053cb0  mov     [rdi+0D0h], cx
0x180053cb7  movzx   ecx, ax
0x180053cba  shr     cx, 8
0x180053cbe  shl     ax, 8
0x180053cc2  or      cx, ax
0x180053cc5  mov     [rdi+0F8h], r8w
0x180053ccd  movzx   eax, [rsp+68h+var_40]
0x180053cd2  mov     [rdi+0E8h], cx
0x180053cd9  mov     ecx, eax
0x180053cdb  imul    ecx, edx
0x180053cde  mov     [rdi+100h], dl
0x180053ce4  mov     [rdi+110h], r8w
0x180053cec  mov     [rdi+118h], al
0x180053cf2  lea     r15d, [rcx+rcx*2]
0x180053cf6  mov     ecx, r15d; cb
0x180053cf9  call    cs:__imp_CoTaskMemAlloc
0x180053d00  nop     dword ptr [rax+rax+00h]
0x180053d05  mov     rsi, rax
0x180053d08  test    rax, rax
0x180053d0b  jz      loc_180053E01
0x180053d11  test    rbp, rbp
0x180053d14  jz      short loc_180053D2F
0x180053d16  lea     rcx, [rbp+10h]; struct IStream *
0x180053d1a  mov     r8d, r15d; unsigned int
0x180053d1d  mov     rdx, rax; void *
0x180053d20  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x180053d25  mov     ebx, eax
0x180053d27  test    eax, eax
0x180053d29  js      loc_180053DC9
0x180053d2f  mov     word ptr [rdi+128h], 41h ; 'A'
0x180053d38  mov     [rdi+130h], r15d
0x180053d3f  mov     [rdi+138h], rsi
0x180053d46  mov     dword ptr [rdi+60h], 0
0x180053d4d  xor     esi, esi
0x180053d4f  test    ebx, ebx
0x180053d51  js      short loc_180053D8F
0x180053d53  test    r14, r14
0x180053d56  jz      short loc_180053D60
0x180053d58  mov     rcx, r14; this
0x180053d5b  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x180053d60  mov     eax, ebx
0x180053d62  mov     rcx, [rsp+68h+var_30]
0x180053d67  xor     rcx, rsp; StackCookie
0x180053d6a  call    __security_check_cookie
0x180053d6f  mov     rbx, [rsp+68h+arg_10]
0x180053d77  add     rsp, 40h
0x180053d7b  pop     r15
0x180053d7d  pop     r14
0x180053d7f  pop     rdi
0x180053d80  pop     rsi
0x180053d81  pop     rbp
0x180053d82  retn
0x180053d84  test    ecx, ecx
0x180053d86  jz      short loc_180053DDB
0x180053d88  mov     ecx, eax; int
0x180053d8a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180053d8f  mov     rcx, rdi; this
0x180053d92  call    ?ClearFields@CMetadataApp0ReaderWriter@@EEAAJXZ; CMetadataApp0ReaderWriter::ClearFields(void)
0x180053d97  test    rsi, rsi
0x180053d9a  jz      short loc_180053D53
0x180053d9c  mov     rcx, rsi; pv
0x180053d9f  call    cs:__imp_CoTaskMemFree
0x180053da6  nop     dword ptr [rax+rax+00h]
0x180053dab  jmp     short loc_180053D53
0x180053dad  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180053db3  jnz     short loc_180053D88
0x180053db5  jmp     short loc_180053D8F
0x180053db7  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180053dbd  jnz     short loc_180053D88
0x180053dbf  test    eax, eax
0x180053dc1  jns     loc_180053C49
0x180053dc7  jmp     short loc_180053D8F
0x180053dc9  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180053dd0  jnz     short loc_180053D88
0x180053dd2  test    eax, eax
0x180053dd4  js      short loc_180053D8F
0x180053dd6  jmp     loc_180053D2F
0x180053ddb  test    eax, eax
0x180053ddd  jns     loc_180053BD6
0x180053de3  jmp     short loc_180053D8F
0x180053de5  jz      short loc_180053D8F
0x180053de7  mov     ecx, ebx
0x180053de9  jmp     short loc_180053D8A
0x180053deb  mov     ebx, 88982F60h
0x180053df0  test    ecx, ecx
0x180053df2  jmp     short loc_180053DE5
0x180053df4  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180053dfa  mov     ebx, 88982F61h
0x180053dff  jmp     short loc_180053DE5
0x180053e01  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180053e08  mov     ebx, 8007000Eh
0x180053e0d  jmp     short loc_180053DE5
```
