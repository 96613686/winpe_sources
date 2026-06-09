# PhoneController::_AssociateCallUpgradeCalls(CallUpdate const &)

- ea: `0x18003541c`
- end: `0x180035688`
- name: `?_AssociateCallUpgradeCalls@PhoneController@@IEAAJAEBUCallUpdate@@@Z`
- size: `620`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct CallUpdate *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180041858`

## callees

- `0x180010664`
- `0x1800107d8`
- `0x18002c574`
- `0x18002c580`
- `0x18003541c`
- `0x1800524c8`
- `0x18007f9ec`
- `0x18008f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180035645`
- `msvcrt!_wcsicmp` at `0x180035645`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035434`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035457`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035434`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035457`

## string_xrefs

- `0x18003543a`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_AssociateCallUpgradeCalls(PhoneController *this, const struct CallUpdate *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  volatile __int32 *v7; // rsi
  __int64 v9; // rbx
  _QWORD *v10; // rcx
  _QWORD *i; // rax
  __int64 v12; // rbx
  __int64 v13; // rdi
  _QWORD *v14; // rdi
  _QWORD *j; // rbx
  unsigned int v16; // eax
  int v17; // edx
  volatile __int32 *v18[5]; // [rsp+30h] [rbp-28h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1041);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (*((_DWORD *)a2 + 2) & 0x400000) == 0 || !*((_DWORD *)a2 + 625) )
  {
    Log_AssertionEvent_3(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1043);
    if ( (*((_DWORD *)a2 + 2) & 0x400000LL) == 0 || !*((_DWORD *)a2 + 625) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v5 = *((_QWORD *)this + 12);
  v18[0] = 0;
  PhoneCallStorage::FindCall(v5, v18, a2, 0);
  v7 = v18[0];
  if ( !v18[0] )
  {
    Log_HREvent_7(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1046);
    return 2147943568LL;
  }
  if ( (*((_QWORD *)a2 + 1) & 0x800000LL) != 0 )
  {
    v9 = *((_QWORD *)this + 12);
    utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(v18, v9 + 48);
    v10 = (_QWORD *)(v9 + 24);
    for ( i = *(_QWORD **)(v9 + 24); i != v10; i = (_QWORD *)*i )
    {
      v12 = i[2];
      if ( *((_QWORD *)a2 + 313) == *(_QWORD *)(v12 + 6768) && *((_QWORD *)a2 + 314) == *(_QWORD *)(v12 + 6776) )
        goto LABEL_18;
    }
  }
  else
  {
    if ( (*((_BYTE *)a2 + 8) & 0x20) == 0 || *((_DWORD *)a2 + 190) != 1 )
    {
      Log_AssertionEvent_3(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1060);
      if ( (*((_BYTE *)a2 + 8) & 0x20) == 0 || *((_DWORD *)a2 + 190) != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v13 = *((_QWORD *)this + 12);
    utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(v18, v13 + 48);
    v14 = (_QWORD *)(v13 + 24);
    for ( j = (_QWORD *)*v14; j != v14; j = (_QWORD *)*j )
    {
      v16 = *(_DWORD *)(j[2] + 3040LL);
      if ( v16 <= 6 )
      {
        v17 = 73;
        if ( _bittest(&v17, v16) )
        {
          if ( !_wcsicmp((const wchar_t *)(j[2] + 24LL), (const wchar_t *)v7 + 12) )
          {
            v12 = j[2];
LABEL_18:
            if ( v12 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
            goto LABEL_21;
          }
        }
      }
    }
  }
  v12 = 0;
LABEL_21:
  utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(v18);
  if ( !v12 )
  {
    Log_HREvent_7(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1075);
    (*(void (__fastcall **)(volatile __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
    return 2147943568LL;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  *((_DWORD *)v7 + 1696) = *(_DWORD *)(v12 + 3068);
  *(_DWORD *)(v12 + 6784) = *((_DWORD *)v7 + 767);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  (*(void (__fastcall **)(volatile __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
  return 0;
}

```

