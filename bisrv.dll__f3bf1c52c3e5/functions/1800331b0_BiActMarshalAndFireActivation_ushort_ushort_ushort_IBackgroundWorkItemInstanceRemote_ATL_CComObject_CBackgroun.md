# BiActMarshalAndFireActivation(ushort *,ushort *,ushort *,IBackgroundWorkItemInstanceRemote *,ATL::CComObject<CBackgroundWorkItemInstanceRemote> *,IBackgroundActivationSessionManagerEvents *,ulong,unsigned __int64,unsigned __int64)

- ea: `0x1800331b0`
- end: `0x180033552`
- name: `?BiActMarshalAndFireActivation@@YAJPEAG00PEAUIBackgroundWorkItemInstanceRemote@@PEAV?$CComObject@VCBackgroundWorkItemInstanceRemote@@@ATL@@PEAUIBackgroundActivationSessionManagerEvents@@K_K4@Z`
- size: `930`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005312c`

## callees

- `0x1800331b0`
- `0x180049844`
- `0x18004de10`
- `0x18004df58`
- `0x180095010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180033387`
- `ntdll!RtlFreeHeap` at `0x180033387`
- `ntdll!RtlAllocateHeap` at `0x1800332e1`
- `ntdll!RtlAllocateHeap` at `0x1800332e1`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18003322b`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18003322b`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800331ff`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800331ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033254`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033254`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033275`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033275`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003325a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003325a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800331d0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800331d0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180033465`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180033465`

## pseudocode

```c
__int64 __fastcall BiActMarshalAndFireActivation(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        IUnknown *a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        __int64 a9)
{
  HGLOBAL v13; // rax
  void *v14; // rbx
  HRESULT v15; // eax
  unsigned int v16; // edi
  HRESULT v17; // eax
  LPSTREAM v18; // rbx
  int v19; // eax
  PVOID Heap; // rax
  void *v21; // rbx
  int v22; // eax
  int v23; // eax
  _QWORD *v25; // rcx
  int v26; // [rsp+50h] [rbp-58h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp-50h] BYREF
  SIZE_T Size[9]; // [rsp+60h] [rbp-48h] BYREF

  v13 = GlobalAlloc(2u, 0);
  v14 = v13;
  if ( v13 )
  {
    ppstm = 0;
    v15 = CreateStreamOnHGlobal(v13, 1, &ppstm);
    v16 = v15;
    if ( v15 < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids,
          (unsigned int)v15);
      GlobalFree(v14);
    }
    else
    {
      v17 = CoMarshalInterface(ppstm, &GUID_0166231b_fd21_4e33_a713_75eb3207a138, a4, 0, 0, 0);
      v16 = v17;
      if ( v17 >= 0 )
      {
        v18 = ppstm;
        Size[0] = 0;
        AcquireSRWLockExclusive((PSRWLOCK)(a5 + 160));
        GetCurrentThreadId();
        *(_QWORD *)(a5 + 168) = v18;
        *(_DWORD *)(a5 + 152) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)(a5 + 160));
        v19 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, __int64, SIZE_T *))(*(_QWORD *)ppstm + 40LL))(
                ppstm,
                0,
                2,
                Size);
        v16 = v19;
        if ( v19 < 0 )
        {
          v25 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            return v16;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_36;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids,
            (unsigned int)v19);
        }
        else
        {
          v16 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
          if ( (v16 & 0x80000000) == 0 )
          {
            v26 = 0;
            Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, LODWORD(Size[0]));
            v21 = Heap;
            if ( Heap )
            {
              v22 = (*(__int64 (__fastcall **)(LPSTREAM, PVOID, _QWORD, int *))(*(_QWORD *)ppstm + 24LL))(
                      ppstm,
                      Heap,
                      LODWORD(Size[0]),
                      &v26);
              v16 = v22;
              if ( v22 < 0 )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    15,
                    WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids,
                    (unsigned int)v22);
              }
              else
              {
                v23 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, int, void *, int, __int64, __int64))(*(_QWORD *)a6 + 24LL))(
                        a6,
                        a1,
                        a2,
                        a3,
                        v26,
                        v21,
                        a7,
                        a8,
                        a9);
                v16 = v23;
                if ( v23 < 0
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    14,
                    (unsigned int)WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids,
                    a1,
                    v23);
                }
              }
              v26 = 0;
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
            }
            else
            {
              v16 = -2147024882;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids);
            }
            return v16;
          }
        }
        v25 = WPP_GLOBAL_Control;
LABEL_36:
        if ( (*((_BYTE *)v25 + 28) & 2) != 0 && *((_BYTE *)v25 + 25) >= 2u )
          WPP_SF_d(v25[2], 17, WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids, v16);
        return v16;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids,
          (unsigned int)v17);
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    }
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids);
    return (unsigned int)-2147024882;
  }
  return v16;
}

```

