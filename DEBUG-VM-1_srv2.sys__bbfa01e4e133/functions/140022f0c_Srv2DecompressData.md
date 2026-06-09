# Srv2DecompressData

- ea: `0x140022f0c`
- end: `0x14002327a`
- name: `Srv2DecompressData`
- size: `878`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400055b0`
- `0x140019168`
- `0x14005d3d0`

## callees

- `0x14001d724`
- `0x1400224b8`
- `0x140022ad8`
- `0x140022f0c`
- `0x140023280`
- `0x1400232cc`
- `0x140038680`
- `0x14005d67c`

## import_xrefs

- `srvnet!SmbCompressionLegacyDecompress` at `0x14002319d`
- `srvnet!SmbCompressionLegacyDecompress` at `0x14002319d`
- `srvnet!SmbCompressionChainedDecompress` at `0x140023159`
- `srvnet!SmbCompressionChainedDecompress` at `0x140023159`
- `srvnet!SrvNetFreeBuffer` at `0x14002325a`
- `srvnet!SrvNetFreeBuffer` at `0x14002325a`
- `srvnet!SrvNetAllocateBuffer` at `0x1400230e0`
- `srvnet!SrvNetAllocateBuffer` at `0x1400230e0`

## pseudocode

```c
__int64 __fastcall Srv2DecompressData(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // r13
  __int64 v9; // rax
  unsigned int v10; // ebp
  unsigned int v11; // r15d
  size_t v12; // r14
  __int16 v13; // r12
  int v14; // eax
  __int64 v15; // r9
  __int64 Buffer; // rax
  __int64 v17; // rsi
  __int64 v18; // rcx
  int v19; // r9d
  unsigned int v20; // r10d
  int v21; // r15d
  __int64 v22; // r9
  int v24; // [rsp+80h] [rbp+8h] BYREF

  v3 = a1[70];
  v24 = 0;
  v5 = a1[38];
  if ( *(_DWORD *)(v5 + 36) >= 0x10u )
  {
    v8 = *(_QWORD *)(a1[12] + 496LL);
    v9 = *(_QWORD *)(v5 + 24);
    v10 = *(_DWORD *)(v9 + 4);
    v11 = *(unsigned __int16 *)(v9 + 8);
    v12 = *(unsigned int *)(v9 + 12);
    v13 = *(_WORD *)(v9 + 10) & 1;
    if ( v13 )
    {
      v15 = v10;
    }
    else
    {
      if ( v11 - 1 > 0x1E )
      {
        v6 = -1073739509;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) )
            WPP_SF_H(WPP_GLOBAL_Control->AttachedDevice, 10, a3, (unsigned __int16)v11);
        }
        v7 = 1;
        goto LABEL_3;
      }
      v14 = *(_DWORD *)(v8 + 152);
      a2 = (unsigned __int8)(v11 - 1);
      if ( !_bittest(&v14, a2) )
      {
        v6 = -1073739509;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_H(WPP_GLOBAL_Control->AttachedDevice, 11, a3, (unsigned __int16)v11);
        }
        v7 = 2;
        goto LABEL_3;
      }
      v15 = (unsigned int)v12 + v10;
      if ( (unsigned int)v15 < v10 )
      {
        v6 = -1073739509;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_b835c930a0933e72ac52d79928636e31_Traceguids, v10, v12);
        }
        v7 = 3;
        goto LABEL_3;
      }
    }
    if ( (unsigned int)v15 > (unsigned __int64)(unsigned int)(*(_DWORD *)(v8 + 36) + 256) + 52 )
    {
      v6 = -1073739509;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_b835c930a0933e72ac52d79928636e31_Traceguids, v15);
      }
      v7 = 4;
      goto LABEL_3;
    }
    Buffer = SrvNetAllocateBuffer((unsigned int)v15, 0);
    v17 = Buffer;
    if ( !Buffer )
    {
      v6 = -1073741670;
      v7 = 5;
      goto LABEL_3;
    }
    v18 = a1[38];
    v19 = *(_DWORD *)(v18 + 36);
    if ( v13 )
    {
      v20 = v19 - 8;
    }
    else
    {
      if ( v19 - 16 < (unsigned int)v12 )
      {
        v6 = -1073739509;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_LLL(WPP_GLOBAL_Control->AttachedDevice);
        }
        v22 = 6;
LABEL_51:
        Smb2LkmdTelCollectParsingFailure2(v3, a2, 21, v22);
        SrvNetFreeBuffer(v17);
        return v6;
      }
      v20 = v19 - 16 - v12;
    }
    if ( v13 )
    {
      v21 = SmbCompressionChainedDecompress(
              *(_QWORD *)(v18 + 24) + 8LL,
              v20,
              *(_QWORD *)(Buffer + 24),
              v10,
              &v24,
              *(_DWORD *)(v8 + 152));
      *(_DWORD *)(v17 + 36) = v24;
    }
    else
    {
      v21 = SmbCompressionLegacyDecompress(
              v11,
              v12 + *(_QWORD *)(v18 + 24) + 16LL,
              v20,
              v12 + *(_QWORD *)(Buffer + 24),
              v10,
              &v24);
      if ( (_DWORD)v12 )
        memmove(*(void **)(v17 + 24), (const void *)(*(_QWORD *)(a1[38] + 24LL) + 16LL), v12);
      *(_DWORD *)(v17 + 36) = v12 + v24;
    }
    if ( v21 >= 0 )
    {
      if ( v24 == v10 )
      {
        Srv2ReplaceReceiveBuffer(a1, v17);
        return 0;
      }
      v6 = -1073739509;
      v22 = 8;
    }
    else
    {
      v6 = -1073739509;
      v22 = 7;
    }
    goto LABEL_51;
  }
  v6 = -1073739509;
  v7 = 0;
