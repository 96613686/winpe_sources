# IndexListClassify

- ea: `0x140002a60`
- end: `0x140002eca`
- name: `IndexListClassify`
- size: `1130`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x140002a60`
- `0x140002ed0`
- `0x140004970`
- `0x140006c40`
- `0x140009520`
- `0x140009e00`
- `0x14000c210`
- `0x140038dc8`
- `0x14004efd4`
- `0x14004faf8`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002da8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002da8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002e7a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002e7a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002dfe`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002dfe`

## string_xrefs

- `0x140002e91`: `ExAllocateFromNPagedLookasideList`
- `0x140002eaf`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall IndexListClassify(__int64 *a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5, _QWORD *a6)
{
  __int64 v6; // rbx
  __int64 v7; // rsi
  _DWORD *v8; // r12
  _DWORD *v9; // r13
  __int64 v10; // r14
  __int64 v13; // rdi
  int v14; // eax
  __int64 v15; // rax
  unsigned int v16; // ecx
  _QWORD *v17; // r9
  unsigned __int64 v18; // rcx
  unsigned __int64 *v19; // rax
  __int64 v21; // rdx
  _DWORD *v22; // r14
  _DWORD *v23; // rsi
  __int64 v24; // rdi
  __int64 v25; // rbx
  bool v26; // dl
  signed __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // [rsp+80h] [rbp+8h] BYREF
  __int64 v31; // [rsp+98h] [rbp+20h]

  v31 = a4;
  v6 = *a1;
  v7 = 0;
  v8 = 0;
  v30 = 0;
  v9 = 0;
  v10 = a4;
  while ( 1 )
  {
    if ( (__int64 *)v6 == a1 )
    {
      if ( v9 )
        *a6 = v9;
      return v7;
    }
    v13 = *(_QWORD *)v6;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_ba5ca1c2eaf63c01ea1309a6ce5ccd57_Traceguids);
    }
    v14 = FilterMatchEx(v6, a2, a3, 0, (__int64)&v30);
    v7 = v30;
    if ( v30 )
      break;
    if ( v14 )
    {
      v15 = *a5;
      if ( !*a5
        || (v16 = *(_DWORD *)(v15 + 60), *(_DWORD *)(v6 + 60) < v16)
        || *(_DWORD *)(v6 + 60) > v16
        || (a3 = *(_QWORD *)(v15 + 24),
            v17 = *(_QWORD **)(v6 + 24),
            v18 = **(_QWORD **)(a3 + 16),
            v19 = (unsigned __int64 *)v17[2],
            *v19 >= v18)
        && (*v19 > v18 || *v17 > *(_QWORD *)a3) )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v6 + 24) + 40LL) & 0x1000) != 0 )
          *a5 = v6;
        if ( v8 && *((_WORD *)v8 + 12) < 7u )
        {
          _InterlockedIncrement64((volatile signed __int64 *)(v6 + 16));
          *(_QWORD *)&v8[2 * (unsigned __int16)(*((_WORD *)v8 + 12))++ + 8] = v6;
          v7 = 0;
          v30 = 0;
LABEL_18:
          if ( !v9 )
            v9 = v8;
          goto LABEL_7;
        }
        if ( v10 && (v21 = *(unsigned __int16 *)(v10 + 16), (unsigned int)v21 < 3) )
        {
          v22 = (_DWORD *)(96 * v21 + v10 + 24);
          v7 = 0;
          *(_WORD *)(v31 + 16) = v21 + 1;
          v22[7] = 1;
        }
        else
        {
          v7 = 0;
          v22 = ExAllocateFromNPagedLookasideList(gWfpGlobal);
          if ( !v22 )
          {
            v29 = WfpReportSysErrorAsNtStatus(v28, "ExAllocateFromNPagedLookasideList", 3221225495LL, 1);
            v7 = v29;
            if ( v29 )
            {
              WfpReportError(v29, "WfpAllocFromNPagedLookasideList");
LABEL_30:
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
              {
                WPP_SF_sd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  15,
                  (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                  (unsigned int)"InsertFilterToMatchBuf",
                  v7);
              }
LABEL_34:
              v30 = v7;
              if ( v7 )
                break;
              v10 = v31;
              goto LABEL_18;
            }
          }
          v22[7] = 0;
        }
        *((_QWORD *)v22 + 1) = v22;
        *(_QWORD *)v22 = v22;
        *((_QWORD *)v22 + 2) = 0;
        v22[6] = -65536;
        *((_QWORD *)v22 + 11) = 0;
        _InterlockedIncrement64((volatile signed __int64 *)(v6 + 16));
        ++*((_WORD *)v22 + 12);
        *((_QWORD *)v22 + 4) = v6;
        if ( v8 )
          *((_QWORD *)v8 + 2) = v22;
        v8 = v22;
        if ( !v7 )
          goto LABEL_34;
        goto LABEL_30;
      }
    }
LABEL_7:
    v6 = v13;
  }
  *a6 = 0;
  if ( v9 )
  {
    do
    {
      v23 = (_DWORD *)*((_QWORD *)v9 + 2);
      v24 = 0;
      if ( *((_WORD *)v9 + 12) )
      {
        while ( 1 )
        {
          v25 = *(_QWORD *)&v9[2 * v24 + 8];
          v26 = 0;
          _InterlockedIncrement64((volatile signed __int64 *)(v25 + 16));
          v27 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v25 + 16), 0xFFFFFFFFFFFFFFFFuLL) - 2;
          if ( (_DWORD)v27 == HIDWORD(v27) )
          {
            _m_prefetchw((const void *)(v25 + 52));
            v26 = (_InterlockedOr((volatile signed __int32 *)(v25 + 52), 0x10u) & 0x10) == 0;
          }
          if ( (*(_DWORD *)(*(_QWORD *)(v25 + 24) + 40LL) & 0x4000) == 0 || !v26 )
            goto LABEL_42;
          if ( !KeGetCurrentIrql() )
            break;
          NetioInsertWorkQueue(&gWfpGlobal[10].L.FreeEx);
LABEL_44:
          v24 = (unsigned int)(v24 + 1);
          if ( (unsigned int)v24 >= *((unsigned __int16 *)v9 + 12) )
            goto LABEL_45;
        }
        FeNotifyIntFilterDelete(v25);
LABEL_42:
        if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(v25 + 16), 0xFFFFFFFFFFFFFFFFuLL) == 1 )
          FreeWFPFilter((_QWORD *)v25);
        goto LABEL_44;
      }
LABEL_45:
      if ( (v9[7] & 1) == 0 )
      {
        if ( *((_QWORD *)v9 + 11) )
          WfpPoolFree(v9 + 22);
        ExFreeToNPagedLookasideList(gWfpGlobal, v9);
      }
      v9 = v23;
    }
    while ( v23 );
    v7 = v30;
  }
  if ( v7 )
    WfpReportError(v7, "IndexListClassify");
  return v7;
}

```

