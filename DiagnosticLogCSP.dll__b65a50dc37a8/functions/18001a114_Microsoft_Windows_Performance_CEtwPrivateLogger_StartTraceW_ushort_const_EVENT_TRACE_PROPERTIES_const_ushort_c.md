# Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(ushort const *,_EVENT_TRACE_PROPERTIES const *,ushort const *,ulong,void *)

- ea: `0x18001a114`
- end: `0x18001a4b6`
- name: `?StartTraceW@CEtwPrivateLogger@Performance@Windows@Microsoft@@QEAAJPEBGPEBU_EVENT_TRACE_PROPERTIES@@0KPEAX@Z`
- size: `930`
- prototype: `__int64 __usercall@<rax>(PTRACEHANDLE TraceHandle@<rcx>, const unsigned __int16 *@<rdx>, const struct _EVENT_TRACE_PROPERTIES *@<r8>, const unsigned __int16 *@<r9>, unsigned int, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017648`

## callees

- `0x180001b90`
- `0x18000265c`
- `0x180002d25`
- `0x180011308`
- `0x18001629c`
- `0x18001a114`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001a410`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001a44d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001a410`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001a44d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001a286`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001a286`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001a1d1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001a1d1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001a1b6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001a38a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001a3a9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001a1b6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001a38a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001a3a9`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18001a437`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18001a437`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18001a3f0`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18001a3f0`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18001a461`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18001a461`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(
        PTRACEHANDLE TraceHandle,
        const unsigned __int16 *a2,
        const struct _EVENT_TRACE_PROPERTIES *a3,
        const unsigned __int16 *a4,
        unsigned int Size,
        void *a6)
{
  __int64 result; // rax
  __int64 v9; // r14
  OLECHAR *v10; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // r9
  unsigned int v13; // edi
  int v14; // ecx
  unsigned __int64 v15; // r12
  unsigned __int64 v16; // rax
  unsigned int v17; // esi
  void *v18; // rax
  __int128 v19; // xmm1
  __int128 v20; // xmm2
  __int128 v21; // xmm3
  __int128 v22; // xmm4
  __int128 v23; // xmm5
  __int128 v24; // xmm6
  __int64 v25; // xmm7_8
  ULONG64 v26; // rax
  _WORD *v27; // rax
  _WORD *v28; // rcx
  HRESULT Guid; // edi
  ULONG64 v30; // rax
  ULONG v31; // eax
  ULONG started; // edi
  _QWORD pguid[3]; // [rsp+50h] [rbp-91h] BYREF
  OLECHAR sz[8]; // [rsp+68h] [rbp-79h] BYREF
  __int128 v36; // [rsp+78h] [rbp-69h]
  __int128 v37; // [rsp+88h] [rbp-59h]
  _OWORD v38[2]; // [rsp+98h] [rbp-49h]

  if ( Size && !a6 )
    return 2147942487LL;
  *(_OWORD *)sz = *(_OWORD *)L"{28ad2447-105b-4fe2-9599-e59b2aa9a634}";
  v37 = *(_OWORD *)L"fe2-9599-e59b2aa9a634}";
  v36 = *(_OWORD *)L"7-105b-4fe2-9599-e59b2aa9a634}";
  v38[0] = *(_OWORD *)L"-e59b2aa9a634}";
  *(_OWORD *)((char *)v38 + 14) = *(_OWORD *)L"a9a634}";
  *(_OWORD *)&pguid[1] = 0;
  CoCreateGuid((GUID *)&pguid[1]);
  StringFromGUID2((const GUID *const)&pguid[1], sz, 39);
  v9 = 1024;
  v10 = sz;
  v11 = 1024;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  result = v11 == 0 ? 0x80070057 : 0;
  v12 = (1024 - v11) & -(__int64)(v11 != 0);
  if ( !v11 )
    return result;
  if ( v12 > 0xFFFFFFFF )
    return 2147942934LL;
  v13 = Size + 120;
  if ( Size >= 0xFFFFFF88 )
    return 2147942934LL;
  if ( (v13 & 1) != 0 )
  {
    v14 = v13 & 1;
    if ( v13 - v14 + 2 >= v13 )
    {
      v13 = v13 - v14 + 2;
      goto LABEL_13;
    }
    return 2147942934LL;
  }
LABEL_13:
  v15 = (unsigned int)v12;
  v16 = 2LL * (unsigned int)v12;
  if ( v16 > 0xFFFFFFFF )
    return 2147942934LL;
  v17 = v16 + v13;
  if ( (unsigned int)v16 + v13 < v13 || v17 + 2048 < v17 )
    return 2147942934LL;
  pguid[1] = v17 + 2048;
  v18 = malloc(pguid[1]);
  TraceHandle[1] = (ULONG64)v18;
  if ( !v18 )
    return 2147942414LL;
  memset_0(v18, 0, pguid[1]);
  v19 = *(_OWORD *)&a3->Wnode.CountLost;
  v20 = *(_OWORD *)a3->Wnode.Guid.Data4;
  v21 = *(_OWORD *)&a3->BufferSize;
  v22 = *(_OWORD *)&a3->LogFileMode;
  v23 = *(_OWORD *)&a3->NumberOfBuffers;
  v24 = *(_OWORD *)&a3->LogBuffersLost;
  v25 = *(_QWORD *)&a3->LogFileNameOffset;
  v26 = TraceHandle[1];
  *(_OWORD *)v26 = *(_OWORD *)&a3->Wnode.BufferSize;
  *(_OWORD *)(v26 + 16) = v19;
  *(_OWORD *)(v26 + 32) = v20;
  *(_OWORD *)(v26 + 48) = v21;
  *(_OWORD *)(v26 + 64) = v22;
  *(_OWORD *)(v26 + 80) = v23;
  *(_OWORD *)(v26 + 96) = v24;
  *(_QWORD *)(v26 + 112) = v25;
  *(_DWORD *)TraceHandle[1] = v17 + 2048;
  *(_DWORD *)(TraceHandle[1] + 44) = 0x20000;
  *(_DWORD *)(TraceHandle[1] + 116) = v13;
  *(_DWORD *)(TraceHandle[1] + 112) = v17;
  if ( a6 )
    memcpy_0((void *)(TraceHandle[1] + 120), a6, Size);
  StringCchCopyNW((unsigned __int16 *)(TraceHandle[1] + v13), v15, sz, v15);
  v27 = (_WORD *)(TraceHandle[1] + v17);
  do
  {
    if ( !*a2 )
      break;
    *v27++ = *a2++;
    --v9;
  }
  while ( v9 );
  v28 = v27 - 1;
  if ( v9 )
    v28 = v27;
  *v28 = 0;
  Guid = CoCreateGuid((GUID *)TraceHandle + 2);
  if ( Guid < 0 || (Guid = CoCreateGuid((GUID *)TraceHandle + 3), Guid < 0) )
  {
    v30 = TraceHandle[1];
LABEL_29:
    free((void *)v30);
    result = (unsigned int)Guid;
    TraceHandle[1] = 0;
    return result;
  }
  TraceHandle[3] = 0;
  TraceHandle[2] = (ULONG64)(TraceHandle + 6);
  v31 = RegisterTraceGuidsW(
          CArchiveDefinitionNode::PersistRollbackMoveState,
          0,
          (LPCGUID)TraceHandle + 2,
          1u,
          (PTRACE_GUID_REGISTRATION)TraceHandle + 1,
          0,
          0,
          TraceHandle + 8);
  Guid = ATL::AtlHresultFromWin32(v31);
  v30 = TraceHandle[1];
  if ( Guid < 0 )
    goto LABEL_29;
  *(_OWORD *)(v30 + 24) = *((_OWORD *)TraceHandle + 2);
  started = StartTraceW(TraceHandle, sz, (PEVENT_TRACE_PROPERTIES)TraceHandle[1]);
  if ( started )
  {
    free((void *)TraceHandle[1]);
    TraceHandle[1] = 0;
    if ( !UnregisterTraceGuids(TraceHandle[8]) )
      TraceHandle[8] = -1;
  }
  return ATL::AtlHresultFromWin32(started);
}

```

