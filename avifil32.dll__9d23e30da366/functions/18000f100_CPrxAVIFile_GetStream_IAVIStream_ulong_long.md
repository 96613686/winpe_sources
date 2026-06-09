# CPrxAVIFile::GetStream(IAVIStream * *,ulong,long)

- ea: `0x18000f100`
- end: `0x18000f2a4`
- name: `?GetStream@CPrxAVIFile@@UEAAJPEAPEAUIAVIStream@@KJ@Z`
- size: `420`
- prototype: `int(CPrxAVIFile *__hidden this, struct IAVIStream **, unsigned int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d0c`
- `0x18000f100`
- `0x180017365`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000f227`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000f227`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000f1f9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000f1f9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000f1d7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000f1d7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f230`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f230`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18000f248`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18000f248`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000f218`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000f218`

## pseudocode

```c
__int64 __fastcall CPrxAVIFile::GetStream(CPrxAVIFile *this, LPVOID *a2, unsigned int a3, unsigned int a4)
{
  __int64 v4; // r14
  __int64 result; // rax
  HGLOBAL v9; // rax
  void *v10; // rsi
  __int64 v11; // rdi
  unsigned int *v12; // rbx
  void *v13; // rax
  HRESULT v14; // ebx
  LPSTREAM ppstm; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v16[16]; // [rsp+30h] [rbp-29h] BYREF
  unsigned int *v17; // [rsp+40h] [rbp-19h]
  unsigned int v18; // [rsp+48h] [rbp-11h]
  int v19; // [rsp+4Ch] [rbp-Dh]
  unsigned int v20; // [rsp+80h] [rbp+27h] BYREF

  v4 = *((_QWORD *)this + 5);
  v20 = 0;
  if ( !v4 )
    return 2147549190LL;
  memset_0(v16, 0, 0x50u);
  v18 = 8;
  v19 = 2;
  if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *, GUID *))(*(_QWORD *)v4 + 24LL))(v4, v16, &IID_IAVIFile) )
    return 2147549195LL;
  *v17 = a3;
  v17[1] = a4;
  if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *, unsigned int *))(*(_QWORD *)v4 + 32LL))(v4, v16, &v20) )
    return 2147549195LL;
  result = *v17;
  v20 = result;
  if ( (_DWORD)result )
    return result;
  ppstm = 0;
  v9 = GlobalAlloc(0x42u, v18 - 4LL);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  v11 = v18;
  v12 = v17;
  v13 = GlobalLock(v9);
  memmove_0(v13, v12 + 1, v11 - 4);
  v14 = CreateStreamOnHGlobal(v10, 0, &ppstm);
  if ( v14 < 0 )
  {
    GlobalUnlock(v10);
    GlobalFree(v10);
    return (unsigned int)v14;
  }
  v14 = CoUnmarshalInterface(ppstm, &IID_IAVIStream, a2);
  ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v4 + 40LL))(v4, v16);
  if ( v14 < 0 )
    return (unsigned int)v14;
  return v20;
}

```

## disassembly

