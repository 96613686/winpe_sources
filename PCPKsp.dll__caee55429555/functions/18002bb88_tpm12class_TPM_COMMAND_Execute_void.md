# tpm12class::TPM_COMMAND::Execute(void)

- ea: `0x18002bb88`
- end: `0x18002c082`
- name: `?Execute@TPM_COMMAND@tpm12class@@QEAAJXZ`
- size: `1274`
- prototype: `__int64 __fastcall(tpm12class::TPM_COMMAND *__hidden this)`
- caller_count: `24`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029f48`
- `0x18002a0b0`
- `0x18002b6e0`
- `0x18004f050`
- `0x18005b7c0`
- `0x18005bcd8`
- `0x18006b1a4`
- `0x18006c5c0`
- `0x18006c6c0`
- `0x18006edfc`
- `0x180071b50`
- `0x18007255c`
- `0x180072c20`
- `0x180073810`
- `0x180082510`
- `0x180083058`
- `0x180083334`
- `0x180085300`
- `0x180085714`
- `0x18008623c`
- `0x180086b10`
- `0x1800875b4`
- `0x1800877b8`
- `0x1800a3c08`

## callees

- `0x18002a750`
- `0x18002bb88`
- `0x18002c324`
- `0x18002d890`
- `0x1800444c0`
- `0x18006edfc`
- `0x1800769e0`
- `0x180076e70`
- `0x18007704c`
- `0x1800a1620`
- `0x1800a177c`
- `0x1800a3b5c`
- `0x1800a3c08`
- `0x1800bacf4`
- `0x1800bb1f8`
- `0x1800bb7d0`
- `0x1800c8010`

## string_xrefs

- `0x18002befa`: `Tbsip_Submit_Command.`

## pseudocode

```c
__int64 __fastcall tpm12class::TPM_COMMAND::Execute(tpm12class::TPM_COMMAND *this)
{
  unsigned int v2; // r13d
  int v3; // ebx
  void *v4; // r12
  void *v5; // r15
  int v6; // ecx
  tpm12class::TPM_SESSION **v7; // r14
  tpm12class::TPM_SESSION **v8; // rsi
  tpm12class::TPM_SESSION *v9; // rcx
  tpm12class::TPM_SESSION *v10; // rax
  const wchar_t *v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  unsigned int v14; // r13d
  unsigned __int8 v15; // al
  unsigned int v16; // ebx
  bool v17; // sf
  tpm12class::TPM_SESSION *v18; // rcx
  __int64 v19; // rax
  _BYTE *v20; // rcx
  __int64 v21; // rcx
  _BYTE *v22; // rax
  size_t Size; // [rsp+78h] [rbp+48h] BYREF
  unsigned int v25; // [rsp+80h] [rbp+50h] BYREF
  int v26; // [rsp+88h] [rbp+58h]

  LODWORD(Size) = 4096;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  v25 = 0;
  v5 = 0;
  v6 = 256;
  v7 = (tpm12class::TPM_SESSION **)((char *)this + 72);
  v8 = (tpm12class::TPM_SESSION **)((char *)this + 64);
  while ( 1 )
  {
    v26 = v6 - 1;
    if ( v6 == 1 )
    {
LABEL_54:
      if ( v3 < 0 )
        goto LABEL_72;
      if ( TraceEnabled() )
      {
        (*(void (__fastcall **)(tpm12class::TPM_COMMAND *, const unsigned __int16 *, __int64))(*(_QWORD *)this + 64LL))(
          this,
          L"RSP.",
          197);
        if ( *((_WORD *)this + 40) == 197
          || (v8 = (tpm12class::TPM_SESSION **)((char *)this + 64), *((_WORD *)this + 40) == 198) )
        {
          (*(void (__fastcall **)(tpm12class::TPM_SESSION *, const unsigned __int16 *))(*(_QWORD *)*v8 + 16LL))(
            *v8,
            L"RSP.");
          if ( *((_WORD *)this + 40) == 198 )
            (*(void (__fastcall **)(tpm12class::TPM_SESSION *, const unsigned __int16 *))(*(_QWORD *)*v7 + 16LL))(
              *v7,
              L"RSP.");
        }
        TraceDirect(L"\r\n");
      }
      v18 = (tpm12class::TPM_SESSION *)*((_QWORD *)this + 8);
      if ( !v18 )
      {
        if ( !*v7 )
        {
          *((_WORD *)this + 40) = 196;
          goto LABEL_73;
        }
        goto LABEL_71;
      }
      if ( *((_QWORD *)this + 9) )
      {
        if ( !*v7 )
        {
LABEL_71:
          v3 = -2147024883;
          goto LABEL_72;
        }
        *((_WORD *)this + 40) = 198;
        v3 = tpm12class::TPM_SESSION::Refresh(v18);
        if ( v3 < 0 )
          goto LABEL_72;
        v18 = (tpm12class::TPM_SESSION *)*((_QWORD *)this + 9);
      }
      else
      {
        *((_WORD *)this + 40) = 197;
      }
      v3 = tpm12class::TPM_SESSION::Refresh(v18);
      if ( v3 >= 0 )
        goto LABEL_73;
      goto LABEL_72;
    }
    v8 = (tpm12class::TPM_SESSION **)((char *)this + 64);
    LODWORD(Size) = 4096;
    v9 = (tpm12class::TPM_SESSION *)*((_QWORD *)this + 8);
    if ( v9 )
    {
      if ( *v7 )
      {
        *((_WORD *)this + 40) = 195;
        v3 = tpm12class::TPM_SESSION::Create(v9);
        if ( v3 < 0 )
          goto LABEL_72;
        v3 = tpm12class::TPM_SESSION::Create(*v7);
        if ( v3 < 0 )
          goto LABEL_72;
        if ( !TraceEnabled() )
          goto LABEL_15;
        (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)*v8 + 26) + 8LL))(
          *((_QWORD *)*v8 + 26),
          L"AUTH1.");
        v10 = *v7;
        v11 = L"AUTH2.";
      }
      else
      {
        *((_WORD *)this + 40) = 194;
        v3 = tpm12class::TPM_SESSION::Create(v9);
        if ( v3 < 0 )
          goto LABEL_72;
        if ( !TraceEnabled() )
          goto LABEL_15;
        v10 = *v8;
        v11 = L"AUTH.";
      }
      (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)v10 + 26) + 8LL))(*((_QWORD *)v10 + 26), v11);
      TraceDirect(L"\r\n");
      goto LABEL_15;
    }
    if ( *v7 )
      goto LABEL_71;
    *((_WORD *)this + 40) = 193;
