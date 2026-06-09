# AfdNotifyRemoveIoCompletion

- ea: `0x1400346f4`
- end: `0x140034a35`
- name: `AfdNotifyRemoveIoCompletion`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140051260`

## callees

- `0x1400346f4`
- `0x140072840`
- `0x140072c80`
- `0x140092008`
- `0x140092254`

## import_xrefs

- `ntoskrnl!IoRemoveIoCompletion` at `0x1400348da`
- `ntoskrnl!IoRemoveIoCompletion` at `0x1400348da`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140034970`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140034970`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400349d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400349fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400349d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400349fe`
- `ntoskrnl!ExAllocatePool2` at `0x140034814`
- `ntoskrnl!ExAllocatePool2` at `0x140034882`
- `ntoskrnl!ExAllocatePool2` at `0x140034814`
- `ntoskrnl!ExAllocatePool2` at `0x140034882`
- `ntoskrnl!IoIs32bitProcess` at `0x14003478a`
- `ntoskrnl!IoIs32bitProcess` at `0x14003478a`
- `ntoskrnl!ProbeForWrite` at `0x1400347da`
- `ntoskrnl!ProbeForWrite` at `0x1400347da`

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
0x1400346f4  mov     [rsp+arg_18], rbx
0x1400346f9  push    rsi
0x1400346fa  push    rdi
0x1400346fb  push    r12
0x1400346fd  push    r13
0x1400346ff  push    r14
0x140034701  sub     rsp, 330h
0x140034708  mov     rax, cs:__security_cookie
0x14003470f  xor     rax, rsp
0x140034712  mov     [rsp+358h+var_38], rax
0x14003471a  mov     r14, r8
0x14003471d  mov     [rsp+358h+var_2D8], rdx
0x140034725  mov     [rsp+358h+var_318], cl
0x140034729  mov     [rsp+358h+var_310], cl
0x14003472d  mov     [rsp+358h+var_2F0], r8
0x140034732  mov     [rsp+358h+var_2E0], 0
0x14003473b  xor     edx, edx; Val
0x14003473d  mov     r8d, 80h; Size
0x140034743  lea     rcx, [rsp+358h+var_2B8]; void *
0x14003474b  call    memset
0x140034750  xor     edi, edi
0x140034752  mov     [rsp+358h+var_2F8], rdi
0x140034757  xor     ebx, ebx
0x140034759  mov     [rsp+358h+var_308], ebx
0x14003475d  mov     esi, [r14+28h]
0x140034761  test    esi, esi
0x140034763  jnz     short loc_14003476C
0x140034765  xor     esi, esi
0x140034767  jmp     loc_1400349B8
0x14003476c  mov     [rsp+358h+Src], rbx
0x140034774  mov     eax, 20h ; ' '
0x140034779  mul     rsi
0x14003477c  mov     r12, rax
0x14003477f  test    rdx, rdx
0x140034782  jnz     loc_1400349B3
0x140034788  xor     ecx, ecx; Irp
0x14003478a  call    cs:__imp_IoIs32bitProcess
0x140034791  nop     dword ptr [rax+rax+00h]
0x140034796  mov     r13b, al
0x140034799  test    al, al
0x14003479b  jz      short loc_1400347C4
0x14003479d  mov     [rsp+358h+Src], rbx
0x1400347a5  mov     ecx, [r14+28h]
0x1400347a9  mov     eax, 10h
0x1400347ae  mul     rcx
0x1400347b1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400347b5  test    rdx, rdx
0x1400347b8  cmovz   rcx, rax
0x1400347bc  mov     r8d, 4
0x1400347c2  jmp     short loc_1400347CD
0x1400347c4  mov     rcx, r12
0x1400347c7  mov     r8d, 8; Alignment
0x1400347cd  cmp     [rsp+358h+var_318], bl
0x1400347d1  jz      short loc_1400347FC
0x1400347d3  mov     rdx, rcx; Length
0x1400347d6  mov     rcx, [r14+10h]; Address
0x1400347da  call    cs:__imp_ProbeForWrite
0x1400347e1  nop     dword ptr [rax+rax+00h]
0x1400347e6  jmp     short loc_1400347FC
0x1400347e8  mov     esi, eax
0x1400347ea  mov     rdi, [rsp+358h+var_2F8]
0x1400347ef  mov     rbx, rdi
0x1400347f2  mov     r14, [rsp+358h+var_2F0]
0x1400347f7  jmp     loc_1400349B8
0x1400347fc  test    r13b, r13b
0x1400347ff  jz      short loc_140034844
0x140034801  cmp     esi, 10h
0x140034804  jbe     short loc_14003483A
0x140034806  mov     r8d, 4E646641h
0x14003480c  mov     rdx, r12
0x14003480f  mov     ecx, 102h
0x140034814  call    cs:__imp_ExAllocatePool2
0x14003481b  nop     dword ptr [rax+rax+00h]
0x140034820  mov     rbx, rax
0x140034823  mov     [rsp+358h+var_300], rax
0x140034828  test    rax, rax
0x14003482b  jnz     short loc_14003484D
0x14003482d  lea     rbx, [rsp+358h+var_238]
0x140034835  lea     esi, [rax+10h]
0x140034838  jmp     short loc_140034848
0x14003483a  lea     rbx, [rsp+358h+var_238]
0x140034842  jmp     short loc_140034848
0x140034844  mov     rbx, [r14+10h]
0x140034848  mov     [rsp+358h+var_300], rbx
0x14003484d  mov     eax, [r14+24h]
0x140034851  cmp     eax, 0FFFFFFFFh
0x140034854  jz      short loc_140034869
0x140034856  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x14003485d  mov     [rsp+358h+var_2E0], rcx
0x140034862  lea     r12, [rsp+358h+var_2E0]
0x140034867  jmp     short loc_14003486C
0x140034869  xor     r12d, r12d
0x14003486c  cmp     esi, 10h
0x14003486f  jbe     short loc_14003489E
0x140034871  mov     edx, esi
0x140034873  shl     rdx, 3
0x140034877  mov     ecx, 42h ; 'B'
0x14003487c  mov     r8d, 4E646641h
0x140034882  call    cs:__imp_ExAllocatePool2
0x140034889  nop     dword ptr [rax+rax+00h]
0x14003488e  mov     rdi, rax
0x140034891  mov     [rsp+358h+var_2F8], rax
0x140034896  test    rax, rax
0x140034899  jnz     short loc_1400348AB
0x14003489b  lea     esi, [rax+10h]
0x14003489e  lea     rdi, [rsp+358h+var_2B8]
0x1400348a6  mov     [rsp+358h+var_2F8], rdi
0x1400348ab  mov     [rsp+358h+var_320], 0
0x1400348b0  mov     [rsp+358h+var_328], r12
0x1400348b5  mov     r12b, [rsp+358h+var_318]
0x1400348ba  mov     [rsp+358h+var_330], r12b
0x1400348bf  lea     rax, [rsp+358h+var_308]
0x1400348c4  mov     [rsp+358h+var_338], rax
0x1400348c9  mov     r9d, esi
0x1400348cc  mov     r8, rdi
0x1400348cf  mov     rdx, rbx
0x1400348d2  mov     rcx, [rsp+358h+var_2D8]
0x1400348da  call    cs:__imp_IoRemoveIoCompletion
0x1400348e1  nop     dword ptr [rax+rax+00h]
0x1400348e6  mov     esi, eax
0x1400348e8  test    eax, eax
0x1400348ea  jnz     loc_1400349B8
0x1400348f0  test    r13b, r13b
0x1400348f3  jz      short loc_140034961
0x1400348f5  cmp     esi, [rsp+358h+var_308]
0x1400348f9  jnb     short loc_140034961
0x1400348fb  mov     ecx, esi
0x1400348fd  mov     edx, esi
0x1400348ff  shl     rdx, 5
0x140034903  mov     eax, [rdx+rbx]
0x140034906  mov     dword ptr [rsp+358h+Src], eax
0x14003490d  mov     eax, [rdx+rbx+8]
0x140034911  mov     dword ptr [rsp+358h+Src+4], eax
0x140034918  mov     eax, [rdx+rbx+18h]
0x14003491c  mov     [rsp+358h+var_2C4], eax
0x140034923  mov     eax, [rdx+rbx+10h]
0x140034927  mov     [rsp+358h+var_2C8], eax
0x14003492e  shl     rcx, 4
0x140034932  add     rcx, [r14+10h]; void *
0x140034936  mov     r8d, 10h; Size
0x14003493c  lea     rdx, [rsp+358h+Src]; Src
0x140034944  call    RtlCopyToUser
0x140034949  nop
0x14003494a  inc     esi
0x14003494c  jmp     short loc_1400348F5
0x14003494e  mov     esi, eax
0x140034950  mov     rdi, [rsp+358h+var_2F8]
0x140034955  mov     rbx, [rsp+358h+var_300]
0x14003495a  mov     r14, [rsp+358h+var_2F0]
0x14003495f  jmp     short loc_1400349B8
0x140034961  mov     rax, [r14+18h]
0x140034965  cmp     [rsp+358h+var_308], 0
0x14003496a  jz      short loc_14003497D
0x14003496c  test    al, 3
0x14003496e  jz      short loc_14003497D
0x140034970  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140034977  nop     dword ptr [rax+rax+00h]
0x14003497c  int     3; Trap to Debugger
0x14003497d  mov     ecx, [rsp+358h+var_308]
0x140034981  test    r12b, r12b
0x140034984  jz      short loc_140034992
0x140034986  mov     edx, ecx
0x140034988  mov     rcx, rax
0x14003498b  call    RtlWriteULongToUser
0x140034990  jmp     short loc_140034994
0x140034992  mov     [rax], ecx
0x140034994  jmp     loc_140034765
0x140034999  mov     esi, eax
0x14003499b  mov     rdi, [rsp+358h+var_2F8]
0x1400349a0  mov     rbx, [rsp+358h+var_300]
0x1400349a5  mov     r14, [rsp+358h+var_2F0]
0x1400349aa  test    eax, eax
0x1400349ac  js      short loc_1400349B8
0x1400349ae  jmp     loc_140034765
0x1400349b3  mov     esi, 0C0000095h
0x1400349b8  test    rbx, rbx
0x1400349bb  jz      short loc_1400349E4
0x1400349bd  lea     rax, [rsp+358h+var_238]
0x1400349c5  cmp     rbx, rax
0x1400349c8  jz      short loc_1400349E4
0x1400349ca  cmp     rbx, [r14+10h]
0x1400349ce  jz      short loc_1400349E4
0x1400349d0  mov     edx, 4E646641h; Tag
0x1400349d5  mov     rcx, rbx; P
0x1400349d8  call    cs:__imp_ExFreePoolWithTag
0x1400349df  nop     dword ptr [rax+rax+00h]
0x1400349e4  test    rdi, rdi
0x1400349e7  jz      short loc_140034A0A
0x1400349e9  lea     rax, [rsp+358h+var_2B8]
0x1400349f1  cmp     rdi, rax
0x1400349f4  jz      short loc_140034A0A
0x1400349f6  mov     edx, 4E646641h; Tag
0x1400349fb  mov     rcx, rdi; P
0x1400349fe  call    cs:__imp_ExFreePoolWithTag
0x140034a05  nop     dword ptr [rax+rax+00h]
0x140034a0a  mov     eax, esi
0x140034a0c  mov     rcx, [rsp+358h+var_38]
0x140034a14  xor     rcx, rsp; StackCookie
0x140034a17  call    __security_check_cookie
0x140034a1c  mov     rbx, [rsp+358h+arg_18]
0x140034a24  add     rsp, 330h
0x140034a2b  pop     r14
0x140034a2d  pop     r13
0x140034a2f  pop     r12
0x140034a31  pop     rdi
0x140034a32  pop     rsi
0x140034a33  retn
0x140073b90  push    rbp
0x140073b92  sub     rsp, 40h
0x140073b96  mov     rbp, rdx
0x140073b99  xor     eax, eax
0x140073b9b  cmp     [rbp+48h], al
0x140073b9e  setnz   al
0x140073ba1  mov     [rbp+70h], eax
0x140073ba4  mov     eax, [rbp+70h]
0x140073ba7  add     rsp, 40h
0x140073bab  pop     rbp
0x140073bac  retn
```
