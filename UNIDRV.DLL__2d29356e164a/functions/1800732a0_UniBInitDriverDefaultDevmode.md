# UniBInitDriverDefaultDevmode

- ea: `0x1800732a0`
- end: `0x180073658`
- name: `UniBInitDriverDefaultDevmode`
- size: `952`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180023c60`

## callees

- `0x1800039d8`
- `0x180004454`
- `0x18003ed80`
- `0x180040294`
- `0x18004e340`
- `0x1800732a0`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x18007356d`
- `WINSPOOL!OpenPrinterW` at `0x18007356d`
- `WINSPOOL!ClosePrinter` at `0x1800735b5`
- `WINSPOOL!ClosePrinter` at `0x1800735b5`
- `KERNEL32!GetLastError` at `0x180073577`
- `KERNEL32!GetLastError` at `0x180073577`

## string_xrefs

- `0x180073580`: `Failed to open printer %s: %d`

## pseudocode

```c
__int64 __fastcall UniBInitDriverDefaultDevmode(__int64 a1, void *a2, __int64 a3, __int64 a4, unsigned int a5)
{
  __int64 v5; // rax
  __int64 v9; // rsi
  __int64 v10; // r9
  unsigned int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rax
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rax
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rax
  __int16 v31; // r10
  _DWORD *v32; // rdx
  DWORD LastError; // eax
  __int64 v34; // rdx
  HANDLE phPrinter; // [rsp+58h] [rbp+10h] BYREF

  phPrinter = a2;
  v5 = *(_QWORD *)(a3 + 328);
  if ( *(_DWORD *)(v5 + 60) )
    v9 = v5 + *(unsigned int *)(v5 + 60);
  else
    v9 = 0;
  *(_DWORD *)(a1 + 64) = 100860929;
  v10 = 67227459;
  *(_WORD *)(a1 + 76) = 1;
  *(_DWORD *)(a1 + 72) = 67227459;
  *(_DWORD *)(a1 + 196) = 1;
  *(_DWORD *)(a1 + 180) = 1;
  *(_DWORD *)(a1 + 68) = 39583964;
  *(_DWORD *)(a1 + 92) = 65537;
  *(_DWORD *)(a1 + 98) = 65539;
  *(_WORD *)(a1 + 88) = 15;
  *(_WORD *)(a1 + 84) = 100;
  if ( *(_DWORD *)(a3 + 300) )
  {
    VConfigXPSDefaultDevmode(a3, a1);
    *(_DWORD *)(a1 + 72) &= 0xFBFFF3FF;
    v11 = *(_DWORD *)(a3 + 236);
    v12 = *(unsigned int *)(a1 + 72);
    if ( v11 && (v13 = *(_QWORD *)(a3 + 328) + v11) != 0 )
    {
      v14 = PGetIndexedOption(a3, v13, *(unsigned int *)(v13 + 20), v12);
      if ( v14 )
      {
        v10 = (unsigned int)v10 | 1;
        *(_DWORD *)(a1 + 72) = v10;
        *(_WORD *)(a1 + 76) = (*(_DWORD *)(v14 + 56) != 0) + 1;
      }
    }
    else
    {
      v10 = (unsigned int)v12 & 0xFFFFFFFE;
      *(_DWORD *)(a1 + 72) = v10;
    }
    v15 = *(_DWORD *)(a3 + 220);
    if ( v15 && (v16 = *(_QWORD *)(a3 + 328) + v15) != 0 )
    {
      v17 = PGetIndexedOption(a3, v16, *(unsigned int *)(v16 + 20), v10);
      if ( v17 )
      {
        LODWORD(v10) = v10 | 0x200;
        *(_DWORD *)(a1 + 72) = v10;
        *(_WORD *)(a1 + 88) = *(_WORD *)(v17 + 60);
      }
    }
    else
    {
      LODWORD(v10) = v10 & 0xFFFFFDFF;
      *(_DWORD *)(a1 + 72) = v10;
    }
  }
  LOWORD(v18) = 0x7FFF;
  if ( *(_DWORD *)(a3 + 64) < 0x7FFFu )
    v18 = *(_DWORD *)(a3 + 64);
  *(_WORD *)(a1 + 86) = v18;
  *(_DWORD *)(a1 + 188) = 1;
  *(_DWORD *)(a1 + 192) = 2;
  *(_DWORD *)(a1 + 200) = *(_DWORD *)(a3 + 200) + 256;
  if ( *(_DWORD *)(a3 + 196) == -1 && *(_DWORD *)(a3 + 192) == -1 && *(_DWORD *)(a3 + 188) == -1 )
    *(_DWORD *)(a1 + 200) = -1;
  if ( !*(_DWORD *)(a3 + 300) )
  {
    v10 = (unsigned int)v10 | 0x1800000;
    *(_DWORD *)(a1 + 72) = v10;
    if ( v9 )
    {
      if ( !*(_DWORD *)(v9 + 404) )
        *(_WORD *)(a1 + 98) = 2;
    }
  }
  v19 = *(_DWORD *)(a3 + 204);
  if ( v19 )
  {
    v20 = *(_QWORD *)(a3 + 328) + v19;
    if ( v20 )
    {
      v21 = PGetIndexedOption(a3, v20, *(unsigned int *)(v20 + 20), v10);
      if ( v21 )
      {
        v10 = (unsigned int)v10 | 0x2400;
        *(_DWORD *)(a1 + 72) = v10;
        *(_WORD *)(a1 + 90) = *(_WORD *)(v21 + 56);
        *(_WORD *)(a1 + 96) = *(_WORD *)(v21 + 60);
      }
    }
  }
  v22 = *(_DWORD *)(a3 + 216);
  if ( v22 )
  {
    v23 = *(_QWORD *)(a3 + 328) + v22;
    if ( v23 )
    {
      LODWORD(v10) = v10 | 0x1000;
      *(_DWORD *)(a1 + 72) = v10;
      v24 = PGetIndexedOption(a3, v23, *(unsigned int *)(v23 + 20), v10);
      if ( v24 )
        *(_WORD *)(a1 + 94) = *(_WORD *)(v24 + 56);
    }
  }
  v25 = *(_DWORD *)(a3 + 224);
  if ( v25 )
  {
    v26 = *(_QWORD *)(a3 + 328) + v25;
    if ( v26 )
    {
      LODWORD(v10) = v10 | 0x2000000;
      *(_DWORD *)(a1 + 72) = v10;
      v27 = PGetIndexedOption(a3, v26, *(unsigned int *)(v26 + 20), v10);
      if ( v27 )
        *(_DWORD *)(a1 + 196) = *(__int16 *)(v27 + 56);
    }
  }
  if ( (*(_BYTE *)(a3 + 140) & 8) != 0 )
  {
    v28 = *(_DWORD *)(a3 + 232);
    if ( v28 )
    {
      v29 = *(_QWORD *)(a3 + 328) + v28;
      if ( v29 )
      {
        v30 = PGetIndexedOption(a3, v29, *(unsigned int *)(v29 + 20), v10);
        if ( v30 )
        {
          if ( *(_DWORD *)(v30 + 44) )
          {
            v32 = (_DWORD *)(*(_QWORD *)(a3 + 328) + *(unsigned int *)(v30 + 44));
            if ( v32 )
            {
              if ( *v32 )
                *(_WORD *)(a1 + 92) = v31;
            }
          }
        }
      }
    }
    *(_DWORD *)(a1 + 72) = v10 | 0x800;
  }
  phPrinter = 0;
  if ( !OpenPrinterW(0, &phPrinter, 0) )
  {
    LastError = GetLastError();
    WriteDbgTraceWarning("UniBInitDriverDefaultDevmode", L"Failed to open printer %s: %d", 0, LastError);
  }
  UniVDefaultDevmodeFormFields(a3, a1, a5, phPrinter);
  if ( phPrinter )
    ClosePrinter(phPrinter);
  v34 = *(unsigned __int16 *)(a1 + 68);
  *(_DWORD *)(v34 + a1 + 4) = 34;
  *(_DWORD *)(v34 + a1 + 8) = 604;
  *(_QWORD *)(v34 + a1 + 32) = 0;
  *(_DWORD *)(v34 + a1 + 40) = 0;
  *(_QWORD *)(v34 + a1 + 20) = 0;
  *(_DWORD *)(v34 + a1 + 28) = *(_DWORD *)(a3 + 200);
  *(_QWORD *)(v34 + a1 + 560) = 1;
  *(_DWORD *)(v34 + a1 + 568) = 0;
  *(_DWORD *)(v34 + a1 + 16) = 0;
  *(_OWORD *)(v34 + a1 + 572) = 0;
  *(_OWORD *)(v34 + a1 + 588) = 0;
  *(_DWORD *)(v34 + a1) = 1431193924;
  *(_DWORD *)(v34 + a1 + 12) = *(_DWORD *)(a4 + 12);
  *(_DWORD *)(v34 + a1 + 44) = *(_DWORD *)(a4 + 20);
  GPDInitDefaultOptions(a4, a1 + 48 + v34, 256, 0);
  return 1;
}

```

