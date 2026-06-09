# CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)

- ea: `0x140003254`
- end: `0x140003299`
- name: `?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ`
- size: `69`
- prototype: `__int64(CommonUtil *__hidden this, wchar_t **, const wchar_t *, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003bc0`
- `0x140003c50`
- `0x14001d464`
- `0x14001e068`
- `0x1400242c4`

## callees

- `0x14000329c`
- `0x140005c20`

## pseudocode

```c
__int64 CommonUtil::NewSprintfW(CommonUtil *this, wchar_t **a2, const wchar_t *a3, char *a4, ...)
{
  const wchar_t *v5; // [rsp+50h] [rbp+18h] BYREF

  v5 = a3;
  return CommonUtil::NewVSprintfW(this, a2, (const wchar_t *)&v5, a4);
}

```

## disassembly

```asm
0x140003254  mov     r11, rsp
0x140003257  mov     [r11+10h], rdx
0x14000325b  mov     [r11+18h], r8
0x14000325f  mov     [r11+20h], r9
0x140003263  sub     rsp, 38h
0x140003267  mov     rax, cs:__security_cookie
0x14000326e  xor     rax, rsp
0x140003271  mov     [rsp+38h+var_10], rax
0x140003276  lea     r8, [r11+18h]; wchar_t *
0x14000327a  mov     qword ptr [r11-18h], 0
0x140003282  call    ?NewVSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WPEAD@Z; CommonUtil::NewVSprintfW(wchar_t * *,wchar_t const *,char *)
0x140003287  mov     rcx, [rsp+38h+var_10]
0x14000328c  xor     rcx, rsp; StackCookie
0x14000328f  call    __security_check_cookie
0x140003294  add     rsp, 38h
0x140003298  retn
```
