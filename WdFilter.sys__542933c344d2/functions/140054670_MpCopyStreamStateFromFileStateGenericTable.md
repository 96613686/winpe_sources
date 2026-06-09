# MpCopyStreamStateFromFileStateGenericTable

- ea: `0x140054670`
- end: `0x1400549c0`
- name: `MpCopyStreamStateFromFileStateGenericTable`
- size: `848`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140051af0`

## callees

- `0x140003d20`
- `0x1400049dc`
- `0x1400051bc`
- `0x140009bf0`
- `0x14000f54c`
- `0x140011890`
- `0x1400118d0`
- `0x140054670`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTable` at `0x140054859`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x140054859`
- `ntoskrnl!RtlLookupElementGenericTable` at `0x14005472e`
- `ntoskrnl!RtlLookupElementGenericTable` at `0x14005472e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054770`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054770`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054764`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054764`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140054709`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140054709`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400546f4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400546f4`

## pseudocode

```c
void __fastcall MpCopyStreamStateFromFileStateGenericTable(
        __int64 a1,
        int a2,
        unsigned __int8 (__fastcall *a3)(__int64, _QWORD *))
{
  __int64 v6; // rsi
  int v7; // ecx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  int v13; // edx
  int v14; // r8d
  __int64 Buffer; // [rsp+30h] [rbp-48h] BYREF
  __int128 v16; // [rsp+38h] [rbp-40h]
  __int64 v17; // [rsp+48h] [rbp-30h]

  v17 = 0;
  v16 = 0;
  if ( a1 && a3 )
  {
    v6 = *(_QWORD *)(a1 + 8);
    if ( *(_DWORD *)(v6 + 120) != a2 )
      return;
    v7 = *(_DWORD *)(a1 + 48);
    if ( (v7 & 0x40) != 0 )
      return;
    if ( *(_DWORD *)(MpData + 4152) && (v7 & 2) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids,
          *(_QWORD *)(a1 + 168));
      return;
    }
    Buffer = *(_QWORD *)(a1 + 168);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v6 + 184), 1u);
    v8 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 168LL);
    if ( !v8 || (v9 = RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)(v8 + 16), &Buffer), (v10 = v9) == 0) )
    {
      switch ( a2 )
      {
        case 27:
          _InterlockedIncrement((volatile signed __int32 *)(MpData + 2944));
          break;
        case 28:
          _InterlockedIncrement((volatile signed __int32 *)(MpData + 2980));
          break;
        case 2:
          _InterlockedIncrement((volatile signed __int32 *)(MpData + 2908));
          break;
      }
LABEL_10:
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 8) + 184LL));
      KeLeaveCriticalRegion();
      return;
    }
    if ( !a3(a1, v9)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids,
        *(_QWORD *)(a1 + 168),
        a2);
    }
    v11 = v10[1];
    if ( *(_QWORD **)(v11 + 8) != v10 + 1 || (v12 = (_QWORD *)v10[2], (_QWORD *)*v12 != v10 + 1) )
      __fastfail(3u);
    *v12 = v11;
    *(_QWORD *)(v11 + 8) = v12;
    --*(_DWORD *)(*(_QWORD *)(a1 + 8) + 180LL);
    if ( !RtlDeleteElementGenericTable((PRTL_GENERIC_TABLE)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 168LL) + 16LL), v10) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
LABEL_24:
        switch ( a2 )
        {
          case 27:
            _InterlockedIncrement((volatile signed __int32 *)(MpData + 2940));
            break;
          case 28:
            _InterlockedIncrement((volatile signed __int32 *)(MpData + 2976));
            break;
          case 2:
            _InterlockedIncrement((volatile signed __int32 *)(MpData + 2904));
            break;
        }
        goto LABEL_10;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_iZ(WPP_GLOBAL_Control->AttachedDevice, v13, v14, *(_QWORD *)(a1 + 168), a1 + 240);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids, a1 + 240);
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids);
}

