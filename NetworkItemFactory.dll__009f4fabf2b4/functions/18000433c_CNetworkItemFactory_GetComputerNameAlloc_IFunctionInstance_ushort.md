# CNetworkItemFactory::_GetComputerNameAlloc(IFunctionInstance *,ushort * *)

- ea: `0x18000433c`
- end: `0x180004425`
- name: `?_GetComputerNameAlloc@CNetworkItemFactory@@CAJPEAUIFunctionInstance@@PEAPEAG@Z`
- size: `233`
- prototype: `static int(struct IFunctionInstance *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004074`

## callees

- `0x180003c14`
- `0x18000433c`
- `0x1800059e8`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800043a4`
- `ole32!CoTaskMemAlloc` at `0x1800043a4`
- `ole32!CoTaskMemFree` at `0x1800043e8`
- `ole32!CoTaskMemFree` at `0x180004405`
- `ole32!CoTaskMemFree` at `0x180004410`
- `ole32!CoTaskMemFree` at `0x1800043e8`
- `ole32!CoTaskMemFree` at `0x180004405`
- `ole32!CoTaskMemFree` at `0x180004410`
- `SHLWAPI!SHStrDupW` at `0x1800043f8`
- `SHLWAPI!SHStrDupW` at `0x1800043f8`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::_GetComputerNameAlloc(struct IFunctionInstance *a1, unsigned __int16 **a2)
{
  int FIComputerName; // ebx
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned __int64 v6; // rbx
  unsigned __int16 *v7; // rdi
  struct _tagpropertykey psz; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  *(_QWORD *)psz.fmtid.Data4 = 0;
  *(_QWORD *)&psz.fmtid.Data1 = 0;
  FIComputerName = GetFIComputerName(a1, &psz, (unsigned __int16 **)psz.fmtid.Data4);
  if ( FIComputerName >= 0 )
  {
    if ( *(_QWORD *)psz.fmtid.Data4 )
    {
      v4 = -1;
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)(*(_QWORD *)psz.fmtid.Data4 + 2 * v5) );
      do
        ++v4;
      while ( *(_WORD *)(*(_QWORD *)&psz.fmtid.Data1 + 2 * v4) );
      v6 = v5 + v4 + 2;
      v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
      if ( v7 )
      {
        FIComputerName = StringCchPrintfW(v7, v6, L"%s\\%s", *(_QWORD *)psz.fmtid.Data4, *(_QWORD *)&psz.fmtid.Data1);
        if ( FIComputerName < 0 )
          CoTaskMemFree(v7);
        else
          *a2 = v7;
      }
      else
      {
        FIComputerName = -2147024882;
      }
    }
    else
    {
      FIComputerName = SHStrDupW(*(LPCWSTR *)&psz.fmtid.Data1, a2);
    }
    CoTaskMemFree(*(LPVOID *)&psz.fmtid.Data1);
    CoTaskMemFree(*(LPVOID *)psz.fmtid.Data4);
  }
  return (unsigned int)FIComputerName;
}

```

## disassembly

```asm
0x18000433c  mov     rax, rsp
0x18000433f  mov     [rax+8], rbx
0x180004343  push    rbp
0x180004344  push    rsi
0x180004345  push    rdi
0x180004346  sub     rsp, 30h
0x18000434a  xor     ebp, ebp
0x18000434c  lea     r8, [rax+18h]; unsigned __int16 **
0x180004350  mov     [rdx], rbp
0x180004353  mov     rsi, rdx
0x180004356  lea     rdx, [rax+10h]; unsigned __int16 **
0x18000435a  mov     [rax+18h], rbp
0x18000435e  mov     [rax+10h], rbp
0x180004362  call    ?GetFIComputerName@@YAJPEAUIFunctionInstance@@PEAPEAG1@Z; GetFIComputerName(IFunctionInstance *,ushort * *,ushort * *)
0x180004367  mov     ebx, eax
0x180004369  test    eax, eax
0x18000436b  js      loc_180004416
0x180004371  mov     rdx, [rsp+48h+pv]
0x180004376  test    rdx, rdx
0x180004379  jz      short loc_1800043F0
0x18000437b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000437f  mov     rcx, rax
0x180004382  inc     rcx
0x180004385  cmp     [rdx+rcx*2], bp
0x180004389  jnz     short loc_180004382
0x18000438b  mov     rdx, [rsp+48h+psz]
0x180004390  inc     rax
0x180004393  cmp     [rdx+rax*2], bp
0x180004397  jnz     short loc_180004390
0x180004399  lea     rbx, [rax+2]
0x18000439d  add     rbx, rcx
0x1800043a0  lea     rcx, [rbx+rbx]; cb
0x1800043a4  call    cs:__imp_CoTaskMemAlloc
0x1800043aa  mov     rdi, rax
0x1800043ad  test    rax, rax
0x1800043b0  jnz     short loc_1800043B9
0x1800043b2  mov     ebx, 8007000Eh
0x1800043b7  jmp     short loc_180004400
0x1800043b9  mov     rax, [rsp+48h+psz]
0x1800043be  lea     r8, aSS; "%s\\%s"
0x1800043c5  mov     r9, [rsp+48h+pv]
0x1800043ca  mov     rdx, rbx; unsigned __int64
0x1800043cd  mov     rcx, rdi; unsigned __int16 *
0x1800043d0  mov     [rsp+48h+var_28], rax
0x1800043d5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800043da  mov     ebx, eax
0x1800043dc  test    eax, eax
0x1800043de  js      short loc_1800043E5
0x1800043e0  mov     [rsi], rdi
0x1800043e3  jmp     short loc_180004400
0x1800043e5  mov     rcx, rdi; pv
0x1800043e8  call    cs:__imp_CoTaskMemFree
0x1800043ee  jmp     short loc_180004400
0x1800043f0  mov     rcx, [rsp+48h+psz]; psz
0x1800043f5  mov     rdx, rsi; ppwsz
0x1800043f8  call    cs:__imp_SHStrDupW
0x1800043fe  mov     ebx, eax
0x180004400  mov     rcx, [rsp+48h+psz]; pv
0x180004405  call    cs:__imp_CoTaskMemFree
0x18000440b  mov     rcx, [rsp+48h+pv]; pv
0x180004410  call    cs:__imp_CoTaskMemFree
0x180004416  mov     eax, ebx
0x180004418  mov     rbx, [rsp+48h+arg_0]
0x18000441d  add     rsp, 30h
0x180004421  pop     rdi
0x180004422  pop     rsi
0x180004423  pop     rbp
0x180004424  retn
```
