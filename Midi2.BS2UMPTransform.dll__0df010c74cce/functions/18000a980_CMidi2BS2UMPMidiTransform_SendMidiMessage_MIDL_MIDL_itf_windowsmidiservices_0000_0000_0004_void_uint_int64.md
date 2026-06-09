# CMidi2BS2UMPMidiTransform::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x18000a980`
- end: `0x18000ac56`
- name: `?SendMidiMessage@CMidi2BS2UMPMidiTransform@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `726`
- prototype: `__int64 __fastcall(__int64, int, __int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task`

## callees

- `0x18000163c`
- `0x180001e60`
- `0x1800076b4`
- `0x180009528`
- `0x18000a328`
- `0x18000a4b8`
- `0x18000a7b0`
- `0x18000a980`
- `0x18000ade4`
- `0x18000b0b4`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a9bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a9bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac27`

## pseudocode

```c
__int64 __fastcall CMidi2BS2UMPMidiTransform::SendMidiMessage(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  _DWORD *v10; // rcx
  unsigned int v11; // r14d
  int v12; // edx
  __int64 v13; // rcx
  int v14; // r8d
  __int64 v15; // r9
  int v16; // eax
  unsigned int v17; // esi
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v20; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v22; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  __int64 v25; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[32]; // [rsp+80h] [rbp-80h] BYREF
  const char *v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+A8h] [rbp-58h]
  __int64 *v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+B8h] [rbp-48h]
  const wchar_t *v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  int *v33; // [rsp+D0h] [rbp-30h]
  __int64 v34; // [rsp+D8h] [rbp-28h]
  __int64 *v35; // [rsp+E0h] [rbp-20h]
  __int64 v36; // [rsp+E8h] [rbp-18h]
  int *v37; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+F8h] [rbp-8h]
  __int64 *v39; // [rsp+100h] [rbp+0h]
  __int64 v40; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v10 = (_DWORD *)*((_QWORD *)MidiBS2UMPTransformTelemetryProvider::Instance() + 1);
  if ( *v10 > 4u )
  {
    v24 = a5;
    v20 = a4;
    v39 = &v24;
    v25 = a3;
    v37 = (int *)&v20;
    v35 = &v25;
    v33 = &v19;
    v31 = L"Translating MIDI 1.0 message to UMP";
    v29 = &v21;
    v27 = "CMidi2BS2UMPMidiTransform::SendMidiMessage";
    v19 = a2;
    v21 = a1;
    v40 = 8;
    v38 = 4;
    v36 = 8;
    v34 = 4;
    v32 = 72;
    v30 = 8;
    v28 = 43;
    tlgWriteTransfer_EventWriteTransfer(v10, &word_18000EE5E, 0, 0, 9, v26);
  }
  v23 = 0;
  v22 = 0;
  v21 = a4 / 3 + 1;
  if ( a4 / 3 != -1 )
    std::vector<unsigned int>::_Reallocate<0>(&v22, &v21);
  v11 = 0;
  if ( a4 )
  {
    do
    {
      bytestreamToUMP::bytestreamParse((bytestreamToUMP *)(a1 + 96), *(_BYTE *)(v11 + a3));
      if ( v11 == a4 - 1 )
        bytestreamToUMP::dumpSysex7State((bytestreamToUMP *)(a1 + 96), 0);
      while ( 1 )
      {
        v12 = *(_DWORD *)(a1 + 228);
        if ( !v12 )
          break;
        v13 = *(int *)(a1 + 220);
        v14 = *(_DWORD *)(a1 + 4 * v13 + 108);
        *(_DWORD *)(a1 + 228) = v12 - 1;
        *(_DWORD *)(a1 + 220) = v13 + 1;
        if ( (_DWORD)v13 == 3 )
          *(_DWORD *)(a1 + 220) = 0;
        v19 = v14;
        if ( *((_QWORD *)&v22 + 1) == v23 )
        {
          std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(&v22, *((_QWORD *)&v22 + 1), &v19);
        }
        else
        {
          **((_DWORD **)&v22 + 1) = v14;
          *((_QWORD *)&v22 + 1) += 4LL;
        }
      }
      ++v11;
    }
    while ( v11 < a4 );
    v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  }
  v15 = (__int64)(*((_QWORD *)&v22 + 1) - v22) >> 2;
  if ( v15
    && (v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 88) + 24LL))(
                *(_QWORD *)(a1 + 88),
                a2 | 2u,
                v22,
                (unsigned int)(4 * v15)),
        v17 = v16,
        v16 < 0) )
  {
    *(_BYTE *)(a1 + 97) = -1;
    *(_OWORD *)(a1 + 108) = 0;
    *(_QWORD *)(a1 + 220) = 0;
    *(_DWORD *)(a1 + 228) = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"avcore\\midi2\\transform\\bytestreamtoump\\midi2.bs2umpmiditransform.cpp",
      (const char *)(unsigned int)v16,
      a5);
    std::vector<unsigned int>::~vector<unsigned int>(&v22);
    if ( v5 )
      LeaveCriticalSection(v5);
    return v17;
  }
  else
  {
    std::vector<unsigned int>::~vector<unsigned int>(&v22);
    if ( v5 )
      LeaveCriticalSection(v5);
    return 0;
  }
}

```

## disassembly

```asm
0x18000a980  mov     [rsp-8+arg_10], rbx
0x18000a985  push    rbp
0x18000a986  push    rsi
0x18000a987  push    rdi
0x18000a988  push    r12
0x18000a98a  push    r13
0x18000a98c  push    r14
0x18000a98e  push    r15
0x18000a990  lea     rbp, [rsp-20h]
0x18000a995  sub     rsp, 120h
0x18000a99c  mov     rax, cs:__security_cookie
0x18000a9a3  xor     rax, rsp
0x18000a9a6  mov     [rbp+50h+var_40], rax
0x18000a9aa  lea     rdi, [rcx+10h]
0x18000a9ae  mov     rbx, rcx
0x18000a9b1  mov     rcx, rdi; lpCriticalSection
0x18000a9b4  mov     r15d, r9d
0x18000a9b7  mov     rsi, r8
0x18000a9ba  mov     r12d, edx
0x18000a9bd  call    cs:__imp_EnterCriticalSection
0x18000a9c3  call    ?Instance@MidiBS2UMPTransformTelemetryProvider@@KAPEAV1@XZ; MidiBS2UMPTransformTelemetryProvider::Instance(void)
0x18000a9c8  xor     r13d, r13d
0x18000a9cb  mov     rcx, [rax+8]
0x18000a9cf  mov     eax, [rcx]
0x18000a9d1  cmp     eax, 4
0x18000a9d4  jbe     loc_18000AA98
0x18000a9da  mov     rax, qword ptr [rbp+50h+arg_20]
0x18000a9e1  lea     rdx, word_18000EE5E
0x18000a9e8  mov     [rsp+150h+var_E8], rax
0x18000a9ed  xor     r9d, r9d
0x18000a9f0  lea     rax, [rsp+150h+var_E8]
0x18000a9f5  mov     [rsp+150h+var_10C], r15d
0x18000a9fa  mov     [rbp+50h+var_50], rax
0x18000a9fe  xor     r8d, r8d
0x18000aa01  lea     rax, [rsp+150h+var_10C]
0x18000aa06  mov     [rsp+150h+var_E0], rsi
0x18000aa0b  mov     [rbp+50h+var_60], rax
0x18000aa0f  lea     rax, [rsp+150h+var_E0]
0x18000aa14  mov     [rbp+50h+var_70], rax
0x18000aa18  lea     rax, [rsp+150h+var_110]
0x18000aa1d  mov     [rbp+50h+var_80], rax
0x18000aa21  lea     rax, aTranslatingMid; "Translating MIDI 1.0 message to UMP"
0x18000aa28  mov     [rbp+50h+var_90], rax
0x18000aa2c  lea     rax, [rsp+150h+var_108]
0x18000aa31  mov     [rbp+50h+var_A0], rax
0x18000aa35  lea     rax, aCmidi2bs2umpmi_1; "CMidi2BS2UMPMidiTransform::SendMidiMess"...
0x18000aa3c  mov     [rbp+50h+var_B0], rax
0x18000aa40  lea     rax, [rbp+50h+var_D0]
0x18000aa44  mov     [rsp+150h+var_128], rax
0x18000aa49  mov     [rsp+150h+var_130], 9
0x18000aa51  mov     [rsp+150h+var_110], r12d
0x18000aa56  mov     [rsp+150h+var_108], rbx
0x18000aa5b  mov     [rbp+50h+var_48], 8
0x18000aa63  mov     [rbp+50h+var_58], 4
0x18000aa6b  mov     [rbp+50h+var_68], 8
0x18000aa73  mov     [rbp+50h+var_78], 4
0x18000aa7b  mov     [rbp+50h+var_88], 48h ; 'H'
0x18000aa83  mov     [rbp+50h+var_98], 8
0x18000aa8b  mov     [rbp+50h+var_A8], 2Bh ; '+'
0x18000aa93  call    _tlgWriteTransfer_EventWriteTransfer
0x18000aa98  mov     eax, 0AAAAAAABh
0x18000aa9d  mov     [rsp+150h+var_F0], r13
0x18000aaa2  mul     r15d
0x18000aaa5  xorps   xmm0, xmm0
0x18000aaa8  movdqu  [rsp+150h+var_100], xmm0
0x18000aaae  shr     edx, 1
0x18000aab0  add     edx, 1
0x18000aab3  mov     eax, edx
0x18000aab5  mov     [rsp+150h+var_108], rax
0x18000aaba  jz      short loc_18000AACB
0x18000aabc  lea     rdx, [rsp+150h+var_108]
0x18000aac1  lea     rcx, [rsp+150h+var_100]
0x18000aac6  call    ??$_Reallocate@$0A@@?$vector@IV?$allocator@I@std@@@std@@AEAAXAEA_K@Z; std::vector<uint>::_Reallocate<0>(unsigned __int64 &)
0x18000aacb  mov     r14d, r13d
0x18000aace  test    r15d, r15d
0x18000aad1  jz      loc_18000AB71
0x18000aad7  lea     r13d, [r15-1]
0x18000aadb  mov     edx, r14d
0x18000aade  lea     rcx, [rbx+60h]; this
0x18000aae2  mov     dl, [rdx+rsi]; unsigned __int8
0x18000aae5  call    ?bytestreamParse@bytestreamToUMP@@QEAAXE@Z; bytestreamToUMP::bytestreamParse(uchar)
0x18000aaea  cmp     r14d, r13d
0x18000aaed  jnz     short loc_18000AAFA
0x18000aaef  xor     edx, edx; bool
0x18000aaf1  lea     rcx, [rbx+60h]; this
0x18000aaf5  call    ?dumpSysex7State@bytestreamToUMP@@QEAAX_N@Z; bytestreamToUMP::dumpSysex7State(bool)
0x18000aafa  mov     edx, [rbx+0E4h]
0x18000ab00  test    edx, edx
0x18000ab02  jz      short loc_18000AB5E
0x18000ab04  movsxd  rcx, dword ptr [rbx+0DCh]
0x18000ab0b  lea     eax, [rdx-1]
0x18000ab0e  mov     r8d, [rbx+rcx*4+6Ch]
0x18000ab13  mov     [rbx+0E4h], eax
0x18000ab19  lea     eax, [rcx+1]
0x18000ab1c  mov     [rbx+0DCh], eax
0x18000ab22  cmp     eax, 4
0x18000ab25  jnz     short loc_18000AB31
0x18000ab27  mov     dword ptr [rbx+0DCh], 0
0x18000ab31  mov     rdx, qword ptr [rsp+150h+var_100+8]
0x18000ab36  mov     [rsp+150h+var_110], r8d
0x18000ab3b  cmp     rdx, [rsp+150h+var_F0]
0x18000ab40  jz      short loc_18000AB4D
0x18000ab42  mov     [rdx], r8d
0x18000ab45  add     qword ptr [rsp+150h+var_100+8], 4
0x18000ab4b  jmp     short loc_18000AAFA
0x18000ab4d  lea     r8, [rsp+150h+var_110]
0x18000ab52  lea     rcx, [rsp+150h+var_100]
0x18000ab57  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x18000ab5c  jmp     short loc_18000AAFA
0x18000ab5e  inc     r14d
0x18000ab61  cmp     r14d, r15d
0x18000ab64  jb      loc_18000AADB
0x18000ab6a  lea     rdi, [rbx+10h]
0x18000ab6e  xor     r13d, r13d
0x18000ab71  mov     r8, qword ptr [rsp+150h+var_100]
0x18000ab76  mov     r9, qword ptr [rsp+150h+var_100+8]
0x18000ab7b  sub     r9, r8
0x18000ab7e  sar     r9, 2
0x18000ab82  test    r9, r9
0x18000ab85  jz      loc_18000AC15
0x18000ab8b  movzx   edx, byte ptr [rbx+0E8h]
0x18000ab92  or      r12d, 2
0x18000ab96  mov     rcx, [rbx+58h]
0x18000ab9a  mov     [rsp+150h+var_128], rdx
0x18000ab9f  mov     rdx, qword ptr [rbp+50h+arg_20]
0x18000aba6  mov     qword ptr [rsp+150h+var_130], rdx; int
0x18000abab  mov     edx, r12d
0x18000abae  mov     rax, [rcx]
0x18000abb1  shl     r9d, 2
0x18000abb5  mov     rax, [rax+18h]
0x18000abb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abbe  mov     esi, eax
0x18000abc0  test    eax, eax
0x18000abc2  jns     short loc_18000AC15
0x18000abc4  mov     rcx, [rbp+58h]; this
0x18000abc8  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transform\\bytestreamtou"...
0x18000abcf  xorps   xmm0, xmm0
0x18000abd2  mov     byte ptr [rbx+61h], 0FFh
0x18000abd6  movups  xmmword ptr [rbx+6Ch], xmm0
0x18000abda  mov     r9d, eax; char *
0x18000abdd  mov     qword ptr [rbx+0DCh], 0
0x18000abe8  mov     edx, 8Dh; void *
0x18000abed  mov     [rbx+0E4h], r13d
0x18000abf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000abf9  lea     rcx, [rsp+150h+var_100]
0x18000abfe  call    ??1?$vector@IV?$allocator@I@std@@@std@@QEAA@XZ; std::vector<uint>::~vector<uint>(void)
0x18000ac03  test    rdi, rdi
0x18000ac06  jz      short loc_18000AC11
0x18000ac08  mov     rcx, rdi; lpCriticalSection
0x18000ac0b  call    cs:__imp_LeaveCriticalSection
0x18000ac11  mov     eax, esi
0x18000ac13  jmp     short loc_18000AC2F
0x18000ac15  lea     rcx, [rsp+150h+var_100]
0x18000ac1a  call    ??1?$vector@IV?$allocator@I@std@@@std@@QEAA@XZ; std::vector<uint>::~vector<uint>(void)
0x18000ac1f  test    rdi, rdi
0x18000ac22  jz      short loc_18000AC2D
0x18000ac24  mov     rcx, rdi; lpCriticalSection
0x18000ac27  call    cs:__imp_LeaveCriticalSection
0x18000ac2d  xor     eax, eax
0x18000ac2f  mov     rcx, [rbp+50h+var_40]
0x18000ac33  xor     rcx, rsp; StackCookie
0x18000ac36  call    __security_check_cookie
0x18000ac3b  mov     rbx, [rsp+150h+arg_10]
0x18000ac43  add     rsp, 120h
0x18000ac4a  pop     r15
0x18000ac4c  pop     r14
0x18000ac4e  pop     r13
0x18000ac50  pop     r12
0x18000ac52  pop     rdi
0x18000ac53  pop     rsi
0x18000ac54  pop     rbp
0x18000ac55  retn
```
