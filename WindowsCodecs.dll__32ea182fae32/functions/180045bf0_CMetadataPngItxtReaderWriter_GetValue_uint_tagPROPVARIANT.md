# CMetadataPngItxtReaderWriter::GetValue(uint,tagPROPVARIANT *)

- ea: `0x180045bf0`
- end: `0x180045e55`
- name: `?GetValue@CMetadataPngItxtReaderWriter@@MEAAJIPEAUtagPROPVARIANT@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(CMetadataPngItxtReaderWriter *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001dd10`
- `0x180020e14`
- `0x180041dec`
- `0x180045bf0`
- `0x180045fbc`
- `0x1800bb784`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045cdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045da4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045de3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045cdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045da4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045de3`

## pseudocode

```c
__int64 __fastcall CMetadataPngItxtReaderWriter::GetValue(
        CMetadataPngItxtReaderWriter *this,
        int a2,
        struct tagPROPVARIANT *a3)
{
  unsigned int v5; // ebx
  ULONGLONG v6; // rsi
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // ecx
  int EmbeddedXMP; // eax
  unsigned __int64 v14; // rax
  unsigned __int16 *v15; // rax
  const unsigned __int16 *v16; // r8
  __int64 v17; // rdx
  unsigned __int16 *v18; // rcx
  unsigned __int64 v19; // rax
  unsigned __int16 *v20; // rax
  int v21; // eax
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rsi
  char *v24; // rax
  const char *v25; // r8
  unsigned __int64 v26; // rdx
  ULONGLONG pullResult; // [rsp+58h] [rbp+20h] BYREF

  pullResult = 0;
  v5 = 0;
  v6 = 0;
  v7 = a2 - 1;
  if ( !v7 )
  {
    v24 = (char *)CoTaskMemAlloc(*((_QWORD *)this + 20) + 1LL);
    a3->hVal.QuadPart = (LONGLONG)v24;
    if ( !v24 )
      goto LABEL_20;
    v25 = (const char *)*((_QWORD *)this + 19);
    if ( !v25 )
    {
      *v24 = 0;
      goto LABEL_46;
    }
    v26 = *((_QWORD *)this + 20) + 1LL;
    goto LABEL_41;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    a3->cVal = *((_BYTE *)this + 168);
    return v5;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v22 = *((_QWORD *)this + 23);
    v23 = v22 + 1;
    if ( v22 + 1 < v22 )
      goto LABEL_24;
    v24 = (char *)CoTaskMemAlloc(v22 + 1);
    a3->hVal.QuadPart = (LONGLONG)v24;
    if ( !v24 )
      goto LABEL_20;
    v25 = (const char *)*((_QWORD *)this + 22);
    if ( !v25 )
    {
      *v24 = 0;
      return v5;
    }
    v26 = v23;
LABEL_41:
    v21 = StringCchCopyA(v24, v26, v25);
    goto LABEL_42;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 != 1 )
      {
        v5 = -2147024809;
        goto LABEL_8;
      }
      EmbeddedXMP = CMetadataPngItxtReaderWriter::GetEmbeddedXMP(this, (struct IUnknown **)&pullResult);
      v5 = EmbeddedXMP;
      if ( EmbeddedXMP >= 0 )
      {
        v6 = pullResult;
        a3->vt = 13;
        a3->hVal.QuadPart = v6;
        (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)v6 + 8LL))(v6);
      }
      else
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(EmbeddedXMP);
        v6 = pullResult;
      }
LABEL_46:
      if ( v6 )
        (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)v6 + 16LL))(v6);
      return v5;
    }
    v14 = *((_QWORD *)this + 27);
    if ( v14 + 1 >= v14 )
    {
      pullResult = v14 + 1;
      if ( ULongLongMult(v14 + 1, 2u, &pullResult) >= 0 )
      {
        v15 = (unsigned __int16 *)CoTaskMemAlloc(pullResult);
        a3->hVal.QuadPart = (LONGLONG)v15;
        if ( !v15 )
        {
LABEL_20:
          v5 = -2147024882;
          goto LABEL_8;
        }
        v16 = (const unsigned __int16 *)*((_QWORD *)this + 26);
        if ( !v16 )
        {
          v15[*((_QWORD *)this + 27)] = 0;
          return v5;
        }
        v17 = *((_QWORD *)this + 27);
        v18 = v15;
        goto LABEL_30;
      }
    }
LABEL_24:
    v5 = -2147024362;
