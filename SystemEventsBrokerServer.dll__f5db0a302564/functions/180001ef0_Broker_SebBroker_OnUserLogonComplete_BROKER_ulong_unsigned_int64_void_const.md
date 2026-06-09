# Broker::SebBroker::OnUserLogonComplete(_BROKER *,ulong,unsigned __int64,void * const)

- ea: `0x180001ef0`
- end: `0x1800020b2`
- name: `?OnUserLogonComplete@SebBroker@Broker@@CAKPEAU_BROKER@@K_KQEAX@Z`
- size: `450`
- prototype: `static unsigned int(struct _BROKER *, unsigned int, unsigned __int64, void *const)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001ef0`
- `0x180002680`
- `0x180005b0c`
- `0x1800076a0`
- `0x180013aa0`
- `0x180016150`
- `0x18001d9ac`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001f88`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001f88`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001ff9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001ff9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Broker::SebBroker::OnUserLogonComplete(struct _BROKER *a1, int a2, __int64 a3, char *pSid)
{
  char *v4; // rsi
  int v5; // r14d
  int v6; // edi
  __int64 v8; // r8
  __int64 v9; // r15
  unsigned int v10; // ebx
  int v11; // edx
  _BYTE *v13; // rbp
  _QWORD *v14; // rcx
  _BYTE *v15; // rbp
  _QWORD *v16; // rcx
  _BYTE *v17; // rdx
  _BYTE *v18; // rdx
  _BYTE v19[32]; // [rsp+0h] [rbp-E8h] BYREF
  size_t Size; // [rsp+20h] [rbp-C8h]
  unsigned int v21; // [rsp+30h] [rbp-B8h]
  __int64 v22; // [rsp+38h] [rbp-B0h]
  char v23; // [rsp+40h] [rbp-A8h]
  DWORD CurrentThreadId; // [rsp+44h] [rbp-A4h]
  __int64 v25; // [rsp+48h] [rbp-A0h] BYREF
  std::_Ref_count_base *v26; // [rsp+50h] [rbp-98h]
  __int64 v27; // [rsp+58h] [rbp-90h] BYREF
  std::_Ref_count_base *v28; // [rsp+60h] [rbp-88h]
  void **pExceptionObject; // [rsp+68h] [rbp-80h] BYREF
  __int128 v30; // [rsp+70h] [rbp-78h]
  int v31; // [rsp+80h] [rbp-68h]
  int v32; // [rsp+88h] [rbp-60h]
  __int64 v33; // [rsp+90h] [rbp-58h] BYREF
  int v34; // [rsp+F8h] [rbp+10h]
  __int64 v35; // [rsp+100h] [rbp+18h]
  char *v36; // [rsp+108h] [rbp+20h]

  v4 = pSid;
  v5 = a3;
  v6 = a2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_dd_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x3Fu, a3, a3, a2, pSid);
  Broker::SebBroker::GetInstance(&v27);
  v9 = v27;
  if ( v27 )
  {
    v10 = 0;
    if ( *(struct _BROKER **)(v27 + 136) == a1 )
    {
      v22 = v27 + 8;
      RtlAcquireSRWLockExclusive(v27 + 8);
      CurrentThreadId = GetCurrentThreadId();
      v23 = 1;
      LOBYTE(Size) = 0;
      Broker::SebBroker::GetSessionInfo(v9, &v25, v6, v4, Size);
      if ( !v25 )
      {
        try
        {
          v30 = 0;
          v31 = 1;
          pExceptionObject = &Broker::Win32Error::`vftable';
          v32 = 1168;
          throw (Broker::Win32Error *)&pExceptionObject;
        }
        catch ( Broker::Win32Error v33 )
        {
          v17 = v19;
          v13 = v17;
          v14 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 2u )
            WPP_SF_d(v14[2], 64, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, *((unsigned int *)v13 + 44));
          *((_DWORD *)v13 + 12) = *((_DWORD *)v13 + 44);
          *((_QWORD *)v13 + 18) = &std::exception::`vftable';
          o___std_exception_destroy_0(v13 + 152);
          v10 = v21;
          LOBYTE(v6) = v34;
          v5 = v35;
          v4 = v36;
          goto LABEL_15;
        }
        catch ( ... )
        {
          v18 = v19;
          v15 = v18;
          v16 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 2u )
            WPP_SF_(v16[2], 65, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
          *((_DWORD *)v15 + 12) = 1359;
          v10 = v21;
          LOBYTE(v6) = v34;
          v5 = v35;
          v4 = v36;
          goto LABEL_15;
        }
      }
      if ( *(_DWORD *)(v25 + 64) || *(_DWORD *)(v25 + 68) )
      {
        LODWORD(Size) = 0;
        LOBYTE(v11) = 1;
        PubSebLevelEvent(*(_QWORD *)(v25 + 64), v11, v6, 0, Size);
      }
      if ( v26 )
        std::_Ref_count_base::_Decref(v26);
      RtlReleaseSRWLockExclusive(v9 + 8);
    }
    else
    {
      v10 = 5;
    }
  }
  else
  {
    v10 = 21;
  }
LABEL_15:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_dd_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x42u, v8, v5, v6, v4);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  return v10;
}

