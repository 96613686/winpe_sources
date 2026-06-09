# FwCopyAuthsetToHigherVersion

- ea: `0x180022250`
- end: `0x1800224ed`
- name: `FwCopyAuthsetToHigherVersion`
- size: `669`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800042c4`
- `0x1800159a0`
- `0x18001e400`
- `0x180021308`
- `0x180022250`

## import_xrefs

- `fwbase!FwFree` at `0x1800224cf`
- `fwbase!FwFree` at `0x1800224d8`
- `fwbase!FwFree` at `0x1800224cf`
- `fwbase!FwFree` at `0x1800224d8`
- `fwbase!FwAlloc` at `0x18002228c`
- `fwbase!FwAlloc` at `0x180022390`
- `fwbase!FwAlloc` at `0x18002228c`
- `fwbase!FwAlloc` at `0x180022390`
- `fwbase!FwStringCopy` at `0x18002242b`
- `fwbase!FwStringCopy` at `0x180022466`
- `fwbase!FwStringCopy` at `0x18002242b`
- `fwbase!FwStringCopy` at `0x180022466`

## pseudocode

```c
__int64 __fastcall FwCopyAuthsetToHigherVersion(unsigned __int16 a1, __int64 a2, _QWORD *a3)
{
  int v3; // ebx
  __int64 v4; // r14
  struct _tag_FW_AUTH_SUITE *v7; // rsi
  __int64 v8; // rax
  __int64 v9; // r9
  LPCOLESTR v10; // rcx
  __int64 v11; // rdx
  __int64 i; // rbp
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // r9d
  __int64 v16; // rcx
  __int64 v18; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v4 = 0;
  v18 = 0;
  if ( a1 >= 0x214u || !a2 )
    goto LABEL_35;
  *a3 = 0;
  v7 = 0;
  v8 = FwAlloc(88);
  v4 = v8;
  if ( v8 )
  {
    *(_WORD *)(v8 + 8) = *(_WORD *)(a2 + 8);
    *(_DWORD *)(v8 + 12) = *(_DWORD *)(a2 + 12);
    *(_DWORD *)(v8 + 64) = *(_DWORD *)(a2 + 64);
    *(_DWORD *)(v8 + 80) = *(_DWORD *)(a2 + 80);
    *(_DWORD *)(v8 + 48) = 0;
    *(_QWORD *)(v8 + 56) = 0;
    *(_QWORD *)(v8 + 16) = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(v8 + 24) = *(_QWORD *)(a2 + 24);
    *(_QWORD *)(v8 + 32) = *(_QWORD *)(a2 + 32);
    *(_QWORD *)(v8 + 40) = *(_QWORD *)(a2 + 40);
    *(_QWORD *)(v8 + 72) = *(_QWORD *)(a2 + 72);
    *(_DWORD *)(v8 + 64) = *(_DWORD *)(a2 + 64);
    *(_DWORD *)(v8 + 80) = *(_DWORD *)(a2 + 80);
    *(_QWORD *)v8 = 0;
    v3 = FwCopyAuthSet(v8, &v18);
    if ( v3 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_32;
      v11 = 118;
LABEL_12:
      v9 = (unsigned int)v3;
      goto LABEL_7;
    }
    if ( *(_DWORD *)(a2 + 48) )
    {
      v7 = (struct _tag_FW_AUTH_SUITE *)FwAlloc(24LL * *(unsigned int *)(a2 + 48));
      if ( !v7 )
      {
        v9 = 2147942414LL;
        v3 = -2147024882;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_32;
        v11 = 119;
        goto LABEL_7;
      }
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a2 + 48); i = (unsigned int)(i + 1) )
      {
        v13 = 3 * i;
        *((_WORD *)v7 + 4 * v13 + 2) = *(_WORD *)(*(_QWORD *)(a2 + 56) + 16LL * (unsigned int)i + 4);
        *((_DWORD *)v7 + 2 * v13) = *(_DWORD *)(*(_QWORD *)(a2 + 56) + 16LL * (unsigned int)i);
        v14 = *(_QWORD *)(a2 + 56);
        v15 = *(_DWORD *)(v14 + 16LL * (unsigned int)i);
        if ( ((v15 - 5) & 0xFFFFFFFD) != 0 )
        {
          if ( v15 == 3 )
          {
            v3 = FwStringCopy(*(_QWORD *)(v14 + 16LL * (unsigned int)i + 8), (char *)v7 + 8 * v13 + 8);
            if ( v3 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v11 = 121;
                goto LABEL_12;
              }
              goto LABEL_32;
            }
          }
        }
        else
        {
          v3 = FwStringCopy(*(_QWORD *)(v14 + 16LL * (unsigned int)i + 8), (char *)v7 + 8 * v13 + 8);
          if ( v3 < 0 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v11 = 120;
              goto LABEL_12;
            }
            goto LABEL_32;
          }
        }
      }
    }
    v16 = v18;
    *(_QWORD *)(v18 + 56) = v7;
    *(_DWORD *)(v16 + 48) = *(_DWORD *)(a2 + 48);
    *a3 = v16;
    goto LABEL_35;
  }
  v9 = 2147942414LL;
  v3 = -2147024882;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
    goto LABEL_32;
  v11 = 117;
