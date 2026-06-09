# UniBInitDriverDefaultDevmode

- ea: `0x18007535c`
- end: `0x180075727`
- name: `UniBInitDriverDefaultDevmode`
- size: `971`
- prototype: `__int64 __fastcall(__int64, void *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180024150`

## callees

- `0x1800039ac`
- `0x180004320`
- `0x18003fe9c`
- `0x180041488`
- `0x18004fa08`
- `0x18007535c`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x180075629`
- `WINSPOOL!OpenPrinterW` at `0x180075629`
- `WINSPOOL!ClosePrinter` at `0x18007567d`
- `WINSPOOL!ClosePrinter` at `0x18007567d`
- `KERNEL32!GetLastError` at `0x180075639`
- `KERNEL32!GetLastError` at `0x180075639`

## string_xrefs

- `0x180075648`: `Failed to open printer %s: %d`

## pseudocode

```c
__int64 __fastcall UniBInitDriverDefaultDevmode(__int64 a1, void *a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // rax
  __int64 v9; // rsi
  unsigned int v10; // r9d
  unsigned int v11; // eax
  _DWORD *v12; // rdx
  __int64 v13; // rax
  unsigned int v14; // r9d
  unsigned int v15; // eax
  _DWORD *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // eax
  _DWORD *v20; // rdx
  __int64 v21; // rax
  unsigned int v22; // eax
  _DWORD *v23; // rdx
  __int64 v24; // rax
  unsigned int v25; // eax
  _DWORD *v26; // rdx
  __int64 v27; // rax
  unsigned int v28; // eax
  _DWORD *v29; // rdx
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
    if ( v11 && (v12 = (_DWORD *)(*(_QWORD *)(a3 + 328) + v11)) != 0 )
    {
      v13 = PGetIndexedOption(a3, v12, v12[5]);
      if ( v13 )
      {
        v14 |= 1u;
        *(_DWORD *)(a1 + 72) = v14;
        *(_WORD *)(a1 + 76) = (*(_DWORD *)(v13 + 56) != 0) + 1;
      }
    }
    else
    {
      v14 = *(_DWORD *)(a1 + 72) & 0xFFFFFFFE;
      *(_DWORD *)(a1 + 72) = v14;
    }
    v15 = *(_DWORD *)(a3 + 220);
    if ( v15 && (v16 = (_DWORD *)(*(_QWORD *)(a3 + 328) + v15)) != 0 )
    {
      v17 = PGetIndexedOption(a3, v16, v16[5]);
      if ( v17 )
      {
        v10 |= 0x200u;
        *(_DWORD *)(a1 + 72) = v10;
        *(_WORD *)(a1 + 88) = *(_WORD *)(v17 + 60);
      }
    }
    else
    {
      v10 = v14 & 0xFFFFFDFF;
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
    v10 |= 0x1800000u;
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
    v20 = (_DWORD *)(*(_QWORD *)(a3 + 328) + v19);
    if ( v20 )
    {
      v21 = PGetIndexedOption(a3, v20, v20[5]);
      if ( v21 )
      {
        v10 |= 0x2400u;
        *(_DWORD *)(a1 + 72) = v10;
        *(_WORD *)(a1 + 90) = *(_WORD *)(v21 + 56);
        *(_WORD *)(a1 + 96) = *(_WORD *)(v21 + 60);
      }
    }
  }
  v22 = *(_DWORD *)(a3 + 216);
  if ( v22 )
  {
    v23 = (_DWORD *)(*(_QWORD *)(a3 + 328) + v22);
    if ( v23 )
    {
      *(_DWORD *)(a1 + 72) = v10 | 0x1000;
      v24 = PGetIndexedOption(a3, v23, v23[5]);
      if ( v24 )
        *(_WORD *)(a1 + 94) = *(_WORD *)(v24 + 56);
    }
  }
  v25 = *(_DWORD *)(a3 + 224);
  if ( v25 )
  {
    v26 = (_DWORD *)(*(_QWORD *)(a3 + 328) + v25);
    if ( v26 )
    {
      *(_DWORD *)(a1 + 72) = v10 | 0x2000000;
      v27 = PGetIndexedOption(a3, v26, v26[5]);
      if ( v27 )
        *(_DWORD *)(a1 + 196) = *(__int16 *)(v27 + 56);
    }
  }
  if ( (*(_BYTE *)(a3 + 140) & 8) != 0 )
  {
    v28 = *(_DWORD *)(a3 + 232);
    if ( v28 )
    {
      v29 = (_DWORD *)(*(_QWORD *)(a3 + 328) + v28);
      if ( v29 )
      {
        v30 = PGetIndexedOption(a3, v29, v29[5]);
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
    WriteDbgTraceWarning(
      (__int64)"UniBInitDriverDefaultDevmode",
      (__int64)L"Failed to open printer %s: %d",
      0,
      LastError);
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
  GPDInitDefaultOptions(a4, a1 + 48 + v34, 0x100u, 0);
  return 1;
}

```

## disassembly

```asm
0x18007535c  mov     [rsp+arg_0], rbx
0x180075361  mov     [rsp+arg_10], rbp
0x180075366  mov     [rsp+phPrinter], rdx
0x18007536b  push    rsi
0x18007536c  push    rdi
0x18007536d  push    r13
0x18007536f  push    r14
0x180075371  push    r15
0x180075373  sub     rsp, 20h
0x180075377  mov     rax, [r8+148h]
0x18007537e  xor     r14d, r14d
0x180075381  mov     rbp, r9
0x180075384  mov     rdi, r8
0x180075387  mov     rbx, rcx
0x18007538a  cmp     [rax+3Ch], r14d
0x18007538e  jz      short loc_180075398
0x180075390  mov     esi, [rax+3Ch]
0x180075393  add     rsi, rax
0x180075396  jmp     short loc_18007539B
0x180075398  mov     rsi, r14
0x18007539b  mov     r15d, 1
0x1800753a1  mov     dword ptr [rcx+40h], 6030401h
0x1800753a8  mov     r9d, 401CF43h
0x1800753ae  mov     [rcx+4Ch], r15w
0x1800753b3  mov     [rcx+48h], r9d
0x1800753b7  mov     [rcx+0C4h], r15d
0x1800753be  mov     [rcx+0B4h], r15d
0x1800753c5  mov     dword ptr [rcx+44h], 25C00DCh
0x1800753cc  mov     dword ptr [rcx+5Ch], 10001h
0x1800753d3  mov     dword ptr [rcx+62h], 10003h
0x1800753da  mov     word ptr [rcx+58h], 0Fh
0x1800753e0  mov     word ptr [rcx+54h], 64h ; 'd'
0x1800753e6  cmp     [r8+12Ch], r14d
0x1800753ed  jz      loc_180075495
0x1800753f3  mov     rdx, rbx
0x1800753f6  mov     rcx, rdi
0x1800753f9  call    VConfigXPSDefaultDevmode
0x1800753fe  and     dword ptr [rbx+48h], 0FBFFF3FFh
0x180075405  mov     eax, [rdi+0ECh]
0x18007540b  mov     r9d, [rbx+48h]
0x18007540f  test    eax, eax
0x180075411  jz      short loc_18007544B
0x180075413  mov     edx, eax
0x180075415  add     rdx, [rdi+148h]
0x18007541c  jz      short loc_18007544B
0x18007541e  mov     r8d, [rdx+14h]
0x180075422  mov     rcx, rdi
0x180075425  call    PGetIndexedOption
0x18007542a  test    rax, rax
0x18007542d  jz      short loc_180075453
0x18007542f  or      r9d, r15d
0x180075432  mov     [rbx+48h], r9d
0x180075436  mov     eax, [rax+38h]
0x180075439  neg     eax
0x18007543b  sbb     cx, cx
0x18007543e  neg     cx
0x180075441  add     cx, r15w
0x180075445  mov     [rbx+4Ch], cx
0x180075449  jmp     short loc_180075453
0x18007544b  and     r9d, 0FFFFFFFEh
0x18007544f  mov     [rbx+48h], r9d
0x180075453  mov     eax, [rdi+0DCh]
0x180075459  test    eax, eax
0x18007545b  jz      short loc_18007548C
0x18007545d  mov     edx, eax
0x18007545f  add     rdx, [rdi+148h]
0x180075466  jz      short loc_18007548C
0x180075468  mov     r8d, [rdx+14h]
0x18007546c  mov     rcx, rdi
0x18007546f  call    PGetIndexedOption
0x180075474  test    rax, rax
0x180075477  jz      short loc_180075495
0x180075479  bts     r9d, 9
0x18007547e  mov     [rbx+48h], r9d
0x180075482  movzx   eax, word ptr [rax+3Ch]
0x180075486  mov     [rbx+58h], ax
0x18007548a  jmp     short loc_180075495
0x18007548c  btr     r9d, 9
0x180075491  mov     [rbx+48h], r9d
0x180075495  mov     eax, 7FFFh
0x18007549a  mov     r10d, 2
0x1800754a0  cmp     [rdi+40h], eax
0x1800754a3  cmovb   eax, [rdi+40h]
0x1800754a7  mov     [rbx+56h], ax
0x1800754ab  mov     [rbx+0BCh], r15d
0x1800754b2  mov     [rbx+0C0h], r10d
0x1800754b9  mov     eax, [rdi+0C8h]
0x1800754bf  add     eax, 100h
0x1800754c4  mov     [rbx+0C8h], eax
0x1800754ca  or      eax, 0FFFFFFFFh
0x1800754cd  cmp     [rdi+0C4h], eax
0x1800754d3  jnz     short loc_1800754EB
0x1800754d5  cmp     [rdi+0C0h], eax
0x1800754db  jnz     short loc_1800754EB
0x1800754dd  cmp     [rdi+0BCh], eax
0x1800754e3  jnz     short loc_1800754EB
0x1800754e5  mov     [rbx+0C8h], eax
0x1800754eb  cmp     [rdi+12Ch], r14d
0x1800754f2  jnz     short loc_180075512
0x1800754f4  or      r9d, 1800000h
0x1800754fb  mov     [rbx+48h], r9d
0x1800754ff  test    rsi, rsi
0x180075502  jz      short loc_180075512
0x180075504  cmp     [rsi+194h], r14d
0x18007550b  jnz     short loc_180075512
0x18007550d  mov     [rbx+62h], r10w
0x180075512  mov     eax, [rdi+0CCh]
0x180075518  test    eax, eax
0x18007551a  jz      short loc_180075556
0x18007551c  mov     edx, eax
0x18007551e  add     rdx, [rdi+148h]
0x180075525  jz      short loc_180075556
0x180075527  mov     r8d, [rdx+14h]
0x18007552b  mov     rcx, rdi
0x18007552e  call    PGetIndexedOption
0x180075533  mov     rcx, rax
0x180075536  test    rax, rax
0x180075539  jz      short loc_180075556
0x18007553b  or      r9d, 2400h
0x180075542  mov     [rbx+48h], r9d
0x180075546  movzx   eax, word ptr [rax+38h]
0x18007554a  mov     [rbx+5Ah], ax
0x18007554e  movzx   eax, word ptr [rcx+3Ch]
0x180075552  mov     [rbx+60h], ax
0x180075556  mov     eax, [rdi+0D8h]
0x18007555c  test    eax, eax
0x18007555e  jz      short loc_18007558D
0x180075560  mov     edx, eax
0x180075562  add     rdx, [rdi+148h]
0x180075569  jz      short loc_18007558D
0x18007556b  bts     r9d, 0Ch
0x180075570  mov     rcx, rdi
0x180075573  mov     [rbx+48h], r9d
0x180075577  mov     r8d, [rdx+14h]
0x18007557b  call    PGetIndexedOption
0x180075580  test    rax, rax
0x180075583  jz      short loc_18007558D
0x180075585  movzx   eax, word ptr [rax+38h]
0x180075589  mov     [rbx+5Eh], ax
0x18007558d  mov     eax, [rdi+0E0h]
0x180075593  test    eax, eax
0x180075595  jz      short loc_1800755C6
0x180075597  mov     edx, eax
0x180075599  add     rdx, [rdi+148h]
0x1800755a0  jz      short loc_1800755C6
0x1800755a2  bts     r9d, 19h
0x1800755a7  mov     rcx, rdi
0x1800755aa  mov     [rbx+48h], r9d
0x1800755ae  mov     r8d, [rdx+14h]
0x1800755b2  call    PGetIndexedOption
0x1800755b7  test    rax, rax
0x1800755ba  jz      short loc_1800755C6
0x1800755bc  movsx   eax, word ptr [rax+38h]
0x1800755c0  mov     [rbx+0C4h], eax
0x1800755c6  test    byte ptr [rdi+8Ch], 8
0x1800755cd  jz      short loc_18007561A
0x1800755cf  mov     eax, [rdi+0E8h]
0x1800755d5  test    eax, eax
0x1800755d7  jz      short loc_180075611
0x1800755d9  mov     edx, eax
0x1800755db  add     rdx, [rdi+148h]
0x1800755e2  jz      short loc_180075611
0x1800755e4  mov     r8d, [rdx+14h]
0x1800755e8  mov     rcx, rdi
0x1800755eb  call    PGetIndexedOption
0x1800755f0  test    rax, rax
0x1800755f3  jz      short loc_180075611
0x1800755f5  cmp     [rax+2Ch], r14d
0x1800755f9  jz      short loc_180075611
0x1800755fb  mov     edx, [rax+2Ch]
0x1800755fe  add     rdx, [rdi+148h]
0x180075605  jz      short loc_180075611
0x180075607  cmp     [rdx], r14d
0x18007560a  jz      short loc_180075611
0x18007560c  mov     [rbx+5Ch], r10w
0x180075611  bts     r9d, 0Bh
0x180075616  mov     [rbx+48h], r9d
0x18007561a  xor     r8d, r8d; pDefault
0x18007561d  mov     [rsp+48h+phPrinter], r14
0x180075622  lea     rdx, [rsp+48h+phPrinter]; phPrinter
0x180075627  xor     ecx, ecx; pPrinterName
0x180075629  call    cs:__imp_OpenPrinterW
0x180075630  nop     dword ptr [rax+rax+00h]
0x180075635  test    eax, eax
0x180075637  jnz     short loc_18007565E
0x180075639  call    cs:__imp_GetLastError
0x180075640  nop     dword ptr [rax+rax+00h]
0x180075645  xor     r8d, r8d
0x180075648  lea     rdx, aFailedToOpenPr; "Failed to open printer %s: %d"
0x18007564f  mov     r9d, eax
0x180075652  lea     rcx, aUnibinitdriver; "UniBInitDriverDefaultDevmode"
0x180075659  call    WriteDbgTraceWarning
0x18007565e  mov     r9, [rsp+48h+phPrinter]
0x180075663  mov     rdx, rbx
0x180075666  mov     r8d, [rsp+48h+arg_20]
0x18007566b  mov     rcx, rdi
0x18007566e  call    UniVDefaultDevmodeFormFields
0x180075673  mov     rcx, [rsp+48h+phPrinter]; hPrinter
0x180075678  test    rcx, rcx
0x18007567b  jz      short loc_180075689
0x18007567d  call    cs:__imp_ClosePrinter
0x180075684  nop     dword ptr [rax+rax+00h]
0x180075689  movzx   edx, word ptr [rbx+44h]
0x18007568d  xor     eax, eax
0x18007568f  xorps   xmm0, xmm0
0x180075692  xor     r9d, r9d
0x180075695  mov     r8d, 100h
0x18007569b  mov     dword ptr [rdx+rbx+4], 22h ; '"'
0x1800756a3  mov     dword ptr [rdx+rbx+8], 25Ch
0x1800756ab  mov     [rdx+rbx+20h], rax
0x1800756b0  mov     [rdx+rbx+28h], eax
0x1800756b4  mov     [rdx+rbx+14h], r14
0x1800756b9  mov     eax, [rdi+0C8h]
0x1800756bf  mov     [rdx+rbx+1Ch], eax
0x1800756c3  mov     [rdx+rbx+230h], r15
0x1800756cb  mov     [rdx+rbx+238h], r14d
0x1800756d3  mov     [rdx+rbx+10h], r14d
0x1800756d8  movups  xmmword ptr [rdx+rbx+23Ch], xmm0
0x1800756e0  movups  xmmword ptr [rdx+rbx+24Ch], xmm0
0x1800756e8  mov     dword ptr [rdx+rbx], 554E4944h
0x1800756ef  mov     ecx, [rbp+0Ch]
0x1800756f2  mov     [rdx+rbx+0Ch], ecx
0x1800756f6  mov     ecx, [rbp+14h]
0x1800756f9  mov     [rdx+rbx+2Ch], ecx
0x1800756fd  add     rbx, 30h ; '0'
0x180075701  add     rdx, rbx
0x180075704  mov     rcx, rbp
0x180075707  call    GPDInitDefaultOptions
0x18007570c  mov     rbx, [rsp+48h+arg_0]
0x180075711  mov     eax, r15d
0x180075714  mov     rbp, [rsp+48h+arg_10]
0x180075719  add     rsp, 20h
0x18007571d  pop     r15
0x18007571f  pop     r14
0x180075721  pop     r13
0x180075723  pop     rdi
0x180075724  pop     rsi
0x180075725  retn
```
