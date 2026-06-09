# IssueCommandSS

- ea: `0x14000be7c`
- end: `0x14000c2cc`
- name: `IssueCommandSS`
- size: `1104`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000c368`

## callees

- `0x140001020`
- `0x140007cc0`
- `0x140007ee4`
- `0x14000bd7c`
- `0x14000be7c`

## import_xrefs

- `ntoskrnl!IoCancelIrp` at `0x14000c1a2`
- `ntoskrnl!IoCancelIrp` at `0x14000c299`
- `ntoskrnl!IoCancelIrp` at `0x14000c2ac`
- `ntoskrnl!IoCancelIrp` at `0x14000c1a2`
- `ntoskrnl!IoCancelIrp` at `0x14000c299`
- `ntoskrnl!IoCancelIrp` at `0x14000c2ac`
- `storport!StorPortExtendedFunction` at `0x14000bfdf`
- `storport!StorPortExtendedFunction` at `0x14000bfdf`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000c01b`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000c01b`

## pseudocode

```c
__int64 IssueCommandSS(_QWORD *a1, __int64 a2, _OWORD *a3, __int64 a4, ...)
{
  char v4; // r14
  int NextFree; // ebx
  int v9; // r9d
  __int64 v10; // rdx
  __int64 v11; // r13
  __int64 v12; // rdi
  __int16 v13; // r12
  char v14; // al
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  char v18; // r13
  __int64 v19; // rbx
  int Default; // eax
  int v21; // edx
  int v22; // r8d
  int v23; // eax
  char v24; // al
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // eax
  char v28; // al
  IRP *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rdx
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rax
  __int64 v34; // rax
  int v35; // eax
  char v36; // al
  int v38; // [rsp+50h] [rbp-68h]
  __int64 v39; // [rsp+58h] [rbp-60h] BYREF
  __int64 v40; // [rsp+60h] [rbp-58h]
  __int64 v41; // [rsp+68h] [rbp-50h]
  __int64 v42; // [rsp+D8h] [rbp+20h]
  __int64 v43; // [rsp+E0h] [rbp+28h] BYREF
  va_list va; // [rsp+E0h] [rbp+28h]
  __int64 v45; // [rsp+E8h] [rbp+30h]
  va_list va1; // [rsp+F0h] [rbp+38h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v43 = va_arg(va1, _QWORD);
  v45 = va_arg(va1, _QWORD);
  v42 = a4;
  v4 = v45;
  LOWORD(v43) = 0;
  v39 = 0;
  LOBYTE(a4) = v45;
  NextFree = QueueFindNextFree(a1, (__int64 *)va, a2, a4);
  if ( NextFree >= 0 )
  {
    v9 = (unsigned __int16)v43;
    v10 = v42;
    v11 = (unsigned __int16)v43;
    v12 = a1[147] + 224LL * (unsigned __int16)v43;
    v13 = __ROR2__(v43 + 1, 8);
    v40 = (unsigned __int16)v43;
    *(_QWORD *)(v12 + 32) = a2;
    *(_QWORD *)(v12 + 160) = v42;
    *(_BYTE *)(v12 + 201) = v4;
    v41 = a1[148];
    *(_DWORD *)(v12 + 8) = 1;
    *(_DWORD *)(v12 + 12) = 1;
    *(_DWORD *)(v12 + 16) = 1;
    if ( a3 )
    {
      v14 = 1;
      *(_OWORD *)(v12 + 168) = *a3;
    }
    else
    {
      v14 = 0;
    }
    *(_BYTE *)(v12 + 184) = v14;
    *(_QWORD *)(v12 + 192) = 0;
    *(_BYTE *)(v12 + 200) = 0;
    if ( (*(_DWORD *)(a2 + 12) & 0xC0) != 0 )
    {
      *(_DWORD *)(v12 + 24) = 3;
      v15 = *(_DWORD *)(a2 + 12) & 0xC0;
      if ( v15 == 64 )
      {
        v38 = 3;
      }
      else
      {
        if ( v15 != 128 )
        {
          NextFree = -1073741811;
LABEL_40:
          QueueReleaseEntry(v12);
          return (unsigned int)NextFree;
        }
        v38 = 0;
      }
      *(_DWORD *)(v12 + 12) = 2;
      if ( a1[1] )
      {
        if ( !v42 )
        {
          v17 = StorPortExtendedFunction(5, a1, a2, &v39);
          v18 = v17;
          if ( v17 )
          {
            if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v19 = *(_QWORD *)(a2 + 24);
              Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
              WPP_RECORDER_SF_iiD(
                Default,
                v21,
                v22,
                12,
                (__int64)WPP_b606bc35c7ef35d872dd65732ef04e06_Traceguids,
                a2,
                v19,
                v18);
            }
            *(_BYTE *)(a2 + 3) = 4;
            NextFree = -1073741670;
            goto LABEL_40;
          }
          v11 = v40;
          v10 = v42;
          v9 = (unsigned __int16)v43;
        }
        v16 = v39;
      }
      else
      {
        v16 = *(_QWORD *)(a2 + 24);
        v39 = v16;
      }
      v23 = IssueBulkRequest(
              (_DWORD)a1,
              v12,
              2,
              v9,
              v16,
              v10,
              *(_DWORD *)(a2 + 16),
              v38 | (v4 != 0 ? 0x10 : 0),
              (__int64)DataCompletion);
      NextFree = v23;
      if ( v23 < 0 )
      {
        if ( v23 == -1073741810 )
        {
          v24 = 14;
        }
        else
        {
          v24 = 4;
          if ( NextFree == -1073741764 )
            v24 = 18;
        }
        *(_BYTE *)(a2 + 3) = v24;
        goto LABEL_40;
      }
      v9 = (unsigned __int16)v43;
    }
    else
    {
      *(_DWORD *)(v12 + 24) = 2;
    }
    v25 = a1[150] + (v11 << 10);
    *(_BYTE *)v25 = 3;
    *(_WORD *)(v25 + 6) = 0;
    *(_WORD *)(v25 + 14) = 0;
    *(_WORD *)(v25 + 2) = v13;
    *(_DWORD *)(v12 + 16) = 2;
    if ( v4 )
      v26 = a1[181];
    else
      v26 = 0;
    v27 = IssueBulkRequest((_DWORD)a1, v12, 3, v9, v25, v26, 1024, v4 != 0 ? 17 : 1, (__int64)SenseIUCompletion);
    NextFree = v27;
    if ( v27 >= 0 )
    {
      v30 = 32 * v11 + v41;
      *(_BYTE *)v30 = 1;
      *(_OWORD *)(v30 + 16) = *(_OWORD *)(a2 + 72);
      v31 = a1[141];
      v32 = *(unsigned __int8 *)(a2 + 7);
      if ( v31 )
        v33 = *(_QWORD *)(32 * v32 + v31);
      else
        v33 = _byteswap_uint64(v32);
      *(_BYTE *)(v30 + 6) &= 3u;
      *(_BYTE *)(v30 + 4) &= 0x80u;
      *(_QWORD *)(v30 + 8) = v33;
      *(_WORD *)(v30 + 2) = v13;
      *(_DWORD *)(v12 + 8) = 2;
      if ( v4 )
        v34 = a1[180];
      else
        v34 = 0;
      v35 = IssueBulkRequest(
              (_DWORD)a1,
              v12,
              1,
              (unsigned __int16)v43,
              v30,
              v34,
              32,
              v4 != 0 ? 0x10 : 0,
              (__int64)CommandIUCompletion);
      NextFree = v35;
      if ( v35 < 0 )
      {
        if ( v35 == -1073741810 )
        {
          v36 = 14;
        }
        else
        {
          v36 = 4;
          if ( NextFree == -1073741764 )
            v36 = 18;
        }
        *(_BYTE *)(a2 + 3) = v36;
        NextFree = 0;
        *(_DWORD *)(v12 + 8) = 3;
        if ( (*(_DWORD *)(a2 + 12) & 0xC0) != 0 )
          IoCancelIrp(*(PIRP *)(v12 + 120));
        IoCancelIrp(*(PIRP *)(v12 + 128));
      }
    }
    else
    {
      if ( v27 == -1073741810 )
      {
        v28 = 14;
      }
      else
      {
        v28 = 4;
        if ( NextFree == -1073741764 )
          v28 = 18;
      }
      *(_BYTE *)(a2 + 3) = v28;
      if ( (*(_DWORD *)(a2 + 12) & 0xC0) != 0 )
      {
        v29 = *(IRP **)(v12 + 120);
        *(_DWORD *)(v12 + 8) = 3;
        *(_DWORD *)(v12 + 16) = 3;
        IoCancelIrp(v29);
        NextFree = 0;
      }
      if ( NextFree < 0 )
        goto LABEL_40;
    }
  }
  return (unsigned int)NextFree;
}

