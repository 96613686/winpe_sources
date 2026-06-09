# CPortClient::SendComplexSyncRequest(ulong,void const *,short,CAlpcView const *,void *,short,long *)

- ea: `0x14000dadc`
- end: `0x14000dc2a`
- name: `?SendComplexSyncRequest@CPortClient@@QEAAJKPEBXFPEBVCAlpcView@@PEAXFPEAJ@Z`
- size: `334`
- prototype: `__int64 __usercall@<rax>(CPortClient *__hidden this@<rcx>, unsigned int@<edx>, const void *@<r8>, __int16@<r9w>, const struct CAlpcView *, void *, __int16, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400035ac`

## callees

- `0x140002e6c`
- `0x14000da7c`
- `0x14000dadc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000db0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000dc09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000db0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000dc09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000dc17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000dc17`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000db20`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000db20`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14000dbb0`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14000dbb0`

## pseudocode

```c
__int64 __fastcall CPortClient::SendComplexSyncRequest(
        CPortClient *this,
        int a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        void *a6,
        __int16 a7,
        int *a8)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v12; // rax
  _DWORD *v13; // rdi
  unsigned int v14; // ebx
  __int64 v15; // rcx
  int v16; // r9d
  HANDLE v17; // rax
  int v19; // [rsp+40h] [rbp-58h] BYREF
  __int128 v20; // [rsp+44h] [rbp-54h]
  __int128 v21; // [rsp+54h] [rbp-44h]
  int v22; // [rsp+64h] [rbp-34h]

  v19 = 0;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  ProcessHeap = GetProcessHeap();
  v12 = HeapAlloc(ProcessHeap, 8u, 0x38u);
  v13 = v12;
  if ( v12 )
  {
    v12[10] = a2;
    *v12 = 3670032;
    *((_QWORD *)v12 + 6) = *a3;
    v15 = *((_QWORD *)this + 2);
    v19 = 0x40000000;
    a5 = 56;
    v14 = NtAlpcSendWaitReceivePort(v15, 0x20000, v12, &v19, v12, &a5, 0, 0) | 0x10000000;
    CPortClient::CheckHRESULT(this, v14);
    if ( v16 >= 0 )
    {
      v14 = 0;
      *a8 = v13[11];
    }
    else
    {
      MilInstrumentationCheckHR_MaybeFailFast(4u, &CPortClient::MILINSTRUMENTATIONHRESULTLIST, 9u, v14, 0x1FEu, 0);
    }
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v13);
  }
  else
  {
    v14 = -2147024882;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &CPortClient::MILINSTRUMENTATIONHRESULTLIST, 9u, -2147024882, 0x1E4u, 0);
  }
  return v14;
}

```

## disassembly

```asm
0x14000dadc  push    rbx
0x14000dade  push    rbp
0x14000dadf  push    rsi
0x14000dae0  push    rdi
0x14000dae1  push    r15
0x14000dae3  sub     rsp, 70h
0x14000dae7  xorps   xmm0, xmm0
0x14000daea  mov     [rsp+98h+var_58], 0
0x14000daf2  xor     eax, eax
0x14000daf4  mov     rbx, r8
0x14000daf7  movups  [rsp+98h+var_54], xmm0
0x14000dafc  mov     [rsp+98h+var_34], eax
0x14000db00  mov     ebp, edx
0x14000db02  movups  [rsp+98h+var_44], xmm0
0x14000db07  mov     rsi, rcx
0x14000db0a  call    cs:__imp_GetProcessHeap
0x14000db10  mov     r15d, 38h ; '8'
0x14000db16  mov     rcx, rax; hHeap
0x14000db19  mov     r8d, r15d; dwBytes
0x14000db1c  lea     edx, [r15-30h]; dwFlags
0x14000db20  call    cs:__imp_HeapAlloc
0x14000db26  mov     rdi, rax
0x14000db29  test    rax, rax
0x14000db2c  jnz     short loc_14000DB5B
0x14000db2e  mov     [rsp+98h+var_70], rax; void *
0x14000db33  lea     r8d, [r15-2Fh]; unsigned int
0x14000db37  mov     ebx, 8007000Eh
0x14000db3c  mov     [rsp+98h+var_78], 1E4h; unsigned int
0x14000db44  mov     r9d, ebx; int
0x14000db47  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CPortClient@@2QBJB; int *
0x14000db4e  lea     ecx, [rax+4]; unsigned int
0x14000db51  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x14000db56  jmp     loc_14000DC1D
0x14000db5b  mov     [rax+28h], ebp
0x14000db5e  lea     r9, [rsp+98h+var_58]
0x14000db63  mov     dword ptr [rax], 380010h
0x14000db69  mov     r8, rdi
0x14000db6c  mov     rax, [rbx]
0x14000db6f  mov     edx, 20000h
0x14000db74  mov     [rdi+30h], rax
0x14000db78  lea     rax, [rsp+98h+arg_20]
0x14000db80  mov     rcx, [rsi+10h]
0x14000db84  mov     [rsp+98h+var_60], 0
0x14000db8d  mov     [rsp+98h+var_68], 0
0x14000db96  mov     [rsp+98h+var_70], rax
0x14000db9b  mov     qword ptr [rsp+98h+var_78], rdi
0x14000dba0  mov     [rsp+98h+var_58], 40000000h
0x14000dba8  mov     [rsp+98h+arg_20], r15
0x14000dbb0  call    cs:__imp_NtAlpcSendWaitReceivePort
0x14000dbb6  mov     ebx, eax
0x14000dbb8  mov     rcx, rsi; this
0x14000dbbb  bts     ebx, 1Ch
0x14000dbbf  mov     r9d, eax
0x14000dbc2  mov     edx, ebx; int
0x14000dbc4  call    ?CheckHRESULT@CPortClient@@AEAAJJ@Z; CPortClient::CheckHRESULT(long)
0x14000dbc9  test    r9d, r9d
0x14000dbcc  jns     short loc_14000DBFA
0x14000dbce  mov     r8d, 9; unsigned int
0x14000dbd4  mov     [rsp+98h+var_70], 0; void *
0x14000dbdd  mov     r9d, ebx; int
0x14000dbe0  mov     [rsp+98h+var_78], 1FEh; unsigned int
0x14000dbe8  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CPortClient@@2QBJB; int *
0x14000dbef  lea     ecx, [r8-5]; unsigned int
0x14000dbf3  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x14000dbf8  jmp     short loc_14000DC09
0x14000dbfa  mov     rcx, [rsp+98h+arg_38]
0x14000dc02  xor     ebx, ebx
0x14000dc04  mov     edx, [rdi+2Ch]
0x14000dc07  mov     [rcx], edx
0x14000dc09  call    cs:__imp_GetProcessHeap
0x14000dc0f  mov     r8, rdi; lpMem
0x14000dc12  xor     edx, edx; dwFlags
0x14000dc14  mov     rcx, rax; hHeap
0x14000dc17  call    cs:__imp_HeapFree
0x14000dc1d  mov     eax, ebx
0x14000dc1f  add     rsp, 70h
0x14000dc23  pop     r15
0x14000dc25  pop     rdi
0x14000dc26  pop     rsi
0x14000dc27  pop     rbp
0x14000dc28  pop     rbx
0x14000dc29  retn
```
