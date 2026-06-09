# CalaisAddReader(CReader *)

- ea: `0x180029f78`
- end: `0x18002a147`
- name: `?CalaisAddReader@@YAKPEAVCReader@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(struct CReader *, __int64, const unsigned __int8 *, const unsigned __int8 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002bc50`
- `0x18002c850`

## callees

- `0x180009d80`
- `0x180012380`
- `0x1800123a0`
- `0x180012820`
- `0x1800174e8`
- `0x180019a40`
- `0x180019bc4`
- `0x180023168`
- `0x180028b28`
- `0x1800297a0`
- `0x180029f78`
- `0x180031df0`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a01f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a01f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a047`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a047`
- `KERNEL32!PulseEvent` at `0x18002a0d5`
- `KERNEL32!PulseEvent` at `0x18002a0d5`

## pseudocode

```c
__int64 __fastcall CalaisAddReader(
        struct CReader *a1,
        __int64 a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4)
{
  ulong v5; // esi
  const unsigned __int16 *v6; // rdi
  const unsigned __int16 *v7; // rbx
  const unsigned __int8 *v8; // rcx
  const unsigned __int16 *v9; // r9
  unsigned int v10; // ecx
  HANDLE v11; // r12
  ulong v12; // ecx
  __int64 i; // rdx
  const unsigned __int16 *v15; // [rsp+20h] [rbp-58h]
  ulong pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  ulong v17; // [rsp+34h] [rbp-44h] BYREF
  ulong v18; // [rsp+38h] [rbp-40h] BYREF
  ulong v19; // [rsp+3Ch] [rbp-3Ch] BYREF
  void **v20; // [rsp+40h] [rbp-38h] BYREF
  void *Block; // [rsp+48h] [rbp-30h]
  __int64 v22; // [rsp+50h] [rbp-28h]
  char v23; // [rsp+90h] [rbp+18h] BYREF

  v5 = 0;
  COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v23, g_pcsControlLocks, a3, a4);
  try
  {
    if ( !dword_18004BF68 )
    {
      pExceptionObject = -2146435054;
      throw &pExceptionObject;
    }
    v6 = &Data;
    v7 = &Data;
    if ( *((_DWORD *)a1 + 7) )
      v7 = (const unsigned __int16 *)*((_QWORD *)a1 + 2);
    if ( LocateReader(v7) )
    {
      CalaisError(v8, 0xCDu, v7, v9, v15);
      v17 = -2146435045;
      throw &v17;
    }
    if ( !dword_18004BF0C )
      goto LABEL_25;
    EnterCriticalSection(&stru_18004BAD0);
    if ( !hObject )
      hObject = CreateSCEvent(0x18u);
    LeaveCriticalSection(&stru_18004BAD0);
    v11 = hObject;
    if ( !hObject )
    {
LABEL_25:
      v18 = -2146435066;
      throw &v18;
    }
    v20 = &CBuffer::`vftable';
    Block = 0;
    v22 = 0;
    ListReaderNames(v10, v7, (struct CBuffer *)&v20);
    if ( HIDWORD(v22) )
      v6 = (const unsigned __int16 *)Block;
    if ( !FirstString(v6) )
      IntroduceReader(v12, v7, v7);
    for ( i = 0;
          HIDWORD(qword_18004B0C8) > (unsigned int)i && *((_QWORD *)qword_18004B0D0 + (int)i);
          i = (unsigned int)(i + 1) )
    {
      ;
    }
    CDynamicArray<CReader>::Set(qword_18004B0D0, i, a1);
    PulseEvent(v11);
    if ( (Microsoft_Windows_Smartcard_TriggerEnableBits & 1) != 0 )
      McTemplateU0j_EventWriteTransfer();
    if ( Block )
      operator delete[](Block);
  }
  catch ( ulong v19 )
  {
    v5 = v19;
  }
  catch ( ... )
  {
    v5 = -2146435068;
  }
  COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v23);
  return v5;
}

