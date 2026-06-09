# ATL::CAxHostWindow::TranslateUrl(ulong,ushort *,ushort * *)

- ea: `0x180011370`
- end: `0x18001148d`
- name: `?TranslateUrl@CAxHostWindow@ATL@@UEAAJKPEAGPEAPEAG@Z`
- size: `285`
- prototype: `int(ATL::CAxHostWindow *__hidden this, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003858`
- `0x180005704`
- `0x180011370`
- `0x180035010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180011412`
- `ole32!CoTaskMemAlloc` at `0x180011412`
- `OLEAUT32!__imp_SysAllocString` at `0x180011435`
- `OLEAUT32!__imp_SysAllocString` at `0x180011435`
- `OLEAUT32!__imp_SysFreeString` at `0x1800113e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180011425`
- `OLEAUT32!__imp_SysFreeString` at `0x180011467`
- `OLEAUT32!__imp_SysFreeString` at `0x1800113e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180011425`
- `OLEAUT32!__imp_SysFreeString` at `0x180011467`
- `OLEAUT32!__imp_SysStringLen` at `0x1800113f2`
- `OLEAUT32!__imp_SysStringLen` at `0x180011401`
- `OLEAUT32!__imp_SysStringLen` at `0x1800113f2`
- `OLEAUT32!__imp_SysStringLen` at `0x180011401`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::TranslateUrl(
        ATL::CAxHostWindow *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  __int64 *v7; // rdi
  int v8; // edi
  __int64 v9; // rbp
  OLECHAR *v10; // rbx
  SIZE_T v11; // rbx
  unsigned __int16 *v12; // rax
  unsigned __int64 v13; // [rsp+20h] [rbp-28h]
  BSTR pbstr; // [rsp+68h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v7 = (__int64 *)*((_QWORD *)this + 13);
  if ( v7 )
  {
    pbstr = 0;
    v9 = *v7;
    if ( a3 )
    {
      v10 = SysAllocString(a3);
      if ( !v10 )
        ATL::AtlThrowImpl(-2147024882);
    }
    else
    {
      v10 = 0;
    }
    v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, OLECHAR *, BSTR *))(v9 + 160))(v7, a2, v10, &pbstr);
    SysFreeString(v10);
    if ( v8 >= 0 && SysStringLen(pbstr) )
    {
      v11 = 2 * SysStringLen(pbstr) + 2;
      v12 = (unsigned __int16 *)CoTaskMemAlloc(v11);
      *a4 = v12;
      if ( !v12 )
      {
        SysFreeString(pbstr);
        return 2147942414LL;
      }
      ATL::Checked::memcpy_s((ATL::Checked *)v12, (void *)v11, (unsigned __int64)pbstr, (const void *)v11, v13);
    }
    else
    {
      v8 = 1;
    }
    SysFreeString(pbstr);
  }
  else
  {
    return 1;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180011370  mov     [rsp+arg_0], rbx
0x180011375  mov     [rsp+arg_8], rbp
0x18001137a  push    rsi
0x18001137b  push    rdi
0x18001137c  push    r14
0x18001137e  sub     rsp, 30h
0x180011382  mov     rsi, r9
0x180011385  mov     r14d, edx
0x180011388  test    r9, r9
0x18001138b  jnz     short loc_180011397
0x18001138d  mov     eax, 80004003h
0x180011392  jmp     loc_18001146F
0x180011397  mov     qword ptr [r9], 0
0x18001139e  mov     rdi, [rcx+68h]
0x1800113a2  test    rdi, rdi
0x1800113a5  jnz     short loc_1800113B1
0x1800113a7  mov     edi, 1
0x1800113ac  jmp     loc_18001146D
0x1800113b1  mov     [rsp+48h+pbstr], 0
0x1800113ba  mov     rbp, [rdi]
0x1800113bd  test    r8, r8
0x1800113c0  jnz     short loc_180011432
0x1800113c2  xor     ebx, ebx
0x1800113c4  mov     rax, [rbp+0A0h]
0x1800113cb  lea     r9, [rsp+48h+pbstr]
0x1800113d0  mov     r8, rbx
0x1800113d3  mov     edx, r14d
0x1800113d6  mov     rcx, rdi
0x1800113d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113de  mov     rcx, rbx; bstrString
0x1800113e1  mov     edi, eax
0x1800113e3  call    cs:__imp_SysFreeString
0x1800113e9  test    edi, edi
0x1800113eb  js      short loc_18001145D
0x1800113ed  mov     rcx, [rsp+48h+pbstr]; pbstr
0x1800113f2  call    cs:__imp_SysStringLen
0x1800113f8  test    eax, eax
0x1800113fa  jz      short loc_18001145D
0x1800113fc  mov     rcx, [rsp+48h+pbstr]; pbstr
0x180011401  call    cs:__imp_SysStringLen
0x180011407  lea     eax, ds:2[rax*2]
0x18001140e  mov     ecx, eax; cb
0x180011410  mov     ebx, eax
0x180011412  call    cs:__imp_CoTaskMemAlloc
0x180011418  mov     [rsi], rax
0x18001141b  test    rax, rax
0x18001141e  jnz     short loc_180011448
0x180011420  mov     rcx, [rsp+48h+pbstr]; bstrString
0x180011425  call    cs:__imp_SysFreeString
0x18001142b  mov     eax, 8007000Eh
0x180011430  jmp     short loc_18001146F
0x180011432  mov     rcx, r8; psz
0x180011435  call    cs:__imp_SysAllocString
0x18001143b  mov     rbx, rax
0x18001143e  test    rax, rax
0x180011441  jz      short loc_180011482
0x180011443  jmp     loc_1800113C4
0x180011448  mov     r8, [rsp+48h+pbstr]; unsigned __int64
0x18001144d  mov     r9, rbx; void *
0x180011450  mov     rdx, rbx; void *
0x180011453  mov     rcx, rax; this
0x180011456  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18001145b  jmp     short loc_180011462
0x18001145d  mov     edi, 1
0x180011462  mov     rcx, [rsp+48h+pbstr]; bstrString
0x180011467  call    cs:__imp_SysFreeString
0x18001146d  mov     eax, edi
0x18001146f  mov     rbx, [rsp+48h+arg_0]
0x180011474  mov     rbp, [rsp+48h+arg_8]
0x180011479  add     rsp, 30h
0x18001147d  pop     r14
0x18001147f  pop     rdi
0x180011480  pop     rsi
0x180011481  retn
0x180011482  mov     ecx, 8007000Eh; int
0x180011487  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
