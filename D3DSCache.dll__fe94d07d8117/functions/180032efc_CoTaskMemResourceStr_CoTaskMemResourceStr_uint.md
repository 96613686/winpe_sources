# CoTaskMemResourceStr::CoTaskMemResourceStr(uint)

- ea: `0x180032efc`
- end: `0x180032f9c`
- name: `??0CoTaskMemResourceStr@@QEAA@I@Z`
- size: `160`
- prototype: `CoTaskMemResourceStr *__fastcall(CoTaskMemResourceStr *this, UINT)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003fdf0`

## callees

- `0x180001d30`
- `0x180032efc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180032f27`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180032f83`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180032f27`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180032f83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032f5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032f5c`

## pseudocode

```c
CoTaskMemResourceStr *__fastcall CoTaskMemResourceStr::CoTaskMemResourceStr(CoTaskMemResourceStr *this, UINT a2)
{
  int StringW; // ebx
  unsigned __int64 v5; // rbx
  LPVOID v6; // rax
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  StringW = LoadStringW(hInstance, a2, (LPWSTR)&v8, 0);
  if ( !StringW )
    ThrowFailure(-2147467259);
  v5 = 2LL * (StringW + 1);
  if ( v5 > 0x7FFFFFFF )
    ThrowFailure(-2147024882);
  v6 = CoTaskMemAlloc(v5);
  *(_QWORD *)this = v6;
  if ( !v6 )
    ThrowFailure(-2147024882);
  LoadStringW(hInstance, a2, *(LPWSTR *)this, v5);
  return this;
}

```

## disassembly

```asm
0x180032efc  mov     rax, rsp
0x180032eff  mov     [rax+10h], rbx
0x180032f03  mov     [rax+18h], rsi
0x180032f07  push    rdi
0x180032f08  sub     rsp, 20h
0x180032f0c  mov     rdi, rcx
0x180032f0f  mov     qword ptr [rax+8], 0
0x180032f17  mov     rcx, cs:hInstance; hInstance
0x180032f1e  lea     r8, [rax+8]; lpBuffer
0x180032f22  xor     r9d, r9d; cchBufferMax
0x180032f25  mov     esi, edx
0x180032f27  call    cs:__imp_LoadStringW
0x180032f2d  mov     ebx, eax
0x180032f2f  test    eax, eax
0x180032f31  jnz     short loc_180032F3D
0x180032f33  mov     ecx, 80004005h; int
0x180032f38  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180032f3d  lea     eax, [rbx+1]
0x180032f40  movsxd  rbx, eax
0x180032f43  add     rbx, rbx
0x180032f46  cmp     rbx, 7FFFFFFFh
0x180032f4d  jbe     short loc_180032F59
0x180032f4f  mov     ecx, 8007000Eh; int
0x180032f54  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180032f59  mov     rcx, rbx; cb
0x180032f5c  call    cs:__imp_CoTaskMemAlloc
0x180032f62  mov     [rdi], rax
0x180032f65  test    rax, rax
0x180032f68  jnz     short loc_180032F74
0x180032f6a  mov     ecx, 8007000Eh; int
0x180032f6f  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180032f74  mov     r8, [rdi]; lpBuffer
0x180032f77  mov     r9d, ebx; cchBufferMax
0x180032f7a  mov     rcx, cs:hInstance; hInstance
0x180032f81  mov     edx, esi; uID
0x180032f83  call    cs:__imp_LoadStringW
0x180032f89  mov     rbx, [rsp+28h+arg_8]
0x180032f8e  mov     rax, rdi
0x180032f91  mov     rsi, [rsp+28h+arg_10]
0x180032f96  add     rsp, 20h
0x180032f9a  pop     rdi
0x180032f9b  retn
```
