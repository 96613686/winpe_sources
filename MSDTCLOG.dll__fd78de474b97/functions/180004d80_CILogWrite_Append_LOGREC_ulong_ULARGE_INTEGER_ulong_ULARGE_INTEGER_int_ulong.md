# CILogWrite::Append(_LOGREC *,ulong,_ULARGE_INTEGER *,ulong *,_ULARGE_INTEGER *,int,ulong *)

- ea: `0x180004d80`
- end: `0x180004f9e`
- name: `?Append@CILogWrite@@UEAAJPEAU_LOGREC@@KPEAT_ULARGE_INTEGER@@PEAK1H2@Z`
- size: `542`
- prototype: `int(CILogWrite *__hidden this, struct _LOGREC *, unsigned int, union _ULARGE_INTEGER *, unsigned int *, union _ULARGE_INTEGER *, int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004d80`
- `0x1800084c8`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f7a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004f70`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004f70`

## pseudocode

```c
__int64 __fastcall CILogWrite::Append(
        CILogWrite *this,
        struct _LOGREC *a2,
        struct _LOGREC *a3,
        union _ULARGE_INTEGER *a4,
        unsigned int *a5,
        union _ULARGE_INTEGER *a6,
        int a7,
        unsigned int *a8)
{
  struct _LOGREC *v8; // rbx
  CILogWrite *v9; // r14
  unsigned int v10; // edi
  int v11; // ecx
  union _ULARGE_INTEGER *v12; // r12
  int v13; // r15d
  ulong v14; // esi
  ULONGLONG v15; // rdx
  unsigned int *v17; // [rsp+28h] [rbp-90h]
  unsigned int v18; // [rsp+40h] [rbp-78h]
  int v19; // [rsp+44h] [rbp-74h]
  ULONGLONG v20; // [rsp+50h] [rbp-68h]
  struct _LOGREC *v21; // [rsp+58h] [rbp-60h]
  union _ULARGE_INTEGER *v22; // [rsp+60h] [rbp-58h]
  ulong v23; // [rsp+68h] [rbp-50h] BYREF
  ulong v24; // [rsp+6Ch] [rbp-4Ch] BYREF
  __int64 v25[9]; // [rsp+70h] [rbp-48h] BYREF
  int v27; // [rsp+C8h] [rbp+10h]
  unsigned int v28; // [rsp+D0h] [rbp+18h]

  v28 = (unsigned int)a3;
  v8 = a2;
  v9 = this;
  v20 = 0;
  if ( !a2 )
    return 2147942487LL;
  v10 = 0;
  v18 = 0;
  v11 = 1;
  v21 = a2;
  v12 = a4;
  v22 = a4;
  v13 = 0;
  v19 = 0;
  v14 = 0;
LABEL_3:
  v15 = v20;
  v27 = v11;
  while ( v10 < (unsigned int)a3 && v11 )
  {
    if ( !v8 || !*(_QWORD *)v8 && *((_DWORD *)v8 + 2) )
      return 2147942487LL;
    if ( *((_WORD *)v8 + 7) != 2 )
      *((_WORD *)v8 + 7) = 1;
    if ( a7 )
    {
      if ( v10 == (_DWORD)a3 - 1 )
        v13 = 1;
      v19 = v13;
    }
    try
    {
      v15 = *(_QWORD *)CLogMgr::_Write(
                         *((CLogMgr **)v9 + 2),
                         v25,
                         a3,
                         (__int64)v8,
                         v13,
                         v17,
                         a8,
                         *(_DWORD *)(*((_QWORD *)v9 + 1) + 328LL)).QuadPart;
      v20 = v15;
      if ( v15 )
      {
        v18 = ++v10;
        if ( a4 )
        {
          v12->QuadPart = v15;
          v22 = ++v12;
        }
        v8 = (struct _LOGREC *)((char *)v8 + 16);
        v21 = v8;
        v11 = v27;
      }
      else
      {
        v11 = 0;
        v27 = 0;
      }
      a3 = (struct _LOGREC *)v28;
    }
    catch ( long v23 )
    {
      v9 = this;
      v10 = v18;
      v11 = 0;
      v8 = v21;
      v12 = v22;
      v13 = v19;
      v14 = v23;
      a3 = (struct _LOGREC *)v28;
      goto LABEL_3;
    }
    catch ( ulong v24 )
    {
      v9 = this;
      v10 = v18;
      v11 = 0;
      v8 = v21;
      v12 = v22;
      v13 = v19;
      v14 = v24;
      a3 = (struct _LOGREC *)v28;
      goto LABEL_3;
    }
  }
  if ( v15 )
  {
    if ( a6 )
      *a6 = *(union _ULARGE_INTEGER *)(*((_QWORD *)v9 + 2) + 472LL);
    if ( a5 )
      *a5 = v10;
  }
  else if ( !v14 )
  {
    v14 = -2147418113;
  }
  if ( (*(unsigned int (__fastcall **)(__int64, ULONGLONG, _QWORD))(*(_QWORD *)(*((_QWORD *)v9 + 2) + 144LL) + 24LL))(
         *((_QWORD *)v9 + 2) + 144LL,
         v15,
         *(_QWORD *)(*((_QWORD *)v9 + 2) + 472LL)) == 2 )
  {
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)v9 + 2) + 384LL), 1u);
    if ( !SetEvent(*(HANDLE *)(*((_QWORD *)v9 + 2) + 544LL)) )
      return GetLastError();
  }
  return v14;
}

```

