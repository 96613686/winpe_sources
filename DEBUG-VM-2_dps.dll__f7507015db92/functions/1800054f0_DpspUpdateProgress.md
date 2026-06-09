# DpspUpdateProgress

- ea: `0x1800054f0`
- end: `0x180005716`
- name: `DpspUpdateProgress`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800104f4`

## callees

- `0x180001010`
- `0x1800054f0`
- `0x1800069b0`
- `0x180009090`
- `0x18000a856`
- `0x18000bcb8`
- `0x18000c90c`
- `0x180018b49`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005561`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005561`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000557f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000558e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000557f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000558e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800055d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800055d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000560a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000563d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000566b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000569d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800056eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000560a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000563d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000566b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000569d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800056eb`

## string_xrefs

- `0x18000552d`: `DpspUpdateProgress`
- `0x1800055b7`: `DpspUpdateProgress`

## pseudocode

```c
__int64 __fastcall DpspUpdateProgress(__int64 a1, unsigned int *a2, __int64 a3)
{
  int v6; // r8d
  int v7; // edi
  __int64 InstanceFromId; // rax
  __int64 v9; // rsi
  int v10; // r8d
  unsigned int v11; // ecx
  __int64 v12; // rdx
  size_t v13; // r15
  size_t v14; // r9
  int Args; // [rsp+20h] [rbp-58h]
  size_t Size; // [rsp+80h] [rbp+8h] BYREF

  LODWORD(Size) = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
      v6 = 3005;
      goto LABEL_3;
    }
    AcquireSRWLockShared(&g_SRWInstanceList);
    InstanceFromId = DpspGetInstanceFromId(a2 + 16, 0);
    v9 = InstanceFromId;
    if ( !InstanceFromId )
    {
      v7 = 0;
      ReleaseSRWLockShared(&g_SRWInstanceList);
      return (unsigned int)v7;
    }
    _InterlockedIncrement((volatile signed __int32 *)(InstanceFromId + 72));
    ReleaseSRWLockShared(&g_SRWInstanceList);
    if ( a1 == *(_QWORD *)(v9 + 808) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(v9 + 16));
      v11 = a2[32] * (*(_DWORD *)(v9 + 220) - *(_DWORD *)(v9 + 216)) / a2[33] + *(_DWORD *)(v9 + 216);
      if ( v11 >= *(_DWORD *)(v9 + 208) )
      {
        *(_DWORD *)(v9 + 208) = v11;
        v7 = ULongSub(a2[31], a2[34], (unsigned int *)&Size);
        if ( v7 >= 0 )
        {
          v13 = (unsigned int)Size;
          if ( (unsigned int)Size <= 0x208 )
          {
            v7 = WdipValidateMessagePayloadRange(a3, v12, (unsigned int)Size);
            if ( v7 >= 0 )
            {
              memset_0((void *)(v9 + 224), 0, v14);
              memcpy_0((void *)(v9 + 224), (char *)a2 + a2[34] + 40, v13);
              *(_DWORD *)(v9 + 744) = v13;
              ReleaseSRWLockExclusive((PSRWLOCK)(v9 + 16));
              goto LABEL_21;
            }
            ReleaseSRWLockExclusive((PSRWLOCK)(v9 + 16));
            v10 = 3084;
            Args = (unsigned __int16)v7;
          }
          else
          {
            ReleaseSRWLockExclusive((PSRWLOCK)(v9 + 16));
            v10 = 3069;
            Args = 534;
            v7 = -2147024362;
          }
        }
        else
        {
          ReleaseSRWLockExclusive((PSRWLOCK)(v9 + 16));
          v10 = 3062;
          Args = (unsigned __int16)v7;
        }
LABEL_11:
        WdipTraceError(
          (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
          (__int64)L"DpspUpdateProgress",
          v10,
          (const wchar_t *)L"Error = %d",
          Args);
LABEL_21:
        DpspCloseInstance(v9, 7, 0, (unsigned int)v7);
        return (unsigned int)v7;
      }
      ReleaseSRWLockExclusive((PSRWLOCK)(v9 + 16));
      v10 = 3048;
    }
    else
    {
      v10 = 3031;
    }
    Args = 16389;
    v7 = -2147467259;
    goto LABEL_11;
  }
  v6 = 3004;
LABEL_3:
  v7 = -2147024809;
  WdipTraceError(
    (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
    (__int64)L"DpspUpdateProgress",
    v6,
    (const wchar_t *)L"Error = %d",
    87);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800054f0  mov     rax, rsp
0x1800054f3  push    rbx
0x1800054f4  push    rbp
0x1800054f5  push    rsi
0x1800054f6  push    rdi
0x1800054f7  push    r12
0x1800054f9  push    r13
0x1800054fb  push    r14
0x1800054fd  push    r15
0x1800054ff  sub     rsp, 38h
0x180005503  mov     dword ptr [rax+8], 0
0x18000550a  mov     r13, r8
0x18000550d  mov     rbp, rdx
0x180005510  mov     rbx, rcx
0x180005513  test    rcx, rcx
0x180005516  jnz     short loc_18000554A
0x180005518  mov     r8d, 0BBCh; int
0x18000551e  lea     r9, aErrorD; "Error = %d"
0x180005525  mov     dword ptr [rsp+78h+Args], 57h ; 'W'; Args
0x18000552d  lea     rdx, aDpspupdateprog; "DpspUpdateProgress"
0x180005534  mov     edi, 80070057h
0x180005539  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180005540  call    WdipTraceError
0x180005545  jmp     loc_180005703
0x18000554a  test    rbp, rbp
0x18000554d  jnz     short loc_180005557
0x18000554f  mov     r8d, 0BBDh
0x180005555  jmp     short loc_18000551E
0x180005557  lea     r14, g_SRWInstanceList
0x18000555e  mov     rcx, r14; SRWLock
0x180005561  call    cs:__imp_AcquireSRWLockShared
0x180005567  lea     rcx, [rbp+40h]
0x18000556b  xor     edx, edx
0x18000556d  call    DpspGetInstanceFromId
0x180005572  mov     rsi, rax
0x180005575  mov     rcx, r14; SRWLock
0x180005578  test    rax, rax
0x18000557b  jnz     short loc_18000558A
0x18000557d  xor     edi, edi
0x18000557f  call    cs:__imp_ReleaseSRWLockShared
0x180005585  jmp     loc_180005703
0x18000558a  lock inc dword ptr [rax+48h]
0x18000558e  call    cs:__imp_ReleaseSRWLockShared
0x180005594  cmp     rbx, [rsi+328h]
0x18000559b  jz      short loc_1800055CF
0x18000559d  mov     r8d, 0BD7h; int
0x1800055a3  mov     dword ptr [rsp+78h+Args], 4005h; Args
0x1800055ab  mov     edi, 80004005h
0x1800055b0  lea     r9, aErrorD; "Error = %d"
0x1800055b7  lea     rdx, aDpspupdateprog; "DpspUpdateProgress"
0x1800055be  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800055c5  call    WdipTraceError
0x1800055ca  jmp     loc_1800056F1
0x1800055cf  lea     r14, [rsi+10h]
0x1800055d3  mov     rcx, r14; SRWLock
0x1800055d6  call    cs:__imp_AcquireSRWLockExclusive
0x1800055dc  mov     r8d, [rsi+0D8h]
0x1800055e3  xor     edx, edx
0x1800055e5  mov     eax, [rsi+0DCh]
0x1800055eb  sub     eax, r8d
0x1800055ee  imul    eax, [rbp+80h]
0x1800055f5  div     dword ptr [rbp+84h]
0x1800055fb  lea     ecx, [rax+r8]
0x1800055ff  cmp     ecx, [rsi+0D0h]
0x180005605  jnb     short loc_180005618
0x180005607  mov     rcx, r14; SRWLock
0x18000560a  call    cs:__imp_ReleaseSRWLockExclusive
0x180005610  mov     r8d, 0BE8h
0x180005616  jmp     short loc_1800055A3
0x180005618  mov     [rsi+0D0h], ecx
0x18000561e  lea     r8, [rsp+78h+Size]; unsigned int *
0x180005626  mov     edx, [rbp+88h]; unsigned int
0x18000562c  mov     ecx, [rbp+7Ch]; unsigned int
0x18000562f  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x180005634  mov     edi, eax
0x180005636  test    eax, eax
0x180005638  jns     short loc_180005655
0x18000563a  mov     rcx, r14; SRWLock
0x18000563d  call    cs:__imp_ReleaseSRWLockExclusive
0x180005643  movzx   ecx, di
0x180005646  mov     r8d, 0BF6h
0x18000564c  mov     dword ptr [rsp+78h+Args], ecx
0x180005650  jmp     loc_1800055B0
0x180005655  mov     r15d, dword ptr [rsp+78h+Size]
0x18000565d  mov     r9d, 208h
0x180005663  cmp     r15d, r9d
0x180005666  jbe     short loc_180005689
0x180005668  mov     rcx, r14; SRWLock
0x18000566b  call    cs:__imp_ReleaseSRWLockExclusive
0x180005671  mov     r8d, 0BFDh
0x180005677  mov     dword ptr [rsp+78h+Args], 216h
0x18000567f  mov     edi, 80070216h
0x180005684  jmp     loc_1800055B0
0x180005689  mov     r8, r15
0x18000568c  mov     rcx, r13
0x18000568f  call    WdipValidateMessagePayloadRange
0x180005694  mov     edi, eax
0x180005696  test    eax, eax
0x180005698  jns     short loc_1800056B5
0x18000569a  mov     rcx, r14; SRWLock
0x18000569d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800056a3  movzx   eax, di
0x1800056a6  mov     r8d, 0C0Ch
0x1800056ac  mov     dword ptr [rsp+78h+Args], eax
0x1800056b0  jmp     loc_1800055B0
0x1800056b5  lea     rbx, [rsi+0E0h]
0x1800056bc  mov     r8, r9; Size
0x1800056bf  mov     rcx, rbx; void *
0x1800056c2  xor     edx, edx; Val
0x1800056c4  call    memset_0
0x1800056c9  mov     edx, [rbp+88h]
0x1800056cf  mov     r8, r15; Size
0x1800056d2  add     rdx, 28h ; '('
0x1800056d6  mov     rcx, rbx; void *
0x1800056d9  add     rdx, rbp; Src
0x1800056dc  call    memcpy_0
0x1800056e1  mov     rcx, r14; SRWLock
0x1800056e4  mov     [rsi+2E8h], r15d
0x1800056eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800056f1  xor     r8d, r8d
0x1800056f4  mov     r9d, edi
0x1800056f7  mov     rcx, rsi
0x1800056fa  lea     edx, [r8+7]
0x1800056fe  call    DpspCloseInstance
0x180005703  mov     eax, edi
0x180005705  add     rsp, 38h
0x180005709  pop     r15
0x18000570b  pop     r14
0x18000570d  pop     r13
0x18000570f  pop     r12
0x180005711  pop     rdi
0x180005712  pop     rsi
0x180005713  pop     rbp
0x180005714  pop     rbx
0x180005715  retn
```
