# IndexBCryptIsoObject(BCRYPTIUM_CONTEXT *,_BCRYPT_ISO_OBJECT *)

- ea: `0x14000a430`
- end: `0x14000a649`
- name: `?IndexBCryptIsoObject@@YAJPEAUBCRYPTIUM_CONTEXT@@PEAU_BCRYPT_ISO_OBJECT@@@Z`
- size: `537`
- prototype: `int(struct BCRYPTIUM_CONTEXT *, struct _BCRYPT_ISO_OBJECT *)`
- caller_count: `6`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140008538`
- `0x14000ee90`
- `0x14000fe40`
- `0x1400100d0`
- `0x140010cd0`
- `0x1400110a0`

## callees

- `0x140002160`
- `0x14000a430`
- `0x140011964`
- `0x1400119a4`
- `0x140011a70`
- `0x140011cf4`
- `0x140011e00`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalReAlloc` at `0x14000a52a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalReAlloc` at `0x14000a52a`
- `ntdll!RtlLeaveCriticalSection` at `0x14000a608`
- `ntdll!RtlLeaveCriticalSection` at `0x14000a608`
- `ntdll!RtlEnterCriticalSection` at `0x14000a47e`
- `ntdll!RtlEnterCriticalSection` at `0x14000a47e`

## pseudocode

