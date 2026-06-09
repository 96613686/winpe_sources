# LS::MeasureLine(CMeasurer &,uint,long *,long,bool,int &,long *,long *,CBreakRecLine const *)

- ea: `0x180080d3c`
- end: `0x180080fc7`
- name: `?MeasureLine@LS@@YAHAEAVCMeasurer@@IPEAJJ_NAEAH11PEBUCBreakRecLine@@@Z`
- size: `651`
- prototype: `__int64 __fastcall(LS *__hidden this, struct CMeasurer *, unsigned int, int *, int, bool, int *, int *, int *, const struct CBreakRecLine *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180018af0`

## callees

- `0x18002af88`
- `0x18002dd3c`
- `0x180080d3c`
- `0x180081004`
- `0x1800810b8`
- `0x1800824a8`
- `0x180082a5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080f13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080f13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180080df3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180080f19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180080df3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180080f19`

## pseudocode

```c
__int64 __fastcall LS::MeasureLine(
        LS *this,
        struct CMeasurer *a2,
        int *a3,
        int *a4,
        int a5,
        _DWORD *a6,
        int *a7,
        int *a8,
        struct CBreakRecLine *a9)
{
  __int64 v9; // r11
  int v10; // r14d
  unsigned int v12; // r12d
  __int64 v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 *v21; // rax
  __int64 v22; // rsi
  int v23; // edi
  _DWORD *LockTelemetry; // rax
  struct Ptls6::ols *Pols; // rax
  Ptls6::ols *v26; // rdi
  __int16 v27; // ax
  int v28; // eax
  __int64 v29; // rcx
  RTL_SRWLOCK *Lock; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  _QWORD v34[2]; // [rsp+50h] [rbp-49h] BYREF
  bool v35; // [rsp+60h] [rbp-39h]
  char v36; // [rsp+61h] [rbp-38h]
  int v37; // [rsp+68h] [rbp-31h] BYREF
  char v38; // [rsp+6Ch] [rbp-2Dh]
  int v39; // [rsp+70h] [rbp-29h]
  __int64 v40; // [rsp+78h] [rbp-21h]
  __int128 v41; // [rsp+80h] [rbp-19h]
  __int16 v42; // [rsp+90h] [rbp-9h]
  int v43; // [rsp+92h] [rbp-7h]
  __int16 v44; // [rsp+96h] [rbp-3h]

  v9 = *((_QWORD *)this + 2);
  v10 = (int)a4;
  v12 = (unsigned int)a2;
  if ( v9 )
    v13 = *(_QWORD *)(v9 + 40);
  else
    v13 = 0;
  v14 = 1;
  if ( (*(_BYTE *)(v13 + 358) & 1) == 0 )
    return 0;
  v34[0] = this;
  if ( v9 )
    v15 = *(_QWORD *)(v9 + 40);
  else
    v15 = 0;
  v16 = *(_QWORD *)(v15 + 256);
  v35 = 0;
  if ( v16 && (v17 = *(__int64 **)(v16 + 80)) != 0 )
  {
    v35 = (v17[2] & 4) != 0;
    v18 = *v17;
  }
  else
  {
    v18 = 0;
  }
  v34[1] = v18;
  v36 = 0;
  if ( v9 )
    v19 = *(_QWORD *)(v9 + 40);
  else
    v19 = 0;
  v20 = *(_QWORD *)(v19 + 256);
  if ( v20 && (v21 = *(__int64 **)(v20 + 80)) != 0 )
    v22 = *v21;
  else
    v22 = 0;
  v23 = (int)CLockSharedData::LockOwner;
  v37 = 0;
  if ( (_DWORD)CLockSharedData::LockOwner && v23 == GetCurrentThreadId() )
  {
    LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
    ++*LockTelemetry;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    AcquireSRWLockExclusive(Lock);
    LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
    v32 = CLock::GetLockTelemetry(0);
    ++*(_DWORD *)(v32 + 4);
  }
  ++CLSLock::_cOLSBusy;
  v38 = 1;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  g_cFCLock += v22 == 0;
  v39 = v22 == 0;
  Pols = CMeasurerLS::GetPols((CMeasurerLS *)v34);
  v26 = Pols;
  if ( !Pols )
    goto LABEL_25;
  v27 = *((_WORD *)Pols + 526);
  if ( (v27 & 0x20) != 0 && !a9 )
  {
    *((_WORD *)v26 + 526) = v27 & 0xFFDF;
    Ptls6::ols::ClearRunCache(v26);
  }
  v28 = Ptls6::ols::MeasureLine(v26, v12, a3, v10, 1, 0, 0, a7, a8, a9);
  if ( v28 >= 0 )
  {
    *a6 = v28 != 1;
    v29 = v40;
    if ( v40 )
    {
      *(_OWORD *)(v40 + 56) = v41;
      *(_WORD *)(v29 + 72) = v42;
      *(_DWORD *)(v29 + 74) = v43;
      *(_WORD *)(v29 + 78) = v44;
    }
  }
  else
  {
LABEL_25:
    v33 = v40;
    if ( v40 )
    {
      *(_OWORD *)(v40 + 56) = v41;
      *(_WORD *)(v33 + 72) = v42;
      *(_DWORD *)(v33 + 74) = v43;
      *(_WORD *)(v33 + 78) = v44;
    }
    v14 = 0;
  }
  g_cFCLock -= v39;
  CLSLock::~CLSLock((CLSLock *)&v37);
  return v14;
}

```

