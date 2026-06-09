# StorageReserveHelper::Internal::GetHandle(void *,unsigned __int64,void * *)

- ea: `0x18002d12c`
- end: `0x18002d1ae`
- name: `?GetHandle@Internal@StorageReserveHelper@@YAJPEAX_KPEAPEAX@Z`
- size: `130`
- prototype: `__int64 __fastcall(StorageReserveHelper::Internal *this, unsigned __int64, _QWORD *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d494`
- `0x18002de04`

## callees

- `0x180003870`
- `0x18000a0cc`
- `0x18002d12c`

## import_xrefs

- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x18002d172`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x18002d172`

## pseudocode

```c
__int64 __fastcall StorageReserveHelper::Internal::GetHandle(
        StorageReserveHelper::Internal *this,
        unsigned __int64 a2,
        _QWORD *a3,
        void **a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  struct FILE_ID_DESCRIPTOR v8; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8.8 = (union FILE_ID_DESCRIPTOR::$937871D590D7CF78B637FB7A33219D36)a2;
  *(_QWORD *)&v8.dwSize = 24;
  v5 = OpenFileById(this, &v8, 0x100180u, 7u, 0, 0x80u);
  *a3 = v5;
  if ( v5 == (HANDLE)-1LL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x91,
             (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
             v6);
  else
    return 0;
}

```

## disassembly

```asm
0x18002d12c  mov     r11, rsp
0x18002d12f  push    rbx
0x18002d130  sub     rsp, 50h
0x18002d134  mov     rax, cs:__security_cookie
0x18002d13b  xor     rax, rsp
0x18002d13e  mov     [rsp+58h+var_10], rax
0x18002d143  xor     eax, eax
0x18002d145  mov     [r11-20h], rdx
0x18002d149  mov     rbx, r8
0x18002d14c  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002d154  mov     r8d, 100180h; dwDesiredAccess
0x18002d15a  mov     [r11-18h], rax
0x18002d15e  lea     rdx, [r11-28h]; lpFileId
0x18002d162  mov     qword ptr [r11-28h], 18h
0x18002d16a  lea     r9d, [rax+7]; dwShareMode
0x18002d16e  mov     [r11-38h], rax
0x18002d172  call    cs:__imp_OpenFileById
0x18002d178  mov     [rbx], rax
0x18002d17b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d17f  jnz     short loc_18002D199
0x18002d181  mov     rcx, [rsp+58h]; this
0x18002d186  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002d18d  mov     edx, 91h; void *
0x18002d192  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d197  jmp     short loc_18002D19B
0x18002d199  xor     eax, eax
0x18002d19b  mov     rcx, [rsp+58h+var_10]
0x18002d1a0  xor     rcx, rsp; StackCookie
0x18002d1a3  call    __security_check_cookie
0x18002d1a8  add     rsp, 50h
0x18002d1ac  pop     rbx
0x18002d1ad  retn
```
