# ValidateSIDKey(_SID_KEY_HEADER const *,ulong,int)

- ea: `0x180010a94`
- end: `0x180010cf2`
- name: `?ValidateSIDKey@@YAJPEBU_SID_KEY_HEADER@@KH@Z`
- size: `606`
- prototype: `__int64 __fastcall(const struct _SID_KEY_HEADER *, unsigned int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c1fc`
- `0x18001a214`

## callees

- `0x180010a94`
- `0x18001a450`

## string_xrefs

- `0x180010bb7`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`
- `0x180010cc2`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`

## pseudocode

```c
__int64 __fastcall ValidateSIDKey(const struct _SID_KEY_HEADER *a1, unsigned int a2, int a3)
{
  int v5; // edx
  int v6; // eax
  bool v7; // zf
  unsigned int v8; // r9d
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // r11
  __int64 v12; // rdi
  __int64 v13; // r14
  __int64 v14; // rsi
  unsigned int v15; // eax
  unsigned int v16; // r9d
  unsigned int v17; // ebx
  unsigned int v18; // edx
  unsigned int v19; // eax
  unsigned int v20; // edx
  unsigned int v21; // r9d
  unsigned int v22; // r8d
  unsigned int v23; // edx
  unsigned int v24; // eax

  if ( !a1 || a2 < 0x50 )
  {
    v8 = 605;
    goto LABEL_57;
  }
  if ( (*((_BYTE *)a1 + 8) & 1) != 0 )
  {
    if ( !*((_DWORD *)a1 + 17) || *((_DWORD *)a1 + 16) )
    {
      v8 = 629;
      goto LABEL_57;
    }
    goto LABEL_17;
  }
  v5 = *((_DWORD *)a1 + 16);
  if ( !v5 )
  {
    if ( *((_DWORD *)a1 + 17) )
    {
      v6 = *((_DWORD *)a1 + 17);
      goto LABEL_9;
    }
LABEL_14:
    v8 = 619;
LABEL_57:
    v17 = -2146893821;
    SidKeyDebugTraceError(0x80090003, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", v8);
    return v17;
  }
  if ( v5 != 64 )
    goto LABEL_14;
  v6 = *((_DWORD *)a1 + 17);
  if ( !v6 )
  {
    v7 = *((_DWORD *)a1 + 5) == 31;
    goto LABEL_11;
  }
LABEL_9:
  v7 = v6 == 64;
LABEL_11:
  if ( !v7 || !v5 && *((_DWORD *)a1 + 4) )
    goto LABEL_14;
LABEL_17:
  v9 = *((unsigned int *)a1 + 10);
  if ( (v9 & 1) != 0 || *(_WORD *)((char *)a1 + v9 + 78) )
  {
    v8 = 640;
    goto LABEL_57;
  }
  v10 = *((unsigned int *)a1 + 12);
  if ( (v10 & 1) != 0 || (v11 = *((unsigned int *)a1 + 11), *(_WORD *)((char *)a1 + v9 + v11 + v10 + 78)) )
  {
    v8 = 651;
    goto LABEL_57;
  }
  v12 = *((unsigned int *)a1 + 18);
  if ( (v12 & 1) != 0
    || (v13 = *((unsigned int *)a1 + 13), *(_WORD *)((char *)a1 + v9 + (unsigned int)v10 + v13 + v11 + v12 + 78)) )
  {
    v8 = 664;
    goto LABEL_57;
  }
  v14 = *((unsigned int *)a1 + 19);
  if ( (v14 & 1) != 0 || *(_WORD *)((char *)a1 + v9 + (unsigned int)v10 + v12 + v13 + v11 + v14 + 78) )
  {
    v8 = 678;
    goto LABEL_57;
  }
  v15 = v9 + 80;
  if ( (unsigned int)v9 >= 0xFFFFFFB0 )
  {
    v16 = 686;
LABEL_27:
    SidKeyDebugTraceError(0x80070216, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", v16);
    return (unsigned int)-2146893821;
  }
  v18 = v15 + v11;
  if ( v15 + (unsigned int)v11 < v15 )
  {
    v16 = 693;
    goto LABEL_27;
  }
  v19 = v18 + v10;
  if ( v18 + (unsigned int)v10 < v18 )
  {
    v16 = 700;
    goto LABEL_27;
  }
  v20 = v19 + v13;
  if ( v19 + (unsigned int)v13 < v19 )
  {
    v16 = 707;
    goto LABEL_27;
  }
  v21 = v20 + *((_DWORD *)a1 + 16);
  if ( v21 < v20 )
  {
    v16 = 715;
    goto LABEL_27;
  }
  v22 = v21 + *((_DWORD *)a1 + 17);
  if ( v22 < v21 )
  {
    v16 = 722;
    goto LABEL_27;
  }
  v23 = v22 + v12;
  if ( v22 + (unsigned int)v12 < v22 )
  {
    v16 = 730;
    goto LABEL_27;
  }
  v24 = v23 + v14;
  if ( v23 + (unsigned int)v14 < v23 )
  {
    v16 = 738;
    goto LABEL_27;
  }
  if ( a3 == 1 && a2 != v24 || a2 < v24 )
  {
    v8 = 750;
    goto LABEL_57;
  }
  if ( *((_DWORD *)a1 + 1) != 1263748171
    || *(_DWORD *)a1 != 1
    || *((_DWORD *)a1 + 4) > 0x1Fu
    || (v17 = 0, *((_DWORD *)a1 + 5) > 0x1Fu) )
  {
    v8 = 763;
    goto LABEL_57;
  }
  return v17;
}

```

