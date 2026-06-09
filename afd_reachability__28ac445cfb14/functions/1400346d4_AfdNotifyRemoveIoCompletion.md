# AfdNotifyRemoveIoCompletion

- ea: `0x1400346d4`
- end: `0x140034a15`
- name: `AfdNotifyRemoveIoCompletion`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400511c0`

## callees

- `0x1400346d4`
- `0x1400726a0`
- `0x140072b00`
- `0x140092008`
- `0x140092254`

## import_xrefs

- `ntoskrnl!IoRemoveIoCompletion` at `0x1400348ba`
- `ntoskrnl!IoRemoveIoCompletion` at `0x1400348ba`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140034950`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140034950`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400349b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400349de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400349b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400349de`
- `ntoskrnl!ExAllocatePool2` at `0x1400347f4`
- `ntoskrnl!ExAllocatePool2` at `0x140034862`
- `ntoskrnl!ExAllocatePool2` at `0x1400347f4`
- `ntoskrnl!ExAllocatePool2` at `0x140034862`
- `ntoskrnl!IoIs32bitProcess` at `0x14003476a`
- `ntoskrnl!IoIs32bitProcess` at `0x14003476a`
- `ntoskrnl!ProbeForWrite` at `0x1400347ba`
- `ntoskrnl!ProbeForWrite` at `0x1400347ba`

## pseudocode

```c
__int64 __fastcall AfdNotifyRemoveIoCompletion(char a1, __int64 a2, __int64 a3)
{
  _BYTE *v4; // rdi
  _BYTE *Pool2; // rbx
  unsigned __int64 v6; // rsi
  unsigned int v7; // esi
  BOOLEAN v8; // r13
  SIZE_T v9; // rcx
  ULONG v10; // r8d
  __int64 v11; // rax
  __int64 *v12; // r12
  __int64 v13; // rdx
  unsigned int *v14; // rax
  unsigned int v17; // [rsp+50h] [rbp-308h] BYREF
  _BYTE *v18; // [rsp+58h] [rbp-300h]
  _BYTE *v19; // [rsp+60h] [rbp-2F8h]
  __int64 v20; // [rsp+68h] [rbp-2F0h]
  __int64 v21; // [rsp+78h] [rbp-2E0h] BYREF
  __int64 v22; // [rsp+80h] [rbp-2D8h]
  __int64 Src; // [rsp+88h] [rbp-2D0h] BYREF
  int v24; // [rsp+90h] [rbp-2C8h]
  int v25; // [rsp+94h] [rbp-2C4h]
  _BYTE v26[128]; // [rsp+A0h] [rbp-2B8h] BYREF
  _BYTE v27[512]; // [rsp+120h] [rbp-238h] BYREF

  v22 = a2;
  v20 = a3;
  v21 = 0;
  memset(v26, 0, sizeof(v26));
  v4 = 0;
  v19 = 0;
  Pool2 = 0;
  v17 = 0;
  v6 = *(unsigned int *)(a3 + 40);
  if ( !(_DWORD)v6 )
    goto LABEL_2;
  Src = 0;
  if ( !is_mul_ok(v6, 0x20u) )
  {
    v7 = -1073741675;
    goto LABEL_36;
  }
  v8 = IoIs32bitProcess(0);
  if ( v8 )
  {
    Src = 0;
    v9 = -1;
    if ( is_mul_ok(*(unsigned int *)(a3 + 40), 0x10u) )
      v9 = 16LL * *(unsigned int *)(a3 + 40);
    v10 = 4;
  }
  else
  {
    v9 = 32 * v6;
    v10 = 8;
  }
  if ( a1 )
    ProbeForWrite(*(volatile void **)(a3 + 16), v9, v10);
  if ( v8 )
  {
    if ( (unsigned int)v6 <= 0x10 )
    {
      Pool2 = v27;
    }
    else
    {
      Pool2 = (_BYTE *)ExAllocatePool2(258, 32 * v6, 1315202625);
      v18 = Pool2;
      if ( Pool2 )
        goto LABEL_18;
      Pool2 = v27;
      LODWORD(v6) = 16;
    }
  }
  else
  {
    Pool2 = *(_BYTE **)(a3 + 16);
  }
  v18 = Pool2;
LABEL_18:
  v11 = *(unsigned int *)(a3 + 36);
  if ( (_DWORD)v11 == -1 )
  {
    v12 = 0;
  }
  else
  {
    v21 = -10000 * v11;
    v12 = &v21;
  }
  if ( (unsigned int)v6 <= 0x10 )
    goto LABEL_24;
  v4 = (_BYTE *)ExAllocatePool2(66, 8LL * (unsigned int)v6, 1315202625);
  v19 = v4;
  if ( !v4 )
  {
    LODWORD(v6) = 16;
LABEL_24:
    v4 = v26;
    v19 = v26;
  }
  v7 = IoRemoveIoCompletion(v22, Pool2, v4, (unsigned int)v6, &v17, a1, v12, 0);
  if ( v7 )
    goto LABEL_36;
  if ( v8 )
  {
    while ( v7 < v17 )
    {
      v13 = 32LL * v7;
      LODWORD(Src) = *(_DWORD *)&Pool2[v13];
      HIDWORD(Src) = *(_DWORD *)&Pool2[v13 + 8];
      v25 = *(_DWORD *)&Pool2[v13 + 24];
      v24 = *(_DWORD *)&Pool2[v13 + 16];
      RtlCopyToUser((void *)(*(_QWORD *)(a3 + 16) + 16LL * v7++), &Src, 0x10u);
    }
  }
  v14 = *(unsigned int **)(a3 + 24);
  if ( v17 && ((unsigned __int8)v14 & 3) != 0 )
    ExRaiseDatatypeMisalignment();
  if ( a1 )
    RtlWriteULongToUser(v14, v17);
  else
    *v14 = v17;
LABEL_2:
  v7 = 0;
LABEL_36:
  if ( Pool2 && Pool2 != v27 && Pool2 != *(_BYTE **)(a3 + 16) )
    ExFreePoolWithTag(Pool2, 0x4E646641u);
  if ( v4 && v4 != v26 )
    ExFreePoolWithTag(v4, 0x4E646641u);
  return v7;
}

```

