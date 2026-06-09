# BinXmlReader::~BinXmlReader(void)

- ea: `0x18000b95c`
- end: `0x18000b9da`
- name: `??1BinXmlReader@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(BinXmlReader *__hidden this)`
- caller_count: `14`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180001568`
- `0x1800071b0`
- `0x180007fb8`
- `0x180017864`
- `0x180026e30`
- `0x180027510`
- `0x1800303fc`
- `0x180039050`
- `0x180039430`
- `0x18003957c`
- `0x18003a09d`
- `0x18003aba5`
- `0x18003ac4f`
- `0x18003adb0`

## callees

- `0x18000a100`
- `0x18000b95c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b984`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b984`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b992`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b992`

## pseudocode

```c
void __fastcall BinXmlReader::~BinXmlReader(BinXmlReader *this)
{
  bool v1; // zf
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  void *v5; // rcx
  void *v6; // rcx

  v1 = *((_BYTE *)this + 144) == 0;
  *((_QWORD *)this + 15) = &Buffer::`vftable';
  if ( !v1 )
  {
    v3 = (void *)*((_QWORD *)this + 16);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
  if ( !*((_BYTE *)this + 116) )
    operator delete(*((void **)this + 13));
  v5 = (void *)*((_QWORD *)this + 8);
  if ( v5 != (void *)-1LL )
  {
    *((_QWORD *)this + 9) = v5;
    operator delete(v5);
  }
  v6 = (void *)*((_QWORD *)this + 5);
  if ( v6 != (void *)-1LL )
  {
    *((_QWORD *)this + 6) = v6;
    operator delete(v6);
  }
}

```

## disassembly

```asm
0x18000b95c  mov     [rsp+arg_0], rbx
0x18000b961  push    rdi
0x18000b962  sub     rsp, 20h
0x18000b966  cmp     byte ptr [rcx+90h], 0
0x18000b96d  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x18000b974  mov     [rcx+78h], rax
0x18000b978  mov     rdi, rcx
0x18000b97b  jz      short loc_18000B998
0x18000b97d  mov     rbx, [rcx+80h]
0x18000b984  call    cs:__imp_GetProcessHeap
0x18000b98a  mov     r8, rbx; lpMem
0x18000b98d  xor     edx, edx; dwFlags
0x18000b98f  mov     rcx, rax; hHeap
0x18000b992  call    cs:__imp_HeapFree
0x18000b998  cmp     byte ptr [rdi+74h], 0
0x18000b99c  jz      short loc_18000B9CF
0x18000b99e  mov     rcx, [rdi+40h]; void *
0x18000b9a2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b9a6  jz      short loc_18000B9B1
0x18000b9a8  mov     [rdi+48h], rcx
0x18000b9ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b9b1  mov     rcx, [rdi+28h]; void *
0x18000b9b5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b9b9  jz      short loc_18000B9C4
0x18000b9bb  mov     [rdi+30h], rcx
0x18000b9bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b9c4  mov     rbx, [rsp+28h+arg_0]
0x18000b9c9  add     rsp, 20h
0x18000b9cd  pop     rdi
0x18000b9ce  retn
0x18000b9cf  mov     rcx, [rdi+68h]; void *
0x18000b9d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b9d8  jmp     short loc_18000B99E
```