LABEL_7:
  WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, v9);
LABEL_32:
  FwAuthSetFree(v18);
  if ( v7 )
    FwFreeAuthSuites(v7, *(_DWORD *)(a2 + 48));
  FwFree(v7);
LABEL_35:
  FwFree(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180022250  push    rbx
0x180022252  push    rbp
0x180022253  push    rsi
0x180022254  push    rdi
0x180022255  push    r14
0x180022257  push    r15
0x180022259  sub     rsp, 28h
0x18002225d  xor     ebx, ebx
0x18002225f  xor     r14d, r14d
0x180022262  mov     eax, 214h
0x180022267  mov     [rsp+58h+arg_18], rbx
0x18002226c  mov     r15, r8
0x18002226f  mov     rdi, rdx
0x180022272  cmp     cx, ax
0x180022275  jnb     loc_1800224D5
0x18002227b  test    rdx, rdx
0x18002227e  jz      loc_1800224D5
0x180022284  lea     ecx, [rbx+58h]
0x180022287  mov     [r8], rbx
0x18002228a  xor     esi, esi
0x18002228c  call    cs:__imp_FwAlloc
0x180022292  mov     r14, rax
0x180022295  test    rax, rax
0x180022298  jnz     short loc_1800222DC
0x18002229a  mov     r9d, 8007000Eh
0x1800222a0  mov     ebx, r9d
0x1800222a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222aa  lea     rax, WPP_GLOBAL_Control
0x1800222b1  cmp     rcx, rax
0x1800222b4  jz      loc_1800224B2
0x1800222ba  test    byte ptr [rcx+1Ch], 1
0x1800222be  jz      loc_1800224B2
0x1800222c4  lea     edx, [rsi+75h]
0x1800222c7  mov     rcx, [rcx+10h]
0x1800222cb  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x1800222d2  call    WPP_SF_d
0x1800222d7  jmp     loc_1800224B2
0x1800222dc  movzx   eax, word ptr [rdi+8]
0x1800222e0  lea     rdx, [rsp+58h+arg_18]
0x1800222e5  mov     [r14+8], ax
0x1800222ea  mov     rcx, r14
0x1800222ed  mov     eax, [rdi+0Ch]
0x1800222f0  mov     [r14+0Ch], eax
0x1800222f4  mov     eax, [rdi+40h]
0x1800222f7  mov     [r14+40h], eax
0x1800222fb  mov     eax, [rdi+50h]
0x1800222fe  mov     [r14+50h], eax
0x180022302  mov     [r14+30h], ebx
0x180022306  mov     [r14+38h], rbx
0x18002230a  mov     rax, [rdi+10h]
0x18002230e  mov     [r14+10h], rax
0x180022312  mov     rax, [rdi+18h]
0x180022316  mov     [r14+18h], rax
0x18002231a  mov     rax, [rdi+20h]
0x18002231e  mov     [r14+20h], rax
0x180022322  mov     rax, [rdi+28h]
0x180022326  mov     [r14+28h], rax
0x18002232a  mov     rax, [rdi+48h]
0x18002232e  mov     [r14+48h], rax
0x180022332  mov     eax, [rdi+40h]
0x180022335  mov     [r14+40h], eax
0x180022339  mov     eax, [rdi+50h]
0x18002233c  mov     [r14+50h], eax
0x180022340  mov     [r14], rbx
0x180022343  call    FwCopyAuthSet
0x180022348  mov     ebx, eax
0x18002234a  test    eax, eax
0x18002234c  jns     short loc_18002237C
0x18002234e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022355  lea     rax, WPP_GLOBAL_Control
0x18002235c  cmp     rcx, rax
0x18002235f  jz      loc_1800224B2
0x180022365  test    byte ptr [rcx+1Ch], 1
0x180022369  jz      loc_1800224B2
0x18002236f  mov     edx, 76h ; 'v'
0x180022374  mov     r9d, ebx
0x180022377  jmp     loc_1800222C7
0x18002237c  cmp     [rdi+30h], esi
0x18002237f  jbe     loc_18002249C
0x180022385  mov     eax, [rdi+30h]
0x180022388  lea     rcx, [rax+rax*2]
0x18002238c  shl     rcx, 3
0x180022390  call    cs:__imp_FwAlloc
0x180022396  mov     rsi, rax
0x180022399  test    rax, rax
0x18002239c  jnz     short loc_1800223D0
0x18002239e  mov     r9d, 8007000Eh
0x1800223a4  mov     ebx, r9d
0x1800223a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223ae  lea     rax, WPP_GLOBAL_Control
0x1800223b5  cmp     rcx, rax
0x1800223b8  jz      loc_1800224B2
0x1800223be  test    byte ptr [rcx+1Ch], 1
0x1800223c2  jz      loc_1800224B2
0x1800223c8  lea     edx, [rsi+77h]
0x1800223cb  jmp     loc_1800222C7
0x1800223d0  xor     ebp, ebp
0x1800223d2  cmp     ebp, [rdi+30h]
0x1800223d5  jnb     loc_18002249C
0x1800223db  mov     rax, [rdi+38h]
0x1800223df  lea     rdx, ds:0[rbp*2]
0x1800223e7  add     rdx, rbp
0x1800223ea  mov     r8d, ebp
0x1800223ed  add     r8, r8
0x1800223f0  movzx   ecx, word ptr [rax+r8*8+4]
0x1800223f6  mov     [rsi+rdx*8+4], cx
0x1800223fb  mov     rax, [rdi+38h]
0x1800223ff  mov     ecx, [rax+r8*8]
0x180022403  mov     [rsi+rdx*8], ecx
0x180022406  mov     rcx, [rdi+38h]
0x18002240a  mov     r9d, [rcx+r8*8]
0x18002240e  lea     eax, [r9-5]
0x180022412  test    eax, 0FFFFFFFDh
0x180022417  jz      short loc_18002245A
0x180022419  cmp     r9d, 3
0x18002241d  jnz     short loc_180022472
0x18002241f  mov     rcx, [rcx+r8*8+8]
0x180022424  inc     rdx
0x180022427  lea     rdx, [rsi+rdx*8]
0x18002242b  call    cs:__imp_FwStringCopy
0x180022431  mov     ebx, eax
0x180022433  test    eax, eax
0x180022435  jns     short loc_180022472
0x180022437  mov     rcx, cs:WPP_GLOBAL_Control
0x18002243e  lea     rax, WPP_GLOBAL_Control
0x180022445  cmp     rcx, rax
0x180022448  jz      short loc_1800224B2
0x18002244a  test    byte ptr [rcx+1Ch], 1
0x18002244e  jz      short loc_1800224B2
0x180022450  mov     edx, 79h ; 'y'
0x180022455  jmp     loc_180022374
0x18002245a  mov     rcx, [rcx+r8*8+8]
0x18002245f  inc     rdx
0x180022462  lea     rdx, [rsi+rdx*8]
0x180022466  call    cs:__imp_FwStringCopy
0x18002246c  mov     ebx, eax
0x18002246e  test    eax, eax
0x180022470  js      short loc_180022479
0x180022472  inc     ebp
0x180022474  jmp     loc_1800223D2
0x180022479  mov     rcx, cs:WPP_GLOBAL_Control
0x180022480  lea     rax, WPP_GLOBAL_Control
0x180022487  cmp     rcx, rax
0x18002248a  jz      short loc_1800224B2
0x18002248c  test    byte ptr [rcx+1Ch], 1
0x180022490  jz      short loc_1800224B2
0x180022492  mov     edx, 78h ; 'x'
0x180022497  jmp     loc_180022374
0x18002249c  mov     rcx, [rsp+58h+arg_18]
0x1800224a1  mov     [rcx+38h], rsi
0x1800224a5  mov     eax, [rdi+30h]
0x1800224a8  mov     [rcx+30h], eax
0x1800224ab  mov     [r15], rcx
0x1800224ae  test    ebx, ebx
0x1800224b0  jns     short loc_1800224D5
0x1800224b2  mov     rcx, [rsp+58h+arg_18]
0x1800224b7  call    FwAuthSetFree
0x1800224bc  test    rsi, rsi
0x1800224bf  jz      short loc_1800224CC
0x1800224c1  mov     edx, [rdi+30h]; unsigned int
0x1800224c4  mov     rcx, rsi; struct _tag_FW_AUTH_SUITE *
0x1800224c7  call    ?FwFreeAuthSuites@@YAXPEAU_tag_FW_AUTH_SUITE@@K@Z; FwFreeAuthSuites(_tag_FW_AUTH_SUITE *,ulong)
0x1800224cc  mov     rcx, rsi
0x1800224cf  call    cs:__imp_FwFree
0x1800224d5  mov     rcx, r14
0x1800224d8  call    cs:__imp_FwFree
0x1800224de  mov     eax, ebx
0x1800224e0  add     rsp, 28h
0x1800224e4  pop     r15
0x1800224e6  pop     r14
0x1800224e8  pop     rdi
0x1800224e9  pop     rsi
0x1800224ea  pop     rbp
0x1800224eb  pop     rbx
0x1800224ec  retn
```
