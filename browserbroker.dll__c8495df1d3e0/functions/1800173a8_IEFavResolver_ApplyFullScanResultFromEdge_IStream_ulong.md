# IEFavResolver::ApplyFullScanResultFromEdge(IStream *,ulong)

- ea: `0x1800173a8`
- end: `0x1800174ff`
- name: `?ApplyFullScanResultFromEdge@IEFavResolver@@AEAAJPEAUIStream@@K@Z`
- size: `343`
- prototype: `__int64 __fastcall(WCHAR *this, struct IStream *pstm, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019b8c`

## callees

- `0x1800164d0`
- `0x180016580`
- `0x180016a9c`
- `0x1800173a8`
- `0x180024f94`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180017435`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180017435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800174b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800174bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800174c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800174b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800174bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800174c6`

## pseudocode

```c
__int64 __fastcall IEFavResolver::ApplyFullScanResultFromEdge(WCHAR *this, struct IStream *pstm, unsigned int a3)
{
  int StrIE; // ebx
  unsigned int v4; // r14d
  int v5; // edi
  unsigned __int16 *v10; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int16 *v11; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v12[3]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int16 *v13; // [rsp+60h] [rbp-10h] BYREF
  int pv; // [rsp+B8h] [rbp+48h] BYREF

  StrIE = 0;
  v4 = 0;
  v5 = 0;
  pv = 0;
  do
  {
    if ( v4 >= a3 )
      break;
    v12[0] = 0;
    ++v4;
    StrIE = IStream_ReadStrIE(pstm, v12);
    if ( StrIE >= 0 )
    {
      v11 = 0;
      StrIE = IStream_ReadStrIE(pstm, &v11);
      if ( StrIE >= 0 )
      {
        pv = 0;
        StrIE = IStream_Read(pstm, &pv, 4u);
        if ( StrIE >= 0 )
        {
          v10 = 0;
          StrIE = IStream_ReadStrIE(pstm, &v10);
          if ( StrIE >= 0 )
          {
            v12[1] = v10;
            v13 = v11;
            v12[2] = v12[0];
            StrIE = IEFavResolver::AddFavorite(this, v11, v10, v12[0], pv, 1);
            BrowserTelemetry::HandleFullScanItemFromEdge<unsigned short const * &,unsigned short * &,unsigned short const * &,long &>((__int64)&v13);
            if ( StrIE < 0 )
              StrIE = 0;
            else
              ++v5;
          }
          CoTaskMemFree(v10);
        }
      }
      CoTaskMemFree(v11);
    }
    CoTaskMemFree(v12[0]);
  }
  while ( StrIE >= 0 );
  pv = v5;
  BrowserTelemetry::HandleFullScanFromEdge<unsigned long &,unsigned long &>((__int64)&pv);
  return (unsigned int)StrIE;
}

```

## disassembly

