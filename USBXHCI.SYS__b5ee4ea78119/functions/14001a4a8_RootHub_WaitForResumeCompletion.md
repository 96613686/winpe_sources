# RootHub_WaitForResumeCompletion

- ea: `0x14001a4a8`
- end: `0x14001a6f3`
- name: `RootHub_WaitForResumeCompletion`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001a360`

## callees

- `0x140002568`
- `0x140019d6c`
- `0x14001a4a8`
- `0x14001ad0c`
- `0x14001f830`
- `0x140057de4`

## import_xrefs

- `HAL!KeStallExecutionProcessor` at `0x14001a5d8`
- `HAL!KeStallExecutionProcessor` at `0x14001a5d8`

## string_xrefs

- `0x14001a670`: `HW_COMPLIANCE: Port %2d Resume failed to complete before timeout`

## pseudocode

```c
__int64 __fastcall RootHub_WaitForResumeCompletion(_QWORD *a1, int a2, int *a3)
{
  char v3; // bp
  __int64 v6; // r13
  __int64 v7; // r12
  __int64 v8; // r15
  __int64 result; // rax
  __int64 *v10; // rdx
  int v11; // ebx
  unsigned int i; // esi
  int v13; // ecx
  int v14; // edx
  __int64 v15; // rax

  v3 = a2;
  v6 = *(_QWORD *)(a1[1] + 88LL);
  v7 = a1[6] + 120LL * (unsigned int)(a2 - 1);
  v8 = a1[5] + 16LL * (unsigned int)(a2 - 1);
  result = XilRegister_ReadUlong(v6, v8);
  *a3 = result;
  v10 = WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 4;
    result = WPP_RECORDER_SF_dD(
               *(_QWORD *)(a1[1] + 72LL),
               (_DWORD)v10,
               11,
               231,
               (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
               v3,
               result);
    v10 = WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids;
  }
  v11 = *a3;
  for ( i = 0; ; ++i )
  {
    if ( *a3 == -1
      || !*(_BYTE *)(v7 + 18)
      || (result = *a3 & 0x20203, (_DWORD)result != 515)
      || (v13 = *a3 & 0x1E0, v13 != 256) && v13 != 480 )
    {
      if ( i > 0x4B0 )
      {
        result = a1[1];
        ++*(_DWORD *)(result + 888);
        ++*(_DWORD *)(result + 956);
        *(_BYTE *)(result + 872) = 1;
      }
      return result;
    }
    if ( i == 6400 )
      break;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_DD(
        *(_QWORD *)(a1[1] + 72LL),
        (_DWORD)v10,
        11,
        233,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        v3,
        i);
    }
    KeStallExecutionProcessor(0xAu);
    result = XilRegister_ReadUlong(v6, v8);
    *a3 = result;
    if ( (_DWORD)result == -1 )
      return result;
    v10 = WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids;
    if ( (_DWORD)result != v11 )
    {
      v10 = WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 4;
        result = WPP_RECORDER_SF_dD(
                   *(_QWORD *)(a1[1] + 72LL),
                   (_DWORD)v10,
                   11,
                   234,
                   (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                   v3,
                   result);
        v10 = WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids;
      }
    }
  }
  MicrosoftTelemetryAssertTriggeredMsgKM(
    "HW_COMPLIANCE: Port %2d Resume failed to complete before timeout",
    (unsigned int)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
  v15 = a1[1];
  ++*(_DWORD *)(v15 + 884);
  ++*(_DWORD *)(v15 + 952);
  *(_BYTE *)(v15 + 872) = 1;
  result = (__int64)&WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 2;
    return WPP_RECORDER_SF_d(
             *(_QWORD *)(a1[1] + 72LL),
             v14,
             11,
             232,
             (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
             v3);
  }
  return result;
}

