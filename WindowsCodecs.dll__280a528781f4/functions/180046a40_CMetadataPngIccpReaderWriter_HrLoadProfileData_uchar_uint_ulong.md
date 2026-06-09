# CMetadataPngIccpReaderWriter::HrLoadProfileData(uchar *,uint,ulong *)

- ea: `0x180046a40`
- end: `0x180046d25`
- name: `?HrLoadProfileData@CMetadataPngIccpReaderWriter@@MEAAJPEAEIPEAK@Z`
- size: `741`
- prototype: `__int64 __fastcall(CMetadataPngIccpReaderWriter *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046630`

## callees

- `0x180046350`
- `0x180046a40`
- `0x180046d30`
- `0x180047e68`
- `0x18004bcf0`
- `0x18004c6ec`
- `0x1800bb784`
- `0x1800e3c04`
- `0x18017b528`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046a8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046b48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046c9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046a8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046b48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046c9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046bf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046cce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046d1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046bf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046cce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046d1a`

## pseudocode

```c
__int64 __fastcall CMetadataPngIccpReaderWriter::HrLoadProfileData(
        CMetadataPngIccpReaderWriter *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rbx
  void *v9; // r15
  __int64 v10; // rax
  __int64 v11; // rsi
  int v12; // eax
  char *v13; // rax
  char *v14; // rbx
  int v15; // ebx
  int v16; // ecx
  const void *v17; // rdx
  __int64 v18; // rax
  size_t v19; // r8
  unsigned __int64 v20; // r8
  unsigned __int8 *v21; // rdx
  int v22; // eax
  void *v24; // rcx
  char *v25; // rax
  char *v26; // r14
  const void *v27; // rdx
  __int64 v28; // rax
  size_t v29; // r8
  unsigned __int8 *v30; // [rsp+20h] [rbp-49h] BYREF
  unsigned int v31; // [rsp+28h] [rbp-41h]
  void *v32; // [rsp+30h] [rbp-39h]
  int v33; // [rsp+38h] [rbp-31h]
  SIZE_T cb; // [rsp+3Ch] [rbp-2Dh]
  __int64 v35; // [rsp+48h] [rbp-21h]
  __int64 (__fastcall *v36)(_QWORD, _QWORD, _QWORD); // [rsp+50h] [rbp-19h]
  void (__fastcall *v37)(__int64, __int64); // [rsp+58h] [rbp-11h]
  __int64 v38; // [rsp+60h] [rbp-9h]

  v4 = 2LL * a3;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  if ( v4 > 0xFFFFFFFF )
    LODWORD(v4) = a3;
  v9 = CoTaskMemAlloc((unsigned int)v4);
  if ( v9 )
  {
    memset_0(&v30, 0, 0x58u);
    v38 = 0;
    v36 = zcalloc;
    v37 = (void (__fastcall *)(__int64, __int64))&zcfree;
    v10 = zcalloc(0, 1, 9072);
    v11 = v10;
    if ( v10 )
    {
      v35 = v10;
      *(_QWORD *)(v10 + 64) = 0;
      *(_QWORD *)v10 = &v30;
      *(_DWORD *)(v10 + 8) = 16180;
      *(_DWORD *)(v10 + 32) = 1;
      if ( !(unsigned int)inflateReset2(&v30, 15) )
      {
        v30 = a2;
        v31 = a3;
LABEL_7:
        v33 = v4;
        v32 = v9;
        while ( 1 )
        {
          v12 = inflate(&v30, 2);
          if ( v12 == 1 )
          {
            v13 = (char *)CoTaskMemAlloc((unsigned int)cb);
            v14 = v13;
            if ( v13 )
            {
              v17 = (const void *)*((_QWORD *)this + 21);
              if ( v17 )
              {
                memcpy_0(v13, v17, *((_QWORD *)this + 22));
                CoTaskMemFree(*((LPVOID *)this + 21));
              }
              v18 = *((_QWORD *)this + 22);
              v19 = (unsigned int)cb - v18;
              *((_QWORD *)this + 21) = v14;
              memcpy_0(&v14[v18], v9, v19);
              v20 = (unsigned int)cb;
              v21 = (unsigned __int8 *)*((_QWORD *)this + 21);
              *((_QWORD *)this + 22) = (unsigned int)cb;
              v22 = CMetadataPngIccpReaderWriter::HrCheckProfileData(this, v21, v20);
              v15 = v22;
              if ( v22 >= 0 )
              {
                *a4 = a3;
                goto LABEL_17;
              }
              if ( !(_DWORD)g_doStackCaptures )
                goto LABEL_17;
              v16 = v22;
            }
            else
            {
LABEL_10:
              v15 = -2147024882;
              if ( !(_DWORD)g_doStackCaptures )
                goto LABEL_17;
              v16 = -2147024882;
            }
            DoStackCapture(v16);
            goto LABEL_17;
          }
          if ( v12 )
            break;
          if ( !v33 )
          {
            v25 = (char *)CoTaskMemAlloc((unsigned int)cb);
            v26 = v25;
            if ( !v25 )
              goto LABEL_10;
            v27 = (const void *)*((_QWORD *)this + 21);
            if ( v27 )
            {
              memcpy_0(v25, v27, *((_QWORD *)this + 22));
              CoTaskMemFree(*((LPVOID *)this + 21));
            }
            v28 = *((_QWORD *)this + 22);
            v29 = (unsigned int)cb - v28;
            *((_QWORD *)this + 21) = v26;
            memcpy_0(&v26[v28], v9, v29);
            *((_QWORD *)this + 22) = (unsigned int)cb;
            goto LABEL_7;
          }
        }
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(-2003292304);
        v15 = -2003292304;
LABEL_17:
        if ( !(unsigned int)inflateEnd(&v30) || v15 < 0 )
        {
LABEL_23:
          CoTaskMemFree(v9);
          if ( v15 >= 0 )
            return (unsigned int)v15;
          goto LABEL_33;
        }
LABEL_22:
        v15 = -2003292304;
        goto LABEL_23;
      }
      v37(v38, v11);
      v35 = 0;
    }
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2003292304);
    goto LABEL_22;
  }
  v15 = -2147024882;
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(-2147024882);
LABEL_33:
  v24 = (void *)*((_QWORD *)this + 21);
  if ( v24 )
  {
    CoTaskMemFree(v24);
    *((_QWORD *)this + 21) = 0;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180046a40  push    rbp
0x180046a42  push    rbx
0x180046a43  push    rsi
0x180046a44  push    rdi
0x180046a45  push    r12
0x180046a47  push    r13
0x180046a49  push    r14
0x180046a4b  push    r15
0x180046a4d  lea     rbp, [rsp-1Fh]
0x180046a52  sub     rsp, 88h
0x180046a59  xor     esi, esi
0x180046a5b  mov     ebx, r8d
0x180046a5e  add     rbx, rbx
0x180046a61  mov     r12d, r8d
0x180046a64  mov     eax, 0FFFFFFFFh
0x180046a69  mov     [rcx+0A8h], rsi
0x180046a70  mov     [rcx+0B0h], rsi
0x180046a77  mov     r13, r9
0x180046a7a  mov     r14, rdx
0x180046a7d  mov     rdi, rcx
0x180046a80  cmp     rbx, rax
0x180046a83  jbe     short loc_180046A88
0x180046a85  mov     ebx, r12d
0x180046a88  mov     ecx, ebx; cb
0x180046a8a  call    cs:__imp_CoTaskMemAlloc
0x180046a90  mov     r15, rax
0x180046a93  test    rax, rax
0x180046a96  jz      loc_180046C3D
0x180046a9c  xor     edx, edx; Val
0x180046a9e  lea     rcx, [rbp+57h+var_A0]; void *
0x180046aa2  lea     r8d, [rdx+58h]; Size
0x180046aa6  call    memset_0
0x180046aab  lea     rax, zcalloc
0x180046ab2  mov     [rbp+57h+var_60], rsi
0x180046ab6  mov     [rbp+57h+var_70], rax
0x180046aba  mov     edx, 1
0x180046abf  lea     rax, zcfree
0x180046ac6  xor     ecx, ecx
0x180046ac8  mov     r8d, 2370h
0x180046ace  mov     [rbp+57h+var_68], rax
0x180046ad2  call    zcalloc
0x180046ad7  mov     rsi, rax
0x180046ada  test    rax, rax
0x180046add  jz      loc_180046BDB
0x180046ae3  mov     [rbp+57h+var_78], rax
0x180046ae7  lea     rcx, [rbp+57h+var_A0]
0x180046aeb  lea     rax, [rbp+57h+var_A0]
0x180046aef  mov     qword ptr [rsi+40h], 0
0x180046af7  mov     edx, 0Fh
0x180046afc  mov     [rsi], rax
0x180046aff  mov     dword ptr [rsi+8], 3F34h
0x180046b06  mov     dword ptr [rsi+20h], 1
0x180046b0d  call    inflateReset2
0x180046b12  test    eax, eax
0x180046b14  jnz     loc_180046C70
0x180046b1a  mov     [rbp+57h+var_A0], r14
0x180046b1e  mov     [rbp+57h+var_98], r12d
0x180046b22  mov     [rbp+57h+var_88], ebx
0x180046b25  mov     [rbp+57h+var_90], r15
0x180046b29  mov     edx, 2
0x180046b2e  lea     rcx, [rbp+57h+var_A0]
0x180046b32  call    inflate
0x180046b37  mov     esi, 88982F70h
0x180046b3c  cmp     eax, 1
0x180046b3f  jnz     loc_180046C25
0x180046b45  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180046b48  call    cs:__imp_CoTaskMemAlloc
0x180046b4e  mov     rbx, rax
0x180046b51  test    rax, rax
0x180046b54  jnz     short loc_180046B6D
0x180046b56  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180046b5d  mov     ebx, 8007000Eh
0x180046b62  jz      short loc_180046BC8
0x180046b64  mov     ecx, ebx; int
0x180046b66  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180046b6b  jmp     short loc_180046BC8
0x180046b6d  mov     rdx, [rdi+0A8h]; Src
0x180046b74  test    rdx, rdx
0x180046b77  jnz     loc_180046D04
0x180046b7d  mov     rax, [rdi+0B0h]
0x180046b84  mov     rdx, r15; Src
0x180046b87  mov     r8d, dword ptr [rbp+57h+cb]
0x180046b8b  sub     r8, rax; Size
0x180046b8e  mov     [rdi+0A8h], rbx
0x180046b95  lea     rcx, [rax+rbx]; void *
0x180046b99  call    memcpy_0
0x180046b9e  mov     r8d, dword ptr [rbp+57h+cb]; unsigned __int64
0x180046ba2  mov     rcx, rdi; this
0x180046ba5  mov     rdx, [rdi+0A8h]; unsigned __int8 *
0x180046bac  mov     [rdi+0B0h], r8
0x180046bb3  call    ?HrCheckProfileData@CMetadataPngIccpReaderWriter@@MEAAJQEAE_K@Z; CMetadataPngIccpReaderWriter::HrCheckProfileData(uchar * const,unsigned __int64)
0x180046bb8  mov     ebx, eax
0x180046bba  test    eax, eax
0x180046bbc  js      short loc_180046C15
0x180046bbe  mov     [r13+0], r12d
0x180046bc2  jmp     short loc_180046BC8
0x180046bc4  test    eax, eax
0x180046bc6  jns     short loc_180046BBE
0x180046bc8  lea     rcx, [rbp+57h+var_A0]
0x180046bcc  call    inflateEnd
0x180046bd1  test    eax, eax
0x180046bd3  jz      short loc_180046BF2
0x180046bd5  test    ebx, ebx
0x180046bd7  js      short loc_180046BF2
0x180046bd9  jmp     short loc_180046BF0
0x180046bdb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180046be2  mov     esi, 88982F70h
0x180046be7  jz      short loc_180046BF0
0x180046be9  mov     ecx, esi; int
0x180046beb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180046bf0  mov     ebx, esi
0x180046bf2  mov     rcx, r15; pv
0x180046bf5  call    cs:__imp_CoTaskMemFree
0x180046bfb  test    ebx, ebx
0x180046bfd  js      short loc_180046C51
0x180046bff  mov     eax, ebx
0x180046c01  add     rsp, 88h
0x180046c08  pop     r15
0x180046c0a  pop     r14
0x180046c0c  pop     r13
0x180046c0e  pop     r12
0x180046c10  pop     rdi
0x180046c11  pop     rsi
0x180046c12  pop     rbx
0x180046c13  pop     rbp
0x180046c14  retn
0x180046c15  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180046c1c  jz      short loc_180046BC4
0x180046c1e  mov     ecx, eax
0x180046c20  jmp     loc_180046B66
0x180046c25  test    eax, eax
0x180046c27  jz      short loc_180046C8D
0x180046c29  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180046c30  jz      short loc_180046C39
0x180046c32  mov     ecx, esi; int
0x180046c34  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180046c39  mov     ebx, esi
0x180046c3b  jmp     short loc_180046BC8
0x180046c3d  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180046c43  mov     ebx, 8007000Eh
0x180046c48  jz      short loc_180046C51
0x180046c4a  mov     ecx, ebx; int
0x180046c4c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180046c51  mov     rcx, [rdi+0A8h]; pv
0x180046c58  test    rcx, rcx
0x180046c5b  jz      short loc_180046BFF
0x180046c5d  call    cs:__imp_CoTaskMemFree
0x180046c63  mov     qword ptr [rdi+0A8h], 0
0x180046c6e  jmp     short loc_180046BFF
0x180046c70  mov     rcx, [rbp+57h+var_60]
0x180046c74  mov     rdx, rsi
0x180046c77  mov     rax, [rbp+57h+var_68]
0x180046c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c80  mov     [rbp+57h+var_78], 0
0x180046c88  jmp     loc_180046BDB
0x180046c8d  cmp     [rbp+57h+var_88], 0
0x180046c91  jnz     loc_180046B29
0x180046c97  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180046c9a  call    cs:__imp_CoTaskMemAlloc
0x180046ca0  mov     r14, rax
0x180046ca3  test    rax, rax
0x180046ca6  jz      loc_180046B56
0x180046cac  mov     rdx, [rdi+0A8h]; Src
0x180046cb3  test    rdx, rdx
0x180046cb6  jz      short loc_180046CD4
0x180046cb8  mov     r8, [rdi+0B0h]; Size
0x180046cbf  mov     rcx, rax; void *
0x180046cc2  call    memcpy_0
0x180046cc7  mov     rcx, [rdi+0A8h]; pv
0x180046cce  call    cs:__imp_CoTaskMemFree
0x180046cd4  mov     rax, [rdi+0B0h]
0x180046cdb  mov     rdx, r15; Src
0x180046cde  mov     r8d, dword ptr [rbp+57h+cb]
0x180046ce2  sub     r8, rax; Size
0x180046ce5  mov     [rdi+0A8h], r14
0x180046cec  lea     rcx, [rax+r14]; void *
0x180046cf0  call    memcpy_0
0x180046cf5  mov     eax, dword ptr [rbp+57h+cb]
0x180046cf8  mov     [rdi+0B0h], rax
0x180046cff  jmp     loc_180046B22
0x180046d04  mov     r8, [rdi+0B0h]; Size
0x180046d0b  mov     rcx, rbx; void *
0x180046d0e  call    memcpy_0
0x180046d13  mov     rcx, [rdi+0A8h]; pv
0x180046d1a  call    cs:__imp_CoTaskMemFree
0x180046d20  jmp     loc_180046B7D
```
