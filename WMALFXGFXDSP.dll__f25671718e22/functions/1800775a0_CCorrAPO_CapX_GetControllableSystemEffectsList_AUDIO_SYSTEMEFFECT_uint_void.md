# CCorrAPO_CapX::GetControllableSystemEffectsList(AUDIO_SYSTEMEFFECT * *,uint *,void *)

- ea: `0x1800775a0`
- end: `0x1800777e4`
- name: `?GetControllableSystemEffectsList@CCorrAPO_CapX@@UEAAJPEAPEAUAUDIO_SYSTEMEFFECT@@PEAIPEAX@Z`
- size: `580`
- prototype: `int(CCorrAPO_CapX *__hidden this, struct AUDIO_SYSTEMEFFECT **, unsigned int *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014d58`
- `0x180014e94`
- `0x180076840`
- `0x180076a20`
- `0x180076b84`
- `0x1800775a0`
- `0x180078f68`
- `0x180079ae0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180077664`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007766d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180077664`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007766d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077757`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800777cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077757`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800777cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077631`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077631`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077651`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077651`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180077697`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180077697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180077712`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180077712`

## pseudocode

```c
__int64 __fastcall CCorrAPO_CapX::GetControllableSystemEffectsList(
        struct _RTL_CRITICAL_SECTION *this,
        struct AUDIO_SYSTEMEFFECT **a2,
        unsigned int *a3,
        void *a4)
{
  __int64 v8; // rdx
  unsigned int LastError; // ebx
  char *v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  CCorrAPOBase *v13; // r15
  HANDLE OwningThread; // rcx
  HANDLE *p_OwningThread; // r12
  HANDLE CurrentProcess; // rbx
  HANDLE v17; // rax
  const char *v18; // r9
  int EffectState; // eax
  __int64 v20; // rbx
  LPVOID v21; // rax
  __int64 v22; // rdx
  unsigned int v23; // r10d
  __int64 v24; // r9
  __int64 v25; // r8
  __int128 v26; // xmm0
  __int64 v27; // rax
  int v28; // r9d
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-48h]
  unsigned int v30; // [rsp+40h] [rbp-28h] BYREF
  __int64 v31; // [rsp+48h] [rbp-20h] BYREF
  unsigned int v32; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  int v34; // [rsp+B8h] [rbp+50h] BYREF

  if ( !a2 )
  {
    v8 = 2375;
LABEL_3:
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"clientcore\\multimedia\\codecdsp\\audio\\lfxgfx\\apo\\lfxgfxapo.cpp",
      (const char *)0x80004003LL,
      dwDesiredAccess);
    return LastError;
  }
  if ( !a3 )
  {
    v8 = 2376;
    goto LABEL_3;
  }
  *a2 = 0;
  *a3 = 0;
  v11 = (char *)(*(ULONG_PTR *)((char *)&this[-7].SpinCount + 4)
               - *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1);
  if ( !v11 )
    v11 = *(char **)((char *)&this[-6].DebugInfo + 4) - *(_QWORD *)GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4;
  if ( v11 )
  {
    v12 = this - 2;
    EnterCriticalSection(this - 2);
    v13 = (CCorrAPOBase *)&this[-10];
    OwningThread = this[-6].OwningThread;
    p_OwningThread = &this[-6].OwningThread;
    if ( OwningThread )
    {
      CloseHandle(OwningThread);
      *p_OwningThread = 0;
    }
    if ( a4 )
    {
      CurrentProcess = GetCurrentProcess();
      v17 = GetCurrentProcess();
      if ( !DuplicateHandle(v17, a4, CurrentProcess, p_OwningThread, 2u, 0, 0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x95C,
                      (unsigned int)"clientcore\\multimedia\\codecdsp\\audio\\lfxgfx\\apo\\lfxgfxapo.cpp",
                      v18);
LABEL_20:
        LeaveCriticalSection(v12);
        return LastError;
      }
    }
    v30 = 0;
    v34 = 0;
    EffectState = CCorrAPOBase::GetEffectState(v13, &v30, &v34);
    LastError = EffectState;
    if ( EffectState < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x962,
        (unsigned int)"clientcore\\multimedia\\codecdsp\\audio\\lfxgfx\\apo\\lfxgfxapo.cpp",
        (const char *)(unsigned int)EffectState,
        dwDesiredAccess);
      goto LABEL_20;
    }
    if ( v34 > 0 )
    {
      v20 = v34;
      v21 = CoTaskMemAlloc(24LL * v34);
      wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(
        &v31,
        v21,
        v20);
      if ( !v31 )
      {
        LastError = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x968,
          (unsigned int)"clientcore\\multimedia\\codecdsp\\audio\\lfxgfx\\apo\\lfxgfxapo.cpp",
          (const char *)0x8007000ELL,
          dwDesiredAccess);
        wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>((__int64)&v31);
        goto LABEL_20;
      }
      v23 = v30;
      v24 = 0;
      LODWORD(v25) = 0;
      do
      {
        if ( _bittest((const int *)&v23, v25) )
        {
          v26 = *(__int128 *)((char *)&xmmword_1801B8454 + 44 * (int)v25);
          v27 = wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator[](
                  &v31,
                  (int)v24);
          v24 = (unsigned int)(v28 + 1);
          *(_OWORD *)v27 = v26;
          *(_DWORD *)(v27 + 16) = 0;
          *(_DWORD *)(v27 + 20) = 1;
        }
        v25 = (unsigned int)(v25 + 1);
      }
      while ( (unsigned int)v25 < 8 );
      *a3 = v32;
      *a2 = (struct AUDIO_SYSTEMEFFECT *)wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::release(
                                           &v31,
                                           v22,
                                           v25,
                                           v24);
      wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>((__int64)&v31);
    }
    LeaveCriticalSection(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x1800775a0  push    rbp
0x1800775a2  push    rbx
0x1800775a3  push    rsi
0x1800775a4  push    rdi
0x1800775a5  push    r12
0x1800775a7  push    r13
0x1800775a9  push    r14
0x1800775ab  push    r15
0x1800775ad  mov     rbp, rsp
0x1800775b0  sub     rsp, 68h
0x1800775b4  mov     r13, r9
0x1800775b7  mov     rsi, r8
0x1800775ba  mov     r14, rdx
0x1800775bd  mov     rbx, rcx
0x1800775c0  test    rdx, rdx
0x1800775c3  jnz     short loc_1800775E9
0x1800775c5  mov     edx, 947h; void *
0x1800775ca  mov     rcx, [rbp+40h]; this
0x1800775ce  lea     r8, aClientcoreMult; "clientcore\\multimedia\\codecdsp\\audio"...
0x1800775d5  mov     ebx, 80004003h
0x1800775da  mov     r9d, ebx; char *
0x1800775dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800775e2  mov     eax, ebx
0x1800775e4  jmp     loc_1800777D3
0x1800775e9  test    rsi, rsi
0x1800775ec  jnz     short loc_1800775F5
0x1800775ee  mov     edx, 948h
0x1800775f3  jmp     short loc_1800775CA
0x1800775f5  mov     qword ptr [rdx], 0
0x1800775fc  mov     dword ptr [r8], 0
0x180077603  mov     rax, [rcx-0F4h]
0x18007760a  sub     rax, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180077611  jnz     short loc_180077621
0x180077613  mov     rax, [rcx-0ECh]
0x18007761a  sub     rax, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x180077621  test    rax, rax
0x180077624  jz      loc_1800777D1
0x18007762a  lea     rdi, [rcx-50h]
0x18007762e  mov     rcx, rdi; lpCriticalSection
0x180077631  call    cs:__imp_EnterCriticalSection
0x180077637  lea     r15, [rbx-190h]
0x18007763e  mov     rcx, [r15+0B0h]; hObject
0x180077645  lea     r12, [rbx-0E0h]
0x18007764c  test    rcx, rcx
0x18007764f  jz      short loc_18007765F
0x180077651  call    cs:__imp_CloseHandle
0x180077657  mov     qword ptr [r12], 0
0x18007765f  test    r13, r13
0x180077662  jz      short loc_1800776BD
0x180077664  call    cs:__imp_GetCurrentProcess
0x18007766a  mov     rbx, rax
0x18007766d  call    cs:__imp_GetCurrentProcess
0x180077673  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18007767b  mov     r9, r12; lpTargetHandle
0x18007767e  mov     rcx, rax; hSourceProcessHandle
0x180077681  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180077689  mov     r8, rbx; hTargetProcessHandle
0x18007768c  mov     [rsp+68h+dwDesiredAccess], 2; dwDesiredAccess
0x180077694  mov     rdx, r13; hSourceHandle
0x180077697  call    cs:__imp_DuplicateHandle
0x18007769d  test    eax, eax
0x18007769f  jnz     short loc_1800776BD
0x1800776a1  mov     rcx, [rbp+40h]; this
0x1800776a5  lea     r8, aClientcoreMult; "clientcore\\multimedia\\codecdsp\\audio"...
0x1800776ac  mov     edx, 95Ch; void *
0x1800776b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800776b6  mov     ebx, eax
0x1800776b8  jmp     loc_180077754
0x1800776bd  lea     r8, [rbp+arg_8]; int *
0x1800776c1  mov     [rbp+var_28], 0
0x1800776c8  lea     rdx, [rbp+var_28]; unsigned int *
0x1800776cc  mov     [rbp+arg_8], 0
0x1800776d3  mov     rcx, r15; this
0x1800776d6  call    ?GetEffectState@CCorrAPOBase@@IEAAJPEAKPEAH@Z; CCorrAPOBase::GetEffectState(ulong *,int *)
0x1800776db  mov     ebx, eax
0x1800776dd  test    eax, eax
0x1800776df  jns     short loc_1800776FB
0x1800776e1  mov     rcx, [rbp+40h]; this
0x1800776e5  lea     r8, aClientcoreMult; "clientcore\\multimedia\\codecdsp\\audio"...
0x1800776ec  mov     r9d, eax; char *
0x1800776ef  mov     edx, 962h; void *
0x1800776f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800776f9  jmp     short loc_180077754
0x1800776fb  movsxd  rax, [rbp+arg_8]
0x1800776ff  test    eax, eax
0x180077701  jle     loc_1800777C8
0x180077707  lea     rcx, [rax+rax*2]
0x18007770b  mov     rbx, rax
0x18007770e  shl     rcx, 3; cb
0x180077712  call    cs:__imp_CoTaskMemAlloc
0x180077718  mov     r8, rbx
0x18007771b  lea     rcx, [rbp+var_20]
0x18007771f  mov     rdx, rax
0x180077722  call    ??0?$unique_any_array_ptr@UAUDIO_SYSTEMEFFECT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@PEAUAUDIO_SYSTEMEFFECT@@_K@Z; wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(AUDIO_SYSTEMEFFECT *,unsigned __int64)
0x180077727  cmp     [rbp+var_20], 0
0x18007772c  jnz     short loc_180077762
0x18007772e  mov     rcx, [rbp+40h]; this
0x180077732  lea     r8, aClientcoreMult; "clientcore\\multimedia\\codecdsp\\audio"...
0x180077739  mov     ebx, 8007000Eh
0x18007773e  mov     edx, 968h; void *
0x180077743  mov     r9d, ebx; char *
0x180077746  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007774b  lea     rcx, [rbp+var_20]
0x18007774f  call    ??1?$unique_any_array_ptr@UAUDIO_SYSTEMEFFECT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x180077754  mov     rcx, rdi; lpCriticalSection
0x180077757  call    cs:__imp_LeaveCriticalSection
0x18007775d  jmp     loc_1800775E2
0x180077762  mov     r10d, [rbp+var_28]
0x180077766  xor     r9d, r9d
0x180077769  xor     r8d, r8d
0x18007776c  bt      r10d, r8d
0x180077770  jnb     short loc_1800777A5
0x180077772  movsxd  rax, r8d
0x180077775  imul    rcx, rax, 2Ch ; ','
0x180077779  lea     rax, xmmword_1801B8454
0x180077780  movsxd  rdx, r9d
0x180077783  movups  xmm0, xmmword ptr [rcx+rax]
0x180077787  lea     rcx, [rbp+var_20]
0x18007778b  call    ??A?$unique_any_array_ptr@UAUDIO_SYSTEMEFFECT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAAEAUAUDIO_SYSTEMEFFECT@@_K@Z; wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator[](unsigned __int64)
0x180077790  inc     r9d
0x180077793  movdqu  xmmword ptr [rax], xmm0
0x180077797  mov     dword ptr [rax+10h], 0
0x18007779e  mov     dword ptr [rax+14h], 1
0x1800777a5  inc     r8d
0x1800777a8  cmp     r8d, 8
0x1800777ac  jb      short loc_18007776C
0x1800777ae  mov     eax, [rbp+var_18]
0x1800777b1  lea     rcx, [rbp+var_20]
0x1800777b5  mov     [rsi], eax
0x1800777b7  call    ?release@?$unique_any_array_ptr@UAUDIO_SYSTEMEFFECT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAPEAUAUDIO_SYSTEMEFFECT@@XZ; wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::release(void)
0x1800777bc  lea     rcx, [rbp+var_20]
0x1800777c0  mov     [r14], rax
0x1800777c3  call    ??1?$unique_any_array_ptr@UAUDIO_SYSTEMEFFECT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x1800777c8  mov     rcx, rdi; lpCriticalSection
0x1800777cb  call    cs:__imp_LeaveCriticalSection
0x1800777d1  xor     eax, eax
0x1800777d3  add     rsp, 68h
0x1800777d7  pop     r15
0x1800777d9  pop     r14
0x1800777db  pop     r13
0x1800777dd  pop     r12
0x1800777df  pop     rdi
0x1800777e0  pop     rsi
0x1800777e1  pop     rbx
0x1800777e2  pop     rbp
0x1800777e3  retn
```
