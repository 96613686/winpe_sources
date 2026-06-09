# CMetadataPngIccpReaderWriter::HrLoadProfileData(uchar *,uint,ulong *)

- ea: `0x180017c90`
- end: `0x180017fa0`
- name: `?HrLoadProfileData@CMetadataPngIccpReaderWriter@@MEAAJPEAEIPEAK@Z`
- size: `784`
- prototype: `__int64 __fastcall(CMetadataPngIccpReaderWriter *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800524b0`

## callees

- `0x1800179b0`
- `0x180017c90`
- `0x180017fb0`
- `0x1800190fc`
- `0x18001cfe8`
- `0x18001dd20`
- `0x1800bd9d4`
- `0x1800e6af4`
- `0x18017e438`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017cda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017d9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017f03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017cda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017d9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017f03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017e51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017ec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017e51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017ec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f8f`

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
0x180017c90  push    rbp
0x180017c92  push    rbx
0x180017c93  push    rsi
0x180017c94  push    rdi
0x180017c95  push    r12
0x180017c97  push    r13
0x180017c99  push    r14
0x180017c9b  push    r15
0x180017c9d  lea     rbp, [rsp-1Fh]
0x180017ca2  sub     rsp, 88h
0x180017ca9  xor     esi, esi
0x180017cab  mov     ebx, r8d
0x180017cae  add     rbx, rbx
0x180017cb1  mov     r12d, r8d
0x180017cb4  mov     eax, 0FFFFFFFFh
0x180017cb9  mov     [rcx+0A8h], rsi
0x180017cc0  mov     [rcx+0B0h], rsi
0x180017cc7  mov     r13, r9
0x180017cca  mov     r14, rdx
0x180017ccd  mov     rdi, rcx
0x180017cd0  cmp     rbx, rax
0x180017cd3  jbe     short loc_180017CD8
0x180017cd5  mov     ebx, r12d
0x180017cd8  mov     ecx, ebx; cb
0x180017cda  call    cs:__imp_CoTaskMemAlloc
0x180017ce1  nop     dword ptr [rax+rax+00h]
0x180017ce6  mov     r15, rax
0x180017ce9  test    rax, rax
0x180017cec  jz      loc_180017EA0
0x180017cf2  xor     edx, edx; Val
0x180017cf4  lea     rcx, [rbp+57h+var_A0]; void *
0x180017cf8  lea     r8d, [rdx+58h]; Size
0x180017cfc  call    memset_0
0x180017d01  lea     rax, zcalloc
0x180017d08  mov     [rbp+57h+var_60], rsi
0x180017d0c  mov     [rbp+57h+var_70], rax
0x180017d10  mov     edx, 1
0x180017d15  lea     rax, zcfree
0x180017d1c  xor     ecx, ecx
0x180017d1e  mov     r8d, 2370h
0x180017d24  mov     [rbp+57h+var_68], rax
0x180017d28  call    zcalloc
0x180017d2d  mov     rsi, rax
0x180017d30  test    rax, rax
0x180017d33  jz      loc_180017E37
0x180017d39  mov     [rbp+57h+var_78], rax
0x180017d3d  lea     rcx, [rbp+57h+var_A0]
0x180017d41  lea     rax, [rbp+57h+var_A0]
0x180017d45  mov     qword ptr [rsi+40h], 0
0x180017d4d  mov     edx, 0Fh
0x180017d52  mov     [rsi], rax
0x180017d55  mov     dword ptr [rsi+8], 3F34h
0x180017d5c  mov     dword ptr [rsi+20h], 1
0x180017d63  call    inflateReset2
0x180017d68  test    eax, eax
0x180017d6a  jnz     loc_180017ED9
0x180017d70  mov     [rbp+57h+var_A0], r14
0x180017d74  mov     [rbp+57h+var_98], r12d
0x180017d78  mov     [rbp+57h+var_88], ebx
0x180017d7b  mov     [rbp+57h+var_90], r15
0x180017d7f  mov     edx, 2
0x180017d84  lea     rcx, [rbp+57h+var_A0]
0x180017d88  call    inflate
0x180017d8d  mov     esi, 88982F70h
0x180017d92  cmp     eax, 1
0x180017d95  jnz     loc_180017E88
0x180017d9b  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180017d9e  call    cs:__imp_CoTaskMemAlloc
0x180017da5  nop     dword ptr [rax+rax+00h]
0x180017daa  mov     rbx, rax
0x180017dad  test    rax, rax
0x180017db0  jnz     short loc_180017DC9
0x180017db2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180017db9  mov     ebx, 8007000Eh
0x180017dbe  jz      short loc_180017E24
0x180017dc0  mov     ecx, ebx; int
0x180017dc2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180017dc7  jmp     short loc_180017E24
0x180017dc9  mov     rdx, [rdi+0A8h]; Src
0x180017dd0  test    rdx, rdx
0x180017dd3  jnz     loc_180017F79
0x180017dd9  mov     rax, [rdi+0B0h]
0x180017de0  mov     rdx, r15; Src
0x180017de3  mov     r8d, dword ptr [rbp+57h+cb]
0x180017de7  sub     r8, rax; Size
0x180017dea  mov     [rdi+0A8h], rbx
0x180017df1  lea     rcx, [rax+rbx]; void *
0x180017df5  call    memcpy_0
0x180017dfa  mov     r8d, dword ptr [rbp+57h+cb]; unsigned __int64
0x180017dfe  mov     rcx, rdi; this
0x180017e01  mov     rdx, [rdi+0A8h]; unsigned __int8 *
0x180017e08  mov     [rdi+0B0h], r8
0x180017e0f  call    ?HrCheckProfileData@CMetadataPngIccpReaderWriter@@MEAAJQEAE_K@Z; CMetadataPngIccpReaderWriter::HrCheckProfileData(uchar * const,unsigned __int64)
0x180017e14  mov     ebx, eax
0x180017e16  test    eax, eax
0x180017e18  js      short loc_180017E78
0x180017e1a  mov     [r13+0], r12d
0x180017e1e  jmp     short loc_180017E24
0x180017e20  test    eax, eax
0x180017e22  jns     short loc_180017E1A
0x180017e24  lea     rcx, [rbp+57h+var_A0]
0x180017e28  call    inflateEnd
0x180017e2d  test    eax, eax
0x180017e2f  jz      short loc_180017E4E
0x180017e31  test    ebx, ebx
0x180017e33  js      short loc_180017E4E
0x180017e35  jmp     short loc_180017E4C
0x180017e37  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180017e3e  mov     esi, 88982F70h
0x180017e43  jz      short loc_180017E4C
0x180017e45  mov     ecx, esi; int
0x180017e47  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180017e4c  mov     ebx, esi
0x180017e4e  mov     rcx, r15; pv
0x180017e51  call    cs:__imp_CoTaskMemFree
0x180017e58  nop     dword ptr [rax+rax+00h]
0x180017e5d  test    ebx, ebx
0x180017e5f  js      short loc_180017EB4
0x180017e61  mov     eax, ebx
0x180017e63  add     rsp, 88h
0x180017e6a  pop     r15
0x180017e6c  pop     r14
0x180017e6e  pop     r13
0x180017e70  pop     r12
0x180017e72  pop     rdi
0x180017e73  pop     rsi
0x180017e74  pop     rbx
0x180017e75  pop     rbp
0x180017e76  retn
0x180017e78  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180017e7f  jz      short loc_180017E20
0x180017e81  mov     ecx, eax
0x180017e83  jmp     loc_180017DC2
0x180017e88  test    eax, eax
0x180017e8a  jz      short loc_180017EF6
0x180017e8c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180017e93  jz      short loc_180017E9C
0x180017e95  mov     ecx, esi; int
0x180017e97  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180017e9c  mov     ebx, esi
0x180017e9e  jmp     short loc_180017E24
0x180017ea0  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180017ea6  mov     ebx, 8007000Eh
0x180017eab  jz      short loc_180017EB4
0x180017ead  mov     ecx, ebx; int
0x180017eaf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180017eb4  mov     rcx, [rdi+0A8h]; pv
0x180017ebb  test    rcx, rcx
0x180017ebe  jz      short loc_180017E61
0x180017ec0  call    cs:__imp_CoTaskMemFree
0x180017ec7  nop     dword ptr [rax+rax+00h]
0x180017ecc  mov     qword ptr [rdi+0A8h], 0
0x180017ed7  jmp     short loc_180017E61
0x180017ed9  mov     rcx, [rbp+57h+var_60]
0x180017edd  mov     rdx, rsi
0x180017ee0  mov     rax, [rbp+57h+var_68]
0x180017ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ee9  mov     [rbp+57h+var_78], 0
0x180017ef1  jmp     loc_180017E37
0x180017ef6  cmp     [rbp+57h+var_88], 0
0x180017efa  jnz     loc_180017D7F
0x180017f00  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180017f03  call    cs:__imp_CoTaskMemAlloc
0x180017f0a  nop     dword ptr [rax+rax+00h]
0x180017f0f  mov     r14, rax
0x180017f12  test    rax, rax
0x180017f15  jz      loc_180017DB2
0x180017f1b  mov     rdx, [rdi+0A8h]; Src
0x180017f22  test    rdx, rdx
0x180017f25  jz      short loc_180017F49
0x180017f27  mov     r8, [rdi+0B0h]; Size
0x180017f2e  mov     rcx, rax; void *
0x180017f31  call    memcpy_0
0x180017f36  mov     rcx, [rdi+0A8h]; pv
0x180017f3d  call    cs:__imp_CoTaskMemFree
0x180017f44  nop     dword ptr [rax+rax+00h]
0x180017f49  mov     rax, [rdi+0B0h]
0x180017f50  mov     rdx, r15; Src
0x180017f53  mov     r8d, dword ptr [rbp+57h+cb]
0x180017f57  sub     r8, rax; Size
0x180017f5a  mov     [rdi+0A8h], r14
0x180017f61  lea     rcx, [rax+r14]; void *
0x180017f65  call    memcpy_0
0x180017f6a  mov     eax, dword ptr [rbp+57h+cb]
0x180017f6d  mov     [rdi+0B0h], rax
0x180017f74  jmp     loc_180017D78
0x180017f79  mov     r8, [rdi+0B0h]; Size
0x180017f80  mov     rcx, rbx; void *
0x180017f83  call    memcpy_0
0x180017f88  mov     rcx, [rdi+0A8h]; pv
0x180017f8f  call    cs:__imp_CoTaskMemFree
0x180017f96  nop     dword ptr [rax+rax+00h]
0x180017f9b  jmp     loc_180017DD9
```
