# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x40adfa`
- end: `0x40ae12`
- name: `?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z`
- size: `24`
- prototype: `void __userpurge(int@<ecx>, wil::details::in1diag3 *this, void *, unsigned int, const char *, int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x40aec9`
- `0x40af70`
- `0x40b08b`
- `0x40c3ba`
- `0x40c61e`

## callees

- `0x40bf2a`

## pseudocode

```c
void __userpurge wil::details::in1diag3::Return_Hr(
        int a1@<ecx>,
        wil::details::in1diag3 *this,
        void *a3,
        unsigned int a4,
        const char *a5,
        int a6)
{
  int v6; // [esp-18h] [ebp-18h]
  int v7; // [esp-14h] [ebp-14h]
  int v8; // [esp-10h] [ebp-10h]
  void *retaddr; // [esp+4h] [ebp+4h]

  wil::details::ReportFailure_Hr<1>(v6, v7, v8, retaddr, a3, a1);
}

```

## disassembly

```asm
0x40adfa  mov     edi, edi
0x40adfc  push    ebp
0x40adfd  mov     ebp, esp
0x40adff  push    ecx
0x40ae00  push    [ebp+arg_4]
0x40ae03  push    dword ptr [ebp+4]
0x40ae06  sub     esp, 0Ch
0x40ae09  call    ??$ReportFailure_Hr@$00@details@wil@@YGXPAXIPBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x40ae0e  pop     ebp
0x40ae0f  retn    8
```