LABEL_15:
    v3 = tpm12class::TpmDataObject::Clear(this, 0);
    if ( v3 < 0 )
      goto LABEL_72;
    LOBYTE(v12) = 1;
    v3 = (*(__int64 (__fastcall **)(tpm12class::TPM_COMMAND *, __int64))(*(_QWORD *)this + 16LL))(this, v12);
    if ( v3 < 0 )
      goto LABEL_72;
    v3 = (**(__int64 (__fastcall ***)(tpm12class::TPM_COMMAND *))this)(this);
    if ( v3 < 0 )
      goto LABEL_72;
    LOBYTE(v13) = 1;
    v3 = (*(__int64 (__fastcall **)(tpm12class::TPM_COMMAND *, __int64))(*(_QWORD *)this + 48LL))(this, v13);
    if ( v3 < 0 )
      goto LABEL_72;
    v14 = *((_DWORD *)this + 4);
    v25 = v14;
    if ( v4 )
      operator delete(v4);
    v4 = operator new(v14);
    memset_0(v4, 0, v14);
    v3 = tpm12class::TPM_COMMAND::Get(this, (unsigned __int8 *)v4, v14, &v25);
    if ( v3 < 0 )
    {
      v2 = v25;
      goto LABEL_72;
    }
    v15 = TraceEnabled();
    v2 = v25;
    if ( v15 )
    {
      (*(void (__fastcall **)(tpm12class::TPM_COMMAND *, const wchar_t *))(*(_QWORD *)this + 56LL))(this, L"RQU.");
      v16 = 1;
      if ( (unsigned __int16)(*((_WORD *)this + 40) - 194) <= 1u )
        (*(void (__fastcall **)(tpm12class::TPM_SESSION *, const wchar_t *))(*(_QWORD *)*v8 + 8LL))(*v8, L"RQU.");
      if ( *((_WORD *)this + 40) == 195 )
        (*(void (__fastcall **)(tpm12class::TPM_SESSION *, const wchar_t *))(*(_QWORD *)*v7 + 8LL))(*v7, L"RQU.");
      TraceDirect(L"\r\n");
      TraceTpmBufferValue(1u, (unsigned __int8 *)v4, v2);
    }
    else
    {
      v16 = 1;
    }
    if ( v5 )
      operator delete(v5);
    v5 = operator new((unsigned int)Size);
    memset_0(v5, 0, (unsigned int)Size);
    if ( g_fpTpmSubmit )
      v16 = g_fpTpmSubmit((unsigned __int8 *const)v4, v2, (unsigned __int8 *)v5, (unsigned int *)&Size);
    v3 = v16 & 0xEFFFFFFF;
    if ( TraceEnabled() )
      break;
    v17 = v3 < 0;
    if ( v3 )
      goto LABEL_51;
