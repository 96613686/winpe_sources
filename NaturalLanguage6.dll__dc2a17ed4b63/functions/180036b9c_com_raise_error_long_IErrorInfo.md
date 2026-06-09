# _com_raise_error(long,IErrorInfo *)

- ea: `0x180036b9c`
- end: `0x180036bcf`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `51`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003894`
- `0x180004220`
- `0x180005190`
- `0x180005380`
- `0x180005b50`
- `0x180007a20`
- `0x18000f580`
- `0x180019a50`
- `0x180023ad0`
- `0x1800241a0`
- `0x18002bf50`
- `0x18002c170`
- `0x180036b04`

## callees

- `0x18003ed6c`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(int a1, struct IErrorInfo *a2)
{
  void **v2; // [rsp+20h] [rbp-28h] BYREF
  int v3; // [rsp+28h] [rbp-20h]
  struct IErrorInfo *v4; // [rsp+30h] [rbp-18h]
  __int64 v5; // [rsp+38h] [rbp-10h]

  v2 = &_com_error::`vftable';
  v3 = a1;
  v4 = a2;
  v5 = 0;
  throw (_com_error *)&v2;
}

```

## disassembly

```asm
0x180036b9c  mov     r11, rsp
0x180036b9f  sub     rsp, 48h
0x180036ba3  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180036baa  mov     [r11-28h], rax
0x180036bae  mov     [rsp+48h+var_20], ecx
0x180036bb2  lea     rcx, [r11-28h]; pExceptionObject
0x180036bb6  mov     [r11-18h], rdx
0x180036bba  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180036bc1  mov     qword ptr [r11-10h], 0
0x180036bc9  call    _CxxThrowException_0
```
