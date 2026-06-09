# common_assert_to_stderr_wchar_t_

- ea: `0x18034551c`
- end: `0x18034566b`
- name: `common_assert_to_stderr_wchar_t_`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1803456a0`

## callees

- `0x18033afc8`
- `0x18034551c`
- `0x18034566c`
- `0x18034568c`
- `0x180345724`
- `0x180346390`
- `0x180346710`
- `0x180347410`

## import_xrefs

- `KERNEL32!GetFileType` at `0x180345576`
- `KERNEL32!GetFileType` at `0x180345576`
- `KERNEL32!GetStdHandle` at `0x180345560`
- `KERNEL32!GetStdHandle` at `0x180345560`
- `KERNEL32!WriteConsoleW` at `0x1803455d5`
- `KERNEL32!WriteConsoleW` at `0x1803455d5`

## pseudocode

```c
void __fastcall __noreturn common_assert_to_stderr_wchar_t_(__int64 a1, __int64 a2, int a3)
{
  char *StdHandle; // rax
  void *v7; // rbx
  __int64 v8; // rax
  FILE *v9; // rax
  FILE *v10; // rax
  int v11; // [rsp+28h] [rbp-D8h]
  DWORD NumberOfCharsWritten; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 assert_format; // [rsp+48h] [rbp-B8h] BYREF
  FILE *v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Buffer[576]; // [rsp+60h] [rbp-A0h] BYREF

  v14 = a1;
  v17 = a2;
  v13 = a3;
  StdHandle = (char *)GetStdHandle(0xFFFFFFF4);
  v7 = StdHandle;
  if ( (unsigned __int64)(StdHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL && GetFileType(StdHandle) == 2 )
  {
    v11 = a3;
    if ( swprintf(Buffer, 0x240u, L"Assertion failed: %Ts, file %Ts, line %d\n", a1, a2, v11) >= 0 )
    {
      v8 = -1;
      do
        ++v8;
      while ( Buffer[v8] );
      NumberOfCharsWritten = 0;
      if ( WriteConsoleW(v7, Buffer, v8, &NumberOfCharsWritten, 0) )
        abort();
    }
  }
  if ( (HIDWORD(_acrt_iob_func(2u)->_base) & 0x4C0) == 0 )
  {
    v9 = _acrt_iob_func(2u);
    setvbuf(v9, 0, 4, 0);
  }
  assert_format = get_assert_format(0);
  v16 = _acrt_iob_func(2u);
  __crt_char_traits<wchar_t>::ftprintf<_iobuf *,wchar_t const *,wchar_t const * const &,wchar_t const * const &,unsigned int const &>(
    (unsigned int)&v16,
    (unsigned int)&assert_format,
    (unsigned int)&v14,
    (unsigned int)&v17,
    (__int64)&v13);
  v10 = _acrt_iob_func(2u);
  fflush(v10);
  abort();
}

```

## disassembly

```asm
0x18034551c  push    rbp
0x18034551e  push    rbx
0x18034551f  push    rsi
0x180345520  push    rdi
0x180345521  push    r14
0x180345523  lea     rbp, [rsp-3F0h]
0x18034552b  sub     rsp, 4F0h
0x180345532  mov     rax, cs:__security_cookie
0x180345539  xor     rax, rsp
0x18034553c  mov     [rbp+410h+var_30], rax
0x180345543  mov     rdi, rcx
0x180345546  mov     [rsp+510h+var_4D0], rcx
0x18034554b  mov     ecx, 0FFFFFFF4h; nStdHandle
0x180345550  mov     [rsp+510h+var_4B8], rdx
0x180345555  mov     r14d, r8d
0x180345558  mov     [rsp+510h+var_4D8], r8d
0x18034555d  mov     rsi, rdx
0x180345560  call    cs:__imp_GetStdHandle
0x180345566  mov     rbx, rax
0x180345569  lea     rcx, [rax-1]
0x18034556d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180345571  ja      short loc_1803455E5
0x180345573  mov     rcx, rax; hFile
0x180345576  call    cs:__imp_GetFileType
0x18034557c  cmp     eax, 2
0x18034557f  jnz     short loc_1803455E5
0x180345581  mov     [rsp+510h+var_4E8], r14d
0x180345586  lea     r8, aAssertionFaile
0x18034558d  mov     r9, rdi
0x180345590  mov     [rsp+510h+lpReserved], rsi
0x180345595  mov     edx, 240h; BufferCount
0x18034559a  lea     rcx, [rsp+510h+Buffer]; Buffer
0x18034559f  call    swprintf
0x1803455a4  xor     edi, edi
0x1803455a6  test    eax, eax
0x1803455a8  js      short loc_1803455E5
0x1803455aa  lea     rcx, [rsp+510h+Buffer]
0x1803455af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1803455b3  inc     rax
0x1803455b6  cmp     [rcx+rax*2], di
0x1803455ba  jnz     short loc_1803455B3
0x1803455bc  lea     r9, [rsp+510h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x1803455c1  mov     [rsp+510h+NumberOfCharsWritten], edi
0x1803455c5  mov     r8d, eax; nNumberOfCharsToWrite
0x1803455c8  mov     [rsp+510h+lpReserved], rdi; lpReserved
0x1803455cd  lea     rdx, [rsp+510h+Buffer]; lpBuffer
0x1803455d2  mov     rcx, rbx; hConsoleOutput
0x1803455d5  call    cs:__imp_WriteConsoleW
0x1803455db  test    eax, eax
0x1803455dd  jz      short loc_1803455E5
0x1803455df  call    abort
0x1803455e5  mov     ecx, 2; Ix
0x1803455ea  call    __acrt_iob_func
0x1803455ef  mov     ecx, [rax+14h]
0x1803455f2  test    ecx, 4C0h
0x1803455f8  jnz     short loc_180345615
0x1803455fa  mov     ecx, 2; Ix
0x1803455ff  call    __acrt_iob_func
0x180345604  xor     r9d, r9d; Size
0x180345607  mov     rcx, rax; Stream
0x18034560a  xor     edx, edx; Buffer
0x18034560c  lea     r8d, [r9+4]; Mode
0x180345610  call    setvbuf
0x180345615  xor     ecx, ecx
0x180345617  call    get_assert_format
0x18034561c  mov     ecx, 2; Ix
0x180345621  mov     [rsp+510h+var_4C8], rax
0x180345626  call    __acrt_iob_func
0x18034562b  mov     [rsp+510h+var_4C0], rax
0x180345630  lea     r9, [rsp+510h+var_4B8]
0x180345635  lea     rax, [rsp+510h+var_4D8]
0x18034563a  lea     r8, [rsp+510h+var_4D0]
0x18034563f  mov     [rsp+510h+lpReserved], rax
0x180345644  lea     rdx, [rsp+510h+var_4C8]
0x180345649  lea     rcx, [rsp+510h+var_4C0]
0x18034564e  call    ??$ftprintf@PEAU_iobuf@@PEB_WAEBQEB_WAEBQEB_WAEBI@?$__crt_char_traits@_W@@SAH$$QEAPEAU_iobuf@@$$QEAPEB_WAEBQEB_W2AEBI@Z
0x180345653  mov     ecx, 2; Ix
0x180345658  call    __acrt_iob_func
0x18034565d  mov     rcx, rax; Stream
0x180345660  call    fflush
0x180345665  call    abort
```
