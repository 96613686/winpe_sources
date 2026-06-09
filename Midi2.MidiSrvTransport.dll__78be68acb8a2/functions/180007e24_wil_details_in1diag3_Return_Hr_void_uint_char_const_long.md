# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180007e24`
- end: `0x180007e42`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `51`
- callee_count: `1`
- tags: ``

## callers

- `0x180004038`
- `0x180004fa0`
- `0x180005fa4`
- `0x18000893c`
- `0x18000aa80`
- `0x18000b5f0`
- `0x18000b7f0`
- `0x18000b8c0`
- `0x18000bbb0`
- `0x18000bcb0`
- `0x18000bfc0`
- `0x18000c090`
- `0x18000c170`
- `0x18000c250`
- `0x18000c3b0`
- `0x18000c480`
- `0x18000c570`
- `0x18000c630`
- `0x18000c6d0`
- `0x18000c830`
- `0x18000c8d0`
- `0x18000c9a0`
- `0x18000d504`
- `0x18000d6d0`
- `0x18000d748`
- `0x18000d8b0`
- `0x18000f144`
- `0x180010094`
- `0x180010260`
- `0x180011cac`
- `0x180011d1c`
- `0x180011dd0`
- `0x180011e8c`
- `0x180011f28`
- `0x180011fc8`
- `0x180012064`
- `0x180012124`
- `0x1800121c4`
- `0x180012384`
- `0x180012448`
- `0x180012574`
- `0x180012610`
- `0x1800126e4`
- `0x180012830`
- `0x180012964`
- `0x180012b04`
- `0x180013730`
- `0x18001389c`
- `0x1800138f8`
- `0x180013a3c`

## callees

- `0x18000323c`

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
0x180007e24  sub     rsp, 48h
0x180007e28  mov     rax, [rsp+48h]
0x180007e2d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180007e32  mov     [rsp+48h+var_20], rax; __int64
0x180007e37  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007e3c  nop
0x180007e3d  add     rsp, 48h
0x180007e41  retn
```
