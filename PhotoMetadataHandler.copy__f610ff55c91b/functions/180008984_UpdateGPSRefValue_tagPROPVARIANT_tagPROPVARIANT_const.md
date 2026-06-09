# UpdateGPSRefValue(tagPROPVARIANT *,tagPROPVARIANT const *)

- ea: `0x180008984`
- end: `0x180008b5a`
- name: `?UpdateGPSRefValue@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z`
- size: `470`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180007de0`
- `0x180012620`

## callees

- `0x180008984`
- `0x1800129d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x180008a7d`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x180008a7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180008ab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180008ab2`

## pseudocode

```c
__int64 __fastcall UpdateGPSRefValue(struct tagPROPVARIANT *a1, const struct tagPROPVARIANT *a2)
{
  LPSTR pszVal; // r8
  BSTR v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // edi
  __int64 v8; // rbp
  wint_t v10; // cx
  BYTE **p_pData; // rbx
  BYTE *v12; // rax
  BSTR bstrVal; // rax

  if ( a2->vt != 31 )
    goto LABEL_14;
  pszVal = a2->pszVal;
  if ( !pszVal )
    goto LABEL_14;
  if ( a1->vt != 31 )
  {
    if ( a1->vt != 4117 && a1->vt != 4116 )
      goto LABEL_14;
    if ( a1->lVal == 3 )
    {
      p_pData = &a1->bstrblobVal.pData;
      v12 = (BYTE *)CoTaskMemRealloc(a1->bstrblobVal.pData, 0x20u);
      if ( !v12 )
      {
        v7 = -2147024882;
LABEL_11:
        if ( g_doStackCaptures )
          DoStackCapture(v7);
        return v7;
      }
      *p_pData = v12;
      a1->lVal = 4;
    }
    else
    {
      if ( a1->lVal != 4 )
        goto LABEL_14;
      p_pData = &a1->bstrblobVal.pData;
    }
    bstrVal = a2->bstrVal;
    if ( *bstrVal != 69 )
    {
      switch ( *bstrVal )
      {
        case 'N':
          goto LABEL_46;
        case 'S':
          goto LABEL_45;
        case 'W':
          goto LABEL_44;
      }
      if ( *bstrVal != 101 )
      {
        if ( *bstrVal != 110 )
        {
          if ( *bstrVal != 115 )
          {
            if ( *bstrVal != 119 )
              goto LABEL_14;
LABEL_44:
            *((_QWORD *)a1->bstrblobVal.pData + 3) = 4;
            return 0;
          }
LABEL_45:
          *((_QWORD *)*p_pData + 3) = 2;
          return 0;
        }
LABEL_46:
        *((_QWORD *)*p_pData + 3) = 1;
        return 0;
      }
    }
    *((_QWORD *)*p_pData + 3) = 3;
    return 0;
  }
  v5 = a1->bstrVal;
  if ( v5 )
  {
    v6 = 0x7FFFFFFF;
    do
    {
      if ( !*v5 )
        break;
      ++v5;
      --v6;
    }
    while ( v6 );
    v7 = v6 == 0 ? 0x80070057 : 0;
    v8 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
    if ( !v6 )
      goto LABEL_11;
    if ( !v8 )
    {
      v7 = -2147024362;
      goto LABEL_11;
    }
    v10 = *pszVal;
    if ( v10 == 87 || v10 == 69 || v10 == 78 || v10 == 83 )
      goto LABEL_18;
    if ( v10 == 101 || v10 == 110 || v10 == 115 || v10 == 119 )
    {
      v10 = towupper(v10);
LABEL_18:
      *(_WORD *)(a1->hVal.QuadPart + 2 * v8 - 2) = v10;
      return 0;
    }
  }
LABEL_14:
  if ( g_doStackCaptures )
    DoStackCapture(-2147024809);
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x180008984  push    rbx
0x180008986  push    rbp
0x180008987  push    rsi
0x180008988  push    rdi
0x180008989  push    r14
0x18000898b  sub     rsp, 20h
0x18000898f  xor     r14d, r14d
0x180008992  mov     rdi, rdx
0x180008995  cmp     word ptr [rdx], 1Fh
0x180008999  mov     rsi, rcx
0x18000899c  jnz     short loc_180008A17
0x18000899e  mov     r8, [rdx+8]
0x1800089a2  test    r8, r8
0x1800089a5  jz      short loc_180008A17
0x1800089a7  cmp     word ptr [rcx], 1Fh
0x1800089ab  jnz     loc_180008A88
0x1800089b1  mov     rax, [rcx+8]
0x1800089b5  test    rax, rax
0x1800089b8  jz      short loc_180008A17
0x1800089ba  mov     edx, 7FFFFFFFh
0x1800089bf  mov     ecx, edx
0x1800089c1  cmp     [rax], r14w
0x1800089c5  jz      short loc_1800089D1
0x1800089c7  add     rax, 2
0x1800089cb  sub     rcx, 1
0x1800089cf  jnz     short loc_1800089C1
0x1800089d1  mov     rax, rcx
0x1800089d4  mov     ebx, 80070057h
0x1800089d9  neg     rax
0x1800089dc  mov     rax, rcx
0x1800089df  sbb     edi, edi
0x1800089e1  sub     rdx, rcx
0x1800089e4  not     edi
0x1800089e6  and     edi, ebx
0x1800089e8  neg     rax
0x1800089eb  sbb     rbp, rbp
0x1800089ee  and     rbp, rdx
0x1800089f1  test    rcx, rcx
0x1800089f4  jz      short loc_180008A01
0x1800089f6  cmp     rbp, 1
0x1800089fa  jnb     short loc_180008A3B
0x1800089fc  mov     edi, 80070216h
0x180008a01  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180008a08  jnz     short loc_180008A29
0x180008a0a  mov     eax, edi
0x180008a0c  add     rsp, 20h
0x180008a10  pop     r14
0x180008a12  pop     rdi
0x180008a13  pop     rsi
0x180008a14  pop     rbp
0x180008a15  pop     rbx
0x180008a16  retn
0x180008a17  mov     ebx, 80070057h
0x180008a1c  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180008a23  jnz     short loc_180008A32
0x180008a25  mov     edi, ebx
0x180008a27  jmp     short loc_180008A0A
0x180008a29  mov     ecx, edi; int
0x180008a2b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008a30  jmp     short loc_180008A0A
0x180008a32  mov     ecx, ebx; int
0x180008a34  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008a39  jmp     short loc_180008A25
0x180008a3b  movsx   ecx, byte ptr [r8]; C
0x180008a3f  cmp     cx, 57h ; 'W'
0x180008a43  jnz     short loc_180008A53
0x180008a45  mov     rax, [rsi+8]
0x180008a49  mov     [rax+rbp*2-2], cx
0x180008a4e  mov     edi, r14d
0x180008a51  jmp     short loc_180008A0A
0x180008a53  cmp     cx, 45h ; 'E'
0x180008a57  jz      short loc_180008A45
0x180008a59  cmp     cx, 4Eh ; 'N'
0x180008a5d  jz      short loc_180008A45
0x180008a5f  cmp     cx, 53h ; 'S'
0x180008a63  jz      short loc_180008A45
0x180008a65  cmp     cx, 65h ; 'e'
0x180008a69  jz      short loc_180008A7D
0x180008a6b  cmp     cx, 6Eh ; 'n'
0x180008a6f  jz      short loc_180008A7D
0x180008a71  cmp     cx, 73h ; 's'
0x180008a75  jz      short loc_180008A7D
0x180008a77  cmp     cx, 77h ; 'w'
0x180008a7b  jnz     short loc_180008A1C
0x180008a7d  call    cs:__imp_towupper
0x180008a83  movzx   ecx, ax
0x180008a86  jmp     short loc_180008A45
0x180008a88  mov     eax, 1015h
0x180008a8d  cmp     [rcx], ax
0x180008a90  jz      short loc_180008AA0
0x180008a92  mov     eax, 1014h
0x180008a97  cmp     [rcx], ax
0x180008a9a  jnz     loc_180008A17
0x180008aa0  cmp     dword ptr [rcx+8], 3
0x180008aa4  jnz     short loc_180008AD3
0x180008aa6  lea     rbx, [rcx+10h]
0x180008aaa  mov     edx, 20h ; ' '; cb
0x180008aaf  mov     rcx, [rbx]; pv
0x180008ab2  call    cs:__imp_CoTaskMemRealloc
0x180008ab8  test    rax, rax
0x180008abb  jnz     short loc_180008AC7
0x180008abd  mov     edi, 8007000Eh
0x180008ac2  jmp     loc_180008A01
0x180008ac7  mov     [rbx], rax
0x180008aca  mov     dword ptr [rsi+8], 4
0x180008ad1  jmp     short loc_180008AE1
0x180008ad3  cmp     dword ptr [rcx+8], 4
0x180008ad7  jnz     loc_180008A17
0x180008add  lea     rbx, [rcx+10h]
0x180008ae1  mov     rax, [rdi+8]
0x180008ae5  cmp     word ptr [rax], 45h ; 'E'
0x180008ae9  jz      short loc_180008B4A
0x180008aeb  cmp     word ptr [rax], 4Eh ; 'N'
0x180008aef  jz      short loc_180008B3A
0x180008af1  cmp     word ptr [rax], 53h ; 'S'
0x180008af5  jz      short loc_180008B2A
0x180008af7  cmp     word ptr [rax], 57h ; 'W'
0x180008afb  jz      short loc_180008B19
0x180008afd  cmp     word ptr [rax], 65h ; 'e'
0x180008b01  jz      short loc_180008B4A
0x180008b03  cmp     word ptr [rax], 6Eh ; 'n'
0x180008b07  jz      short loc_180008B3A
0x180008b09  cmp     word ptr [rax], 73h ; 's'
0x180008b0d  jz      short loc_180008B2A
0x180008b0f  cmp     word ptr [rax], 77h ; 'w'
0x180008b13  jnz     loc_180008A17
0x180008b19  mov     rax, [rsi+10h]
0x180008b1d  mov     qword ptr [rax+18h], 4
0x180008b25  jmp     loc_180008A4E
0x180008b2a  mov     rax, [rbx]
0x180008b2d  mov     qword ptr [rax+18h], 2
0x180008b35  jmp     loc_180008A4E
0x180008b3a  mov     rax, [rbx]
0x180008b3d  mov     qword ptr [rax+18h], 1
0x180008b45  jmp     loc_180008A4E
0x180008b4a  mov     rax, [rbx]
0x180008b4d  mov     qword ptr [rax+18h], 3
0x180008b55  jmp     loc_180008A4E
```
