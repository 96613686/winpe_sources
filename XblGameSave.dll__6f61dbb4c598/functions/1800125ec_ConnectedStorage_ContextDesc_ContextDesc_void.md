# ConnectedStorage::ContextDesc::~ContextDesc(void)

- ea: `0x1800125ec`
- end: `0x180012653`
- name: `??1ContextDesc@ConnectedStorage@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(ConnectedStorage::ContextDesc *__hidden this)`
- caller_count: `139`
- callee_count: `0`
- tags: ``

## callers

- `0x180011e7c`
- `0x1800126f4`
- `0x18001278c`
- `0x18001eec8`
- `0x18001fac4`
- `0x18001fcd0`
- `0x180021dd0`
- `0x180022210`
- `0x180022630`
- `0x180022e30`
- `0x1800238b0`
- `0x180023e80`
- `0x180025610`
- `0x18002f328`
- `0x18002f458`
- `0x18002f588`
- `0x18002f6b8`
- `0x18002f9c0`
- `0x18003089c`
- `0x180031098`
- `0x18003116c`
- `0x1800311a0`
- `0x180031338`
- `0x1800318bc`
- `0x180031efc`
- `0x180032918`
- `0x180032a40`
- `0x180032c7c`
- `0x180032f64`
- `0x18003365c`
- `0x18003373c`
- `0x1800341a4`
- `0x180034294`
- `0x1800343b8`
- `0x1800344b0`
- `0x180034dc8`
- `0x180039824`
- `0x18003a3a0`
- `0x18003a510`
- `0x18003a590`
- `0x18003a610`
- `0x18003a6a0`
- `0x18003a720`
- `0x18003a890`
- `0x18003a950`
- `0x18003a9d0`
- `0x18003eb74`
- `0x18003eee0`
- `0x18003ef24`
- `0x18003ef9c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001260b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001261d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001262f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012640`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001260b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001261d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001262f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012640`

## pseudocode

```c
void __fastcall ConnectedStorage::ContextDesc::~ContextDesc(HSTRING *this)
{
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[2]);
  this[2] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x1800125ec  push    rbx
0x1800125ee  sub     rsp, 20h
0x1800125f2  mov     rbx, rcx
0x1800125f5  mov     rcx, [rcx+20h]; string
0x1800125f9  call    cs:__imp_WindowsDeleteString
0x1800125ff  mov     qword ptr [rbx+20h], 0
0x180012607  mov     rcx, [rbx+18h]; string
0x18001260b  call    cs:__imp_WindowsDeleteString
0x180012611  mov     qword ptr [rbx+18h], 0
0x180012619  mov     rcx, [rbx+10h]; string
0x18001261d  call    cs:__imp_WindowsDeleteString
0x180012623  mov     qword ptr [rbx+10h], 0
0x18001262b  mov     rcx, [rbx+8]; string
0x18001262f  call    cs:__imp_WindowsDeleteString
0x180012635  mov     qword ptr [rbx+8], 0
0x18001263d  mov     rcx, [rbx]; string
0x180012640  call    cs:__imp_WindowsDeleteString
0x180012646  mov     qword ptr [rbx], 0
0x18001264d  add     rsp, 20h
0x180012651  pop     rbx
0x180012652  retn
```