## disassembly

```asm
0x180004d80  mov     r11, rsp
0x180004d83  mov     [r11+20h], r9
0x180004d87  mov     [r11+18h], r8d
0x180004d8b  mov     [r11+8], rcx
0x180004d8f  push    rbx
0x180004d90  push    rsi
0x180004d91  push    rdi
0x180004d92  push    r12
0x180004d94  push    r13
0x180004d96  push    r14
0x180004d98  push    r15
0x180004d9a  sub     rsp, 80h
0x180004da1  mov     rax, r9
0x180004da4  mov     rbx, rdx
0x180004da7  mov     r14, rcx
0x180004daa  mov     qword ptr [r11-68h], 0
0x180004db2  test    rdx, rdx
0x180004db5  jz      loc_180004F86
0x180004dbb  xor     edi, edi
0x180004dbd  mov     [rsp+0B8h+var_78], edi
0x180004dc1  lea     r13d, [rdi+1]
0x180004dc5  mov     ecx, r13d
0x180004dc8  mov     [rsp+0B8h+var_60], rdx
0x180004dcd  mov     r12, rax
0x180004dd0  mov     [rsp+0B8h+var_58], rax
0x180004dd5  xor     r15d, r15d
0x180004dd8  mov     [rsp+0B8h+var_74], r15d
0x180004ddd  xor     esi, esi
0x180004ddf  mov     rdx, [rsp+0B8h+var_68]
0x180004de4  mov     [rsp+0B8h+arg_8], ecx
0x180004deb  mov     eax, 2
0x180004df0  cmp     edi, r8d
0x180004df3  jnb     loc_180004EFC
0x180004df9  test    ecx, ecx
0x180004dfb  jz      loc_180004EFC
0x180004e01  test    rbx, rbx
0x180004e04  jz      loc_180004F86
0x180004e0a  cmp     qword ptr [rbx], 0
0x180004e0e  jnz     short loc_180004E1A
0x180004e10  cmp     dword ptr [rbx+8], 0
0x180004e14  ja      loc_180004F86
0x180004e1a  cmp     [rbx+0Eh], ax
0x180004e1e  jz      short loc_180004E25
0x180004e20  mov     [rbx+0Eh], r13w
0x180004e25  cmp     [rsp+0B8h+arg_30], 0
0x180004e2d  jz      short loc_180004E3E
0x180004e2f  lea     eax, [r8-1]
0x180004e33  cmp     edi, eax
0x180004e35  cmovz   r15d, r13d
0x180004e39  mov     [rsp+0B8h+var_74], r15d
0x180004e3e  mov     rax, [r14+8]
0x180004e42  mov     ecx, [rax+148h]
0x180004e48  mov     [rsp+0B8h+var_80], ecx
0x180004e4c  mov     rax, [rsp+0B8h+arg_38]
0x180004e54  mov     qword ptr [rsp+0B8h+var_88], rax; unsigned int
0x180004e59  mov     [rsp+0B8h+var_98], r15d; int
0x180004e5e  mov     r9, rbx; int
0x180004e61  lea     rdx, [rsp+0B8h+var_48]; unsigned int
0x180004e66  mov     rcx, [r14+10h]; this
0x180004e6a  call    ?_Write@CLogMgr@@AEAA?AT_ULARGE_INTEGER@@KPEAU_LOGREC@@HHPEAKK@Z; CLogMgr::_Write(ulong,_LOGREC *,int,int,ulong *,ulong)
0x180004e6f  mov     rdx, [rax]
0x180004e72  mov     [rsp+0B8h+var_68], rdx
0x180004e77  test    rdx, rdx
0x180004e7a  jnz     short loc_180004E87
0x180004e7c  xor     ecx, ecx
0x180004e7e  mov     [rsp+0B8h+arg_8], ecx
0x180004e85  jmp     short loc_180004EB6
0x180004e87  add     edi, r13d
0x180004e8a  mov     [rsp+0B8h+var_78], edi
0x180004e8e  cmp     [rsp+0B8h+arg_18], 0
0x180004e97  jz      short loc_180004EA6
0x180004e99  mov     [r12], rdx
0x180004e9d  add     r12, 8
0x180004ea1  mov     [rsp+0B8h+var_58], r12
0x180004ea6  add     rbx, 10h
0x180004eaa  mov     [rsp+0B8h+var_60], rbx
0x180004eaf  mov     ecx, [rsp+0B8h+arg_8]
0x180004eb6  mov     r8d, [rsp+0B8h+arg_10]
0x180004ebe  jmp     loc_180004DEB
0x180004ec3  mov     r13d, 1
0x180004ec9  mov     r14, [rsp+0B8h+arg_0]
0x180004ed1  mov     edi, [rsp+0B8h+var_78]
0x180004ed5  mov     ecx, [rsp+0B8h+arg_8]
0x180004edc  mov     rbx, [rsp+0B8h+var_60]
0x180004ee1  mov     r12, [rsp+0B8h+var_58]
0x180004ee6  mov     r15d, [rsp+0B8h+var_74]
0x180004eeb  mov     esi, [rsp+0B8h+var_70]
0x180004eef  mov     r8d, [rsp+0B8h+arg_10]
0x180004ef7  jmp     loc_180004DDF
0x180004efc  test    rdx, rdx
0x180004eff  jnz     short loc_180004F0C
0x180004f01  test    esi, esi
0x180004f03  jnz     short loc_180004F36
0x180004f05  mov     esi, 8000FFFFh
0x180004f0a  jmp     short loc_180004F36
0x180004f0c  mov     r8, [rsp+0B8h+arg_28]
0x180004f14  test    r8, r8
0x180004f17  jz      short loc_180004F27
0x180004f19  mov     rax, [r14+10h]
0x180004f1d  mov     rcx, [rax+1D8h]
0x180004f24  mov     [r8], rcx
0x180004f27  mov     rax, [rsp+0B8h+arg_20]
0x180004f2f  test    rax, rax
0x180004f32  jz      short loc_180004F36
0x180004f34  mov     [rax], edi
0x180004f36  mov     r8, [r14+10h]
0x180004f3a  lea     rcx, [r8+90h]
0x180004f41  mov     rax, [rcx]
0x180004f44  mov     r8, [r8+1D8h]
0x180004f4b  mov     rax, [rax+18h]
0x180004f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f54  cmp     eax, 2
0x180004f57  jnz     short loc_180004F82
0x180004f59  mov     rax, [r14+10h]
0x180004f5d  lock add [rax+180h], r13d
0x180004f65  mov     rcx, [r14+10h]
0x180004f69  mov     rcx, [rcx+220h]; hEvent
0x180004f70  call    cs:__imp_SetEvent
0x180004f76  test    eax, eax
0x180004f78  jnz     short loc_180004F82
0x180004f7a  call    cs:__imp_GetLastError
0x180004f80  mov     esi, eax
0x180004f82  mov     eax, esi
0x180004f84  jmp     short loc_180004F8B
0x180004f86  mov     eax, 80070057h
0x180004f8b  add     rsp, 80h
0x180004f92  pop     r15
0x180004f94  pop     r14
0x180004f96  pop     r13
0x180004f98  pop     r12
0x180004f9a  pop     rdi
0x180004f9b  pop     rsi
0x180004f9c  pop     rbx
0x180004f9d  retn
```
