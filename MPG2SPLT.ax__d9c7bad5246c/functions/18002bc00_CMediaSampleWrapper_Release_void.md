# CMediaSampleWrapper::Release(void)

- ea: `0x18002bc00`
- end: `0x18002bd08`
- name: `?Release@CMediaSampleWrapper@@UEAAKXZ`
- size: `264`
- prototype: `unsigned int __fastcall(CMediaSampleWrapper *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180006af0`
- `0x18002bc00`
- `0x180034010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18002bcb8`
- `KERNEL32!SetEvent` at `0x18002bcb8`
- `KERNEL32!DeleteCriticalSection` at `0x18002bc36`
- `KERNEL32!DeleteCriticalSection` at `0x18002bc36`
- `KERNEL32!LeaveCriticalSection` at `0x18002bca0`
- `KERNEL32!LeaveCriticalSection` at `0x18002bce1`
- `KERNEL32!LeaveCriticalSection` at `0x18002bca0`
- `KERNEL32!LeaveCriticalSection` at `0x18002bce1`
- `KERNEL32!EnterCriticalSection` at `0x18002bc80`
- `KERNEL32!EnterCriticalSection` at `0x18002bcae`
- `KERNEL32!EnterCriticalSection` at `0x18002bc80`
- `KERNEL32!EnterCriticalSection` at `0x18002bcae`

## pseudocode

```c
__int64 __fastcall CMediaSampleWrapper::Release(CMediaSampleWrapper *this)
{
  __int64 result; // rax
  struct _AMMediaType *v3; // rcx
  __int64 v4; // rdi
  __int64 v5; // rax

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( (_DWORD)result )
  {
    if ( (_DWORD)result != 1 )
      return result;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 16LL))(*((_QWORD *)this + 17));
    *((_QWORD *)this + 17) = 0;
    *((_DWORD *)this + 5) = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    v3 = (struct _AMMediaType *)*((_QWORD *)this + 10);
    if ( v3 )
    {
      DeleteMediaType(v3);
      *((_QWORD *)this + 10) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    v4 = *((_QWORD *)this + 1);
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 56));
    SetEvent(*(HANDLE *)(v4 + 96));
    v5 = *(_QWORD *)(v4 + 32);
    *((_QWORD *)this + 18) = v5;
    *((_QWORD *)this + 19) = v4 + 32;
    *(_QWORD *)(v5 + 8) = (char *)this + 144;
    *(_QWORD *)(v4 + 32) = (char *)this + 144;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 56));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  else if ( this )
  {
    *(_QWORD *)this = &CMediaSampleWrapper::`vftable';
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    operator delete(this, 0xA0u);
  }
  return 0;
}

```

## disassembly

```asm
0x18002bc00  mov     [rsp+arg_0], rbx
0x18002bc05  mov     [rsp+arg_8], rsi
0x18002bc0a  push    rdi
0x18002bc0b  sub     rsp, 20h
0x18002bc0f  mov     rsi, rcx
0x18002bc12  or      eax, 0FFFFFFFFh
0x18002bc15  lock xadd [rcx+10h], eax
0x18002bc1a  sub     eax, 1
0x18002bc1d  jnz     short loc_18002BC4E
0x18002bc1f  test    rcx, rcx
0x18002bc22  jz      loc_18002BCF6
0x18002bc28  lea     rax, ??_7CMediaSampleWrapper@@6B@; const CMediaSampleWrapper::`vftable'
0x18002bc2f  mov     [rcx], rax
0x18002bc32  add     rcx, 60h ; '`'; lpCriticalSection
0x18002bc36  call    cs:__imp_DeleteCriticalSection
0x18002bc3c  mov     edx, 0A0h; unsigned __int64
0x18002bc41  mov     rcx, rsi; void *
0x18002bc44  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002bc49  jmp     loc_18002BCF6
0x18002bc4e  cmp     eax, 1
0x18002bc51  jnz     loc_18002BCF8
0x18002bc57  mov     rcx, [rcx+88h]
0x18002bc5e  mov     rax, [rcx]
0x18002bc61  mov     rax, [rax+10h]
0x18002bc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc6a  lea     rcx, [rsi+60h]; lpCriticalSection
0x18002bc6e  mov     qword ptr [rsi+88h], 0
0x18002bc79  mov     dword ptr [rsi+14h], 0
0x18002bc80  call    cs:__imp_EnterCriticalSection
0x18002bc86  mov     rcx, [rsi+50h]; pv
0x18002bc8a  test    rcx, rcx
0x18002bc8d  jz      short loc_18002BC9C
0x18002bc8f  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x18002bc94  mov     qword ptr [rsi+50h], 0
0x18002bc9c  lea     rcx, [rsi+60h]; lpCriticalSection
0x18002bca0  call    cs:__imp_LeaveCriticalSection
0x18002bca6  mov     rdi, [rsi+8]
0x18002bcaa  lea     rcx, [rdi+38h]; lpCriticalSection
0x18002bcae  call    cs:__imp_EnterCriticalSection
0x18002bcb4  mov     rcx, [rdi+60h]; hEvent
0x18002bcb8  call    cs:__imp_SetEvent
0x18002bcbe  lea     r8, [rdi+20h]
0x18002bcc2  mov     rax, [r8]
0x18002bcc5  lea     rdx, [rsi+90h]
0x18002bccc  mov     [rdx], rax
0x18002bccf  lea     rcx, [rdi+38h]; lpCriticalSection
0x18002bcd3  mov     [rsi+98h], r8
0x18002bcda  mov     [rax+8], rdx
0x18002bcde  mov     [r8], rdx
0x18002bce1  call    cs:__imp_LeaveCriticalSection
0x18002bce7  mov     rax, [rdi]
0x18002bcea  mov     rcx, rdi
0x18002bced  mov     rax, [rax+10h]
0x18002bcf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcf6  xor     eax, eax
0x18002bcf8  mov     rbx, [rsp+28h+arg_0]
0x18002bcfd  mov     rsi, [rsp+28h+arg_8]
0x18002bd02  add     rsp, 20h
0x18002bd06  pop     rdi
0x18002bd07  retn
```
