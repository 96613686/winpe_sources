# AutoDeleteFileStream::~AutoDeleteFileStream(void)

- ea: `0x14000d394`
- end: `0x14000d453`
- name: `??1AutoDeleteFileStream@@UEAA@XZ`
- size: `191`
- prototype: `void __fastcall(AutoDeleteFileStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000d4a0`

## callees

- `0x140001008`
- `0x14000d394`
- `0x140010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000d426`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000d426`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000d3be`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000d3be`

## pseudocode

```c
void __fastcall AutoDeleteFileStream::~AutoDeleteFileStream(AutoDeleteFileStream *this)
{
  char *v2; // rbx
  const WCHAR *v3; // rcx
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  char *v7; // rax
  __int64 v8; // rcx
  char *v9; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &AutoDeleteFileStream::`vftable';
  v2 = (char *)this + 16;
  if ( *((_QWORD *)this + 5) < 8u )
    v3 = (const WCHAR *)((char *)this + 16);
  else
    v3 = *(const WCHAR **)v2;
  if ( !DeleteFileW(v3) && (unsigned int)dword_140017048 > 2 )
  {
    if ( *((_QWORD *)v2 + 3) < 8u )
      v7 = v2;
    else
      v7 = *(char **)v2;
    v9 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v4,
      (unsigned int)word_1400139B2,
      v5,
      v6,
      (__int64)&v9);
  }
  v8 = *((_QWORD *)this + 6);
  if ( v8 )
  {
    *((_QWORD *)this + 6) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  if ( *((_QWORD *)v2 + 3) >= 8u )
    operator delete(*(void **)v2);
  *((_QWORD *)v2 + 3) = 7;
  *((_QWORD *)v2 + 2) = 0;
  *(_WORD *)v2 = 0;
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x14000d394  mov     [rsp+arg_8], rbx
0x14000d399  push    rdi
0x14000d39a  sub     rsp, 30h
0x14000d39e  mov     rdi, rcx
0x14000d3a1  lea     rax, ??_7AutoDeleteFileStream@@6B@; const AutoDeleteFileStream::`vftable'
0x14000d3a8  mov     [rcx], rax
0x14000d3ab  lea     rbx, [rcx+10h]
0x14000d3af  cmp     qword ptr [rbx+18h], 8
0x14000d3b4  jb      short loc_14000D3BB
0x14000d3b6  mov     rcx, [rbx]
0x14000d3b9  jmp     short loc_14000D3BE
0x14000d3bb  mov     rcx, rbx; lpFileName
0x14000d3be  call    cs:__imp_DeleteFileW
0x14000d3c4  test    eax, eax
0x14000d3c6  jnz     short loc_14000D3FE
0x14000d3c8  mov     eax, cs:dword_140017048
0x14000d3ce  cmp     eax, 2
0x14000d3d1  jbe     short loc_14000D3FE
0x14000d3d3  cmp     qword ptr [rbx+18h], 8
0x14000d3d8  jb      short loc_14000D3DF
0x14000d3da  mov     rax, [rbx]
0x14000d3dd  jmp     short loc_14000D3E2
0x14000d3df  mov     rax, rbx
0x14000d3e2  mov     [rsp+38h+arg_0], rax
0x14000d3e7  lea     rax, [rsp+38h+arg_0]
0x14000d3ec  mov     [rsp+38h+var_18], rax
0x14000d3f1  lea     rdx, word_1400139B2
0x14000d3f8  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14000d3fd  nop
0x14000d3fe  mov     rcx, [rdi+30h]
0x14000d402  test    rcx, rcx
0x14000d405  jz      short loc_14000D41C
0x14000d407  mov     qword ptr [rdi+30h], 0
0x14000d40f  mov     rax, [rcx]
0x14000d412  mov     rax, [rax+10h]
0x14000d416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d41b  nop
0x14000d41c  cmp     qword ptr [rbx+18h], 8
0x14000d421  jb      short loc_14000D42C
0x14000d423  mov     rcx, [rbx]
0x14000d426  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000d42c  mov     qword ptr [rbx+18h], 7
0x14000d434  mov     qword ptr [rbx+10h], 0
0x14000d43c  xor     eax, eax
0x14000d43e  mov     [rbx], ax
0x14000d441  mov     dword ptr [rdi+0Ch], 0C0000001h
0x14000d448  mov     rbx, [rsp+38h+arg_8]
0x14000d44d  add     rsp, 30h
0x14000d451  pop     rdi
0x14000d452  retn
```
