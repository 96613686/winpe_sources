# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18000bc80`
- end: `0x18000bcaa`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `42`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000baa0`
- `0x18000beb0`
- `0x180010260`
- `0x1800126e4`
- `0x180012964`
- `0x180013bf4`
- `0x180013d98`

## callees

- `0x18000328c`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>((int)this, (int)a2, a3, 0, 0, retaddr, v4);
}

```

## disassembly

```asm
0x18000bc80  sub     rsp, 48h
0x18000bc84  mov     rax, [rsp+48h]
0x18000bc89  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000bc8e  mov     [rsp+48h+var_20], rax; __int64
0x18000bc93  mov     [rsp+48h+var_28], 0; __int64
0x18000bc9c  xor     r9d, r9d; int
0x18000bc9f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000bca4  nop
0x18000bca5  add     rsp, 48h
0x18000bca9  retn
```
