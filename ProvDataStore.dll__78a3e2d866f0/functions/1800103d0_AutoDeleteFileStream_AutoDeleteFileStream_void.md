# AutoDeleteFileStream::~AutoDeleteFileStream(void)

- ea: `0x1800103d0`
- end: `0x18001049c`
- name: `??1AutoDeleteFileStream@@UEAA@XZ`
- size: `204`
- prototype: `void __fastcall(AutoDeleteFileStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800104c0`

## callees

- `0x18000108c`
- `0x1800103d0`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001046f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001046f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800103fa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800103fa`

## pseudocode

```c
void __fastcall AutoDeleteFileStream::~AutoDeleteFileStream(AutoDeleteFileStream *this)
{
  char *v2; // rbx
  const WCHAR *v3; // rcx
  char *v4; // rax
  __int64 v5; // rcx
  char *v6; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &AutoDeleteFileStream::`vftable';
  v2 = (char *)this + 16;
  if ( *((_QWORD *)this + 5) < 8u )
    v3 = (const WCHAR *)((char *)this + 16);
  else
    v3 = *(const WCHAR **)v2;
  if ( !DeleteFileW(v3) && (unsigned int)dword_180019000 > 2 )
  {
    if ( *((_QWORD *)v2 + 3) < 8u )
      v4 = v2;
    else
      v4 = *(char **)v2;
    v6 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_180019000,
      (unsigned int)&byte_1800158DF,
      0,
      0,
      (__int64)&v6);
  }
  v5 = *((_QWORD *)this + 6);
  if ( v5 )
  {
    *((_QWORD *)this + 6) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
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
0x1800103d0  mov     [rsp+arg_8], rbx
0x1800103d5  push    rdi
0x1800103d6  sub     rsp, 30h
0x1800103da  mov     rdi, rcx
0x1800103dd  lea     rax, ??_7AutoDeleteFileStream@@6B@; const AutoDeleteFileStream::`vftable'
0x1800103e4  mov     [rcx], rax
0x1800103e7  lea     rbx, [rcx+10h]
0x1800103eb  cmp     qword ptr [rbx+18h], 8
0x1800103f0  jb      short loc_1800103F7
0x1800103f2  mov     rcx, [rbx]
0x1800103f5  jmp     short loc_1800103FA
0x1800103f7  mov     rcx, rbx; lpFileName
0x1800103fa  call    cs:__imp_DeleteFileW
0x180010400  test    eax, eax
0x180010402  jnz     short loc_180010447
0x180010404  mov     eax, cs:dword_180019000
0x18001040a  cmp     eax, 2
0x18001040d  jbe     short loc_180010447
0x18001040f  cmp     qword ptr [rbx+18h], 8
0x180010414  jb      short loc_18001041B
0x180010416  mov     rax, [rbx]
0x180010419  jmp     short loc_18001041E
0x18001041b  mov     rax, rbx
0x18001041e  mov     [rsp+38h+arg_0], rax
0x180010423  lea     rax, [rsp+38h+arg_0]
0x180010428  mov     [rsp+38h+var_18], rax
0x18001042d  xor     r9d, r9d
0x180010430  xor     r8d, r8d
0x180010433  lea     rdx, byte_1800158DF
0x18001043a  lea     rcx, dword_180019000
0x180010441  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180010446  nop
0x180010447  mov     rcx, [rdi+30h]
0x18001044b  test    rcx, rcx
0x18001044e  jz      short loc_180010465
0x180010450  mov     qword ptr [rdi+30h], 0
0x180010458  mov     rax, [rcx]
0x18001045b  mov     rax, [rax+10h]
0x18001045f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010464  nop
0x180010465  cmp     qword ptr [rbx+18h], 8
0x18001046a  jb      short loc_180010475
0x18001046c  mov     rcx, [rbx]
0x18001046f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010475  mov     qword ptr [rbx+18h], 7
0x18001047d  mov     qword ptr [rbx+10h], 0
0x180010485  xor     eax, eax
0x180010487  mov     [rbx], ax
0x18001048a  mov     dword ptr [rdi+0Ch], 0C0000001h
0x180010491  mov     rbx, [rsp+38h+arg_8]
0x180010496  add     rsp, 30h
0x18001049a  pop     rdi
0x18001049b  retn
```
