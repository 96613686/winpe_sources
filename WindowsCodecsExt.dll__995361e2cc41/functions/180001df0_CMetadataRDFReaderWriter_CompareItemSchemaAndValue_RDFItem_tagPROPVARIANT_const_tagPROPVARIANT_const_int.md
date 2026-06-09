# CMetadataRDFReaderWriter::CompareItemSchemaAndValue(RDFItem *,tagPROPVARIANT const *,tagPROPVARIANT const *,int *)

- ea: `0x180001df0`
- end: `0x1800020d5`
- name: `?CompareItemSchemaAndValue@CMetadataRDFReaderWriter@@KAJPEAVRDFItem@@PEBUtagPROPVARIANT@@1PEAH@Z`
- size: `741`
- prototype: `__int64 __fastcall(struct RDFItem *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001630`
- `0x1800017a0`
- `0x180001b50`

## callees

- `0x180001df0`
- `0x1800171c4`
- `0x180032da9`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180001fdc`
- `OLEAUT32!__imp_SysStringLen` at `0x180001fdc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001ffa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001ffa`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::CompareItemSchemaAndValue(
        struct RDFItem *a1,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        int *a4)
{
  struct RDFItem *v5; // rdi
  const WCHAR *lpString2; // r12
  BSTR bstrVal; // rax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  unsigned __int64 cchCount2; // r15
  const wchar_t *v12; // rbp
  int v13; // eax
  unsigned int v14; // r14d
  const wchar_t *v15; // rsi
  BOOL v16; // eax
  unsigned __int16 *v17; // rax
  int v18; // ecx
  int v19; // edx
  __int64 v20; // rbx
  __int64 v21; // rdi
  UINT v22; // eax

  *a4 = 0;
  v5 = a1;
  if ( a3 && a3->vt != 31 )
  {
    if ( g_doStackCaptures )
      DoStackCapture(-2147024809);
    return 2147942487LL;
  }
  lpString2 = a3->bstrVal;
  if ( lpString2 )
  {
    bstrVal = a3->bstrVal;
    v8 = 0x7FFFFFFF;
    do
    {
      if ( !*bstrVal )
        break;
      ++bstrVal;
      --v8;
    }
    while ( v8 );
    v9 = -2147024809;
    if ( v8 )
    {
      v9 = 0;
      cchCount2 = 0x7FFFFFFF - v8;
    }
    else
    {
      cchCount2 = 0;
    }
    if ( v8 )
    {
      if ( cchCount2 > 0xFFFFFFFF )
      {
        if ( g_doStackCaptures )
          DoStackCapture(-2147024362);
        return 2147942934LL;
      }
      if ( !a2 )
        goto LABEL_40;
      if ( a2->vt != 31 )
        goto LABEL_40;
      v12 = a2->bstrVal;
      if ( !v12 )
        goto LABEL_40;
      v13 = (*(__int64 (__fastcall **)(struct RDFItem *))(*(_QWORD *)v5 + 88LL))(v5);
      v14 = v13;
      if ( v13 < 0 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_37;
        goto LABEL_45;
      }
      v15 = (const wchar_t *)*((_QWORD *)v5 + 8);
      v16 = 0;
      if ( v15 )
      {
        v17 = (unsigned __int16 *)*((_QWORD *)v5 + 8);
        do
        {
          v18 = *(unsigned __int16 *)((char *)v17 + (char *)v12 - (char *)v15);
          v19 = *v17 - v18;
          if ( v19 )
            break;
          ++v17;
        }
        while ( v18 );
        if ( v19 )
        {
          v20 = -1;
          v21 = -1;
          do
            ++v21;
          while ( v15[v21] );
          do
            ++v20;
          while ( v12[v20] );
          v16 = (_DWORD)v20 == (_DWORD)v21 + 1
             && !wcsncmp_0(v15, v12, (unsigned int)v21)
             && v12[(unsigned int)v21] == 47
             || (_DWORD)v21 == (_DWORD)v20 + 1
             && !wcsncmp_0(v15, v12, (unsigned int)v20)
             && v15[(unsigned int)v20] == 47;
          v5 = a1;
        }
        else
        {
          v16 = 1;
        }
        if ( v16 )
        {
LABEL_40:
          v13 = (*(__int64 (__fastcall **)(struct RDFItem *))(*(_QWORD *)v5 + 96LL))(v5);
          v14 = v13;
          if ( v13 < 0 )
          {
            if ( !g_doStackCaptures )
            {
LABEL_37:
              if ( g_doStackCaptures )
                DoStackCapture(v14);
              return v14;
            }
LABEL_45:
            DoStackCapture(v13);
            goto LABEL_37;
          }
          v22 = SysStringLen(*((BSTR *)v5 + 7));
          if ( CompareStringW(0x400u, 0, *((PCNZWCH *)v5 + 7), v22, lpString2, cchCount2) == 2 )
          {
            *a4 = 1;
            return v14;
          }
          v16 = 0;
        }
      }
      *a4 = v16;
      if ( (v14 & 0x80000000) != 0 )
        goto LABEL_37;
      return v14;
    }
  }
  else
  {
    v9 = -2147024809;
  }
  if ( g_doStackCaptures )
    DoStackCapture(v9);
  return v9;
}

```