LABEL_3:
  Smb2LkmdTelCollectParsingFailure2(v3, a2, 21, v7);
  return v6;
}

```

## disassembly

```asm
0x140022f0c  mov     rax, rsp
0x140022f0f  push    rbx
0x140022f10  push    rbp
0x140022f11  push    rsi
0x140022f12  push    rdi
0x140022f13  push    r12
0x140022f15  push    r13
0x140022f17  push    r14
0x140022f19  push    r15
0x140022f1b  sub     rsp, 38h
0x140022f1f  mov     rdi, [rcx+230h]
0x140022f26  xor     r13d, r13d
0x140022f29  mov     rbx, rcx
0x140022f2c  mov     [rax+8], r13d
0x140022f30  mov     rcx, [rcx+130h]
0x140022f37  cmp     dword ptr [rcx+24h], 10h
0x140022f3b  jnb     short loc_140022F58
0x140022f3d  mov     ebx, 0C000090Bh
0x140022f42  xor     r9d, r9d
0x140022f45  mov     r8d, 15h
0x140022f4b  mov     rcx, rdi
0x140022f4e  call    Smb2LkmdTelCollectParsingFailure2
0x140022f53  jmp     loc_140023266
0x140022f58  mov     rax, [rbx+60h]
0x140022f5c  mov     esi, 1
0x140022f61  mov     r13, [rax+1F0h]
0x140022f68  mov     rax, [rcx+18h]
0x140022f6c  movzx   r12d, word ptr [rax+0Ah]
0x140022f71  mov     ebp, [rax+4]
0x140022f74  movzx   r15d, word ptr [rax+8]
0x140022f79  mov     r14d, [rax+0Ch]
0x140022f7d  and     r12w, si
0x140022f81  jnz     loc_14002307C
0x140022f87  lea     eax, [r15-1]
0x140022f8b  mov     ecx, r15d
0x140022f8e  cmp     eax, 1Eh
0x140022f91  jbe     short loc_140022FD1
0x140022f93  mov     ebx, 0C000090Bh
0x140022f98  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140022f9f  lea     rax, WPP_GLOBAL_Control
0x140022fa6  cmp     rcx, rax
0x140022fa9  jz      short loc_140022FC9
0x140022fab  mov     eax, [rcx+2Ch]
0x140022fae  test    sil, al
0x140022fb1  jz      short loc_140022FC9
0x140022fb3  cmp     [rcx+29h], sil
0x140022fb7  jb      short loc_140022FC9
0x140022fb9  mov     rcx, [rcx+18h]
0x140022fbd  lea     edx, [rsi+9]
0x140022fc0  movzx   r9d, r15w
0x140022fc4  call    WPP_SF_H
0x140022fc9  mov     r9d, esi
0x140022fcc  jmp     loc_140022F45
0x140022fd1  mov     eax, [r13+98h]
0x140022fd8  dec     ecx
0x140022fda  movzx   edx, cl
0x140022fdd  bt      eax, edx
0x140022fe0  jb      short loc_140023025
0x140022fe2  mov     ebx, 0C000090Bh
0x140022fe7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140022fee  lea     rax, WPP_GLOBAL_Control
0x140022ff5  cmp     rcx, rax
0x140022ff8  jz      short loc_14002301A
0x140022ffa  mov     eax, [rcx+2Ch]
0x140022ffd  test    sil, al
0x140023000  jz      short loc_14002301A
0x140023002  cmp     [rcx+29h], sil
0x140023006  jb      short loc_14002301A
0x140023008  mov     rcx, [rcx+18h]
0x14002300c  mov     edx, 0Bh
0x140023011  movzx   r9d, r15w
0x140023015  call    WPP_SF_H
0x14002301a  mov     r9d, 2
0x140023020  jmp     loc_140022F45
0x140023025  lea     r9d, [r14+rbp]
0x140023029  cmp     r9d, ebp
0x14002302c  jnb     short loc_14002307F
0x14002302e  mov     ebx, 0C000090Bh
0x140023033  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002303a  lea     rax, WPP_GLOBAL_Control
0x140023041  cmp     rcx, rax
0x140023044  jz      short loc_140023071
0x140023046  mov     eax, [rcx+2Ch]
0x140023049  test    sil, al
0x14002304c  jz      short loc_140023071
0x14002304e  cmp     [rcx+29h], sil
0x140023052  jb      short loc_140023071
0x140023054  mov     rcx, [rcx+18h]
0x140023058  lea     r8, WPP_b835c930a0933e72ac52d79928636e31_Traceguids
0x14002305f  mov     edx, 0Ch
0x140023064  mov     dword ptr [rsp+78h+var_58], r14d
0x140023069  mov     r9d, ebp
0x14002306c  call    WPP_SF_DD
0x140023071  mov     r9d, 3
0x140023077  jmp     loc_140022F45
0x14002307c  mov     r9d, ebp
0x14002307f  mov     ecx, [r13+24h]
0x140023083  add     ecx, 100h
0x140023089  mov     r8d, r9d
0x14002308c  add     rcx, 34h ; '4'
0x140023090  cmp     r8, rcx
0x140023093  jbe     short loc_1400230DB
0x140023095  mov     ebx, 0C000090Bh
0x14002309a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400230a1  lea     rax, WPP_GLOBAL_Control
0x1400230a8  cmp     rcx, rax
0x1400230ab  jz      short loc_1400230D0
0x1400230ad  mov     eax, [rcx+2Ch]
0x1400230b0  test    sil, al
0x1400230b3  jz      short loc_1400230D0
0x1400230b5  cmp     [rcx+29h], sil
0x1400230b9  jb      short loc_1400230D0
0x1400230bb  mov     rcx, [rcx+18h]
0x1400230bf  lea     r8, WPP_b835c930a0933e72ac52d79928636e31_Traceguids
0x1400230c6  mov     edx, 0Dh
0x1400230cb  call    WPP_SF_d
0x1400230d0  mov     r9d, 4
0x1400230d6  jmp     loc_140022F45
0x1400230db  xor     edx, edx
0x1400230dd  mov     rcx, r8
0x1400230e0  call    cs:__imp_SrvNetAllocateBuffer
0x1400230e7  nop     dword ptr [rax+rax+00h]
0x1400230ec  mov     rsi, rax
0x1400230ef  test    rax, rax
0x1400230f2  jnz     short loc_140023102
0x1400230f4  mov     ebx, 0C000009Ah
0x1400230f9  lea     r9d, [rax+5]
0x1400230fd  jmp     loc_140022F45
0x140023102  mov     rcx, [rbx+130h]
0x140023109  mov     r9d, [rcx+24h]
0x14002310d  test    r12w, r12w
0x140023111  jz      short loc_140023119
0x140023113  lea     r10d, [r9-8]
0x140023117  jmp     short loc_140023129
0x140023119  lea     r10d, [r9-10h]
0x14002311d  cmp     r10d, r14d
0x140023120  jb      loc_140023210
0x140023126  sub     r10d, r14d
0x140023129  test    r12w, r12w
0x14002312d  jz      short loc_140023174
0x14002312f  mov     eax, [r13+98h]
0x140023136  mov     r9d, ebp
0x140023139  mov     rcx, [rcx+18h]
0x14002313d  mov     edx, r10d
0x140023140  mov     r8, [rsi+18h]
0x140023144  add     rcx, 8
0x140023148  mov     dword ptr [rsp+78h+var_50], eax
0x14002314c  lea     rax, [rsp+78h+arg_0]
0x140023154  mov     [rsp+78h+var_58], rax
0x140023159  call    cs:__imp_SmbCompressionChainedDecompress
0x140023160  nop     dword ptr [rax+rax+00h]
0x140023165  mov     r15d, eax
0x140023168  mov     eax, [rsp+78h+arg_0]
0x14002316f  mov     [rsi+24h], eax
0x140023172  jmp     short loc_1400231D9
0x140023174  mov     rdx, [rcx+18h]
0x140023178  lea     rax, [rsp+78h+arg_0]
0x140023180  mov     r9, [rsi+18h]
0x140023184  add     rdx, 10h
0x140023188  mov     [rsp+78h+var_50], rax
0x14002318d  add     rdx, r14
0x140023190  add     r9, r14
0x140023193  mov     dword ptr [rsp+78h+var_58], ebp
0x140023197  mov     ecx, r15d
0x14002319a  mov     r8d, r10d
0x14002319d  call    cs:__imp_SmbCompressionLegacyDecompress
0x1400231a4  nop     dword ptr [rax+rax+00h]
0x1400231a9  mov     r15d, eax
0x1400231ac  test    r14d, r14d
0x1400231af  jz      short loc_1400231CC
0x1400231b1  mov     rax, [rbx+130h]
0x1400231b8  mov     r8, r14; Size
0x1400231bb  mov     rcx, [rsi+18h]; void *
0x1400231bf  mov     rdx, [rax+18h]
0x1400231c3  add     rdx, 10h; Src
0x1400231c7  call    memmove
0x1400231cc  mov     ecx, [rsp+78h+arg_0]
0x1400231d3  add     ecx, r14d
0x1400231d6  mov     [rsi+24h], ecx
0x1400231d9  test    r15d, r15d
0x1400231dc  jns     short loc_1400231EB
0x1400231de  mov     ebx, 0C000090Bh
0x1400231e3  mov     r9d, 7
0x1400231e9  jmp     short loc_140023249
0x1400231eb  cmp     [rsp+78h+arg_0], ebp
0x1400231f2  jz      short loc_140023201
0x1400231f4  mov     ebx, 0C000090Bh
0x1400231f9  mov     r9d, 8
0x1400231ff  jmp     short loc_140023249
0x140023201  mov     rdx, rsi
0x140023204  mov     rcx, rbx
0x140023207  call    Srv2ReplaceReceiveBuffer
0x14002320c  xor     eax, eax
0x14002320e  jmp     short loc_140023268
0x140023210  mov     ebx, 0C000090Bh
0x140023215  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002321c  lea     rax, WPP_GLOBAL_Control
0x140023223  cmp     rcx, rax
0x140023226  jz      short loc_140023243
0x140023228  mov     eax, [rcx+2Ch]
0x14002322b  test    al, 1
0x14002322d  jz      short loc_140023243
0x14002322f  cmp     byte ptr [rcx+29h], 1
0x140023233  jb      short loc_140023243
0x140023235  mov     rcx, [rcx+18h]
0x140023239  mov     dword ptr [rsp+78h+var_50], r14d
0x14002323e  call    WPP_SF_LLL
0x140023243  mov     r9d, 6
0x140023249  mov     r8d, 15h
0x14002324f  mov     rcx, rdi
0x140023252  call    Smb2LkmdTelCollectParsingFailure2
0x140023257  mov     rcx, rsi
0x14002325a  call    cs:__imp_SrvNetFreeBuffer
0x140023261  nop     dword ptr [rax+rax+00h]
0x140023266  mov     eax, ebx
0x140023268  add     rsp, 38h
0x14002326c  pop     r15
0x14002326e  pop     r14
0x140023270  pop     r13
0x140023272  pop     r12
0x140023274  pop     rdi
0x140023275  pop     rsi
0x140023276  pop     rbp
0x140023277  pop     rbx
0x140023278  retn
```
