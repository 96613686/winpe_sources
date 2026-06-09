# FwCopyCertCriteria(_tag_FW_CERT_CRITERIA *,_tag_FW_CERT_CRITERIA * *)

- ea: `0x18001df4c`
- end: `0x18001e0c3`
- name: `?FwCopyCertCriteria@@YAJPEAU_tag_FW_CERT_CRITERIA@@PEAPEAU1@@Z`
- size: `375`
- prototype: `__int64 __fastcall(struct _tag_FW_CERT_CRITERIA *, struct _tag_FW_CERT_CRITERIA **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015cd0`

## callees

- `0x1800042c4`
- `0x18001df4c`

## import_xrefs

- `fwbase!FwAlloc` at `0x18001df69`
- `fwbase!FwAlloc` at `0x18001e012`
- `fwbase!FwAlloc` at `0x18001df69`
- `fwbase!FwAlloc` at `0x18001e012`
- `fwbase!FwStringCopy` at `0x18001dfcb`
- `fwbase!FwStringCopy` at `0x18001e06b`
- `fwbase!FwStringCopy` at `0x18001dfcb`
- `fwbase!FwStringCopy` at `0x18001e06b`
- `fwbase!FwStringCopyA` at `0x18001e033`
- `fwbase!FwStringCopyA` at `0x18001e033`
- `fwbase!FwFreeCertCriteria` at `0x18001e0ab`
- `fwbase!FwFreeCertCriteria` at `0x18001e0ab`

## pseudocode

