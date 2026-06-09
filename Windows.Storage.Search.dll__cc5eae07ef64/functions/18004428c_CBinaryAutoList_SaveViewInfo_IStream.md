# CBinaryAutoList::_SaveViewInfo(IStream *)

- ea: `0x18004428c`
- end: `0x18004450f`
- name: `?_SaveViewInfo@CBinaryAutoList@@AEAAJPEAUIStream@@@Z`
- size: `643`
- prototype: `int(CBinaryAutoList *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043cf0`

## callees

- `0x18004428c`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Write` at `0x1800442f8`
- `SHCORE!IStream_Write` at `0x18004433a`
- `SHCORE!IStream_Write` at `0x18004436c`
- `SHCORE!IStream_Write` at `0x18004439d`
- `SHCORE!IStream_Write` at `0x1800443d2`
- `SHCORE!IStream_Write` at `0x18004440a`
- `SHCORE!IStream_Write` at `0x180044442`
- `SHCORE!IStream_Write` at `0x180044480`
- `SHCORE!IStream_Write` at `0x1800444d3`
- `SHCORE!IStream_Write` at `0x1800442f8`
- `SHCORE!IStream_Write` at `0x18004433a`
- `SHCORE!IStream_Write` at `0x18004436c`
- `SHCORE!IStream_Write` at `0x18004439d`
- `SHCORE!IStream_Write` at `0x1800443d2`
- `SHCORE!IStream_Write` at `0x18004440a`
- `SHCORE!IStream_Write` at `0x180044442`
- `SHCORE!IStream_Write` at `0x180044480`
- `SHCORE!IStream_Write` at `0x1800444d3`
- `SHCORE!IStream_WriteStr` at `0x180044499`
- `SHCORE!IStream_WriteStr` at `0x180044505`
- `SHCORE!IStream_WriteStr` at `0x180044499`
- `SHCORE!IStream_WriteStr` at `0x180044505`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800444e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800444f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800444e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800444f3`

## pseudocode

