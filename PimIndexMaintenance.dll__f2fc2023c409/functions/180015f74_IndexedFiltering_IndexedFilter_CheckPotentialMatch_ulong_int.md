# IndexedFiltering::IndexedFilter::_CheckPotentialMatch(ulong,int *)

- ea: `0x180015f74`
- end: `0x1800160ee`
- name: `?_CheckPotentialMatch@IndexedFilter@IndexedFiltering@@AEAAJKPEAH@Z`
- size: `378`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexedFilter *this, __int64, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180015374`

## callees

- `0x180002da8`
- `0x1800157c0`
- `0x180015f74`
- `0x180016158`
- `0x180021240`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800160cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800160cc`

## string_xrefs

- `0x180015ffe`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexedfilter.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexedFilter::_CheckPotentialMatch(
        IndexedFiltering::IndexedFilter *this,
        __int64 a2,
        int *a3)
{
  unsigned int v4; // r14d
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx
  int v12; // [rsp+40h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-38h] BYREF
  __int64 v14; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v15; // [rsp+58h] [rbp-28h] BYREF
  __int64 v16; // [rsp+60h] [rbp-20h] BYREF
  int v17; // [rsp+68h] [rbp-18h]

  v16 = 0;
  v4 = a2;
  v17 = 0;
  hMem = 0;
  v14 = 0;
  v12 = 0;
  if ( !a3 )
    Log_AssertionEvent_2(this, a2, 446);
  if ( *((_DWORD *)this + 7) >= *((_DWORD *)this + 39) )
    Log_AssertionEvent_2(this, a2, 447);
  v6 = *((_QWORD *)this + *((unsigned int *)this + 7) + 12);
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, int *))(*(_QWORD *)v6 + 24LL))(v6, &v14, &v12);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 10) + 32LL))(
           *((_QWORD *)this + 10),
           v4,
           &v16);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v10 = *((_QWORD *)this + 11);
      v15 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD, HLOCAL *, unsigned __int64 *))(*(_QWORD *)v10 + 24LL))(
             v10,
             &v16,
             v14,
             (unsigned __int16)v12,
             &hMem,
             &v15);
      v8 = v7;
      if ( v7 == -2147023728 || v7 == -2147024871 )
      {
        *a3 = 0;
        v8 = 0;
        goto LABEL_17;
      }
      if ( v7 >= 0 )
      {
        v7 = IndexedFiltering::IndexedFilter::_DoPropertiesMatch(
               this,
               (struct _SQLCEPROPVAL *)hMem,
               v15,
               *((struct IndexedFiltering::IIndexSource **)this + *((unsigned int *)this + 7) + 12),
               a3);
        v8 = v7;
        if ( v7 >= 0 )
          goto LABEL_17;
        v9 = 475;
      }
      else
      {
        v9 = 468;
      }
    }
    else
    {
      v9 = 453;
    }
  }
  else
  {
    v9 = 450;
  }
  Log_HREvent(
    (unsigned int)v7,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexedfilter.cpp",
    v9);
LABEL_17:
  LocalFree(hMem);
  return v8;
}

