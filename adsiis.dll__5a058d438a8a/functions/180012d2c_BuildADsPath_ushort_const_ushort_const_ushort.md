# BuildADsPath(ushort const *,ushort const *,ushort * *)

- ea: `0x180012d2c`
- end: `0x180012e64`
- name: `?BuildADsPath@@YAJPEBG0PEAPEAG@Z`
- size: `312`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800148a0`

## callees

- `0x180012d2c`
- `0x18001beb8`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180012dd5`
- `msvcrt!swprintf_s` at `0x180012dd5`
- `msvcrt!wcscat_s` at `0x180012e10`
- `msvcrt!wcscat_s` at `0x180012e1f`
- `msvcrt!wcscat_s` at `0x180012e10`
- `msvcrt!wcscat_s` at `0x180012e1f`
- `msvcrt!wcscpy_s` at `0x180012de4`
- `msvcrt!wcscpy_s` at `0x180012de4`
- `msvcrt!_wcsicmp` at `0x180012d61`
- `msvcrt!_wcsicmp` at `0x180012df2`
- `msvcrt!_wcsicmp` at `0x180012d61`
- `msvcrt!_wcsicmp` at `0x180012df2`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180012da5`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180012da5`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180012e35`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180012e35`

## pseudocode

```c
__int64 __fastcall BuildADsPath(wchar_t *Source, wchar_t *a2, unsigned __int16 **a3)
{
  __int64 v7; // rax
  __int64 v8; // rcx
  rsize_t v9; // rbx
  wchar_t *v10; // rdi
  int v11; // eax
  const wchar_t *v12; // r8
  unsigned int v13; // ebx
  wchar_t Buffer[264]; // [rsp+20h] [rbp-248h] BYREF

  if ( !_wcsicmp(Source, L"ADs:") )
    return ADsAllocString(a2, a3);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( Source[v8] );
  do
    ++v7;
  while ( a2[v7] );
  v9 = (unsigned int)(v7 + v8 + 262);
  v10 = (wchar_t *)AllocADsMem(2 * (int)v9);
  if ( !v10 )
    return 2147942414LL;
  swprintf_s(Buffer, 0x104u, L"%s:", L"IIS");
  wcscpy_s(v10, v9, Source);
  v11 = _wcsicmp(v10, Buffer);
  v12 = L"/";
  if ( !v11 )
    v12 = L"//";
  wcscat_s(v10, v9, v12);
  wcscat_s(v10, v9, a2);
  v13 = ADsAllocString(v10, a3);
  FreeADsMem(v10);
  return v13;
}

```

## disassembly

```asm
0x180012d2c  mov     [rsp+arg_18], rbx
0x180012d31  push    rbp
0x180012d32  push    rsi
0x180012d33  push    rdi
0x180012d34  push    r14
0x180012d36  push    r15
0x180012d38  sub     rsp, 240h
0x180012d3f  mov     rax, cs:__security_cookie
0x180012d46  xor     rax, rsp
0x180012d49  mov     [rsp+268h+var_38], rax
0x180012d51  mov     rsi, rdx
0x180012d54  mov     r14, r8
0x180012d57  lea     rdx, aAds; "ADs:"
0x180012d5e  mov     rbp, rcx
0x180012d61  call    cs:__imp__wcsicmp
0x180012d67  xor     r15d, r15d
0x180012d6a  test    eax, eax
0x180012d6c  jnz     short loc_180012D7E
0x180012d6e  mov     rdx, r14
0x180012d71  mov     rcx, rsi
0x180012d74  call    ADsAllocString
0x180012d79  jmp     loc_180012E3D
0x180012d7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012d82  mov     rcx, rax
0x180012d85  inc     rcx
0x180012d88  cmp     [rbp+rcx*2+0], r15w
0x180012d8e  jnz     short loc_180012D85
0x180012d90  inc     rax
0x180012d93  cmp     [rsi+rax*2], r15w
0x180012d98  jnz     short loc_180012D90
0x180012d9a  lea     ebx, [rcx+106h]
0x180012da0  add     ebx, eax
0x180012da2  lea     ecx, [rbx+rbx]; cb
0x180012da5  call    cs:__imp_AllocADsMem
0x180012dab  mov     rdi, rax
0x180012dae  test    rax, rax
0x180012db1  jnz     short loc_180012DBD
0x180012db3  mov     eax, 8007000Eh
0x180012db8  jmp     loc_180012E3D
0x180012dbd  lea     r9, aIis; "IIS"
0x180012dc4  mov     edx, 104h; BufferCount
0x180012dc9  lea     r8, aS_0; "%s:"
0x180012dd0  lea     rcx, [rsp+268h+Buffer]; Buffer
0x180012dd5  call    cs:__imp_swprintf_s
0x180012ddb  mov     r8, rbp; Source
0x180012dde  mov     rdx, rbx; SizeInWords
0x180012de1  mov     rcx, rdi; Destination
0x180012de4  call    cs:__imp_wcscpy_s
0x180012dea  lea     rdx, [rsp+268h+Buffer]; String2
0x180012def  mov     rcx, rdi; String1
0x180012df2  call    cs:__imp__wcsicmp
0x180012df8  mov     rdx, rbx; SizeInWords
0x180012dfb  lea     r8, Source; "/"
0x180012e02  mov     rcx, rdi; Destination
0x180012e05  test    eax, eax
0x180012e07  jnz     short loc_180012E10
0x180012e09  lea     r8, asc_1800212C8; "//"
0x180012e10  call    cs:__imp_wcscat_s
0x180012e16  mov     r8, rsi; Source
0x180012e19  mov     rdx, rbx; SizeInWords
0x180012e1c  mov     rcx, rdi; Destination
0x180012e1f  call    cs:__imp_wcscat_s
0x180012e25  mov     rdx, r14
0x180012e28  mov     rcx, rdi
0x180012e2b  call    ADsAllocString
0x180012e30  mov     rcx, rdi; pMem
0x180012e33  mov     ebx, eax
0x180012e35  call    cs:__imp_FreeADsMem
0x180012e3b  mov     eax, ebx
0x180012e3d  mov     rcx, [rsp+268h+var_38]
0x180012e45  xor     rcx, rsp; StackCookie
0x180012e48  call    __security_check_cookie
0x180012e4d  mov     rbx, [rsp+268h+arg_18]
0x180012e55  add     rsp, 240h
0x180012e5c  pop     r15
0x180012e5e  pop     r14
0x180012e60  pop     rdi
0x180012e61  pop     rsi
0x180012e62  pop     rbp
0x180012e63  retn
```
