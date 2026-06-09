# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x1800046b4`
- end: `0x180004706`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `82`
- prototype: `int(char *, unsigned __int64, const char *, ...)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ea0`
- `0x180003f10`
- `0x180003f80`
- `0x1800048d0`
- `0x1800089d0`
- `0x1800095a8`
- `0x18000a590`

## callees

- `0x1800046b4`
- `0x180004798`

## pseudocode

```c
HRESULT StringCchPrintfA(char *a1, size_t a2, size_t *a3, ...)
{
  HRESULT result; // eax
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( !a2 )
    return -2147024809;
  if ( a2 <= 0x7FFFFFFF )
    return StringVPrintfWorkerA(a1, a2, a3, (STRSAFE_LPCSTR)a3, va);
  result = -2147024809;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800046b4  mov     [rsp+arg_10], r8
0x1800046b9  mov     qword ptr [rsp+arg_18], r9
0x1800046be  sub     rsp, 48h
0x1800046c2  test    rdx, rdx
0x1800046c5  jz      short loc_1800046F4
0x1800046c7  cmp     rdx, 7FFFFFFFh
0x1800046ce  jbe     short loc_1800046D7
0x1800046d0  mov     eax, 80070057h
0x1800046d5  jmp     short loc_1800046FE
0x1800046d7  lea     rax, [rsp+48h+arg_18]
0x1800046dc  mov     [rsp+48h+var_18], 0
0x1800046e5  mov     r9, r8; pszFormat
0x1800046e8  mov     [rsp+48h+argList], rax; argList
0x1800046ed  call    StringVPrintfWorkerA
0x1800046f2  jmp     short loc_180004701
0x1800046f4  mov     eax, 80070057h
0x1800046f9  test    rdx, rdx
0x1800046fc  jz      short loc_180004701
0x1800046fe  mov     byte ptr [rcx], 0
0x180004701  add     rsp, 48h
0x180004705  retn
```
