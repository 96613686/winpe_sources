# FwppReferenceNetBufferListCommon

- ea: `0x1800067d0`
- end: `0x180006a16`
- name: `FwppReferenceNetBufferListCommon`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b550`

## callees

- `0x180004904`
- `0x1800067d0`
- `0x18000c9b4`
- `0x18000de60`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x1800067fd`
- `ntoskrnl!MmBadPointer` at `0x18000688a`
- `ntoskrnl!MmBadPointer` at `0x1800068ea`
- `ntoskrnl!MmBadPointer` at `0x18000694c`
- `ntoskrnl!MmBadPointer` at `0x180006965`
- `ntoskrnl!MmBadPointer` at `0x180006a07`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000697f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000697f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180006826`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180006826`
- `NETIO!WfpNblInfoSet` at `0x180006959`
- `NETIO!WfpNblInfoSet` at `0x180006959`
- `NETIO!WfpNblInfoGet` at `0x1800067e8`
- `NETIO!WfpNblInfoGet` at `0x180006879`
- `NETIO!WfpNblInfoGet` at `0x1800068dc`
- `NETIO!WfpNblInfoGet` at `0x1800067e8`
- `NETIO!WfpNblInfoGet` at `0x180006879`
- `NETIO!WfpNblInfoGet` at `0x1800068dc`
- `NETIO!WfpNblInfoAlloc` at `0x1800068c6`
- `NETIO!WfpNblInfoAlloc` at `0x1800068c6`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x1800069b5`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x1800069b5`

## string_xrefs

- `0x1800069e3`: `ExAllocateFromNPagedLookasideList`
- `0x1800069f8`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
void __fastcall FwppReferenceNetBufferListCommon(__int64 a1, char a2, _DWORD *a3)
{
  _QWORD *v6; // rax
  PVOID *v7; // rdx
  _DWORD *v8; // rcx
  __int64 v9; // rcx
  _DWORD *v10; // rbx
  _QWORD *v11; // rax
  int v12; // esi
  __int64 v13; // r8
  __int64 v14; // rax

  v6 = (_QWORD *)WfpNblInfoGet(a1);
  if ( !v6 || (v7 = (PVOID *)MmBadPointer, v6 == MmBadPointer) )
  {
    v7 = (PVOID *)MmBadPointer;
    v8 = MmBadPointer;
    if ( v6 != MmBadPointer )
      goto LABEL_5;
  }
  else
  {
    v8 = (_DWORD *)v6[1];
  }
  if ( v8 && v8 != *v7 )
  {
    if ( v8[1] == 2 )
      ++v8[87];
    return;
  }
LABEL_5:
  v10 = ExAllocateFromNPagedLookasideList(&gFwpNblInfo);
  if ( v10 || (v14 = WfpReportSysErrorAsNtStatus(v9, (int)"ExAllocateFromNPagedLookasideList", -1073741801)) == 0 )
  {
    memset(v10, 0, 0x178u);
    v10[1] = 2;
    v10[44] = a2 != 0;
    if ( a3 )
    {
      v10[86] = *a3;
      *((_QWORD *)v10 + 42) = v10 + 86;
    }
    v10[87] = 1;
  }
  else
  {
    WfpReportError(v14, (int)"WfpAllocFromNPagedLookasideList");
    v10 = MmBadPointer;
  }
  v11 = (_QWORD *)WfpNblInfoGet(a1);
  if ( v11 && v11 != MmBadPointer )
    goto LABEL_11;
  v12 = WfpNblInfoAlloc(a1);
  if ( !v12 )
  {
    v11 = (_QWORD *)WfpNblInfoGet(a1);
LABEL_11:
    if ( v10 )
    {
      *v10 = 1852864326;
      *((_QWORD *)v10 + 1) = v11;
      v11[1] = v10;
    }
    else
    {
      v11[1] = 0;
      WfpNblInfoDestroyIfUnused(a1);
    }
    return;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, v13, "WfpNblInfoAlloc", v12);
  }
  WfpReportError(v12, (int)"FwppSetPacketInfo");
  WfpNblInfoSet(a1, MmBadPointer);
  if ( v10 != MmBadPointer )
    ExFreeToNPagedLookasideList(&gFwpNblInfo, v10);
}

