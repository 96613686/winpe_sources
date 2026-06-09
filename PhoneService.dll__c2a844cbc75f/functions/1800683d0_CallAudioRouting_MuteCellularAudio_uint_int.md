# CallAudioRouting::_MuteCellularAudio(uint,int)

- ea: `0x1800683d0`
- end: `0x18006855e`
- name: `?_MuteCellularAudio@CallAudioRouting@@AEAAXIH@Z`
- size: `398`
- prototype: `void __fastcall(CallAudioRouting *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180064350`

## callees

- `0x18005f9b4`
- `0x18005f9c0`
- `0x18006321c`
- `0x180064dac`
- `0x1800683d0`
- `0x18007f9ec`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006841b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800684d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006841b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800684d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068459`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006848c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068512`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068526`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068459`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006848c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068512`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068526`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800683e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068408`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800683e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068408`

## string_xrefs

- `0x1800683fc`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180068443`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800684b6`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800684fc`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
void __fastcall CallAudioRouting::_MuteCellularAudio(CallAudioRouting *this, unsigned int a2, unsigned int a3)
{
  __int64 v6; // rcx
  unsigned int v7; // r14d
  int v8; // r15d
  __int64 v9; // rbx
  int v10; // eax
  struct CallAudioRouting::CellularAudioState *v11[9]; // [rsp+30h] [rbp-48h] BYREF

  if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2946);
    if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v11[0] = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState(this, a2, v11) )
  {
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2961);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    return;
  }
  v7 = *((_DWORD *)v11[0] + 1);
  v8 = *((_DWORD *)v11[0] + 3);
  v9 = *((_QWORD *)v11[0] + 3);
  if ( v9 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 8LL))(*((_QWORD *)v11[0] + 3));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( v7 )
  {
    if ( !v8 )
    {
      v10 = CallAudioRouting::_CallAudioRoutingManagerToSetMuteTx(this, a2, v7, a3);
      if ( v10 < 0 )
      {
        Log_HREvent_17(
          (unsigned int)v10,
          0,
          "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp",
          2975);
        goto LABEL_12;
      }
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v11[0] = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState(this, a2, v11) )
  {
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2988);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
LABEL_12:
    if ( !v9 )
      return;
    goto LABEL_17;
  }
  *((_DWORD *)v11[0] + 4) = a3;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, a2, a3);
LABEL_17:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
}

```

## disassembly