```

## disassembly

```asm
0x180029f78  mov     rax, rsp
0x180029f7b  mov     [rax+8], rbx
0x180029f7f  mov     [rax+20h], rsi
0x180029f83  push    rdi
0x180029f84  push    r12
0x180029f86  push    r14
0x180029f88  sub     rsp, 60h
0x180029f8c  mov     r14, rcx
0x180029f8f  xor     esi, esi
0x180029f91  mov     rdx, cs:?g_pcsControlLocks@@3PAPEAVCCriticalSectionObject@@A; struct CCriticalSectionObject *
0x180029f98  lea     rcx, [rax+18h]; this
0x180029f9c  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x180029fa1  nop
0x180029fa2  cmp     cs:dword_18004BF68, esi
0x180029fa8  jnz     short loc_180029FC3
0x180029faa  mov     [rsp+78h+pExceptionObject], 80100012h
0x180029fb2  lea     rdx, _TI1K; pThrowInfo
0x180029fb9  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180029fbe  call    _CxxThrowException_0
0x180029fc3  lea     rdi, Data
0x180029fca  cmp     dword ptr [r14+1Ch], 0
0x180029fcf  mov     rbx, rdi
0x180029fd2  jbe     short loc_180029FD8
0x180029fd4  mov     rbx, [r14+10h]
0x180029fd8  mov     rcx, rbx; lpString1
0x180029fdb  call    LocateReader
0x180029fe0  test    rax, rax
0x180029fe3  jz      short loc_18002A00B
0x180029fe5  mov     r8, rbx; unsigned __int16 *
0x180029fe8  mov     edx, 0CDh; unsigned int
0x180029fed  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x180029ff2  mov     [rsp+78h+var_44], 8010001Bh
0x180029ffa  lea     rdx, _TI1K; pThrowInfo
0x18002a001  lea     rcx, [rsp+78h+var_44]; pExceptionObject
0x18002a006  call    _CxxThrowException_0
0x18002a00b  cmp     cs:dword_18004BF0C, 0
0x18002a012  jz      loc_18002A0FF
0x18002a018  lea     rcx, stru_18004BAD0; lpCriticalSection
0x18002a01f  call    cs:__imp_EnterCriticalSection
0x18002a025  cmp     cs:hObject, 0
0x18002a02d  jnz     short loc_18002A040
0x18002a02f  mov     ecx, 18h; unsigned int
0x18002a034  call    ?CreateSCEvent@@YAPEAXK@Z; CreateSCEvent(ulong)
0x18002a039  mov     cs:hObject, rax
0x18002a040  lea     rcx, stru_18004BAD0; lpCriticalSection
0x18002a047  call    cs:__imp_LeaveCriticalSection
0x18002a04d  mov     r12, cs:hObject
0x18002a054  test    r12, r12
0x18002a057  jz      loc_18002A0FF
0x18002a05d  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002a064  mov     [rsp+78h+var_38], rax
0x18002a069  mov     [rsp+78h+Block], 0
0x18002a072  mov     [rsp+78h+var_28], 0
0x18002a07b  lea     r8, [rsp+78h+var_38]; struct CBuffer *
0x18002a080  mov     rdx, rbx; unsigned __int16 *
0x18002a083  call    ?ListReaderNames@@YAXKPEBGAEAVCBuffer@@@Z; ListReaderNames(ulong,ushort const *,CBuffer &)
0x18002a088  cmp     dword ptr [rsp+78h+var_28+4], 0
0x18002a08d  cmova   rdi, [rsp+78h+Block]
0x18002a093  mov     rcx, rdi; unsigned __int16 *
0x18002a096  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18002a09b  test    rax, rax
0x18002a09e  jnz     short loc_18002A0AB
0x18002a0a0  mov     r8, rbx; unsigned __int16 *
0x18002a0a3  mov     rdx, rbx; unsigned __int16 *
0x18002a0a6  call    ?IntroduceReader@@YAXKPEBG0@Z; IntroduceReader(ulong,ushort const *,ushort const *)
0x18002a0ab  xor     edx, edx
0x18002a0ad  mov     rcx, cs:qword_18004B0D0
0x18002a0b4  cmp     dword ptr cs:qword_18004B0C8+4, edx
0x18002a0ba  jbe     short loc_18002A0CA
0x18002a0bc  movsxd  rax, edx
0x18002a0bf  cmp     qword ptr [rcx+rax*8], 0
0x18002a0c4  jz      short loc_18002A0CA
0x18002a0c6  inc     edx
0x18002a0c8  jmp     short loc_18002A0B4
0x18002a0ca  mov     r8, r14
0x18002a0cd  call    ?Set@?$CDynamicArray@VCReader@@@@QEAAPEAVCReader@@HPEAV2@@Z; CDynamicArray<CReader>::Set(int,CReader *)
0x18002a0d2  mov     rcx, r12; hEvent
0x18002a0d5  call    cs:__imp_PulseEvent
0x18002a0db  test    cs:Microsoft_Windows_Smartcard_TriggerEnableBits, 1
0x18002a0e2  jz      short loc_18002A0EA
0x18002a0e4  call    McTemplateU0j_EventWriteTransfer
0x18002a0e9  nop
0x18002a0ea  cmp     [rsp+78h+Block], 0
0x18002a0f0  jz      short loc_18002A0FD
0x18002a0f2  mov     rcx, [rsp+78h+Block]; Block
0x18002a0f7  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18002a0fc  nop
0x18002a0fd  jmp     short loc_18002A122
0x18002a0ff  mov     [rsp+78h+var_40], 80100006h
0x18002a107  lea     rdx, _TI1K; pThrowInfo
0x18002a10e  lea     rcx, [rsp+78h+var_40]; pExceptionObject
0x18002a113  call    _CxxThrowException_0
0x18002a119  jmp     short $+2
0x18002a11b  mov     esi, [rsp+78h+arg_8]
0x18002a122  lea     rcx, [rsp+78h+arg_10]; this
0x18002a12a  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18002a12f  mov     eax, esi
0x18002a131  lea     r11, [rsp+78h+var_18]
0x18002a136  mov     rbx, [r11+20h]
0x18002a13a  mov     rsi, [r11+38h]
0x18002a13e  mov     rsp, r11
0x18002a141  pop     r14
0x18002a143  pop     r12
0x18002a145  pop     rdi
0x18002a146  retn
```