```asm
0x1800173a8  mov     [rsp-28h+arg_0], rbx
0x1800173ad  mov     [rsp-28h+arg_8], rsi
0x1800173b2  mov     [rsp-28h+arg_10], r8d
0x1800173b7  push    rbp
0x1800173b8  push    rdi
0x1800173b9  push    r12
0x1800173bb  push    r14
0x1800173bd  push    r15
0x1800173bf  mov     rbp, rsp
0x1800173c2  sub     rsp, 70h
0x1800173c6  xor     ebx, ebx
0x1800173c8  xor     r14d, r14d
0x1800173cb  xor     edi, edi
0x1800173cd  mov     r15d, r8d
0x1800173d0  mov     [rbp+pv], edi
0x1800173d3  mov     rsi, rdx
0x1800173d6  mov     r12, rcx
0x1800173d9  cmp     r14d, r15d
0x1800173dc  jnb     loc_1800174D4
0x1800173e2  lea     rdx, [rbp+var_28]
0x1800173e6  mov     [rbp+var_28], 0
0x1800173ee  mov     rcx, rsi
0x1800173f1  inc     r14d
0x1800173f4  call    IStream_ReadStrIE
0x1800173f9  mov     ebx, eax
0x1800173fb  test    eax, eax
0x1800173fd  js      loc_1800174C2
0x180017403  lea     rdx, [rbp+var_30]
0x180017407  mov     [rbp+var_30], 0
0x18001740f  mov     rcx, rsi
0x180017412  call    IStream_ReadStrIE
0x180017417  mov     ebx, eax
0x180017419  test    eax, eax
0x18001741b  js      loc_1800174B8
0x180017421  mov     r8d, 4; cb
0x180017427  mov     [rbp+pv], 0
0x18001742e  lea     rdx, [rbp+pv]; pv
0x180017432  mov     rcx, rsi; pstm
0x180017435  call    cs:__imp_IStream_Read
0x18001743b  mov     ebx, eax
0x18001743d  test    eax, eax
0x18001743f  js      short loc_1800174B8
0x180017441  lea     rdx, [rbp+var_38]
0x180017445  mov     [rbp+var_38], 0
0x18001744d  mov     rcx, rsi
0x180017450  call    IStream_ReadStrIE
0x180017455  mov     ebx, eax
0x180017457  test    eax, eax
0x180017459  js      short loc_1800174AE
0x18001745b  mov     r8, [rbp+var_38]; unsigned __int16 *
0x18001745f  mov     rcx, r12; this
0x180017462  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x180017466  mov     r9, [rbp+var_28]; unsigned __int16 *
0x18001746a  mov     eax, [rbp+pv]
0x18001746d  mov     [rsp+70h+var_48], 1; int
0x180017475  mov     [rbp+var_20], r8
0x180017479  mov     [rbp+var_10], rdx
0x18001747d  mov     [rbp+var_18], r9
0x180017481  mov     [rsp+70h+var_50], eax; int
0x180017485  call    ?AddFavorite@IEFavResolver@@QEAAJPEBG00HH@Z; IEFavResolver::AddFavorite(ushort const *,ushort const *,ushort const *,int,int)
0x18001748a  lea     r9, [rbp+var_40]
0x18001748e  mov     [rbp+var_40], eax
0x180017491  lea     r8, [rbp+var_20]
0x180017495  mov     ebx, eax
0x180017497  lea     rdx, [rbp+var_18]
0x18001749b  lea     rcx, [rbp+var_10]
0x18001749f  call    ??$HandleFullScanItemFromEdge@AEAPEBGAEAPEAGAEAPEBGAEAJ@BrowserTelemetry@@SAXAEAPEBGAEAPEAG0AEAJ@Z; BrowserTelemetry::HandleFullScanItemFromEdge<ushort const * &,ushort * &,ushort const * &,long &>(ushort const * &,ushort * &,ushort const * &,long &)
0x1800174a4  test    ebx, ebx
0x1800174a6  js      short loc_1800174AC
0x1800174a8  inc     edi
0x1800174aa  jmp     short loc_1800174AE
0x1800174ac  xor     ebx, ebx
0x1800174ae  mov     rcx, [rbp+var_38]; pv
0x1800174b2  call    cs:__imp_CoTaskMemFree
0x1800174b8  mov     rcx, [rbp+var_30]; pv
0x1800174bc  call    cs:__imp_CoTaskMemFree
0x1800174c2  mov     rcx, [rbp+var_28]; pv
0x1800174c6  call    cs:__imp_CoTaskMemFree
0x1800174cc  test    ebx, ebx
0x1800174ce  jns     loc_1800173D9
0x1800174d4  lea     rdx, [rbp+arg_10]
0x1800174d8  mov     [rbp+pv], edi
0x1800174db  lea     rcx, [rbp+pv]
0x1800174df  call    ??$HandleFullScanFromEdge@AEAKAEAK@BrowserTelemetry@@SAXAEAK0@Z; BrowserTelemetry::HandleFullScanFromEdge<ulong &,ulong &>(ulong &,ulong &)
0x1800174e4  lea     r11, [rsp+70h+var_s0]
0x1800174e9  mov     eax, ebx
0x1800174eb  mov     rbx, [r11+30h]
0x1800174ef  mov     rsi, [r11+38h]
0x1800174f3  mov     rsp, r11
0x1800174f6  pop     r15
0x1800174f8  pop     r14
0x1800174fa  pop     r12
0x1800174fc  pop     rdi
0x1800174fd  pop     rbp
0x1800174fe  retn
```
