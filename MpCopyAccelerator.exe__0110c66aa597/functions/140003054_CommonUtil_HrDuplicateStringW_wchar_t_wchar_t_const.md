# CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)

- ea: `0x140003054`
- end: `0x140003085`
- name: `?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z`
- size: `49`
- prototype: `int(CommonUtil *__hidden this, wchar_t **, const wchar_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000309c`
- `0x140003a24`
- `0x140003bc0`
- `0x140022ac4`
- `0x1400234b0`

## callees

- `0x140003008`
- `0x140010dd0`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrDuplicateStringW(CommonUtil *this, wchar_t **a2, const wchar_t *a3)
{
  size_t v5; // rax

  v5 = wcslen((const wchar_t *)a2);
  return CommonUtil::MpDuplicateBuffer<wchar_t>(this, v5 + 1, a2);
}

```

## disassembly

```asm
0x140003054  mov     [rsp+arg_0], rbx
0x140003059  push    rdi
0x14000305a  sub     rsp, 20h
0x14000305e  mov     rdi, rcx
0x140003061  mov     rbx, rdx
0x140003064  mov     rcx, rdx; String
0x140003067  call    wcslen
0x14000306c  mov     r8, rbx
0x14000306f  mov     rcx, rdi
0x140003072  lea     rdx, [rax+1]
0x140003076  mov     rbx, [rsp+28h+arg_0]
0x14000307b  add     rsp, 20h
0x14000307f  pop     rdi
0x140003080  jmp     ??$MpDuplicateBuffer@_W@CommonUtil@@YAJPEAPEA_W_KPEB_W@Z; CommonUtil::MpDuplicateBuffer<wchar_t>(wchar_t * *,unsigned __int64,wchar_t const *)
```