```asm
0x1800683d0  push    rbx
0x1800683d2  push    rbp
0x1800683d3  push    rsi
0x1800683d4  push    rdi
0x1800683d5  push    r12
0x1800683d7  push    r14
0x1800683d9  push    r15
0x1800683db  sub     rsp, 40h
0x1800683df  mov     r12d, r8d
0x1800683e2  mov     ebp, edx
0x1800683e4  mov     rsi, rcx
0x1800683e7  call    cs:__imp_GetCurrentThreadId
0x1800683ed  lea     rdi, [rsi+58h]
0x1800683f1  cmp     [rdi+10h], eax
0x1800683f4  jnz     short loc_180068418
0x1800683f6  mov     r8d, 0B82h
0x1800683fc  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180068403  call    Log_AssertionEvent_9
0x180068408  call    cs:__imp_GetCurrentThreadId
0x18006840e  cmp     [rsi+68h], eax
0x180068411  jnz     short loc_180068418
0x180068413  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180068418  mov     rcx, rdi; lpCriticalSection
0x18006841b  call    cs:__imp_EnterCriticalSection
0x180068421  lea     r8, [rsp+78h+var_48]; struct CallAudioRouting::CellularAudioState **
0x180068426  mov     [rsp+78h+var_48], 0
0x18006842f  mov     edx, ebp; unsigned int
0x180068431  mov     rcx, rsi; this
0x180068434  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x180068439  test    eax, eax
0x18006843b  jnz     short loc_180068464
0x18006843d  mov     r9d, 0B91h
0x180068443  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006844a  xor     edx, edx
0x18006844c  mov     ecx, 80070490h
0x180068451  call    Log_HREvent_17
0x180068456  mov     rcx, rdi; lpCriticalSection
0x180068459  call    cs:__imp_LeaveCriticalSection
0x18006845f  jmp     loc_18006854F
0x180068464  mov     rbx, [rsp+78h+var_48]
0x180068469  mov     r14d, [rbx+4]
0x18006846d  mov     r15d, [rbx+0Ch]
0x180068471  mov     rbx, [rbx+18h]
0x180068475  test    rbx, rbx
0x180068478  jz      short loc_180068489
0x18006847a  mov     rax, [rbx]
0x18006847d  mov     rcx, rbx
0x180068480  mov     rax, [rax+8]
0x180068484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068489  mov     rcx, rdi; lpCriticalSection
0x18006848c  call    cs:__imp_LeaveCriticalSection
0x180068492  test    r14d, r14d
0x180068495  jz      short loc_1800684D1
0x180068497  test    r15d, r15d
0x18006849a  jnz     short loc_1800684D1
0x18006849c  mov     r9d, r12d
0x18006849f  mov     r8d, r14d
0x1800684a2  mov     edx, ebp
0x1800684a4  mov     rcx, rsi
0x1800684a7  call    ?_CallAudioRoutingManagerToSetMuteTx@CallAudioRouting@@AEAAJIW4CellularAudioType@@H@Z; CallAudioRouting::_CallAudioRoutingManagerToSetMuteTx(uint,CellularAudioType,int)
0x1800684ac  test    eax, eax
0x1800684ae  jns     short loc_1800684D1
0x1800684b0  mov     r9d, 0B9Fh
0x1800684b6  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800684bd  xor     edx, edx
0x1800684bf  mov     ecx, eax
0x1800684c1  call    Log_HREvent_17
0x1800684c6  test    rbx, rbx
0x1800684c9  jz      loc_18006854F
0x1800684cf  jmp     short loc_180068540
0x1800684d1  mov     rcx, rdi; lpCriticalSection
0x1800684d4  call    cs:__imp_EnterCriticalSection
0x1800684da  lea     r8, [rsp+78h+var_48]; struct CallAudioRouting::CellularAudioState **
0x1800684df  mov     [rsp+78h+var_48], 0
0x1800684e8  mov     edx, ebp; unsigned int
0x1800684ea  mov     rcx, rsi; this
0x1800684ed  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x1800684f2  test    eax, eax
0x1800684f4  jnz     short loc_18006851A
0x1800684f6  mov     r9d, 0BACh
0x1800684fc  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180068503  xor     edx, edx
0x180068505  mov     ecx, 80070490h
0x18006850a  call    Log_HREvent_17
0x18006850f  mov     rcx, rdi; lpCriticalSection
0x180068512  call    cs:__imp_LeaveCriticalSection
0x180068518  jmp     short loc_1800684C6
0x18006851a  mov     rax, [rsp+78h+var_48]
0x18006851f  mov     rcx, rdi; lpCriticalSection
0x180068522  mov     [rax+10h], r12d
0x180068526  call    cs:__imp_LeaveCriticalSection
0x18006852c  mov     rax, [rbx]
0x18006852f  mov     r8d, r12d
0x180068532  mov     edx, ebp
0x180068534  mov     rcx, rbx
0x180068537  mov     rax, [rax+18h]
0x18006853b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068540  mov     rax, [rbx]
0x180068543  mov     rcx, rbx
0x180068546  mov     rax, [rax+10h]
0x18006854a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006854f  add     rsp, 40h
0x180068553  pop     r15
0x180068555  pop     r14
0x180068557  pop     r12
0x180068559  pop     rdi
0x18006855a  pop     rsi
0x18006855b  pop     rbp
0x18006855c  pop     rbx
0x18006855d  retn
```
