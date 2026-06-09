# RWFileManager::RWFileManager(wchar_t const *,wchar_t const *)

- ea: `0x18013bc20`
- end: `0x18013c00b`
- name: `??0RWFileManager@@QEAA@PEB_W0@Z`
- size: `1003`
- prototype: `RWFileManager *__fastcall(RWFileManager *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180095380`

## callees

- `0x180083790`
- `0x180135760`
- `0x180135ab0`
- `0x180135b40`
- `0x180135d40`
- `0x180137ba0`
- `0x180138110`
- `0x1801381a0`
- `0x18013b2e4`
- `0x18013b638`
- `0x18013b888`
- `0x18013bc20`
- `0x18013c1f0`
- `0x18013c250`
- `0x18013c2b0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18013bcd4`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18013bcf8`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18013bd1c`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18013bf07`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18013bf2b`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18013bf4e`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18013bcd4`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18013bcf8`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18013bd1c`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18013bf07`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18013bf2b`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18013bf4e`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x18013bd8b`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x18013bda7`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x18013bdc4`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x18013bd8b`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x18013bda7`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x18013bdc4`
- `api-ms-win-crt-stdio-l1-1-0!fseek` at `0x18013bcaa`
- `api-ms-win-crt-stdio-l1-1-0!fseek` at `0x18013bd67`
- `api-ms-win-crt-stdio-l1-1-0!fseek` at `0x18013bee4`
- `api-ms-win-crt-stdio-l1-1-0!fseek` at `0x18013bcaa`
- `api-ms-win-crt-stdio-l1-1-0!fseek` at `0x18013bd67`
- `api-ms-win-crt-stdio-l1-1-0!fseek` at `0x18013bee4`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18013bd3f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18013bdfd`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18013be5a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18013bf71`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18013bd3f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18013bdfd`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18013be5a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18013bf71`
- `api-ms-win-crt-filesystem-l1-1-0!_waccess` at `0x18013bc77`
- `api-ms-win-crt-filesystem-l1-1-0!_waccess` at `0x18013bc77`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
RWFileManager *__fastcall RWFileManager::RWFileManager(RWFileManager *this, const wchar_t *a2, const wchar_t *a3)
{
  __int64 v4; // rdi
  _DWORD *v5; // r12
  _DWORD *v6; // r13
  int IsEmpty; // eax
  FILE *v8; // rcx
  void *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  _QWORD *v12; // rax
  void *v14; // rax
  const struct RWCatMsg *v15; // rax
  const struct RWMessage *v16; // rax
  const struct RWxmsg *v17; // rax
  _QWORD v18[2]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v19[32]; // [rsp+30h] [rbp-20h] BYREF
  void *Buffer; // [rsp+98h] [rbp+48h] BYREF

  v18[1] = -2;
  RWFile::RWFile(this, a2, a3);
  v4 = 0;
  *((_QWORD *)this + 2) = 0;
  v5 = (_DWORD *)((char *)this + 24);
  *((_DWORD *)this + 6) = -1;
  v6 = (_DWORD *)((char *)this + 28);
  *((_DWORD *)this + 7) = -1;
  if ( *((_QWORD *)this + 1) && waccess(*(const wchar_t **)this, 0) >= 0 )
  {
    IsEmpty = RWFile::IsEmpty(this);
    v8 = (FILE *)*((_QWORD *)this + 1);
    if ( IsEmpty )
    {
      *v5 = -1;
      *v6 = 280;
      if ( fseek(v8, 0, 0) < 0 )
        RWFileManager::seekErr(this);
      LODWORD(Buffer) = *v5;
      if ( fwrite(&Buffer, 4u, 1u, *((FILE **)this + 1)) != 1
        || (LODWORD(Buffer) = *v6, fwrite(&Buffer, 4u, 1u, *((FILE **)this + 1)) != 1)
        || (LODWORD(Buffer) = 268, fwrite(&Buffer, 4u, 1u, *((FILE **)this + 1)) != 1) )
      {
        RWFileManager::writeErr(this);
      }
      if ( dword_1802B0018 )
        v9 = COWSAllocator::AllocCurrentHeap(0x128u);
      else
        v9 = malloc(0x128u);
      Buffer = v9;
      if ( v9 )
        v4 = sub_18013B638(v9, this, 1);
LABEL_45:
      *((_QWORD *)this + 2) = v4;
      return this;
    }
    LODWORD(Buffer) = 0;
    if ( fseek(v8, 0, 0) < 0 )
      RWFileManager::seekErr(this);
    if ( fread((char *)this + 24, 4u, 1u, *((FILE **)this + 1)) != 1
      || fread((char *)this + 28, 4u, 1u, *((FILE **)this + 1)) != 1
      || fread(&Buffer, 4u, 1u, *((FILE **)this + 1)) != 1 )
    {
      RWFileManager::readErr(this);
    }
    if ( (unsigned int)Buffer > 0x3E80 )
    {
      if ( !(unsigned int)RWFile::Erase(this) )
        RWFileManager::seekErr(this);
      *v5 = -1;
      *v6 = 280;
      LODWORD(Buffer) = 268;
      if ( fseek(*((FILE **)this + 1), 0, 0) < 0 )
        RWFileManager::seekErr(this);
      LODWORD(v18[0]) = *v5;
      if ( fwrite(v18, 4u, 1u, *((FILE **)this + 1)) != 1
        || (LODWORD(v18[0]) = *v6, fwrite(v18, 4u, 1u, *((FILE **)this + 1)) != 1)
        || (LODWORD(v18[0]) = (_DWORD)Buffer, fwrite(v18, 4u, 1u, *((FILE **)this + 1)) != 1) )
      {
        RWFileManager::writeErr(this);
      }
      if ( dword_1802B0018 )
        v14 = COWSAllocator::AllocCurrentHeap(0x128u);
      else
        v14 = malloc(0x128u);
      v18[0] = v14;
      if ( v14 )
        v4 = sub_18013B638(v14, this, 1);
      goto LABEL_45;
    }
    if ( (_DWORD)Buffer == 268 )
    {
      if ( dword_1802B0018 )
        v10 = COWSAllocator::AllocCurrentHeap(0x128u);
      else
        v10 = malloc(0x128u);
      v11 = v10;
      v18[0] = v10;
      if ( v10 )
      {
        *v10 = &RWListManager::`vftable';
        v10[1] = this;
        *v10 = &RWNewListManager::`vftable';
        sub_18013B888(v10, 12);
      }
      else
      {
        v11 = 0;
      }
    }
    else
    {
      if ( (_DWORD)Buffer != 92 )
      {
        v15 = RWTOOL_FLIST();
        v16 = RWMessage::RWMessage((RWMessage *)v18, v15, 268, (unsigned int)Buffer);
        v17 = RWExternalErr::RWExternalErr((RWExternalErr *)v19, v16);
        RWThrow(v17);
      }
      if ( dword_1802B0018 )
        v12 = COWSAllocator::AllocCurrentHeap(0x78u);
      else
        v12 = malloc(0x78u);
      v11 = v12;
      v18[0] = v12;
      if ( v12 )
      {
        *v12 = &RWListManager::`vftable';
        v12[1] = this;
        *v12 = &RWOldListManager::`vftable';
        sub_18013B2E4(v12, 12);
      }
      else
      {
        v11 = 0;
      }
    }
    *((_QWORD *)this + 2) = v11;
  }
  return this;
}

```

