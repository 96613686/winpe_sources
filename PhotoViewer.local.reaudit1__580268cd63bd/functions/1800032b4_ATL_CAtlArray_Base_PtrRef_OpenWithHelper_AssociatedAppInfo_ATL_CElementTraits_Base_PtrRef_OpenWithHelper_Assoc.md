# ATL::CAtlArray<Base::PtrRef<OpenWithHelper::AssociatedAppInfo>,ATL::CElementTraits<Base::PtrRef<OpenWithHelper::AssociatedAppInfo>>>::GrowBuffer(unsigned __int64)

- ea: `0x1800032b4`
- end: `0x18000337c`
- name: `?GrowBuffer@?$CAtlArray@V?$PtrRef@VAssociatedAppInfo@OpenWithHelper@@@Base@@V?$CElementTraits@V?$PtrRef@VAssociatedAppInfo@OpenWithHelper@@@Base@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18004a548`
- `0x18004a5f0`
- `0x18004a698`
- `0x18004a88c`
- `0x18006a8e4`
- `0x18006ab2c`
- `0x180078408`

## callees

- `0x1800032b4`
- `0x1800046f8`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18000334d`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18000334d`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800032ef`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000332a`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800032ef`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000332a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000335d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000335d`

## pseudocode

```c
char __fastcall ATL::CAtlArray<Base::PtrRef<OpenWithHelper::AssociatedAppInfo>,ATL::CElementTraits<Base::PtrRef<OpenWithHelper::AssociatedAppInfo>>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 8u);
    *(_QWORD *)a1 = v6;
    if ( v6 )
      goto LABEL_15;
    return 0;
  }
  if ( !v5 )
  {
    v5 = v4 >> 1;
    if ( a2 - v4 > v4 >> 1 )
      v5 = a2 - v4;
  }
  if ( a2 < v4 + v5 )
    a2 = v4 + v5;
  v7 = calloc(a2, 8u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
  ATL::AtlCrtErrorCheck(v10);
  free(*(void **)a1);
  *(_QWORD *)a1 = v8;
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x1800032b4  mov     [rsp+arg_0], rbx
0x1800032b9  mov     [rsp+arg_8], rsi
0x1800032be  push    rdi
0x1800032bf  sub     rsp, 20h
0x1800032c3  mov     rdi, rdx
0x1800032c6  mov     rbx, rcx
0x1800032c9  mov     rdx, [rcx+10h]
0x1800032cd  cmp     rdi, rdx
0x1800032d0  jbe     loc_18000336A
0x1800032d6  cmp     qword ptr [rbx], 0
0x1800032da  movsxd  rcx, dword ptr [rcx+18h]
0x1800032de  jnz     short loc_1800032FF
0x1800032e0  cmp     rcx, rdi
0x1800032e3  mov     edx, 8; Size
0x1800032e8  cmova   rdi, rcx
0x1800032ec  mov     rcx, rdi; Count
0x1800032ef  call    cs:__imp_calloc
0x1800032f5  mov     [rbx], rax
0x1800032f8  test    rax, rax
0x1800032fb  jz      short loc_180003338
0x1800032fd  jmp     short loc_180003366
0x1800032ff  test    rcx, rcx
0x180003302  jnz     short loc_180003317
0x180003304  mov     rcx, rdx
0x180003307  mov     rax, rdi
0x18000330a  shr     rcx, 1
0x18000330d  sub     rax, rdx
0x180003310  cmp     rax, rcx
0x180003313  cmova   rcx, rax
0x180003317  lea     rax, [rdx+rcx]
0x18000331b  mov     edx, 8; Size
0x180003320  cmp     rdi, rax
0x180003323  cmovb   rdi, rax
0x180003327  mov     rcx, rdi; Count
0x18000332a  call    cs:__imp_calloc
0x180003330  mov     rsi, rax
0x180003333  test    rax, rax
0x180003336  jnz     short loc_18000333C
0x180003338  xor     al, al
0x18000333a  jmp     short loc_18000336C
0x18000333c  mov     rdx, [rbx+8]
0x180003340  mov     rcx, rsi; Destination
0x180003343  mov     r8, [rbx]; Source
0x180003346  shl     rdx, 3; DestinationSize
0x18000334a  mov     r9, rdx; SourceSize
0x18000334d  call    cs:__imp_memmove_s
0x180003353  mov     ecx, eax; int
0x180003355  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000335a  mov     rcx, [rbx]; Block
0x18000335d  call    cs:__imp_free
0x180003363  mov     [rbx], rsi
0x180003366  mov     [rbx+10h], rdi
0x18000336a  mov     al, 1
0x18000336c  mov     rbx, [rsp+28h+arg_0]
0x180003371  mov     rsi, [rsp+28h+arg_8]
0x180003376  add     rsp, 20h
0x18000337a  pop     rdi
0x18000337b  retn
```