LABEL_39:
    v3 = tpm12class::TPM_COMMAND::Set(this, (const unsigned __int8 *)v5, Size);
    if ( (v3 & 0xFFFF0000) != 0x80280000 )
      goto LABEL_54;
    if ( TraceEnabled() )
    {
      tpm12class::TPM_COMMAND::DecodeRsp(this, L"RSP.");
      TraceDirect(L"\r\n");
    }
    if ( v3 != -2144860160 )
      goto LABEL_54;
    if ( g_fpIdle )
      g_fpIdle(0x1F4u);
    if ( *v8 )
      tpm12class::TPM_SESSION::Release(*v8);
    if ( *v7 )
      tpm12class::TPM_SESSION::Release(*v7);
    v6 = v26;
  }
  if ( !v3 )
  {
    TraceTpmBufferValue(0, (unsigned __int8 *)v5, Size);
    TraceDirect(L"\r\n");
    goto LABEL_39;
  }
  TraceUINT32Value(L"Tbsip_Submit_Command.", L"TBS_RESULT", v3, 0, 0, 0);
  v17 = v3 < 0;
LABEL_51:
  if ( !v17 )
    goto LABEL_73;
LABEL_72:
  ReleaseSessionIf_0(*((_QWORD *)this + 8));
  ReleaseSessionIf_0(*((_QWORD *)this + 9));
