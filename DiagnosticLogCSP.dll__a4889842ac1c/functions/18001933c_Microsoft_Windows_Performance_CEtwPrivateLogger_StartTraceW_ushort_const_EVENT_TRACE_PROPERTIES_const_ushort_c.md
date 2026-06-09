# Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(ushort const *,_EVENT_TRACE_PROPERTIES const *,ushort const *,ulong,void *)

- ea: `0x18001933c`
- end: `0x1800196a1`
- name: `?StartTraceW@CEtwPrivateLogger@Performance@Windows@Microsoft@@QEAAJPEBGPEBU_EVENT_TRACE_PROPERTIES@@0KPEAX@Z`
- size: `869`
- prototype: `__int64 __usercall@<rax>(PTRACEHANDLE TraceHandle@<rcx>, const unsigned __int16 *@<rdx>, const struct _EVENT_TRACE_PROPERTIES *@<r8>, const unsigned __int16 *@<r9>, unsigned int, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016a50`

## callees

- `0x180001b60`
- `0x18000262c`
- `0x180002cf5`
- `0x180010a84`
- `0x180015734`
- `0x18001933c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019614`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019645`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019614`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019645`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800194a2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800194a2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800193f3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800193f3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800193de`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800195a0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800195b9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800193de`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800195a0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800195b9`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180019635`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180019635`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800195fa`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800195fa`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180019653`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180019653`

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
  int Guid; // edi
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
0x18001933c  mov     rax, rsp
0x18001933f  push    rbp
0x180019340  push    rbx
0x180019341  push    rsi
0x180019342  push    rdi
0x180019343  push    r12
0x180019345  push    r13
0x180019347  push    r14
0x180019349  push    r15
0x18001934b  lea     rbp, [rax-4Fh]
0x18001934f  sub     rsp, 0E8h
0x180019356  movaps  xmmword ptr [rax-58h], xmm6
0x18001935a  movaps  xmmword ptr [rax-68h], xmm7
0x18001935e  mov     rax, cs:__security_cookie
0x180019365  xor     rax, rsp
0x180019368  mov     [rbp+47h+var_70], rax
0x18001936c  mov     r13d, dword ptr [rbp+47h+Size]
0x180019370  xor     edi, edi
0x180019372  mov     rax, [rbp+47h+arg_28]
0x180019376  mov     r15, rdx
0x180019379  mov     [rsp+120h+var_E0], r8
0x18001937e  mov     rbx, rcx
0x180019381  mov     qword ptr [rsp+120h+pguid], rax
0x180019386  test    r13d, r13d
0x180019389  jz      short loc_18001939A
0x18001938b  test    rax, rax
0x18001938e  jnz     short loc_18001939A
0x180019390  mov     eax, 80070057h
0x180019395  jmp     loc_180019673
0x18001939a  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f; "{28ad2447-105b-4fe2-9599-e59b2aa9a634}"
0x1800193a1  lea     rcx, [rsp+120h+pguid+8]; pguid
0x1800193a6  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+10h; "7-105b-4fe2-9599-e59b2aa9a634}"
0x1800193ad  movaps  xmmword ptr [rbp+47h+sz], xmm0
0x1800193b1  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f+20h; "fe2-9599-e59b2aa9a634}"
0x1800193b8  movaps  [rbp+47h+var_A0], xmm0
0x1800193bc  movups  xmm0, xmmword ptr cs:a28ad2447105b4f+3Eh; "a9a634}"
0x1800193c3  movaps  [rbp+47h+var_B0], xmm1
0x1800193c7  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+30h; "-e59b2aa9a634}"
0x1800193ce  movaps  xmmword ptr [rbp+47h+var_90], xmm1
0x1800193d2  movups  xmmword ptr [rbp+47h+var_90+0Eh], xmm0
0x1800193d6  xorps   xmm0, xmm0
0x1800193d9  movups  xmmword ptr [rsp+120h+pguid+8], xmm0
0x1800193de  call    cs:__imp_CoCreateGuid
0x1800193e4  mov     r8d, 27h ; '''; cchMax
0x1800193ea  lea     rdx, [rbp+47h+sz]; lpsz
0x1800193ee  lea     rcx, [rsp+120h+pguid+8]; rguid
0x1800193f3  call    cs:__imp_StringFromGUID2
0x1800193f9  mov     r14d, 400h
0x1800193ff  lea     rax, [rbp+47h+sz]
0x180019403  mov     r8d, r14d
0x180019406  cmp     [rax], di
0x180019409  jz      short loc_180019415
0x18001940b  add     rax, 2
0x18001940f  sub     r8, 1
0x180019413  jnz     short loc_180019406
0x180019415  mov     rax, r8
0x180019418  mov     rdx, r14
0x18001941b  neg     rax
0x18001941e  mov     rcx, r8
0x180019421  sbb     eax, eax
0x180019423  sub     rdx, r8
0x180019426  not     eax
0x180019428  and     eax, 80070057h
0x18001942d  neg     rcx
0x180019430  sbb     r9, r9
0x180019433  and     r9, rdx
0x180019436  test    r8, r8
0x180019439  jz      loc_180019673
0x18001943f  mov     edx, 0FFFFFFFFh
0x180019444  cmp     r9, rdx
0x180019447  ja      loc_18001966E
0x18001944d  lea     edi, [r13+78h]
0x180019451  cmp     edi, 78h ; 'x'
0x180019454  jb      loc_18001966E
0x18001945a  mov     ecx, edi
0x18001945c  and     ecx, 1
0x18001945f  jz      short loc_180019472
0x180019461  mov     eax, edi
0x180019463  sub     eax, ecx
0x180019465  add     eax, 2
0x180019468  cmp     eax, edi
0x18001946a  jb      loc_18001966E
0x180019470  mov     edi, eax
0x180019472  mov     r12d, r9d
0x180019475  lea     rax, [r12+r12]
0x180019479  cmp     rax, rdx
0x18001947c  ja      loc_18001966E
0x180019482  lea     esi, [rax+rdi]
0x180019485  cmp     esi, edi
0x180019487  jb      loc_18001966E
0x18001948d  lea     eax, [rsi+800h]
0x180019493  cmp     eax, esi
0x180019495  jb      loc_18001966E
0x18001949b  mov     ecx, eax; Size
0x18001949d  mov     qword ptr [rsp+120h+pguid+8], rax
0x1800194a2  call    cs:__imp_malloc
0x1800194a8  mov     [rbx+8], rax
0x1800194ac  test    rax, rax
0x1800194af  jnz     short loc_1800194BB
0x1800194b1  mov     eax, 8007000Eh
0x1800194b6  jmp     loc_180019673
0x1800194bb  mov     r8, qword ptr [rsp+120h+pguid+8]; Size
0x1800194c0  xor     edx, edx; Val
0x1800194c2  mov     rcx, rax; void *
0x1800194c5  call    memset_0
0x1800194ca  mov     rax, [rsp+120h+var_E0]
0x1800194cf  lea     ecx, [rsi+800h]
0x1800194d5  mov     rdx, qword ptr [rsp+120h+pguid]; Src
0x1800194da  movaps  xmm0, xmmword ptr [rax]
0x1800194dd  movaps  xmm1, xmmword ptr [rax+10h]
0x1800194e1  movaps  xmm2, xmmword ptr [rax+20h]
0x1800194e5  movaps  xmm3, xmmword ptr [rax+30h]
0x1800194e9  movaps  xmm4, xmmword ptr [rax+40h]
0x1800194ed  movaps  xmm5, xmmword ptr [rax+50h]
0x1800194f1  movaps  xmm6, xmmword ptr [rax+60h]
0x1800194f5  movsd   xmm7, qword ptr [rax+70h]
0x1800194fa  mov     rax, [rbx+8]
0x1800194fe  movups  xmmword ptr [rax], xmm0
0x180019501  movups  xmmword ptr [rax+10h], xmm1
0x180019505  movups  xmmword ptr [rax+20h], xmm2
0x180019509  movups  xmmword ptr [rax+30h], xmm3
0x18001950d  movups  xmmword ptr [rax+40h], xmm4
0x180019511  movups  xmmword ptr [rax+50h], xmm5
0x180019515  movups  xmmword ptr [rax+60h], xmm6
0x180019519  movsd   qword ptr [rax+70h], xmm7
0x18001951e  mov     rax, [rbx+8]
0x180019522  mov     [rax], ecx
0x180019524  mov     rax, [rbx+8]
0x180019528  mov     dword ptr [rax+2Ch], 20000h
0x18001952f  mov     rax, [rbx+8]
0x180019533  mov     [rax+74h], edi
0x180019536  mov     rax, [rbx+8]
0x18001953a  mov     [rax+70h], esi
0x18001953d  test    rdx, rdx
0x180019540  jz      short loc_180019552
0x180019542  mov     rcx, [rbx+8]
0x180019546  mov     r8, r13; Size
0x180019549  add     rcx, 78h ; 'x'; void *
0x18001954d  call    memcpy_0
0x180019552  mov     ecx, edi
0x180019554  lea     r8, [rbp+47h+sz]; unsigned __int16 *
0x180019558  add     rcx, [rbx+8]; unsigned __int16 *
0x18001955c  mov     r9, r12; unsigned __int64
0x18001955f  mov     rdx, r12; unsigned __int64
0x180019562  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180019567  mov     eax, esi
0x180019569  add     rax, [rbx+8]
0x18001956d  xor     r12d, r12d
0x180019570  movzx   ecx, word ptr [r15]
0x180019574  test    cx, cx
0x180019577  jz      short loc_18001958A
0x180019579  mov     [rax], cx
0x18001957c  add     r15, 2
0x180019580  add     rax, 2
0x180019584  sub     r14, 1
0x180019588  jnz     short loc_180019570
0x18001958a  lea     rcx, [rax-2]
0x18001958e  test    r14, r14
0x180019591  lea     rsi, [rbx+20h]
0x180019595  cmovnz  rcx, rax
0x180019599  mov     [rcx], r12w
0x18001959d  mov     rcx, rsi; pguid
0x1800195a0  call    cs:__imp_CoCreateGuid
0x1800195a6  mov     edi, eax
0x1800195a8  test    eax, eax
0x1800195aa  jns     short loc_1800195B2
0x1800195ac  mov     rax, [rbx+8]
0x1800195b0  jmp     short loc_180019611
0x1800195b2  lea     r14, [rbx+30h]
0x1800195b6  mov     rcx, r14; pguid
0x1800195b9  call    cs:__imp_CoCreateGuid
0x1800195bf  mov     edi, eax
0x1800195c1  test    eax, eax
0x1800195c3  js      short loc_1800195AC
0x1800195c5  lea     rcx, [rbx+10h]
0x1800195c9  mov     [rbx+18h], r12
0x1800195cd  lea     rax, [rbx+40h]
0x1800195d1  mov     [rcx], r14
0x1800195d4  mov     [rsp+120h+RegistrationHandle], rax; RegistrationHandle
0x1800195d9  mov     r9d, 1; GuidCount
0x1800195df  mov     [rsp+120h+MofResourceName], r12; MofResourceName
0x1800195e4  mov     r8, rsi; ControlGuid
0x1800195e7  mov     [rsp+120h+MofImagePath], r12; MofImagePath
0x1800195ec  xor     edx, edx; RequestContext
0x1800195ee  mov     [rsp+120h+TraceGuidReg], rcx; TraceGuidReg
0x1800195f3  lea     rcx, ?PersistRollbackMoveState@CArchiveDefinitionNode@@UEAAJPEAUIConfigManager2URI@@PEAUISequentialStream@@1@Z; RequestAddress
0x1800195fa  call    cs:__imp_RegisterTraceGuidsW
0x180019600  mov     ecx, eax; unsigned int
0x180019602  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180019607  mov     edi, eax
0x180019609  mov     rax, [rbx+8]
0x18001960d  test    edi, edi
0x18001960f  jns     short loc_180019622
0x180019611  mov     rcx, rax; Block
0x180019614  call    cs:__imp_free
0x18001961a  mov     eax, edi
0x18001961c  mov     [rbx+8], r12
0x180019620  jmp     short loc_180019673
0x180019622  movups  xmm0, xmmword ptr [rsi]
0x180019625  lea     rdx, [rbp+47h+sz]; InstanceName
0x180019629  mov     rcx, rbx; TraceHandle
0x18001962c  movdqu  xmmword ptr [rax+18h], xmm0
0x180019631  mov     r8, [rbx+8]; Properties
0x180019635  call    cs:__imp_StartTraceW
0x18001963b  mov     edi, eax
0x18001963d  test    eax, eax
0x18001963f  jz      short loc_180019665
0x180019641  mov     rcx, [rbx+8]; Block
0x180019645  call    cs:__imp_free
0x18001964b  mov     [rbx+8], r12
0x18001964f  mov     rcx, [rbx+40h]; RegistrationHandle
0x180019653  call    cs:__imp_UnregisterTraceGuids
0x180019659  test    eax, eax
0x18001965b  jnz     short loc_180019665
0x18001965d  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x180019665  mov     ecx, edi; unsigned int
0x180019667  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001966c  jmp     short loc_180019673
0x18001966e  mov     eax, 80070216h
0x180019673  mov     rcx, [rbp+47h+var_70]
0x180019677  xor     rcx, rsp; StackCookie
0x18001967a  call    __security_check_cookie
0x18001967f  lea     r11, [rsp+120h+var_38]
0x180019687  movaps  xmm6, xmmword ptr [r11-18h]
0x18001968c  movaps  xmm7, xmmword ptr [r11-28h]
0x180019691  mov     rsp, r11
0x180019694  pop     r15
0x180019696  pop     r14
0x180019698  pop     r13
0x18001969a  pop     r12
0x18001969c  pop     rdi
0x18001969d  pop     rsi
0x18001969e  pop     rbx
0x18001969f  pop     rbp
0x1800196a0  retn
```
