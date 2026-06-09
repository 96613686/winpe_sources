# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x180007a04`
- end: `0x180007a1d`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `26`
- callee_count: `1`
- tags: ``

## callers

- `0x180005cd0`
- `0x180005d70`
- `0x1800064d4`
- `0x1800065a8`
- `0x1800066cc`
- `0x18000681c`
- `0x18000691c`
- `0x180006bb0`
- `0x180007be0`
- `0x180008a94`
- `0x180008c1c`
- `0x180008d9c`
- `0x18000a1d8`
- `0x18000a2d4`
- `0x18000a3a0`
- `0x18000b6a8`
- `0x18000b7d4`
- `0x18000b89c`
- `0x18000b990`
- `0x18000c234`
- `0x18000c808`
- `0x18000c8f8`
- `0x18000ca20`
- `0x18000e038`
- `0x18000e0e4`
- `0x18000e84c`

## callees

- `0x180005ee0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4,
        int a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v6) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<0>((int)this, (int)a2, a3, (int)a4, v5, retaddr, v6);
}

```

## disassembly

```asm
0x180007a04  sub     rsp, 48h
0x180007a08  mov     rax, [rsp+48h]
0x180007a0d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180007a12  mov     [rsp+48h+var_20], rax; __int64
0x180007a17  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