```

## disassembly

```asm
0x180001ef0  mov     rax, rsp
0x180001ef3  mov     [rax+8], rbx
0x180001ef7  mov     [rax+20h], r9
0x180001efb  mov     [rax+18h], r8
0x180001eff  mov     [rax+10h], edx
0x180001f02  push    rsi
0x180001f03  push    rdi
0x180001f04  push    r12
0x180001f06  push    r14
0x180001f08  push    r15
0x180001f0a  sub     rsp, 0C0h
0x180001f11  mov     rsi, r9
0x180001f14  mov     r14, r8
0x180001f17  mov     edi, edx
0x180001f19  mov     r12, rcx
0x180001f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f23  test    byte ptr [rcx+1Ch], 1
0x180001f27  jz      short loc_180001F49
0x180001f29  cmp     byte ptr [rcx+19h], 4
0x180001f2d  jb      short loc_180001F49
0x180001f2f  mov     r9d, r8d
0x180001f32  mov     edx, 3Fh ; '?'
0x180001f37  mov     [rsp+0E8h+pSid], rsi; pSid
0x180001f3c  mov     dword ptr [rsp+0E8h+Size], edi; char
0x180001f40  mov     rcx, [rcx+10h]; LoggerHandle
0x180001f44  call    WPP_SF_dd_sid_
0x180001f49  lea     rcx, [rsp+0E8h+var_90]
0x180001f4e  call    ?GetInstance@SebBroker@Broker@@SA?AV?$shared_ptr@VSebBroker@Broker@@@std@@XZ; Broker::SebBroker::GetInstance(void)
0x180001f53  nop
0x180001f54  mov     r15, [rsp+0E8h+var_90]
0x180001f59  test    r15, r15
0x180001f5c  jnz     short loc_180001F67
0x180001f5e  lea     ebx, [r15+15h]
0x180001f62  jmp     loc_18000205B
0x180001f67  xor     ebx, ebx
0x180001f69  cmp     [r15+88h], r12
0x180001f70  jz      short loc_180001F7C
0x180001f72  mov     ebx, 5
0x180001f77  jmp     loc_18000205B
0x180001f7c  lea     r12, [r15+8]
0x180001f80  mov     [rsp+0E8h+var_B0], r12
0x180001f85  mov     rcx, r12
0x180001f88  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001f8e  call    cs:__imp_GetCurrentThreadId
0x180001f94  mov     [rsp+0E8h+var_A4], eax
0x180001f98  mov     [rsp+0E8h+var_A8], 1
0x180001f9d  mov     byte ptr [rsp+0E8h+Size], 0
0x180001fa2  mov     r9, rsi
0x180001fa5  mov     r8d, edi
0x180001fa8  lea     rdx, [rsp+0E8h+var_A0]
0x180001fad  mov     rcx, r15
0x180001fb0  call    ?GetSessionInfo@SebBroker@Broker@@QEAA?AV?$shared_ptr@U_SessionInfo@Broker@@@std@@KQEAX_N@Z; Broker::SebBroker::GetSessionInfo(ulong,void * const,bool)
0x180001fb5  nop
0x180001fb6  mov     rcx, [rsp+0E8h+var_A0]
0x180001fbb  test    rcx, rcx
0x180001fbe  jz      short loc_180002002
0x180001fc0  cmp     dword ptr [rcx+40h], 0
0x180001fc4  jnz     short loc_180001FCC
0x180001fc6  cmp     dword ptr [rcx+44h], 0
0x180001fca  jz      short loc_180001FE6
0x180001fcc  mov     dword ptr [rsp+0E8h+Size], 0; Size
0x180001fd4  xor     r9d, r9d; int
0x180001fd7  mov     r8d, edi; int
0x180001fda  mov     dl, 1; int
0x180001fdc  mov     rcx, [rcx+40h]; int
0x180001fe0  call    PubSebLevelEvent
0x180001fe5  nop
0x180001fe6  mov     rcx, [rsp+0E8h+var_98]; this
0x180001feb  test    rcx, rcx
0x180001fee  jz      short loc_180001FF6
0x180001ff0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180001ff5  nop
0x180001ff6  mov     rcx, r12
0x180001ff9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001fff  nop
0x180002000  jmp     short loc_18000205B
0x180002002  xorps   xmm0, xmm0
0x180002005  movups  [rsp+0E8h+var_78], xmm0
0x18000200a  mov     [rsp+0E8h+var_68], 1
0x180002015  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000201c  mov     [rsp+0E8h+pExceptionObject], rax
0x180002021  mov     [rsp+0E8h+var_60], 490h
0x18000202c  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180002033  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180002038  call    _CxxThrowException_0
0x18000203e  jmp     short $+2
0x180002040  mov     ebx, [rsp+0E8h+var_B8]
0x180002044  mov     edi, [rsp+0E8h+arg_8]
0x18000204b  mov     r14, [rsp+0E8h+arg_10]
0x180002053  mov     rsi, [rsp+0E8h+arg_18]
0x18000205b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002062  test    byte ptr [rcx+1Ch], 1
0x180002066  jz      short loc_180002089
0x180002068  cmp     byte ptr [rcx+19h], 4
0x18000206c  jb      short loc_180002089
0x18000206e  mov     r9d, r14d
0x180002071  mov     edx, 42h ; 'B'
0x180002076  mov     [rsp+0E8h+pSid], rsi; pSid
0x18000207b  mov     dword ptr [rsp+0E8h+Size], edi; char
0x18000207f  mov     rcx, [rcx+10h]; LoggerHandle
0x180002083  call    WPP_SF_dd_sid_
0x180002088  nop
0x180002089  mov     rcx, [rsp+0E8h+var_88]; this
0x18000208e  test    rcx, rcx
0x180002091  jz      short loc_180002098
0x180002093  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180002098  mov     eax, ebx
0x18000209a  mov     rbx, [rsp+0E8h+arg_0]
0x1800020a2  add     rsp, 0C0h
0x1800020a9  pop     r15
0x1800020ab  pop     r14
0x1800020ad  pop     r12
0x1800020af  pop     rdi
0x1800020b0  pop     rsi
0x1800020b1  retn
```
