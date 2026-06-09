# CMetadataPngItxtReaderWriter::GetValue(uint,tagPROPVARIANT *)

- ea: `0x18004ffe0`
- end: `0x180050262`
- name: `?GetValue@CMetadataPngItxtReaderWriter@@MEAAJIPEAUtagPROPVARIANT@@@Z`
- size: `642`
- prototype: `__int64 __fastcall(CMetadataPngItxtReaderWriter *this, int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003573c`
- `0x180042ae8`
- `0x18004f894`
- `0x18004ffe0`
- `0x18005066c`
- `0x1800bd9d4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800500cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050149`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800501a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800501e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800500cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050149`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800501a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800501e9`

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
0x18004ffe0  mov     [rsp+arg_0], rbx
0x18004ffe5  mov     [rsp+arg_8], rbp
0x18004ffea  push    rsi
0x18004ffeb  push    rdi
0x18004ffec  push    r14
0x18004ffee  sub     rsp, 20h
0x18004fff2  xor     ebp, ebp
0x18004fff4  mov     r14, r8
0x18004fff7  mov     [rsp+38h+pullResult], rbp
0x18004fffc  mov     rdi, rcx
0x18004ffff  mov     ebx, ebp
0x180050001  mov     esi, ebp
0x180050003  sub     edx, 1
0x180050006  jz      loc_1800501DF
0x18005000c  sub     edx, 1
0x18005000f  jz      loc_1800501D3
0x180050015  sub     edx, 1
0x180050018  jz      loc_18005018D
0x18005001e  sub     edx, 1
0x180050021  jz      loc_18005011C
0x180050027  sub     edx, 1
0x18005002a  jz      short loc_18005009E
0x18005002c  cmp     edx, 1
0x18005002f  jz      short loc_18005004E
0x180050031  mov     ebx, 80070057h
0x180050036  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x18005003c  jz      loc_18005024C
0x180050042  mov     ecx, ebx; int
0x180050044  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180050049  jmp     loc_18005024C
0x18005004e  lea     rdx, [rsp+38h+pullResult]; struct IUnknown **
0x180050053  call    ?GetEmbeddedXMP@CMetadataPngItxtReaderWriter@@IEAAJPEAPEAUIUnknown@@@Z; CMetadataPngItxtReaderWriter::GetEmbeddedXMP(IUnknown * *)
0x180050058  mov     ebx, eax
0x18005005a  test    eax, eax
0x18005005c  jns     short loc_18005007B
0x18005005e  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180050064  jz      short loc_180050077
0x180050066  mov     ecx, eax; int
0x180050068  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18005006d  mov     rsi, [rsp+38h+pullResult]
0x180050072  jmp     loc_180050238
0x180050077  test    eax, eax
0x180050079  js      short loc_18005006D
0x18005007b  mov     rsi, [rsp+38h+pullResult]
0x180050080  mov     word ptr [r14], 0Dh
0x180050086  mov     rcx, rsi
0x180050089  mov     [r14+8], rsi
0x18005008d  mov     rax, [rsi]
0x180050090  mov     rax, [rax+8]
0x180050094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050099  jmp     loc_180050238
0x18005009e  mov     rax, [rcx+0D8h]
0x1800500a5  lea     rcx, [rax+1]; ullMultiplicand
0x1800500a9  cmp     rcx, rax
0x1800500ac  jb      short loc_180050112
0x1800500ae  lea     r8, [rsp+38h+pullResult]; pullResult
0x1800500b3  mov     [rsp+38h+pullResult], rcx
0x1800500b8  mov     edx, 2; ullMultiplier
0x1800500bd  call    ULongLongMult
0x1800500c2  test    eax, eax
0x1800500c4  js      short loc_180050112
0x1800500c6  mov     rcx, [rsp+38h+pullResult]; cb
0x1800500cb  call    cs:__imp_CoTaskMemAlloc
0x1800500d2  nop     dword ptr [rax+rax+00h]
0x1800500d7  mov     [r14+8], rax
0x1800500db  test    rax, rax
0x1800500de  jnz     short loc_1800500EA
0x1800500e0  mov     ebx, 8007000Eh
0x1800500e5  jmp     loc_180050036
0x1800500ea  mov     r8, [rdi+0D0h]
0x1800500f1  test    r8, r8
0x1800500f4  jz      short loc_180050102
0x1800500f6  mov     rdx, [rdi+0D8h]
0x1800500fd  mov     rcx, rax
0x180050100  jmp     short loc_180050178
0x180050102  mov     rcx, [rdi+0D8h]
0x180050109  mov     [rax+rcx*2], bp
0x18005010d  jmp     loc_18005024C
0x180050112  mov     ebx, 80070216h
0x180050117  jmp     loc_180050036
0x18005011c  mov     rax, [rcx+0C8h]
0x180050123  lea     rcx, [rax+1]; ullMultiplicand
0x180050127  cmp     rcx, rax
0x18005012a  jb      short loc_180050112
0x18005012c  lea     r8, [rsp+38h+pullResult]; pullResult
0x180050131  mov     [rsp+38h+pullResult], rcx
0x180050136  mov     edx, 2; ullMultiplier
0x18005013b  call    ULongLongMult
0x180050140  test    eax, eax
0x180050142  js      short loc_180050112
0x180050144  mov     rcx, [rsp+38h+pullResult]; cb
0x180050149  call    cs:__imp_CoTaskMemAlloc
0x180050150  nop     dword ptr [rax+rax+00h]
0x180050155  mov     [r14+8], rax
0x180050159  mov     rcx, rax; unsigned __int16 *
0x18005015c  test    rax, rax
0x18005015f  jz      loc_1800500E0
0x180050165  mov     r8, [rdi+0C0h]; unsigned __int16 *
0x18005016c  test    r8, r8
0x18005016f  jz      short loc_180050185
0x180050171  mov     rdx, [rdi+0C8h]
0x180050178  inc     rdx; unsigned __int64
0x18005017b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180050180  jmp     loc_180050220
0x180050185  mov     [rax], bp
0x180050188  jmp     loc_18005024C
0x18005018d  mov     rax, [rcx+0B8h]
0x180050194  lea     rsi, [rax+1]
0x180050198  cmp     rsi, rax
0x18005019b  jb      loc_180050112
0x1800501a1  mov     rcx, rsi; cb
0x1800501a4  call    cs:__imp_CoTaskMemAlloc
0x1800501ab  nop     dword ptr [rax+rax+00h]
0x1800501b0  mov     [r14+8], rax
0x1800501b4  test    rax, rax
0x1800501b7  jz      loc_1800500E0
0x1800501bd  mov     r8, [rdi+0B0h]
0x1800501c4  test    r8, r8
0x1800501c7  jz      short loc_1800501CE
0x1800501c9  mov     rdx, rsi
0x1800501cc  jmp     short loc_180050218
0x1800501ce  mov     [rax], bpl
0x1800501d1  jmp     short loc_18005024C
0x1800501d3  mov     al, [rcx+0A8h]
0x1800501d9  mov     [r8+8], al
0x1800501dd  jmp     short loc_18005024C
0x1800501df  mov     rcx, [rcx+0A0h]
0x1800501e6  inc     rcx; cb
0x1800501e9  call    cs:__imp_CoTaskMemAlloc
0x1800501f0  nop     dword ptr [rax+rax+00h]
0x1800501f5  mov     [r14+8], rax
0x1800501f9  test    rax, rax
0x1800501fc  jz      loc_1800500E0
0x180050202  mov     r8, [rdi+98h]; char *
0x180050209  test    r8, r8
0x18005020c  jz      short loc_180050235
0x18005020e  mov     rdx, [rdi+0A0h]
0x180050215  inc     rdx; unsigned __int64
0x180050218  mov     rcx, rax; char *
0x18005021b  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180050220  mov     ebx, eax
0x180050222  test    eax, eax
0x180050224  jns     short loc_18005024C
0x180050226  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x18005022c  jz      short loc_18005024C
0x18005022e  mov     ecx, eax
0x180050230  jmp     loc_180050044
0x180050235  mov     [rax], bpl
0x180050238  test    rsi, rsi
0x18005023b  jz      short loc_18005024C
0x18005023d  mov     rdx, [rsi]
0x180050240  mov     rcx, rsi
0x180050243  mov     rax, [rdx+10h]
0x180050247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005024c  mov     rbp, [rsp+38h+arg_8]
0x180050251  mov     eax, ebx
0x180050253  mov     rbx, [rsp+38h+arg_0]
0x180050258  add     rsp, 20h
0x18005025c  pop     r14
0x18005025e  pop     rdi
0x18005025f  pop     rsi
0x180050260  retn
```