## disassembly

```asm
0x140002a60  mov     rax, rsp
0x140002a63  mov     [rax+20h], r9
0x140002a67  push    rbx
0x140002a68  push    rbp
0x140002a69  push    rsi
0x140002a6a  push    r12
0x140002a6c  push    r13
0x140002a6e  push    r14
0x140002a70  push    r15
0x140002a72  sub     rsp, 40h
0x140002a76  mov     rbx, [rcx]
0x140002a79  xor     esi, esi
0x140002a7b  xor     r12d, r12d
0x140002a7e  mov     [rax+8], rsi
0x140002a82  xor     r13d, r13d
0x140002a85  mov     [rax+10h], rdi
0x140002a89  mov     r14, r9
0x140002a8c  mov     rbp, rdx
0x140002a8f  mov     r15, rcx
0x140002a92  lea     rax, WPP_GLOBAL_Control
0x140002a99  cmp     rbx, r15
0x140002a9c  jz      loc_140002B7A
0x140002aa2  mov     rdi, [rbx]
0x140002aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x140002aac  cmp     rcx, rax
0x140002aaf  jz      short loc_140002ABB
0x140002ab1  cmp     byte ptr [rcx+29h], 6
0x140002ab5  jnb     loc_140002E37
0x140002abb  lea     rax, [rsp+78h+arg_0]
0x140002ac3  xor     r9d, r9d
0x140002ac6  mov     rdx, rbp
0x140002ac9  mov     [rsp+78h+var_58], rax
0x140002ace  mov     rcx, rbx
0x140002ad1  call    FilterMatchEx
0x140002ad6  mov     rsi, [rsp+78h+arg_0]
0x140002ade  test    rsi, rsi
0x140002ae1  jnz     loc_140002CC7
0x140002ae7  test    eax, eax
0x140002ae9  jnz     short loc_140002AF0
0x140002aeb  mov     rbx, rdi
0x140002aee  jmp     short loc_140002A92
0x140002af0  mov     rdx, [rsp+78h+arg_20]
0x140002af8  mov     rax, [rdx]
0x140002afb  test    rax, rax
0x140002afe  jz      short loc_140002B28
0x140002b00  mov     ecx, [rax+3Ch]
0x140002b03  cmp     [rbx+3Ch], ecx
0x140002b06  jb      short loc_140002B28
0x140002b08  ja      short loc_140002B28
0x140002b0a  mov     r8, [rax+18h]
0x140002b0e  mov     r9, [rbx+18h]
0x140002b12  mov     rax, [r8+10h]
0x140002b16  mov     rcx, [rax]
0x140002b19  mov     rax, [r9+10h]
0x140002b1d  cmp     [rax], rcx
0x140002b20  jb      short loc_140002AEB
0x140002b22  jbe     loc_140002DCD
0x140002b28  mov     rax, [rbx+18h]
0x140002b2c  test    dword ptr [rax+28h], 1000h
0x140002b33  jz      short loc_140002B38
0x140002b35  mov     [rdx], rbx
0x140002b38  test    r12, r12
0x140002b3b  jz      loc_140002BED
0x140002b41  cmp     word ptr [r12+18h], 7
0x140002b48  jnb     loc_140002BED
0x140002b4e  lock inc qword ptr [rbx+10h]
0x140002b53  movzx   eax, word ptr [r12+18h]
0x140002b59  mov     [r12+rax*8+20h], rbx
0x140002b5e  inc     word ptr [r12+18h]
0x140002b64  xor     esi, esi
0x140002b66  mov     [rsp+78h+arg_0], rsi
0x140002b6e  test    r13, r13
0x140002b71  cmovz   r13, r12
0x140002b75  jmp     loc_140002AEB
0x140002b7a  test    r13, r13
0x140002b7d  jz      short loc_140002B91
0x140002b7f  mov     rax, [rsp+78h+arg_28]
0x140002b87  mov     [rax], r13
0x140002b8a  lea     rax, WPP_GLOBAL_Control
0x140002b91  test    rsi, rsi
0x140002b94  jz      short loc_140002BD1
0x140002b96  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b9d  cmp     rcx, rax
0x140002ba0  jz      short loc_140002BD1
0x140002ba2  cmp     byte ptr [rcx+29h], 2
0x140002ba6  jb      short loc_140002BD1
0x140002ba8  test    dword ptr [rcx+2Ch], 1000h
0x140002baf  jz      short loc_140002BD1
0x140002bb1  mov     rcx, [rcx+18h]
0x140002bb5  lea     r9, aIndexlistclass_0; "IndexListClassify"
0x140002bbc  mov     edx, 0Fh
0x140002bc1  mov     dword ptr [rsp+78h+var_58], esi
0x140002bc5  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140002bcc  call    WPP_SF_sd
0x140002bd1  mov     rdi, [rsp+78h+arg_8]
0x140002bd9  mov     rax, rsi
0x140002bdc  add     rsp, 40h
0x140002be0  pop     r15
0x140002be2  pop     r14
0x140002be4  pop     r13
0x140002be6  pop     r12
0x140002be8  pop     rsi
0x140002be9  pop     rbp
0x140002bea  pop     rbx
0x140002beb  retn
0x140002bed  test    r14, r14
0x140002bf0  jz      loc_140002D9F
0x140002bf6  movzx   edx, word ptr [r14+10h]
0x140002bfb  cmp     edx, 3
0x140002bfe  jnb     loc_140002D9F
0x140002c04  mov     rax, [rsp+78h+arg_18]
0x140002c0c  lea     rcx, [rdx+rdx*2]
0x140002c10  shl     rcx, 5
0x140002c14  add     r14, 18h
0x140002c18  add     r14, rcx
0x140002c1b  xor     esi, esi
0x140002c1d  inc     dx
0x140002c20  mov     [rax+10h], dx
0x140002c24  mov     dword ptr [r14+1Ch], 1
0x140002c2c  mov     [r14+8], r14
0x140002c30  mov     [r14], r14
0x140002c33  mov     qword ptr [r14+10h], 0
0x140002c3b  mov     dword ptr [r14+18h], 0FFFF0000h
0x140002c43  mov     qword ptr [r14+58h], 0
0x140002c4b  lock inc qword ptr [rbx+10h]
0x140002c50  inc     word ptr [r14+18h]
0x140002c55  mov     [r14+20h], rbx
0x140002c59  test    r12, r12
0x140002c5c  jz      short loc_140002C63
0x140002c5e  mov     [r12+10h], r14
0x140002c63  mov     r12, r14
0x140002c66  test    rsi, rsi
0x140002c69  jz      short loc_140002CAD
0x140002c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c72  lea     rax, WPP_GLOBAL_Control
0x140002c79  cmp     rcx, rax
0x140002c7c  jz      short loc_140002CAD
0x140002c7e  cmp     byte ptr [rcx+29h], 2
0x140002c82  jb      short loc_140002CAD
0x140002c84  test    dword ptr [rcx+2Ch], 1000h
0x140002c8b  jz      short loc_140002CAD
0x140002c8d  mov     rcx, [rcx+18h]
0x140002c91  lea     r9, aInsertfilterto; "InsertFilterToMatchBuf"
0x140002c98  mov     edx, 0Fh
0x140002c9d  mov     dword ptr [rsp+78h+var_58], esi
0x140002ca1  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140002ca8  call    WPP_SF_sd
0x140002cad  mov     [rsp+78h+arg_0], rsi
0x140002cb5  test    rsi, rsi
0x140002cb8  jnz     short loc_140002CC7
0x140002cba  mov     r14, [rsp+78h+arg_18]
0x140002cc2  jmp     loc_140002B6E
0x140002cc7  mov     rax, [rsp+78h+arg_28]
0x140002ccf  mov     qword ptr [rax], 0
0x140002cd6  test    r13, r13
0x140002cd9  jz      loc_140002D82
0x140002cdf  mov     rsi, [r13+10h]
0x140002ce3  xor     edi, edi
0x140002ce5  xor     eax, eax
0x140002ce7  mov     [rsp+78h+var_48], rsi
0x140002cec  cmp     ax, [r13+18h]
0x140002cf1  jnb     short loc_140002D62
0x140002cf3  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x140002cfa  mov     esi, 1
0x140002cff  mov     rbx, [r13+rdi*8+20h]
0x140002d04  xor     dl, dl
0x140002d06  lock inc qword ptr [rbx+10h]
0x140002d0b  mov     rcx, rbp
0x140002d0e  lock xadd [rbx+10h], rcx
0x140002d14  sub     rcx, 2
0x140002d18  mov     rax, rcx
0x140002d1b  shr     rax, 20h
0x140002d1f  cmp     ecx, eax
0x140002d21  jz      loc_140002DDE
0x140002d27  mov     rax, [rbx+18h]
0x140002d2b  test    dword ptr [rax+28h], 4000h
0x140002d32  jz      short loc_140002D3C
0x140002d34  test    dl, dl
0x140002d36  jnz     loc_140002DFE
0x140002d3c  mov     rax, rbp
0x140002d3f  lock xadd [rbx+10h], rax
0x140002d45  cmp     rax, rsi
0x140002d48  jnz     short loc_140002D52
0x140002d4a  mov     rcx, rbx; P
0x140002d4d  call    FreeWFPFilter
0x140002d52  movzx   eax, word ptr [r13+18h]
0x140002d57  inc     edi
0x140002d59  cmp     edi, eax
0x140002d5b  jb      short loc_140002CFF
0x140002d5d  mov     rsi, [rsp+78h+var_48]
0x140002d62  mov     eax, [r13+1Ch]
0x140002d66  test    al, 1
0x140002d68  jz      loc_140002E65
0x140002d6e  mov     r13, rsi
0x140002d71  test    rsi, rsi
0x140002d74  jnz     loc_140002CDF
0x140002d7a  mov     rsi, [rsp+78h+arg_0]
0x140002d82  test    rsi, rsi
0x140002d85  jz      loc_140002BD1
0x140002d8b  lea     rdx, aIndexlistclass_0; "IndexListClassify"
0x140002d92  mov     rcx, rsi
0x140002d95  call    WfpReportError
0x140002d9a  jmp     loc_140002BD1
0x140002d9f  mov     rcx, cs:gWfpGlobal; Lookaside
0x140002da6  xor     esi, esi
0x140002da8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002daf  nop     dword ptr [rax+rax+00h]
0x140002db4  mov     r14, rax
0x140002db7  test    rax, rax
0x140002dba  jz      loc_140002E8B
0x140002dc0  mov     dword ptr [r14+1Ch], 0
0x140002dc8  jmp     loc_140002C2C
0x140002dcd  mov     rax, [r8]
0x140002dd0  cmp     [r9], rax
0x140002dd3  jbe     loc_140002AEB
0x140002dd9  jmp     loc_140002B28
0x140002dde  prefetchw byte ptr [rbx+34h]
0x140002de2  mov     eax, [rbx+34h]
0x140002de5  mov     ecx, eax
0x140002de7  or      ecx, 10h
0x140002dea  lock cmpxchg [rbx+34h], ecx
0x140002def  jnz     short loc_140002DE5
0x140002df1  test    al, 10h
0x140002df3  movzx   edx, dl
0x140002df6  cmovz   edx, esi
0x140002df9  jmp     loc_140002D27
0x140002dfe  call    cs:__imp_KeGetCurrentIrql
0x140002e05  nop     dword ptr [rax+rax+00h]
0x140002e0a  test    al, al
0x140002e0c  jnz     short loc_140002E1B
0x140002e0e  mov     rcx, rbx
0x140002e11  call    FeNotifyIntFilterDelete
0x140002e16  jmp     loc_140002D3C
0x140002e1b  mov     rcx, cs:gWfpGlobal
0x140002e22  lea     rdx, [rbx+28h]
0x140002e26  add     rcx, 538h; Context
0x140002e2d  call    NetioInsertWorkQueue
0x140002e32  jmp     loc_140002D52
0x140002e37  test    dword ptr [rcx+2Ch], 2000h
0x140002e3e  jz      loc_140002ABB
0x140002e44  mov     r9, [rbx+18h]
0x140002e48  lea     r8, WPP_ba5ca1c2eaf63c01ea1309a6ce5ccd57_Traceguids
0x140002e4f  mov     rcx, [rcx+18h]
0x140002e53  mov     edx, 0Ah
0x140002e58  mov     r9, [r9]
0x140002e5b  call    WPP_SF_q
0x140002e60  jmp     loc_140002ABB
0x140002e65  cmp     qword ptr [r13+58h], 0
0x140002e6a  lea     rcx, [r13+58h]
0x140002e6e  jnz     short loc_140002EC3
0x140002e70  mov     rcx, cs:gWfpGlobal; Lookaside
0x140002e77  mov     rdx, r13; Entry
0x140002e7a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002e81  nop     dword ptr [rax+rax+00h]
0x140002e86  jmp     loc_140002D6E
0x140002e8b  mov     r9d, 1
0x140002e91  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x140002e98  mov     r8d, 0C0000017h
0x140002e9e  call    WfpReportSysErrorAsNtStatus
0x140002ea3  mov     rsi, rax
0x140002ea6  test    rax, rax
0x140002ea9  jz      loc_140002DC0
0x140002eaf  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x140002eb6  mov     rcx, rax
0x140002eb9  call    WfpReportError
0x140002ebe  jmp     loc_140002C6B
0x140002ec3  call    WfpPoolFree
0x140002ec8  jmp     short loc_140002E70
```
