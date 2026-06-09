# CHandlerItemInfo::_LoadRequiredData(ISyncMgrHandler *)

- ea: `0x180003480`
- end: `0x18000384c`
- name: `?_LoadRequiredData@CHandlerItemInfo@@AEAAJPEAUISyncMgrHandler@@@Z`
- size: `972`
- prototype: `__int64 __fastcall(CHandlerItemInfo *__hidden this, struct ISyncMgrHandler *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007964`

## callees

- `0x180003480`
- `0x18000b5f0`
- `0x18001c614`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003826`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003826`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003507`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003507`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003836`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003836`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180003521`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180003521`

## pseudocode

```c
__int64 __fastcall CHandlerItemInfo::_LoadRequiredData(CHandlerItemInfo *this, struct ISyncMgrHandler *a2)
{
  struct ISyncMgrHandlerVtbl *lpVtbl; // rax
  __int64 result; // rax
  struct ISyncMgrHandlerVtbl *v6; // rax
  int v7; // ebx
  struct ISyncMgrHandlerVtbl *v8; // rax
  char v9; // bp
  int v10; // edx
  int v11; // esi
  int v12; // eax
  int v13; // [rsp+58h] [rbp+10h] BYREF
  int v14; // [rsp+60h] [rbp+18h] BYREF
  LPCWSTR lpString1; // [rsp+68h] [rbp+20h] BYREF

  lpVtbl = a2->lpVtbl;
  lpString1 = 0;
  result = ((__int64 (__fastcall *)(struct ISyncMgrHandler *, LPCWSTR *))lpVtbl->GetName)(a2, &lpString1);
  if ( (int)result >= 0 )
  {
    v6 = a2->lpVtbl;
    v13 = 0;
    v7 = ((__int64 (__fastcall *)(struct ISyncMgrHandler *, int *))v6->GetCapabilities)(a2, &v13);
    if ( v7 >= 0 )
    {
      v8 = a2->lpVtbl;
      v14 = 0;
      v7 = ((__int64 (__fastcall *)(struct ISyncMgrHandler *, int *))v8->GetPolicies)(a2, &v14);
      if ( v7 >= 0 )
      {
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 3));
        v9 = 0;
        if ( lpString1 && lstrcmpW(lpString1, (LPCWSTR)this + 166) )
        {
          v9 = 1;
          CItemInfo::SetName(this, lpString1);
        }
        v10 = v13;
        v11 = *((_DWORD *)this + 212);
        *((_BYTE *)this + 1974) = 0;
        if ( (v10 & 0x10) != 0 )
          *((_BYTE *)this + 1974) = 1;
        v12 = v11 & 0x400000 | 0xCF0;
        if ( (v10 & 0xF30017) == v10 && (v14 & 0x12F3F) == v14 )
        {
          v7 = 0;
          if ( (v10 & dword_18006FF00) != 0 )
            v12 |= dword_18006FF04;
          if ( (v10 & dword_18006FF08) != 0 )
            v12 |= dword_18006FF0C;
          if ( (v10 & dword_18006FF10) != 0 )
            v12 |= dword_18006FF14;
          if ( (v10 & dword_18006FF18) != 0 )
            v12 |= dword_18006FF1C;
          if ( (v10 & dword_18006FF20) != 0 )
            v12 |= dword_18006FF24;
          if ( (v10 & dword_18006FF28) != 0 )
            v12 |= dword_18006FF2C;
          if ( (v10 & dword_18006FF30) != 0 )
            v12 |= dword_18006FF34;
          if ( (v10 & dword_18006FF38) != 0 )
            v12 |= dword_18006FF3C;
          if ( (v10 & dword_18006FF40) != 0 )
            v12 |= dword_18006FF44;
          if ( (v14 & dword_18006FE60) != 0 )
          {
            if ( byte_18006FE68 == 1 )
              v12 |= dword_18006FE64;
            else
              v12 &= ~dword_18006FE64;
          }
          if ( (v14 & dword_18006FE6C) != 0 )
          {
            if ( byte_18006FE74 == 1 )
              v12 |= dword_18006FE70;
            else
              v12 &= ~dword_18006FE70;
          }
          if ( (v14 & dword_18006FE78) != 0 )
          {
            if ( byte_18006FE80 == 1 )
              v12 |= dword_18006FE7C;
            else
              v12 &= ~dword_18006FE7C;
          }
          if ( (v14 & dword_18006FE84) != 0 )
          {
            if ( byte_18006FE8C == 1 )
              v12 |= dword_18006FE88;
            else
              v12 &= ~dword_18006FE88;
          }
          if ( (v14 & dword_18006FE90) != 0 )
          {
            if ( byte_18006FE98 == 1 )
              v12 |= dword_18006FE94;
            else
              v12 &= ~dword_18006FE94;
          }
          if ( (v14 & dword_18006FE9C) != 0 )
          {
            if ( byte_18006FEA4 == 1 )
              v12 |= dword_18006FEA0;
            else
              v12 &= ~dword_18006FEA0;
          }
          if ( (v14 & dword_18006FEA8) != 0 )
          {
            if ( byte_18006FEB0 == 1 )
              v12 |= dword_18006FEAC;
            else
              v12 &= ~dword_18006FEAC;
          }
          if ( (v14 & dword_18006FEB4) != 0 )
          {
            if ( byte_18006FEBC == 1 )
              v12 |= dword_18006FEB8;
            else
              v12 &= ~dword_18006FEB8;
          }
          if ( (v14 & dword_18006FEC0) != 0 )
          {
            if ( byte_18006FEC8 == 1 )
              v12 |= dword_18006FEC4;
            else
              v12 &= ~dword_18006FEC4;
          }
          if ( (v14 & dword_18006FECC) != 0 )
          {
            if ( byte_18006FED4 == 1 )
              v12 |= dword_18006FED0;
            else
              v12 &= ~dword_18006FED0;
          }
          if ( (v14 & dword_18006FED8) != 0 )
          {
            if ( byte_18006FEE0 == 1 )
              v12 |= dword_18006FEDC;
            else
              v12 &= ~dword_18006FEDC;
          }
          if ( (v14 & dword_18006FEE4) != 0 )
          {
            if ( byte_18006FEEC == 1 )
              v12 |= dword_18006FEE8;
            else
              v12 &= ~dword_18006FEE8;
          }
          if ( (v14 & dword_18006FEF0) != 0 )
          {
            if ( byte_18006FEF8 == 1 )
              v12 |= dword_18006FEF4;
            else
              v12 &= ~dword_18006FEF4;
          }
        }
        else
        {
          v7 = -2147024809;
        }
        if ( v11 != v12 )
        {
          *((_DWORD *)this + 212) = v12;
          CItemState::MarkChangeState((char *)this + 8, 2);
        }
        if ( v7 >= 0 && v11 != *((_DWORD *)this + 212) || v9 == 1 )
          CItemState::MarkChangeState((char *)this + 8, 2);
        LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 3));
      }
    }
    CoTaskMemFree((LPVOID)lpString1);
    return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x180003480  push    rsi
0x180003482  push    rdi
0x180003483  push    r14
0x180003485  sub     rsp, 30h
0x180003489  mov     rax, [rdx]
0x18000348c  mov     rsi, rdx
0x18000348f  mov     rdi, rcx
0x180003492  lea     rdx, [rsp+48h+lpString1]
0x180003497  xor     r14d, r14d
0x18000349a  mov     rcx, rsi
0x18000349d  mov     [rsp+48h+lpString1], r14
0x1800034a2  mov     rax, [rax+18h]
0x1800034a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ab  test    eax, eax
0x1800034ad  js      loc_180003843
0x1800034b3  mov     rax, [rsi]
0x1800034b6  lea     rdx, [rsp+48h+arg_8]
0x1800034bb  mov     rcx, rsi
0x1800034be  mov     [rsp+48h+var_20], rbx
0x1800034c3  mov     [rsp+48h+arg_8], r14d
0x1800034c8  mov     rax, [rax+30h]
0x1800034cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d1  mov     ebx, eax
0x1800034d3  test    eax, eax
0x1800034d5  js      loc_180003831
0x1800034db  mov     rax, [rsi]
0x1800034de  lea     rdx, [rsp+48h+arg_10]
0x1800034e3  mov     rcx, rsi
0x1800034e6  mov     [rsp+48h+arg_10], r14d
0x1800034eb  mov     rax, [rax+38h]
0x1800034ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034f4  mov     ebx, eax
0x1800034f6  test    eax, eax
0x1800034f8  js      loc_180003831
0x1800034fe  mov     rcx, [rdi+18h]; lpCriticalSection
0x180003502  mov     [rsp+48h+var_28], rbp
0x180003507  call    cs:__imp_EnterCriticalSection
0x18000350d  mov     rcx, [rsp+48h+lpString1]; lpString1
0x180003512  xor     bpl, bpl
0x180003515  test    rcx, rcx
0x180003518  jz      short loc_18000353B
0x18000351a  lea     rdx, [rdi+14Ch]; lpString2
0x180003521  call    cs:__imp_lstrcmpW
0x180003527  test    eax, eax
0x180003529  jz      short loc_18000353B
0x18000352b  mov     rdx, [rsp+48h+lpString1]; unsigned __int16 *
0x180003530  mov     rcx, rdi; this
0x180003533  mov     bpl, 1
0x180003536  call    ?SetName@CItemInfo@@IEAAJPEBG@Z; CItemInfo::SetName(ushort const *)
0x18000353b  mov     edx, [rsp+48h+arg_8]
0x18000353f  mov     esi, [rdi+350h]
0x180003545  mov     [rdi+7B6h], r14b
0x18000354c  test    dl, 10h
0x18000354f  jz      short loc_180003558
0x180003551  mov     byte ptr [rdi+7B6h], 1
0x180003558  mov     eax, esi
0x18000355a  mov     ecx, edx
0x18000355c  and     eax, 400000h
0x180003561  and     ecx, 0F30017h
0x180003567  or      eax, 0CF0h
0x18000356c  cmp     ecx, edx
0x18000356e  jnz     loc_1800037E5
0x180003574  mov     r8d, [rsp+48h+arg_10]
0x180003579  mov     ecx, r8d
0x18000357c  and     ecx, 12F3Fh
0x180003582  cmp     ecx, r8d
0x180003585  jnz     loc_1800037E5
0x18000358b  mov     ecx, eax
0x18000358d  mov     ebx, r14d
0x180003590  or      ecx, cs:dword_18006FF04
0x180003596  test    cs:dword_18006FF00, edx
0x18000359c  cmovnz  eax, ecx
0x18000359f  test    cs:dword_18006FF08, edx
0x1800035a5  jz      short loc_1800035AD
0x1800035a7  or      eax, cs:dword_18006FF0C
0x1800035ad  test    cs:dword_18006FF10, edx
0x1800035b3  jz      short loc_1800035BB
0x1800035b5  or      eax, cs:dword_18006FF14
0x1800035bb  test    cs:dword_18006FF18, edx
0x1800035c1  jz      short loc_1800035C9
0x1800035c3  or      eax, cs:dword_18006FF1C
0x1800035c9  test    cs:dword_18006FF20, edx
0x1800035cf  jz      short loc_1800035D7
0x1800035d1  or      eax, cs:dword_18006FF24
0x1800035d7  test    cs:dword_18006FF28, edx
0x1800035dd  jz      short loc_1800035E5
0x1800035df  or      eax, cs:dword_18006FF2C
0x1800035e5  test    cs:dword_18006FF30, edx
0x1800035eb  jz      short loc_1800035F3
0x1800035ed  or      eax, cs:dword_18006FF34
0x1800035f3  test    cs:dword_18006FF38, edx
0x1800035f9  jz      short loc_180003601
0x1800035fb  or      eax, cs:dword_18006FF3C
0x180003601  test    cs:dword_18006FF40, edx
0x180003607  jz      short loc_18000360F
0x180003609  or      eax, cs:dword_18006FF44
0x18000360f  test    cs:dword_18006FE60, r8d
0x180003616  jz      short loc_180003633
0x180003618  cmp     cs:byte_18006FE68, 1
0x18000361f  jnz     short loc_180003629
0x180003621  or      eax, cs:dword_18006FE64
0x180003627  jmp     short loc_180003633
0x180003629  mov     ecx, cs:dword_18006FE64
0x18000362f  not     ecx
0x180003631  and     eax, ecx
0x180003633  test    cs:dword_18006FE6C, r8d
0x18000363a  jz      short loc_180003657
0x18000363c  cmp     cs:byte_18006FE74, 1
0x180003643  jnz     short loc_18000364D
0x180003645  or      eax, cs:dword_18006FE70
0x18000364b  jmp     short loc_180003657
0x18000364d  mov     ecx, cs:dword_18006FE70
0x180003653  not     ecx
0x180003655  and     eax, ecx
0x180003657  test    cs:dword_18006FE78, r8d
0x18000365e  jz      short loc_18000367B
0x180003660  cmp     cs:byte_18006FE80, 1
0x180003667  jnz     short loc_180003671
0x180003669  or      eax, cs:dword_18006FE7C
0x18000366f  jmp     short loc_18000367B
0x180003671  mov     ecx, cs:dword_18006FE7C
0x180003677  not     ecx
0x180003679  and     eax, ecx
0x18000367b  test    cs:dword_18006FE84, r8d
0x180003682  jz      short loc_18000369F
0x180003684  cmp     cs:byte_18006FE8C, 1
0x18000368b  jnz     short loc_180003695
0x18000368d  or      eax, cs:dword_18006FE88
0x180003693  jmp     short loc_18000369F
0x180003695  mov     ecx, cs:dword_18006FE88
0x18000369b  not     ecx
0x18000369d  and     eax, ecx
0x18000369f  test    cs:dword_18006FE90, r8d
0x1800036a6  jz      short loc_1800036C3
0x1800036a8  cmp     cs:byte_18006FE98, 1
0x1800036af  jnz     short loc_1800036B9
0x1800036b1  or      eax, cs:dword_18006FE94
0x1800036b7  jmp     short loc_1800036C3
0x1800036b9  mov     ecx, cs:dword_18006FE94
0x1800036bf  not     ecx
0x1800036c1  and     eax, ecx
0x1800036c3  test    cs:dword_18006FE9C, r8d
0x1800036ca  jz      short loc_1800036E7
0x1800036cc  cmp     cs:byte_18006FEA4, 1
0x1800036d3  jnz     short loc_1800036DD
0x1800036d5  or      eax, cs:dword_18006FEA0
0x1800036db  jmp     short loc_1800036E7
0x1800036dd  mov     ecx, cs:dword_18006FEA0
0x1800036e3  not     ecx
0x1800036e5  and     eax, ecx
0x1800036e7  test    cs:dword_18006FEA8, r8d
0x1800036ee  jz      short loc_18000370B
0x1800036f0  cmp     cs:byte_18006FEB0, 1
0x1800036f7  jnz     short loc_180003701
0x1800036f9  or      eax, cs:dword_18006FEAC
0x1800036ff  jmp     short loc_18000370B
0x180003701  mov     ecx, cs:dword_18006FEAC
0x180003707  not     ecx
0x180003709  and     eax, ecx
0x18000370b  test    cs:dword_18006FEB4, r8d
0x180003712  jz      short loc_18000372F
0x180003714  cmp     cs:byte_18006FEBC, 1
0x18000371b  jnz     short loc_180003725
0x18000371d  or      eax, cs:dword_18006FEB8
0x180003723  jmp     short loc_18000372F
0x180003725  mov     ecx, cs:dword_18006FEB8
0x18000372b  not     ecx
0x18000372d  and     eax, ecx
0x18000372f  test    cs:dword_18006FEC0, r8d
0x180003736  jz      short loc_180003753
0x180003738  cmp     cs:byte_18006FEC8, 1
0x18000373f  jnz     short loc_180003749
0x180003741  or      eax, cs:dword_18006FEC4
0x180003747  jmp     short loc_180003753
0x180003749  mov     ecx, cs:dword_18006FEC4
0x18000374f  not     ecx
0x180003751  and     eax, ecx
0x180003753  test    cs:dword_18006FECC, r8d
0x18000375a  jz      short loc_180003777
0x18000375c  cmp     cs:byte_18006FED4, 1
0x180003763  jnz     short loc_18000376D
0x180003765  or      eax, cs:dword_18006FED0
0x18000376b  jmp     short loc_180003777
0x18000376d  mov     ecx, cs:dword_18006FED0
0x180003773  not     ecx
0x180003775  and     eax, ecx
0x180003777  test    cs:dword_18006FED8, r8d
0x18000377e  jz      short loc_18000379B
0x180003780  cmp     cs:byte_18006FEE0, 1
0x180003787  jnz     short loc_180003791
0x180003789  or      eax, cs:dword_18006FEDC
0x18000378f  jmp     short loc_18000379B
0x180003791  mov     ecx, cs:dword_18006FEDC
0x180003797  not     ecx
0x180003799  and     eax, ecx
0x18000379b  test    cs:dword_18006FEE4, r8d
0x1800037a2  jz      short loc_1800037BF
0x1800037a4  cmp     cs:byte_18006FEEC, 1
0x1800037ab  jnz     short loc_1800037B5
0x1800037ad  or      eax, cs:dword_18006FEE8
0x1800037b3  jmp     short loc_1800037BF
0x1800037b5  mov     ecx, cs:dword_18006FEE8
0x1800037bb  not     ecx
0x1800037bd  and     eax, ecx
0x1800037bf  test    cs:dword_18006FEF0, r8d
0x1800037c6  jz      short loc_1800037EA
0x1800037c8  cmp     cs:byte_18006FEF8, 1
0x1800037cf  jnz     short loc_1800037D9
0x1800037d1  or      eax, cs:dword_18006FEF4
0x1800037d7  jmp     short loc_1800037EA
0x1800037d9  mov     ecx, cs:dword_18006FEF4
0x1800037df  not     ecx
0x1800037e1  and     eax, ecx
0x1800037e3  jmp     short loc_1800037EA
0x1800037e5  mov     ebx, 80070057h
0x1800037ea  cmp     esi, eax
0x1800037ec  jz      short loc_180003802
0x1800037ee  mov     edx, 2
0x1800037f3  mov     [rdi+350h], eax
0x1800037f9  lea     rcx, [rdi+8]
0x1800037fd  call    ?MarkChangeState@CItemState@@QEAAJW4SYNCMGR_INVALIDATE_REASON@@@Z; CItemState::MarkChangeState(SYNCMGR_INVALIDATE_REASON)
0x180003802  test    ebx, ebx
0x180003804  js      short loc_18000380E
0x180003806  cmp     esi, [rdi+350h]
0x18000380c  jnz     short loc_180003814
0x18000380e  cmp     bpl, 1
0x180003812  jnz     short loc_180003822
0x180003814  mov     edx, 2
0x180003819  lea     rcx, [rdi+8]
0x18000381d  call    ?MarkChangeState@CItemState@@QEAAJW4SYNCMGR_INVALIDATE_REASON@@@Z; CItemState::MarkChangeState(SYNCMGR_INVALIDATE_REASON)
0x180003822  mov     rcx, [rdi+18h]; lpCriticalSection
0x180003826  call    cs:__imp_LeaveCriticalSection
0x18000382c  mov     rbp, [rsp+48h+var_28]
0x180003831  mov     rcx, [rsp+48h+lpString1]; pv
0x180003836  call    cs:__imp_CoTaskMemFree
0x18000383c  mov     eax, ebx
0x18000383e  mov     rbx, [rsp+48h+var_20]
0x180003843  add     rsp, 30h
0x180003847  pop     r14
0x180003849  pop     rdi
0x18000384a  pop     rsi
0x18000384b  retn
```