LABEL_73:
  if ( v5 )
  {
    v19 = (unsigned int)Size;
    v20 = v5;
    if ( (_DWORD)Size )
    {
      do
      {
        *v20++ = 0;
        --v19;
      }
      while ( v19 );
    }
    operator delete(v5);
  }
  LODWORD(Size) = 0;
  if ( v4 )
  {
    v21 = v2;
    v22 = v4;
    if ( v2 )
    {
      do
      {
        *v22++ = 0;
        --v21;
      }
      while ( v21 );
    }
    operator delete(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002bb88  mov     [rsp-38h+arg_0], rbx
0x18002bb8d  push    rbp
0x18002bb8e  push    rsi
0x18002bb8f  push    rdi
0x18002bb90  push    r12
0x18002bb92  push    r13
0x18002bb94  push    r14
0x18002bb96  push    r15
0x18002bb98  mov     rbp, rsp
0x18002bb9b  sub     rsp, 30h
0x18002bb9f  mov     rdi, rcx
0x18002bba2  mov     dword ptr [rbp+Size], 1000h
0x18002bba9  xor     r13d, r13d
0x18002bbac  xor     ebx, ebx
0x18002bbae  xor     r12d, r12d
0x18002bbb1  mov     [rbp+arg_10], r13d
0x18002bbb5  xor     r15d, r15d
0x18002bbb8  mov     ecx, 100h
0x18002bbbd  lea     r14, [rdi+48h]
0x18002bbc1  lea     rsi, [rdi+40h]
0x18002bbc5  mov     eax, 0C3h
0x18002bbca  add     ecx, 0FFFFFFFFh
0x18002bbcd  mov     [rbp+arg_18], ecx
0x18002bbd0  lea     edx, [rax-1]
0x18002bbd3  jz      loc_18002BF1C
0x18002bbd9  lea     rsi, [rdi+40h]
0x18002bbdd  mov     dword ptr [rbp+Size], 1000h
0x18002bbe4  mov     rcx, [rsi]; this
0x18002bbe7  test    rcx, rcx
0x18002bbea  jnz     short loc_18002BC00
0x18002bbec  cmp     [r14], rcx
0x18002bbef  jnz     loc_18002BFFC
0x18002bbf5  mov     word ptr [rdi+50h], 0C1h
0x18002bbfb  jmp     loc_18002BCA6
0x18002bc00  cmp     qword ptr [r14], 0
0x18002bc04  jnz     short loc_18002BC32
0x18002bc06  mov     [rdi+50h], dx
0x18002bc0a  call    ?Create@TPM_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPM_SESSION::Create(void)
0x18002bc0f  mov     ebx, eax
0x18002bc11  test    eax, eax
0x18002bc13  js      loc_18002C001
0x18002bc19  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18002bc1e  test    al, al
0x18002bc20  jz      loc_18002BCA6
0x18002bc26  mov     rax, [rsi]
0x18002bc29  lea     rdx, aAuth_1; "AUTH."
0x18002bc30  jmp     short loc_18002BC87
0x18002bc32  mov     [rdi+50h], ax
0x18002bc36  call    ?Create@TPM_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPM_SESSION::Create(void)
0x18002bc3b  mov     ebx, eax
0x18002bc3d  test    eax, eax
0x18002bc3f  js      loc_18002C001
0x18002bc45  mov     rcx, [r14]; this
0x18002bc48  call    ?Create@TPM_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPM_SESSION::Create(void)
0x18002bc4d  mov     ebx, eax
0x18002bc4f  test    eax, eax
0x18002bc51  js      loc_18002C001
0x18002bc57  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18002bc5c  test    al, al
0x18002bc5e  jz      short loc_18002BCA6
0x18002bc60  mov     rax, [rsi]
0x18002bc63  lea     rdx, aAuth1_0; "AUTH1."
0x18002bc6a  mov     rcx, [rax+0D0h]
0x18002bc71  mov     rax, [rcx]
0x18002bc74  mov     rax, [rax+8]
0x18002bc78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc7d  mov     rax, [r14]
0x18002bc80  lea     rdx, aAuth2_0; "AUTH2."
0x18002bc87  mov     rcx, [rax+0D0h]
0x18002bc8e  mov     rax, [rcx]
0x18002bc91  mov     rax, [rax+8]
0x18002bc95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc9a  lea     rcx, asc_1800E7284; "\r\n"
0x18002bca1  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x18002bca6  xor     edx, edx; unsigned __int8
0x18002bca8  mov     rcx, rdi; this
0x18002bcab  call    ?Clear@TpmDataObject@tpm12class@@MEAAJE@Z; tpm12class::TpmDataObject::Clear(uchar)
0x18002bcb0  mov     ebx, eax
0x18002bcb2  test    eax, eax
0x18002bcb4  js      short loc_18002BD02
0x18002bcb6  mov     rax, [rdi]
0x18002bcb9  mov     dl, 1
0x18002bcbb  mov     rcx, rdi
0x18002bcbe  mov     rax, [rax+10h]
0x18002bcc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcc7  mov     ebx, eax
0x18002bcc9  test    eax, eax
0x18002bccb  js      short loc_18002BD02
0x18002bccd  mov     rax, [rdi]
0x18002bcd0  mov     rcx, rdi
0x18002bcd3  mov     rax, [rax]
0x18002bcd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcdb  mov     ebx, eax
0x18002bcdd  test    eax, eax
0x18002bcdf  js      short loc_18002BD02
0x18002bce1  mov     rax, [rdi]
0x18002bce4  mov     dl, 1
0x18002bce6  mov     rcx, rdi
0x18002bce9  mov     rax, [rax+30h]
0x18002bced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcf2  mov     ebx, eax
0x18002bcf4  test    eax, eax
0x18002bcf6  js      short loc_18002BD02
0x18002bcf8  mov     r13d, [rdi+10h]
0x18002bcfc  mov     [rbp+arg_10], r13d
0x18002bd00  jmp     short loc_18002BD0A
0x18002bd02  test    ebx, ebx
0x18002bd04  js      loc_18002C001
0x18002bd0a  test    r12, r12
0x18002bd0d  jz      short loc_18002BD17
0x18002bd0f  mov     rcx, r12; Block
0x18002bd12  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002bd17  mov     ecx, r13d; Size
0x18002bd1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bd1f  mov     r8d, r13d; Size
0x18002bd22  xor     edx, edx; Val
0x18002bd24  mov     rcx, rax; void *
0x18002bd27  mov     r12, rax
0x18002bd2a  call    memset_0
0x18002bd2f  lea     r9, [rbp+arg_10]; unsigned int *
0x18002bd33  mov     r8d, r13d; unsigned int
0x18002bd36  mov     rdx, r12; unsigned __int8 *
0x18002bd39  mov     rcx, rdi; this
0x18002bd3c  call    ?Get@TPM_COMMAND@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TPM_COMMAND::Get(uchar *,uint,uint *)
0x18002bd41  mov     ebx, eax
0x18002bd43  test    eax, eax
0x18002bd45  js      loc_18002BF13
0x18002bd4b  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18002bd50  mov     r13d, [rbp+arg_10]
0x18002bd54  test    al, al
0x18002bd56  jz      short loc_18002BDD6
0x18002bd58  mov     rax, [rdi]
0x18002bd5b  lea     rdx, aRqu; "RQU."
0x18002bd62  mov     rcx, rdi
0x18002bd65  mov     rax, [rax+38h]
0x18002bd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd6e  movzx   eax, word ptr [rdi+50h]
0x18002bd72  mov     ecx, 0C2h
0x18002bd77  sub     ax, cx
0x18002bd7a  mov     ebx, 1
0x18002bd7f  cmp     ax, bx
0x18002bd82  ja      short loc_18002BD9A
0x18002bd84  mov     rcx, [rsi]
0x18002bd87  lea     rdx, aRqu; "RQU."
0x18002bd8e  mov     rax, [rcx]
0x18002bd91  mov     rax, [rax+8]
0x18002bd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd9a  mov     eax, 0C3h
0x18002bd9f  cmp     [rdi+50h], ax
0x18002bda3  jnz     short loc_18002BDBB
0x18002bda5  mov     rcx, [r14]
0x18002bda8  lea     rdx, aRqu; "RQU."
0x18002bdaf  mov     rax, [rcx]
0x18002bdb2  mov     rax, [rax+8]
0x18002bdb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdbb  lea     rcx, asc_1800E7284; "\r\n"
0x18002bdc2  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x18002bdc7  mov     r8d, r13d; unsigned int
0x18002bdca  mov     rdx, r12; unsigned __int8 *
0x18002bdcd  mov     cl, bl; unsigned __int8
0x18002bdcf  call    ?TraceTpmBufferValue@@YAJEPEAEI@Z; TraceTpmBufferValue(uchar,uchar *,uint)
0x18002bdd4  jmp     short loc_18002BDDB
0x18002bdd6  mov     ebx, 1
0x18002bddb  test    r15, r15
0x18002bdde  jz      short loc_18002BDE8
0x18002bde0  mov     rcx, r15; Block
0x18002bde3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002bde8  mov     ecx, dword ptr [rbp+Size]; Size
0x18002bdeb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bdf0  mov     r8d, dword ptr [rbp+Size]; Size
0x18002bdf4  xor     edx, edx; Val
0x18002bdf6  mov     rcx, rax; void *
0x18002bdf9  mov     r15, rax
0x18002bdfc  call    memset_0
0x18002be01  mov     rax, cs:?g_fpTpmSubmit@@3P6AIQEAEIPEAEPEAI@ZEA; uint (*g_fpTpmSubmit)(uchar * const,uint,uchar *,uint *)
0x18002be08  test    rax, rax
0x18002be0b  jz      short loc_18002BE21
0x18002be0d  lea     r9, [rbp+Size]
0x18002be11  mov     r8, r15
0x18002be14  mov     edx, r13d
0x18002be17  mov     rcx, r12
0x18002be1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be1f  mov     ebx, eax
0x18002be21  btr     ebx, 1Ch
0x18002be25  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18002be2a  test    al, al
0x18002be2c  jz      short loc_18002BE52
0x18002be2e  test    ebx, ebx
0x18002be30  jnz     loc_18002BEDF
0x18002be36  mov     r8d, dword ptr [rbp+Size]; unsigned int
0x18002be3a  mov     rdx, r15; unsigned __int8 *
0x18002be3d  xor     ecx, ecx; unsigned __int8
0x18002be3f  call    ?TraceTpmBufferValue@@YAJEPEAEI@Z; TraceTpmBufferValue(uchar,uchar *,uint)
0x18002be44  lea     rcx, asc_1800E7284; "\r\n"
0x18002be4b  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x18002be50  jmp     short loc_18002BE5A
0x18002be52  test    ebx, ebx
0x18002be54  jnz     loc_18002BF08
0x18002be5a  mov     r8d, dword ptr [rbp+Size]; unsigned int
0x18002be5e  mov     rdx, r15; unsigned __int8 *
0x18002be61  mov     rcx, rdi; this
0x18002be64  call    ?Set@TPM_COMMAND@tpm12class@@QEAAJPEBEI@Z; tpm12class::TPM_COMMAND::Set(uchar const *,uint)
0x18002be69  mov     ebx, eax
0x18002be6b  and     eax, 0FFFF0000h
0x18002be70  cmp     eax, 80280000h
0x18002be75  jnz     loc_18002BF1C
0x18002be7b  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18002be80  test    al, al
0x18002be82  jz      short loc_18002BE9F
0x18002be84  lea     rdx, aRsp; "RSP."
0x18002be8b  mov     rcx, rdi; this
0x18002be8e  call    ?DecodeRsp@TPM_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPM_COMMAND::DecodeRsp(ushort *)
0x18002be93  lea     rcx, asc_1800E7284; "\r\n"
0x18002be9a  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x18002be9f  cmp     ebx, 80280800h
0x18002bea5  jnz     short loc_18002BF1C
0x18002bea7  mov     rax, cs:?g_fpIdle@@3P6AXK@ZEA; void (*g_fpIdle)(ulong)
0x18002beae  test    rax, rax
0x18002beb1  jz      short loc_18002BEBD
0x18002beb3  mov     ecx, 1F4h
0x18002beb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bebd  mov     rcx, [rsi]; this
0x18002bec0  test    rcx, rcx
0x18002bec3  jz      short loc_18002BECA
0x18002bec5  call    ?Release@TPM_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPM_SESSION::Release(void)
0x18002beca  mov     rcx, [r14]; this
0x18002becd  test    rcx, rcx
0x18002bed0  jz      short loc_18002BED7
0x18002bed2  call    ?Release@TPM_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPM_SESSION::Release(void)
0x18002bed7  mov     ecx, [rbp+arg_18]
0x18002beda  jmp     loc_18002BBC5
0x18002bedf  mov     [rsp+30h+var_8], 0; unsigned __int8
0x18002bee4  lea     rdx, aTbsResult; "TBS_RESULT"
0x18002beeb  xor     r9d, r9d; unsigned __int8
0x18002beee  mov     [rsp+30h+var_10], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x18002bef7  mov     r8d, ebx; unsigned int
0x18002befa  lea     rcx, aTbsipSubmitCom_0; "Tbsip_Submit_Command."
0x18002bf01  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18002bf06  test    ebx, ebx
0x18002bf08  js      loc_18002C001
0x18002bf0e  jmp     loc_18002C013
0x18002bf13  mov     r13d, [rbp+arg_10]
0x18002bf17  jmp     loc_18002C001
0x18002bf1c  test    ebx, ebx
0x18002bf1e  js      loc_18002C001
0x18002bf24  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18002bf29  mov     edx, 0C6h
0x18002bf2e  lea     r8d, [rdx-1]
0x18002bf32  test    al, al
0x18002bf34  jz      short loc_18002BFB2
0x18002bf36  mov     rax, [rdi]
0x18002bf39  lea     rdx, aRsp; "RSP."
0x18002bf40  mov     rcx, rdi
0x18002bf43  mov     rax, [rax+40h]
0x18002bf47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf4c  mov     eax, 0C5h
0x18002bf51  cmp     [rdi+50h], ax
0x18002bf55  jz      short loc_18002BF66
0x18002bf57  mov     eax, 0C6h
0x18002bf5c  lea     rsi, [rdi+40h]
0x18002bf60  cmp     [rdi+50h], ax
0x18002bf64  jnz     short loc_18002BF9D
0x18002bf66  mov     rcx, [rsi]
0x18002bf69  lea     rdx, aRsp; "RSP."
0x18002bf70  mov     rax, [rcx]
0x18002bf73  mov     rax, [rax+10h]
0x18002bf77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf7c  mov     eax, 0C6h
0x18002bf81  cmp     [rdi+50h], ax
0x18002bf85  jnz     short loc_18002BF9D
0x18002bf87  mov     rcx, [r14]
0x18002bf8a  lea     rdx, aRsp; "RSP."
0x18002bf91  mov     rax, [rcx]
0x18002bf94  mov     rax, [rax+10h]
0x18002bf98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf9d  lea     rcx, asc_1800E7284; "\r\n"
0x18002bfa4  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x18002bfa9  mov     edx, 0C6h
0x18002bfae  lea     r8d, [rdx-1]
0x18002bfb2  mov     rcx, [rdi+40h]; this
0x18002bfb6  test    rcx, rcx
0x18002bfb9  jnz     short loc_18002BFC8
0x18002bfbb  cmp     [r14], rcx
0x18002bfbe  jnz     short loc_18002BFFC
0x18002bfc0  mov     word ptr [rdi+50h], 0C4h
0x18002bfc6  jmp     short loc_18002C013
0x18002bfc8  cmp     qword ptr [rdi+48h], 0
0x18002bfcd  jnz     short loc_18002BFE1
0x18002bfcf  mov     [rdi+50h], r8w
0x18002bfd4  call    ?Refresh@TPM_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPM_SESSION::Refresh(void)
0x18002bfd9  mov     ebx, eax
0x18002bfdb  test    eax, eax
0x18002bfdd  jns     short loc_18002C013
0x18002bfdf  jmp     short loc_18002C001
0x18002bfe1  cmp     qword ptr [r14], 0
0x18002bfe5  jz      short loc_18002BFFC
0x18002bfe7  mov     [rdi+50h], dx
0x18002bfeb  call    ?Refresh@TPM_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPM_SESSION::Refresh(void)
0x18002bff0  mov     ebx, eax
0x18002bff2  test    eax, eax
  ... truncated ...
```