```c
__int64 __fastcall IndexBCryptIsoObject(struct BCRYPTIUM_CONTEXT *a1, struct _BCRYPT_ISO_OBJECT *a2)
{
  __int64 v4; // r8
  __int64 v5; // r14
  unsigned int v6; // edi
  unsigned int v7; // esi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  HLOCAL v10; // rax
  unsigned int v11; // r8d
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 26);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 24));
  v5 = *((unsigned int *)a1 + 17);
  v6 = 0x7FFFFFFF;
  if ( (_DWORD)v5 == 0x7FFFFFFF )
  {
    v7 = -1073741801;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 28;
LABEL_8:
      WPP_SF_Dd(v8[2], v9, v4, v6, -1073741801);
      goto LABEL_29;
    }
    goto LABEL_29;
  }
  if ( (_DWORD)v5 != *((_DWORD *)a1 + 16) )
  {
LABEL_26:
    v14 = *((_QWORD *)a1 + 9);
    v7 = 0;
    *((_DWORD *)a1 + 17) = *(_DWORD *)(v14 + 8 * v5) >> 1;
    *(_QWORD *)(v14 + 8 * v5) = a2;
    *((_QWORD *)a2 + 3) = v5;
    BCryptIumReferenceObject(a2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        v15,
        (unsigned int)v5,
        *((_DWORD *)a1 + 17),
        *((_DWORD *)a2 + 8));
    goto LABEL_29;
  }
  if ( (unsigned int)((1 << (*((_DWORD *)a1 + 20) + 1)) - 1) < 0x7FFFFFFF )
    v6 = (1 << (*((_DWORD *)a1 + 20) + 1)) - 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_LLLL(*((_QWORD *)WPP_GLOBAL_Control + 2));
  v10 = LocalReAlloc(*((HLOCAL *)a1 + 9), 8LL * v6, 2u);
  if ( v10 )
  {
    v11 = *((_DWORD *)a1 + 16);
    *((_QWORD *)a1 + 9) = v10;
    while ( v11 < v6 )
    {
      v12 = v11;
      v13 = (2 * v11++ + 2) | 1LL;
      *(_QWORD *)(*((_QWORD *)a1 + 9) + 8 * v12) = v13;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 31);
    ++*((_DWORD *)a1 + 20);
    *((_DWORD *)a1 + 16) = v6;
    goto LABEL_26;
  }
  v7 = -1073741801;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 30;
    goto LABEL_8;
  }
LABEL_29:
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 24));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x22u, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x14000a430  push    rbx
0x14000a432  push    rbp
0x14000a433  push    rsi
0x14000a434  push    rdi
0x14000a435  push    r12
0x14000a437  push    r14
0x14000a439  push    r15
0x14000a43b  sub     rsp, 40h
0x14000a43f  mov     rbp, rdx
0x14000a442  mov     rbx, rcx
0x14000a445  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a44c  lea     r12, WPP_GLOBAL_Control
0x14000a453  cmp     rcx, r12
0x14000a456  jz      short loc_14000A47A
0x14000a458  test    byte ptr [rcx+1Ch], 4
0x14000a45c  jz      short loc_14000A47A
0x14000a45e  test    rdx, rdx
0x14000a461  jz      short loc_14000A469
0x14000a463  mov     r9d, [rdx+14h]
0x14000a467  jmp     short loc_14000A46C
0x14000a469  xor     r9d, r9d
0x14000a46c  mov     rcx, [rcx+10h]
0x14000a470  mov     edx, 1Ah
0x14000a475  call    WPP_SF_L
0x14000a47a  lea     rcx, [rbx+18h]; CriticalSection
0x14000a47e  call    cs:__imp_RtlEnterCriticalSection
0x14000a484  mov     r14d, [rbx+44h]
0x14000a488  mov     edi, 7FFFFFFFh
0x14000a48d  cmp     r14d, edi
0x14000a490  jnz     short loc_14000A4CD
0x14000a492  mov     eax, 0C0000017h
0x14000a497  mov     esi, eax
0x14000a499  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4a0  cmp     rcx, r12
0x14000a4a3  jz      loc_14000A604
0x14000a4a9  test    byte ptr [rcx+1Ch], 1
0x14000a4ad  jz      loc_14000A604
0x14000a4b3  mov     edx, 1Ch
0x14000a4b8  mov     rcx, [rcx+10h]
0x14000a4bc  mov     r9d, edi
0x14000a4bf  mov     [rsp+78h+var_58], eax
0x14000a4c3  call    WPP_SF_Dd
0x14000a4c8  jmp     loc_14000A604
0x14000a4cd  mov     r9d, [rbx+40h]
0x14000a4d1  cmp     r14d, r9d
0x14000a4d4  jnz     loc_14000A5B6
0x14000a4da  mov     edx, [rbx+50h]
0x14000a4dd  mov     eax, 1
0x14000a4e2  lea     r8d, [rdx+1]
0x14000a4e6  mov     ecx, r8d
0x14000a4e9  shl     eax, cl
0x14000a4eb  dec     eax
0x14000a4ed  cmp     eax, edi
0x14000a4ef  cmovb   edi, eax
0x14000a4f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4f9  cmp     rcx, r12
0x14000a4fc  jz      short loc_14000A51A
0x14000a4fe  test    byte ptr [rcx+1Ch], 4
0x14000a502  jz      short loc_14000A51A
0x14000a504  mov     rcx, [rcx+10h]
0x14000a508  mov     [rsp+78h+var_48], r8d
0x14000a50d  mov     [rsp+78h+var_50], edx
0x14000a511  mov     [rsp+78h+var_58], edi
0x14000a515  call    WPP_SF_LLLL
0x14000a51a  mov     rcx, [rbx+48h]; hMem
0x14000a51e  mov     r8d, 2; uFlags
0x14000a524  mov     edx, edi
0x14000a526  shl     rdx, 3; uBytes
0x14000a52a  call    cs:__imp_LocalReAlloc
0x14000a530  test    rax, rax
0x14000a533  jnz     short loc_14000A560
0x14000a535  mov     eax, 0C0000017h
0x14000a53a  mov     esi, eax
0x14000a53c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a543  cmp     rcx, r12
0x14000a546  jz      loc_14000A604
0x14000a54c  test    byte ptr [rcx+1Ch], 1
0x14000a550  jz      loc_14000A604
0x14000a556  mov     edx, 1Eh
0x14000a55b  jmp     loc_14000A4B8
0x14000a560  mov     r8d, [rbx+40h]
0x14000a564  mov     [rbx+48h], rax
0x14000a568  jmp     short loc_14000A584
0x14000a56a  mov     rax, [rbx+48h]
0x14000a56e  lea     edx, ds:2[r8*2]
0x14000a576  mov     ecx, r8d
0x14000a579  or      rdx, 1
0x14000a57d  inc     r8d
0x14000a580  mov     [rax+rcx*8], rdx
0x14000a584  cmp     r8d, edi
0x14000a587  jb      short loc_14000A56A
0x14000a589  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a590  cmp     rcx, r12
0x14000a593  jz      short loc_14000A5B0
0x14000a595  test    byte ptr [rcx+1Ch], 4
0x14000a599  jz      short loc_14000A5B0
0x14000a59b  mov     rcx, [rcx+10h]
0x14000a59f  mov     r9d, edi
0x14000a5a2  sub     r9d, [rbx+40h]
0x14000a5a6  mov     edx, 1Fh
0x14000a5ab  call    WPP_SF_L
0x14000a5b0  inc     dword ptr [rbx+50h]
0x14000a5b3  mov     [rbx+40h], edi
0x14000a5b6  mov     rcx, [rbx+48h]
0x14000a5ba  xor     esi, esi
0x14000a5bc  mov     eax, [rcx+r14*8]
0x14000a5c0  shr     eax, 1
0x14000a5c2  mov     [rbx+44h], eax
0x14000a5c5  mov     [rcx+r14*8], rbp
0x14000a5c9  mov     rcx, rbp; struct _BCRYPT_ISO_OBJECT *
0x14000a5cc  mov     [rbp+18h], r14
0x14000a5d0  call    ?BCryptIumReferenceObject@@YAJPEAU_BCRYPT_ISO_OBJECT@@@Z; BCryptIumReferenceObject(_BCRYPT_ISO_OBJECT *)
0x14000a5d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5dc  cmp     rcx, r12
0x14000a5df  jz      short loc_14000A604
0x14000a5e1  test    byte ptr [rcx+1Ch], 4
0x14000a5e5  jz      short loc_14000A604
0x14000a5e7  mov     eax, [rbp+20h]
0x14000a5ea  lea     edx, [rsi+20h]
0x14000a5ed  mov     rcx, [rcx+10h]
0x14000a5f1  mov     r9d, r14d
0x14000a5f4  mov     [rsp+78h+var_50], eax
0x14000a5f8  mov     eax, [rbx+44h]
0x14000a5fb  mov     [rsp+78h+var_58], eax
0x14000a5ff  call    WPP_SF_DDd
0x14000a604  lea     rcx, [rbx+18h]; CriticalSection
0x14000a608  call    cs:__imp_RtlLeaveCriticalSection
0x14000a60e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a615  cmp     rcx, r12
0x14000a618  jz      short loc_14000A638
0x14000a61a  test    byte ptr [rcx+1Ch], 4
0x14000a61e  jz      short loc_14000A638
0x14000a620  mov     rcx, [rcx+10h]
0x14000a624  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000a62b  mov     edx, 22h ; '"'
0x14000a630  mov     r9d, esi
0x14000a633  call    WPP_SF_d
0x14000a638  mov     eax, esi
0x14000a63a  add     rsp, 40h
0x14000a63e  pop     r15
0x14000a640  pop     r14
0x14000a642  pop     r12
0x14000a644  pop     rdi
0x14000a645  pop     rsi
0x14000a646  pop     rbp
0x14000a647  pop     rbx
0x14000a648  retn
```