## disassembly

```asm
0x18001a114  mov     rax, rsp
0x18001a117  push    rbp
0x18001a118  push    rbx
0x18001a119  push    rsi
0x18001a11a  push    rdi
0x18001a11b  push    r12
0x18001a11d  push    r13
0x18001a11f  push    r14
0x18001a121  push    r15
0x18001a123  lea     rbp, [rax-4Fh]
0x18001a127  sub     rsp, 0E8h
0x18001a12e  movaps  xmmword ptr [rax-58h], xmm6
0x18001a132  movaps  xmmword ptr [rax-68h], xmm7
0x18001a136  mov     rax, cs:__security_cookie
0x18001a13d  xor     rax, rsp
0x18001a140  mov     [rbp+47h+var_70], rax
0x18001a144  mov     r13d, dword ptr [rbp+47h+Size]
0x18001a148  xor     edi, edi
0x18001a14a  mov     rax, [rbp+47h+arg_28]
0x18001a14e  mov     r15, rdx
0x18001a151  mov     [rsp+120h+var_E0], r8
0x18001a156  mov     rbx, rcx
0x18001a159  mov     qword ptr [rsp+120h+pguid], rax
0x18001a15e  test    r13d, r13d
0x18001a161  jz      short loc_18001A172
0x18001a163  test    rax, rax
0x18001a166  jnz     short loc_18001A172
0x18001a168  mov     eax, 80070057h
0x18001a16d  jmp     loc_18001A487
0x18001a172  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f; "{28ad2447-105b-4fe2-9599-e59b2aa9a634}"
0x18001a179  lea     rcx, [rsp+120h+pguid+8]; pguid
0x18001a17e  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+10h; "7-105b-4fe2-9599-e59b2aa9a634}"
0x18001a185  movaps  xmmword ptr [rbp+47h+sz], xmm0
0x18001a189  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f+20h; "fe2-9599-e59b2aa9a634}"
0x18001a190  movaps  [rbp+47h+var_A0], xmm0
0x18001a194  movups  xmm0, xmmword ptr cs:a28ad2447105b4f+3Eh; "a9a634}"
0x18001a19b  movaps  [rbp+47h+var_B0], xmm1
0x18001a19f  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+30h; "-e59b2aa9a634}"
0x18001a1a6  movaps  xmmword ptr [rbp+47h+var_90], xmm1
0x18001a1aa  movups  xmmword ptr [rbp+47h+var_90+0Eh], xmm0
0x18001a1ae  xorps   xmm0, xmm0
0x18001a1b1  movups  xmmword ptr [rsp+120h+pguid+8], xmm0
0x18001a1b6  call    cs:__imp_CoCreateGuid
0x18001a1bd  nop     dword ptr [rax+rax+00h]
0x18001a1c2  mov     r8d, 27h ; '''; cchMax
0x18001a1c8  lea     rdx, [rbp+47h+sz]; lpsz
0x18001a1cc  lea     rcx, [rsp+120h+pguid+8]; rguid
0x18001a1d1  call    cs:__imp_StringFromGUID2
0x18001a1d8  nop     dword ptr [rax+rax+00h]
0x18001a1dd  mov     r14d, 400h
0x18001a1e3  lea     rax, [rbp+47h+sz]
0x18001a1e7  mov     r8d, r14d
0x18001a1ea  cmp     [rax], di
0x18001a1ed  jz      short loc_18001A1F9
0x18001a1ef  add     rax, 2
0x18001a1f3  sub     r8, 1
0x18001a1f7  jnz     short loc_18001A1EA
0x18001a1f9  mov     rax, r8
0x18001a1fc  mov     rdx, r14
0x18001a1ff  neg     rax
0x18001a202  mov     rcx, r8
0x18001a205  sbb     eax, eax
0x18001a207  sub     rdx, r8
0x18001a20a  not     eax
0x18001a20c  and     eax, 80070057h
0x18001a211  neg     rcx
0x18001a214  sbb     r9, r9
0x18001a217  and     r9, rdx
0x18001a21a  test    r8, r8
0x18001a21d  jz      loc_18001A487
0x18001a223  mov     edx, 0FFFFFFFFh
0x18001a228  cmp     r9, rdx
0x18001a22b  ja      loc_18001A482
0x18001a231  lea     edi, [r13+78h]
0x18001a235  cmp     edi, 78h ; 'x'
0x18001a238  jb      loc_18001A482
0x18001a23e  mov     ecx, edi
0x18001a240  and     ecx, 1
0x18001a243  jz      short loc_18001A256
0x18001a245  mov     eax, edi
0x18001a247  sub     eax, ecx
0x18001a249  add     eax, 2
0x18001a24c  cmp     eax, edi
0x18001a24e  jb      loc_18001A482
0x18001a254  mov     edi, eax
0x18001a256  mov     r12d, r9d
0x18001a259  lea     rax, [r12+r12]
0x18001a25d  cmp     rax, rdx
0x18001a260  ja      loc_18001A482
0x18001a266  lea     esi, [rax+rdi]
0x18001a269  cmp     esi, edi
0x18001a26b  jb      loc_18001A482
0x18001a271  lea     eax, [rsi+800h]
0x18001a277  cmp     eax, esi
0x18001a279  jb      loc_18001A482
0x18001a27f  mov     ecx, eax; Size
0x18001a281  mov     qword ptr [rsp+120h+pguid+8], rax
0x18001a286  call    cs:__imp_malloc
0x18001a28d  nop     dword ptr [rax+rax+00h]
0x18001a292  mov     [rbx+8], rax
0x18001a296  test    rax, rax
0x18001a299  jnz     short loc_18001A2A5
0x18001a29b  mov     eax, 8007000Eh
0x18001a2a0  jmp     loc_18001A487
0x18001a2a5  mov     r8, qword ptr [rsp+120h+pguid+8]; Size
0x18001a2aa  xor     edx, edx; Val
0x18001a2ac  mov     rcx, rax; void *
0x18001a2af  call    memset_0
0x18001a2b4  mov     rax, [rsp+120h+var_E0]
0x18001a2b9  lea     ecx, [rsi+800h]
0x18001a2bf  mov     rdx, qword ptr [rsp+120h+pguid]; Src
0x18001a2c4  movaps  xmm0, xmmword ptr [rax]
0x18001a2c7  movaps  xmm1, xmmword ptr [rax+10h]
0x18001a2cb  movaps  xmm2, xmmword ptr [rax+20h]
0x18001a2cf  movaps  xmm3, xmmword ptr [rax+30h]
0x18001a2d3  movaps  xmm4, xmmword ptr [rax+40h]
0x18001a2d7  movaps  xmm5, xmmword ptr [rax+50h]
0x18001a2db  movaps  xmm6, xmmword ptr [rax+60h]
0x18001a2df  movsd   xmm7, qword ptr [rax+70h]
0x18001a2e4  mov     rax, [rbx+8]
0x18001a2e8  movups  xmmword ptr [rax], xmm0
0x18001a2eb  movups  xmmword ptr [rax+10h], xmm1
0x18001a2ef  movups  xmmword ptr [rax+20h], xmm2
0x18001a2f3  movups  xmmword ptr [rax+30h], xmm3
0x18001a2f7  movups  xmmword ptr [rax+40h], xmm4
0x18001a2fb  movups  xmmword ptr [rax+50h], xmm5
0x18001a2ff  movups  xmmword ptr [rax+60h], xmm6
0x18001a303  movsd   qword ptr [rax+70h], xmm7
0x18001a308  mov     rax, [rbx+8]
0x18001a30c  mov     [rax], ecx
0x18001a30e  mov     rax, [rbx+8]
0x18001a312  mov     dword ptr [rax+2Ch], 20000h
0x18001a319  mov     rax, [rbx+8]
0x18001a31d  mov     [rax+74h], edi
0x18001a320  mov     rax, [rbx+8]
0x18001a324  mov     [rax+70h], esi
0x18001a327  test    rdx, rdx
0x18001a32a  jz      short loc_18001A33C
0x18001a32c  mov     rcx, [rbx+8]
0x18001a330  mov     r8, r13; Size
0x18001a333  add     rcx, 78h ; 'x'; void *
0x18001a337  call    memcpy_0
0x18001a33c  mov     ecx, edi
0x18001a33e  lea     r8, [rbp+47h+sz]; unsigned __int16 *
0x18001a342  add     rcx, [rbx+8]; unsigned __int16 *
0x18001a346  mov     r9, r12; unsigned __int64
0x18001a349  mov     rdx, r12; unsigned __int64
0x18001a34c  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001a351  mov     eax, esi
0x18001a353  add     rax, [rbx+8]
0x18001a357  xor     r12d, r12d
0x18001a35a  movzx   ecx, word ptr [r15]
0x18001a35e  test    cx, cx
0x18001a361  jz      short loc_18001A374
0x18001a363  mov     [rax], cx
0x18001a366  add     r15, 2
0x18001a36a  add     rax, 2
0x18001a36e  sub     r14, 1
0x18001a372  jnz     short loc_18001A35A
0x18001a374  lea     rcx, [rax-2]
0x18001a378  test    r14, r14
0x18001a37b  lea     rsi, [rbx+20h]
0x18001a37f  cmovnz  rcx, rax
0x18001a383  mov     [rcx], r12w
0x18001a387  mov     rcx, rsi; pguid
0x18001a38a  call    cs:__imp_CoCreateGuid
0x18001a391  nop     dword ptr [rax+rax+00h]
0x18001a396  mov     edi, eax
0x18001a398  test    eax, eax
0x18001a39a  jns     short loc_18001A3A2
0x18001a39c  mov     rax, [rbx+8]
0x18001a3a0  jmp     short loc_18001A40D
0x18001a3a2  lea     r14, [rbx+30h]
0x18001a3a6  mov     rcx, r14; pguid
0x18001a3a9  call    cs:__imp_CoCreateGuid
0x18001a3b0  nop     dword ptr [rax+rax+00h]
0x18001a3b5  mov     edi, eax
0x18001a3b7  test    eax, eax
0x18001a3b9  js      short loc_18001A39C
0x18001a3bb  lea     rcx, [rbx+10h]
0x18001a3bf  mov     [rbx+18h], r12
0x18001a3c3  lea     rax, [rbx+40h]
0x18001a3c7  mov     [rcx], r14
0x18001a3ca  mov     [rsp+120h+RegistrationHandle], rax; RegistrationHandle
0x18001a3cf  mov     r9d, 1; GuidCount
0x18001a3d5  mov     [rsp+120h+MofResourceName], r12; MofResourceName
0x18001a3da  mov     r8, rsi; ControlGuid
0x18001a3dd  mov     [rsp+120h+MofImagePath], r12; MofImagePath
0x18001a3e2  xor     edx, edx; RequestContext
0x18001a3e4  mov     [rsp+120h+TraceGuidReg], rcx; TraceGuidReg
0x18001a3e9  lea     rcx, ?PersistRollbackMoveState@CArchiveDefinitionNode@@UEAAJPEAUIConfigManager2URI@@PEAUISequentialStream@@1@Z; RequestAddress
0x18001a3f0  call    cs:__imp_RegisterTraceGuidsW
0x18001a3f7  nop     dword ptr [rax+rax+00h]
0x18001a3fc  mov     ecx, eax; unsigned int
0x18001a3fe  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001a403  mov     edi, eax
0x18001a405  mov     rax, [rbx+8]
0x18001a409  test    edi, edi
0x18001a40b  jns     short loc_18001A424
0x18001a40d  mov     rcx, rax; Block
0x18001a410  call    cs:__imp_free
0x18001a417  nop     dword ptr [rax+rax+00h]
0x18001a41c  mov     eax, edi
0x18001a41e  mov     [rbx+8], r12
0x18001a422  jmp     short loc_18001A487
0x18001a424  movups  xmm0, xmmword ptr [rsi]
0x18001a427  lea     rdx, [rbp+47h+sz]; InstanceName
0x18001a42b  mov     rcx, rbx; TraceHandle
0x18001a42e  movdqu  xmmword ptr [rax+18h], xmm0
0x18001a433  mov     r8, [rbx+8]; Properties
0x18001a437  call    cs:__imp_StartTraceW
0x18001a43e  nop     dword ptr [rax+rax+00h]
0x18001a443  mov     edi, eax
0x18001a445  test    eax, eax
0x18001a447  jz      short loc_18001A479
0x18001a449  mov     rcx, [rbx+8]; Block
0x18001a44d  call    cs:__imp_free
0x18001a454  nop     dword ptr [rax+rax+00h]
0x18001a459  mov     [rbx+8], r12
0x18001a45d  mov     rcx, [rbx+40h]; RegistrationHandle
0x18001a461  call    cs:__imp_UnregisterTraceGuids
0x18001a468  nop     dword ptr [rax+rax+00h]
0x18001a46d  test    eax, eax
0x18001a46f  jnz     short loc_18001A479
0x18001a471  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x18001a479  mov     ecx, edi; unsigned int
0x18001a47b  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001a480  jmp     short loc_18001A487
0x18001a482  mov     eax, 80070216h
0x18001a487  mov     rcx, [rbp+47h+var_70]
0x18001a48b  xor     rcx, rsp; StackCookie
0x18001a48e  call    __security_check_cookie
0x18001a493  lea     r11, [rsp+120h+var_38]
0x18001a49b  movaps  xmm6, xmmword ptr [r11-18h]
0x18001a4a0  movaps  xmm7, xmmword ptr [r11-28h]
0x18001a4a5  mov     rsp, r11
0x18001a4a8  pop     r15
0x18001a4aa  pop     r14
0x18001a4ac  pop     r13
0x18001a4ae  pop     r12
0x18001a4b0  pop     rdi
0x18001a4b1  pop     rsi
0x18001a4b2  pop     rbx
0x18001a4b3  pop     rbp
0x18001a4b4  retn
```
