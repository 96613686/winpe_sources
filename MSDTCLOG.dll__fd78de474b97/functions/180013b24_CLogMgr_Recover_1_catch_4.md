# _CLogMgr::_Recover_::_1_::catch$4

- ea: `0x180013b24`
- end: `0x180013ddc`
- name: `_CLogMgr::_Recover_::_1_::catch$4`
- size: `696`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001300`
- `0x18000a1a8`
- `0x18000b06c`
- `0x18000b2c8`
- `0x18000d998`
- `0x18001266c`
- `0x180013b24`
- `0x180015010`

## string_xrefs

- `0x180013bca`: `com\complus\dtc\dtc\log\logmgr\src\logmgr.cpp`

## pseudocode

```c
__int64 __fastcall CLogMgr::_Recover_::_1_::catch_4(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  int v4; // eax
  __int64 v5; // rdi
  unsigned int v6; // eax
  bool v7; // cc
  int v8; // eax
  __int64 v9; // r14
  __int64 v10; // rcx
  unsigned __int16 i; // si
  unsigned __int16 j; // ax

  if ( *(_DWORD *)(a2 + 204) != -2147479510 )
    throw;
  *(_DWORD *)(a2 + 80) = 0;
  *(_OWORD *)(a2 + 240) = 0;
  *(_QWORD *)(a2 + 256) = 0;
  *(_OWORD *)(a2 + 216) = 0;
  *(_QWORD *)(a2 + 232) = 0;
  v3 = *(_QWORD *)(a2 + 160);
  if ( *(_QWORD *)(v3 + 24) )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v3 + 24) + 24LL))(
           *(_QWORD *)(v3 + 24),
           4098,
           4);
    if ( v4 < 0 )
      TraceFile(v4, "failed in m_pIDtcTrace->Trace", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logmgr.cpp", 2633);
  }
  if ( !(unsigned int)CLogStorage::_FindEOF(
                        *(CLogStorage **)(v3 + 392),
                        (unsigned int *)(a2 + 104),
                        (unsigned int *)(a2 + 80),
                        (struct _LOGRECHEADER *)(a2 + 240),
                        (struct _LOGRECHEADER *)(a2 + 216)) )
  {
    *(_DWORD *)(a2 + 152) = -1073737670;
    throw (ulong *)(a2 + 152);
  }
  *(_QWORD *)(a2 + 112) = 0;
  *(_OWORD *)(a2 + 272) = *(_OWORD *)(a2 + 216);
  *(_QWORD *)(a2 + 288) = *(_QWORD *)(a2 + 232);
  v5 = *(_QWORD *)(a2 + 176);
  if ( !(unsigned int)CLogStorage::_FillRSL(*(_QWORD *)(v3 + 392), v5, a2 + 112, a2 + 272) )
  {
    *(_DWORD *)(a2 + 156) = -1073737670;
    throw (ulong *)(a2 + 156);
  }
  v6 = *(_DWORD *)(a2 + 260);
  *(_DWORD *)v5 = v6;
  v7 = v6 <= *(_DWORD *)(a2 + 240);
  v8 = *(_DWORD *)(a2 + 80);
  if ( v7 )
    ++v8;
  *(_DWORD *)(v5 + 4) = v8;
  **(_DWORD **)(a2 + 128) = *(_DWORD *)v5;
  v9 = *(_QWORD *)(a2 + 112);
  CLogStorage::ForceRestart(*(CLogStorage **)(v3 + 392), (struct _RESTARTLOG *)v5, (struct _STRMTBL *)v9);
  v10 = *(_QWORD *)(v3 + 400);
  *(_OWORD *)(v10 + 24) = *(_OWORD *)v5;
  *(_OWORD *)(v10 + 40) = *(_OWORD *)(v5 + 16);
  *(_OWORD *)(v10 + 56) = *(_OWORD *)(v5 + 32);
  *(_OWORD *)(v10 + 72) = *(_OWORD *)(v5 + 48);
  *(_OWORD *)(v10 + 88) = *(_OWORD *)(v5 + 64);
  *(_DWORD *)(v10 + 104) = *(_DWORD *)(v5 + 80);
  if ( *(_QWORD *)(v3 + 296) )
  {
    for ( i = 0; i < *(_WORD *)(*(_QWORD *)(v3 + 400) + 88LL); ++i )
    {
      if ( *(_QWORD *)(44LL * i + *(_QWORD *)(v3 + 296) + 20) )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(44LL * i + *(_QWORD *)(v3 + 296) + 20) + 16LL))(*(_QWORD *)(44LL * i + *(_QWORD *)(v3 + 296) + 20));
        *(_QWORD *)(44LL * i + *(_QWORD *)(v3 + 296) + 20) = 0;
      }
    }
    operator delete(*(void **)(v3 + 296));
  }
  *(_QWORD *)(v3 + 296) = v9;
  for ( j = 0; j < *(_WORD *)(v5 + 64); ++j )
  {
    *(_QWORD *)(v9 + 20) = 0;
    v9 += 44;
  }
  return 0;
}