## disassembly

```asm
0x180001df0  mov     [rsp+arg_0], rcx
0x180001df5  push    rbx
0x180001df6  push    rdi
0x180001df7  push    r13
0x180001df9  sub     rsp, 40h
0x180001dfd  mov     dword ptr [r9], 0
0x180001e04  mov     r13, r9
0x180001e07  mov     rdi, rcx
0x180001e0a  test    r8, r8
0x180001e0d  jnz     loc_180001E94
0x180001e13  mov     [rsp+58h+arg_18], r12
0x180001e18  mov     r12, [r8+8]
0x180001e1c  mov     [rsp+58h+var_28], r15
0x180001e21  test    r12, r12
0x180001e24  jz      loc_180002040
0x180001e2a  mov     r15d, 7FFFFFFFh
0x180001e30  mov     rax, r12
0x180001e33  mov     ecx, r15d
0x180001e36  cmp     word ptr [rax], 0
0x180001e3a  jz      short loc_180001E46
0x180001e3c  add     rax, 2
0x180001e40  sub     rcx, 1
0x180001e44  jnz     short loc_180001E36
0x180001e46  xor     eax, eax
0x180001e48  mov     ebx, 80070057h
0x180001e4d  test    rcx, rcx
0x180001e50  cmovnz  ebx, eax
0x180001e53  jz      loc_180002038
0x180001e59  sub     r15, rcx
0x180001e5c  test    rcx, rcx
0x180001e5f  jz      loc_180002045
0x180001e65  mov     eax, 0FFFFFFFFh
0x180001e6a  cmp     r15, rax
0x180001e6d  jbe     short loc_180001EBC
0x180001e6f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001e76  jnz     loc_1800020C6
0x180001e7c  mov     eax, 80070216h
0x180001e81  mov     r12, [rsp+58h+arg_18]
0x180001e86  mov     r15, [rsp+58h+var_28]
0x180001e8b  add     rsp, 40h
0x180001e8f  pop     r13
0x180001e91  pop     rdi
0x180001e92  pop     rbx
0x180001e93  retn
0x180001e94  cmp     word ptr [r8], 1Fh
0x180001e99  jz      loc_180001E13
0x180001e9f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001ea6  mov     ebx, 80070057h
0x180001eab  jnz     loc_18000205E
0x180001eb1  mov     eax, ebx
0x180001eb3  add     rsp, 40h
0x180001eb7  pop     r13
0x180001eb9  pop     rdi
0x180001eba  pop     rbx
0x180001ebb  retn
0x180001ebc  mov     [rsp+58h+var_20], r14
0x180001ec1  mov     [rsp+58h+arg_8], rbp
0x180001ec6  mov     [rsp+58h+arg_10], rsi
0x180001ecb  test    rdx, rdx
0x180001ece  jz      loc_180001FB5
0x180001ed4  cmp     word ptr [rdx], 1Fh
0x180001ed8  jnz     loc_180001FB5
0x180001ede  mov     rbp, [rdx+8]
0x180001ee2  test    rbp, rbp
0x180001ee5  jz      loc_180001FB5
0x180001eeb  mov     rax, [rdi]
0x180001eee  mov     rcx, rdi
0x180001ef1  mov     rax, [rax+58h]
0x180001ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001efa  mov     r14d, eax
0x180001efd  test    eax, eax
0x180001eff  jns     short loc_180001F16
0x180001f01  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001f08  jnz     loc_180002019
0x180001f0e  test    eax, eax
0x180001f10  js      loc_180001F95
0x180001f16  mov     rsi, [rdi+40h]
0x180001f1a  xor     eax, eax
0x180001f1c  test    rsi, rsi
0x180001f1f  jz      short loc_180001F8C
0x180001f21  mov     r8, rbp
0x180001f24  mov     rax, rsi
0x180001f27  sub     r8, rsi
0x180001f2a  nop     word ptr [rax+rax+00h]
0x180001f30  movzx   edx, word ptr [rax]
0x180001f33  movzx   ecx, word ptr [rax+r8]
0x180001f38  sub     edx, ecx
0x180001f3a  jnz     short loc_180001F44
0x180001f3c  add     rax, 2
0x180001f40  test    ecx, ecx
0x180001f42  jnz     short loc_180001F30
0x180001f44  test    edx, edx
0x180001f46  jz      loc_18000206A
0x180001f4c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180001f53  mov     rdi, rbx
0x180001f56  inc     rdi
0x180001f59  cmp     word ptr [rsi+rdi*2], 0
0x180001f5e  jnz     short loc_180001F56
0x180001f60  inc     rbx
0x180001f63  cmp     word ptr [rbp+rbx*2+0], 0
0x180001f69  jnz     short loc_180001F60
0x180001f6b  lea     eax, [rdi+1]
0x180001f6e  cmp     ebx, eax
0x180001f70  jz      loc_180002074
0x180001f76  lea     eax, [rbx+1]
0x180001f79  cmp     edi, eax
0x180001f7b  jz      loc_180002099
0x180001f81  xor     eax, eax
0x180001f83  mov     rdi, [rsp+58h+arg_0]
0x180001f88  test    eax, eax
0x180001f8a  jnz     short loc_180001FB5
0x180001f8c  mov     [r13+0], eax
0x180001f90  test    r14d, r14d
0x180001f93  jns     short loc_180001F9E
0x180001f95  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001f9c  jnz     short loc_18000200F
0x180001f9e  mov     rsi, [rsp+58h+arg_10]
0x180001fa3  mov     eax, r14d
0x180001fa6  mov     r14, [rsp+58h+var_20]
0x180001fab  mov     rbp, [rsp+58h+arg_8]
0x180001fb0  jmp     loc_180001E81
0x180001fb5  mov     rax, [rdi]
0x180001fb8  mov     rcx, rdi
0x180001fbb  mov     rax, [rax+60h]
0x180001fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc4  mov     r14d, eax
0x180001fc7  test    eax, eax
0x180001fc9  jns     short loc_180001FD8
0x180001fcb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001fd2  jnz     short loc_18000202C
0x180001fd4  test    eax, eax
0x180001fd6  js      short loc_180001F95
0x180001fd8  mov     rcx, [rdi+38h]; pbstr
0x180001fdc  call    cs:__imp_SysStringLen
0x180001fe2  mov     r8, [rdi+38h]; lpString1
0x180001fe6  xor     edx, edx; dwCmpFlags
0x180001fe8  mov     r9d, eax; cchCount1
0x180001feb  mov     [rsp+58h+cchCount2], r15d; cchCount2
0x180001ff0  mov     ecx, 400h; Locale
0x180001ff5  mov     [rsp+58h+lpString2], r12; lpString2
0x180001ffa  call    cs:__imp_CompareStringW
0x180002000  cmp     eax, 2
0x180002003  jnz     short loc_180002025
0x180002005  mov     dword ptr [r13+0], 1
0x18000200d  jmp     short loc_180001F9E
0x18000200f  mov     ecx, r14d; int
0x180002012  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180002017  jmp     short loc_180001F9E
0x180002019  mov     ecx, eax; int
0x18000201b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180002020  jmp     loc_180001F95
0x180002025  xor     eax, eax
0x180002027  jmp     loc_180001F8C
0x18000202c  mov     ecx, eax; int
0x18000202e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180002033  jmp     loc_180001F95
0x180002038  xor     r15d, r15d
0x18000203b  jmp     loc_180001E5C
0x180002040  mov     ebx, 80070057h
0x180002045  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000204c  jnz     short loc_180002055
0x18000204e  mov     eax, ebx
0x180002050  jmp     loc_180001E81
0x180002055  mov     ecx, ebx; int
0x180002057  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000205c  jmp     short loc_18000204E
0x18000205e  mov     ecx, ebx; int
0x180002060  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180002065  jmp     loc_180001EB1
0x18000206a  mov     eax, 1
0x18000206f  jmp     loc_180001F88
0x180002074  mov     r8d, edi; MaxCount
0x180002077  mov     rdx, rbp; String2
0x18000207a  mov     rcx, rsi; String1
0x18000207d  call    wcsncmp_0
0x180002082  test    eax, eax
0x180002084  jnz     loc_180001F76
0x18000208a  mov     eax, edi
0x18000208c  cmp     word ptr [rbp+rax*2+0], 2Fh ; '/'
0x180002092  jz      short loc_1800020BC
0x180002094  jmp     loc_180001F76
0x180002099  mov     r8d, ebx; MaxCount
0x18000209c  mov     rdx, rbp; String2
0x18000209f  mov     rcx, rsi; String1
0x1800020a2  call    wcsncmp_0
0x1800020a7  test    eax, eax
0x1800020a9  jnz     loc_180001F81
0x1800020af  mov     eax, ebx
0x1800020b1  cmp     word ptr [rsi+rax*2], 2Fh ; '/'
0x1800020b6  jnz     loc_180001F81
0x1800020bc  mov     eax, 1
0x1800020c1  jmp     loc_180001F83
0x1800020c6  mov     ecx, 80070216h; int
0x1800020cb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800020d0  jmp     loc_180001E7C
```
