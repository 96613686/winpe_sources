# CSCardSubcontext::GetStatusChange(ushort const *,SCARD_READERSTATEW *,ulong,ulong)

- ea: `0x180009c10`
- end: `0x18000a281`
- name: `?GetStatusChange@CSCardSubcontext@@QEAAXPEBGPEAUSCARD_READERSTATEW@@KK@Z`
- size: `1649`
- prototype: `void(CSCardSubcontext *__hidden this, const unsigned __int16 *, struct SCARD_READERSTATEW *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800051b0`

## callees

- `0x180009c10`
- `0x18000bcf0`
- `0x18000bd10`
- `0x18000d640`
- `0x180015280`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180009d91`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180009d91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a007`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a007`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a015`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a015`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CSCardSubcontext::GetStatusChange(
        CSCardSubcontext *this,
        const unsigned __int16 *a2,
        struct SCARD_READERSTATEW *a3,
        unsigned int a4,
        unsigned int a5)
{
  char *v7; // r13
  unsigned int v8; // edi
  unsigned int v9; // r12d
  const WCHAR *v10; // r15
  void *v11; // rax
  unsigned int v12; // esi
  WCHAR *v13; // rax
  int v14; // r14d
  const WCHAR *v15; // rax
  const unsigned __int16 *String; // rax
  const unsigned __int16 *v17; // rbx
  __int64 v18; // r8
  struct CBuffer *v19; // r8
  __int64 v20; // rax
  size_t v21; // r14
  unsigned int v22; // esi
  char *v23; // rdi
  size_t v24; // r8
  const WCHAR *v25; // rdx
  int v26; // r14d
  const WCHAR *v27; // r15
  unsigned int v28; // esi
  char *v29; // rdi
  unsigned int v30; // ebx
  char *v31; // rdi
  int v32; // edi
  const WCHAR *v33; // rcx
  const WCHAR *v34; // rax
  ulong v35; // eax
  void *v36; // rbx
  char *v37; // rdi
  __int64 v38; // rsi
  unsigned int v39; // r12d
  struct SCARD_READERSTATEW *v40; // r15
  __int64 v41; // r14
  char *v42; // rdi
  ulong v43; // r14d
  HANDLE ProcessHeap; // rax
  char *v45; // rax
  char *v46; // r15
  char *v47; // rax
  char *v48; // r12
  char *v49; // rax
  char *v50; // rsi
  int pExceptionObject; // [rsp+40h] [rbp-61h] BYREF
  ulong v52; // [rsp+48h] [rbp-59h] BYREF
  const int *v53; // [rsp+50h] [rbp-51h]
  char *v54; // [rsp+58h] [rbp-49h]
  __int64 v55; // [rsp+60h] [rbp-41h]
  __int64 v56; // [rsp+68h] [rbp-39h] BYREF
  const int *v57; // [rsp+70h] [rbp-31h] BYREF
  void *v58; // [rsp+78h] [rbp-29h]
  __int64 v59; // [rsp+80h] [rbp-21h]
  const int *v60; // [rsp+88h] [rbp-19h]
  WCHAR *v61; // [rsp+90h] [rbp-11h]
  __int64 v62; // [rsp+98h] [rbp-9h]
  void *v63; // [rsp+A0h] [rbp-1h]
  LPVOID lpMem; // [rsp+A8h] [rbp+7h] BYREF
  const WCHAR *v65; // [rsp+B0h] [rbp+Fh]
  void *v66; // [rsp+B8h] [rbp+17h]

  lpMem = 0;
  v53 = &CBuffer::`vftable';
  v7 = 0;
  v54 = 0;
  v8 = 0;
  v55 = 0;
  v9 = 0;
  v60 = &CBuffer::`vftable';
  v10 = 0;
  v63 = 0;
  v61 = 0;
  v62 = 0;
  v57 = &CBuffer::`vftable';
  v58 = 0;
  v59 = 0;
  v11 = operator new[](0x10u);
  v66 = v11;
  if ( !v11 )
  {
    pExceptionObject = 14;
    throw (ulong *)&pExceptionObject;
  }
  v58 = v11;
  v59 = 0x1000000000LL;
  LODWORD(v56) = 0;
  if ( !a4 )
  {
    v57 = &CBuffer::`vftable';
    operator delete(v11);
    v58 = 0;
    v59 = 0;
    v60 = &CBuffer::`vftable';
    v61 = 0;
    v62 = 0;
    v53 = &CBuffer::`vftable';
    v54 = 0;
    v55 = 0;
    return;
  }
  v12 = 4 * a4;
  v52 = 4 * a4;
  if ( 4 * a4 )
  {
    v13 = (WCHAR *)operator new[](v12);
    v10 = v13;
    v63 = v13;
    if ( !v13 )
    {
      pExceptionObject = 14;
      throw (ulong *)&pExceptionObject;
    }
    v61 = v13;
    v14 = 4 * a4;
    HIDWORD(v62) = v12;
  }
  else
  {
    v14 = HIDWORD(v62);
  }
  LODWORD(v62) = v12;
  v15 = &WideCharStr;
  if ( v14 )
    v15 = v10;
  v65 = v15;
  if ( !*a2 )
  {
    pExceptionObject = -2146435063;
    throw (ulong *)&pExceptionObject;
  }
  String = FirstString(a2);
  for ( pExceptionObject = 0; ; pExceptionObject = v26 + 1 )
  {
    v17 = String;
    if ( !String )
      break;
    v18 = -1;
    do
      ++v18;
    while ( aPnp[v18] );
    if ( (unsigned int)_o__wcsnicmp(L"\\\\?PNP?\\", String) )
    {
      if ( (unsigned int)GetReaderInfo(*(_DWORD *)(*((_QWORD *)this + 5) + 28LL), v17, v19, (const void **)&v57) != 1 )
      {
        pExceptionObject = -2146435063;
        throw (ulong *)&pExceptionObject;
      }
      v21 = (unsigned int)v59;
      v27 = &WideCharStr;
      v66 = v58;
      if ( HIDWORD(v59) )
        v27 = (const WCHAR *)v58;
      if ( (_DWORD)v59 )
      {
        v28 = v59 + v8;
        if ( v8 )
        {
          if ( v9 >= v28 )
            goto LABEL_39;
          v47 = (char *)operator new[](v28);
          v48 = v47;
          if ( !v47 )
          {
            pExceptionObject = 14;
            throw (ulong *)&pExceptionObject;
          }
          memcpy_0(v47, v7, v8);
          operator delete(v7);
          v7 = v48;
          v54 = v48;
          v9 = v21 + v8;
          HIDWORD(v55) = v21 + v8;
          v24 = v21;
          v25 = v27;
        }
        else
        {
          if ( v9 < v28 )
          {
            v29 = (char *)operator new[](v28);
            if ( !v29 )
            {
              pExceptionObject = 14;
              throw (ulong *)&pExceptionObject;
            }
            if ( v7 )
              operator delete(v7);
            v7 = v29;
            v54 = v29;
            v9 = v28;
            HIDWORD(v55) = v28;
          }
          v8 = 0;
          LODWORD(v55) = 0;
LABEL_39:
          v24 = v21;
          v25 = v27;
        }
LABEL_26:
        memcpy_0(&v7[v8], v25, v24);
        v8 += v21;
        LODWORD(v55) = v8;
      }
    }
    else
    {
      v20 = -1;
      do
        ++v20;
      while ( v17[v20] );
      LODWORD(v21) = 2 * v20 + 2;
      if ( 2 * (_DWORD)v20 != -2 )
      {
        v22 = v21 + v8;
        if ( v8 )
        {
          if ( v9 < v22 )
          {
            v45 = (char *)operator new[](v22);
            v46 = v45;
            if ( !v45 )
            {
              pExceptionObject = 14;
              throw (ulong *)&pExceptionObject;
            }
            memcpy_0(v45, v7, v8);
            operator delete(v7);
            v7 = v46;
            v54 = v46;
            v9 = v21 + v8;
            HIDWORD(v55) = v21 + v8;
          }
        }
        else
        {
          if ( v9 < v22 )
          {
            v23 = (char *)operator new[](v22);
            if ( !v23 )
            {
              pExceptionObject = 14;
              throw (ulong *)&pExceptionObject;
            }
            if ( v7 )
              operator delete(v7);
            v7 = v23;
            v54 = v23;
            v9 = v22;
            HIDWORD(v55) = v22;
          }
          v8 = 0;
          LODWORD(v55) = 0;
        }
        v24 = (unsigned int)v21;
        v25 = v17;
        goto LABEL_26;
      }
    }
    v26 = pExceptionObject;
    *(_DWORD *)&v65[2 * pExceptionObject] = a3[(unsigned __int64)(unsigned int)pExceptionObject].dwCurrentState;
    String = NextString(v17);
  }
  v30 = v8 + 2;
  if ( v8 )
  {
    if ( v9 < v30 )
    {
      v49 = (char *)operator new[](v30);
      v50 = v49;
      if ( !v49 )
      {
        pExceptionObject = 14;
        throw (ulong *)&pExceptionObject;
      }
      memcpy_0(v49, v7, v8);
      operator delete(v7);
      v7 = v50;
      v54 = v50;
      v9 = v8 + 2;
      HIDWORD(v55) = v8 + 2;
    }
  }
  else
  {
    if ( v9 < v30 )
    {
      v31 = (char *)operator new[](v30);
      if ( !v31 )
      {
        pExceptionObject = 14;
        throw (ulong *)&pExceptionObject;
      }
      if ( v7 )
        operator delete(v7);
      v7 = v31;
      v54 = v31;
      v9 = v30;
      HIDWORD(v55) = v30;
    }
    v8 = 0;
    LODWORD(v55) = 0;
  }
  *(_WORD *)&v7[v8] = 0;
  v32 = v8 + 2;
  LODWORD(v55) = v32;
  v33 = &WideCharStr;
  v34 = &WideCharStr;
  if ( HIDWORD(v62) )
    v34 = (const WCHAR *)v63;
  if ( v9 )
    LODWORD(v33) = (_DWORD)v7;
  v35 = CalRpcGetStatusChange(
          *((_QWORD *)this + 14),
          a5,
          (int)v33,
          v32,
          (__int64)v34,
          v52 >> 2,
          (__int64)&lpMem,
          (__int64)&v56,
          pExceptionObject,
          v52,
          (int)v53,
          (int)v54,
          v55);
  v52 = v35;
  if ( v35 )
  {
    v52 = v35;
    throw &v52;
  }
  v36 = lpMem;
  v37 = (char *)lpMem;
  v38 = 0;
  v39 = v56;
  while ( 1 )
  {
    if ( (unsigned int)v38 >= a4 )
    {
      v43 = v52;
      goto LABEL_57;
    }
    v40 = &a3[(unsigned __int64)(unsigned int)v38];
    v40->dwEventState = *(_DWORD *)&v65[2 * v38];
    v41 = (unsigned __int8)*v37;
    if ( (unsigned int)v41 >= v39 )
      break;
    v42 = v37 + 1;
    *(_OWORD *)v40->rgbAtr = 0;
    *(_OWORD *)&v40->rgbAtr[16] = 0;
    *(_DWORD *)&v40->rgbAtr[32] = 0;
    memcpy_0(v40->rgbAtr, v42, (unsigned int)v41);
    v40->cbAtr = v41;
    v39 += -1 - v41;
    LODWORD(v56) = v39;
    v37 = &v42[v41];
    v38 = (unsigned int)(v38 + 1);
  }
  v43 = -2146435053;
LABEL_57:
  if ( v36 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v36);
  }
  if ( v43 )
  {
    v52 = v43;
    throw &v52;
  }
  v57 = &CBuffer::`vftable';
  if ( v66 )
    operator delete(v66);
  v58 = 0;
  v59 = 0;
  v60 = &CBuffer::`vftable';
  if ( v63 )
    operator delete(v63);
  v61 = 0;
  v62 = 0;
  v53 = &CBuffer::`vftable';
  if ( v7 )
    operator delete(v7);
  v54 = 0;
  v55 = 0;
}