```

## disassembly

```asm
0x14000be7c  mov     r11, rsp
0x14000be7f  mov     [r11+20h], r9
0x14000be83  push    rbx
0x14000be84  push    rbp
0x14000be85  push    rsi
0x14000be86  push    rdi
0x14000be87  push    r12
0x14000be89  push    r13
0x14000be8b  push    r14
0x14000be8d  push    r15
0x14000be8f  sub     rsp, 78h
0x14000be93  mov     r14b, byte ptr [rsp+0B8h+arg_28]
0x14000be9b  xor     eax, eax
0x14000be9d  mov     r15, r8
0x14000bea0  mov     [r11+28h], ax
0x14000bea5  mov     r8, rdx
0x14000bea8  mov     [r11-60h], rax
0x14000beac  mov     rsi, rdx
0x14000beaf  mov     r9b, r14b
0x14000beb2  lea     rdx, [r11+28h]
0x14000beb6  mov     rbp, rcx
0x14000beb9  call    QueueFindNextFree
0x14000bebe  mov     ebx, eax
0x14000bec0  test    eax, eax
0x14000bec2  js      loc_14000C2B8
0x14000bec8  movzx   r9d, word ptr [rsp+0B8h+arg_20]
0x14000bed1  mov     r10d, 1
0x14000bed7  mov     rdx, [rsp+0B8h+arg_18]
0x14000bedf  mov     r13d, r9d
0x14000bee2  imul    rdi, r9, 0E0h
0x14000bee9  lea     r12d, [r10+r9]
0x14000beed  mov     word ptr [rsp+0B8h+arg_20], r9w
0x14000bef6  add     rdi, [rbp+498h]
0x14000befd  ror     r12w, 8
0x14000bf02  mov     [rsp+0B8h+var_58], r9
0x14000bf07  mov     [rdi+20h], rsi
0x14000bf0b  mov     [rdi+0A0h], rdx
0x14000bf12  mov     [rdi+0C9h], r14b
0x14000bf19  mov     rax, [rbp+4A0h]
0x14000bf20  mov     [rsp+0B8h+var_50], rax
0x14000bf25  mov     [rdi+8], r10d
0x14000bf29  mov     [rdi+0Ch], r10d
0x14000bf2d  mov     [rdi+10h], r10d
0x14000bf31  test    r15, r15
0x14000bf34  jz      short loc_14000BF47
0x14000bf36  movups  xmm0, xmmword ptr [r15]
0x14000bf3a  mov     al, r10b
0x14000bf3d  movdqu  xmmword ptr [rdi+0A8h], xmm0
0x14000bf45  jmp     short loc_14000BF49
0x14000bf47  xor     al, al
0x14000bf49  mov     [rdi+0B8h], al
0x14000bf4f  mov     qword ptr [rdi+0C0h], 0
0x14000bf5a  mov     byte ptr [rdi+0C8h], 0
0x14000bf61  mov     eax, [rsi+0Ch]
0x14000bf64  test    al, 0C0h
0x14000bf66  jz      loc_14000C0D9
0x14000bf6c  mov     dword ptr [rdi+18h], 3
0x14000bf73  mov     eax, [rsi+0Ch]
0x14000bf76  and     eax, 0C0h
0x14000bf7b  cmp     eax, 40h ; '@'
0x14000bf7e  jnz     short loc_14000BF8A
0x14000bf80  mov     [rsp+0B8h+var_68], 3
0x14000bf88  jmp     short loc_14000BF9D
0x14000bf8a  cmp     eax, 80h
0x14000bf8f  jnz     loc_14000C0CF
0x14000bf95  mov     [rsp+0B8h+var_68], 0
0x14000bf9d  mov     al, r14b
0x14000bfa0  mov     r15d, 2
0x14000bfa6  neg     al
0x14000bfa8  mov     [rdi+0Ch], r15d
0x14000bfac  sbb     ebx, ebx
0x14000bfae  and     ebx, 10h
0x14000bfb1  cmp     qword ptr [rbp+8], 0
0x14000bfb6  jnz     short loc_14000BFC6
0x14000bfb8  mov     rcx, [rsi+18h]
0x14000bfbc  mov     [rsp+0B8h+var_60], rcx
0x14000bfc1  jmp     loc_14000C077
0x14000bfc6  test    rdx, rdx
0x14000bfc9  jnz     loc_14000C072
0x14000bfcf  lea     r9, [rsp+0B8h+var_60]
0x14000bfd4  mov     r8, rsi
0x14000bfd7  mov     rdx, rbp
0x14000bfda  mov     ecx, 5
0x14000bfdf  call    cs:__imp_StorPortExtendedFunction
0x14000bfe6  nop     dword ptr [rax+rax+00h]
0x14000bfeb  mov     r13d, eax
0x14000bfee  test    eax, eax
0x14000bff0  jz      short loc_14000C05C
0x14000bff2  cmp     cs:gTracingEnabled, 0
0x14000bff9  jz      short loc_14000C04E
0x14000bffb  lea     rax, WPP_RECORDER_INITIALIZED
0x14000c002  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000c009  jz      short loc_14000C04E
0x14000c00b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c012  mov     ebp, 0Ch
0x14000c017  mov     rbx, [rsi+18h]
0x14000c01b  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000c022  nop     dword ptr [rax+rax+00h]
0x14000c027  mov     [rsp+0B8h+var_80], r13d
0x14000c02c  movzx   r9d, bp
0x14000c030  mov     rcx, rax
0x14000c033  mov     [rsp+0B8h+var_88], rbx
0x14000c038  lea     rax, WPP_b606bc35c7ef35d872dd65732ef04e06_Traceguids
0x14000c03f  mov     [rsp+0B8h+var_90], rsi
0x14000c044  mov     [rsp+0B8h+var_98], rax
0x14000c049  call    WPP_RECORDER_SF_iiD
0x14000c04e  mov     byte ptr [rsi+3], 4
0x14000c052  mov     ebx, 0C000009Ah
0x14000c057  jmp     loc_14000C1B8
0x14000c05c  mov     r13, [rsp+0B8h+var_58]
0x14000c061  mov     rdx, [rsp+0B8h+arg_18]
0x14000c069  movzx   r9d, word ptr [rsp+0B8h+arg_20]
0x14000c072  mov     rcx, [rsp+0B8h+var_60]
0x14000c077  or      ebx, [rsp+0B8h+var_68]
0x14000c07b  lea     rax, DataCompletion
0x14000c082  mov     [rsp+0B8h+var_78], rax
0x14000c087  mov     r8d, r15d
0x14000c08a  mov     eax, [rsi+10h]
0x14000c08d  mov     [rsp+0B8h+var_80], ebx
0x14000c091  mov     dword ptr [rsp+0B8h+var_88], eax
0x14000c095  mov     [rsp+0B8h+var_90], rdx
0x14000c09a  mov     rdx, rdi
0x14000c09d  mov     [rsp+0B8h+var_98], rcx
0x14000c0a2  mov     rcx, rbp
0x14000c0a5  call    IssueBulkRequest
0x14000c0aa  mov     ebx, eax
0x14000c0ac  test    eax, eax
0x14000c0ae  jns     short loc_14000C0E5
0x14000c0b0  cmp     eax, 0C000000Eh
0x14000c0b5  jz      short loc_14000C0C5
0x14000c0b7  mov     al, 4
0x14000c0b9  cmp     ebx, 0C000003Ch
0x14000c0bf  jnz     short loc_14000C0C7
0x14000c0c1  mov     al, 12h
0x14000c0c3  jmp     short loc_14000C0C7
0x14000c0c5  mov     al, 0Eh
0x14000c0c7  mov     [rsi+3], al
0x14000c0ca  jmp     loc_14000C1B8
0x14000c0cf  mov     ebx, 0C000000Dh
0x14000c0d4  jmp     loc_14000C1B8
0x14000c0d9  mov     r15d, 2
0x14000c0df  mov     [rdi+18h], r15d
0x14000c0e3  jmp     short loc_14000C0F4
0x14000c0e5  movzx   r9d, word ptr [rsp+0B8h+arg_20]
0x14000c0ee  mov     r10d, 1
0x14000c0f4  xor     eax, eax
0x14000c0f6  mov     rdx, r13
0x14000c0f9  shl     rdx, 0Ah
0x14000c0fd  add     rdx, [rbp+4B0h]
0x14000c104  mov     byte ptr [rdx], 3
0x14000c107  mov     [rdx+6], ax
0x14000c10b  mov     [rdx+0Eh], ax
0x14000c10f  mov     [rdx+2], r12w
0x14000c114  mov     [rdi+10h], r15d
0x14000c118  test    r14b, r14b
0x14000c11b  jz      short loc_14000C126
0x14000c11d  mov     r8, [rbp+5A8h]
0x14000c124  jmp     short loc_14000C129
0x14000c126  xor     r8d, r8d
0x14000c129  mov     al, r14b
0x14000c12c  neg     al
0x14000c12e  lea     rax, SenseIUCompletion
0x14000c135  mov     [rsp+0B8h+var_78], rax
0x14000c13a  sbb     ecx, ecx
0x14000c13c  and     ecx, 10h
0x14000c13f  add     ecx, r10d
0x14000c142  mov     [rsp+0B8h+var_80], ecx
0x14000c146  mov     rcx, rbp
0x14000c149  mov     dword ptr [rsp+0B8h+var_88], 400h
0x14000c151  mov     [rsp+0B8h+var_90], r8
0x14000c156  mov     r8d, 3
0x14000c15c  mov     [rsp+0B8h+var_98], rdx
0x14000c161  mov     rdx, rdi
0x14000c164  call    IssueBulkRequest
0x14000c169  mov     ebx, eax
0x14000c16b  test    eax, eax
0x14000c16d  jns     short loc_14000C1C5
0x14000c16f  cmp     eax, 0C000000Eh
0x14000c174  jz      short loc_14000C184
0x14000c176  mov     al, 4
0x14000c178  cmp     ebx, 0C000003Ch
0x14000c17e  jnz     short loc_14000C186
0x14000c180  mov     al, 12h
0x14000c182  jmp     short loc_14000C186
0x14000c184  mov     al, 0Eh
0x14000c186  mov     [rsi+3], al
0x14000c189  mov     eax, [rsi+0Ch]
0x14000c18c  test    al, 0C0h
0x14000c18e  jz      short loc_14000C1B0
0x14000c190  mov     rcx, [rdi+78h]; Irp
0x14000c194  mov     dword ptr [rdi+8], 3
0x14000c19b  mov     dword ptr [rdi+10h], 3
0x14000c1a2  call    cs:__imp_IoCancelIrp
0x14000c1a9  nop     dword ptr [rax+rax+00h]
0x14000c1ae  xor     ebx, ebx
0x14000c1b0  test    ebx, ebx
0x14000c1b2  jns     loc_14000C2B8
0x14000c1b8  mov     rcx, rdi
0x14000c1bb  call    QueueReleaseEntry
0x14000c1c0  jmp     loc_14000C2B8
0x14000c1c5  mov     rcx, [rsp+0B8h+var_50]
0x14000c1ca  shl     r13, 5
0x14000c1ce  add     rcx, r13
0x14000c1d1  mov     byte ptr [rcx], 1
0x14000c1d4  movups  xmm0, xmmword ptr [rsi+48h]
0x14000c1d8  movdqu  xmmword ptr [rcx+10h], xmm0
0x14000c1dd  mov     rdx, [rbp+468h]
0x14000c1e4  movzx   eax, byte ptr [rsi+7]
0x14000c1e8  test    rdx, rdx
0x14000c1eb  jz      short loc_14000C1F7
0x14000c1ed  shl     rax, 5
0x14000c1f1  mov     rax, [rax+rdx]
0x14000c1f5  jmp     short loc_14000C1FA
0x14000c1f7  bswap   rax
0x14000c1fa  and     byte ptr [rcx+6], 3
0x14000c1fe  and     byte ptr [rcx+4], 80h
0x14000c202  mov     [rcx+8], rax
0x14000c206  mov     al, r14b
0x14000c209  neg     al
0x14000c20b  mov     [rcx+2], r12w
0x14000c210  mov     [rdi+8], r15d
0x14000c214  sbb     edx, edx
0x14000c216  and     edx, 10h
0x14000c219  test    r14b, r14b
0x14000c21c  jz      short loc_14000C227
0x14000c21e  mov     rax, [rbp+5A0h]
0x14000c225  jmp     short loc_14000C229
0x14000c227  xor     eax, eax
0x14000c229  lea     r9, CommandIUCompletion
0x14000c230  mov     r8d, 1
0x14000c236  mov     [rsp+0B8h+var_78], r9
0x14000c23b  movzx   r9d, word ptr [rsp+0B8h+arg_20]
0x14000c244  mov     [rsp+0B8h+var_80], edx
0x14000c248  mov     rdx, rdi
0x14000c24b  mov     dword ptr [rsp+0B8h+var_88], 20h ; ' '
0x14000c253  mov     [rsp+0B8h+var_90], rax
0x14000c258  mov     [rsp+0B8h+var_98], rcx
0x14000c25d  mov     rcx, rbp
0x14000c260  call    IssueBulkRequest
0x14000c265  mov     ebx, eax
0x14000c267  test    eax, eax
0x14000c269  jns     short loc_14000C2B8
0x14000c26b  cmp     eax, 0C000000Eh
0x14000c270  jz      short loc_14000C280
0x14000c272  mov     al, 4
0x14000c274  cmp     ebx, 0C000003Ch
0x14000c27a  jnz     short loc_14000C282
0x14000c27c  mov     al, 12h
0x14000c27e  jmp     short loc_14000C282
0x14000c280  mov     al, 0Eh
0x14000c282  mov     [rsi+3], al
0x14000c285  xor     ebx, ebx
0x14000c287  mov     dword ptr [rdi+8], 3
0x14000c28e  mov     eax, [rsi+0Ch]
0x14000c291  test    al, 0C0h
0x14000c293  jz      short loc_14000C2A5
0x14000c295  mov     rcx, [rdi+78h]; Irp
0x14000c299  call    cs:__imp_IoCancelIrp
0x14000c2a0  nop     dword ptr [rax+rax+00h]
0x14000c2a5  mov     rcx, [rdi+80h]; Irp
0x14000c2ac  call    cs:__imp_IoCancelIrp
0x14000c2b3  nop     dword ptr [rax+rax+00h]
0x14000c2b8  mov     eax, ebx
0x14000c2ba  add     rsp, 78h
0x14000c2be  pop     r15
0x14000c2c0  pop     r14
0x14000c2c2  pop     r13
0x14000c2c4  pop     r12
0x14000c2c6  pop     rdi
0x14000c2c7  pop     rsi
0x14000c2c8  pop     rbp
0x14000c2c9  pop     rbx
0x14000c2ca  retn
```
