# RfbServerFolderQuery::CreatePidl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180013190`
- end: `0x180013245`
- name: `?CreatePidl@RfbServerFolderQuery@@IEAA?AV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `181`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180013250`
- `0x1800132f0`

## callees

- `0x180002dac`
- `0x180002dc4`
- `0x180013190`
- `0x180019010`

## import_xrefs

- `SHELL32!SHGetMalloc` at `0x1800131b7`
- `SHELL32!SHGetMalloc` at `0x1800131b7`

## pseudocode

```c
_QWORD *__fastcall RfbServerFolderQuery::CreatePidl(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  char *v5; // rbx
  _QWORD *v6; // r14
  __int64 v7; // rbp
  char *v8; // rax
  IMalloc *ppMalloc; // [rsp+78h] [rbp+10h] BYREF

  ppMalloc = 0;
  v5 = 0;
  if ( SHGetMalloc(&ppMalloc) >= 0 )
  {
    v6 = a3 + 2;
    v7 = 2LL * a3[2] + 8;
    v8 = (char *)((__int64 (__fastcall *)(IMalloc *, __int64))ppMalloc->lpVtbl->Alloc)(ppMalloc, 2LL * a3[2] + 11);
    v5 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, v7 + 3);
      *(_WORD *)v5 = v7;
      *(_DWORD *)(v5 + 2) = 0;
      if ( a3[3] > 7u )
        a3 = (_QWORD *)*a3;
      memcpy_0(v5 + 6, a3, 2LL * *v6);
    }
    ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Release)(ppMalloc);
  }
  *a2 = v5;
  return a2;
}

```

## disassembly

```asm
0x180013190  mov     [rsp+ppMalloc], rdx
0x180013195  push    rbx
0x180013196  push    rbp
0x180013197  push    rsi
0x180013198  push    rdi
0x180013199  push    r14
0x18001319b  push    r15
0x18001319d  sub     rsp, 38h
0x1800131a1  lea     rcx, [rsp+68h+ppMalloc]; ppMalloc
0x1800131a6  mov     [rsp+68h+ppMalloc], 0
0x1800131af  mov     rdi, r8
0x1800131b2  mov     rsi, rdx
0x1800131b5  xor     ebx, ebx
0x1800131b7  call    cs:__imp_SHGetMalloc
0x1800131bd  test    eax, eax
0x1800131bf  js      short loc_180013232
0x1800131c1  mov     rcx, [rsp+68h+ppMalloc]
0x1800131c6  lea     r14, [rdi+10h]
0x1800131ca  mov     rax, [r14]
0x1800131cd  lea     rbp, ds:8[rax*2]
0x1800131d5  mov     rax, [rcx]
0x1800131d8  lea     rdx, [rbp+3]
0x1800131dc  mov     rax, [rax+18h]
0x1800131e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131e5  mov     rbx, rax
0x1800131e8  test    rax, rax
0x1800131eb  jz      short loc_180013221
0x1800131ed  lea     r8, [rbp+3]; Size
0x1800131f1  xor     edx, edx; Val
0x1800131f3  mov     rcx, rax; void *
0x1800131f6  call    memset_0
0x1800131fb  mov     [rbx], bp
0x1800131fe  mov     dword ptr [rbx+2], 0
0x180013205  cmp     qword ptr [rdi+18h], 7
0x18001320a  jbe     short loc_18001320F
0x18001320c  mov     rdi, [rdi]
0x18001320f  mov     r8, [r14]
0x180013212  lea     rcx, [rbx+6]; void *
0x180013216  add     r8, r8; Size
0x180013219  mov     rdx, rdi; Src
0x18001321c  call    memcpy_0
0x180013221  mov     rcx, [rsp+68h+ppMalloc]
0x180013226  mov     rax, [rcx]
0x180013229  mov     rax, [rax+10h]
0x18001322d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013232  mov     [rsi], rbx
0x180013235  mov     rax, rsi
0x180013238  add     rsp, 38h
0x18001323c  pop     r15
0x18001323e  pop     r14
0x180013240  pop     rdi
0x180013241  pop     rsi
0x180013242  pop     rbp
0x180013243  pop     rbx
0x180013244  retn
```
