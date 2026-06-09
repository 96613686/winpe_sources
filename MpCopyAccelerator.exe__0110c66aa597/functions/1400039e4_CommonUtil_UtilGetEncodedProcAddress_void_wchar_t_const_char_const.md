# CommonUtil::UtilGetEncodedProcAddress(void * *,wchar_t const *,char const *)

- ea: `0x1400039e4`
- end: `0x140003a21`
- name: `?UtilGetEncodedProcAddress@CommonUtil@@YAJPEAPEAXPEB_WPEBD@Z`
- size: `61`
- prototype: `int(CommonUtil *__hidden this, void **, const wchar_t *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003ed8`

## callees

- `0x1400025b0`
- `0x1400039e4`
- `0x140003de4`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetEncodedProcAddress(
        CommonUtil *this,
        const WCHAR *a2,
        wchar_t *a3,
        const char *a4)
{
  __int64 result; // rax
  __int64 v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  result = CommonUtil::UtilRawGetLoadedProcAddress((CommonUtil *)&v6, a2, a3, 0);
  if ( (int)result >= 0 )
  {
    *(_QWORD *)this = MpEncodeVoidPointer(v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400039e4  push    rbx; bool
0x1400039e6  sub     rsp, 20h
0x1400039ea  mov     rbx, rcx
0x1400039ed  mov     [rsp+28h+arg_18], 0
0x1400039f6  lea     rcx, [rsp+28h+arg_18]; this
0x1400039fb  xor     r9d, r9d; char *
0x1400039fe  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEB_WPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),wchar_t const *,char const *,bool)
0x140003a03  mov     edx, eax
0x140003a05  shr     edx, 1Fh
0x140003a08  test    dl, dl
0x140003a0a  jnz     short loc_140003A1B
0x140003a0c  mov     rcx, [rsp+28h+arg_18]
0x140003a11  call    MpEncodeVoidPointer
0x140003a16  mov     [rbx], rax
0x140003a19  xor     eax, eax
0x140003a1b  add     rsp, 20h
0x140003a1f  pop     rbx
0x140003a20  retn
```