```

## disassembly

```asm
0x14001a4a8  push    rbx
0x14001a4aa  push    rbp
0x14001a4ab  push    rsi
0x14001a4ac  push    rdi
0x14001a4ad  push    r12
0x14001a4af  push    r13
0x14001a4b1  push    r14
0x14001a4b3  push    r15
0x14001a4b5  sub     rsp, 48h
0x14001a4b9  mov     rax, [rcx+8]
0x14001a4bd  mov     ebp, edx
0x14001a4bf  mov     rdi, rcx
0x14001a4c2  mov     r14, r8
0x14001a4c5  mov     r13, [rax+58h]
0x14001a4c9  lea     eax, [rdx-1]
0x14001a4cc  mov     r9d, eax
0x14001a4cf  imul    r12, r9, 78h ; 'x'
0x14001a4d3  mov     r15d, eax
0x14001a4d6  add     r12, [rcx+30h]
0x14001a4da  shl     r15, 4
0x14001a4de  add     r15, [rcx+28h]
0x14001a4e2  mov     rcx, r13
0x14001a4e5  mov     rdx, r15
0x14001a4e8  call    XilRegister_ReadUlong
0x14001a4ed  mov     [r14], eax
0x14001a4f0  lea     r8, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001a4f7  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14001a4fe  lea     rdx, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001a505  jnz     short loc_14001A53A
0x14001a507  mov     ebx, [r14]
0x14001a50a  xor     esi, esi
0x14001a50c  mov     ecx, [r14]
0x14001a50f  cmp     ecx, 0FFFFFFFFh
0x14001a512  jz      short loc_14001A51C
0x14001a514  cmp     byte ptr [r12+12h], 0
0x14001a51a  jnz     short loc_14001A572
0x14001a51c  cmp     esi, 4B0h
0x14001a522  ja      loc_14001A6D7
0x14001a528  add     rsp, 48h
0x14001a52c  pop     r15
0x14001a52e  pop     r14
0x14001a530  pop     r13
0x14001a532  pop     r12
0x14001a534  pop     rdi
0x14001a535  pop     rsi
0x14001a536  pop     rbp
0x14001a537  pop     rbx
0x14001a538  retn
0x14001a53a  mov     rcx, [rdi+8]
0x14001a53e  mov     r9d, 0E7h
0x14001a544  mov     [rsp+88h+var_58], eax
0x14001a548  mov     r8d, 0Bh
0x14001a54e  mov     [rsp+88h+var_60], ebp
0x14001a552  mov     [rsp+88h+var_68], rdx
0x14001a557  mov     dl, 4
0x14001a559  mov     rcx, [rcx+48h]
0x14001a55d  call    WPP_RECORDER_SF_dD
0x14001a562  lea     rdx, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001a569  lea     r8, WPP_RECORDER_INITIALIZED
0x14001a570  jmp     short loc_14001A507
0x14001a572  mov     eax, ecx
0x14001a574  and     eax, 20203h
0x14001a579  cmp     eax, 203h
0x14001a57e  jnz     short loc_14001A51C
0x14001a580  and     ecx, 1E0h
0x14001a586  cmp     ecx, 100h
0x14001a58c  jz      short loc_14001A596
0x14001a58e  cmp     ecx, 1E0h
0x14001a594  jnz     short loc_14001A51C
0x14001a596  cmp     esi, 1900h
0x14001a59c  jz      loc_14001A670
0x14001a5a2  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x14001a5a9  jz      short loc_14001A5D3
0x14001a5ab  mov     rcx, [rdi+8]
0x14001a5af  mov     r9d, 0E9h
0x14001a5b5  mov     [rsp+88h+var_58], esi
0x14001a5b9  mov     r8d, 0Bh
0x14001a5bf  mov     [rsp+88h+var_60], ebp
0x14001a5c3  mov     [rsp+88h+var_68], rdx
0x14001a5c8  mov     dl, 4
0x14001a5ca  mov     rcx, [rcx+48h]
0x14001a5ce  call    WPP_RECORDER_SF_DD
0x14001a5d3  mov     ecx, 0Ah; MicroSeconds
0x14001a5d8  call    cs:__imp_KeStallExecutionProcessor
0x14001a5df  nop     dword ptr [rax+rax+00h]
0x14001a5e4  mov     rdx, r15
0x14001a5e7  mov     rcx, r13
0x14001a5ea  call    XilRegister_ReadUlong
0x14001a5ef  mov     [r14], eax
0x14001a5f2  cmp     eax, 0FFFFFFFFh
0x14001a5f5  jz      loc_14001A528
0x14001a5fb  inc     esi
0x14001a5fd  lea     rdx, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001a604  lea     r8, WPP_RECORDER_INITIALIZED
0x14001a60b  cmp     eax, ebx
0x14001a60d  jz      loc_14001A50C
0x14001a613  lea     r8, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001a61a  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14001a621  lea     rdx, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001a628  jz      loc_14001A50C
0x14001a62e  mov     rcx, [rdi+8]
0x14001a632  mov     r9d, 0EAh
0x14001a638  mov     [rsp+88h+var_58], eax
0x14001a63c  mov     r8d, 0Bh
0x14001a642  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001a649  mov     [rsp+88h+var_60], ebp
0x14001a64d  mov     dl, 4
0x14001a64f  mov     [rsp+88h+var_68], rax
0x14001a654  mov     rcx, [rcx+48h]
0x14001a658  call    WPP_RECORDER_SF_dD
0x14001a65d  lea     rdx, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001a664  lea     r8, WPP_RECORDER_INITIALIZED
0x14001a66b  jmp     loc_14001A50C
0x14001a670  lea     rcx, aHwCompliancePo; __annotation("Debug", "TelemetryAssert", "FALSE", "HW_COMPLIANCE: Port %2d Resume failed to complete before timeout")
0x14001a677  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001a67c  mov     rax, [rdi+8]
0x14001a680  inc     dword ptr [rax+374h]
0x14001a686  inc     dword ptr [rax+3B8h]
0x14001a68c  mov     byte ptr [rax+368h], 1
0x14001a693  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001a69a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a6a1  jz      loc_14001A528
0x14001a6a7  mov     rcx, [rdi+8]
0x14001a6ab  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001a6b2  mov     r9d, 0E8h
0x14001a6b8  mov     [rsp+88h+var_60], ebp
0x14001a6bc  mov     r8d, 0Bh
0x14001a6c2  mov     [rsp+88h+var_68], rax
0x14001a6c7  mov     dl, 2
0x14001a6c9  mov     rcx, [rcx+48h]
0x14001a6cd  call    WPP_RECORDER_SF_d
0x14001a6d2  jmp     loc_14001A528
0x14001a6d7  mov     rax, [rdi+8]
0x14001a6db  inc     dword ptr [rax+378h]
0x14001a6e1  inc     dword ptr [rax+3BCh]
0x14001a6e7  mov     byte ptr [rax+368h], 1
0x14001a6ee  jmp     loc_14001A528
```