```asm
0x18000f100  mov     [rsp-8+arg_10], rbx
0x18000f105  push    rbp
0x18000f106  push    rsi
0x18000f107  push    rdi
0x18000f108  push    r14
0x18000f10a  push    r15
0x18000f10c  lea     rbp, [rsp-37h]
0x18000f111  sub     rsp, 90h
0x18000f118  mov     rax, cs:__security_cookie
0x18000f11f  xor     rax, rsp
0x18000f122  mov     [rbp+57h+var_28], rax
0x18000f126  mov     r14, [rcx+28h]
0x18000f12a  mov     ebx, r9d
0x18000f12d  mov     [rbp+57h+var_30], 0
0x18000f134  mov     edi, r8d
0x18000f137  mov     r15, rdx
0x18000f13a  test    r14, r14
0x18000f13d  jnz     short loc_18000F149
0x18000f13f  mov     eax, 80010006h
0x18000f144  jmp     loc_18000F281
0x18000f149  xor     edx, edx; Val
0x18000f14b  lea     rcx, [rbp+57h+var_80]; void *
0x18000f14f  lea     r8d, [rdx+50h]; Size
0x18000f153  call    memset_0
0x18000f158  mov     [rbp+57h+var_68], 8
0x18000f15f  lea     r8, IID_IAVIFile
0x18000f166  mov     [rbp+57h+var_64], 2
0x18000f16d  lea     rdx, [rbp+57h+var_80]
0x18000f171  mov     rax, [r14]
0x18000f174  mov     rcx, r14
0x18000f177  mov     rax, [rax+18h]
0x18000f17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f180  test    eax, eax
0x18000f182  jnz     loc_18000F27C
0x18000f188  mov     rax, [rbp+57h+var_70]
0x18000f18c  lea     r8, [rbp+57h+var_30]
0x18000f190  lea     rdx, [rbp+57h+var_80]
0x18000f194  mov     rcx, r14
0x18000f197  mov     [rax], edi
0x18000f199  mov     rax, [rbp+57h+var_70]
0x18000f19d  mov     [rax+4], ebx
0x18000f1a0  mov     rax, [r14]
0x18000f1a3  mov     rax, [rax+20h]
0x18000f1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1ac  test    eax, eax
0x18000f1ae  jnz     loc_18000F27C
0x18000f1b4  mov     rax, [rbp+57h+var_70]
0x18000f1b8  mov     eax, [rax]
0x18000f1ba  mov     [rbp+57h+var_30], eax
0x18000f1bd  test    eax, eax
0x18000f1bf  jnz     loc_18000F281
0x18000f1c5  mov     edx, [rbp+57h+var_68]
0x18000f1c8  lea     ecx, [rax+42h]; uFlags
0x18000f1cb  sub     rdx, 4; dwBytes
0x18000f1cf  mov     [rbp+57h+ppstm], 0
0x18000f1d7  call    cs:__imp_GlobalAlloc
0x18000f1dd  mov     rsi, rax
0x18000f1e0  test    rax, rax
0x18000f1e3  jnz     short loc_18000F1EF
0x18000f1e5  mov     eax, 8007000Eh
0x18000f1ea  jmp     loc_18000F281
0x18000f1ef  mov     edi, [rbp+57h+var_68]
0x18000f1f2  mov     rcx, rsi; hMem
0x18000f1f5  mov     rbx, [rbp+57h+var_70]
0x18000f1f9  call    cs:__imp_GlobalLock
0x18000f1ff  mov     rcx, rax; void *
0x18000f202  lea     r8, [rdi-4]; Size
0x18000f206  lea     rdx, [rbx+4]; Src
0x18000f20a  call    memmove_0
0x18000f20f  lea     r8, [rbp+57h+ppstm]; ppstm
0x18000f213  xor     edx, edx; fDeleteOnRelease
0x18000f215  mov     rcx, rsi; hGlobal
0x18000f218  call    cs:__imp_CreateStreamOnHGlobal
0x18000f21e  mov     ebx, eax
0x18000f220  test    eax, eax
0x18000f222  jns     short loc_18000F23A
0x18000f224  mov     rcx, rsi; hMem
0x18000f227  call    cs:__imp_GlobalUnlock
0x18000f22d  mov     rcx, rsi; hMem
0x18000f230  call    cs:__imp_GlobalFree
0x18000f236  mov     eax, ebx
0x18000f238  jmp     short loc_18000F281
0x18000f23a  mov     rcx, [rbp+57h+ppstm]; pStm
0x18000f23e  lea     rdx, IID_IAVIStream; riid
0x18000f245  mov     r8, r15; ppv
0x18000f248  call    cs:__imp_CoUnmarshalInterface
0x18000f24e  mov     rcx, [rbp+57h+ppstm]
0x18000f252  mov     ebx, eax
0x18000f254  mov     rdx, [rcx]
0x18000f257  mov     rax, [rdx+10h]
0x18000f25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f260  mov     rdx, [r14]
0x18000f263  mov     rcx, r14
0x18000f266  mov     rax, [rdx+28h]
0x18000f26a  lea     rdx, [rbp+57h+var_80]
0x18000f26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f273  test    ebx, ebx
0x18000f275  js      short loc_18000F236
0x18000f277  mov     eax, [rbp+57h+var_30]
0x18000f27a  jmp     short loc_18000F281
0x18000f27c  mov     eax, 8001000Bh
0x18000f281  mov     rcx, [rbp+57h+var_28]
0x18000f285  xor     rcx, rsp; StackCookie
0x18000f288  call    __security_check_cookie
0x18000f28d  mov     rbx, [rsp+0B0h+arg_10]
0x18000f295  add     rsp, 90h
0x18000f29c  pop     r15
0x18000f29e  pop     r14
0x18000f2a0  pop     rdi
0x18000f2a1  pop     rsi
0x18000f2a2  pop     rbp
0x18000f2a3  retn
```