```

## disassembly

```asm
0x180013b24  mov     [rsp+arg_8], rdx
0x180013b29  push    rbx
0x180013b2a  push    rbp
0x180013b2b  push    rsi
0x180013b2c  push    rdi
0x180013b2d  push    r14
0x180013b2f  sub     rsp, 50h
0x180013b33  mov     rbp, rdx
0x180013b36  cmp     dword ptr [rbp+0CCh], 8000102Ah
0x180013b40  jnz     loc_180013DC6
0x180013b46  mov     dword ptr [rbp+50h], 0
0x180013b4d  xorps   xmm0, xmm0
0x180013b50  xor     eax, eax
0x180013b52  movups  xmmword ptr [rbp+0F0h], xmm0
0x180013b59  mov     [rbp+100h], rax
0x180013b60  xorps   xmm1, xmm1
0x180013b63  movups  xmmword ptr [rbp+0D8h], xmm1
0x180013b6a  mov     [rbp+0E8h], rax
0x180013b71  mov     rbx, [rbp+0A0h]
0x180013b78  cmp     [rbx+18h], rax
0x180013b7c  jz      short loc_180013BDF
0x180013b7e  mov     rax, [rbx+18h]
0x180013b82  mov     rdx, [rax]
0x180013b85  mov     rax, [rdx+18h]
0x180013b89  mov     [rsp+78h+var_40], 0
0x180013b92  mov     [rsp+78h+var_48], 0
0x180013b9b  mov     [rsp+78h+var_50], 0
0x180013ba3  mov     dword ptr [rsp+78h+var_58], 8000D008h
0x180013bab  xor     r9d, r9d
0x180013bae  mov     edx, 1002h
0x180013bb3  lea     r8d, [r9+4]
0x180013bb7  mov     rcx, [rbx+18h]
0x180013bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bc0  test    eax, eax
0x180013bc2  jns     short loc_180013BDF
0x180013bc4  mov     r9d, 0A49h; unsigned int
0x180013bca  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x180013bd1  lea     rdx, aFailedInMPidtc; "failed in m_pIDtcTrace->Trace"
0x180013bd8  mov     ecx, eax; int
0x180013bda  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180013bdf  lea     rax, [rbp+0D8h]
0x180013be6  mov     [rsp+78h+var_58], rax; struct _LOGRECHEADER *
0x180013beb  lea     r9, [rbp+0F0h]; struct _LOGRECHEADER *
0x180013bf2  lea     r8, [rbp+50h]; unsigned int *
0x180013bf6  lea     rdx, [rbp+68h]; unsigned int *
0x180013bfa  mov     rcx, [rbx+188h]; this
0x180013c01  call    ?_FindEOF@CLogStorage@@AEAAHPEAK0PEAU_LOGRECHEADER@@1@Z; CLogStorage::_FindEOF(ulong *,ulong *,_LOGRECHEADER *,_LOGRECHEADER *)
0x180013c06  test    eax, eax
0x180013c08  jnz     short loc_180013C28
0x180013c0a  mov     dword ptr [rbp+98h], 0C000103Ah
0x180013c14  lea     rdx, _TI1K; pThrowInfo
0x180013c1b  lea     rcx, [rbp+98h]; pExceptionObject
0x180013c22  call    _CxxThrowException_0
0x180013c28  mov     qword ptr [rbp+70h], 0
0x180013c30  movups  xmm0, xmmword ptr [rbp+0D8h]
0x180013c37  movaps  xmmword ptr [rbp+110h], xmm0
0x180013c3e  movsd   xmm1, qword ptr [rbp+0E8h]
0x180013c46  movsd   qword ptr [rbp+120h], xmm1
0x180013c4e  lea     r9, [rbp+110h]
0x180013c55  lea     r8, [rbp+70h]
0x180013c59  mov     rdi, [rbp+0B0h]
0x180013c60  mov     rdx, rdi
0x180013c63  mov     rcx, [rbx+188h]
0x180013c6a  call    ?_FillRSL@CLogStorage@@AEAAHPEAU_RESTARTLOG@@PEAPEAU_STRMTBL@@U_LOGRECHEADER@@@Z; CLogStorage::_FillRSL(_RESTARTLOG *,_STRMTBL * *,_LOGRECHEADER)
0x180013c6f  test    eax, eax
0x180013c71  jnz     short loc_180013C91
0x180013c73  mov     dword ptr [rbp+9Ch], 0C000103Ah
0x180013c7d  lea     rdx, _TI1K; pThrowInfo
0x180013c84  lea     rcx, [rbp+9Ch]; pExceptionObject
0x180013c8b  call    _CxxThrowException_0
0x180013c91  mov     eax, [rbp+104h]
0x180013c97  mov     [rdi], eax
0x180013c99  cmp     eax, [rbp+0F0h]
0x180013c9f  mov     eax, [rbp+50h]
0x180013ca2  ja      short loc_180013CA6
0x180013ca4  inc     eax
0x180013ca6  mov     [rdi+4], eax
0x180013ca9  mov     ecx, [rdi]
0x180013cab  mov     rax, [rbp+80h]
0x180013cb2  mov     [rax], ecx
0x180013cb4  mov     r14, [rbp+70h]
0x180013cb8  mov     r8, r14; struct _STRMTBL *
0x180013cbb  mov     rdx, rdi; struct _RESTARTLOG *
0x180013cbe  mov     rcx, [rbx+188h]; this
0x180013cc5  call    ?ForceRestart@CLogStorage@@QEAAXPEAU_RESTARTLOG@@PEAU_STRMTBL@@@Z; CLogStorage::ForceRestart(_RESTARTLOG *,_STRMTBL *)
0x180013cca  mov     rcx, [rbx+190h]
0x180013cd1  movaps  xmm0, xmmword ptr [rdi]
0x180013cd4  movups  xmmword ptr [rcx+18h], xmm0
0x180013cd8  movaps  xmm1, xmmword ptr [rdi+10h]
0x180013cdc  movups  xmmword ptr [rcx+28h], xmm1
0x180013ce0  movaps  xmm0, xmmword ptr [rdi+20h]
0x180013ce4  movups  xmmword ptr [rcx+38h], xmm0
0x180013ce8  movaps  xmm1, xmmword ptr [rdi+30h]
0x180013cec  movups  xmmword ptr [rcx+48h], xmm1
0x180013cf0  movaps  xmm0, xmmword ptr [rdi+40h]
0x180013cf4  movups  xmmword ptr [rcx+58h], xmm0
0x180013cf8  mov     eax, [rdi+50h]
0x180013cfb  mov     [rcx+68h], eax
0x180013cfe  cmp     qword ptr [rbx+128h], 0
0x180013d06  jz      loc_180013D98
0x180013d0c  xor     esi, esi
0x180013d0e  mov     rax, [rbx+190h]
0x180013d15  xor     ecx, ecx
0x180013d17  cmp     cx, [rax+58h]
0x180013d1b  jnb     short loc_180013D8C
0x180013d1d  movzx   eax, si
0x180013d20  imul    rcx, rax, 2Ch ; ','
0x180013d24  mov     rax, [rbx+128h]
0x180013d2b  cmp     qword ptr [rcx+rax+14h], 0
0x180013d31  jz      short loc_180013D7C
0x180013d33  movzx   eax, si
0x180013d36  imul    rcx, rax, 2Ch ; ','
0x180013d3a  mov     rax, [rbx+128h]
0x180013d41  mov     rcx, [rcx+rax+14h]
0x180013d46  mov     rdx, [rcx]
0x180013d49  movzx   eax, si
0x180013d4c  imul    r8, rax, 2Ch ; ','
0x180013d50  mov     rcx, [rbx+128h]
0x180013d57  mov     rcx, [r8+rcx+14h]
0x180013d5c  mov     rax, [rdx+10h]
0x180013d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d65  movzx   eax, si
0x180013d68  imul    rcx, rax, 2Ch ; ','
0x180013d6c  mov     rax, [rbx+128h]
0x180013d73  mov     qword ptr [rcx+rax+14h], 0
0x180013d7c  inc     si
0x180013d7f  mov     rax, [rbx+190h]
0x180013d86  cmp     si, [rax+58h]
0x180013d8a  jb      short loc_180013D1D
0x180013d8c  mov     rcx, [rbx+128h]; Block
0x180013d93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013d98  mov     [rbx+128h], r14
0x180013d9f  xor     eax, eax
0x180013da1  xor     ecx, ecx
0x180013da3  cmp     cx, [rdi+40h]
0x180013da7  jnb     short loc_180013DBA
0x180013da9  mov     [r14+14h], rcx
0x180013dad  lea     r14, [r14+2Ch]
0x180013db1  inc     ax
0x180013db4  cmp     ax, [rdi+40h]
0x180013db8  jb      short loc_180013DA9
0x180013dba  mov     rax, 0
0x180013dc4  jmp     short loc_180013DD0
0x180013dc6  xor     edx, edx; pThrowInfo
0x180013dc8  xor     ecx, ecx; pExceptionObject
0x180013dca  call    _CxxThrowException_0
0x180013dd0  add     rsp, 50h
0x180013dd4  pop     r14
0x180013dd6  pop     rdi
0x180013dd7  pop     rsi
0x180013dd8  pop     rbp
0x180013dd9  pop     rbx
0x180013dda  retn
```