```

## disassembly

```asm
0x1800067d0  mov     [rsp+arg_8], rbp
0x1800067d5  mov     [rsp+arg_10], rsi
0x1800067da  push    rdi
0x1800067db  sub     rsp, 30h
0x1800067df  mov     rsi, r8
0x1800067e2  movzx   ebp, dl
0x1800067e5  mov     rdi, rcx
0x1800067e8  call    cs:__imp_WfpNblInfoGet
0x1800067ef  nop     dword ptr [rax+rax+00h]
0x1800067f4  test    rax, rax
0x1800067f7  jz      loc_1800068EA
0x1800067fd  mov     rdx, cs:MmBadPointer
0x180006804  cmp     rax, [rdx]
0x180006807  jz      loc_1800068EA
0x18000680d  mov     rcx, [rax+8]
0x180006811  test    rcx, rcx
0x180006814  jnz     loc_180006990
0x18000681a  lea     rcx, gFwpNblInfo; Lookaside
0x180006821  mov     [rsp+38h+arg_0], rbx
0x180006826  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18000682d  nop     dword ptr [rax+rax+00h]
0x180006832  mov     rbx, rax
0x180006835  test    rax, rax
0x180006838  jz      loc_1800069DD
0x18000683e  xor     edx, edx; Val
0x180006840  mov     r8d, 178h; Size
0x180006846  mov     rcx, rbx; void *
0x180006849  call    memset
0x18000684e  xor     eax, eax
0x180006850  mov     dword ptr [rbx+4], 2
0x180006857  test    bpl, bpl
0x18000685a  setnz   al
0x18000685d  mov     [rbx+0B0h], eax
0x180006863  test    rsi, rsi
0x180006866  jnz     loc_1800069C6
0x18000686c  mov     dword ptr [rbx+15Ch], 1
0x180006876  mov     rcx, rdi
0x180006879  call    cs:__imp_WfpNblInfoGet
0x180006880  nop     dword ptr [rax+rax+00h]
0x180006885  test    rax, rax
0x180006888  jz      short loc_1800068C3
0x18000688a  mov     rcx, cs:MmBadPointer
0x180006891  cmp     rax, [rcx]
0x180006894  jz      short loc_1800068C3
0x180006896  test    rbx, rbx
0x180006899  jz      loc_1800069AE
0x18000689f  mov     dword ptr [rbx], 6E707746h
0x1800068a5  mov     [rbx+8], rax
0x1800068a9  mov     [rax+8], rbx
0x1800068ad  mov     rbx, [rsp+38h+arg_0]
0x1800068b2  mov     rbp, [rsp+38h+arg_8]
0x1800068b7  mov     rsi, [rsp+38h+arg_10]
0x1800068bc  add     rsp, 30h
0x1800068c0  pop     rdi
0x1800068c1  retn
0x1800068c3  mov     rcx, rdi
0x1800068c6  call    cs:__imp_WfpNblInfoAlloc
0x1800068cd  nop     dword ptr [rax+rax+00h]
0x1800068d2  movsxd  rsi, eax
0x1800068d5  test    eax, eax
0x1800068d7  jnz     short loc_180006902
0x1800068d9  mov     rcx, rdi
0x1800068dc  call    cs:__imp_WfpNblInfoGet
0x1800068e3  nop     dword ptr [rax+rax+00h]
0x1800068e8  jmp     short loc_180006896
0x1800068ea  mov     rdx, cs:MmBadPointer
0x1800068f1  mov     rcx, [rdx]
0x1800068f4  cmp     rax, rcx
0x1800068f7  jz      loc_180006811
0x1800068fd  jmp     loc_18000681A
0x180006902  mov     rcx, cs:WPP_GLOBAL_Control
0x180006909  lea     rax, WPP_GLOBAL_Control
0x180006910  cmp     rcx, rax
0x180006913  jz      short loc_18000693D
0x180006915  cmp     byte ptr [rcx+29h], 2
0x180006919  jb      short loc_18000693D
0x18000691b  test    dword ptr [rcx+2Ch], 1000h
0x180006922  jz      short loc_18000693D
0x180006924  mov     rcx, [rcx+18h]
0x180006928  lea     r9, aWfpnblinfoallo; "WfpNblInfoAlloc"
0x18000692f  mov     edx, 0Ah
0x180006934  mov     [rsp+38h+var_18], esi
0x180006938  call    WPP_SF_sd
0x18000693d  mov     rcx, rsi
0x180006940  lea     rdx, aFwppsetpacketi; "FwppSetPacketInfo"
0x180006947  call    WfpReportError
0x18000694c  mov     rdx, cs:MmBadPointer
0x180006953  mov     rcx, rdi
0x180006956  mov     rdx, [rdx]
0x180006959  call    cs:__imp_WfpNblInfoSet
0x180006960  nop     dword ptr [rax+rax+00h]
0x180006965  mov     rax, cs:MmBadPointer
0x18000696c  cmp     rbx, [rax]
0x18000696f  jz      loc_1800068AD
0x180006975  mov     rdx, rbx; Entry
0x180006978  lea     rcx, gFwpNblInfo; Lookaside
0x18000697f  call    cs:__imp_ExFreeToNPagedLookasideList
0x180006986  nop     dword ptr [rax+rax+00h]
0x18000698b  jmp     loc_1800068AD
0x180006990  cmp     rcx, [rdx]
0x180006993  jz      loc_18000681A
0x180006999  cmp     dword ptr [rcx+4], 2
0x18000699d  jnz     loc_1800068B2
0x1800069a3  inc     dword ptr [rcx+15Ch]
0x1800069a9  jmp     loc_1800068B2
0x1800069ae  mov     rcx, rdi
0x1800069b1  mov     [rax+8], rbx
0x1800069b5  call    cs:__imp_WfpNblInfoDestroyIfUnused
0x1800069bc  nop     dword ptr [rax+rax+00h]
0x1800069c1  jmp     loc_1800068AD
0x1800069c6  mov     eax, [rsi]
0x1800069c8  lea     rcx, [rbx+158h]
0x1800069cf  mov     [rcx], eax
0x1800069d1  mov     [rbx+150h], rcx
0x1800069d8  jmp     loc_18000686C
0x1800069dd  mov     r8d, 0C0000017h
0x1800069e3  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x1800069ea  call    WfpReportSysErrorAsNtStatus
0x1800069ef  test    rax, rax
0x1800069f2  jz      loc_18000683E
0x1800069f8  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x1800069ff  mov     rcx, rax
0x180006a02  call    WfpReportError
0x180006a07  mov     rbx, cs:MmBadPointer
0x180006a0e  mov     rbx, [rbx]
0x180006a11  jmp     loc_180006876
```