```c
__int64 __fastcall CBinaryAutoList::_SaveViewInfo(CBinaryAutoList *this, struct IStream *a2)
{
  __int64 v3; // rcx
  HRESULT v5; // ebx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-60h] BYREF
  int v15; // [rsp+24h] [rbp-5Ch] BYREF
  int v16; // [rsp+28h] [rbp-58h] BYREF
  BOOL v17; // [rsp+2Ch] [rbp-54h] BYREF
  BOOL v18; // [rsp+30h] [rbp-50h] BYREF
  PCWSTR v19; // [rsp+38h] [rbp-48h] BYREF
  PCWSTR psz; // [rsp+40h] [rbp-40h] BYREF
  GUID pv; // [rsp+48h] [rbp-38h] BYREF
  DWORD pid; // [rsp+58h] [rbp-28h]
  __int128 v23; // [rsp+60h] [rbp-20h] BYREF

  pid = PKEY_Null.pid;
  v3 = *((_QWORD *)this + 4);
  pv = PKEY_Null.fmtid;
  v16 = 0;
  (*(void (__fastcall **)(__int64, GUID *, int *))(*(_QWORD *)v3 + 48LL))(v3, &pv, &v16);
  v5 = IStream_Write(a2, &pv, 0x14u);
  if ( v5 >= 0 )
  {
    v5 = IStream_Write(a2, &v16, 4u);
    if ( v5 >= 0 )
    {
      v7 = *((_QWORD *)this + 4);
      v23 = 0;
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v7 + 104LL))(v7, &v23);
      v5 = IStream_Write(a2, &v23, 0x10u);
      if ( v5 >= 0 )
      {
        v8 = *((_QWORD *)this + 4);
        v14 = -1;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 64LL))(v8, &v14);
        v5 = IStream_Write(a2, &v14, 4u);
        if ( v5 >= 0 )
        {
          v9 = *((_QWORD *)this + 4);
          v15 = -1;
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 72LL))(v9, &v15);
          v5 = IStream_Write(a2, &v15, 4u);
          if ( v5 >= 0 )
          {
            v10 = *((_QWORD *)this + 4);
            v14 = -1;
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 192LL))(v10, &v14);
            v5 = IStream_Write(a2, &v14, 4u);
            if ( v5 >= 0 )
            {
              v11 = *((_QWORD *)this + 4);
              v15 = -1;
              (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 144LL))(v11, &v15);
              v5 = IStream_Write(a2, &v15, 4u);
              if ( v5 >= 0 )
              {
                v12 = *((_QWORD *)this + 4);
                psz = 0;
                v17 = (*(int (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v12 + 24LL))(v12, &psz) >= 0;
                v5 = IStream_Write(a2, &v17, 4u);
                if ( v5 >= 0 )
                {
                  if ( !v17 || (v5 = IStream_WriteStr(a2, psz), v5 >= 0) )
                  {
                    v13 = *((_QWORD *)this + 4);
                    v19 = 0;
                    v18 = (*(int (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v13 + 32LL))(v13, &v19) >= 0;
                    v5 = IStream_Write(a2, &v18, 4u);
                    if ( v5 >= 0 && v18 )
                      v5 = IStream_WriteStr(a2, v19);
                    CoTaskMemFree((LPVOID)v19);
                  }
                }
                CoTaskMemFree((LPVOID)psz);
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004428c  mov     [rsp-18h+arg_10], rbx
0x180044291  mov     [rsp-18h+arg_18], rsi
0x180044296  push    rbp
0x180044297  push    rdi
0x180044298  push    r15
0x18004429a  mov     rbp, rsp
0x18004429d  sub     rsp, 80h
0x1800442a4  mov     rax, cs:__security_cookie
0x1800442ab  xor     rax, rsp
0x1800442ae  mov     [rbp+var_10], rax
0x1800442b2  mov     eax, cs:PKEY_Null.pid
0x1800442b8  lea     r8, [rbp+var_58]
0x1800442bc  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x1800442c3  mov     [rbp+var_28], eax
0x1800442c6  mov     rsi, rcx
0x1800442c9  mov     rcx, [rcx+20h]
0x1800442cd  mov     rdi, rdx
0x1800442d0  movups  [rbp+pv], xmm0
0x1800442d4  mov     [rbp+var_58], 0
0x1800442db  lea     rdx, [rbp+pv]
0x1800442df  mov     rax, [rcx]
0x1800442e2  mov     rax, [rax+30h]
0x1800442e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442eb  mov     r8d, 14h; cb
0x1800442f1  lea     rdx, [rbp+pv]; pv
0x1800442f5  mov     rcx, rdi; pstm
0x1800442f8  call    cs:__imp_IStream_Write
0x1800442fe  mov     ebx, eax
0x180044300  test    eax, eax
0x180044302  jns     short loc_18004432A
0x180044304  mov     eax, ebx
0x180044306  mov     rcx, [rbp+var_10]
0x18004430a  xor     rcx, rsp; StackCookie
0x18004430d  call    __security_check_cookie
0x180044312  lea     r11, [rsp+80h+var_s0]
0x18004431a  mov     rbx, [r11+30h]
0x18004431e  mov     rsi, [r11+38h]
0x180044322  mov     rsp, r11
0x180044325  pop     r15
0x180044327  pop     rdi
0x180044328  pop     rbp
0x180044329  retn
0x18004432a  mov     r15d, 4
0x180044330  lea     rdx, [rbp+var_58]; pv
0x180044334  mov     r8d, r15d; cb
0x180044337  mov     rcx, rdi; pstm
0x18004433a  call    cs:__imp_IStream_Write
0x180044340  mov     ebx, eax
0x180044342  test    eax, eax
0x180044344  js      short loc_180044304
0x180044346  mov     rcx, [rsi+20h]
0x18004434a  lea     rdx, [rbp+var_20]
0x18004434e  xorps   xmm0, xmm0
0x180044351  movups  [rbp+var_20], xmm0
0x180044355  mov     rax, [rcx]
0x180044358  mov     rax, [rax+68h]
0x18004435c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044361  lea     r8d, [r15+0Ch]; cb
0x180044365  mov     rcx, rdi; pstm
0x180044368  lea     rdx, [rbp+var_20]; pv
0x18004436c  call    cs:__imp_IStream_Write
0x180044372  mov     ebx, eax
0x180044374  test    eax, eax
0x180044376  js      short loc_180044304
0x180044378  mov     rcx, [rsi+20h]
0x18004437c  lea     rdx, [rbp+var_60]
0x180044380  mov     [rbp+var_60], 0FFFFFFFFh
0x180044387  mov     rax, [rcx]
0x18004438a  mov     rax, [rax+40h]
0x18004438e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044393  mov     r8d, r15d; cb
0x180044396  lea     rdx, [rbp+var_60]; pv
0x18004439a  mov     rcx, rdi; pstm
0x18004439d  call    cs:__imp_IStream_Write
0x1800443a3  mov     ebx, eax
0x1800443a5  test    eax, eax
0x1800443a7  js      loc_180044304
0x1800443ad  mov     rcx, [rsi+20h]
0x1800443b1  lea     rdx, [rbp+var_5C]
0x1800443b5  mov     [rbp+var_5C], 0FFFFFFFFh
0x1800443bc  mov     rax, [rcx]
0x1800443bf  mov     rax, [rax+48h]
0x1800443c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443c8  mov     r8d, r15d; cb
0x1800443cb  lea     rdx, [rbp+var_5C]; pv
0x1800443cf  mov     rcx, rdi; pstm
0x1800443d2  call    cs:__imp_IStream_Write
0x1800443d8  mov     ebx, eax
0x1800443da  test    eax, eax
0x1800443dc  js      loc_180044304
0x1800443e2  mov     rcx, [rsi+20h]
0x1800443e6  lea     rdx, [rbp+var_60]
0x1800443ea  mov     [rbp+var_60], 0FFFFFFFFh
0x1800443f1  mov     rax, [rcx]
0x1800443f4  mov     rax, [rax+0C0h]
0x1800443fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044400  mov     r8d, r15d; cb
0x180044403  lea     rdx, [rbp+var_60]; pv
0x180044407  mov     rcx, rdi; pstm
0x18004440a  call    cs:__imp_IStream_Write
0x180044410  mov     ebx, eax
0x180044412  test    eax, eax
0x180044414  js      loc_180044304
0x18004441a  mov     rcx, [rsi+20h]
0x18004441e  lea     rdx, [rbp+var_5C]
0x180044422  mov     [rbp+var_5C], 0FFFFFFFFh
0x180044429  mov     rax, [rcx]
0x18004442c  mov     rax, [rax+90h]
0x180044433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044438  mov     r8d, r15d; cb
0x18004443b  lea     rdx, [rbp+var_5C]; pv
0x18004443f  mov     rcx, rdi; pstm
0x180044442  call    cs:__imp_IStream_Write
0x180044448  mov     ebx, eax
0x18004444a  test    eax, eax
0x18004444c  js      loc_180044304
0x180044452  mov     rcx, [rsi+20h]
0x180044456  lea     rdx, [rbp+psz]
0x18004445a  mov     [rbp+psz], 0
0x180044462  mov     rax, [rcx]
0x180044465  mov     rax, [rax+18h]
0x180044469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004446e  not     eax
0x180044470  lea     rdx, [rbp+var_54]; pv
0x180044474  shr     eax, 1Fh
0x180044477  mov     r8d, r15d; cb
0x18004447a  mov     rcx, rdi; pstm
0x18004447d  mov     [rbp+var_54], eax
0x180044480  call    cs:__imp_IStream_Write
0x180044486  mov     ebx, eax
0x180044488  test    eax, eax
0x18004448a  js      short loc_1800444EF
0x18004448c  cmp     [rbp+var_54], 0
0x180044490  jz      short loc_1800444A5
0x180044492  mov     rdx, [rbp+psz]; psz
0x180044496  mov     rcx, rdi; pstm
0x180044499  call    cs:__imp_IStream_WriteStr
0x18004449f  mov     ebx, eax
0x1800444a1  test    eax, eax
0x1800444a3  js      short loc_1800444EF
0x1800444a5  mov     rcx, [rsi+20h]
0x1800444a9  lea     rdx, [rbp+var_48]
0x1800444ad  mov     [rbp+var_48], 0
0x1800444b5  mov     rax, [rcx]
0x1800444b8  mov     rax, [rax+20h]
0x1800444bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444c1  not     eax
0x1800444c3  lea     rdx, [rbp+var_50]; pv
0x1800444c7  shr     eax, 1Fh
0x1800444ca  mov     r8d, r15d; cb
0x1800444cd  mov     rcx, rdi; pstm
0x1800444d0  mov     [rbp+var_50], eax
0x1800444d3  call    cs:__imp_IStream_Write
0x1800444d9  mov     ebx, eax
0x1800444db  test    eax, eax
0x1800444dd  js      short loc_1800444E5
0x1800444df  cmp     [rbp+var_50], 0
0x1800444e3  jnz     short loc_1800444FE
0x1800444e5  mov     rcx, [rbp+var_48]; pv
0x1800444e9  call    cs:__imp_CoTaskMemFree
0x1800444ef  mov     rcx, [rbp+psz]; pv
0x1800444f3  call    cs:__imp_CoTaskMemFree
0x1800444f9  jmp     loc_180044304
0x1800444fe  mov     rdx, [rbp+var_48]; psz
0x180044502  mov     rcx, rdi; pstm
0x180044505  call    cs:__imp_IStream_WriteStr
0x18004450b  mov     ebx, eax
0x18004450d  jmp     short loc_1800444E5
```
