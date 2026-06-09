# Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(ushort const *,_EVENT_TRACE_PROPERTIES const *,ushort const *,ulong,void *)

- ea: `0x1800062a4`
- end: `0x180006635`
- name: `?StartTraceW@CEtwPrivateLogger@Performance@Windows@Microsoft@@QEAAJPEBGPEBU_EVENT_TRACE_PROPERTIES@@0KPEAX@Z`
- size: `913`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEtwPrivateLogger *this, char *, const struct _EVENT_TRACE_PROPERTIES *, const unsigned __int16 *, size_t Size, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003024`

## callees

- `0x180006210`
- `0x1800062a4`
- `0x180006960`
- `0x180026e30`
- `0x180026f6c`
- `0x1800278f0`

## import_xrefs

- `msvcrt!malloc` at `0x180006441`
- `msvcrt!malloc` at `0x180006441`
- `msvcrt!free` at `0x1800065af`
- `msvcrt!free` at `0x1800065e4`
- `msvcrt!free` at `0x1800065af`
- `msvcrt!free` at `0x1800065e4`
- `ole32!StringFromGUID2` at `0x180006375`
- `ole32!StringFromGUID2` at `0x180006375`
- `ole32!CoCreateGuid` at `0x180006361`
- `ole32!CoCreateGuid` at `0x180006544`
- `ole32!CoCreateGuid` at `0x180006557`
- `ole32!CoCreateGuid` at `0x180006361`
- `ole32!CoCreateGuid` at `0x180006544`
- `ole32!CoCreateGuid` at `0x180006557`
- `ADVAPI32!StartTraceW` at `0x1800065d4`
- `ADVAPI32!StartTraceW` at `0x1800065d4`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180006598`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180006598`
- `ADVAPI32!UnregisterTraceGuids` at `0x1800065f2`
- `ADVAPI32!UnregisterTraceGuids` at `0x1800065f2`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(
        Microsoft::Windows::Performance::CEtwPrivateLogger *this,
        char *a2,
        const struct _EVENT_TRACE_PROPERTIES *a3,
        const unsigned __int16 *a4,
        size_t Size,
        void *a6)
{
  __int64 result; // rax
  __int64 v8; // r15
  OLECHAR *v9; // rax
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // edi
  unsigned int v14; // edx
  int v15; // eax
  bool v16; // cf
  unsigned __int64 v17; // r12
  unsigned __int64 v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // r14d
  unsigned int v21; // eax
  unsigned int v22; // esi
  void *v23; // rax
  __int64 v24; // rax
  char *v25; // rcx
  signed __int64 v26; // rbx
  __int16 v27; // ax
  char *v28; // rax
  HRESULT Guid; // edi
  ULONG v30; // eax
  ULONG started; // edi
  GUID pguid; // [rsp+68h] [rbp-49h] BYREF
  OLECHAR sz[8]; // [rsp+78h] [rbp-39h] BYREF
  __int128 v37; // [rsp+88h] [rbp-29h]
  __int128 v38; // [rsp+98h] [rbp-19h]
  __int128 v39; // [rsp+A8h] [rbp-9h]
  __int64 v40; // [rsp+B8h] [rbp+7h]
  int v41; // [rsp+C0h] [rbp+Fh]
  wchar_t v42; // [rsp+C4h] [rbp+13h]

  if ( (_DWORD)Size && !a6 )
    return 2147942487LL;
  *(_OWORD *)sz = *(_OWORD *)L"{28ad2447-105b-4fe2-9599-e59b2aa9a634}";
  v41 = *(_DWORD *)L"4}";
  v38 = *(_OWORD *)L"fe2-9599-e59b2aa9a634}";
  v37 = *(_OWORD *)L"7-105b-4fe2-9599-e59b2aa9a634}";
  v42 = a28ad2447105b4f[38];
  v40 = *(_QWORD *)L"9a634}";
  v39 = *(_OWORD *)L"-e59b2aa9a634}";
  *(_QWORD *)&pguid.Data1 = 0;
  *(_QWORD *)pguid.Data4 = 0;
  CoCreateGuid(&pguid);
  StringFromGUID2(&pguid, sz, 39);
  v8 = 1024;
  v9 = sz;
  v10 = 1024;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  result = v10 == 0 ? 0x80070057 : 0;
  if ( v10 )
    v11 = 1024 - v10;
  else
    v11 = 0;
  if ( v10 )
  {
    if ( v11 > 0xFFFFFFFF )
      return 2147942934LL;
    v12 = Size + 120;
    if ( (unsigned int)Size >= 0xFFFFFF88 )
      return 2147942934LL;
    v13 = Size + 120;
    if ( (v12 & 1) != 0 )
    {
      v14 = v12 - (v12 & 1) + 2;
      v15 = -1;
      if ( v14 >= v13 )
        v15 = v14;
      v13 = v15;
      if ( v14 < (int)Size + 120 )
      {
        v16 = 1;
        return v16 ? 0x80070216 : 0;
      }
    }
    v17 = (unsigned int)v11;
    v18 = 2LL * (unsigned int)v11;
    if ( v18 > 0xFFFFFFFF )
      return 2147942934LL;
    v19 = v13 + v18;
    v16 = v19 < v13;
    if ( v19 < v13 )
      return v16 ? 0x80070216 : 0;
    v20 = v19;
    v21 = v19 + 2048;
    if ( v20 + 2048 < v20 )
      return 2147942934LL;
    v22 = v21;
    *(_QWORD *)&pguid.Data1 = v21;
    v23 = malloc(v21);
    *((_QWORD *)this + 1) = v23;
    if ( v23 )
    {
      memset_0(v23, 0, *(size_t *)&pguid.Data1);
      v24 = *((_QWORD *)this + 1);
      *(_OWORD *)v24 = *(_OWORD *)&a3->Wnode.BufferSize;
      *(_OWORD *)(v24 + 16) = *(_OWORD *)&a3->Wnode.CountLost;
      *(_OWORD *)(v24 + 32) = *(_OWORD *)a3->Wnode.Guid.Data4;
      *(_OWORD *)(v24 + 48) = *(_OWORD *)&a3->BufferSize;
      *(_OWORD *)(v24 + 64) = *(_OWORD *)&a3->LogFileMode;
      *(_OWORD *)(v24 + 80) = *(_OWORD *)&a3->NumberOfBuffers;
      *(_OWORD *)(v24 + 96) = *(_OWORD *)&a3->LogBuffersLost;
      *(_QWORD *)(v24 + 112) = *(_QWORD *)&a3->LogFileNameOffset;
      **((_DWORD **)this + 1) = v22;
      *(_DWORD *)(*((_QWORD *)this + 1) + 44LL) = 0x20000;
      *(_DWORD *)(*((_QWORD *)this + 1) + 116LL) = v13;
      *(_DWORD *)(*((_QWORD *)this + 1) + 112LL) = v20;
      if ( a6 )
        memcpy_0((void *)(*((_QWORD *)this + 1) + 120LL), a6, (unsigned int)Size);
      StringCchCopyNW((char *)(*((_QWORD *)this + 1) + v13), v17, (char *)sz, v17);
      v25 = (char *)(*((_QWORD *)this + 1) + v20);
      v26 = a2 - v25;
      do
      {
        v27 = *(_WORD *)&v25[v26];
        if ( !v27 )
          break;
        *(_WORD *)v25 = v27;
        v25 += 2;
        --v8;
      }
      while ( v8 );
      v28 = v25 - 2;
      if ( v8 )
        v28 = v25;
      *(_WORD *)v28 = 0;
      Guid = CoCreateGuid((GUID *)this + 2);
      if ( Guid >= 0 )
      {
        Guid = CoCreateGuid((GUID *)this + 3);
        if ( Guid >= 0 )
        {
          *((_QWORD *)this + 3) = 0;
          *((_QWORD *)this + 2) = (char *)this + 48;
          v30 = RegisterTraceGuidsW(
                  Microsoft::Windows::Performance::CEtwPrivateLogger::ControlCallback,
                  0,
                  (LPCGUID)this + 2,
                  1u,
                  (PTRACE_GUID_REGISTRATION)this + 1,
                  0,
                  0,
                  (PTRACEHANDLE)this + 8);
          Guid = ATL::AtlHresultFromWin32(v30);
        }
      }
      if ( Guid >= 0 )
      {
        *(_OWORD *)(*((_QWORD *)this + 1) + 24LL) = *((_OWORD *)this + 2);
        started = StartTraceW((PTRACEHANDLE)this, sz, *((PEVENT_TRACE_PROPERTIES *)this + 1));
        if ( started )
        {
          free(*((void **)this + 1));
          *((_QWORD *)this + 1) = 0;
          if ( !UnregisterTraceGuids(*((_QWORD *)this + 8)) )
            *((_QWORD *)this + 8) = -1;
        }
        return ATL::AtlHresultFromWin32(started);
      }
      else
      {
        free(*((void **)this + 1));
        result = (unsigned int)Guid;
        *((_QWORD *)this + 1) = 0;
      }
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800062a4  mov     rax, rsp
0x1800062a7  mov     [rax+10h], rbx
0x1800062ab  mov     [rax+18h], rsi
0x1800062af  mov     [rax+20h], rdi
0x1800062b3  push    rbp
0x1800062b4  push    r12
0x1800062b6  push    r13
0x1800062b8  push    r14
0x1800062ba  push    r15
0x1800062bc  lea     rbp, [rax-4Fh]
0x1800062c0  sub     rsp, 0D0h
0x1800062c7  mov     rax, cs:__security_cookie
0x1800062ce  xor     rax, rsp
0x1800062d1  mov     [rbp+47h+var_30], rax
0x1800062d5  mov     r13d, dword ptr [rbp+47h+Size]
0x1800062d9  xor     edi, edi
0x1800062db  mov     rax, [rbp+47h+arg_28]
0x1800062df  mov     rbx, rcx
0x1800062e2  mov     [rbp+47h+var_B0], r8
0x1800062e6  mov     [rbp+47h+var_A0], rdx
0x1800062ea  mov     [rbp+47h+TraceHandle], rcx
0x1800062ee  mov     [rbp+47h+Src], rax
0x1800062f2  test    r13d, r13d
0x1800062f5  jz      short loc_180006306
0x1800062f7  test    rax, rax
0x1800062fa  jnz     short loc_180006306
0x1800062fc  mov     eax, 80070057h
0x180006301  jmp     loc_180006608
0x180006306  mov     eax, dword ptr cs:a28ad2447105b4f+48h; "4}"
0x18000630c  lea     rcx, [rbp+47h+pguid]; pguid
0x180006310  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f; "{28ad2447-105b-4fe2-9599-e59b2aa9a634}"
0x180006317  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+10h; "7-105b-4fe2-9599-e59b2aa9a634}"
0x18000631e  movaps  xmmword ptr [rbp+47h+sz], xmm0
0x180006322  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f+20h; "fe2-9599-e59b2aa9a634}"
0x180006329  mov     [rbp+47h+var_38], eax
0x18000632c  movzx   eax, word ptr cs:a28ad2447105b4f+4Ch; ""
0x180006333  movaps  [rbp+47h+var_60], xmm0
0x180006337  movsd   xmm0, qword ptr cs:a28ad2447105b4f+40h; "9a634}"
0x18000633f  movaps  [rbp+47h+var_70], xmm1
0x180006343  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+30h; "-e59b2aa9a634}"
0x18000634a  mov     [rbp+47h+var_34], ax
0x18000634e  xor     eax, eax
0x180006350  movsd   [rbp+47h+var_40], xmm0
0x180006355  movaps  [rbp+47h+var_50], xmm1
0x180006359  mov     qword ptr [rbp+47h+pguid.Data1], rax
0x18000635d  mov     qword ptr [rbp+47h+pguid.Data4], rax
0x180006361  call    cs:__imp_CoCreateGuid
0x180006367  mov     r8d, 27h ; '''; cchMax
0x18000636d  lea     rdx, [rbp+47h+sz]; lpsz
0x180006371  lea     rcx, [rbp+47h+pguid]; rguid
0x180006375  call    cs:__imp_StringFromGUID2
0x18000637b  mov     r15d, 400h
0x180006381  lea     rax, [rbp+47h+sz]
0x180006385  mov     edx, r15d
0x180006388  cmp     [rax], di
0x18000638b  jz      short loc_180006397
0x18000638d  add     rax, 2
0x180006391  sub     rdx, 1
0x180006395  jnz     short loc_180006388
0x180006397  mov     rax, rdx
0x18000639a  neg     rax
0x18000639d  sbb     eax, eax
0x18000639f  not     eax
0x1800063a1  and     eax, 80070057h
0x1800063a6  test    rdx, rdx
0x1800063a9  jz      short loc_1800063B3
0x1800063ab  mov     rcx, r15
0x1800063ae  sub     rcx, rdx
0x1800063b1  jmp     short loc_1800063B6
0x1800063b3  mov     rcx, rdi
0x1800063b6  test    eax, eax
0x1800063b8  js      loc_180006608
0x1800063be  mov     esi, 0FFFFFFFFh
0x1800063c3  cmp     rcx, rsi
0x1800063c6  jbe     short loc_1800063D2
0x1800063c8  mov     eax, 80070216h
0x1800063cd  jmp     loc_180006608
0x1800063d2  lea     eax, [r13+78h]
0x1800063d6  mov     edi, esi
0x1800063d8  cmp     eax, 78h ; 'x'
0x1800063db  cmovnb  edi, eax
0x1800063de  mov     r9d, edi
0x1800063e1  jb      short loc_1800063C8
0x1800063e3  mov     edx, edi
0x1800063e5  and     edx, 1
0x1800063e8  jz      short loc_180006411
0x1800063ea  mov     eax, edi
0x1800063ec  mov     r8d, edi
0x1800063ef  sub     eax, edx
0x1800063f1  lea     edx, [rax+2]
0x1800063f4  mov     eax, esi
0x1800063f6  cmp     edx, edi
0x1800063f8  cmovnb  eax, edx
0x1800063fb  mov     edi, eax
0x1800063fd  cmp     edx, r8d
0x180006400  jnb     short loc_180006411
0x180006402  cmp     edx, r8d
0x180006405  sbb     eax, eax
0x180006407  and     eax, 80070216h
0x18000640c  jmp     loc_180006608
0x180006411  mov     r12d, ecx
0x180006414  lea     rax, [r12+r12]
0x180006418  cmp     rax, rsi
0x18000641b  ja      short loc_1800063C8
0x18000641d  add     eax, edi
0x18000641f  mov     r14d, esi
0x180006422  cmp     eax, edi
0x180006424  cmovnb  r14d, eax
0x180006428  jb      short loc_180006405
0x18000642a  lea     eax, [r14+800h]
0x180006431  cmp     eax, r14d
0x180006434  cmovnb  esi, eax
0x180006437  jb      short loc_1800063C8
0x180006439  mov     eax, esi
0x18000643b  mov     ecx, esi; Size
0x18000643d  mov     qword ptr [rbp+47h+pguid.Data1], rax
0x180006441  call    cs:__imp_malloc
0x180006447  mov     [rbx+8], rax
0x18000644b  test    rax, rax
0x18000644e  jnz     short loc_18000645A
0x180006450  mov     eax, 8007000Eh
0x180006455  jmp     loc_180006608
0x18000645a  mov     r8, qword ptr [rbp+47h+pguid.Data1]; Size
0x18000645e  xor     edx, edx; Val
0x180006460  mov     rcx, rax; void *
0x180006463  call    memset_0
0x180006468  mov     rax, [rbx+8]
0x18000646c  mov     rcx, [rbp+47h+var_B0]
0x180006470  mov     rdx, [rbp+47h+Src]; Src
0x180006474  movaps  xmm0, xmmword ptr [rcx]
0x180006477  movups  xmmword ptr [rax], xmm0
0x18000647a  movaps  xmm1, xmmword ptr [rcx+10h]
0x18000647e  movups  xmmword ptr [rax+10h], xmm1
0x180006482  movaps  xmm0, xmmword ptr [rcx+20h]
0x180006486  movups  xmmword ptr [rax+20h], xmm0
0x18000648a  movaps  xmm1, xmmword ptr [rcx+30h]
0x18000648e  movups  xmmword ptr [rax+30h], xmm1
0x180006492  movaps  xmm0, xmmword ptr [rcx+40h]
0x180006496  movups  xmmword ptr [rax+40h], xmm0
0x18000649a  movaps  xmm1, xmmword ptr [rcx+50h]
0x18000649e  movups  xmmword ptr [rax+50h], xmm1
0x1800064a2  movaps  xmm0, xmmword ptr [rcx+60h]
0x1800064a6  movups  xmmword ptr [rax+60h], xmm0
0x1800064aa  movsd   xmm1, qword ptr [rcx+70h]
0x1800064af  movsd   qword ptr [rax+70h], xmm1
0x1800064b4  mov     rax, [rbx+8]
0x1800064b8  mov     [rax], esi
0x1800064ba  mov     rax, [rbx+8]
0x1800064be  mov     dword ptr [rax+2Ch], 20000h
0x1800064c5  mov     rax, [rbx+8]
0x1800064c9  mov     [rax+74h], edi
0x1800064cc  mov     rax, [rbx+8]
0x1800064d0  mov     [rax+70h], r14d
0x1800064d4  test    rdx, rdx
0x1800064d7  jz      short loc_1800064E9
0x1800064d9  mov     rcx, [rbx+8]
0x1800064dd  mov     r8, r13; Size
0x1800064e0  add     rcx, 78h ; 'x'; void *
0x1800064e4  call    memcpy_0
0x1800064e9  mov     ecx, edi
0x1800064eb  lea     r8, [rbp+47h+sz]; unsigned __int16 *
0x1800064ef  add     rcx, [rbx+8]; unsigned __int16 *
0x1800064f3  mov     r9, r12; unsigned __int64
0x1800064f6  mov     rdx, r12; unsigned __int64
0x1800064f9  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800064fe  mov     ecx, r14d
0x180006501  add     rcx, [rbx+8]
0x180006505  mov     rbx, [rbp+47h+var_A0]
0x180006509  sub     rbx, rcx
0x18000650c  xor     r12d, r12d
0x18000650f  test    r15, r15
0x180006512  jz      short loc_18000652A
0x180006514  movzx   eax, word ptr [rbx+rcx]
0x180006518  test    ax, ax
0x18000651b  jz      short loc_18000652A
0x18000651d  mov     [rcx], ax
0x180006520  add     rcx, 2
0x180006524  sub     r15, 1
0x180006528  jnz     short loc_18000650F
0x18000652a  mov     rbx, [rbp+47h+TraceHandle]
0x18000652e  lea     rax, [rcx-2]
0x180006532  test    r15, r15
0x180006535  cmovnz  rax, rcx
0x180006539  lea     rsi, [rbx+20h]
0x18000653d  mov     rcx, rsi; pguid
0x180006540  mov     [rax], r12w
0x180006544  call    cs:__imp_CoCreateGuid
0x18000654a  mov     edi, eax
0x18000654c  test    eax, eax
0x18000654e  js      short loc_1800065A7
0x180006550  lea     r14, [rbx+30h]
0x180006554  mov     rcx, r14; pguid
0x180006557  call    cs:__imp_CoCreateGuid
0x18000655d  mov     edi, eax
0x18000655f  test    eax, eax
0x180006561  js      short loc_1800065A7
0x180006563  lea     rcx, [rbx+10h]
0x180006567  mov     [rbx+18h], r12
0x18000656b  lea     rax, [rbx+40h]
0x18000656f  mov     [rcx], r14
0x180006572  mov     [rsp+0F0h+RegistrationHandle], rax; RegistrationHandle
0x180006577  mov     r9d, 1; GuidCount
0x18000657d  mov     [rsp+0F0h+MofResourceName], r12; MofResourceName
0x180006582  mov     r8, rsi; ControlGuid
0x180006585  mov     [rsp+0F0h+MofImagePath], r12; MofImagePath
0x18000658a  xor     edx, edx; RequestContext
0x18000658c  mov     [rsp+0F0h+TraceGuidReg], rcx; TraceGuidReg
0x180006591  lea     rcx, ?ControlCallback@CEtwPrivateLogger@Performance@Windows@Microsoft@@CAKW4WMIDPREQUESTCODE@@PEAXPEAK1@Z; RequestAddress
0x180006598  call    cs:__imp_RegisterTraceGuidsW
0x18000659e  mov     ecx, eax; unsigned int
0x1800065a0  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800065a5  mov     edi, eax
0x1800065a7  test    edi, edi
0x1800065a9  jns     short loc_1800065BD
0x1800065ab  mov     rcx, [rbx+8]; Block
0x1800065af  call    cs:__imp_free
0x1800065b5  mov     eax, edi
0x1800065b7  mov     [rbx+8], r12
0x1800065bb  jmp     short loc_180006608
0x1800065bd  mov     rax, [rbx+8]
0x1800065c1  lea     rdx, [rbp+47h+sz]; InstanceName
0x1800065c5  movups  xmm0, xmmword ptr [rsi]
0x1800065c8  mov     rcx, rbx; TraceHandle
0x1800065cb  movdqu  xmmword ptr [rax+18h], xmm0
0x1800065d0  mov     r8, [rbx+8]; Properties
0x1800065d4  call    cs:__imp_StartTraceW
0x1800065da  mov     edi, eax
0x1800065dc  test    eax, eax
0x1800065de  jz      short loc_180006601
0x1800065e0  mov     rcx, [rbx+8]; Block
0x1800065e4  call    cs:__imp_free
0x1800065ea  mov     [rbx+8], r12
0x1800065ee  mov     rcx, [rbx+40h]; RegistrationHandle
0x1800065f2  call    cs:__imp_UnregisterTraceGuids
0x1800065f8  test    eax, eax
0x1800065fa  jnz     short loc_180006601
0x1800065fc  or      qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x180006601  mov     ecx, edi; unsigned int
0x180006603  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180006608  mov     rcx, [rbp+47h+var_30]
0x18000660c  xor     rcx, rsp; StackCookie
0x18000660f  call    __security_check_cookie
0x180006614  lea     r11, [rsp+0F0h+var_20]
0x18000661c  mov     rbx, [r11+38h]
0x180006620  mov     rsi, [r11+40h]
0x180006624  mov     rdi, [r11+48h]
0x180006628  mov     rsp, r11
0x18000662b  pop     r15
0x18000662d  pop     r14
0x18000662f  pop     r13
0x180006631  pop     r12
0x180006633  pop     rbp
0x180006634  retn
```