```

## disassembly

```asm
0x180009c10  mov     [rsp-8+arg_8], rbx
0x180009c15  mov     [rsp-8+arg_18], r9d
0x180009c1a  mov     [rsp-8+arg_10], r8
0x180009c1f  mov     [rsp-8+arg_0], rcx
0x180009c24  push    rbp
0x180009c25  push    rsi
0x180009c26  push    rdi
0x180009c27  push    r12
0x180009c29  push    r13
0x180009c2b  push    r14
0x180009c2d  push    r15
0x180009c2f  lea     rbp, [rsp-1Fh]
0x180009c34  sub     rsp, 0C0h
0x180009c3b  mov     r14d, r9d
0x180009c3e  mov     rbx, rdx
0x180009c41  xor     eax, eax
0x180009c43  mov     [rbp+4Fh+lpMem], rax
0x180009c47  lea     rcx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180009c4e  mov     [rbp+4Fh+var_A0], rcx
0x180009c52  mov     r13d, eax
0x180009c55  mov     [rbp+4Fh+var_98], rax
0x180009c59  mov     edi, eax
0x180009c5b  mov     [rbp+4Fh+var_90], rax
0x180009c5f  mov     r12d, eax
0x180009c62  mov     [rbp+4Fh+var_68], rcx
0x180009c66  mov     r15d, eax
0x180009c69  mov     [rbp+4Fh+var_50], rax
0x180009c6d  mov     [rbp+4Fh+var_60], rax
0x180009c71  mov     [rbp+4Fh+var_58], rax
0x180009c75  mov     [rbp+4Fh+var_80], rcx
0x180009c79  mov     [rbp+4Fh+var_78], rax
0x180009c7d  mov     [rbp+4Fh+var_70], rax
0x180009c81  mov     ecx, 10h; unsigned __int64
0x180009c86  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009c8b  mov     [rbp+4Fh+var_38], rax
0x180009c8f  test    rax, rax
0x180009c92  jz      loc_18000A180
0x180009c98  mov     [rbp+4Fh+var_78], rax
0x180009c9c  mov     dword ptr [rbp+4Fh+var_70+4], 10h
0x180009ca3  xor     ecx, ecx
0x180009ca5  mov     dword ptr [rbp+4Fh+var_70], ecx
0x180009ca8  mov     dword ptr [rbp+4Fh+var_88], ecx
0x180009cab  test    r14d, r14d
0x180009cae  jnz     short loc_180009D00
0x180009cb0  lea     rdi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180009cb7  mov     [rbp+4Fh+var_80], rdi
0x180009cbb  mov     rcx, rax; void *
0x180009cbe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009cc3  xor     eax, eax
0x180009cc5  mov     [rbp+4Fh+var_78], rax
0x180009cc9  mov     [rbp+4Fh+var_70], rax
0x180009ccd  mov     [rbp+4Fh+var_68], rdi
0x180009cd1  mov     [rbp+4Fh+var_60], rax
0x180009cd5  mov     [rbp+4Fh+var_58], rax
0x180009cd9  mov     [rbp+4Fh+var_A0], rdi
0x180009cdd  mov     [rbp+4Fh+var_98], rax
0x180009ce1  mov     [rbp+4Fh+var_90], rax
0x180009ce5  mov     rbx, [rsp+0F0h+arg_8]
0x180009ced  add     rsp, 0C0h
0x180009cf4  pop     r15
0x180009cf6  pop     r14
0x180009cf8  pop     r13
0x180009cfa  pop     r12
0x180009cfc  pop     rdi
0x180009cfd  pop     rsi
0x180009cfe  pop     rbp
0x180009cff  retn
0x180009d00  lea     esi, ds:0[r14*4]
0x180009d08  mov     [rbp+4Fh+var_A8], esi
0x180009d0b  test    esi, esi
0x180009d0d  jz      loc_18000A154
0x180009d13  mov     ecx, esi; unsigned __int64
0x180009d15  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009d1a  mov     r15, rax
0x180009d1d  mov     [rbp+4Fh+var_50], rax
0x180009d21  test    rax, rax
0x180009d24  jz      loc_18000A198
0x180009d2a  mov     [rbp+4Fh+var_60], rax
0x180009d2e  mov     r14d, esi
0x180009d31  mov     dword ptr [rbp+4Fh+var_58+4], esi
0x180009d34  xor     ecx, ecx
0x180009d36  mov     dword ptr [rbp+4Fh+var_58], ecx
0x180009d39  mov     dword ptr [rbp+4Fh+var_58], esi
0x180009d3c  lea     rsi, WideCharStr
0x180009d43  mov     rax, rsi
0x180009d46  test    r14d, r14d
0x180009d49  cmovnz  rax, r15
0x180009d4d  mov     [rbp+4Fh+var_40], rax
0x180009d51  cmp     cx, [rbx]
0x180009d54  jz      loc_18000A1B0
0x180009d5a  mov     rcx, rbx; unsigned __int16 *
0x180009d5d  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x180009d62  mov     [rbp+4Fh+pExceptionObject], 0
0x180009d69  mov     rbx, rax
0x180009d6c  test    rax, rax
0x180009d6f  jz      loc_180009EE1
0x180009d75  mov     rcx, cs:off_180034170; "\\\\?PNP?\\"
0x180009d7c  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180009d83  inc     r8
0x180009d86  cmp     word ptr [rcx+r8*2], 0
0x180009d8c  jnz     short loc_180009D83
0x180009d8e  mov     rdx, rbx
0x180009d91  call    cs:__imp__o__wcsnicmp
0x180009d97  test    eax, eax
0x180009d99  jnz     loc_180009E57
0x180009d9f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009da6  nop     word ptr [rax+rax+00000000h]
0x180009db0  lea     rax, [rax+1]
0x180009db4  cmp     word ptr [rbx+rax*2], 0
0x180009db9  jnz     short loc_180009DB0
0x180009dbb  lea     r14d, ds:2[rax*2]
0x180009dc3  test    r14d, r14d
0x180009dc6  jz      short loc_180009E28
0x180009dc8  lea     esi, [r14+rdi]
0x180009dcc  test    edi, edi
0x180009dce  jnz     loc_18000A082
0x180009dd4  cmp     r12d, esi
0x180009dd7  jnb     short loc_180009E06
0x180009dd9  mov     ecx, esi; unsigned __int64
0x180009ddb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009de0  mov     rdi, rax
0x180009de3  test    rax, rax
0x180009de6  jz      loc_18000A1E0
0x180009dec  test    r13, r13
0x180009def  jz      short loc_180009DF9
0x180009df1  mov     rcx, r13; void *
0x180009df4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009df9  mov     r13, rdi
0x180009dfc  mov     [rbp+4Fh+var_98], rdi
0x180009e00  mov     r12d, esi
0x180009e03  mov     dword ptr [rbp+4Fh+var_90+4], esi
0x180009e06  xor     edi, edi
0x180009e08  mov     dword ptr [rbp+4Fh+var_90], edi
0x180009e0b  mov     r8d, r14d; Size
0x180009e0e  mov     rdx, rbx; Src
0x180009e11  mov     ecx, edi
0x180009e13  add     rcx, r13; void *
0x180009e16  call    memcpy_0
0x180009e1b  add     edi, r14d
0x180009e1e  lea     rsi, WideCharStr
0x180009e25  mov     dword ptr [rbp+4Fh+var_90], edi
0x180009e28  mov     r14d, [rbp+4Fh+pExceptionObject]
0x180009e2c  mov     eax, r14d
0x180009e2f  shl     rax, 6
0x180009e33  mov     rdx, [rbp+4Fh+arg_10]
0x180009e37  mov     eax, [rax+rdx+10h]
0x180009e3b  mov     rdx, [rbp+4Fh+var_40]
0x180009e3f  mov     [rdx+r14*4], eax
0x180009e43  mov     rcx, rbx; unsigned __int16 *
0x180009e46  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x180009e4b  inc     r14d
0x180009e4e  mov     [rbp+4Fh+pExceptionObject], r14d
0x180009e52  jmp     loc_180009D69
0x180009e57  mov     rax, [rbp+4Fh+arg_0]
0x180009e5b  mov     rcx, [rax+28h]
0x180009e5f  lea     r9, [rbp+4Fh+var_80]; struct CBuffer *
0x180009e63  mov     rdx, rbx; unsigned __int16 *
0x180009e66  mov     ecx, [rcx+1Ch]; unsigned int
0x180009e69  call    ?GetReaderInfo@@YAHKPEBGPEAVCBuffer@@1@Z; GetReaderInfo(ulong,ushort const *,CBuffer *,CBuffer *)
0x180009e6e  cmp     eax, 1
0x180009e71  jnz     loc_18000A15D
0x180009e77  mov     r14d, dword ptr [rbp+4Fh+var_70]
0x180009e7b  mov     r15, rsi
0x180009e7e  mov     rax, [rbp+4Fh+var_78]
0x180009e82  mov     [rbp+4Fh+var_38], rax
0x180009e86  cmp     dword ptr [rbp+4Fh+var_70+4], 0
0x180009e8a  cmova   r15, rax
0x180009e8e  test    r14d, r14d
0x180009e91  jz      short loc_180009E28
0x180009e93  lea     esi, [r14+rdi]
0x180009e97  test    edi, edi
0x180009e99  jnz     loc_18000A0C6
0x180009e9f  cmp     r12d, esi
0x180009ea2  jnb     short loc_180009ED1
0x180009ea4  mov     ecx, esi; unsigned __int64
0x180009ea6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009eab  mov     rdi, rax
0x180009eae  test    rax, rax
0x180009eb1  jz      loc_18000A210
0x180009eb7  test    r13, r13
0x180009eba  jz      short loc_180009EC4
0x180009ebc  mov     rcx, r13; void *
0x180009ebf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009ec4  mov     r13, rdi
0x180009ec7  mov     [rbp+4Fh+var_98], rdi
0x180009ecb  mov     r12d, esi
0x180009ece  mov     dword ptr [rbp+4Fh+var_90+4], esi
0x180009ed1  xor     edi, edi
0x180009ed3  mov     dword ptr [rbp+4Fh+var_90], edi
0x180009ed6  mov     r8, r14
0x180009ed9  mov     rdx, r15
0x180009edc  jmp     loc_180009E11
0x180009ee1  lea     ebx, [rdi+2]
0x180009ee4  test    edi, edi
0x180009ee6  jnz     loc_18000A110
0x180009eec  cmp     r12d, ebx
0x180009eef  jnb     short loc_180009F1E
0x180009ef1  mov     ecx, ebx; unsigned __int64
0x180009ef3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009ef8  mov     rdi, rax
0x180009efb  test    rax, rax
0x180009efe  jz      loc_18000A240
0x180009f04  test    r13, r13
0x180009f07  jz      short loc_180009F11
0x180009f09  mov     rcx, r13; void *
0x180009f0c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f11  mov     r13, rdi
0x180009f14  mov     [rbp+4Fh+var_98], rdi
0x180009f18  mov     r12d, ebx
0x180009f1b  mov     dword ptr [rbp+4Fh+var_90+4], ebx
0x180009f1e  xor     edi, edi
0x180009f20  mov     dword ptr [rbp+4Fh+var_90], edi
0x180009f23  mov     ecx, edi
0x180009f25  xor     eax, eax
0x180009f27  mov     [rcx+r13], ax
0x180009f2c  add     edi, 2
0x180009f2f  mov     dword ptr [rbp+4Fh+var_90], edi
0x180009f32  mov     esi, [rbp+4Fh+var_A8]
0x180009f35  shr     esi, 2
0x180009f38  lea     rcx, WideCharStr
0x180009f3f  mov     rax, rcx
0x180009f42  cmp     dword ptr [rbp+4Fh+var_58+4], 0
0x180009f46  cmova   rax, [rbp+4Fh+var_50]
0x180009f4b  test    r12d, r12d
0x180009f4e  cmovnz  rcx, r13
0x180009f52  lea     rdx, [rbp+4Fh+var_88]
0x180009f56  mov     [rsp+0F0h+var_B8], rdx; __int64
0x180009f5b  lea     rdx, [rbp+4Fh+lpMem]
0x180009f5f  mov     [rsp+0F0h+var_C0], rdx; __int64
0x180009f64  mov     [rsp+0F0h+var_C8], esi; int
0x180009f68  mov     [rsp+0F0h+var_D0], rax; __int64
0x180009f6d  mov     r9d, edi; int
0x180009f70  mov     r8, rcx; int
0x180009f73  mov     edx, [rbp+4Fh+arg_20]; int
0x180009f76  mov     rax, [rbp+4Fh+arg_0]
0x180009f7a  mov     rcx, [rax+70h]; int
0x180009f7e  call    CalRpcGetStatusChange
0x180009f83  mov     [rbp+4Fh+var_A8], eax
0x180009f86  test    eax, eax
0x180009f88  jnz     loc_18000A258
0x180009f8e  mov     rbx, [rbp+4Fh+lpMem]
0x180009f92  mov     rdi, rbx
0x180009f95  xor     esi, esi
0x180009f97  mov     r12d, dword ptr [rbp+4Fh+var_88]
0x180009f9b  cmp     esi, [rbp+4Fh+arg_18]
0x180009f9e  jnb     short loc_180009FFE
0x180009fa0  mov     r15d, esi
0x180009fa3  shl     r15, 6
0x180009fa7  add     r15, [rbp+4Fh+arg_10]
0x180009fab  mov     rax, [rbp+4Fh+var_40]
0x180009faf  mov     eax, [rax+rsi*4]
0x180009fb2  mov     [r15+14h], eax
0x180009fb6  movzx   r14d, byte ptr [rdi]
0x180009fba  cmp     r14d, r12d
0x180009fbd  jnb     loc_18000A175
0x180009fc3  inc     rdi
0x180009fc6  lea     rcx, [r15+1Ch]; void *
0x180009fca  xorps   xmm0, xmm0
0x180009fcd  xor     eax, eax
0x180009fcf  movups  xmmword ptr [rcx], xmm0
0x180009fd2  movups  xmmword ptr [rcx+10h], xmm0
0x180009fd6  mov     [rcx+20h], eax
0x180009fd9  mov     r8d, r14d; Size
0x180009fdc  mov     rdx, rdi; Src
0x180009fdf  call    memcpy_0
0x180009fe4  mov     [r15+18h], r14d
0x180009fe8  mov     eax, 0FFFFFFFFh
0x180009fed  sub     eax, r14d
0x180009ff0  add     r12d, eax
0x180009ff3  mov     dword ptr [rbp+4Fh+var_88], r12d
0x180009ff7  add     rdi, r14
0x180009ffa  inc     esi
0x180009ffc  jmp     short loc_180009F9B
0x180009ffe  mov     r14d, [rbp+4Fh+var_A8]
0x18000a002  test    rbx, rbx
0x18000a005  jz      short loc_18000A01B
0x18000a007  call    cs:__imp_GetProcessHeap
0x18000a00d  mov     rcx, rax; hHeap
0x18000a010  mov     r8, rbx; lpMem
0x18000a013  xor     edx, edx; dwFlags
0x18000a015  call    cs:__imp_HeapFree
0x18000a01b  test    r14d, r14d
0x18000a01e  jnz     loc_18000A26C
0x18000a024  lea     rdi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000a02b  mov     [rbp+4Fh+var_80], rdi
0x18000a02f  mov     rcx, [rbp+4Fh+var_38]; void *
0x18000a033  test    rcx, rcx
0x18000a036  jz      short loc_18000A03D
0x18000a038  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a03d  xor     ebx, ebx
0x18000a03f  mov     [rbp+4Fh+var_78], rbx
0x18000a043  mov     [rbp+4Fh+var_70], rbx
0x18000a047  mov     [rbp+4Fh+var_68], rdi
0x18000a04b  mov     r15, [rbp+4Fh+var_50]
0x18000a04f  test    r15, r15
0x18000a052  jz      short loc_18000A05C
0x18000a054  mov     rcx, r15; void *
0x18000a057  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a05c  mov     [rbp+4Fh+var_60], rbx
0x18000a060  mov     [rbp+4Fh+var_58], rbx
  ... truncated ...
```
