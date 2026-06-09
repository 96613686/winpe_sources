# Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(ushort const *,_EVENT_TRACE_PROPERTIES const *,ushort const *,ulong,void *)

- ea: `0x180007e84`
- end: `0x1800081e6`
- name: `?StartTraceW@CEtwPrivateLogger@Performance@Windows@Microsoft@@QEAAJPEBGPEBU_EVENT_TRACE_PROPERTIES@@0KPEAX@Z`
- size: `866`
- prototype: `__int64 __usercall@<rax>(PTRACEHANDLE TraceHandle@<rcx>, const unsigned __int16 *@<rdx>, const struct _EVENT_TRACE_PROPERTIES *@<r8>, const unsigned __int16 *@<r9>, unsigned int, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800059a4`

## callees

- `0x180001870`
- `0x1800023d8`
- `0x1800023e4`
- `0x180002420`
- `0x1800027b1`
- `0x180004694`
- `0x180007e84`
- `0x1800081ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180007f26`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800080e7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180008100`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180007f26`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800080e7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180008100`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180007f3b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180007f3b`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180008141`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180008141`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180008198`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180008198`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18000817b`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18000817b`

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
  v18 = o_malloc_0(pguid[1]);
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
          _scrt_stub_for_is_c_termination_complete,
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
0x180007e84  mov     rax, rsp
0x180007e87  push    rbp
0x180007e88  push    rbx
0x180007e89  push    rsi
0x180007e8a  push    rdi
0x180007e8b  push    r12
0x180007e8d  push    r13
0x180007e8f  push    r14
0x180007e91  push    r15
0x180007e93  lea     rbp, [rax-4Fh]
0x180007e97  sub     rsp, 0E8h
0x180007e9e  movaps  xmmword ptr [rax-58h], xmm6
0x180007ea2  movaps  xmmword ptr [rax-68h], xmm7
0x180007ea6  mov     rax, cs:__security_cookie
0x180007ead  xor     rax, rsp
0x180007eb0  mov     [rbp+47h+var_70], rax
0x180007eb4  mov     r13d, dword ptr [rbp+47h+Size]
0x180007eb8  xor     edi, edi
0x180007eba  mov     rax, [rbp+47h+arg_28]
0x180007ebe  mov     r15, rdx
0x180007ec1  mov     [rsp+120h+var_E0], r8
0x180007ec6  mov     rbx, rcx
0x180007ec9  mov     qword ptr [rsp+120h+pguid], rax
0x180007ece  test    r13d, r13d
0x180007ed1  jz      short loc_180007EE2
0x180007ed3  test    rax, rax
0x180007ed6  jnz     short loc_180007EE2
0x180007ed8  mov     eax, 80070057h
0x180007edd  jmp     loc_1800081B8
0x180007ee2  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f; "{28ad2447-105b-4fe2-9599-e59b2aa9a634}"
0x180007ee9  lea     rcx, [rsp+120h+pguid+8]; pguid
0x180007eee  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+10h; "7-105b-4fe2-9599-e59b2aa9a634}"
0x180007ef5  movaps  xmmword ptr [rbp+47h+sz], xmm0
0x180007ef9  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f+20h; "fe2-9599-e59b2aa9a634}"
0x180007f00  movaps  [rbp+47h+var_A0], xmm0
0x180007f04  movups  xmm0, xmmword ptr cs:a28ad2447105b4f+3Eh; "a9a634}"
0x180007f0b  movaps  [rbp+47h+var_B0], xmm1
0x180007f0f  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+30h; "-e59b2aa9a634}"
0x180007f16  movaps  xmmword ptr [rbp+47h+var_90], xmm1
0x180007f1a  movups  xmmword ptr [rbp+47h+var_90+0Eh], xmm0
0x180007f1e  xorps   xmm0, xmm0
0x180007f21  movups  xmmword ptr [rsp+120h+pguid+8], xmm0
0x180007f26  call    cs:__imp_CoCreateGuid
0x180007f2c  mov     r8d, 27h ; '''; cchMax
0x180007f32  lea     rdx, [rbp+47h+sz]; lpsz
0x180007f36  lea     rcx, [rsp+120h+pguid+8]; rguid
0x180007f3b  call    cs:__imp_StringFromGUID2
0x180007f41  mov     r14d, 400h
0x180007f47  lea     rax, [rbp+47h+sz]
0x180007f4b  mov     r8d, r14d
0x180007f4e  cmp     [rax], di
0x180007f51  jz      short loc_180007F5D
0x180007f53  add     rax, 2
0x180007f57  sub     r8, 1
0x180007f5b  jnz     short loc_180007F4E
0x180007f5d  mov     rax, r8
0x180007f60  mov     rdx, r14
0x180007f63  neg     rax
0x180007f66  mov     rcx, r8
0x180007f69  sbb     eax, eax
0x180007f6b  sub     rdx, r8
0x180007f6e  not     eax
0x180007f70  and     eax, 80070057h
0x180007f75  neg     rcx
0x180007f78  sbb     r9, r9
0x180007f7b  and     r9, rdx
0x180007f7e  test    r8, r8
0x180007f81  jz      loc_1800081B8
0x180007f87  mov     edx, 0FFFFFFFFh
0x180007f8c  cmp     r9, rdx
0x180007f8f  ja      loc_1800081B3
0x180007f95  lea     edi, [r13+78h]
0x180007f99  cmp     edi, 78h ; 'x'
0x180007f9c  jb      loc_1800081B3
0x180007fa2  mov     ecx, edi
0x180007fa4  and     ecx, 1
0x180007fa7  jz      short loc_180007FBA
0x180007fa9  mov     eax, edi
0x180007fab  sub     eax, ecx
0x180007fad  add     eax, 2
0x180007fb0  cmp     eax, edi
0x180007fb2  jb      loc_1800081B3
0x180007fb8  mov     edi, eax
0x180007fba  mov     r12d, r9d
0x180007fbd  lea     rax, [r12+r12]
0x180007fc1  cmp     rax, rdx
0x180007fc4  ja      loc_1800081B3
0x180007fca  lea     esi, [rax+rdi]
0x180007fcd  cmp     esi, edi
0x180007fcf  jb      loc_1800081B3
0x180007fd5  lea     eax, [rsi+800h]
0x180007fdb  cmp     eax, esi
0x180007fdd  jb      loc_1800081B3
0x180007fe3  mov     ecx, eax; Size
0x180007fe5  mov     qword ptr [rsp+120h+pguid+8], rax
0x180007fea  call    _o_malloc_0
0x180007fef  mov     [rbx+8], rax
0x180007ff3  test    rax, rax
0x180007ff6  jnz     short loc_180008002
0x180007ff8  mov     eax, 8007000Eh
0x180007ffd  jmp     loc_1800081B8
0x180008002  mov     r8, qword ptr [rsp+120h+pguid+8]; Size
0x180008007  xor     edx, edx; Val
0x180008009  mov     rcx, rax; void *
0x18000800c  call    memset_0
0x180008011  mov     rax, [rsp+120h+var_E0]
0x180008016  lea     ecx, [rsi+800h]
0x18000801c  mov     rdx, qword ptr [rsp+120h+pguid]; Src
0x180008021  movaps  xmm0, xmmword ptr [rax]
0x180008024  movaps  xmm1, xmmword ptr [rax+10h]
0x180008028  movaps  xmm2, xmmword ptr [rax+20h]
0x18000802c  movaps  xmm3, xmmword ptr [rax+30h]
0x180008030  movaps  xmm4, xmmword ptr [rax+40h]
0x180008034  movaps  xmm5, xmmword ptr [rax+50h]
0x180008038  movaps  xmm6, xmmword ptr [rax+60h]
0x18000803c  movsd   xmm7, qword ptr [rax+70h]
0x180008041  mov     rax, [rbx+8]
0x180008045  movups  xmmword ptr [rax], xmm0
0x180008048  movups  xmmword ptr [rax+10h], xmm1
0x18000804c  movups  xmmword ptr [rax+20h], xmm2
0x180008050  movups  xmmword ptr [rax+30h], xmm3
0x180008054  movups  xmmword ptr [rax+40h], xmm4
0x180008058  movups  xmmword ptr [rax+50h], xmm5
0x18000805c  movups  xmmword ptr [rax+60h], xmm6
0x180008060  movsd   qword ptr [rax+70h], xmm7
0x180008065  mov     rax, [rbx+8]
0x180008069  mov     [rax], ecx
0x18000806b  mov     rax, [rbx+8]
0x18000806f  mov     dword ptr [rax+2Ch], 20000h
0x180008076  mov     rax, [rbx+8]
0x18000807a  mov     [rax+74h], edi
0x18000807d  mov     rax, [rbx+8]
0x180008081  mov     [rax+70h], esi
0x180008084  test    rdx, rdx
0x180008087  jz      short loc_180008099
0x180008089  mov     rcx, [rbx+8]
0x18000808d  mov     r8, r13; Size
0x180008090  add     rcx, 78h ; 'x'; void *
0x180008094  call    memcpy_0
0x180008099  mov     ecx, edi
0x18000809b  lea     r8, [rbp+47h+sz]; unsigned __int16 *
0x18000809f  add     rcx, [rbx+8]; unsigned __int16 *
0x1800080a3  mov     r9, r12; unsigned __int64
0x1800080a6  mov     rdx, r12; unsigned __int64
0x1800080a9  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800080ae  mov     eax, esi
0x1800080b0  add     rax, [rbx+8]
0x1800080b4  xor     r12d, r12d
0x1800080b7  movzx   ecx, word ptr [r15]
0x1800080bb  test    cx, cx
0x1800080be  jz      short loc_1800080D1
0x1800080c0  mov     [rax], cx
0x1800080c3  add     r15, 2
0x1800080c7  add     rax, 2
0x1800080cb  sub     r14, 1
0x1800080cf  jnz     short loc_1800080B7
0x1800080d1  lea     rcx, [rax-2]
0x1800080d5  test    r14, r14
0x1800080d8  lea     rsi, [rbx+20h]
0x1800080dc  cmovnz  rcx, rax
0x1800080e0  mov     [rcx], r12w
0x1800080e4  mov     rcx, rsi; pguid
0x1800080e7  call    cs:__imp_CoCreateGuid
0x1800080ed  mov     edi, eax
0x1800080ef  test    eax, eax
0x1800080f1  jns     short loc_1800080F9
0x1800080f3  mov     rax, [rbx+8]
0x1800080f7  jmp     short loc_180008158
0x1800080f9  lea     r14, [rbx+30h]
0x1800080fd  mov     rcx, r14; pguid
0x180008100  call    cs:__imp_CoCreateGuid
0x180008106  mov     edi, eax
0x180008108  test    eax, eax
0x18000810a  js      short loc_1800080F3
0x18000810c  lea     rcx, [rbx+10h]
0x180008110  mov     [rbx+18h], r12
0x180008114  lea     rax, [rbx+40h]
0x180008118  mov     [rcx], r14
0x18000811b  mov     [rsp+120h+RegistrationHandle], rax; RegistrationHandle
0x180008120  mov     r9d, 1; GuidCount
0x180008126  mov     [rsp+120h+MofResourceName], r12; MofResourceName
0x18000812b  mov     r8, rsi; ControlGuid
0x18000812e  mov     [rsp+120h+MofImagePath], r12; MofImagePath
0x180008133  xor     edx, edx; RequestContext
0x180008135  mov     [rsp+120h+TraceGuidReg], rcx; TraceGuidReg
0x18000813a  lea     rcx, __scrt_stub_for_is_c_termination_complete; RequestAddress
0x180008141  call    cs:__imp_RegisterTraceGuidsW
0x180008147  mov     ecx, eax; unsigned int
0x180008149  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000814e  mov     edi, eax
0x180008150  mov     rax, [rbx+8]
0x180008154  test    edi, edi
0x180008156  jns     short loc_180008168
0x180008158  mov     rcx, rax; Block
0x18000815b  call    free
0x180008160  mov     eax, edi
0x180008162  mov     [rbx+8], r12
0x180008166  jmp     short loc_1800081B8
0x180008168  movups  xmm0, xmmword ptr [rsi]
0x18000816b  lea     rdx, [rbp+47h+sz]; InstanceName
0x18000816f  mov     rcx, rbx; TraceHandle
0x180008172  movdqu  xmmword ptr [rax+18h], xmm0
0x180008177  mov     r8, [rbx+8]; Properties
0x18000817b  call    cs:__imp_StartTraceW
0x180008181  mov     edi, eax
0x180008183  test    eax, eax
0x180008185  jz      short loc_1800081AA
0x180008187  mov     rcx, [rbx+8]; Block
0x18000818b  call    free
0x180008190  mov     [rbx+8], r12
0x180008194  mov     rcx, [rbx+40h]; RegistrationHandle
0x180008198  call    cs:__imp_UnregisterTraceGuids
0x18000819e  test    eax, eax
0x1800081a0  jnz     short loc_1800081AA
0x1800081a2  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x1800081aa  mov     ecx, edi; unsigned int
0x1800081ac  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800081b1  jmp     short loc_1800081B8
0x1800081b3  mov     eax, 80070216h
0x1800081b8  mov     rcx, [rbp+47h+var_70]
0x1800081bc  xor     rcx, rsp; StackCookie
0x1800081bf  call    __security_check_cookie
0x1800081c4  lea     r11, [rsp+120h+var_38]
0x1800081cc  movaps  xmm6, xmmword ptr [r11-18h]
0x1800081d1  movaps  xmm7, xmmword ptr [r11-28h]
0x1800081d6  mov     rsp, r11
0x1800081d9  pop     r15
0x1800081db  pop     r14
0x1800081dd  pop     r13
0x1800081df  pop     r12
0x1800081e1  pop     rdi
0x1800081e2  pop     rsi
0x1800081e3  pop     rbx
0x1800081e4  pop     rbp
0x1800081e5  retn
```
