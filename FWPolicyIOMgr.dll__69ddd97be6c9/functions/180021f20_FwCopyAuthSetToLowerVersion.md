# FwCopyAuthSetToLowerVersion

- ea: `0x180021f20`
- end: `0x180022247`
- name: `FwCopyAuthSetToLowerVersion`
- size: `807`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180021e30`

## callees

- `0x1800042c4`
- `0x1800159a0`
- `0x18001e400`
- `0x18001e874`
- `0x18001e9ac`
- `0x180021308`
- `0x180021f20`

## import_xrefs

- `fwbase!FwFree` at `0x1800221ff`
- `fwbase!FwFree` at `0x18002221f`
- `fwbase!FwFree` at `0x180022228`
- `fwbase!FwFree` at `0x1800221ff`
- `fwbase!FwFree` at `0x18002221f`
- `fwbase!FwFree` at `0x180022228`
- `fwbase!FwAlloc` at `0x180022011`
- `fwbase!FwAlloc` at `0x1800220cc`
- `fwbase!FwAlloc` at `0x180022011`
- `fwbase!FwAlloc` at `0x1800220cc`
- `fwbase!FwStringCopy` at `0x180022165`
- `fwbase!FwStringCopy` at `0x18002219d`
- `fwbase!FwStringCopy` at `0x180022165`
- `fwbase!FwStringCopy` at `0x18002219d`

## pseudocode

```c
__int64 __fastcall FwCopyAuthSetToLowerVersion(unsigned __int16 a1, __int64 a2, __int64 *a3)
{
  __int64 v4; // rdi
  __int64 v5; // rsi
  struct _tag_FW_AUTH_SUITE *v6; // rbp
  __int64 v8; // r9
  int v9; // ebx
  LPCOLESTR v10; // rcx
  __int64 v11; // rdx
  LPCOLESTR v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 i; // r14
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // r9d
  __int64 v21; // rcx
  struct _tag_FW_AUTH_SUITE *v22; // rcx
  __int64 v24; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  v24 = 0;
  v5 = 0;
  v6 = 0;
  if ( a1 >= 0x214u )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = 2147942487LL;
    v9 = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_40;
    v11 = 110;
    goto LABEL_5;
  }
  if ( !a2 )
  {
    v8 = 2147942487LL;
    v9 = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_40;
    v11 = 111;
    goto LABEL_5;
  }
  *a3 = 0;
  v9 = FwCopyAuthSet(a2, &v24);
  if ( v9 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_19;
    v13 = 112;
    v14 = (unsigned int)v9;
LABEL_18:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, v14);
LABEL_19:
    v4 = v24;
    goto LABEL_40;
  }
  v15 = FwAlloc(88);
  v5 = v15;
  if ( !v15 )
  {
    v14 = 2147942414LL;
    v9 = -2147024882;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_19;
    v13 = 113;
    goto LABEL_18;
  }
  v4 = v24;
  *(_WORD *)(v15 + 8) = *(_WORD *)(v24 + 8);
  *(_DWORD *)(v15 + 12) = *(_DWORD *)(v4 + 12);
  *(_DWORD *)(v15 + 64) = *(_DWORD *)(v4 + 64);
  *(_DWORD *)(v15 + 80) = *(_DWORD *)(v4 + 80);
  *(_DWORD *)(v15 + 48) = 0;
  *(_QWORD *)(v15 + 56) = 0;
  *(_QWORD *)(v15 + 16) = *(_QWORD *)(v4 + 16);
  *(_QWORD *)(v15 + 24) = *(_QWORD *)(v4 + 24);
  *(_QWORD *)(v15 + 32) = *(_QWORD *)(v4 + 32);
  *(_QWORD *)(v15 + 40) = *(_QWORD *)(v4 + 40);
  *(_QWORD *)(v15 + 72) = *(_QWORD *)(v4 + 72);
  *(_DWORD *)(v15 + 64) = *(_DWORD *)(v4 + 64);
  *(_DWORD *)(v15 + 80) = *(_DWORD *)(v4 + 80);
  *(_QWORD *)v15 = 0;
  v16 = *(_DWORD *)(v4 + 48);
  if ( !v16 )
  {
LABEL_39:
    *(_DWORD *)(v5 + 48) = v16;
    *(_QWORD *)(v5 + 56) = v6;
    *a3 = v5;
    v22 = *(struct _tag_FW_AUTH_SUITE **)(v4 + 56);
    if ( v22 )
      FwFreeAuthSuites(v22, *(_DWORD *)(v4 + 48));
    FwFree(*(_QWORD *)(v4 + 56));
    v21 = v4;
    goto LABEL_44;
  }
  v6 = (struct _tag_FW_AUTH_SUITE *)FwAlloc(16LL * v16);
  if ( !v6 )
  {
    v8 = 2147942414LL;
    v9 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_40;
    v11 = 114;
LABEL_5:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, v8);
    goto LABEL_40;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v16 = *(_DWORD *)(v4 + 48);
    if ( (unsigned int)i >= v16 )
      goto LABEL_39;
    v18 = 16LL * (unsigned int)i;
    *(_WORD *)((char *)v6 + v18 + 4) = *(_WORD *)(*(_QWORD *)(v4 + 56) + 24 * i + 4);
    *(_DWORD *)((char *)v6 + v18) = *(_DWORD *)(*(_QWORD *)(v4 + 56) + 24 * i);
    v19 = *(_QWORD *)(v4 + 56);
    v20 = *(_DWORD *)(v19 + 24 * i);
    if ( ((v20 - 5) & 0xFFFFFFFD) == 0 )
      break;
    if ( v20 == 3 )
    {
      v9 = FwStringCopy(*(_QWORD *)(v19 + 24 * i + 8), (char *)v6 + v18 + 8);
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v11 = 116;
LABEL_38:
          v8 = (unsigned int)v9;
          goto LABEL_5;
        }
        goto LABEL_40;
      }
    }
