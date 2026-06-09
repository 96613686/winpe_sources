# ErrorRecord::SetInternalWinSATErrorRecord(char const *,ulong,ushort const *)

- ea: `0x18001afa8`
- end: `0x18001b05f`
- name: `?SetInternalWinSATErrorRecord@ErrorRecord@@QEAAXPEBDKPEBG@Z`
- size: `183`
- prototype: `void(ErrorRecord *__hidden this, const char *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001b5d8`

## callees

- `0x18001ae60`
- `0x18001aef4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b00e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b024`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b038`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b00e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b024`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b038`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001afc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001afc9`

## pseudocode

```c
void __fastcall ErrorRecord::SetInternalWinSATErrorRecord(
        ErrorRecord *this,
        const char *a2,
        int a3,
        const unsigned __int16 *a4)
{
  DWORD CurrentThreadId; // eax
  unsigned __int64 v9; // r8
  void *v10; // rcx
  void *v11; // rcx

  CurrentThreadId = GetCurrentThreadId();
  *((_DWORD *)this + 2) = -1;
  *(_DWORD *)this = CurrentThreadId;
  *((_BYTE *)this + 4) = 1;
  *((_DWORD *)this + 3) = -2147467259;
  *((_DWORD *)this + 6) = a3;
  ErrorRecord::MakeDeepStringCopy((char **)this + 2, a2, v9);
  ErrorRecord::MakeDeepStringCopy((unsigned __int16 **)this + 4, a4, 0xFFFFFFFFFFFFFFFFuLL);
  operator delete[](*((void **)this + 5));
  v10 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 5) = 0;
  operator delete[](v10);
  v11 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 6) = 0;
  operator delete[](v11);
  *((_QWORD *)this + 7) = 0;
}

```

## disassembly

```asm
0x18001afa8  mov     [rsp+arg_0], rbx
0x18001afad  mov     [rsp+arg_8], rsi
0x18001afb2  mov     [rsp+arg_10], rdi
0x18001afb7  push    r14
0x18001afb9  sub     rsp, 20h
0x18001afbd  mov     rsi, r9
0x18001afc0  mov     ebx, r8d
0x18001afc3  mov     rdi, rdx
0x18001afc6  mov     r14, rcx
0x18001afc9  call    cs:__imp_GetCurrentThreadId
0x18001afd0  nop     dword ptr [rax+rax+00h]
0x18001afd5  or      dword ptr [r14+8], 0FFFFFFFFh
0x18001afda  lea     rcx, [r14+10h]; char **
0x18001afde  mov     rdx, rdi; char *
0x18001afe1  mov     [r14], eax
0x18001afe4  mov     byte ptr [r14+4], 1
0x18001afe9  mov     dword ptr [r14+0Ch], 80004005h
0x18001aff1  mov     [r14+18h], ebx
0x18001aff5  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEADPEBD_K@Z; ErrorRecord::MakeDeepStringCopy(char * &,char const *,unsigned __int64)
0x18001affa  lea     rcx, [r14+20h]; unsigned __int16 **
0x18001affe  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x18001b002  mov     rdx, rsi; unsigned __int16 *
0x18001b005  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEAGPEBG_K@Z; ErrorRecord::MakeDeepStringCopy(ushort * &,ushort const *,unsigned __int64)
0x18001b00a  mov     rcx, [r14+28h]
0x18001b00e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001b015  nop     dword ptr [rax+rax+00h]
0x18001b01a  mov     rcx, [r14+30h]
0x18001b01e  xor     ebx, ebx
0x18001b020  mov     [r14+28h], rbx
0x18001b024  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001b02b  nop     dword ptr [rax+rax+00h]
0x18001b030  mov     rcx, [r14+38h]
0x18001b034  mov     [r14+30h], rbx
0x18001b038  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001b03f  nop     dword ptr [rax+rax+00h]
0x18001b044  mov     rsi, [rsp+28h+arg_8]
0x18001b049  mov     rdi, [rsp+28h+arg_10]
0x18001b04e  mov     [r14+38h], rbx
0x18001b052  mov     rbx, [rsp+28h+arg_0]
0x18001b057  add     rsp, 20h
0x18001b05b  pop     r14
0x18001b05d  retn
```
