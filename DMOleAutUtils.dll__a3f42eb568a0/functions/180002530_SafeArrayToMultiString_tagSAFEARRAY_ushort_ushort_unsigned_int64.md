# SafeArrayToMultiString(tagSAFEARRAY *,ushort,ushort * *,unsigned __int64 *)

- ea: `0x180002530`
- end: `0x18000277f`
- name: `?SafeArrayToMultiString@@YAJPEAUtagSAFEARRAY@@GPEAPEAGPEA_K@Z`
- size: `591`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, unsigned __int16, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002530`
- `0x180002788`
- `0x180003574`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800025ae`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800025ae`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000258c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000258c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180002718`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180002718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002709`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002709`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000264d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000264d`

## pseudocode

```c
__int64 __fastcall SafeArrayToMultiString(
        SAFEARRAY *psa,
        unsigned __int16 a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4)
{
  unsigned int v4; // r13d
  SAFEARRAY *v6; // r14
  unsigned __int16 *v7; // rdi
  unsigned __int16 *v8; // rsi
  HRESULT UBound; // ebx
  int v10; // r11d
  bool v11; // zf
  unsigned int v12; // edx
  unsigned int v13; // r9d
  _WORD *v14; // rcx
  __int64 v15; // r8
  int v16; // r15d
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // r14
  unsigned __int64 v19; // rcx
  unsigned __int16 *v20; // rsi
  unsigned __int64 v22; // rsi
  unsigned int v23; // [rsp+28h] [rbp-38h]
  LONG plUbound; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v25; // [rsp+38h] [rbp-28h] BYREF
  void *ppvData; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v27; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v28; // [rsp+50h] [rbp-10h]

  v4 = 0;
  plUbound = 0;
  ppvData = 0;
  v6 = psa;
  v27 = 0;
  v7 = 0;
  v8 = 0;
  if ( !psa || !a3 )
    goto LABEL_2;
  UBound = SafeArrayAccessData(psa, &ppvData);
  if ( UBound < 0 )
    goto LABEL_26;
  if ( !ppvData )
  {
LABEL_2:
    UBound = -2147024809;
    goto LABEL_26;
  }
  UBound = SafeArrayGetUBound(v6, 1u, &plUbound);
  if ( UBound >= 0 )
  {
    v10 = 0;
    v11 = plUbound == -1;
    v12 = plUbound + 1;
    v13 = 0;
    ++plUbound;
    if ( !v11 )
    {
      do
      {
        v14 = (_WORD *)*((_QWORD *)ppvData + v13);
        if ( !v14 )
          goto LABEL_2;
        v15 = 0x7FFFFFFF;
        do
        {
          if ( !*v14 )
            break;
          ++v14;
          --v15;
        }
        while ( v15 );
        UBound = v15 == 0 ? 0x80070057 : 0;
        if ( !v15 )
          goto LABEL_26;
        ++v13;
        v10 += v15 != 0 ? 0x7FFFFFFF - v15 + 1 : 1;
      }
      while ( v13 < v12 );
    }
    v16 = v10 + (a2 != 0) + 1;
    if ( v16 < 0 )
    {
      UBound = -2147467259;
    }
    else
    {
      v17 = (unsigned __int16 *)LocalAlloc(0, (unsigned int)(2 * v16));
      v7 = v17;
      if ( v17 )
      {
        *v17 = 0;
        v18 = v17;
        v28 = (unsigned int)(v16 - 1);
        v19 = (unsigned int)v16;
        v17[v28] = 0;
        v25 = (unsigned int)v16;
        if ( plUbound )
        {
          while ( 1 )
          {
            UBound = StringCchCatExW(v18, v19, *((const unsigned __int16 **)ppvData + v4), &v27, &v25, v23);
            if ( UBound < 0 )
              break;
            if ( !v25 )
            {
              UBound = -2147467259;
              MicrosoftTelemetryAssertTriggeredNoArgs();
              break;
            }
            v20 = v27;
            v19 = v25 - 1;
            ++v4;
            --v25;
            *v27 = a2;
            v8 = v20 + 1;
            v27 = v8;
            v18 = v8;
            *v8 = 0;
            if ( v4 >= plUbound )
              goto LABEL_21;
          }
        }
        else
        {
LABEL_21:
          if ( a2 )
          {
            if ( v8 )
            {
              *v8 = a2;
            }
            else
            {
              if ( v18 != v7 )
                MicrosoftTelemetryAssertTriggeredNoArgs();
              *v18 = a2;
            }
          }
          v22 = v28;
          if ( v7[v28] )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          *a3 = v7;
          v7 = 0;
          if ( a4 )
          {
            if ( !v16 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            *a4 = v22;
          }
        }
        v6 = psa;
      }
      else
      {
        UBound = -2147024882;
      }
    }
  }
LABEL_26:
  LocalFree(v7);
  if ( ppvData )
    SafeArrayUnaccessData(v6);
  return (unsigned int)UBound;
}

```

## disassembly

```asm
0x180002530  mov     rax, rsp
0x180002533  mov     [rax+10h], rbx
0x180002537  mov     [rax+20h], r9
0x18000253b  mov     [rax+18h], r8
0x18000253f  mov     [rax+8], rcx
0x180002543  push    rbp
0x180002544  push    rsi
0x180002545  push    rdi
0x180002546  push    r12
0x180002548  push    r13
0x18000254a  push    r14
0x18000254c  push    r15
0x18000254e  mov     rbp, rsp
0x180002551  sub     rsp, 60h
0x180002555  xor     r13d, r13d
0x180002558  mov     rax, r8
0x18000255b  mov     [rbp+plUbound], r13d
0x18000255f  movzx   r12d, dx
0x180002563  mov     [rbp+ppvData], r13
0x180002567  mov     r14, rcx
0x18000256a  mov     [rbp+var_18], r13
0x18000256e  mov     edi, r13d
0x180002571  mov     esi, r13d
0x180002574  test    rcx, rcx
0x180002577  jnz     short loc_180002583
0x180002579  mov     ebx, 80070057h
0x18000257e  jmp     loc_180002706
0x180002583  test    rax, rax
0x180002586  jz      short loc_180002579
0x180002588  lea     rdx, [rbp+ppvData]; ppvData
0x18000258c  call    cs:__imp_SafeArrayAccessData
0x180002592  mov     ebx, eax
0x180002594  test    eax, eax
0x180002596  js      loc_180002706
0x18000259c  cmp     [rbp+ppvData], r13
0x1800025a0  jz      short loc_180002579
0x1800025a2  lea     r8, [rbp+plUbound]; plUbound
0x1800025a6  mov     edx, 1; nDim
0x1800025ab  mov     rcx, r14; psa
0x1800025ae  call    cs:__imp_SafeArrayGetUBound
0x1800025b4  mov     ebx, eax
0x1800025b6  test    eax, eax
0x1800025b8  js      loc_180002706
0x1800025be  mov     edx, [rbp+plUbound]
0x1800025c1  mov     r11d, r13d
0x1800025c4  add     edx, 1
0x1800025c7  mov     r9d, r13d
0x1800025ca  mov     [rbp+plUbound], edx
0x1800025cd  jz      short loc_180002630
0x1800025cf  mov     r15, [rbp+ppvData]
0x1800025d3  mov     eax, r9d
0x1800025d6  mov     rcx, [r15+rax*8]
0x1800025da  test    rcx, rcx
0x1800025dd  jz      short loc_180002579
0x1800025df  mov     r8d, 7FFFFFFFh
0x1800025e5  cmp     [rcx], r13w
0x1800025e9  jz      short loc_1800025F5
0x1800025eb  add     rcx, 2
0x1800025ef  sub     r8, 1
0x1800025f3  jnz     short loc_1800025E5
0x1800025f5  mov     rax, r8
0x1800025f8  mov     ecx, 7FFFFFFFh
0x1800025fd  neg     rax
0x180002600  mov     rax, r8
0x180002603  sbb     ebx, ebx
0x180002605  sub     rcx, r8
0x180002608  not     ebx
0x18000260a  and     ebx, 80070057h
0x180002610  neg     rax
0x180002613  sbb     r10, r10
0x180002616  and     r10, rcx
0x180002619  test    r8, r8
0x18000261c  jz      loc_180002706
0x180002622  inc     r11d
0x180002625  inc     r9d
0x180002628  add     r11d, r10d
0x18000262b  cmp     r9d, edx
0x18000262e  jb      short loc_1800025D3
0x180002630  cmp     r13w, r12w
0x180002634  mov     ecx, r13d
0x180002637  setnz   cl
0x18000263a  lea     r15d, [rcx+1]
0x18000263e  add     r15d, r11d
0x180002641  js      loc_180002778
0x180002647  lea     edx, [r15+r15]; uBytes
0x18000264b  xor     ecx, ecx; uFlags
0x18000264d  call    cs:__imp_LocalAlloc
0x180002653  mov     rdi, rax
0x180002656  test    rax, rax
0x180002659  jnz     short loc_180002665
0x18000265b  mov     ebx, 8007000Eh
0x180002660  jmp     loc_180002706
0x180002665  mov     [rax], r13w
0x180002669  mov     r14, rdi
0x18000266c  lea     eax, [r15-1]
0x180002670  mov     ecx, eax
0x180002672  mov     [rbp+var_10], rcx
0x180002676  mov     ecx, r15d
0x180002679  mov     [rdi+rax*2], r13w
0x18000267e  mov     [rbp+var_28], rcx
0x180002682  cmp     [rbp+plUbound], esi
0x180002685  jbe     short loc_1800026E1
0x180002687  mov     r8, [rbp+ppvData]
0x18000268b  lea     rdx, [rbp+var_28]
0x18000268f  mov     eax, r13d
0x180002692  lea     r9, [rbp+var_18]; unsigned __int16 **
0x180002696  mov     [rsp+60h+var_40], rdx; unsigned __int64 *
0x18000269b  mov     rdx, rcx; unsigned __int64
0x18000269e  mov     rcx, r14; unsigned __int16 *
0x1800026a1  mov     r8, [r8+rax*8]; unsigned __int16 *
0x1800026a5  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800026aa  mov     ebx, eax
0x1800026ac  test    eax, eax
0x1800026ae  js      short loc_1800026FF
0x1800026b0  mov     rcx, [rbp+var_28]
0x1800026b4  test    rcx, rcx
0x1800026b7  jz      short loc_1800026F5
0x1800026b9  mov     rsi, [rbp+var_18]
0x1800026bd  xor     eax, eax
0x1800026bf  dec     rcx
0x1800026c2  inc     r13d
0x1800026c5  mov     [rbp+var_28], rcx
0x1800026c9  mov     [rsi], r12w
0x1800026cd  add     rsi, 2
0x1800026d1  mov     [rbp+var_18], rsi
0x1800026d5  mov     r14, rsi
0x1800026d8  mov     [rsi], ax
0x1800026db  cmp     r13d, [rbp+plUbound]
0x1800026df  jb      short loc_180002687
0x1800026e1  xor     r13d, r13d
0x1800026e4  cmp     r13w, r12w
0x1800026e8  jz      short loc_180002746
0x1800026ea  test    rsi, rsi
0x1800026ed  jz      short loc_180002738
0x1800026ef  mov     [rsi], r12w
0x1800026f3  jmp     short loc_180002746
0x1800026f5  mov     ebx, 80004005h
0x1800026fa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800026ff  xor     r13d, r13d
0x180002702  mov     r14, [rbp+arg_0]
0x180002706  mov     rcx, rdi; hMem
0x180002709  call    cs:__imp_LocalFree
0x18000270f  cmp     [rbp+ppvData], r13
0x180002713  jz      short loc_18000271E
0x180002715  mov     rcx, r14; psa
0x180002718  call    cs:__imp_SafeArrayUnaccessData
0x18000271e  mov     eax, ebx
0x180002720  mov     rbx, [rsp+60h+arg_8]
0x180002728  add     rsp, 60h
0x18000272c  pop     r15
0x18000272e  pop     r14
0x180002730  pop     r13
0x180002732  pop     r12
0x180002734  pop     rdi
0x180002735  pop     rsi
0x180002736  pop     rbp
0x180002737  retn
0x180002738  cmp     r14, rdi
0x18000273b  jz      short loc_180002742
0x18000273d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002742  mov     [r14], r12w
0x180002746  mov     rsi, [rbp+var_10]
0x18000274a  cmp     r13w, [rdi+rsi*2]
0x18000274f  jz      short loc_180002756
0x180002751  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002756  mov     rax, [rbp+arg_10]
0x18000275a  mov     r14, [rbp+arg_18]
0x18000275e  mov     [rax], rdi
0x180002761  mov     rdi, r13
0x180002764  test    r14, r14
0x180002767  jz      short loc_180002702
0x180002769  test    r15d, r15d
0x18000276c  jnz     short loc_180002773
0x18000276e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002773  mov     [r14], rsi
0x180002776  jmp     short loc_180002702
0x180002778  mov     ebx, 80004005h
0x18000277d  jmp     short loc_180002706
```