LABEL_34:
    ;
  }
  v9 = FwStringCopy(*(_QWORD *)(v19 + 24 * i + 8), (char *)v6 + v18 + 8);
  if ( v9 >= 0 )
    goto LABEL_34;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v11 = 115;
    goto LABEL_38;
  }
LABEL_40:
  FwAuthSetFree(v4);
  FwFreeAuthSuitesByVersion(v6, *(_DWORD *)(v4 + 48), a1);
  FwFree(v6);
  v21 = v5;
LABEL_44:
  FwFree(v21);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180021f20  mov     [rsp+arg_0], rbx
0x180021f25  mov     [rsp+arg_8], rbp
0x180021f2a  push    rsi
0x180021f2b  push    rdi
0x180021f2c  push    r12
0x180021f2e  push    r14
0x180021f30  push    r15
0x180021f32  sub     rsp, 20h
0x180021f36  movzx   r12d, cx
0x180021f3a  xor     edi, edi
0x180021f3c  mov     ecx, 214h
0x180021f41  mov     [rsp+48h+arg_18], rdi
0x180021f46  xor     esi, esi
0x180021f48  xor     ebp, ebp
0x180021f4a  mov     r15, r8
0x180021f4d  mov     rax, rdx
0x180021f50  cmp     r12w, cx
0x180021f54  jb      short loc_180021F9D
0x180021f56  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180021f5b  mov     r9d, 80070057h
0x180021f61  mov     ebx, r9d
0x180021f64  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f6b  lea     rax, WPP_GLOBAL_Control
0x180021f72  cmp     rcx, rax
0x180021f75  jz      loc_1800221E5
0x180021f7b  test    byte ptr [rcx+1Ch], 1
0x180021f7f  jz      loc_1800221E5
0x180021f85  lea     edx, [rsi+6Eh]
0x180021f88  mov     rcx, [rcx+10h]
0x180021f8c  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180021f93  call    WPP_SF_d
0x180021f98  jmp     loc_1800221E5
0x180021f9d  test    rax, rax
0x180021fa0  jnz     short loc_180021FD3
0x180021fa2  mov     r9d, 80070057h
0x180021fa8  mov     ebx, r9d
0x180021fab  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fb2  lea     rax, WPP_GLOBAL_Control
0x180021fb9  cmp     rcx, rax
0x180021fbc  jz      loc_1800221E5
0x180021fc2  test    byte ptr [rcx+1Ch], 1
0x180021fc6  jz      loc_1800221E5
0x180021fcc  mov     edx, 6Fh ; 'o'
0x180021fd1  jmp     short loc_180021F88
0x180021fd3  lea     rdx, [rsp+48h+arg_18]
0x180021fd8  mov     [r8], rsi
0x180021fdb  mov     rcx, rax
0x180021fde  call    FwCopyAuthSet
0x180021fe3  mov     ebx, eax
0x180021fe5  test    eax, eax
0x180021fe7  jns     short loc_18002200C
0x180021fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ff0  lea     rax, WPP_GLOBAL_Control
0x180021ff7  cmp     rcx, rax
0x180021ffa  jz      short loc_180022054
0x180021ffc  test    byte ptr [rcx+1Ch], 1
0x180022000  jz      short loc_180022054
0x180022002  mov     edx, 70h ; 'p'
0x180022007  mov     r9d, ebx
0x18002200a  jmp     short loc_180022044
0x18002200c  mov     ecx, 58h ; 'X'
0x180022011  call    cs:__imp_FwAlloc
0x180022017  mov     rsi, rax
0x18002201a  test    rax, rax
0x18002201d  jnz     short loc_18002205E
0x18002201f  mov     r9d, 8007000Eh
0x180022025  mov     ebx, r9d
0x180022028  mov     rcx, cs:WPP_GLOBAL_Control
0x18002202f  lea     rax, WPP_GLOBAL_Control
0x180022036  cmp     rcx, rax
0x180022039  jz      short loc_180022054
0x18002203b  test    byte ptr [rcx+1Ch], 1
0x18002203f  jz      short loc_180022054
0x180022041  lea     edx, [rsi+71h]
0x180022044  mov     rcx, [rcx+10h]
0x180022048  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x18002204f  call    WPP_SF_d
0x180022054  mov     rdi, [rsp+48h+arg_18]
0x180022059  jmp     loc_1800221E5
0x18002205e  mov     rdi, [rsp+48h+arg_18]
0x180022063  movzx   eax, word ptr [rdi+8]
0x180022067  mov     [rsi+8], ax
0x18002206b  mov     eax, [rdi+0Ch]
0x18002206e  mov     [rsi+0Ch], eax
0x180022071  mov     eax, [rdi+40h]
0x180022074  mov     [rsi+40h], eax
0x180022077  mov     eax, [rdi+50h]
0x18002207a  mov     [rsi+50h], eax
0x18002207d  mov     [rsi+30h], ebp
0x180022080  mov     [rsi+38h], rbp
0x180022084  mov     rax, [rdi+10h]
0x180022088  mov     [rsi+10h], rax
0x18002208c  mov     rax, [rdi+18h]
0x180022090  mov     [rsi+18h], rax
0x180022094  mov     rax, [rdi+20h]
0x180022098  mov     [rsi+20h], rax
0x18002209c  mov     rax, [rdi+28h]
0x1800220a0  mov     [rsi+28h], rax
0x1800220a4  mov     rax, [rdi+48h]
0x1800220a8  mov     [rsi+48h], rax
0x1800220ac  mov     eax, [rdi+40h]
0x1800220af  mov     [rsi+40h], eax
0x1800220b2  mov     eax, [rdi+50h]
0x1800220b5  mov     [rsi+50h], eax
0x1800220b8  mov     [rsi], rbp
0x1800220bb  mov     eax, [rdi+30h]
0x1800220be  test    eax, eax
0x1800220c0  jz      loc_1800221D7
0x1800220c6  mov     ecx, eax
0x1800220c8  shl     rcx, 4
0x1800220cc  call    cs:__imp_FwAlloc
0x1800220d2  mov     rbp, rax
0x1800220d5  test    rax, rax
0x1800220d8  jnz     short loc_18002210C
0x1800220da  mov     r9d, 8007000Eh
0x1800220e0  mov     ebx, r9d
0x1800220e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220ea  lea     rax, WPP_GLOBAL_Control
0x1800220f1  cmp     rcx, rax
0x1800220f4  jz      loc_1800221E5
0x1800220fa  test    byte ptr [rcx+1Ch], 1
0x1800220fe  jz      loc_1800221E5
0x180022104  lea     edx, [rbp+72h]
0x180022107  jmp     loc_180021F88
0x18002210c  xor     r14d, r14d
0x18002210f  mov     eax, [rdi+30h]
0x180022112  cmp     r14d, eax
0x180022115  jnb     loc_1800221D7
0x18002211b  mov     rax, [rdi+38h]
0x18002211f  lea     r8, [r14+r14*2]
0x180022123  mov     edx, r14d
0x180022126  shl     rdx, 4
0x18002212a  movzx   ecx, word ptr [rax+r8*8+4]
0x180022130  mov     [rdx+rbp+4], cx
0x180022135  mov     rax, [rdi+38h]
0x180022139  mov     ecx, [rax+r8*8]
0x18002213d  mov     [rdx+rbp], ecx
0x180022140  mov     rcx, [rdi+38h]
0x180022144  mov     r9d, [rcx+r8*8]
0x180022148  lea     eax, [r9-5]
0x18002214c  test    eax, 0FFFFFFFDh
0x180022151  jz      short loc_180022191
0x180022153  cmp     r9d, 3
0x180022157  jnz     short loc_1800221A9
0x180022159  mov     rcx, [rcx+r8*8+8]
0x18002215e  add     rdx, 8
0x180022162  add     rdx, rbp
0x180022165  call    cs:__imp_FwStringCopy
0x18002216b  mov     ebx, eax
0x18002216d  test    eax, eax
0x18002216f  jns     short loc_1800221A9
0x180022171  mov     rcx, cs:WPP_GLOBAL_Control
0x180022178  lea     rax, WPP_GLOBAL_Control
0x18002217f  cmp     rcx, rax
0x180022182  jz      short loc_1800221E5
0x180022184  test    byte ptr [rcx+1Ch], 1
0x180022188  jz      short loc_1800221E5
0x18002218a  mov     edx, 74h ; 't'
0x18002218f  jmp     short loc_1800221CF
0x180022191  mov     rcx, [rcx+r8*8+8]
0x180022196  add     rdx, 8
0x18002219a  add     rdx, rbp
0x18002219d  call    cs:__imp_FwStringCopy
0x1800221a3  mov     ebx, eax
0x1800221a5  test    eax, eax
0x1800221a7  js      short loc_1800221B1
0x1800221a9  inc     r14d
0x1800221ac  jmp     loc_18002210F
0x1800221b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221b8  lea     rax, WPP_GLOBAL_Control
0x1800221bf  cmp     rcx, rax
0x1800221c2  jz      short loc_1800221E5
0x1800221c4  test    byte ptr [rcx+1Ch], 1
0x1800221c8  jz      short loc_1800221E5
0x1800221ca  mov     edx, 73h ; 's'
0x1800221cf  mov     r9d, ebx
0x1800221d2  jmp     loc_180021F88
0x1800221d7  mov     [rsi+30h], eax
0x1800221da  mov     [rsi+38h], rbp
0x1800221de  mov     [r15], rsi
0x1800221e1  test    ebx, ebx
0x1800221e3  jns     short loc_18002220A
0x1800221e5  mov     rcx, rdi
0x1800221e8  call    FwAuthSetFree
0x1800221ed  mov     edx, [rdi+30h]; unsigned int
0x1800221f0  movzx   r8d, r12w; unsigned __int16
0x1800221f4  mov     rcx, rbp; struct _tag_FW_AUTH_SUITE *
0x1800221f7  call    ?FwFreeAuthSuitesByVersion@@YAXPEAU_tag_FW_AUTH_SUITE@@KG@Z; FwFreeAuthSuitesByVersion(_tag_FW_AUTH_SUITE *,ulong,ushort)
0x1800221fc  mov     rcx, rbp
0x1800221ff  call    cs:__imp_FwFree
0x180022205  mov     rcx, rsi
0x180022208  jmp     short loc_180022228
0x18002220a  mov     rcx, [rdi+38h]; struct _tag_FW_AUTH_SUITE *
0x18002220e  test    rcx, rcx
0x180022211  jz      short loc_18002221B
0x180022213  mov     edx, [rdi+30h]; unsigned int
0x180022216  call    ?FwFreeAuthSuites@@YAXPEAU_tag_FW_AUTH_SUITE@@K@Z; FwFreeAuthSuites(_tag_FW_AUTH_SUITE *,ulong)
0x18002221b  mov     rcx, [rdi+38h]
0x18002221f  call    cs:__imp_FwFree
0x180022225  mov     rcx, rdi
0x180022228  call    cs:__imp_FwFree
0x18002222e  mov     rbp, [rsp+48h+arg_8]
0x180022233  mov     eax, ebx
0x180022235  mov     rbx, [rsp+48h+arg_0]
0x18002223a  add     rsp, 20h
0x18002223e  pop     r15
0x180022240  pop     r14
0x180022242  pop     r12
0x180022244  pop     rdi
0x180022245  pop     rsi
0x180022246  retn
```