## disassembly

```asm
0x18013bc20  mov     rax, rsp
0x18013bc23  mov     [rax+8], rcx
0x18013bc27  push    rbp
0x18013bc28  push    rdi
0x18013bc29  push    r12
0x18013bc2b  push    r13
0x18013bc2d  push    r14
0x18013bc2f  mov     rbp, rsp
0x18013bc32  sub     rsp, 50h
0x18013bc36  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x18013bc3e  mov     [rax+10h], rbx
0x18013bc42  mov     [rax+18h], rsi
0x18013bc46  mov     rbx, rcx
0x18013bc49  call    ??0RWFile@@QEAA@PEB_W0@Z; RWFile::RWFile(wchar_t const *,wchar_t const *)
0x18013bc4e  nop
0x18013bc4f  xor     edi, edi
0x18013bc51  mov     [rbx+10h], rdi
0x18013bc55  lea     r12, [rbx+18h]
0x18013bc59  or      esi, 0FFFFFFFFh
0x18013bc5c  mov     [r12], esi
0x18013bc60  lea     r13, [rbx+1Ch]
0x18013bc64  mov     [r13+0], esi
0x18013bc68  cmp     [rbx+8], rdi
0x18013bc6c  jz      loc_18013BE9B
0x18013bc72  xor     edx, edx; AccessMode
0x18013bc74  mov     rcx, [rbx]; FileName
0x18013bc77  call    cs:_waccess
0x18013bc7d  test    eax, eax
0x18013bc7f  js      loc_18013BE9B
0x18013bc85  mov     rcx, rbx; this
0x18013bc88  call    ?IsEmpty@RWFile@@QEAAHXZ; RWFile::IsEmpty(void)
0x18013bc8d  xor     r8d, r8d; Origin
0x18013bc90  xor     edx, edx; Offset
0x18013bc92  mov     rcx, [rbx+8]; Stream
0x18013bc96  test    eax, eax
0x18013bc98  jz      loc_18013BD64
0x18013bc9e  mov     [r12], esi
0x18013bca2  mov     dword ptr [r13+0], 118h
0x18013bcaa  call    cs:fseek
0x18013bcb0  test    eax, eax
0x18013bcb2  js      loc_18013BF9A
0x18013bcb8  mov     eax, [r12]
0x18013bcbc  mov     dword ptr [rbp+Buffer], eax
0x18013bcbf  mov     r9, [rbx+8]; Stream
0x18013bcc3  lea     esi, [rdi+1]
0x18013bcc6  mov     r8d, esi; ElementCount
0x18013bcc9  lea     r14d, [rdi+4]
0x18013bccd  mov     edx, r14d; ElementSize
0x18013bcd0  lea     rcx, [rbp+Buffer]; Buffer
0x18013bcd4  call    cs:fwrite
0x18013bcda  cmp     rax, rsi
0x18013bcdd  jnz     loc_18013BFA3
0x18013bce3  mov     eax, [r13+0]
0x18013bce7  mov     dword ptr [rbp+Buffer], eax
0x18013bcea  mov     r9, [rbx+8]; Stream
0x18013bcee  mov     r8d, esi; ElementCount
0x18013bcf1  mov     edx, r14d; ElementSize
0x18013bcf4  lea     rcx, [rbp+Buffer]; Buffer
0x18013bcf8  call    cs:fwrite
0x18013bcfe  cmp     rax, rsi
0x18013bd01  jnz     loc_18013BFA3
0x18013bd07  mov     dword ptr [rbp+Buffer], 10Ch
0x18013bd0e  mov     r9, [rbx+8]; Stream
0x18013bd12  mov     r8d, esi; ElementCount
0x18013bd15  mov     edx, r14d; ElementSize
0x18013bd18  lea     rcx, [rbp+Buffer]; Buffer
0x18013bd1c  call    cs:fwrite
0x18013bd22  cmp     rax, rsi
0x18013bd25  jnz     loc_18013BFA3
0x18013bd2b  mov     ecx, 128h; unsigned __int64
0x18013bd30  cmp     cs:dword_1802B0018, edi
0x18013bd36  jz      short loc_18013BD3F
0x18013bd38  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18013bd3d  jmp     short loc_18013BD45
0x18013bd3f  call    cs:malloc
0x18013bd45  mov     [rbp+Buffer], rax
0x18013bd49  test    rax, rax
0x18013bd4c  jz      short loc_18013BD5F
0x18013bd4e  mov     r8d, esi
0x18013bd51  mov     rdx, rbx
0x18013bd54  mov     rcx, rax
0x18013bd57  call    sub_18013B638
0x18013bd5c  mov     rdi, rax
0x18013bd5f  jmp     loc_18013BF91
0x18013bd64  mov     dword ptr [rbp+Buffer], edi
0x18013bd67  call    cs:fseek
0x18013bd6d  test    eax, eax
0x18013bd6f  js      loc_18013BFAC
0x18013bd75  mov     r9, [rbx+8]; Stream
0x18013bd79  mov     esi, 1
0x18013bd7e  mov     r8d, esi; ElementCount
0x18013bd81  lea     r14d, [rsi+3]
0x18013bd85  mov     edx, r14d; ElementSize
0x18013bd88  mov     rcx, r12; Buffer
0x18013bd8b  call    cs:fread
0x18013bd91  cmp     rax, rsi
0x18013bd94  jnz     loc_18013C002
0x18013bd9a  mov     r9, [rbx+8]; Stream
0x18013bd9e  mov     r8d, esi; ElementCount
0x18013bda1  mov     edx, r14d; ElementSize
0x18013bda4  mov     rcx, r13; Buffer
0x18013bda7  call    cs:fread
0x18013bdad  cmp     rax, rsi
0x18013bdb0  jnz     loc_18013C002
0x18013bdb6  mov     r9, [rbx+8]; Stream
0x18013bdba  mov     r8d, esi; ElementCount
0x18013bdbd  mov     edx, r14d; ElementSize
0x18013bdc0  lea     rcx, [rbp+Buffer]; Buffer
0x18013bdc4  call    cs:fread
0x18013bdca  cmp     rax, rsi
0x18013bdcd  jnz     loc_18013C002
0x18013bdd3  cmp     dword ptr [rbp+Buffer], 3E80h
0x18013bdda  ja      loc_18013BEB7
0x18013bde0  cmp     dword ptr [rbp+Buffer], 10Ch
0x18013bde7  jnz     short loc_18013BE3C
0x18013bde9  mov     ecx, 128h; unsigned __int64
0x18013bdee  cmp     cs:dword_1802B0018, edi
0x18013bdf4  jz      short loc_18013BDFD
0x18013bdf6  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18013bdfb  jmp     short loc_18013BE03
0x18013bdfd  call    cs:malloc
0x18013be03  mov     rsi, rax
0x18013be06  mov     [rbp+var_30], rax
0x18013be0a  test    rax, rax
0x18013be0d  jz      short loc_18013BE37
0x18013be0f  lea     rax, ??_7RWListManager@@6B@; const RWListManager::`vftable'
0x18013be16  mov     [rsi], rax
0x18013be19  mov     [rsi+8], rbx
0x18013be1d  lea     rax, ??_7RWNewListManager@@6B@; const RWNewListManager::`vftable'
0x18013be24  mov     [rsi], rax
0x18013be27  mov     edx, 0Ch
0x18013be2c  mov     rcx, rsi
0x18013be2f  call    sub_18013B888
0x18013be34  nop
0x18013be35  jmp     short loc_18013BE3A
0x18013be37  mov     rsi, rdi
0x18013be3a  jmp     short loc_18013BE97
0x18013be3c  cmp     dword ptr [rbp+Buffer], 5Ch ; '\'
0x18013be40  jnz     loc_18013BFB5
0x18013be46  mov     ecx, 78h ; 'x'; unsigned __int64
0x18013be4b  cmp     cs:dword_1802B0018, edi
0x18013be51  jz      short loc_18013BE5A
0x18013be53  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18013be58  jmp     short loc_18013BE60
0x18013be5a  call    cs:malloc
0x18013be60  mov     rsi, rax
0x18013be63  mov     [rbp+var_30], rax
0x18013be67  test    rax, rax
0x18013be6a  jz      short loc_18013BE94
0x18013be6c  lea     rax, ??_7RWListManager@@6B@; const RWListManager::`vftable'
0x18013be73  mov     [rsi], rax
0x18013be76  mov     [rsi+8], rbx
0x18013be7a  lea     rax, ??_7RWOldListManager@@6B@; const RWOldListManager::`vftable'
0x18013be81  mov     [rsi], rax
0x18013be84  mov     edx, 0Ch
0x18013be89  mov     rcx, rsi
0x18013be8c  call    sub_18013B2E4
0x18013be91  nop
0x18013be92  jmp     short loc_18013BE97
0x18013be94  mov     rsi, rdi
0x18013be97  mov     [rbx+10h], rsi
0x18013be9b  mov     rax, rbx
0x18013be9e  lea     r11, [rsp+50h+var_s0]
0x18013bea3  mov     rbx, [r11+38h]
0x18013bea7  mov     rsi, [r11+40h]
0x18013beab  mov     rsp, r11
0x18013beae  pop     r14
0x18013beb0  pop     r13
0x18013beb2  pop     r12
0x18013beb4  pop     rdi
0x18013beb5  pop     rbp
0x18013beb6  retn
0x18013beb7  mov     rcx, rbx; this
0x18013beba  call    ?Erase@RWFile@@QEAAHXZ; RWFile::Erase(void)
0x18013bebf  test    eax, eax
0x18013bec1  jz      loc_18013BFE7
0x18013bec7  or      dword ptr [r12], 0FFFFFFFFh
0x18013becc  mov     dword ptr [r13+0], 118h
0x18013bed4  mov     dword ptr [rbp+Buffer], 10Ch
0x18013bedb  xor     r8d, r8d; Origin
0x18013bede  xor     edx, edx; Offset
0x18013bee0  mov     rcx, [rbx+8]; Stream
0x18013bee4  call    cs:fseek
0x18013beea  test    eax, eax
0x18013beec  js      loc_18013BFF0
0x18013bef2  mov     eax, [r12]
0x18013bef6  mov     dword ptr [rbp+var_30], eax
0x18013bef9  mov     r9, [rbx+8]; Stream
0x18013befd  mov     r8, rsi; ElementCount
0x18013bf00  mov     rdx, r14; ElementSize
0x18013bf03  lea     rcx, [rbp+var_30]; Buffer
0x18013bf07  call    cs:fwrite
0x18013bf0d  cmp     rax, rsi
0x18013bf10  jnz     loc_18013BFF9
0x18013bf16  mov     eax, [r13+0]
0x18013bf1a  mov     dword ptr [rbp+var_30], eax
0x18013bf1d  mov     r9, [rbx+8]; Stream
0x18013bf21  mov     r8, rsi; ElementCount
0x18013bf24  mov     rdx, r14; ElementSize
0x18013bf27  lea     rcx, [rbp+var_30]; Buffer
0x18013bf2b  call    cs:fwrite
0x18013bf31  cmp     rax, rsi
0x18013bf34  jnz     loc_18013BFF9
0x18013bf3a  mov     eax, dword ptr [rbp+Buffer]
0x18013bf3d  mov     dword ptr [rbp+var_30], eax
0x18013bf40  mov     r9, [rbx+8]; Stream
0x18013bf44  mov     r8, rsi; ElementCount
0x18013bf47  mov     rdx, r14; ElementSize
0x18013bf4a  lea     rcx, [rbp+var_30]; Buffer
0x18013bf4e  call    cs:fwrite
0x18013bf54  cmp     rax, rsi
0x18013bf57  jnz     loc_18013BFF9
0x18013bf5d  mov     ecx, 128h; unsigned __int64
0x18013bf62  cmp     cs:dword_1802B0018, edi
0x18013bf68  jz      short loc_18013BF71
0x18013bf6a  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18013bf6f  jmp     short loc_18013BF77
0x18013bf71  call    cs:malloc
0x18013bf77  mov     [rbp+var_30], rax
0x18013bf7b  test    rax, rax
0x18013bf7e  jz      short loc_18013BF91
0x18013bf80  mov     r8d, esi
0x18013bf83  mov     rdx, rbx
0x18013bf86  mov     rcx, rax
0x18013bf89  call    sub_18013B638
0x18013bf8e  mov     rdi, rax
0x18013bf91  mov     [rbx+10h], rdi
0x18013bf95  jmp     loc_18013BE9B
0x18013bf9a  mov     rcx, rbx; this
0x18013bf9d  call    ?seekErr@RWFileManager@@IEAAXXZ; RWFileManager::seekErr(void)
0x18013bfa3  mov     rcx, rbx; this
0x18013bfa6  call    ?writeErr@RWFileManager@@IEAAXXZ; RWFileManager::writeErr(void)
0x18013bfac  mov     rcx, rbx; this
0x18013bfaf  call    ?seekErr@RWFileManager@@IEAAXXZ; RWFileManager::seekErr(void)
0x18013bfb5  call    ?RWTOOL_FLIST@@YAQEBURWCatMsg@@XZ; RWTOOL_FLIST(void)
0x18013bfba  mov     rdx, rax; struct RWCatMsg *
0x18013bfbd  mov     r9d, dword ptr [rbp+Buffer]
0x18013bfc1  mov     r8d, 10Ch
0x18013bfc7  lea     rcx, [rbp+var_30]; this
0x18013bfcb  call    ??0RWMessage@@QEAA@PEBURWCatMsg@@ZZ; RWMessage::RWMessage(RWCatMsg const *,...)
0x18013bfd0  nop
0x18013bfd1  mov     rdx, rax; struct RWMessage *
0x18013bfd4  lea     rcx, [rbp+var_20]; this
0x18013bfd8  call    ??0RWExternalErr@@QEAA@AEBVRWMessage@@@Z; RWExternalErr::RWExternalErr(RWMessage const &)
0x18013bfdd  nop
0x18013bfde  mov     rcx, rax; struct RWxmsg *
0x18013bfe1  call    ?RWThrow@@YAXAEBVRWxmsg@@@Z; RWThrow(RWxmsg const &)
0x18013bfe7  mov     rcx, rbx; this
0x18013bfea  call    ?seekErr@RWFileManager@@IEAAXXZ; RWFileManager::seekErr(void)
0x18013bff0  mov     rcx, rbx; this
0x18013bff3  call    ?seekErr@RWFileManager@@IEAAXXZ; RWFileManager::seekErr(void)
0x18013bff9  mov     rcx, rbx; this
0x18013bffc  call    ?writeErr@RWFileManager@@IEAAXXZ; RWFileManager::writeErr(void)
0x18013c002  mov     rcx, rbx; this
0x18013c005  call    ?readErr@RWFileManager@@IEAAXXZ; RWFileManager::readErr(void)
```
