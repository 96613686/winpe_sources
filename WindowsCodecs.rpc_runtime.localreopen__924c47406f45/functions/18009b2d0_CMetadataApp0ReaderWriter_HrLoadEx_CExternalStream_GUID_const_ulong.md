# CMetadataApp0ReaderWriter::HrLoadEx(CExternalStream *,_GUID const *,ulong)

- ea: `0x18009b2d0`
- end: `0x18009b552`
- name: `?HrLoadEx@CMetadataApp0ReaderWriter@@UEAAJPEAVCExternalStream@@PEBU_GUID@@K@Z`
- size: `642`
- prototype: `__int64 __fastcall(CMetadataApp0ReaderWriter *__hidden this, struct CExternalStream *, const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180032d50`
- `0x180032d70`
- `0x180036cb4`
- `0x18009b2d0`
- `0x18009b560`
- `0x1800bb784`
- `0x1800e2f90`
- `0x18017b540`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009b449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009b449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b4e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b4e8`

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
0x18009b2d0  mov     [rsp+arg_10], rbx
0x18009b2d5  push    rbp
0x18009b2d6  push    rsi
0x18009b2d7  push    rdi
0x18009b2d8  push    r14
0x18009b2da  push    r15
0x18009b2dc  sub     rsp, 40h
0x18009b2e0  mov     rax, cs:__security_cookie
0x18009b2e7  xor     rax, rsp
0x18009b2ea  mov     [rsp+68h+var_30], rax
0x18009b2ef  xor     eax, eax
0x18009b2f1  lea     r14, [rcx+28h]
0x18009b2f5  mov     rdi, rcx
0x18009b2f8  mov     [rsp+68h+var_48], rax
0x18009b2fd  mov     rcx, r14; this
0x18009b300  mov     [rsp+68h+var_40], al
0x18009b304  mov     rbp, rdx
0x18009b307  xor     esi, esi
0x18009b309  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18009b30e  mov     rcx, rdi; this
0x18009b311  call    ?ClearFields@CMetadataApp0ReaderWriter@@EEAAJXZ; CMetadataApp0ReaderWriter::ClearFields(void)
0x18009b316  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18009b31c  mov     ebx, eax
0x18009b31e  test    eax, eax
0x18009b320  js      loc_18009B4CD
0x18009b326  test    rbp, rbp
0x18009b329  jz      short loc_18009B399
0x18009b32b  mov     eax, [rdi+80h]
0x18009b331  sub     eax, [rdi+88h]
0x18009b337  cmp     eax, 9
0x18009b33a  jb      loc_18009B52E
0x18009b340  mov     r8d, 5; unsigned int
0x18009b346  lea     rdx, [rsp+68h+Buf1]; void *
0x18009b34b  lea     rcx, [rbp+10h]; struct IStream *
0x18009b34f  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x18009b354  mov     ebx, eax
0x18009b356  test    eax, eax
0x18009b358  js      loc_18009B4F0
0x18009b35e  mov     r8d, 5; Size
0x18009b364  lea     rdx, aJfif; "JFIF"
0x18009b36b  lea     rcx, [rsp+68h+Buf1]; Buf1
0x18009b370  call    memcmp_0
0x18009b375  test    eax, eax
0x18009b377  jnz     loc_18009B537
0x18009b37d  lea     r8d, [rax+9]; unsigned int
0x18009b381  lea     rdx, [rsp+68h+var_48]; void *
0x18009b386  lea     rcx, [rbp+10h]; struct IStream *
0x18009b38a  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x18009b38f  mov     ebx, eax
0x18009b391  test    eax, eax
0x18009b393  js      loc_18009B4FA
0x18009b399  movzx   eax, word ptr [rsp+68h+var_48]
0x18009b39e  mov     edx, 12h
0x18009b3a3  movzx   ecx, ax
0x18009b3a6  mov     [rdi+98h], dx
0x18009b3ad  shr     cx, 8
0x18009b3b1  shl     ax, 8
0x18009b3b5  or      cx, ax
0x18009b3b8  mov     [rdi+0C8h], dx
0x18009b3bf  mov     al, byte ptr [rsp+68h+var_48+2]
0x18009b3c3  lea     r8d, [rdx-1]
0x18009b3c7  mov     [rdi+0A0h], cx
0x18009b3ce  mov     [rdi+0B8h], al
0x18009b3d4  movzx   eax, word ptr [rsp+68h+var_48+3]
0x18009b3d9  movzx   ecx, ax
0x18009b3dc  mov     [rdi+0E0h], dx
0x18009b3e3  movzx   edx, byte ptr [rsp+68h+var_48+7]
0x18009b3e8  shr     cx, 8
0x18009b3ec  shl     ax, 8
0x18009b3f0  or      cx, ax
0x18009b3f3  mov     [rdi+0B0h], r8w
0x18009b3fb  movzx   eax, word ptr [rsp+68h+var_48+5]
0x18009b400  mov     [rdi+0D0h], cx
0x18009b407  movzx   ecx, ax
0x18009b40a  shr     cx, 8
0x18009b40e  shl     ax, 8
0x18009b412  or      cx, ax
0x18009b415  mov     [rdi+0F8h], r8w
0x18009b41d  movzx   eax, [rsp+68h+var_40]
0x18009b422  mov     [rdi+0E8h], cx
0x18009b429  mov     ecx, eax
0x18009b42b  imul    ecx, edx
0x18009b42e  mov     [rdi+100h], dl
0x18009b434  mov     [rdi+110h], r8w
0x18009b43c  mov     [rdi+118h], al
0x18009b442  lea     r15d, [rcx+rcx*2]
0x18009b446  mov     ecx, r15d; cb
0x18009b449  call    cs:__imp_CoTaskMemAlloc
0x18009b44f  mov     rsi, rax
0x18009b452  test    rax, rax
0x18009b455  jz      loc_18009B544
0x18009b45b  test    rbp, rbp
0x18009b45e  jz      short loc_18009B479
0x18009b460  lea     rcx, [rbp+10h]; struct IStream *
0x18009b464  mov     r8d, r15d; unsigned int
0x18009b467  mov     rdx, rax; void *
0x18009b46a  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x18009b46f  mov     ebx, eax
0x18009b471  test    eax, eax
0x18009b473  js      loc_18009B50C
0x18009b479  mov     word ptr [rdi+128h], 41h ; 'A'
0x18009b482  mov     [rdi+130h], r15d
0x18009b489  mov     [rdi+138h], rsi
0x18009b490  mov     dword ptr [rdi+60h], 0
0x18009b497  xor     esi, esi
0x18009b499  test    ebx, ebx
0x18009b49b  js      short loc_18009B4D8
0x18009b49d  test    r14, r14
0x18009b4a0  jz      short loc_18009B4AA
0x18009b4a2  mov     rcx, r14; this
0x18009b4a5  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x18009b4aa  mov     eax, ebx
0x18009b4ac  mov     rcx, [rsp+68h+var_30]
0x18009b4b1  xor     rcx, rsp; StackCookie
0x18009b4b4  call    __security_check_cookie
0x18009b4b9  mov     rbx, [rsp+68h+arg_10]
0x18009b4c1  add     rsp, 40h
0x18009b4c5  pop     r15
0x18009b4c7  pop     r14
0x18009b4c9  pop     rdi
0x18009b4ca  pop     rsi
0x18009b4cb  pop     rbp
0x18009b4cc  retn
0x18009b4cd  test    ecx, ecx
0x18009b4cf  jz      short loc_18009B51E
0x18009b4d1  mov     ecx, eax; int
0x18009b4d3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009b4d8  mov     rcx, rdi; this
0x18009b4db  call    ?ClearFields@CMetadataApp0ReaderWriter@@EEAAJXZ; CMetadataApp0ReaderWriter::ClearFields(void)
0x18009b4e0  test    rsi, rsi
0x18009b4e3  jz      short loc_18009B49D
0x18009b4e5  mov     rcx, rsi; pv
0x18009b4e8  call    cs:__imp_CoTaskMemFree
0x18009b4ee  jmp     short loc_18009B49D
0x18009b4f0  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x18009b4f6  jnz     short loc_18009B4D1
0x18009b4f8  jmp     short loc_18009B4D8
0x18009b4fa  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x18009b500  jnz     short loc_18009B4D1
0x18009b502  test    eax, eax
0x18009b504  jns     loc_18009B399
0x18009b50a  jmp     short loc_18009B4D8
0x18009b50c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009b513  jnz     short loc_18009B4D1
0x18009b515  test    eax, eax
0x18009b517  js      short loc_18009B4D8
0x18009b519  jmp     loc_18009B479
0x18009b51e  test    eax, eax
0x18009b520  jns     loc_18009B326
0x18009b526  jmp     short loc_18009B4D8
0x18009b528  jz      short loc_18009B4D8
0x18009b52a  mov     ecx, ebx
0x18009b52c  jmp     short loc_18009B4D3
0x18009b52e  mov     ebx, 88982F60h
0x18009b533  test    ecx, ecx
0x18009b535  jmp     short loc_18009B528
0x18009b537  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x18009b53d  mov     ebx, 88982F61h
0x18009b542  jmp     short loc_18009B528
0x18009b544  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009b54b  mov     ebx, 8007000Eh
0x18009b550  jmp     short loc_18009B528
```