## disassembly

```asm
0x180010a94  push    rbx
0x180010a96  push    rbp
0x180010a97  push    rsi
0x180010a98  push    rdi
0x180010a99  push    r12
0x180010a9b  push    r13
0x180010a9d  push    r14
0x180010a9f  push    r15
0x180010aa1  sub     rsp, 28h
0x180010aa5  xor     r13d, r13d
0x180010aa8  mov     r12d, r8d
0x180010aab  mov     r10d, edx
0x180010aae  test    rcx, rcx
0x180010ab1  jz      loc_180010CBC
0x180010ab7  cmp     edx, 50h ; 'P'
0x180010aba  jb      loc_180010CBC
0x180010ac0  test    byte ptr [rcx+8], 1
0x180010ac4  jnz     short loc_180010B04
0x180010ac6  mov     edx, [rcx+40h]
0x180010ac9  test    edx, edx
0x180010acb  jnz     short loc_180010AD8
0x180010acd  cmp     [rcx+44h], r13d
0x180010ad1  jz      short loc_180010AF9
0x180010ad3  mov     eax, [rcx+44h]
0x180010ad6  jmp     short loc_180010AE4
0x180010ad8  cmp     edx, 40h ; '@'
0x180010adb  jnz     short loc_180010AF9
0x180010add  mov     eax, [rcx+44h]
0x180010ae0  test    eax, eax
0x180010ae2  jz      short loc_180010AE9
0x180010ae4  cmp     eax, 40h ; '@'
0x180010ae7  jmp     short loc_180010AED
0x180010ae9  cmp     dword ptr [rcx+14h], 1Fh
0x180010aed  jnz     short loc_180010AF9
0x180010aef  test    edx, edx
0x180010af1  jnz     short loc_180010B18
0x180010af3  cmp     [rcx+10h], r13d
0x180010af7  jz      short loc_180010B18
0x180010af9  mov     r9d, 26Bh
0x180010aff  jmp     loc_180010CC2
0x180010b04  cmp     [rcx+44h], r13d
0x180010b08  jz      loc_180010CB4
0x180010b0e  cmp     [rcx+40h], r13d
0x180010b12  jnz     loc_180010CB4
0x180010b18  mov     edx, [rcx+28h]
0x180010b1b  test    dl, 1
0x180010b1e  jnz     loc_180010CAC
0x180010b24  cmp     [rdx+rcx+4Eh], r13w
0x180010b2a  jnz     loc_180010CAC
0x180010b30  mov     r9d, [rcx+30h]
0x180010b34  test    r9b, 1
0x180010b38  jnz     loc_180010CA4
0x180010b3e  mov     r11d, [rcx+2Ch]
0x180010b42  mov     ebx, r9d
0x180010b45  lea     rax, [r11+r9]
0x180010b49  add     rax, rdx
0x180010b4c  cmp     [rax+rcx+4Eh], r13w
0x180010b52  jnz     loc_180010CA4
0x180010b58  mov     edi, [rcx+48h]
0x180010b5b  test    dil, 1
0x180010b5f  jnz     loc_180010C9C
0x180010b65  mov     r14d, [rcx+34h]
0x180010b69  lea     r15, [r14+r11]
0x180010b6d  lea     rax, [r15+rdi]
0x180010b71  add     rax, rbx
0x180010b74  add     rax, rdx
0x180010b77  cmp     [rax+rcx+4Eh], r13w
0x180010b7d  jnz     loc_180010C9C
0x180010b83  mov     esi, [rcx+4Ch]
0x180010b86  test    sil, 1
0x180010b8a  jnz     loc_180010C94
0x180010b90  lea     rax, [r15+rsi]
0x180010b94  add     rax, rdi
0x180010b97  add     rax, rbx
0x180010b9a  add     rax, rdx
0x180010b9d  cmp     [rax+rcx+4Eh], r13w
0x180010ba3  jnz     loc_180010C94
0x180010ba9  lea     eax, [rdx+50h]
0x180010bac  cmp     eax, 50h ; 'P'
0x180010baf  jnb     short loc_180010BD9
0x180010bb1  mov     r9d, 2AEh; unsigned int
0x180010bb7  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180010bbe  mov     ecx, 80070216h; unsigned int
0x180010bc3  lea     rdx, aHr; "hr"
0x180010bca  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180010bcf  mov     ebx, 80090003h
0x180010bd4  jmp     loc_180010CDF
0x180010bd9  lea     edx, [rax+r11]
0x180010bdd  cmp     edx, eax
0x180010bdf  jnb     short loc_180010BE9
0x180010be1  mov     r9d, 2B5h
0x180010be7  jmp     short loc_180010BB7
0x180010be9  lea     eax, [rdx+r9]
0x180010bed  cmp     eax, edx
0x180010bef  jnb     short loc_180010BF9
0x180010bf1  mov     r9d, 2BCh
0x180010bf7  jmp     short loc_180010BB7
0x180010bf9  lea     edx, [rax+r14]
0x180010bfd  cmp     edx, eax
0x180010bff  jnb     short loc_180010C09
0x180010c01  mov     r9d, 2C3h
0x180010c07  jmp     short loc_180010BB7
0x180010c09  mov     r9d, [rcx+40h]
0x180010c0d  add     r9d, edx
0x180010c10  cmp     r9d, edx
0x180010c13  jnb     short loc_180010C1D
0x180010c15  mov     r9d, 2CBh
0x180010c1b  jmp     short loc_180010BB7
0x180010c1d  mov     r8d, [rcx+44h]
0x180010c21  add     r8d, r9d
0x180010c24  cmp     r8d, r9d
0x180010c27  jnb     short loc_180010C31
0x180010c29  mov     r9d, 2D2h
0x180010c2f  jmp     short loc_180010BB7
0x180010c31  lea     edx, [r8+rdi]
0x180010c35  cmp     edx, r8d
0x180010c38  jnb     short loc_180010C45
0x180010c3a  mov     r9d, 2DAh
0x180010c40  jmp     loc_180010BB7
0x180010c45  lea     eax, [rdx+rsi]
0x180010c48  cmp     eax, edx
0x180010c4a  jnb     short loc_180010C57
0x180010c4c  mov     r9d, 2E2h
0x180010c52  jmp     loc_180010BB7
0x180010c57  cmp     r12d, 1
0x180010c5b  jnz     short loc_180010C62
0x180010c5d  cmp     r10d, eax
0x180010c60  jnz     short loc_180010C67
0x180010c62  cmp     r10d, eax
0x180010c65  jnb     short loc_180010C6F
0x180010c67  mov     r9d, 2EEh
0x180010c6d  jmp     short loc_180010CC2
0x180010c6f  cmp     dword ptr [rcx+4], 4B53444Bh
0x180010c76  jnz     short loc_180010C8C
0x180010c78  cmp     dword ptr [rcx], 1
0x180010c7b  jnz     short loc_180010C8C
0x180010c7d  cmp     dword ptr [rcx+10h], 1Fh
0x180010c81  ja      short loc_180010C8C
0x180010c83  cmp     dword ptr [rcx+14h], 1Fh
0x180010c87  mov     ebx, r13d
0x180010c8a  jbe     short loc_180010CDF
0x180010c8c  mov     r9d, 2FBh
0x180010c92  jmp     short loc_180010CC2
0x180010c94  mov     r9d, 2A6h
0x180010c9a  jmp     short loc_180010CC2
0x180010c9c  mov     r9d, 298h
0x180010ca2  jmp     short loc_180010CC2
0x180010ca4  mov     r9d, 28Bh
0x180010caa  jmp     short loc_180010CC2
0x180010cac  mov     r9d, 280h
0x180010cb2  jmp     short loc_180010CC2
0x180010cb4  mov     r9d, 275h
0x180010cba  jmp     short loc_180010CC2
0x180010cbc  mov     r9d, 25Dh; unsigned int
0x180010cc2  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180010cc9  mov     ecx, 80090003h; unsigned int
0x180010cce  lea     rdx, aHr; "hr"
0x180010cd5  mov     ebx, 80090003h
0x180010cda  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180010cdf  mov     eax, ebx
0x180010ce1  add     rsp, 28h
0x180010ce5  pop     r15
0x180010ce7  pop     r14
0x180010ce9  pop     r13
0x180010ceb  pop     r12
0x180010ced  pop     rdi
0x180010cee  pop     rsi
0x180010cef  pop     rbp
0x180010cf0  pop     rbx
0x180010cf1  retn
```
