# I_s_RPC_SCardGetReaderDeviceInstanceId

- ea: `0x180012190`
- end: `0x1800122c7`
- name: `I_s_RPC_SCardGetReaderDeviceInstanceId`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task`

## callers

- `0x180030340`

## callees

- `0x1800028b0`
- `0x1800059c0`
- `0x180009190`
- `0x18000c9a0`
- `0x18000d190`
- `0x180010910`
- `0x180012190`
- `0x1800122d0`
- `0x18001c370`
- `0x18003261b`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18001225d`
- `msvcrt!wcsncpy_s` at `0x18001225d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall I_s_RPC_SCardGetReaderDeviceInstanceId(LPVOID *a1, const WCHAR *a2, wchar_t **a3, unsigned int *a4)
{
  unsigned int v8; // edi
  CReaderProxy **v9; // rbx
  const wchar_t *v10; // rsi
  __int64 v11; // rax
  unsigned int v12; // eax
  rsize_t v13; // r14
  wchar_t *v14; // rax
  ulong pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  ulong v17; // [rsp+24h] [rbp-44h] BYREF
  ulong v18; // [rsp+28h] [rbp-40h] BYREF
  LPVOID *v19; // [rsp+30h] [rbp-38h] BYREF
  CReaderProxy **v20; // [rsp+70h] [rbp+8h] BYREF

  v8 = 0;
  _InterlockedExchange(&g_fExtendShutdownTimer, 1);
  CalRpcSetServiceThreadId(a1);
  try
  {
    CMutex::Grab((CMutex *)(a1 + 10));
    v19 = a1;
    if ( !a2 || !*a2 )
    {
      v17 = -2146435068;
      throw &v17;
    }
    try
    {
      v9 = (CReaderProxy **)CalaisLockReader(a2, a1[22]);
      v20 = v9;
      v10 = CReaderProxy::DeviceInstanceId(*v9);
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
      v12 = v11 + 1;
      *a4 = v12;
      v13 = v12;
      v14 = (wchar_t *)AllocH(2LL * v12);
      *a3 = v14;
      if ( !v14 )
      {
        pExceptionObject = -2146435066;
        throw &pExceptionObject;
      }
      wcsncpy_s(v14, *a4, v10, v13);
      if ( v9 )
      {
        CReaderProxy::Release(*v9);
        operator delete(v9);
        v20 = 0;
      }
      CServiceThreadLock::~CServiceThreadLock((CServiceThreadLock *)&v19);
    }
    catch ( ... )
    {
      if ( v20 )
        CalaisReleaseReader(&v20);
      throw;
    }
  }
  catch ( ulong v18 )
  {
    LODWORD(v20) = v18;
    return (unsigned int)v20;
  }
  catch ( ... )
  {
    LODWORD(v20) = -2146435055;
    return (unsigned int)v20;
  }
  return v8;
}

```

## disassembly

```asm
0x180012190  mov     [rsp+arg_8], rbx
0x180012195  mov     [rsp+arg_10], rsi
0x18001219a  push    rdi
0x18001219b  push    r12
0x18001219d  push    r13
0x18001219f  push    r14
0x1800121a1  push    r15
0x1800121a3  sub     rsp, 40h
0x1800121a7  mov     r15, r9
0x1800121aa  mov     r12, r8
0x1800121ad  mov     rsi, rdx
0x1800121b0  mov     rbx, rcx
0x1800121b3  xor     r13d, r13d
0x1800121b6  mov     edi, r13d
0x1800121b9  lea     eax, [r13+1]
0x1800121bd  xchg    eax, cs:?g_fExtendShutdownTimer@@3JA; long g_fExtendShutdownTimer
0x1800121c3  call    ?CalRpcSetServiceThreadId@@YAKPEAVCServiceThread@@@Z; CalRpcSetServiceThreadId(CServiceThread *)
0x1800121c8  mov     [rsp+68h+arg_0], r13
0x1800121cd  lea     rcx, [rbx+50h]; this
0x1800121d1  call    ?Grab@CMutex@@QEAAXXZ; CMutex::Grab(void)
0x1800121d6  mov     [rsp+68h+var_38], rbx
0x1800121db  test    rsi, rsi
0x1800121de  jz      loc_18001228B
0x1800121e4  cmp     r13w, [rsi]
0x1800121e8  jz      loc_18001228B
0x1800121ee  mov     rdx, [rbx+0B0h]; pSid2
0x1800121f5  mov     rcx, rsi; lpString1
0x1800121f8  call    ?CalaisLockReader@@YAPEAVCReaderReference@@PEBGPEAX@Z; CalaisLockReader(ushort const *,void *)
0x1800121fd  mov     rbx, rax
0x180012200  mov     [rsp+68h+arg_0], rax
0x180012205  mov     rcx, [rax]; this
0x180012208  call    ?DeviceInstanceId@CReaderProxy@@QEAAPEBGXZ; CReaderProxy::DeviceInstanceId(void)
0x18001220d  mov     rsi, rax
0x180012210  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012214  inc     rax
0x180012217  cmp     [rsi+rax*2], r13w
0x18001221c  jnz     short loc_180012214
0x18001221e  inc     eax
0x180012220  mov     [r15], eax
0x180012223  mov     r14d, eax
0x180012226  lea     rcx, [rax+rax]; unsigned __int64
0x18001222a  call    ?AllocH@@YAPEAX_K@Z; AllocH(unsigned __int64)
0x18001222f  mov     [r12], rax
0x180012233  test    rax, rax
0x180012236  jnz     short loc_180012251
0x180012238  mov     [rsp+68h+pExceptionObject], 80100006h
0x180012240  lea     rdx, _TI1K; pThrowInfo
0x180012247  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001224c  call    _CxxThrowException_0
0x180012251  mov     edx, [r15]; SizeInWords
0x180012254  mov     r9, r14; MaxCount
0x180012257  mov     r8, rsi; Source
0x18001225a  mov     rcx, rax; Destination
0x18001225d  call    cs:__imp_wcsncpy_s
0x180012263  test    rbx, rbx
0x180012266  jz      short loc_18001227E
0x180012268  mov     rcx, [rbx]; this
0x18001226b  call    ?Release@CReaderProxy@@QEAAXXZ; CReaderProxy::Release(void)
0x180012270  nop
0x180012271  mov     rcx, rbx; Block
0x180012274  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012279  mov     [rsp+68h+arg_0], r13
0x18001227e  lea     rcx, [rsp+68h+var_38]; this
0x180012283  call    ??1CServiceThreadLock@@QEAA@XZ; CServiceThreadLock::~CServiceThreadLock(void)
0x180012288  nop
0x180012289  jmp     short loc_1800122AB
0x18001228b  mov     [rsp+68h+var_44], 80100004h
0x180012293  lea     rdx, _TI1K; pThrowInfo
0x18001229a  lea     rcx, [rsp+68h+var_44]; pExceptionObject
0x18001229f  call    _CxxThrowException_0
0x1800122a5  jmp     short $+2
0x1800122a7  mov     edi, dword ptr [rsp+68h+arg_0]
0x1800122ab  mov     eax, edi
0x1800122ad  lea     r11, [rsp+68h+var_28]
0x1800122b2  mov     rbx, [r11+38h]
0x1800122b6  mov     rsi, [r11+40h]
0x1800122ba  mov     rsp, r11
0x1800122bd  pop     r15
0x1800122bf  pop     r14
0x1800122c1  pop     r13
0x1800122c3  pop     r12
0x1800122c5  pop     rdi
0x1800122c6  retn
```
