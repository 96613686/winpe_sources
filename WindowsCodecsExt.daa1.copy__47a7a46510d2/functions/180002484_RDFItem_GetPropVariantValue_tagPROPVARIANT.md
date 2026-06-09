# RDFItem::GetPropVariantValue(tagPROPVARIANT *)

- ea: `0x180002484`
- end: `0x18000258b`
- name: `?GetPropVariantValue@RDFItem@@QEAAJPEAUtagPROPVARIANT@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(RDFItem *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800011e0`
- `0x1800017a0`
- `0x180001b50`
- `0x1800022a8`

## callees

- `0x180002484`
- `0x180002594`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000256f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000256f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002523`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002523`
- `OLEAUT32!__imp_SysStringLen` at `0x180002510`
- `OLEAUT32!__imp_SysStringLen` at `0x180002510`

## pseudocode

```c
__int64 __fastcall RDFItem::GetPropVariantValue(RDFItem *this, struct tagPROPVARIANT *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // ecx
  unsigned __int64 v7; // rax
  UINT v9; // eax
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rbp
  int v13; // eax

  if ( (*((_BYTE *)this + 8) & 4) != 0 )
  {
    a2->vt = 13;
    v5 = 0;
    a2->hVal.QuadPart = *((_QWORD *)this + 6);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
    return v5;
  }
  v4 = (*(__int64 (__fastcall **)(RDFItem *))(*(_QWORD *)this + 16LL))(this);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v9 = SysStringLen(*((BSTR *)this + 4));
    if ( v9 + 1 >= v9 && (v7 = 2LL * (v9 + 1), v7 <= 0xFFFFFFFF) )
    {
      v10 = (unsigned int)v7;
      v11 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v7);
      v12 = v11;
      if ( v11 )
      {
        v13 = StringCchCopyW(v11, v10 >> 1, *((const unsigned __int16 **)this + 4));
        v5 = v13;
        if ( v13 >= 0 )
        {
          a2->vt = 31;
          a2->hVal.QuadPart = (LONGLONG)v12;
        }
        else
        {
          if ( g_doStackCaptures )
            DoStackCapture(v13);
          CoTaskMemFree(v12);
        }
        return v5;
      }
      v5 = -2147024882;
    }
    else
    {
      v5 = -2147024362;
    }
    if ( !g_doStackCaptures )
      return v5;
    v6 = v5;
    goto LABEL_5;
  }
  if ( g_doStackCaptures )
  {
    v6 = v4;
LABEL_5:
    DoStackCapture(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x180002484  push    rbx
0x180002486  push    rbp
0x180002487  push    rsi
0x180002488  push    r14
0x18000248a  sub     rsp, 28h
0x18000248e  test    byte ptr [rcx+8], 4
0x180002492  mov     r14, rdx
0x180002495  mov     rsi, rcx
0x180002498  jnz     short loc_1800024EB
0x18000249a  mov     rax, [rcx]
0x18000249d  mov     rax, [rax+10h]
0x1800024a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024a6  mov     ebx, eax
0x1800024a8  test    eax, eax
0x1800024aa  jns     short loc_18000250C
0x1800024ac  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800024b3  jz      short loc_1800024DF
0x1800024b5  mov     ecx, eax; int
0x1800024b7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800024bc  jmp     short loc_1800024DF
0x1800024be  mov     eax, ecx
0x1800024c0  mov     ecx, 0FFFFFFFFh
0x1800024c5  add     rax, rax
0x1800024c8  cmp     rax, rcx
0x1800024cb  jbe     short loc_18000251F
0x1800024cd  mov     ebx, 80070216h
0x1800024d2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800024d9  jnz     loc_18000257A
0x1800024df  mov     eax, ebx
0x1800024e1  add     rsp, 28h
0x1800024e5  pop     r14
0x1800024e7  pop     rsi
0x1800024e8  pop     rbp
0x1800024e9  pop     rbx
0x1800024ea  retn
0x1800024eb  mov     word ptr [rdx], 0Dh
0x1800024f0  xor     ebx, ebx
0x1800024f2  mov     rcx, [rcx+30h]
0x1800024f6  mov     [rdx+8], rcx
0x1800024fa  mov     rcx, [rsi+30h]
0x1800024fe  mov     rdx, [rcx]
0x180002501  mov     rax, [rdx+8]
0x180002505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000250a  jmp     short loc_1800024DF
0x18000250c  mov     rcx, [rsi+20h]; pbstr
0x180002510  call    cs:__imp_SysStringLen
0x180002516  lea     ecx, [rax+1]
0x180002519  cmp     ecx, eax
0x18000251b  jb      short loc_1800024CD
0x18000251d  jmp     short loc_1800024BE
0x18000251f  mov     ecx, eax; cb
0x180002521  mov     ebx, eax
0x180002523  call    cs:__imp_CoTaskMemAlloc
0x180002529  mov     rbp, rax
0x18000252c  test    rax, rax
0x18000252f  jz      short loc_180002581
0x180002531  mov     r8, [rsi+20h]; unsigned __int16 *
0x180002535  mov     rcx, rax; unsigned __int16 *
0x180002538  shr     rbx, 1
0x18000253b  mov     rdx, rbx; unsigned __int64
0x18000253e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002543  mov     ebx, eax
0x180002545  test    eax, eax
0x180002547  jns     short loc_180002556
0x180002549  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180002550  jnz     short loc_180002565
0x180002552  test    eax, eax
0x180002554  js      short loc_18000256C
0x180002556  mov     word ptr [r14], 1Fh
0x18000255c  mov     [r14+8], rbp
0x180002560  jmp     loc_1800024DF
0x180002565  mov     ecx, eax; int
0x180002567  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000256c  mov     rcx, rbp; pv
0x18000256f  call    cs:__imp_CoTaskMemFree
0x180002575  jmp     loc_1800024DF
0x18000257a  mov     ecx, ebx
0x18000257c  jmp     loc_1800024B7
0x180002581  mov     ebx, 8007000Eh
0x180002586  jmp     loc_1800024D2
```
