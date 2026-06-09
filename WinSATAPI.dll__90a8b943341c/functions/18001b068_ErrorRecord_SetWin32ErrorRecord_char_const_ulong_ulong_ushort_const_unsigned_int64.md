# ErrorRecord::SetWin32ErrorRecord(char const *,ulong,ulong,ushort const *,unsigned __int64)

- ea: `0x18001b068`
- end: `0x18001b115`
- name: `?SetWin32ErrorRecord@ErrorRecord@@QEAAXPEBDKKPEBG_K@Z`
- size: `173`
- prototype: `void(ErrorRecord *__hidden this, const char *, unsigned int, unsigned int, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001b790`

## callees

- `0x18001a92c`
- `0x18001ae60`
- `0x18001aef4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b0d8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b0ed`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b0d8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b0ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b089`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b089`

## pseudocode

```c
void __fastcall ErrorRecord::SetWin32ErrorRecord(
        ErrorRecord *this,
        const char *a2,
        int a3,
        DWORD a4,
        unsigned __int16 *a5,
        unsigned __int64 a6)
{
  DWORD CurrentThreadId; // eax
  unsigned __int64 v11; // r8
  void *v12; // rcx

  CurrentThreadId = GetCurrentThreadId();
  *((_DWORD *)this + 3) = 0;
  *(_DWORD *)this = CurrentThreadId;
  *((_BYTE *)this + 4) = 1;
  *((_DWORD *)this + 2) = a4;
  *((_DWORD *)this + 6) = a3;
  ErrorRecord::MakeDeepStringCopy((char **)this + 2, a2, v11);
  *((_QWORD *)this + 4) = GetErrorMessage<unsigned short>(a4);
  ErrorRecord::MakeDeepStringCopy((unsigned __int16 **)this + 5, a5, a6);
  operator delete[](*((void **)this + 6));
  v12 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 6) = 0;
  operator delete[](v12);
  *((_QWORD *)this + 7) = 0;
}

```

## disassembly

```asm
0x18001b068  mov     [rsp+arg_0], rbx
0x18001b06d  mov     [rsp+arg_8], rsi
0x18001b072  mov     [rsp+arg_10], rdi
0x18001b077  push    r14
0x18001b079  sub     rsp, 20h
0x18001b07d  mov     esi, r9d
0x18001b080  mov     ebx, r8d
0x18001b083  mov     rdi, rdx
0x18001b086  mov     r14, rcx
0x18001b089  call    cs:__imp_GetCurrentThreadId
0x18001b090  nop     dword ptr [rax+rax+00h]
0x18001b095  and     dword ptr [r14+0Ch], 0
0x18001b09a  lea     rcx, [r14+10h]; char **
0x18001b09e  mov     rdx, rdi; char *
0x18001b0a1  mov     [r14], eax
0x18001b0a4  mov     byte ptr [r14+4], 1
0x18001b0a9  mov     [r14+8], esi
0x18001b0ad  mov     [r14+18h], ebx
0x18001b0b1  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEADPEBD_K@Z; ErrorRecord::MakeDeepStringCopy(char * &,char const *,unsigned __int64)
0x18001b0b6  mov     ecx, esi; dwMessageId
0x18001b0b8  call    ??$GetErrorMessage@G@@YAPEAGK@Z; GetErrorMessage<ushort>(ulong)
0x18001b0bd  mov     r8, [rsp+28h+arg_28]; unsigned __int64
0x18001b0c2  lea     rcx, [r14+28h]; unsigned __int16 **
0x18001b0c6  mov     rdx, [rsp+28h+arg_20]; unsigned __int16 *
0x18001b0cb  mov     [r14+20h], rax
0x18001b0cf  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEAGPEBG_K@Z; ErrorRecord::MakeDeepStringCopy(ushort * &,ushort const *,unsigned __int64)
0x18001b0d4  mov     rcx, [r14+30h]
0x18001b0d8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001b0df  nop     dword ptr [rax+rax+00h]
0x18001b0e4  mov     rcx, [r14+38h]
0x18001b0e8  and     qword ptr [r14+30h], 0
0x18001b0ed  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001b0f4  nop     dword ptr [rax+rax+00h]
0x18001b0f9  and     qword ptr [r14+38h], 0
0x18001b0fe  mov     rbx, [rsp+28h+arg_0]
0x18001b103  mov     rsi, [rsp+28h+arg_8]
0x18001b108  mov     rdi, [rsp+28h+arg_10]
0x18001b10d  add     rsp, 20h
0x18001b111  pop     r14
0x18001b113  retn
```
