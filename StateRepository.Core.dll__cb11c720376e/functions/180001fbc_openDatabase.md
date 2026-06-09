# openDatabase

- ea: `0x180001fbc`
- end: `0x1800024d4`
- name: `openDatabase`
- size: `1304`
- prototype: `__int64 __fastcall(const char *, __int64 *, int, __int64)`
- caller_count: `3`
- callee_count: `29`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001fb0`
- `0x18008f030`
- `0x18008f050`

## callees

- `0x180001010`
- `0x18000126c`
- `0x180001e70`
- `0x180001ef4`
- `0x180001fbc`
- `0x180004194`
- `0x180004dfc`
- `0x180005d14`
- `0x180009f00`
- `0x18000a404`
- `0x18000aac0`
- `0x18000b220`
- `0x18000bd44`
- `0x18000c250`
- `0x180023b30`
- `0x180024440`
- `0x1800275f0`
- `0x180056c50`
- `0x18005879c`
- `0x18005be2c`
- `0x18005cf6c`
- `0x180060134`
- `0x180064ef0`
- `0x1800653f0`
- `0x180067e68`
- `0x180068380`
- `0x180087708`
- `0x1800878d0`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall openDatabase(const char *a1, __int64 *a2, int a3, __int64 a4)
{
  __int64 v8; // rsi
  __int64 result; // rax
  int v10; // ebp
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rdi
  __int64 *v14; // r14
  __int64 v15; // rax
  unsigned int v16; // ebx
  const char *v17; // rdx
  unsigned int v18; // eax
  const char *v19; // r8
  unsigned int v20; // eax
  __int64 v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rbx
  unsigned int v24; // eax
  int v25; // ebx
  unsigned int v26; // ebx
  __int64 v27; // rcx
  _QWORD v28[9]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v29; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v30; // [rsp+90h] [rbp+18h] BYREF

  v29 = 0;
  v28[0] = 0;
  v8 = 0;
  if ( !a2 )
    return sqlite3ReportError(21, 184352, "misuse");
  *a2 = 0;
  result = sqlite3_initialize();
  if ( !(_DWORD)result )
  {
    if ( (_BYTE)word_1800B5634 && (a3 & 0x8000) == 0 )
    {
      v10 = 1;
      if ( (a3 & 0x10000) == 0 )
        v10 = HIBYTE(word_1800B5634);
    }
    else
    {
      v10 = 0;
    }
    if ( (a3 & 0x40000) != 0 )
    {
      a3 &= ~0x20000u;
    }
    else if ( dword_1800B577C )
    {
      a3 |= 0x20000u;
    }
    v11 = a3 & 0xFFF600E7;
    v30 = v11;
    v12 = sqlite3MallocZero(0x318u);
    v13 = v12;
    if ( !v12 )
      goto LABEL_46;
    v14 = (__int64 *)(v12 + 24);
    if ( v10 )
    {
      v15 = sqlite3MutexAlloc(1);
      *v14 = v15;
      if ( !v15 )
      {
        sqlite3_free(v13);
        v13 = 0;
LABEL_46:
        v26 = sqlite3_errcode(v13);
        if ( (_BYTE)v26 == 7 )
        {
          sqlite3Close(v13, 0);
          v13 = 0;
        }
        else if ( v26 )
        {
          *(_BYTE *)(v13 + 113) = -70;
        }
        v27 = v29;
        *a2 = v13;
        sqlite3_free_filename(v27);
        return v26;
      }
    }
    sqlite3_mutex_enter(*v14);
    *(_WORD *)(v13 + 420) = 0;
    *(_DWORD *)(v13 + 40) = 2;
    *(_BYTE *)(v13 + 113) = 109;
    *(_DWORD *)(v13 + 416) = 1;
    *(_QWORD *)(v13 + 32) = v13 + 672;
    *(_DWORD *)(v13 + 88) = (v11 & 0x2000000) != 0 ? -1 : 255;
    *(_OWORD *)(v13 + 136) = xmmword_18009E9A8;
    *(_OWORD *)(v13 + 152) = xmmword_18009E9B8;
    *(_BYTE *)(v13 + 101) = 1;
    *(_BYTE *)(v13 + 106) = -1;
    *(_OWORD *)(v13 + 168) = xmmword_18009E9C8;
    *(_DWORD *)(v13 + 180) = 0;
    *(_QWORD *)(v13 + 64) = qword_1800B5758;
    *(_QWORD *)(v13 + 208) = off_1800B5540;
    *(_QWORD *)(v13 + 48) |= 0xE00480E0uLL;
    *(_DWORD *)(v13 + 116) = 0;
    *(_QWORD *)(v13 + 632) = 0;
    *(_QWORD *)(v13 + 640) = 0;
    *(_QWORD *)(v13 + 624) = 0;
    *(_QWORD *)(v13 + 560) = 0;
    *(_QWORD *)(v13 + 568) = 0;
    *(_QWORD *)(v13 + 552) = 0;
    createCollation(v13, (__int64)"BINARY", 1u, 0, (__int64)&binCollFunc, 0);
    createCollation(v13, (__int64)"BINARY", 3u, 0, (__int64)&binCollFunc, 0);
    createCollation(v13, (__int64)"BINARY", 2u, 0, (__int64)&binCollFunc, 0);
    createCollation(v13, (__int64)"NOCASE", 1u, 0, (__int64)nocaseCollatingFunc, 0);
    createCollation(v13, (__int64)"RTRIM", 1u, 0, (__int64)rtrimCollFunc, 0);
    if ( *(_BYTE *)(v13 + 103) )
      goto LABEL_43;
    *(_DWORD *)(v13 + 76) = v11;
    if ( ((1 << (v11 & 7)) & 0x46) != 0 )
    {
      v17 = ":memory:";
      if ( a1 )
        v17 = a1;
      v18 = sqlite3ParseUri(a4, v17, &v30, v13, &v29, v28);
      v16 = v18;
      if ( !v18 )
      {
        v20 = sqlite3BtreeOpen(*(_QWORD *)v13, v29, v13, *(_QWORD *)(v13 + 32) + 8LL, 0, v30 | 0x100);
        if ( v20 )
        {
          if ( v20 == 3082 )
            v20 = 7;
          sqlite3Error(v13, v20);
        }
        else
        {
          sqlite3BtreeEnter(*(_QWORD *)(*(_QWORD *)(v13 + 32) + 8LL));
          v21 = *(_QWORD *)(v13 + 32);
          *(_QWORD *)(v21 + 24) = sqlite3SchemaGet(v13, *(_QWORD *)(v21 + 8));
          if ( !*(_BYTE *)(v13 + 103) )
          {
            v22 = *(_QWORD *)(*(_QWORD *)(v13 + 32) + 24LL);
            LOBYTE(v22) = *(_BYTE *)(v22 + 113);
            sqlite3SetTextEncoding(v13, v22);
          }
          sqlite3BtreeLeave(*(_QWORD *)(*(_QWORD *)(v13 + 32) + 8LL));
          v23 = *(_QWORD *)(v13 + 32);
          *(_QWORD *)(v23 + 56) = sqlite3SchemaGet(v13, 0);
          **(_QWORD **)(v13 + 32) = "main";
          *(_BYTE *)(*(_QWORD *)(v13 + 32) + 16LL) = 3;
          *(_QWORD *)(*(_QWORD *)(v13 + 32) + 32LL) = "temp";
          *(_BYTE *)(*(_QWORD *)(v13 + 32) + 48LL) = 1;
          *(_BYTE *)(v13 + 113) = 118;
          if ( !*(_BYTE *)(v13 + 103) )
          {
            sqlite3Error(v13, 0);
            if ( (unsigned int)sqlite3_overload_function(v13, "MATCH", 2) == 7 )
              sqlite3OomFault(v13);
            v24 = sqlite3_errcode(v13);
            v25 = 0;
            while ( !v24 )
            {
              if ( v25 >= 2 )
              {
                sqlite3AutoLoadExtensions(v13);
                if ( (unsigned int)sqlite3_errcode(v13) )
                  goto LABEL_43;
LABEL_42:
                setupLookaside(v13, 0, (unsigned int)dword_1800B5644, (unsigned int)dword_1800B5648);
                sqlite3_wal_autocheckpoint(v13, 1000);
                goto LABEL_43;
              }
              v24 = ((__int64 (__fastcall *)(__int64))funcs_18000242C[v25++])(v13);
            }
            sqlite3Error(v13, v24);
            goto LABEL_42;
          }
        }
LABEL_43:
        sqlite3_mutex_leave(*v14);
        goto LABEL_46;
      }
      if ( v18 == 7 )
        sqlite3OomFault(v13);
      v8 = v28[0];
      v19 = "%s";
      if ( v28[0] )
      {
LABEL_27:
        sqlite3ErrorWithMsg(v13, v16, v19);
        sqlite3_free(v8);
        goto LABEL_43;
      }
    }
    else
    {
      v16 = 21;
      sqlite3_log(
        21,
        "%s at line %d of [%.10s]",
        "misuse",
        184567,
        "2aabe05e2e8cae4847a802ee2daddc1d7413d8fc560254d93ee3e72c14685b6c");
    }
    v19 = 0;
    goto LABEL_27;
  }
  return result;
}

```