```c
__int64 __fastcall FwCopyCertCriteria(struct _tag_FW_CERT_CRITERIA *a1, struct _tag_FW_CERT_CRITERIA **a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  int v6; // edi
  LPCOLESTR v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // eax
  __int64 i; // rbp

  *a2 = 0;
  v4 = FwAlloc(48);
  v5 = v4;
  if ( !v4 )
  {
    v6 = -2147024882;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_23;
    v8 = 93;
    goto LABEL_22;
  }
  *(_WORD *)v4 = *(_WORD *)a1;
  *(_WORD *)(v4 + 2) = *((_WORD *)a1 + 1);
  *(_DWORD *)(v4 + 4) = *((_DWORD *)a1 + 1);
  v9 = *((_DWORD *)a1 + 2);
  *(_DWORD *)(v5 + 8) = v9;
  if ( v9 )
  {
    v6 = FwStringCopy(*((_QWORD *)a1 + 2), v5 + 16);
    if ( v6 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_23;
      v8 = 94;
      goto LABEL_22;
    }
  }
  v10 = *((_DWORD *)a1 + 6);
  *(_DWORD *)(v5 + 24) = v10;
  if ( v10 )
  {
    *(_QWORD *)(v5 + 32) = FwAlloc(8LL * v10);
    for ( i = 0; (unsigned int)i < *(_DWORD *)(v5 + 24); i = (unsigned int)(i + 1) )
    {
      v6 = FwStringCopyA(*(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * i), *(_QWORD *)(v5 + 32) + 8 * i);
      if ( v6 < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v8 = 95;
          goto LABEL_22;
        }
        goto LABEL_23;
      }
    }
  }
  v6 = FwStringCopy(*((_QWORD *)a1 + 5), v5 + 40);
  if ( v6 >= 0 )
  {
    *a2 = (struct _tag_FW_CERT_CRITERIA *)v5;
    return (unsigned int)v6;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v8 = 96;
LABEL_22:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v6);
  }
LABEL_23:
  FwFreeCertCriteria(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001df4c  push    rbx
0x18001df4e  push    rbp
0x18001df4f  push    rsi
0x18001df50  push    rdi
0x18001df51  push    r14
0x18001df53  sub     rsp, 20h
0x18001df57  mov     rsi, rcx
0x18001df5a  mov     qword ptr [rdx], 0
0x18001df61  mov     ecx, 30h ; '0'
0x18001df66  mov     r14, rdx
0x18001df69  call    cs:__imp_FwAlloc
0x18001df6f  mov     rbx, rax
0x18001df72  test    rax, rax
0x18001df75  jnz     short loc_18001DFA5
0x18001df77  mov     edi, 8007000Eh
0x18001df7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df83  lea     rax, WPP_GLOBAL_Control
0x18001df8a  cmp     rcx, rax
0x18001df8d  jz      loc_18001E0A8
0x18001df93  test    byte ptr [rcx+1Ch], 1
0x18001df97  jz      loc_18001E0A8
0x18001df9d  lea     edx, [rbx+5Dh]
0x18001dfa0  jmp     loc_18001E095
0x18001dfa5  movzx   eax, word ptr [rsi]
0x18001dfa8  mov     [rbx], ax
0x18001dfab  movzx   eax, word ptr [rsi+2]
0x18001dfaf  mov     [rbx+2], ax
0x18001dfb3  mov     eax, [rsi+4]
0x18001dfb6  mov     [rbx+4], eax
0x18001dfb9  mov     eax, [rsi+8]
0x18001dfbc  mov     [rbx+8], eax
0x18001dfbf  test    eax, eax
0x18001dfc1  jz      short loc_18001E002
0x18001dfc3  mov     rcx, [rsi+10h]
0x18001dfc7  lea     rdx, [rbx+10h]
0x18001dfcb  call    cs:__imp_FwStringCopy
0x18001dfd1  mov     edi, eax
0x18001dfd3  test    eax, eax
0x18001dfd5  jns     short loc_18001E002
0x18001dfd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfde  lea     rax, WPP_GLOBAL_Control
0x18001dfe5  cmp     rcx, rax
0x18001dfe8  jz      loc_18001E0A8
0x18001dfee  test    byte ptr [rcx+1Ch], 1
0x18001dff2  jz      loc_18001E0A8
0x18001dff8  mov     edx, 5Eh ; '^'
0x18001dffd  jmp     loc_18001E095
0x18001e002  mov     eax, [rsi+18h]
0x18001e005  mov     [rbx+18h], eax
0x18001e008  test    eax, eax
0x18001e00a  jz      short loc_18001E063
0x18001e00c  mov     ecx, eax
0x18001e00e  shl     rcx, 3
0x18001e012  call    cs:__imp_FwAlloc
0x18001e018  mov     [rbx+20h], rax
0x18001e01c  xor     ebp, ebp
0x18001e01e  cmp     ebp, [rbx+18h]
0x18001e021  jnb     short loc_18001E063
0x18001e023  mov     rax, [rbx+20h]
0x18001e027  mov     rcx, [rsi+20h]
0x18001e02b  lea     rdx, [rax+rbp*8]
0x18001e02f  mov     rcx, [rcx+rbp*8]
0x18001e033  call    cs:__imp_FwStringCopyA
0x18001e039  mov     edi, eax
0x18001e03b  test    eax, eax
0x18001e03d  js      short loc_18001E043
0x18001e03f  inc     ebp
0x18001e041  jmp     short loc_18001E01E
0x18001e043  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e04a  lea     rax, WPP_GLOBAL_Control
0x18001e051  cmp     rcx, rax
0x18001e054  jz      short loc_18001E0A8
0x18001e056  test    byte ptr [rcx+1Ch], 1
0x18001e05a  jz      short loc_18001E0A8
0x18001e05c  mov     edx, 5Fh ; '_'
0x18001e061  jmp     short loc_18001E095
0x18001e063  mov     rcx, [rsi+28h]
0x18001e067  lea     rdx, [rbx+28h]
0x18001e06b  call    cs:__imp_FwStringCopy
0x18001e071  mov     edi, eax
0x18001e073  test    eax, eax
0x18001e075  jns     short loc_18001E0B3
0x18001e077  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e07e  lea     rax, WPP_GLOBAL_Control
0x18001e085  cmp     rcx, rax
0x18001e088  jz      short loc_18001E0A8
0x18001e08a  test    byte ptr [rcx+1Ch], 1
0x18001e08e  jz      short loc_18001E0A8
0x18001e090  mov     edx, 60h ; '`'
0x18001e095  mov     rcx, [rcx+10h]
0x18001e099  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x18001e0a0  mov     r9d, edi
0x18001e0a3  call    WPP_SF_d
0x18001e0a8  mov     rcx, rbx
0x18001e0ab  call    cs:__imp_FwFreeCertCriteria
0x18001e0b1  jmp     short loc_18001E0B6
0x18001e0b3  mov     [r14], rbx
0x18001e0b6  mov     eax, edi
0x18001e0b8  add     rsp, 20h
0x18001e0bc  pop     r14
0x18001e0be  pop     rdi
0x18001e0bf  pop     rsi
0x18001e0c0  pop     rbp
0x18001e0c1  pop     rbx
0x18001e0c2  retn
```
