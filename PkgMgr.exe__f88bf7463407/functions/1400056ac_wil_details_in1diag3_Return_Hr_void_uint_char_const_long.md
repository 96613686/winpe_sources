# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1400056ac`
- end: `0x1400056d3`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `39`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `61`
- callee_count: `1`
- tags: ``

## callers

- `0x140003ff8`
- `0x140004190`
- `0x140004bd4`
- `0x140005280`
- `0x140005ebc`
- `0x140005f40`
- `0x140007524`
- `0x1400089c0`
- `0x140008de8`
- `0x14000903c`
- `0x1400092fc`
- `0x1400098b8`
- `0x140009f08`
- `0x14000a1dc`
- `0x14000aca8`
- `0x14000b454`
- `0x14000baa4`
- `0x14000bdbc`
- `0x14000bf34`
- `0x14000c384`
- `0x14000ca60`
- `0x14000ccac`
- `0x14000d410`
- `0x14000e8f4`
- `0x14000f180`
- `0x140010b3c`
- `0x140010d34`
- `0x140011100`
- `0x1400113d4`
- `0x14001154c`
- `0x140011884`
- `0x140011a4c`
- `0x140011d50`
- `0x140011e8c`
- `0x140012b88`
- `0x140013288`
- `0x140015a08`
- `0x140016328`
- `0x1400165f8`
- `0x140016bc8`
- `0x140016dc8`
- `0x1400170c0`
- `0x140017390`
- `0x140017568`
- `0x140017b80`
- `0x140017eb4`
- `0x1400237c0`
- `0x140023880`
- `0x1400243e8`
- `0x1400244a0`

## callees

- `0x140003480`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-38h]
  wil::details *v5; // [rsp+30h] [rbp-28h]
  __int64 retaddr; // [rsp+58h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x1400056ac  sub     rsp, 58h
0x1400056b0  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400056b9  mov     rax, [rsp+58h]
0x1400056be  mov     dword ptr [rsp+58h+var_28], r9d; wil::details *
0x1400056c3  mov     [rsp+58h+var_30], rax; __int64
0x1400056c8  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400056cd  nop
0x1400056ce  add     rsp, 58h
0x1400056d2  retn
```