## disassembly

```asm
0x1400346d4  mov     [rsp+arg_18], rbx
0x1400346d9  push    rsi
0x1400346da  push    rdi
0x1400346db  push    r12
0x1400346dd  push    r13
0x1400346df  push    r14
0x1400346e1  sub     rsp, 330h
0x1400346e8  mov     rax, cs:__security_cookie
0x1400346ef  xor     rax, rsp
0x1400346f2  mov     [rsp+358h+var_38], rax
0x1400346fa  mov     r14, r8
0x1400346fd  mov     [rsp+358h+var_2D8], rdx
0x140034705  mov     [rsp+358h+var_318], cl
0x140034709  mov     [rsp+358h+var_310], cl
0x14003470d  mov     [rsp+358h+var_2F0], r8
0x140034712  mov     [rsp+358h+var_2E0], 0
0x14003471b  xor     edx, edx; Val
0x14003471d  mov     r8d, 80h; Size
0x140034723  lea     rcx, [rsp+358h+var_2B8]; void *
0x14003472b  call    memset
0x140034730  xor     edi, edi
0x140034732  mov     [rsp+358h+var_2F8], rdi
0x140034737  xor     ebx, ebx
0x140034739  mov     [rsp+358h+var_308], ebx
0x14003473d  mov     esi, [r14+28h]
0x140034741  test    esi, esi
0x140034743  jnz     short loc_14003474C
0x140034745  xor     esi, esi
0x140034747  jmp     loc_140034998
0x14003474c  mov     [rsp+358h+Src], rbx
0x140034754  mov     eax, 20h ; ' '
0x140034759  mul     rsi
0x14003475c  mov     r12, rax
0x14003475f  test    rdx, rdx
0x140034762  jnz     loc_140034993
0x140034768  xor     ecx, ecx; Irp
0x14003476a  call    cs:__imp_IoIs32bitProcess
0x140034771  nop     dword ptr [rax+rax+00h]
0x140034776  mov     r13b, al
0x140034779  test    al, al
0x14003477b  jz      short loc_1400347A4
0x14003477d  mov     [rsp+358h+Src], rbx
0x140034785  mov     ecx, [r14+28h]
0x140034789  mov     eax, 10h
0x14003478e  mul     rcx
0x140034791  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140034795  test    rdx, rdx
0x140034798  cmovz   rcx, rax
0x14003479c  mov     r8d, 4
0x1400347a2  jmp     short loc_1400347AD
0x1400347a4  mov     rcx, r12
0x1400347a7  mov     r8d, 8; Alignment
0x1400347ad  cmp     [rsp+358h+var_318], bl
0x1400347b1  jz      short loc_1400347DC
0x1400347b3  mov     rdx, rcx; Length
0x1400347b6  mov     rcx, [r14+10h]; Address
0x1400347ba  call    cs:__imp_ProbeForWrite
0x1400347c1  nop     dword ptr [rax+rax+00h]
0x1400347c6  jmp     short loc_1400347DC
0x1400347c8  mov     esi, eax
0x1400347ca  mov     rdi, [rsp+358h+var_2F8]
0x1400347cf  mov     rbx, rdi
0x1400347d2  mov     r14, [rsp+358h+var_2F0]
0x1400347d7  jmp     loc_140034998
0x1400347dc  test    r13b, r13b
0x1400347df  jz      short loc_140034824
0x1400347e1  cmp     esi, 10h
0x1400347e4  jbe     short loc_14003481A
0x1400347e6  mov     r8d, 4E646641h
0x1400347ec  mov     rdx, r12
0x1400347ef  mov     ecx, 102h
0x1400347f4  call    cs:__imp_ExAllocatePool2
0x1400347fb  nop     dword ptr [rax+rax+00h]
0x140034800  mov     rbx, rax
0x140034803  mov     [rsp+358h+var_300], rax
0x140034808  test    rax, rax
0x14003480b  jnz     short loc_14003482D
0x14003480d  lea     rbx, [rsp+358h+var_238]
0x140034815  lea     esi, [rax+10h]
0x140034818  jmp     short loc_140034828
0x14003481a  lea     rbx, [rsp+358h+var_238]
0x140034822  jmp     short loc_140034828
0x140034824  mov     rbx, [r14+10h]
0x140034828  mov     [rsp+358h+var_300], rbx
0x14003482d  mov     eax, [r14+24h]
0x140034831  cmp     eax, 0FFFFFFFFh
0x140034834  jz      short loc_140034849
0x140034836  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x14003483d  mov     [rsp+358h+var_2E0], rcx
0x140034842  lea     r12, [rsp+358h+var_2E0]
0x140034847  jmp     short loc_14003484C
0x140034849  xor     r12d, r12d
0x14003484c  cmp     esi, 10h
0x14003484f  jbe     short loc_14003487E
0x140034851  mov     edx, esi
0x140034853  shl     rdx, 3
0x140034857  mov     ecx, 42h ; 'B'
0x14003485c  mov     r8d, 4E646641h
0x140034862  call    cs:__imp_ExAllocatePool2
0x140034869  nop     dword ptr [rax+rax+00h]
0x14003486e  mov     rdi, rax
0x140034871  mov     [rsp+358h+var_2F8], rax
0x140034876  test    rax, rax
0x140034879  jnz     short loc_14003488B
0x14003487b  lea     esi, [rax+10h]
0x14003487e  lea     rdi, [rsp+358h+var_2B8]
0x140034886  mov     [rsp+358h+var_2F8], rdi
0x14003488b  mov     [rsp+358h+var_320], 0
0x140034890  mov     [rsp+358h+var_328], r12
0x140034895  mov     r12b, [rsp+358h+var_318]
0x14003489a  mov     [rsp+358h+var_330], r12b
0x14003489f  lea     rax, [rsp+358h+var_308]
0x1400348a4  mov     [rsp+358h+var_338], rax
0x1400348a9  mov     r9d, esi
0x1400348ac  mov     r8, rdi
0x1400348af  mov     rdx, rbx
0x1400348b2  mov     rcx, [rsp+358h+var_2D8]
0x1400348ba  call    cs:__imp_IoRemoveIoCompletion
0x1400348c1  nop     dword ptr [rax+rax+00h]
0x1400348c6  mov     esi, eax
0x1400348c8  test    eax, eax
0x1400348ca  jnz     loc_140034998
0x1400348d0  test    r13b, r13b
0x1400348d3  jz      short loc_140034941
0x1400348d5  cmp     esi, [rsp+358h+var_308]
0x1400348d9  jnb     short loc_140034941
0x1400348db  mov     ecx, esi
0x1400348dd  mov     edx, esi
0x1400348df  shl     rdx, 5
0x1400348e3  mov     eax, [rdx+rbx]
0x1400348e6  mov     dword ptr [rsp+358h+Src], eax
0x1400348ed  mov     eax, [rdx+rbx+8]
0x1400348f1  mov     dword ptr [rsp+358h+Src+4], eax
0x1400348f8  mov     eax, [rdx+rbx+18h]
0x1400348fc  mov     [rsp+358h+var_2C4], eax
0x140034903  mov     eax, [rdx+rbx+10h]
0x140034907  mov     [rsp+358h+var_2C8], eax
0x14003490e  shl     rcx, 4
0x140034912  add     rcx, [r14+10h]; void *
0x140034916  mov     r8d, 10h; Size
0x14003491c  lea     rdx, [rsp+358h+Src]; Src
0x140034924  call    RtlCopyToUser
0x140034929  nop
0x14003492a  inc     esi
0x14003492c  jmp     short loc_1400348D5
0x14003492e  mov     esi, eax
0x140034930  mov     rdi, [rsp+358h+var_2F8]
0x140034935  mov     rbx, [rsp+358h+var_300]
0x14003493a  mov     r14, [rsp+358h+var_2F0]
0x14003493f  jmp     short loc_140034998
0x140034941  mov     rax, [r14+18h]
0x140034945  cmp     [rsp+358h+var_308], 0
0x14003494a  jz      short loc_14003495D
0x14003494c  test    al, 3
0x14003494e  jz      short loc_14003495D
0x140034950  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140034957  nop     dword ptr [rax+rax+00h]
0x14003495c  int     3; Trap to Debugger
0x14003495d  mov     ecx, [rsp+358h+var_308]
0x140034961  test    r12b, r12b
0x140034964  jz      short loc_140034972
0x140034966  mov     edx, ecx
0x140034968  mov     rcx, rax
0x14003496b  call    RtlWriteULongToUser
0x140034970  jmp     short loc_140034974
0x140034972  mov     [rax], ecx
0x140034974  jmp     loc_140034745
0x140034979  mov     esi, eax
0x14003497b  mov     rdi, [rsp+358h+var_2F8]
0x140034980  mov     rbx, [rsp+358h+var_300]
0x140034985  mov     r14, [rsp+358h+var_2F0]
0x14003498a  test    eax, eax
0x14003498c  js      short loc_140034998
0x14003498e  jmp     loc_140034745
0x140034993  mov     esi, 0C0000095h
0x140034998  test    rbx, rbx
0x14003499b  jz      short loc_1400349C4
0x14003499d  lea     rax, [rsp+358h+var_238]
0x1400349a5  cmp     rbx, rax
0x1400349a8  jz      short loc_1400349C4
0x1400349aa  cmp     rbx, [r14+10h]
0x1400349ae  jz      short loc_1400349C4
0x1400349b0  mov     edx, 4E646641h; Tag
0x1400349b5  mov     rcx, rbx; P
0x1400349b8  call    cs:__imp_ExFreePoolWithTag
0x1400349bf  nop     dword ptr [rax+rax+00h]
0x1400349c4  test    rdi, rdi
0x1400349c7  jz      short loc_1400349EA
0x1400349c9  lea     rax, [rsp+358h+var_2B8]
0x1400349d1  cmp     rdi, rax
0x1400349d4  jz      short loc_1400349EA
0x1400349d6  mov     edx, 4E646641h; Tag
0x1400349db  mov     rcx, rdi; P
0x1400349de  call    cs:__imp_ExFreePoolWithTag
0x1400349e5  nop     dword ptr [rax+rax+00h]
0x1400349ea  mov     eax, esi
0x1400349ec  mov     rcx, [rsp+358h+var_38]
0x1400349f4  xor     rcx, rsp; StackCookie
0x1400349f7  call    __security_check_cookie
0x1400349fc  mov     rbx, [rsp+358h+arg_18]
0x140034a04  add     rsp, 330h
0x140034a0b  pop     r14
0x140034a0d  pop     r13
0x140034a0f  pop     r12
0x140034a11  pop     rdi
0x140034a12  pop     rsi
0x140034a13  retn
0x140073a10  push    rbp
0x140073a12  sub     rsp, 40h
0x140073a16  mov     rbp, rdx
0x140073a19  xor     eax, eax
0x140073a1b  cmp     [rbp+48h], al
0x140073a1e  setnz   al
0x140073a21  mov     [rbp+70h], eax
0x140073a24  mov     eax, [rbp+70h]
0x140073a27  add     rsp, 40h
0x140073a2b  pop     rbp
0x140073a2c  retn
```