## disassembly

```asm
0x180080d3c  push    rbp
0x180080d3e  push    rbx
0x180080d3f  push    rsi
0x180080d40  push    rdi
0x180080d41  push    r12
0x180080d43  push    r14
0x180080d45  push    r15
0x180080d47  lea     rbp, [rsp-7]
0x180080d4c  sub     rsp, 0A0h
0x180080d53  mov     r11, [rcx+10h]
0x180080d57  mov     r14d, r9d
0x180080d5a  mov     r15, r8
0x180080d5d  mov     r12d, edx
0x180080d60  test    r11, r11
0x180080d63  jz      loc_180080F72
0x180080d69  mov     rax, [r11+28h]
0x180080d6d  mov     ebx, 1
0x180080d72  test    [rax+166h], bl
0x180080d78  jz      loc_180080F34
0x180080d7e  mov     [rbp+37h+var_80], rcx
0x180080d82  test    r11, r11
0x180080d85  jz      loc_180080F79
0x180080d8b  mov     rax, [r11+28h]
0x180080d8f  mov     rcx, [rax+100h]
0x180080d96  mov     [rbp+37h+var_70], 0
0x180080d9a  test    rcx, rcx
0x180080d9d  jz      short loc_180080DAC
0x180080d9f  mov     rcx, [rcx+50h]
0x180080da3  test    rcx, rcx
0x180080da6  jnz     loc_180080F87
0x180080dac  xor     eax, eax
0x180080dae  mov     [rbp+37h+var_78], rax
0x180080db2  mov     [rbp+37h+var_6F], 0
0x180080db6  test    r11, r11
0x180080db9  jz      loc_180080F80
0x180080dbf  mov     rax, [r11+28h]
0x180080dc3  mov     rcx, [rax+100h]
0x180080dca  test    rcx, rcx
0x180080dcd  jz      short loc_180080DDC
0x180080dcf  mov     rax, [rcx+50h]
0x180080dd3  test    rax, rax
0x180080dd6  jnz     loc_180080F9A
0x180080ddc  xor     esi, esi
0x180080dde  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x180080de4  mov     [rbp+37h+var_68], 0
0x180080deb  test    edi, edi
0x180080ded  jz      loc_180080F09
0x180080df3  call    cs:__imp_GetCurrentThreadId
0x180080df9  cmp     edi, eax
0x180080dfb  jnz     loc_180080F09
0x180080e01  xor     ecx, ecx
0x180080e03  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180080e08  add     [rax], ebx
0x180080e0a  add     cs:?_cOLSBusy@CLSLock@@1HA, ebx; int CLSLock::_cOLSBusy
0x180080e10  lea     rcx, [rbp+37h+var_80]; this
0x180080e14  xor     eax, eax
0x180080e16  mov     [rbp+37h+var_64], bl
0x180080e19  xorps   xmm0, xmm0
0x180080e1c  mov     [rbp+37h+var_58], 0
0x180080e24  test    rsi, rsi
0x180080e27  movdqa  [rbp+37h+var_50], xmm0
0x180080e2c  mov     [rbp+37h+var_40], 0
0x180080e32  setz    al
0x180080e35  add     cs:?g_cFCLock@@3JA, eax; long g_cFCLock
0x180080e3b  mov     [rbp+37h+var_60], eax
0x180080e3e  call    ?GetPols@CMeasurerLS@@QEAAPEAUols@Ptls6@@XZ; CMeasurerLS::GetPols(void)
0x180080e43  mov     rdi, rax
0x180080e46  test    rax, rax
0x180080e49  jz      loc_180080F38
0x180080e4f  movzx   eax, word ptr [rax+41Ch]
0x180080e56  mov     rsi, [rbp+37h+arg_40]
0x180080e5d  test    al, 20h
0x180080e5f  jnz     loc_180080FA2
0x180080e65  mov     rax, [rbp+37h+arg_38]
0x180080e69  mov     r9d, r14d; int
0x180080e6c  mov     [rsp+0D0h+var_88], rsi; struct CBreakRecLine *
0x180080e71  mov     r8, r15; int *
0x180080e74  mov     [rsp+0D0h+var_90], rax; int *
0x180080e79  mov     edx, r12d; unsigned int
0x180080e7c  mov     rax, [rbp+37h+arg_30]
0x180080e80  mov     rcx, rdi; this
0x180080e83  mov     [rsp+0D0h+var_98], rax; int *
0x180080e88  mov     [rsp+0D0h+var_A0], 0; bool
0x180080e8d  mov     [rsp+0D0h+var_A8], 0; bool
0x180080e92  mov     [rsp+0D0h+var_B0], bl; bool
0x180080e96  call    ?MeasureLine@ols@Ptls6@@QEAAJIPEAJJ_N1100PEBUCBreakRecLine@@@Z; Ptls6::ols::MeasureLine(uint,long *,long,bool,bool,bool,long *,long *,CBreakRecLine const *)
0x180080e9b  test    eax, eax
0x180080e9d  js      loc_180080F38
0x180080ea3  xor     ecx, ecx
0x180080ea5  cmp     eax, ebx
0x180080ea7  mov     rax, [rbp+37h+arg_28]
0x180080eab  setnz   cl
0x180080eae  mov     [rax], ecx
0x180080eb0  mov     rcx, [rbp+37h+var_58]
0x180080eb4  test    rcx, rcx
0x180080eb7  jz      short loc_180080EE3
0x180080eb9  mov     rax, qword ptr [rbp+37h+var_50]
0x180080ebd  mov     [rcx+38h], rax
0x180080ec1  mov     rax, qword ptr [rbp+37h+var_50+8]
0x180080ec5  mov     [rcx+40h], rax
0x180080ec9  mov     al, byte ptr [rbp+37h+var_40]
0x180080ecc  mov     [rcx+48h], al
0x180080ecf  mov     al, byte ptr [rbp+37h+var_40+1]
0x180080ed2  mov     [rcx+49h], al
0x180080ed5  mov     eax, [rbp+37h+var_3E]
0x180080ed8  mov     [rcx+4Ah], eax
0x180080edb  movzx   eax, [rbp+37h+var_3A]
0x180080edf  mov     [rcx+4Eh], ax
0x180080ee3  mov     ecx, [rbp+37h+var_60]
0x180080ee6  sub     cs:?g_cFCLock@@3JA, ecx; long g_cFCLock
0x180080eec  lea     rcx, [rbp+37h+var_68]; this
0x180080ef0  call    ??1CLSLock@@QEAA@XZ; CLSLock::~CLSLock(void)
0x180080ef5  mov     eax, ebx
0x180080ef7  add     rsp, 0A0h
0x180080efe  pop     r15
0x180080f00  pop     r14
0x180080f02  pop     r12
0x180080f04  pop     rdi
0x180080f05  pop     rsi
0x180080f06  pop     rbx
0x180080f07  pop     rbp
0x180080f08  retn
0x180080f09  xor     ecx, ecx
0x180080f0b  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x180080f10  mov     rcx, rax; SRWLock
0x180080f13  call    cs:__imp_AcquireSRWLockExclusive
0x180080f19  call    cs:__imp_GetCurrentThreadId
0x180080f1f  xor     ecx, ecx
0x180080f21  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x180080f27  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180080f2c  add     [rax+4], ebx
0x180080f2f  jmp     loc_180080E0A
0x180080f34  xor     eax, eax
0x180080f36  jmp     short loc_180080EF7
0x180080f38  mov     rcx, [rbp+37h+var_58]
0x180080f3c  test    rcx, rcx
0x180080f3f  jz      short loc_180080F6B
0x180080f41  mov     rax, qword ptr [rbp+37h+var_50]
0x180080f45  mov     [rcx+38h], rax
0x180080f49  mov     rax, qword ptr [rbp+37h+var_50+8]
0x180080f4d  mov     [rcx+40h], rax
0x180080f51  mov     al, byte ptr [rbp+37h+var_40]
0x180080f54  mov     [rcx+48h], al
0x180080f57  mov     al, byte ptr [rbp+37h+var_40+1]
0x180080f5a  mov     [rcx+49h], al
0x180080f5d  mov     eax, [rbp+37h+var_3E]
0x180080f60  mov     [rcx+4Ah], eax
0x180080f63  movzx   eax, [rbp+37h+var_3A]
0x180080f67  mov     [rcx+4Eh], ax
0x180080f6b  xor     ebx, ebx
0x180080f6d  jmp     loc_180080EE3
0x180080f72  xor     eax, eax
0x180080f74  jmp     loc_180080D6D
0x180080f79  xor     eax, eax
0x180080f7b  jmp     loc_180080D8F
0x180080f80  xor     eax, eax
0x180080f82  jmp     loc_180080DC3
0x180080f87  mov     eax, [rcx+10h]
0x180080f8a  shr     eax, 2
0x180080f8d  and     al, bl
0x180080f8f  mov     [rbp+37h+var_70], al
0x180080f92  mov     rax, [rcx]
0x180080f95  jmp     loc_180080DAE
0x180080f9a  mov     rsi, [rax]
0x180080f9d  jmp     loc_180080DDE
0x180080fa2  test    rsi, rsi
0x180080fa5  jnz     loc_180080E65
0x180080fab  mov     ecx, 0FFDFh
0x180080fb0  and     ax, cx
0x180080fb3  mov     rcx, rdi; this
0x180080fb6  mov     [rdi+41Ch], ax
0x180080fbd  call    ?ClearRunCache@ols@Ptls6@@QEAAXXZ; Ptls6::ols::ClearRunCache(void)
0x180080fc2  jmp     loc_180080E65
```
