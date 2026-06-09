# CItemIDFactory<DSPROFILEITEM,999534523>::s_CreateItemID(DSPROFILEITEM const *,IPropertyStore *,_ITEMIDLIST * *,IMalloc *)

- ea: `0x1800054b0`
- end: `0x1800055cd`
- name: `?s_CreateItemID@?$CItemIDFactory@UDSPROFILEITEM@@$0DLJDKPLL@@@SAJPEFBUDSPROFILEITEM@@PEAUIPropertyStore@@PEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180003280`

## callees

- `0x180001916`
- `0x1800054b0`
- `0x18000a7a7`
- `0x18000b010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180005559`
- `ole32!CoTaskMemAlloc` at `0x180005559`
- `ole32!CoTaskMemFree` at `0x1800055ba`
- `ole32!CoTaskMemFree` at `0x1800055ba`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<DSPROFILEITEM,999534523>::s_CreateItemID(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        _QWORD *a3,
        __int64 a4)
{
  unsigned int v4; // eax
  int v6; // ebx
  __int16 v7; // si
  size_t v8; // rdi
  char *v9; // rax
  char *v10; // rbx
  __int64 v12; // [rsp+50h] [rbp+30h] BYREF
  void *Src; // [rsp+58h] [rbp+38h] BYREF
  unsigned int Size; // [rsp+68h] [rbp+48h] BYREF
  int Size_4; // [rsp+6Ch] [rbp+4Ch]

  Size_4 = HIDWORD(a4);
  v12 = a1;
  v4 = 0;
  *a3 = 0;
  Src = 0;
  Size = 0;
  if ( a2 )
  {
    v12 = 0;
    v6 = (**a2)(a2, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &v12);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v6 = (*(__int64 (__fastcall **)(__int64, void **, unsigned int *))(*(_QWORD *)v12 + 40LL))(v12, &Src, &Size);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v4 = Size;
  }
  v7 = v4 + 14;
  v8 = v4 + 12 + 10LL;
  if ( v8 <= 0x10001 && (v9 = (char *)CoTaskMemAlloc(v4 + 12 + 10LL), (v10 = v9) != 0) )
  {
    memset_0(v9, 0, v8);
    *((_WORD *)v10 + 2) = v7;
    *(_WORD *)v10 = v8 - 2;
    *(_DWORD *)(v10 + 6) = 999534523;
    *((_WORD *)v10 + 5) = Size;
    *((_WORD *)v10 + 6) = 4;
    if ( Src )
      memcpy_0(v10 + 18, Src, Size);
    *a3 = v10;
    v6 = 0;
  }
  else
  {
    v6 = -2147024882;
  }
  CoTaskMemFree(Src);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800054b0  mov     [rsp-28h+Size], r9
0x1800054b5  mov     [rsp-28h+arg_0], rcx
0x1800054ba  push    rbp
0x1800054bb  push    rbx
0x1800054bc  push    rsi
0x1800054bd  push    rdi
0x1800054be  push    r14
0x1800054c0  mov     rbp, rsp
0x1800054c3  sub     rsp, 20h
0x1800054c7  xor     eax, eax
0x1800054c9  mov     qword ptr [r8], 0
0x1800054d0  mov     [rbp+Src], 0
0x1800054d8  mov     r14, r8
0x1800054db  mov     dword ptr [rbp+Size], eax
0x1800054de  mov     r9, rdx
0x1800054e1  test    rdx, rdx
0x1800054e4  jz      short loc_180005542
0x1800054e6  mov     [rbp+arg_0], rax
0x1800054ea  lea     r8, [rbp+arg_0]
0x1800054ee  mov     rax, [rdx]
0x1800054f1  mov     rcx, r9
0x1800054f4  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x1800054fb  mov     rax, [rax]
0x1800054fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005503  mov     ebx, eax
0x180005505  test    eax, eax
0x180005507  js      loc_1800055C0
0x18000550d  mov     rcx, [rbp+arg_0]
0x180005511  lea     r8, [rbp+Size]
0x180005515  lea     rdx, [rbp+Src]
0x180005519  mov     rax, [rcx]
0x18000551c  mov     rax, [rax+28h]
0x180005520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005525  mov     rcx, [rbp+arg_0]
0x180005529  mov     ebx, eax
0x18000552b  mov     rax, [rcx]
0x18000552e  mov     rax, [rax+10h]
0x180005532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005537  test    ebx, ebx
0x180005539  js      loc_1800055C0
0x18000553f  mov     eax, dword ptr [rbp+Size]
0x180005542  lea     esi, [rax+0Ch]
0x180005545  add     rsi, 2
0x180005549  lea     rdi, [rsi+8]
0x18000554d  cmp     rdi, 10001h
0x180005554  ja      short loc_1800055B1
0x180005556  mov     rcx, rdi; cb
0x180005559  call    cs:__imp_CoTaskMemAlloc
0x18000555f  mov     rbx, rax
0x180005562  test    rax, rax
0x180005565  jz      short loc_1800055B1
0x180005567  mov     r8, rdi; Size
0x18000556a  xor     edx, edx; Val
0x18000556c  mov     rcx, rax; void *
0x18000556f  call    memset_0
0x180005574  mov     [rbx+4], si
0x180005578  sub     di, 2
0x18000557c  mov     [rbx], di
0x18000557f  mov     dword ptr [rbx+6], 3B93AFBBh
0x180005586  movzx   ecx, word ptr [rbp+Size]
0x18000558a  mov     [rbx+0Ah], cx
0x18000558e  mov     word ptr [rbx+0Ch], 4
0x180005594  mov     rdx, [rbp+Src]; Src
0x180005598  test    rdx, rdx
0x18000559b  jz      short loc_1800055AA
0x18000559d  mov     r8d, dword ptr [rbp+Size]; Size
0x1800055a1  lea     rcx, [rbx+12h]; void *
0x1800055a5  call    memcpy_0
0x1800055aa  mov     [r14], rbx
0x1800055ad  xor     ebx, ebx
0x1800055af  jmp     short loc_1800055B6
0x1800055b1  mov     ebx, 8007000Eh
0x1800055b6  mov     rcx, [rbp+Src]; pv
0x1800055ba  call    cs:__imp_CoTaskMemFree
0x1800055c0  mov     eax, ebx
0x1800055c2  add     rsp, 20h
0x1800055c6  pop     r14
0x1800055c8  pop     rdi
0x1800055c9  pop     rsi
0x1800055ca  pop     rbx
0x1800055cb  pop     rbp
0x1800055cc  retn
```