## disassembly

```asm
0x1800331b0  push    rbx
0x1800331b2  push    rbp
0x1800331b3  push    rsi
0x1800331b4  push    rdi
0x1800331b5  push    r14
0x1800331b7  push    r15
0x1800331b9  sub     rsp, 78h
0x1800331bd  mov     r14, rdx
0x1800331c0  mov     r15, rcx
0x1800331c3  xor     edx, edx; dwBytes
0x1800331c5  mov     ecx, 2; uFlags
0x1800331ca  mov     rsi, r9
0x1800331cd  mov     rbp, r8
0x1800331d0  call    cs:__imp_GlobalAlloc
0x1800331d6  mov     rbx, rax
0x1800331d9  test    rax, rax
0x1800331dc  jz      loc_180033405
0x1800331e2  mov     [rsp+0A8h+arg_0], r12
0x1800331ea  lea     r8, [rsp+0A8h+ppstm]; ppstm
0x1800331ef  xor     r12d, r12d
0x1800331f2  mov     edx, 1; fDeleteOnRelease
0x1800331f7  mov     rcx, rax; hGlobal
0x1800331fa  mov     [rsp+0A8h+ppstm], r12
0x1800331ff  call    cs:__imp_CreateStreamOnHGlobal
0x180033205  mov     edi, eax
0x180033207  test    eax, eax
0x180033209  js      loc_180033437
0x18003320f  mov     rcx, [rsp+0A8h+ppstm]; pStm
0x180033214  lea     rdx, _GUID_0166231b_fd21_4e33_a713_75eb3207a138; riid
0x18003321b  mov     [rsp+0A8h+mshlflags], r12d; mshlflags
0x180033220  xor     r9d, r9d; dwDestContext
0x180033223  mov     r8, rsi; pUnk
0x180033226  mov     [rsp+0A8h+pvDestContext], r12; pvDestContext
0x18003322b  call    cs:__imp_CoMarshalInterface
0x180033231  mov     edi, eax
0x180033233  test    eax, eax
0x180033235  js      loc_180033470
0x18003323b  mov     rdi, [rsp+0A8h+arg_20]
0x180033243  mov     rbx, [rsp+0A8h+ppstm]
0x180033248  mov     [rsp+0A8h+Size], r12
0x18003324d  lea     rcx, [rdi+0A0h]; SRWLock
0x180033254  call    cs:__imp_AcquireSRWLockExclusive
0x18003325a  call    cs:__imp_GetCurrentThreadId
0x180033260  lea     rcx, [rdi+0A0h]; SRWLock
0x180033267  mov     [rdi+0A8h], rbx
0x18003326e  mov     [rdi+98h], r12d
0x180033275  call    cs:__imp_ReleaseSRWLockExclusive
0x18003327b  mov     rcx, [rsp+0A8h+ppstm]
0x180033280  lea     r9, [rsp+0A8h+Size]
0x180033285  mov     r8d, 2
0x18003328b  mov     edx, r12d
0x18003328e  mov     rax, [rcx]
0x180033291  mov     rax, [rax+28h]
0x180033295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003329a  mov     edi, eax
0x18003329c  test    eax, eax
0x18003329e  js      loc_1800334EB
0x1800332a4  mov     rcx, [rsp+0A8h+ppstm]
0x1800332a9  xor     r9d, r9d
0x1800332ac  xor     r8d, r8d
0x1800332af  mov     edx, r12d
0x1800332b2  mov     rax, [rcx]
0x1800332b5  mov     rax, [rax+28h]
0x1800332b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332be  mov     edi, eax
0x1800332c0  test    eax, eax
0x1800332c2  js      loc_18003351A
0x1800332c8  mov     r8d, dword ptr [rsp+0A8h+Size]; Size
0x1800332cd  xor     edx, edx; Flags
0x1800332cf  mov     [rsp+0A8h+var_58], r12d
0x1800332d4  mov     rcx, gs:60h
0x1800332dd  mov     rcx, [rcx+30h]; HeapHandle
0x1800332e1  call    cs:__imp_RtlAllocateHeap
0x1800332e7  mov     rbx, rax
0x1800332ea  test    rax, rax
0x1800332ed  jz      loc_1800334B1
0x1800332f3  mov     rcx, [rsp+0A8h+ppstm]
0x1800332f8  lea     r9, [rsp+0A8h+var_58]
0x1800332fd  mov     r8d, dword ptr [rsp+0A8h+Size]
0x180033302  mov     rdx, rbx
0x180033305  mov     rax, [rcx]
0x180033308  mov     rax, [rax+18h]
0x18003330c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033311  mov     edi, eax
0x180033313  test    eax, eax
0x180033315  js      loc_1800333A4
0x18003331b  mov     rcx, [rsp+0A8h+arg_28]
0x180033323  mov     r9, rbp
0x180033326  mov     rdx, [rsp+0A8h+arg_40]
0x18003332e  mov     r8, r14
0x180033331  mov     [rsp+0A8h+var_68], rdx
0x180033336  mov     rdx, [rsp+0A8h+arg_38]
0x18003333e  mov     rax, [rcx]
0x180033341  mov     [rsp+0A8h+var_70], rdx
0x180033346  mov     edx, [rsp+0A8h+arg_30]
0x18003334d  mov     [rsp+0A8h+var_78], edx
0x180033351  mov     edx, [rsp+0A8h+var_58]
0x180033355  mov     rax, [rax+18h]
0x180033359  mov     qword ptr [rsp+0A8h+mshlflags], rbx
0x18003335e  mov     dword ptr [rsp+0A8h+pvDestContext], edx
0x180033362  mov     rdx, r15
0x180033365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003336a  mov     edi, eax
0x18003336c  test    eax, eax
0x18003336e  js      short loc_1800333D1
0x180033370  mov     [rsp+0A8h+var_58], r12d
0x180033375  mov     r8, rbx; P
0x180033378  mov     rcx, gs:60h
0x180033381  xor     edx, edx; Flags
0x180033383  mov     rcx, [rcx+30h]; HeapHandle
0x180033387  call    cs:__imp_RtlFreeHeap
0x18003338d  mov     r12, [rsp+0A8h+arg_0]
0x180033395  mov     eax, edi
0x180033397  add     rsp, 78h
0x18003339b  pop     r15
0x18003339d  pop     r14
0x18003339f  pop     rdi
0x1800333a0  pop     rsi
0x1800333a1  pop     rbp
0x1800333a2  pop     rbx
0x1800333a3  retn
0x1800333a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333ab  test    byte ptr [rcx+1Ch], 2
0x1800333af  jz      short loc_180033370
0x1800333b1  cmp     byte ptr [rcx+19h], 2
0x1800333b5  jb      short loc_180033370
0x1800333b7  mov     rcx, [rcx+10h]
0x1800333bb  lea     r8, WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids
0x1800333c2  mov     edx, 0Fh
0x1800333c7  mov     r9d, eax
0x1800333ca  call    WPP_SF_d
0x1800333cf  jmp     short loc_180033370
0x1800333d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333d8  test    byte ptr [rcx+1Ch], 2
0x1800333dc  jz      short loc_180033370
0x1800333de  cmp     byte ptr [rcx+19h], 2
0x1800333e2  jb      short loc_180033370
0x1800333e4  mov     rcx, [rcx+10h]
0x1800333e8  lea     r8, WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids
0x1800333ef  mov     edx, 0Eh
0x1800333f4  mov     dword ptr [rsp+0A8h+pvDestContext], eax
0x1800333f8  mov     r9, r15
0x1800333fb  call    WPP_SF_Sd
0x180033400  jmp     loc_180033370
0x180033405  mov     rcx, cs:WPP_GLOBAL_Control
0x18003340c  test    byte ptr [rcx+1Ch], 2
0x180033410  jz      short loc_18003342D
0x180033412  cmp     byte ptr [rcx+19h], 2
0x180033416  jb      short loc_18003342D
0x180033418  mov     rcx, [rcx+10h]
0x18003341c  lea     r8, WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids
0x180033423  mov     edx, 0Ah
0x180033428  call    WPP_SF_
0x18003342d  mov     edi, 8007000Eh
0x180033432  jmp     loc_180033395
0x180033437  mov     rcx, cs:WPP_GLOBAL_Control
0x18003343e  test    byte ptr [rcx+1Ch], 2
0x180033442  jz      short loc_180033462
0x180033444  cmp     byte ptr [rcx+19h], 2
0x180033448  jb      short loc_180033462
0x18003344a  mov     rcx, [rcx+10h]
0x18003344e  lea     r8, WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids
0x180033455  mov     edx, 0Bh
0x18003345a  mov     r9d, eax
0x18003345d  call    WPP_SF_d
0x180033462  mov     rcx, rbx; hMem
0x180033465  call    cs:__imp_GlobalFree
0x18003346b  jmp     loc_18003338D
0x180033470  mov     rcx, cs:WPP_GLOBAL_Control
0x180033477  test    byte ptr [rcx+1Ch], 2
0x18003347b  jz      short loc_18003349B
0x18003347d  cmp     byte ptr [rcx+19h], 2
0x180033481  jb      short loc_18003349B
0x180033483  mov     rcx, [rcx+10h]
0x180033487  lea     r8, WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids
0x18003348e  mov     edx, 0Ch
0x180033493  mov     r9d, eax
0x180033496  call    WPP_SF_d
0x18003349b  mov     rcx, [rsp+0A8h+ppstm]
0x1800334a0  mov     rax, [rcx]
0x1800334a3  mov     rax, [rax+10h]
0x1800334a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334ac  jmp     loc_18003338D
0x1800334b1  mov     edi, 8007000Eh
0x1800334b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334bd  test    byte ptr [rcx+1Ch], 2
0x1800334c1  jz      loc_18003338D
0x1800334c7  cmp     byte ptr [rcx+19h], 2
0x1800334cb  jb      loc_18003338D
0x1800334d1  mov     rcx, [rcx+10h]
0x1800334d5  lea     r8, WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids
0x1800334dc  mov     edx, 10h
0x1800334e1  call    WPP_SF_
0x1800334e6  jmp     loc_18003338D
0x1800334eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334f2  test    byte ptr [rcx+1Ch], 2
0x1800334f6  jz      loc_18003338D
0x1800334fc  cmp     byte ptr [rcx+19h], 2
0x180033500  jb      short loc_180033521
0x180033502  mov     rcx, [rcx+10h]
0x180033506  lea     r8, WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids
0x18003350d  mov     edx, 0Dh
0x180033512  mov     r9d, eax
0x180033515  call    WPP_SF_d
0x18003351a  mov     rcx, cs:WPP_GLOBAL_Control
0x180033521  test    byte ptr [rcx+1Ch], 2
0x180033525  jz      loc_18003338D
0x18003352b  cmp     byte ptr [rcx+19h], 2
0x18003352f  jb      loc_18003338D
0x180033535  mov     rcx, [rcx+10h]
0x180033539  lea     r8, WPP_58d63a676bdf3c706a6b95209dd76db8_Traceguids
0x180033540  mov     edx, 11h
0x180033545  mov     r9d, edi
0x180033548  call    WPP_SF_d
0x18003354d  jmp     loc_18003338D
```
