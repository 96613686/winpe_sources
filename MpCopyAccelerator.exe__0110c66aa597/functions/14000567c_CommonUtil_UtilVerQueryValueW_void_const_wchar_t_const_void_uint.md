# CommonUtil::UtilVerQueryValueW(void const *,wchar_t const *,void * *,uint *)

- ea: `0x14000567c`
- end: `0x1400056bd`
- name: `?UtilVerQueryValueW@CommonUtil@@YAJPEBXPEB_WPEAPEAXPEAI@Z`
- size: `65`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, const void *, const wchar_t *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003380`

## callees

- `0x14000567c`
- `0x140024c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005691`
- `KERNEL32!GetLastError` at `0x140005691`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilVerQueryValueW(CommonUtil *this, const void *a2, const wchar_t *a3, void **a4)
{
  signed int LastError; // eax
  signed int v5; // edx
  __int64 result; // rax

  if ( ((unsigned int (__fastcall *)(CommonUtil *, const void *, const wchar_t *, void **))off_14003B120[0])(
         this,
         a2,
         a3,
         a4) )
  {
    return 0;
  }
  LastError = GetLastError();
  v5 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v5 = LastError;
  result = 2147944213LL;
  if ( v5 < 0 )
    return (unsigned int)v5;
  return result;
}

```

## disassembly

```asm
0x14000567c  sub     rsp, 38h
0x140005680  mov     rax, cs:off_14003B120
0x140005687  call    cs:__guard_dispatch_icall_fptr
0x14000568d  test    eax, eax
0x14000568f  jnz     short loc_1400056B6
0x140005691  call    cs:__imp_GetLastError
0x140005697  movzx   edx, ax
0x14000569a  or      edx, 80070000h
0x1400056a0  test    eax, eax
0x1400056a2  cmovle  edx, eax
0x1400056a5  mov     ecx, edx
0x1400056a7  shr     ecx, 1Fh
0x1400056aa  mov     eax, 80070715h
0x1400056af  test    cl, cl
0x1400056b1  cmovnz  eax, edx
0x1400056b4  jmp     short loc_1400056B8
0x1400056b6  xor     eax, eax
0x1400056b8  add     rsp, 38h
0x1400056bc  retn
```