## disassembly

```asm
0x1800732a0  mov     [rsp+arg_0], rbx
0x1800732a5  mov     [rsp+arg_10], rbp
0x1800732aa  mov     [rsp+phPrinter], rdx
0x1800732af  push    rsi
0x1800732b0  push    rdi
0x1800732b1  push    r13
0x1800732b3  push    r14
0x1800732b5  push    r15
0x1800732b7  sub     rsp, 20h
0x1800732bb  mov     rax, [r8+148h]
0x1800732c2  xor     r14d, r14d
0x1800732c5  mov     rbp, r9
0x1800732c8  mov     rdi, r8
0x1800732cb  mov     rbx, rcx
0x1800732ce  cmp     [rax+3Ch], r14d
0x1800732d2  jz      short loc_1800732DC
0x1800732d4  mov     esi, [rax+3Ch]
0x1800732d7  add     rsi, rax
0x1800732da  jmp     short loc_1800732DF
0x1800732dc  mov     rsi, r14
0x1800732df  mov     r15d, 1
0x1800732e5  mov     dword ptr [rcx+40h], 6030401h
0x1800732ec  mov     r9d, 401CF43h
0x1800732f2  mov     [rcx+4Ch], r15w
0x1800732f7  mov     [rcx+48h], r9d
0x1800732fb  mov     [rcx+0C4h], r15d
0x180073302  mov     [rcx+0B4h], r15d
0x180073309  mov     dword ptr [rcx+44h], 25C00DCh
0x180073310  mov     dword ptr [rcx+5Ch], 10001h
0x180073317  mov     dword ptr [rcx+62h], 10003h
0x18007331e  mov     word ptr [rcx+58h], 0Fh
0x180073324  mov     word ptr [rcx+54h], 64h ; 'd'
0x18007332a  cmp     [r8+12Ch], r14d
0x180073331  jz      loc_1800733D9
0x180073337  mov     rdx, rbx
0x18007333a  mov     rcx, rdi
0x18007333d  call    VConfigXPSDefaultDevmode
0x180073342  and     dword ptr [rbx+48h], 0FBFFF3FFh
0x180073349  mov     eax, [rdi+0ECh]
0x18007334f  mov     r9d, [rbx+48h]
0x180073353  test    eax, eax
0x180073355  jz      short loc_18007338F
0x180073357  mov     edx, eax
0x180073359  add     rdx, [rdi+148h]
0x180073360  jz      short loc_18007338F
0x180073362  mov     r8d, [rdx+14h]
0x180073366  mov     rcx, rdi
0x180073369  call    PGetIndexedOption
0x18007336e  test    rax, rax
0x180073371  jz      short loc_180073397
0x180073373  or      r9d, r15d
0x180073376  mov     [rbx+48h], r9d
0x18007337a  mov     eax, [rax+38h]
0x18007337d  neg     eax
0x18007337f  sbb     cx, cx
0x180073382  neg     cx
0x180073385  add     cx, r15w
0x180073389  mov     [rbx+4Ch], cx
0x18007338d  jmp     short loc_180073397
0x18007338f  and     r9d, 0FFFFFFFEh
0x180073393  mov     [rbx+48h], r9d
0x180073397  mov     eax, [rdi+0DCh]
0x18007339d  test    eax, eax
0x18007339f  jz      short loc_1800733D0
0x1800733a1  mov     edx, eax
0x1800733a3  add     rdx, [rdi+148h]
0x1800733aa  jz      short loc_1800733D0
0x1800733ac  mov     r8d, [rdx+14h]
0x1800733b0  mov     rcx, rdi
0x1800733b3  call    PGetIndexedOption
0x1800733b8  test    rax, rax
0x1800733bb  jz      short loc_1800733D9
0x1800733bd  bts     r9d, 9
0x1800733c2  mov     [rbx+48h], r9d
0x1800733c6  movzx   eax, word ptr [rax+3Ch]
0x1800733ca  mov     [rbx+58h], ax
0x1800733ce  jmp     short loc_1800733D9
0x1800733d0  btr     r9d, 9
0x1800733d5  mov     [rbx+48h], r9d
0x1800733d9  mov     eax, 7FFFh
0x1800733de  mov     r10d, 2
0x1800733e4  cmp     [rdi+40h], eax
0x1800733e7  cmovb   eax, [rdi+40h]
0x1800733eb  mov     [rbx+56h], ax
0x1800733ef  mov     [rbx+0BCh], r15d
0x1800733f6  mov     [rbx+0C0h], r10d
0x1800733fd  mov     eax, [rdi+0C8h]
0x180073403  add     eax, 100h
0x180073408  mov     [rbx+0C8h], eax
0x18007340e  or      eax, 0FFFFFFFFh
0x180073411  cmp     [rdi+0C4h], eax
0x180073417  jnz     short loc_18007342F
0x180073419  cmp     [rdi+0C0h], eax
0x18007341f  jnz     short loc_18007342F
0x180073421  cmp     [rdi+0BCh], eax
0x180073427  jnz     short loc_18007342F
0x180073429  mov     [rbx+0C8h], eax
0x18007342f  cmp     [rdi+12Ch], r14d
0x180073436  jnz     short loc_180073456
0x180073438  or      r9d, 1800000h
0x18007343f  mov     [rbx+48h], r9d
0x180073443  test    rsi, rsi
0x180073446  jz      short loc_180073456
0x180073448  cmp     [rsi+194h], r14d
0x18007344f  jnz     short loc_180073456
0x180073451  mov     [rbx+62h], r10w
0x180073456  mov     eax, [rdi+0CCh]
0x18007345c  test    eax, eax
0x18007345e  jz      short loc_18007349A
0x180073460  mov     edx, eax
0x180073462  add     rdx, [rdi+148h]
0x180073469  jz      short loc_18007349A
0x18007346b  mov     r8d, [rdx+14h]
0x18007346f  mov     rcx, rdi
0x180073472  call    PGetIndexedOption
0x180073477  mov     rcx, rax
0x18007347a  test    rax, rax
0x18007347d  jz      short loc_18007349A
0x18007347f  or      r9d, 2400h
0x180073486  mov     [rbx+48h], r9d
0x18007348a  movzx   eax, word ptr [rax+38h]
0x18007348e  mov     [rbx+5Ah], ax
0x180073492  movzx   eax, word ptr [rcx+3Ch]
0x180073496  mov     [rbx+60h], ax
0x18007349a  mov     eax, [rdi+0D8h]
0x1800734a0  test    eax, eax
0x1800734a2  jz      short loc_1800734D1
0x1800734a4  mov     edx, eax
0x1800734a6  add     rdx, [rdi+148h]
0x1800734ad  jz      short loc_1800734D1
0x1800734af  bts     r9d, 0Ch
0x1800734b4  mov     rcx, rdi
0x1800734b7  mov     [rbx+48h], r9d
0x1800734bb  mov     r8d, [rdx+14h]
0x1800734bf  call    PGetIndexedOption
0x1800734c4  test    rax, rax
0x1800734c7  jz      short loc_1800734D1
0x1800734c9  movzx   eax, word ptr [rax+38h]
0x1800734cd  mov     [rbx+5Eh], ax
0x1800734d1  mov     eax, [rdi+0E0h]
0x1800734d7  test    eax, eax
0x1800734d9  jz      short loc_18007350A
0x1800734db  mov     edx, eax
0x1800734dd  add     rdx, [rdi+148h]
0x1800734e4  jz      short loc_18007350A
0x1800734e6  bts     r9d, 19h
0x1800734eb  mov     rcx, rdi
0x1800734ee  mov     [rbx+48h], r9d
0x1800734f2  mov     r8d, [rdx+14h]
0x1800734f6  call    PGetIndexedOption
0x1800734fb  test    rax, rax
0x1800734fe  jz      short loc_18007350A
0x180073500  movsx   eax, word ptr [rax+38h]
0x180073504  mov     [rbx+0C4h], eax
0x18007350a  test    byte ptr [rdi+8Ch], 8
0x180073511  jz      short loc_18007355E
0x180073513  mov     eax, [rdi+0E8h]
0x180073519  test    eax, eax
0x18007351b  jz      short loc_180073555
0x18007351d  mov     edx, eax
0x18007351f  add     rdx, [rdi+148h]
0x180073526  jz      short loc_180073555
0x180073528  mov     r8d, [rdx+14h]
0x18007352c  mov     rcx, rdi
0x18007352f  call    PGetIndexedOption
0x180073534  test    rax, rax
0x180073537  jz      short loc_180073555
0x180073539  cmp     [rax+2Ch], r14d
0x18007353d  jz      short loc_180073555
0x18007353f  mov     edx, [rax+2Ch]
0x180073542  add     rdx, [rdi+148h]
0x180073549  jz      short loc_180073555
0x18007354b  cmp     [rdx], r14d
0x18007354e  jz      short loc_180073555
0x180073550  mov     [rbx+5Ch], r10w
0x180073555  bts     r9d, 0Bh
0x18007355a  mov     [rbx+48h], r9d
0x18007355e  xor     r8d, r8d; pDefault
0x180073561  mov     [rsp+48h+phPrinter], r14
0x180073566  lea     rdx, [rsp+48h+phPrinter]; phPrinter
0x18007356b  xor     ecx, ecx; pPrinterName
0x18007356d  call    cs:__imp_OpenPrinterW
0x180073573  test    eax, eax
0x180073575  jnz     short loc_180073596
0x180073577  call    cs:__imp_GetLastError
0x18007357d  xor     r8d, r8d
0x180073580  lea     rdx, aFailedToOpenPr; "Failed to open printer %s: %d"
0x180073587  mov     r9d, eax
0x18007358a  lea     rcx, aUnibinitdriver; "UniBInitDriverDefaultDevmode"
0x180073591  call    WriteDbgTraceWarning
0x180073596  mov     r9, [rsp+48h+phPrinter]
0x18007359b  mov     rdx, rbx
0x18007359e  mov     r8d, [rsp+48h+arg_20]
0x1800735a3  mov     rcx, rdi
0x1800735a6  call    UniVDefaultDevmodeFormFields
0x1800735ab  mov     rcx, [rsp+48h+phPrinter]; hPrinter
0x1800735b0  test    rcx, rcx
0x1800735b3  jz      short loc_1800735BB
0x1800735b5  call    cs:__imp_ClosePrinter
0x1800735bb  movzx   edx, word ptr [rbx+44h]
0x1800735bf  xor     eax, eax
0x1800735c1  xorps   xmm0, xmm0
0x1800735c4  xor     r9d, r9d
0x1800735c7  mov     r8d, 100h
0x1800735cd  mov     dword ptr [rdx+rbx+4], 22h ; '"'
0x1800735d5  mov     dword ptr [rdx+rbx+8], 25Ch
0x1800735dd  mov     [rdx+rbx+20h], rax
0x1800735e2  mov     [rdx+rbx+28h], eax
0x1800735e6  mov     [rdx+rbx+14h], r14
0x1800735eb  mov     eax, [rdi+0C8h]
0x1800735f1  mov     [rdx+rbx+1Ch], eax
0x1800735f5  mov     [rdx+rbx+230h], r15
0x1800735fd  mov     [rdx+rbx+238h], r14d
0x180073605  mov     [rdx+rbx+10h], r14d
0x18007360a  movups  xmmword ptr [rdx+rbx+23Ch], xmm0
0x180073612  movups  xmmword ptr [rdx+rbx+24Ch], xmm0
0x18007361a  mov     dword ptr [rdx+rbx], 554E4944h
0x180073621  mov     ecx, [rbp+0Ch]
0x180073624  mov     [rdx+rbx+0Ch], ecx
0x180073628  mov     ecx, [rbp+14h]
0x18007362b  mov     [rdx+rbx+2Ch], ecx
0x18007362f  add     rbx, 30h ; '0'
0x180073633  add     rdx, rbx
0x180073636  mov     rcx, rbp
0x180073639  call    GPDInitDefaultOptions
0x18007363e  mov     rbx, [rsp+48h+arg_0]
0x180073643  mov     eax, r15d
0x180073646  mov     rbp, [rsp+48h+arg_10]
0x18007364b  add     rsp, 20h
0x18007364f  pop     r15
0x180073651  pop     r14
0x180073653  pop     r13
0x180073655  pop     rdi
0x180073656  pop     rsi
0x180073657  retn
```
