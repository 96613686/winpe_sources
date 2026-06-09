# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x18006d510`
- end: `0x18006d52e`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18006cc10`
- `0x18007ca10`
- `0x18007cda0`
- `0x18007d000`
- `0x18007dde0`
- `0x18007e1c0`
- `0x18007e3b0`
- `0x18007ee80`
- `0x18007f280`
- `0x18007f940`

## callees

- `0x18006c480`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x18006d510  sub     rsp, 48h
0x18006d514  mov     rax, [rsp+48h]
0x18006d519  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18006d51e  mov     [rsp+48h+var_20], rax; __int64
0x18006d523  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18006d528  nop
0x18006d529  add     rsp, 48h
0x18006d52d  retn
```
