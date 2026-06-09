# CLogStorage::_VerifyRestart(CBuffer *,ulong *,ulong,int *,ulong *)

- ea: `0x18000c7fc`
- end: `0x18000c912`
- name: `?_VerifyRestart@CLogStorage@@AEAAPEAU_RESTARTPAGE@@PEAVCBuffer@@PEAKKPEAH1@Z`
- size: `278`
- prototype: `struct _RESTARTPAGE *__fastcall(CLogStorage *__hidden this, struct CBuffer *, unsigned int *, unsigned int, int *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002900`
- `0x18000a288`

## callees

- `0x18000c7fc`
- `0x18000d998`
- `0x18001266c`
- `0x180015010`

## string_xrefs

- `0x18000c8a8`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000c8e0`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
struct _RESTARTPAGE *__fastcall CLogStorage::_VerifyRestart(
        CLogStorage *this,
        struct CBuffer *a2,
        unsigned int *a3,
        ulong a4,
        int *a5,
        unsigned int *a6)
{
  int *v6; // rsi
  _DWORD *v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // ecx
  unsigned int v11; // eax
  ulong pExceptionObject; // [rsp+48h] [rbp+20h] BYREF

  pExceptionObject = a4;
  v6 = a5;
  *a3 = 0;
  *v6 = 0;
  if ( !a2 )
  {
    TraceFile(-2147024809, "E_INVALIDARG", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x4FAu);
    pExceptionObject = -2147024809;
    throw &pExceptionObject;
  }
  v8 = (_DWORD *)*((_QWORD *)a2 + 3);
  if ( !v8 )
  {
    TraceFile(-2147024809, "E_INVALIDARG", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x503u);
    pExceptionObject = -2147024809;
    throw &pExceptionObject;
  }
  if ( *v8 == 1381258066 )
  {
    v9 = ((__int64 (__fastcall *)(_QWORD, _DWORD *, void *))lpCalcCRC)(
           (unsigned int)(*((_DWORD *)this + 10) - 8),
           v8 + 2,
           pulCRCTable);
    if ( a6 )
    {
      *a6 = v9;
    }
    else if ( v9 != v8[1] )
    {
      *a3 = 0;
      *v6 = 1;
      return (struct _RESTARTPAGE *)v8;
    }
    v10 = v8[18];
    v11 = v8[7];
    if ( v10 <= v8[16] )
      v10 = v8[16];
    if ( v11 <= v10 )
      v11 = v10;
    *a3 = v11;
  }
  return (struct _RESTARTPAGE *)v8;
}

```

## disassembly

```asm
0x18000c7fc  mov     [rsp+arg_0], rbx
0x18000c801  mov     [rsp+arg_8], rsi
0x18000c806  mov     [rsp+pExceptionObject], r9d
0x18000c80b  push    rdi
0x18000c80c  sub     rsp, 20h
0x18000c810  mov     rsi, [rsp+28h+arg_20]
0x18000c815  mov     rdi, r8
0x18000c818  mov     dword ptr [r8], 0
0x18000c81f  mov     dword ptr [rsi], 0
0x18000c825  test    rdx, rdx
0x18000c828  jz      short loc_18000C8A2
0x18000c82a  mov     rbx, [rdx+18h]
0x18000c82e  test    rbx, rbx
0x18000c831  jz      loc_18000C8DA
0x18000c837  cmp     dword ptr [rbx], 52545352h
0x18000c83d  jnz     short loc_18000C87C
0x18000c83f  mov     ecx, [rcx+28h]
0x18000c842  lea     rdx, [rbx+8]
0x18000c846  mov     r8, cs:?pulCRCTable@@3PEAKEA; ulong * pulCRCTable
0x18000c84d  sub     ecx, 8
0x18000c850  mov     rax, cs:?lpCalcCRC@@3P6AKIPEAEPEAK@ZEA; ulong (*lpCalcCRC)(uint,uchar *,ulong *)
0x18000c857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c85c  mov     rcx, [rsp+28h+arg_28]
0x18000c861  test    rcx, rcx
0x18000c864  jz      short loc_18000C88F
0x18000c866  mov     [rcx], eax
0x18000c868  mov     ecx, [rbx+48h]
0x18000c86b  cmp     ecx, [rbx+40h]
0x18000c86e  mov     eax, [rbx+1Ch]
0x18000c871  cmovbe  ecx, [rbx+40h]
0x18000c875  cmp     eax, ecx
0x18000c877  cmovbe  eax, ecx
0x18000c87a  mov     [rdi], eax
0x18000c87c  mov     rsi, [rsp+28h+arg_8]
0x18000c881  mov     rax, rbx
0x18000c884  mov     rbx, [rsp+28h+arg_0]
0x18000c889  add     rsp, 20h
0x18000c88d  pop     rdi
0x18000c88e  retn
0x18000c88f  cmp     eax, [rbx+4]
0x18000c892  jz      short loc_18000C868
0x18000c894  mov     dword ptr [rdi], 0
0x18000c89a  mov     dword ptr [rsi], 1
0x18000c8a0  jmp     short loc_18000C87C
0x18000c8a2  mov     r9d, 4FAh; unsigned int
0x18000c8a8  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000c8af  lea     rdx, aEInvalidarg; "E_INVALIDARG"
0x18000c8b6  mov     ecx, 80070057h; int
0x18000c8bb  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000c8c0  lea     rdx, _TI1K; pThrowInfo
0x18000c8c7  mov     [rsp+28h+pExceptionObject], 80070057h
0x18000c8cf  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c8d4  call    _CxxThrowException_0
0x18000c8da  mov     r9d, 503h; unsigned int
0x18000c8e0  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000c8e7  lea     rdx, aEInvalidarg; "E_INVALIDARG"
0x18000c8ee  mov     ecx, 80070057h; int
0x18000c8f3  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000c8f8  lea     rdx, _TI1K; pThrowInfo
0x18000c8ff  mov     [rsp+28h+pExceptionObject], 80070057h
0x18000c907  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c90c  call    _CxxThrowException_0
```