## disassembly

```asm
0x18003541c  mov     [rsp+arg_8], rbx
0x180035421  mov     [rsp+arg_10], rbp
0x180035426  push    rsi
0x180035427  push    rdi
0x180035428  push    r15
0x18003542a  sub     rsp, 40h
0x18003542e  mov     rdi, rdx
0x180035431  mov     rbx, rcx
0x180035434  call    cs:__imp_GetCurrentThreadId
0x18003543a  lea     r15, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180035441  cmp     [rbx+0F0h], eax
0x180035447  jz      short loc_18003546A
0x180035449  mov     r8d, 411h
0x18003544f  mov     rdx, r15
0x180035452  call    Log_AssertionEvent_3
0x180035457  call    cs:__imp_GetCurrentThreadId
0x18003545d  cmp     [rbx+0F0h], eax
0x180035463  jz      short loc_18003546A
0x180035465  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003546a  mov     eax, [rdi+8]
0x18003546d  bt      rax, 16h
0x180035472  jnb     short loc_18003547D
0x180035474  cmp     dword ptr [rdi+9C4h], 0
0x18003547b  jnz     short loc_1800354A3
0x18003547d  mov     r8d, 413h
0x180035483  mov     rdx, r15
0x180035486  call    Log_AssertionEvent_3
0x18003548b  mov     eax, [rdi+8]
0x18003548e  bt      rax, 16h
0x180035493  jnb     short loc_18003549E
0x180035495  cmp     dword ptr [rdi+9C4h], 0
0x18003549c  jnz     short loc_1800354A3
0x18003549e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800354a3  mov     rcx, [rbx+60h]
0x1800354a7  lea     rdx, [rsp+58h+var_28]
0x1800354ac  xor     r9d, r9d
0x1800354af  mov     [rsp+58h+var_28], 0
0x1800354b8  mov     r8, rdi
0x1800354bb  call    ?FindCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@AEBIPEAUISecurityToken@@@Z; PhoneCallStorage::FindCall(uint const &,ISecurityToken *)
0x1800354c0  mov     rsi, [rsp+58h+var_28]
0x1800354c5  test    rsi, rsi
0x1800354c8  jnz     short loc_1800354E8
0x1800354ca  mov     ebx, 80070490h
0x1800354cf  mov     r9d, 416h
0x1800354d5  mov     ecx, ebx
0x1800354d7  mov     r8, r15
0x1800354da  xor     edx, edx
0x1800354dc  call    Log_HREvent_7
0x1800354e1  mov     eax, ebx
0x1800354e3  jmp     loc_1800355BE
0x1800354e8  test    qword ptr [rdi+8], 800000h
0x1800354f0  jz      loc_1800355D1
0x1800354f6  mov     rbx, [rbx+60h]
0x1800354fa  lea     rcx, [rsp+58h+var_28]
0x1800354ff  lea     rdx, [rbx+30h]
0x180035503  call    ??0?$lock_guard@VThreadCheck@@@utl@@QEAA@AEAVThreadCheck@@@Z; utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(ThreadCheck &)
0x180035508  lea     rcx, [rbx+18h]
0x18003550c  mov     rax, [rcx]
0x18003550f  cmp     rax, rcx
0x180035512  jz      short loc_180035553
0x180035514  mov     rbx, [rax+10h]
0x180035518  mov     rdx, [rdi+9C8h]
0x18003551f  cmp     rdx, [rbx+1A70h]
0x180035526  jnz     short loc_180035538
0x180035528  mov     rdx, [rdi+9D0h]
0x18003552f  cmp     rdx, [rbx+1A78h]
0x180035536  jz      short loc_18003553D
0x180035538  mov     rax, [rax]
0x18003553b  jmp     short loc_18003550F
0x18003553d  test    rbx, rbx
0x180035540  jz      short loc_180035555
0x180035542  mov     rax, [rbx]
0x180035545  mov     rcx, rbx
0x180035548  mov     rax, [rax+8]
0x18003554c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035551  jmp     short loc_180035555
0x180035553  xor     ebx, ebx
0x180035555  lea     rcx, [rsp+58h+var_28]
0x18003555a  call    ??1?$lock_guard@VThreadCheck@@@utl@@QEAA@XZ; utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(void)
0x18003555f  test    rbx, rbx
0x180035562  jz      loc_18003565D
0x180035568  mov     rax, [rbx]
0x18003556b  mov     rcx, rbx
0x18003556e  mov     rax, [rax+8]
0x180035572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035577  mov     rax, [rbx]
0x18003557a  mov     rcx, rbx
0x18003557d  mov     rax, [rax+10h]
0x180035581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035586  mov     eax, [rbx+0BFCh]
0x18003558c  mov     rcx, rbx
0x18003558f  mov     [rsi+1A80h], eax
0x180035595  mov     eax, [rsi+0BFCh]
0x18003559b  mov     [rbx+1A80h], eax
0x1800355a1  mov     rax, [rbx]
0x1800355a4  mov     rax, [rax+10h]
0x1800355a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355ad  mov     rax, [rsi]
0x1800355b0  mov     rcx, rsi
0x1800355b3  mov     rax, [rax+10h]
0x1800355b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355bc  xor     eax, eax
0x1800355be  mov     rbx, [rsp+58h+arg_8]
0x1800355c3  mov     rbp, [rsp+58h+arg_10]
0x1800355c8  add     rsp, 40h
0x1800355cc  pop     r15
0x1800355ce  pop     rdi
0x1800355cf  pop     rsi
0x1800355d0  retn
0x1800355d1  test    byte ptr [rdi+8], 20h
0x1800355d5  jz      short loc_1800355E0
0x1800355d7  cmp     dword ptr [rdi+2F8h], 1
0x1800355de  jz      short loc_180035602
0x1800355e0  mov     r8d, 424h
0x1800355e6  mov     rdx, r15
0x1800355e9  call    Log_AssertionEvent_3
0x1800355ee  test    byte ptr [rdi+8], 20h
0x1800355f2  jz      short loc_1800355FD
0x1800355f4  cmp     dword ptr [rdi+2F8h], 1
0x1800355fb  jz      short loc_180035602
0x1800355fd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180035602  mov     rdi, [rbx+60h]
0x180035606  lea     rcx, [rsp+58h+var_28]
0x18003560b  lea     rdx, [rdi+30h]
0x18003560f  call    ??0?$lock_guard@VThreadCheck@@@utl@@QEAA@AEAVThreadCheck@@@Z; utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(ThreadCheck &)
0x180035614  add     rdi, 18h
0x180035618  mov     rbx, [rdi]
0x18003561b  cmp     rbx, rdi
0x18003561e  jz      loc_180035553
0x180035624  mov     rcx, [rbx+10h]
0x180035628  add     rcx, 18h; String1
0x18003562c  mov     eax, [rcx+0BC8h]
0x180035632  cmp     eax, 6
0x180035635  ja      short loc_18003564F
0x180035637  mov     edx, 49h ; 'I'
0x18003563c  bt      edx, eax
0x18003563f  jnb     short loc_18003564F
0x180035641  lea     rdx, [rsi+18h]; String2
0x180035645  call    cs:__imp__wcsicmp
0x18003564b  test    eax, eax
0x18003564d  jz      short loc_180035654
0x18003564f  mov     rbx, [rbx]
0x180035652  jmp     short loc_18003561B
0x180035654  mov     rbx, [rbx+10h]
0x180035658  jmp     loc_18003553D
0x18003565d  mov     ebx, 80070490h
0x180035662  mov     r9d, 433h
0x180035668  mov     ecx, ebx
0x18003566a  mov     r8, r15
0x18003566d  xor     edx, edx
0x18003566f  call    Log_HREvent_7
0x180035674  mov     rax, [rsi]
0x180035677  mov     rcx, rsi
0x18003567a  mov     rax, [rax+10h]
0x18003567e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035683  jmp     loc_1800354E1
```