## disassembly

```asm
0x180001fbc  mov     rax, rsp
0x180001fbf  mov     [rax+8], rbx
0x180001fc3  push    rbp
0x180001fc4  push    rsi
0x180001fc5  push    rdi
0x180001fc6  push    r12
0x180001fc8  push    r13
0x180001fca  push    r14
0x180001fcc  push    r15
0x180001fce  sub     rsp, 40h
0x180001fd2  xor     r14d, r14d
0x180001fd5  mov     r13, r9
0x180001fd8  mov     [rax+10h], r14
0x180001fdc  mov     ebx, r8d
0x180001fdf  mov     [rax-48h], r14
0x180001fe3  mov     r15, rdx
0x180001fe6  mov     r12, rcx
0x180001fe9  mov     esi, r14d
0x180001fec  test    rdx, rdx
0x180001fef  jnz     short loc_18000200B
0x180001ff1  lea     r8, aMisuse; "misuse"
0x180001ff8  mov     edx, 2D020h
0x180001ffd  lea     ecx, [r15+15h]
0x180002001  call    sqlite3ReportError
0x180002006  jmp     loc_1800024BC
0x18000200b  mov     [rdx], r14
0x18000200e  call    sqlite3_initialize
0x180002013  test    eax, eax
0x180002015  jnz     loc_1800024BC
0x18000201b  cmp     byte ptr cs:word_1800B5634, r14b
0x180002022  jz      short loc_18000202A
0x180002024  bt      ebx, 0Fh
0x180002028  jnb     short loc_18000202F
0x18000202a  mov     ebp, r14d
0x18000202d  jmp     short loc_180002041
0x18000202f  mov     ebp, 1
0x180002034  bt      ebx, 10h
0x180002038  jb      short loc_180002041
0x18000203a  movzx   ebp, byte ptr cs:word_1800B5634+1
0x180002041  bt      ebx, 12h
0x180002045  jnb     short loc_18000204D
0x180002047  btr     ebx, 11h
0x18000204b  jmp     short loc_18000205A
0x18000204d  cmp     cs:dword_1800B577C, r14d
0x180002054  jz      short loc_18000205A
0x180002056  bts     ebx, 11h
0x18000205a  and     ebx, 0FFF600E7h
0x180002060  mov     ecx, 318h; Size
0x180002065  mov     [rsp+78h+arg_10], ebx
0x18000206c  call    sqlite3MallocZero
0x180002071  mov     rdi, rax
0x180002074  test    rax, rax
0x180002077  jz      loc_180002483
0x18000207d  lea     r14, [rax+18h]
0x180002081  test    ebp, ebp
0x180002083  jz      short loc_1800020A8
0x180002085  mov     ecx, 1
0x18000208a  call    sqlite3MutexAlloc
0x18000208f  xor     ebp, ebp
0x180002091  mov     [r14], rax
0x180002094  test    rax, rax
0x180002097  jnz     short loc_1800020AA
0x180002099  mov     rcx, rdi
0x18000209c  call    sqlite3_free
0x1800020a1  mov     edi, ebp
0x1800020a3  jmp     loc_180002485
0x1800020a8  xor     ebp, ebp
0x1800020aa  mov     rcx, [r14]
0x1800020ad  call    sqlite3_mutex_enter
0x1800020b2  mov     [rdi+1A4h], bp
0x1800020b9  mov     eax, ebx
0x1800020bb  mov     dword ptr [rdi+28h], 2
0x1800020c2  and     eax, 2000000h
0x1800020c7  mov     byte ptr [rdi+71h], 6Dh ; 'm'
0x1800020cb  neg     eax
0x1800020cd  mov     dword ptr [rdi+1A0h], 1
0x1800020d7  lea     rax, [rdi+2A0h]
0x1800020de  mov     [rdi+20h], rax
0x1800020e2  sbb     ecx, ecx
0x1800020e4  and     ecx, 0FFFFFF00h
0x1800020ea  mov     [rsp+78h+var_50], rbp
0x1800020ef  add     ecx, 0FFh
0x1800020f5  xor     r9d, r9d
0x1800020f8  mov     [rdi+58h], ecx
0x1800020fb  mov     r8b, 1
0x1800020fe  movups  xmm0, cs:xmmword_18009E9A8
0x180002105  mov     rcx, rdi
0x180002108  movups  xmmword ptr [rdi+88h], xmm0
0x18000210f  movups  xmm1, cs:xmmword_18009E9B8
0x180002116  movups  xmmword ptr [rdi+98h], xmm1
0x18000211d  movups  xmm0, cs:xmmword_18009E9C8
0x180002124  mov     byte ptr [rdi+65h], 1
0x180002128  mov     byte ptr [rdi+6Ah], 0FFh
0x18000212c  movups  xmmword ptr [rdi+0A8h], xmm0
0x180002133  mov     [rdi+0B4h], ebp
0x180002139  mov     rax, cs:qword_1800B5758
0x180002140  mov     [rdi+40h], rax
0x180002144  lea     rax, off_1800B5540; "ANY"
0x18000214b  mov     [rdi+0D0h], rax
0x180002152  mov     eax, 0E00480E0h
0x180002157  or      [rdi+30h], rax
0x18000215b  lea     rax, binCollFunc
0x180002162  mov     [rdi+74h], ebp
0x180002165  mov     [rdi+278h], rbp
0x18000216c  mov     [rdi+280h], rbp
0x180002173  mov     [rdi+270h], rsi
0x18000217a  mov     [rdi+230h], rbp
0x180002181  mov     [rdi+238h], rbp
0x180002188  lea     rbp, aBinary_0; "BINARY"
0x18000218f  mov     rdx, rbp
0x180002192  mov     [rdi+228h], rsi
0x180002199  mov     [rsp+78h+var_58], rax
0x18000219e  call    createCollation
0x1800021a3  lea     rax, binCollFunc
0x1800021aa  mov     [rsp+78h+var_50], rsi
0x1800021af  xor     r9d, r9d
0x1800021b2  mov     [rsp+78h+var_58], rax
0x1800021b7  mov     r8b, 3
0x1800021ba  mov     rdx, rbp
0x1800021bd  mov     rcx, rdi
0x1800021c0  call    createCollation
0x1800021c5  lea     rax, binCollFunc
0x1800021cc  mov     [rsp+78h+var_50], rsi
0x1800021d1  xor     r9d, r9d
0x1800021d4  mov     [rsp+78h+var_58], rax
0x1800021d9  mov     r8b, 2
0x1800021dc  mov     rdx, rbp
0x1800021df  mov     rcx, rdi
0x1800021e2  call    createCollation
0x1800021e7  lea     rax, nocaseCollatingFunc
0x1800021ee  xor     ebp, ebp
0x1800021f0  mov     [rsp+78h+var_50], rbp
0x1800021f5  lea     rdx, aNocase; "NOCASE"
0x1800021fc  xor     r9d, r9d
0x1800021ff  mov     [rsp+78h+var_58], rax
0x180002204  mov     r8b, 1
0x180002207  mov     rcx, rdi
0x18000220a  call    createCollation
0x18000220f  lea     rax, rtrimCollFunc
0x180002216  mov     [rsp+78h+var_50], rbp
0x18000221b  xor     r9d, r9d
0x18000221e  mov     [rsp+78h+var_58], rax
0x180002223  mov     r8b, 1
0x180002226  lea     rdx, aRtrim_0; "RTRIM"
0x18000222d  mov     rcx, rdi
0x180002230  call    createCollation
0x180002235  cmp     [rdi+67h], bpl
0x180002239  jnz     loc_180002466
0x18000223f  mov     [rdi+4Ch], ebx
0x180002242  lea     eax, [rbp+1]
0x180002245  and     ebx, 7
0x180002248  mov     cl, bl
0x18000224a  shl     eax, cl
0x18000224c  test    al, 46h
0x18000224e  jnz     short loc_18000227C
0x180002250  lea     rax, a20241207203959+14h; "2aabe05e2e8cae4847a802ee2daddc1d7413d8f"...
0x180002257  mov     r9d, 2D0F7h
0x18000225d  lea     ebx, [rbp+15h]
0x180002260  mov     [rsp+78h+var_58], rax
0x180002265  mov     ecx, ebx
0x180002267  lea     r8, aMisuse; "misuse"
0x18000226e  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x180002275  call    sqlite3_log
0x18000227a  jmp     short loc_1800022D8
0x18000227c  lea     rax, [rsp+78h+var_48]
0x180002281  test    r12, r12
0x180002284  mov     [rsp+78h+var_50], rax
0x180002289  lea     rdx, Str2; ":memory:"
0x180002290  lea     rax, [rsp+78h+arg_8]
0x180002298  cmovnz  rdx, r12
0x18000229c  mov     r9, rdi
0x18000229f  mov     [rsp+78h+var_58], rax
0x1800022a4  lea     r8, [rsp+78h+arg_10]
0x1800022ac  mov     rcx, r13
0x1800022af  call    sqlite3ParseUri
0x1800022b4  mov     ebx, eax
0x1800022b6  test    eax, eax
0x1800022b8  jz      short loc_1800022F5
0x1800022ba  cmp     eax, 7
0x1800022bd  jnz     short loc_1800022C7
0x1800022bf  mov     rcx, rdi
0x1800022c2  call    sqlite3OomFault
0x1800022c7  mov     rsi, [rsp+78h+var_48]
0x1800022cc  lea     r8, aS_7; "%s"
0x1800022d3  test    rsi, rsi
0x1800022d6  jnz     short loc_1800022DB
0x1800022d8  mov     r8, rbp
0x1800022db  mov     r9, rsi
0x1800022de  mov     edx, ebx
0x1800022e0  mov     rcx, rdi
0x1800022e3  call    sqlite3ErrorWithMsg
0x1800022e8  mov     rcx, rsi
0x1800022eb  call    sqlite3_free
0x1800022f0  jmp     loc_180002466
0x1800022f5  mov     eax, [rsp+78h+arg_10]
0x1800022fc  mov     r8, rdi
0x1800022ff  mov     r9, [rdi+20h]
0x180002303  bts     eax, 8
0x180002307  mov     rdx, [rsp+78h+arg_8]
0x18000230f  add     r9, 8
0x180002313  mov     rcx, [rdi]
0x180002316  mov     dword ptr [rsp+78h+var_50], eax
0x18000231a  mov     dword ptr [rsp+78h+var_58], ebp
0x18000231e  call    sqlite3BtreeOpen
0x180002323  test    eax, eax
0x180002325  jz      short loc_180002343
0x180002327  cmp     eax, 0C0Ah
0x18000232c  mov     ecx, 7
0x180002331  cmovz   eax, ecx
0x180002334  mov     rcx, rdi
0x180002337  mov     edx, eax
0x180002339  call    sqlite3Error
0x18000233e  jmp     loc_180002466
0x180002343  mov     rcx, [rdi+20h]
0x180002347  mov     rcx, [rcx+8]
0x18000234b  call    sqlite3BtreeEnter
0x180002350  mov     rbx, [rdi+20h]
0x180002354  mov     rcx, rdi
0x180002357  mov     rdx, rbx
0x18000235a  mov     rdx, [rbx+8]
0x18000235e  call    sqlite3SchemaGet
0x180002363  mov     [rbx+18h], rax
0x180002367  cmp     [rdi+67h], bpl
0x18000236b  jnz     short loc_180002380
0x18000236d  mov     rax, [rdi+20h]
0x180002371  mov     rcx, rdi
0x180002374  mov     rdx, [rax+18h]
0x180002378  mov     dl, [rdx+71h]
0x18000237b  call    sqlite3SetTextEncoding
0x180002380  mov     rcx, [rdi+20h]
0x180002384  mov     rcx, [rcx+8]
0x180002388  call    sqlite3BtreeLeave
0x18000238d  mov     rbx, [rdi+20h]
0x180002391  xor     edx, edx
0x180002393  mov     rcx, rdi
0x180002396  call    sqlite3SchemaGet
0x18000239b  mov     [rbx+38h], rax
0x18000239f  lea     rcx, aMain; "main"
0x1800023a6  mov     rax, [rdi+20h]
0x1800023aa  mov     [rax], rcx
0x1800023ad  lea     rcx, aTemp; "temp"
0x1800023b4  mov     rax, [rdi+20h]
0x1800023b8  mov     byte ptr [rax+10h], 3
0x1800023bc  mov     rax, [rdi+20h]
0x1800023c0  mov     [rax+20h], rcx
0x1800023c4  mov     rax, [rdi+20h]
0x1800023c8  mov     byte ptr [rax+30h], 1
0x1800023cc  mov     byte ptr [rdi+71h], 76h ; 'v'
0x1800023d0  cmp     [rdi+67h], bpl
0x1800023d4  jnz     loc_180002466
0x1800023da  xor     edx, edx
0x1800023dc  mov     rcx, rdi
0x1800023df  call    sqlite3Error
0x1800023e4  mov     r8d, 2
0x1800023ea  lea     rdx, aMatch; "MATCH"
0x1800023f1  mov     rcx, rdi
0x1800023f4  call    sqlite3_overload_function
0x1800023f9  mov     ecx, 7
0x1800023fe  cmp     eax, ecx
0x180002400  jnz     short loc_18000240A
0x180002402  mov     rcx, rdi
0x180002405  call    sqlite3OomFault
0x18000240a  mov     rcx, rdi
0x18000240d  call    sqlite3_errcode
0x180002412  mov     ebx, ebp
0x180002414  jmp     short loc_180002433
0x180002416  mov     rcx, rdi
0x180002419  cmp     ebx, 2
0x18000241c  jge     short loc_180002470
0x18000241e  lea     rdx, funcs_18000242C
0x180002425  movsxd  rax, ebx
0x180002428  mov     rax, ds:(funcs_18000242C - 18009B4C0h)[rdx+rax*8]
0x18000242c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002431  inc     ebx
0x180002433  test    eax, eax
0x180002435  jz      short loc_180002416
0x180002437  mov     edx, eax
0x180002439  mov     rcx, rdi
0x18000243c  call    sqlite3Error
0x180002441  mov     r9d, cs:dword_1800B5648
0x180002448  xor     edx, edx
0x18000244a  mov     r8d, cs:dword_1800B5644
0x180002451  mov     rcx, rdi
0x180002454  call    setupLookaside
0x180002459  mov     edx, 3E8h
0x18000245e  mov     rcx, rdi
0x180002461  call    sqlite3_wal_autocheckpoint
0x180002466  mov     rcx, [r14]
0x180002469  call    sqlite3_mutex_leave
0x18000246e  jmp     short loc_180002485
0x180002470  call    sqlite3AutoLoadExtensions
0x180002475  mov     rcx, rdi
0x180002478  call    sqlite3_errcode
0x18000247d  test    eax, eax
0x18000247f  jz      short loc_180002441
0x180002481  jmp     short loc_180002466
0x180002483  xor     ebp, ebp
0x180002485  mov     rcx, rdi
0x180002488  call    sqlite3_errcode
0x18000248d  mov     ebx, eax
  ... truncated ...
```