```

## disassembly

```asm
0x180015f74  push    rbp
0x180015f76  push    rbx
0x180015f77  push    rsi
0x180015f78  push    rdi
0x180015f79  push    r14
0x180015f7b  mov     rbp, rsp
0x180015f7e  sub     rsp, 80h
0x180015f85  mov     rax, cs:__security_cookie
0x180015f8c  xor     rax, rsp
0x180015f8f  mov     [rbp+var_10], rax
0x180015f93  xor     eax, eax
0x180015f95  mov     rsi, r8
0x180015f98  mov     [rbp+var_20], rax
0x180015f9c  mov     r14d, edx
0x180015f9f  mov     [rbp+var_18], eax
0x180015fa2  mov     rdi, rcx
0x180015fa5  mov     [rbp+hMem], rax
0x180015fa9  mov     [rbp+var_30], rax
0x180015fad  mov     [rbp+var_40], eax
0x180015fb0  test    r8, r8
0x180015fb3  jnz     short loc_180015FC0
0x180015fb5  mov     r8d, 1BEh
0x180015fbb  call    Log_AssertionEvent_2
0x180015fc0  mov     eax, [rdi+9Ch]
0x180015fc6  cmp     [rdi+1Ch], eax
0x180015fc9  jb      short loc_180015FD6
0x180015fcb  mov     r8d, 1BFh
0x180015fd1  call    Log_AssertionEvent_2
0x180015fd6  mov     eax, [rdi+1Ch]
0x180015fd9  lea     r8, [rbp+var_40]
0x180015fdd  lea     rdx, [rbp+var_30]
0x180015fe1  mov     rcx, [rdi+rax*8+60h]
0x180015fe6  mov     rax, [rcx]
0x180015fe9  mov     rax, [rax+18h]
0x180015fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ff2  mov     ebx, eax
0x180015ff4  test    eax, eax
0x180015ff6  jns     short loc_180016016
0x180015ff8  mov     r9d, 1C2h
0x180015ffe  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016005  mov     edx, 1
0x18001600a  mov     ecx, eax
0x18001600c  call    Log_HREvent
0x180016011  jmp     loc_1800160C8
0x180016016  mov     rcx, [rdi+50h]
0x18001601a  lea     r8, [rbp+var_20]
0x18001601e  mov     edx, r14d
0x180016021  mov     rax, [rcx]
0x180016024  mov     rax, [rax+20h]
0x180016028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001602d  mov     ebx, eax
0x18001602f  test    eax, eax
0x180016031  jns     short loc_18001603B
0x180016033  mov     r9d, 1C5h
0x180016039  jmp     short loc_180015FFE
0x18001603b  mov     rcx, [rdi+58h]
0x18001603f  lea     rdx, [rbp+var_28]
0x180016043  movzx   r9d, word ptr [rbp+var_40]
0x180016048  mov     r8, [rbp+var_30]
0x18001604c  mov     [rsp+80h+var_58], rdx
0x180016051  lea     rdx, [rbp+hMem]
0x180016055  mov     [rbp+var_28], 0
0x18001605d  mov     rax, [rcx]
0x180016060  mov     [rsp+80h+var_60], rdx
0x180016065  lea     rdx, [rbp+var_20]
0x180016069  mov     rax, [rax+18h]
0x18001606d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016072  mov     ebx, eax
0x180016074  cmp     eax, 80070490h
0x180016079  jz      short loc_1800160C0
0x18001607b  cmp     eax, 80070019h
0x180016080  jz      short loc_1800160C0
0x180016082  test    eax, eax
0x180016084  jns     short loc_180016091
0x180016086  mov     r9d, 1D4h
0x18001608c  jmp     loc_180015FFE
0x180016091  mov     r9d, [rdi+1Ch]
0x180016095  mov     rcx, rdi; this
0x180016098  mov     r8, [rbp+var_28]; unsigned __int64
0x18001609c  mov     rdx, [rbp+hMem]; struct _SQLCEPROPVAL *
0x1800160a0  mov     [rsp+80h+var_60], rsi; int *
0x1800160a5  mov     r9, [rdi+r9*8+60h]; struct IndexedFiltering::IIndexSource *
0x1800160aa  call    ?_DoPropertiesMatch@IndexedFilter@IndexedFiltering@@AEAAJPEAU_SQLCEPROPVAL@@_KPEAUIIndexSource@2@PEAH@Z; IndexedFiltering::IndexedFilter::_DoPropertiesMatch(_SQLCEPROPVAL *,unsigned __int64,IndexedFiltering::IIndexSource *,int *)
0x1800160af  mov     ebx, eax
0x1800160b1  test    eax, eax
0x1800160b3  jns     short loc_1800160C8
0x1800160b5  mov     r9d, 1DBh
0x1800160bb  jmp     loc_180015FFE
0x1800160c0  mov     dword ptr [rsi], 0
0x1800160c6  xor     ebx, ebx
0x1800160c8  mov     rcx, [rbp+hMem]; hMem
0x1800160cc  call    cs:__imp_LocalFree
0x1800160d2  mov     eax, ebx
0x1800160d4  mov     rcx, [rbp+var_10]
0x1800160d8  xor     rcx, rsp; StackCookie
0x1800160db  call    __security_check_cookie
0x1800160e0  add     rsp, 80h
0x1800160e7  pop     r14
0x1800160e9  pop     rdi
0x1800160ea  pop     rsi
0x1800160eb  pop     rbx
0x1800160ec  pop     rbp
0x1800160ed  retn
```