LABEL_8:
    if ( (_DWORD)g_doStackCaptures )
    {
      v12 = v5;
LABEL_10:
      DoStackCapture(v12);
      return v5;
    }
    return v5;
  }
  v19 = *((_QWORD *)this + 25);
  if ( v19 + 1 < v19 )
    goto LABEL_24;
  pullResult = v19 + 1;
  if ( ULongLongMult(v19 + 1, 2u, &pullResult) < 0 )
    goto LABEL_24;
  v20 = (unsigned __int16 *)CoTaskMemAlloc(pullResult);
  a3->hVal.QuadPart = (LONGLONG)v20;
  v18 = v20;
  if ( !v20 )
    goto LABEL_20;
  v16 = (const unsigned __int16 *)*((_QWORD *)this + 24);
  if ( !v16 )
  {
    *v20 = 0;
    return v5;
  }
  v17 = *((_QWORD *)this + 25);
LABEL_30:
  v21 = StringCchCopyW(v18, v17 + 1, v16);
LABEL_42:
  v5 = v21;
  if ( v21 < 0 && (_DWORD)g_doStackCaptures )
  {
    v12 = v21;
    goto LABEL_10;
  }
  return v5;
}

```

## disassembly

```asm
0x180045bf0  mov     [rsp+arg_0], rbx
0x180045bf5  mov     [rsp+arg_8], rbp
0x180045bfa  push    rsi
0x180045bfb  push    rdi
0x180045bfc  push    r14
0x180045bfe  sub     rsp, 20h
0x180045c02  xor     ebp, ebp
0x180045c04  mov     r14, r8
0x180045c07  mov     [rsp+38h+pullResult], rbp
0x180045c0c  mov     rdi, rcx
0x180045c0f  mov     ebx, ebp
0x180045c11  mov     esi, ebp
0x180045c13  sub     edx, 1
0x180045c16  jz      loc_180045DD9
0x180045c1c  sub     edx, 1
0x180045c1f  jz      loc_180045DCD
0x180045c25  sub     edx, 1
0x180045c28  jz      loc_180045D8D
0x180045c2e  sub     edx, 1
0x180045c31  jz      loc_180045D26
0x180045c37  sub     edx, 1
0x180045c3a  jz      short loc_180045CAE
0x180045c3c  cmp     edx, 1
0x180045c3f  jz      short loc_180045C5E
0x180045c41  mov     ebx, 80070057h
0x180045c46  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180045c4c  jz      loc_180045E40
0x180045c52  mov     ecx, ebx; int
0x180045c54  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180045c59  jmp     loc_180045E40
0x180045c5e  lea     rdx, [rsp+38h+pullResult]; struct IUnknown **
0x180045c63  call    ?GetEmbeddedXMP@CMetadataPngItxtReaderWriter@@IEAAJPEAPEAUIUnknown@@@Z; CMetadataPngItxtReaderWriter::GetEmbeddedXMP(IUnknown * *)
0x180045c68  mov     ebx, eax
0x180045c6a  test    eax, eax
0x180045c6c  jns     short loc_180045C8B
0x180045c6e  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180045c74  jz      short loc_180045C87
0x180045c76  mov     ecx, eax; int
0x180045c78  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180045c7d  mov     rsi, [rsp+38h+pullResult]
0x180045c82  jmp     loc_180045E2C
0x180045c87  test    eax, eax
0x180045c89  js      short loc_180045C7D
0x180045c8b  mov     rsi, [rsp+38h+pullResult]
0x180045c90  mov     word ptr [r14], 0Dh
0x180045c96  mov     rcx, rsi
0x180045c99  mov     [r14+8], rsi
0x180045c9d  mov     rax, [rsi]
0x180045ca0  mov     rax, [rax+8]
0x180045ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ca9  jmp     loc_180045E2C
0x180045cae  mov     rax, [rcx+0D8h]
0x180045cb5  lea     rcx, [rax+1]; ullMultiplicand
0x180045cb9  cmp     rcx, rax
0x180045cbc  jb      short loc_180045D1C
0x180045cbe  lea     r8, [rsp+38h+pullResult]; pullResult
0x180045cc3  mov     [rsp+38h+pullResult], rcx
0x180045cc8  mov     edx, 2; ullMultiplier
0x180045ccd  call    ULongLongMult
0x180045cd2  test    eax, eax
0x180045cd4  js      short loc_180045D1C
0x180045cd6  mov     rcx, [rsp+38h+pullResult]; cb
0x180045cdb  call    cs:__imp_CoTaskMemAlloc
0x180045ce1  mov     [r14+8], rax
0x180045ce5  test    rax, rax
0x180045ce8  jnz     short loc_180045CF4
0x180045cea  mov     ebx, 8007000Eh
0x180045cef  jmp     loc_180045C46
0x180045cf4  mov     r8, [rdi+0D0h]
0x180045cfb  test    r8, r8
0x180045cfe  jz      short loc_180045D0C
0x180045d00  mov     rdx, [rdi+0D8h]
0x180045d07  mov     rcx, rax
0x180045d0a  jmp     short loc_180045D78
0x180045d0c  mov     rcx, [rdi+0D8h]
0x180045d13  mov     [rax+rcx*2], bp
0x180045d17  jmp     loc_180045E40
0x180045d1c  mov     ebx, 80070216h
0x180045d21  jmp     loc_180045C46
0x180045d26  mov     rax, [rcx+0C8h]
0x180045d2d  lea     rcx, [rax+1]; ullMultiplicand
0x180045d31  cmp     rcx, rax
0x180045d34  jb      short loc_180045D1C
0x180045d36  lea     r8, [rsp+38h+pullResult]; pullResult
0x180045d3b  mov     [rsp+38h+pullResult], rcx
0x180045d40  mov     edx, 2; ullMultiplier
0x180045d45  call    ULongLongMult
0x180045d4a  test    eax, eax
0x180045d4c  js      short loc_180045D1C
0x180045d4e  mov     rcx, [rsp+38h+pullResult]; cb
0x180045d53  call    cs:__imp_CoTaskMemAlloc
0x180045d59  mov     [r14+8], rax
0x180045d5d  mov     rcx, rax; unsigned __int16 *
0x180045d60  test    rax, rax
0x180045d63  jz      short loc_180045CEA
0x180045d65  mov     r8, [rdi+0C0h]; unsigned __int16 *
0x180045d6c  test    r8, r8
0x180045d6f  jz      short loc_180045D85
0x180045d71  mov     rdx, [rdi+0C8h]
0x180045d78  inc     rdx; unsigned __int64
0x180045d7b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180045d80  jmp     loc_180045E14
0x180045d85  mov     [rax], bp
0x180045d88  jmp     loc_180045E40
0x180045d8d  mov     rax, [rcx+0B8h]
0x180045d94  lea     rsi, [rax+1]
0x180045d98  cmp     rsi, rax
0x180045d9b  jb      loc_180045D1C
0x180045da1  mov     rcx, rsi; cb
0x180045da4  call    cs:__imp_CoTaskMemAlloc
0x180045daa  mov     [r14+8], rax
0x180045dae  test    rax, rax
0x180045db1  jz      loc_180045CEA
0x180045db7  mov     r8, [rdi+0B0h]
0x180045dbe  test    r8, r8
0x180045dc1  jz      short loc_180045DC8
0x180045dc3  mov     rdx, rsi
0x180045dc6  jmp     short loc_180045E0C
0x180045dc8  mov     [rax], bpl
0x180045dcb  jmp     short loc_180045E40
0x180045dcd  mov     al, [rcx+0A8h]
0x180045dd3  mov     [r8+8], al
0x180045dd7  jmp     short loc_180045E40
0x180045dd9  mov     rcx, [rcx+0A0h]
0x180045de0  inc     rcx; cb
0x180045de3  call    cs:__imp_CoTaskMemAlloc
0x180045de9  mov     [r14+8], rax
0x180045ded  test    rax, rax
0x180045df0  jz      loc_180045CEA
0x180045df6  mov     r8, [rdi+98h]; char *
0x180045dfd  test    r8, r8
0x180045e00  jz      short loc_180045E29
0x180045e02  mov     rdx, [rdi+0A0h]
0x180045e09  inc     rdx; unsigned __int64
0x180045e0c  mov     rcx, rax; char *
0x180045e0f  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180045e14  mov     ebx, eax
0x180045e16  test    eax, eax
0x180045e18  jns     short loc_180045E40
0x180045e1a  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180045e20  jz      short loc_180045E40
0x180045e22  mov     ecx, eax
0x180045e24  jmp     loc_180045C54
0x180045e29  mov     [rax], bpl
0x180045e2c  test    rsi, rsi
0x180045e2f  jz      short loc_180045E40
0x180045e31  mov     rdx, [rsi]
0x180045e34  mov     rcx, rsi
0x180045e37  mov     rax, [rdx+10h]
0x180045e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e40  mov     rbp, [rsp+38h+arg_8]
0x180045e45  mov     eax, ebx
0x180045e47  mov     rbx, [rsp+38h+arg_0]
0x180045e4c  add     rsp, 20h
0x180045e50  pop     r14
0x180045e52  pop     rdi
0x180045e53  pop     rsi
0x180045e54  retn
```
