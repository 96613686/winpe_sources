# I_s_RPC_SCardWriteCache

- ea: `0x180019640`
- end: `0x180019737`
- name: `I_s_RPC_SCardWriteCache`
- size: `247`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, unsigned int, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180015120`

## callees

- `0x180002584`
- `0x1800136a0`
- `0x1800141c0`
- `0x180019640`
- `0x180023168`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001970d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001970d`

## pseudocode

```c
__int64 __fastcall I_s_RPC_SCardWriteCache(
        __int64 a1,
        struct _GUID *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned __int8 *a5,
        unsigned int a6)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx
  ulong pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  int v13; // [rsp+34h] [rbp-34h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-30h] BYREF
  void **v15; // [rsp+40h] [rbp-28h] BYREF
  void *Block; // [rsp+48h] [rbp-20h]
  __int64 v17; // [rsp+50h] [rbp-18h]
  int v18; // [rsp+70h] [rbp+8h] BYREF
  int v19; // [rsp+74h] [rbp+Ch]

  v19 = HIDWORD(a1);
  hMem = 0;
  v18 = 0;
  v15 = &CBuffer::`vftable';
  Block = 0;
  v17 = 0;
  _InterlockedExchange(&g_fExtendShutdownTimer, 1);
  v9 = CalRpcIdentifyCaller((LPWSTR *)&hMem, &v18);
  try
  {
    if ( v9 )
    {
      pExceptionObject = v9;
      throw &pExceptionObject;
    }
    CBuffer::Set((CBuffer *)&v15, a5, a6);
    v10 = ServerCacheWrite(a2, a3, a4, v18, (const unsigned __int16 *)hMem, (struct CBuffer *)&v15);
  }
  catch ( ulong v13 )
  {
    v18 = v13;
    v10 = v18;
  }
  catch ( ... )
  {
    v18 = -2146435055;
    v10 = v18;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( Block )
    operator delete[](Block);
  return v10;
}

```

## disassembly

```asm
0x180019640  mov     r11, rsp
0x180019643  mov     [r11+10h], rbx
0x180019647  mov     [r11+18h], rsi
0x18001964b  mov     [r11+8], rcx
0x18001964f  push    rdi
0x180019650  sub     rsp, 60h
0x180019654  mov     rbx, r9
0x180019657  mov     edi, r8d
0x18001965a  mov     rsi, rdx
0x18001965d  mov     qword ptr [r11-30h], 0
0x180019665  mov     [rsp+68h+arg_0], 0
0x18001966d  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180019674  mov     [r11-28h], rax
0x180019678  mov     qword ptr [r11-20h], 0
0x180019680  mov     qword ptr [r11-18h], 0
0x180019688  mov     eax, 1
0x18001968d  xchg    eax, cs:?g_fExtendShutdownTimer@@3JA; long g_fExtendShutdownTimer
0x180019693  lea     rdx, [r11+8]; int *
0x180019697  lea     rcx, [r11-30h]; StringSid
0x18001969b  call    ?CalRpcIdentifyCaller@@YAKPEAPEAGPEAH@Z; CalRpcIdentifyCaller(ushort * *,int *)
0x1800196a0  test    eax, eax
0x1800196a2  jz      short loc_1800196B9
0x1800196a4  mov     [rsp+68h+pExceptionObject], eax
0x1800196a8  lea     rdx, _TI1K; pThrowInfo
0x1800196af  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800196b4  call    _CxxThrowException_0
0x1800196b9  mov     r8d, [rsp+68h+arg_28]; unsigned int
0x1800196c1  mov     rdx, [rsp+68h+arg_20]; unsigned __int8 *
0x1800196c9  lea     rcx, [rsp+68h+var_28]; this
0x1800196ce  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x1800196d3  lea     rax, [rsp+68h+var_28]
0x1800196d8  mov     [rsp+68h+var_40], rax; struct CBuffer *
0x1800196dd  mov     rax, [rsp+68h+hMem]
0x1800196e2  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x1800196e7  mov     r9d, [rsp+68h+arg_0]; int
0x1800196ec  mov     r8, rbx; unsigned __int16 *
0x1800196ef  mov     edx, edi; unsigned int
0x1800196f1  mov     rcx, rsi; struct _GUID *
0x1800196f4  call    ?ServerCacheWrite@@YAKPEAU_GUID@@KPEBGH1AEAVCBuffer@@@Z; ServerCacheWrite(_GUID *,ulong,ushort const *,int,ushort const *,CBuffer &)
0x1800196f9  mov     ebx, eax
0x1800196fb  jmp     short loc_180019703
0x1800196fd  jmp     short $+2
0x1800196ff  mov     ebx, [rsp+68h+arg_0]
0x180019703  mov     rcx, [rsp+68h+hMem]; hMem
0x180019708  test    rcx, rcx
0x18001970b  jz      short loc_180019714
0x18001970d  call    cs:__imp_LocalFree
0x180019713  nop
0x180019714  mov     rcx, [rsp+68h+Block]; Block
0x180019719  test    rcx, rcx
0x18001971c  jz      short loc_180019723
0x18001971e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180019723  mov     eax, ebx
0x180019725  lea     r11, [rsp+68h+var_8]
0x18001972a  mov     rbx, [r11+18h]
0x18001972e  mov     rsi, [r11+20h]
0x180019732  mov     rsp, r11
0x180019735  pop     rdi
0x180019736  retn
```