```

## disassembly

```asm
0x140054670  push    rbx
0x140054672  push    rbp
0x140054673  push    rdi
0x140054674  sub     rsp, 60h
0x140054678  mov     rax, cs:__security_cookie
0x14005467f  xor     rax, rsp
0x140054682  mov     [rsp+78h+var_28], rax
0x140054687  mov     [rsp+78h+var_30], 0
0x140054690  xorps   xmm0, xmm0
0x140054693  mov     rbp, r8
0x140054696  mov     edi, edx
0x140054698  mov     rbx, rcx
0x14005469b  movdqu  [rsp+78h+var_40], xmm0
0x1400546a1  test    rcx, rcx
0x1400546a4  jz      loc_140054984
0x1400546aa  test    r8, r8
0x1400546ad  jz      loc_140054984
0x1400546b3  mov     [rsp+78h+arg_8], rsi
0x1400546bb  mov     rsi, [rcx+8]
0x1400546bf  cmp     [rsi+78h], edx
0x1400546c2  jnz     loc_14005477C
0x1400546c8  mov     ecx, [rcx+30h]
0x1400546cb  test    cl, 40h
0x1400546ce  jnz     loc_14005477C
0x1400546d4  mov     rax, cs:MpData
0x1400546db  cmp     dword ptr [rax+1038h], 0
0x1400546e2  jnz     loc_1400547B8
0x1400546e8  mov     rax, [rbx+0A8h]
0x1400546ef  mov     [rsp+78h+Buffer], rax
0x1400546f4  call    cs:__imp_KeEnterCriticalRegion
0x1400546fb  nop     dword ptr [rax+rax+00h]
0x140054700  lea     rcx, [rsi+0B8h]; Resource
0x140054707  mov     dl, 1; Wait
0x140054709  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140054710  nop     dword ptr [rax+rax+00h]
0x140054715  mov     rax, [rbx+8]
0x140054719  mov     rcx, [rax+0A8h]
0x140054720  test    rcx, rcx
0x140054723  jz      short loc_140054746
0x140054725  add     rcx, 10h; Table
0x140054729  lea     rdx, [rsp+78h+Buffer]; Buffer
0x14005472e  call    cs:__imp_RtlLookupElementGenericTable
0x140054735  nop     dword ptr [rax+rax+00h]
0x14005473a  mov     rsi, rax
0x14005473d  test    rax, rax
0x140054740  jnz     loc_1400547F9
0x140054746  cmp     edi, 1Bh
0x140054749  jnz     short loc_14005479A
0x14005474b  mov     rax, cs:MpData
0x140054752  lock inc dword ptr [rax+0B80h]
0x140054759  mov     rcx, [rbx+8]
0x14005475d  add     rcx, 0B8h; Resource
0x140054764  call    cs:__imp_ExReleaseResourceLite
0x14005476b  nop     dword ptr [rax+rax+00h]
0x140054770  call    cs:__imp_KeLeaveCriticalRegion
0x140054777  nop     dword ptr [rax+rax+00h]
0x14005477c  mov     rsi, [rsp+78h+arg_8]
0x140054784  mov     rcx, [rsp+78h+var_28]
0x140054789  xor     rcx, rsp; StackCookie
0x14005478c  call    __security_check_cookie
0x140054791  add     rsp, 60h
0x140054795  pop     rdi
0x140054796  pop     rbp
0x140054797  pop     rbx
0x140054798  retn
0x14005479a  cmp     edi, 1Ch
0x14005479d  jz      loc_140054891
0x1400547a3  cmp     edi, 2
0x1400547a6  jnz     short loc_140054759
0x1400547a8  mov     rax, cs:MpData
0x1400547af  lock inc dword ptr [rax+0B5Ch]
0x1400547b6  jmp     short loc_140054759
0x1400547b8  test    cl, 2
0x1400547bb  jz      loc_1400546E8
0x1400547c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400547c8  lea     rbp, WPP_GLOBAL_Control
0x1400547cf  cmp     rcx, rbp
0x1400547d2  jz      short loc_14005477C
0x1400547d4  mov     eax, [rcx+2Ch]
0x1400547d7  test    al, 4
0x1400547d9  jz      short loc_14005477C
0x1400547db  mov     r9, [rbx+0A8h]
0x1400547e2  lea     r8, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids
0x1400547e9  mov     rcx, [rcx+18h]
0x1400547ed  mov     edx, 0Dh
0x1400547f2  call    WPP_SF_q
0x1400547f7  jmp     short loc_14005477C
0x1400547f9  mov     rdx, rsi
0x1400547fc  mov     rcx, rbx
0x1400547ff  mov     rax, rbp
0x140054802  call    cs:__guard_dispatch_icall_fptr
0x140054808  lea     rbp, WPP_GLOBAL_Control
0x14005480f  test    al, al
0x140054811  jz      loc_1400548EE
0x140054817  mov     rdx, [rsi+8]
0x14005481b  lea     rax, [rsi+8]
0x14005481f  cmp     [rdx+8], rax
0x140054823  jnz     loc_14005497D
0x140054829  mov     rcx, [rax+8]
0x14005482d  cmp     [rcx], rax
0x140054830  jnz     loc_14005497D
0x140054836  mov     [rcx], rdx
0x140054839  mov     [rdx+8], rcx
0x14005483d  mov     rdx, rsi; Buffer
0x140054840  mov     rax, [rbx+8]
0x140054844  dec     dword ptr [rax+0B4h]
0x14005484a  mov     rax, [rbx+8]
0x14005484e  mov     rcx, [rax+0A8h]
0x140054855  add     rcx, 10h; Table
0x140054859  call    cs:__imp_RtlDeleteElementGenericTable
0x140054860  nop     dword ptr [rax+rax+00h]
0x140054865  test    al, al
0x140054867  jz      loc_14005492E
0x14005486d  mov     rcx, cs:WPP_GLOBAL_Control
0x140054874  cmp     rcx, rbp
0x140054877  jnz     short loc_1400548C9
0x140054879  cmp     edi, 1Bh
0x14005487c  jnz     short loc_1400548A4
0x14005487e  mov     rax, cs:MpData
0x140054885  lock inc dword ptr [rax+0B7Ch]
0x14005488c  jmp     loc_140054759
0x140054891  mov     rax, cs:MpData
0x140054898  lock inc dword ptr [rax+0BA4h]
0x14005489f  jmp     loc_140054759
0x1400548a4  cmp     edi, 1Ch
0x1400548a7  jz      loc_14005496A
0x1400548ad  cmp     edi, 2
0x1400548b0  jnz     loc_140054759
0x1400548b6  mov     rax, cs:MpData
0x1400548bd  lock inc dword ptr [rax+0B58h]
0x1400548c4  jmp     loc_140054759
0x1400548c9  mov     eax, [rcx+2Ch]
0x1400548cc  test    al, 4
0x1400548ce  jz      short loc_140054879
0x1400548d0  mov     rcx, [rcx+18h]
0x1400548d4  lea     r9, [rbx+0F0h]
0x1400548db  mov     edx, 10h
0x1400548e0  lea     r8, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids
0x1400548e7  call    WPP_SF_Z
0x1400548ec  jmp     short loc_140054879
0x1400548ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400548f5  cmp     rcx, rbp
0x1400548f8  jz      loc_140054817
0x1400548fe  mov     eax, [rcx+2Ch]
0x140054901  test    al, 2
0x140054903  jz      loc_140054817
0x140054909  mov     r9, [rbx+0A8h]
0x140054910  lea     r8, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids
0x140054917  mov     rcx, [rcx+18h]
0x14005491b  mov     edx, 0Eh
0x140054920  mov     dword ptr [rsp+78h+var_58], edi
0x140054924  call    WPP_SF_qD
0x140054929  jmp     loc_140054817
0x14005492e  mov     rcx, cs:WPP_GLOBAL_Control
0x140054935  cmp     rcx, rbp
0x140054938  jz      loc_140054879
0x14005493e  mov     eax, [rcx+2Ch]
0x140054941  test    al, 1
0x140054943  jz      loc_14005486D
0x140054949  mov     r9, [rbx+0A8h]
0x140054950  lea     rax, [rbx+0F0h]
0x140054957  mov     rcx, [rcx+18h]
0x14005495b  mov     [rsp+78h+var_58], rax
0x140054960  call    WPP_SF_iZ
0x140054965  jmp     loc_14005486D
0x14005496a  mov     rax, cs:MpData
0x140054971  lock inc dword ptr [rax+0BA0h]
0x140054978  jmp     loc_140054759
0x14005497d  mov     ecx, 3
0x140054982  int     29h; Win8: RtlFailFast(ecx)
0x140054984  mov     rcx, cs:WPP_GLOBAL_Control
0x14005498b  lea     rbp, WPP_GLOBAL_Control
0x140054992  cmp     rcx, rbp
0x140054995  jz      loc_140054784
0x14005499b  mov     eax, [rcx+2Ch]
0x14005499e  test    al, 1
0x1400549a0  jz      loc_140054784
0x1400549a6  mov     rcx, [rcx+18h]
0x1400549aa  lea     r8, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids
0x1400549b1  mov     edx, 0Ch
0x1400549b6  call    WPP_SF_
0x1400549bb  jmp     loc_140054784
```
