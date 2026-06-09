# CDPComActivityStoreManagementControl::SetActivityPermissionScopePolicy(CDPComActivityPolicySourceAndType const *,uchar,char const *,int,CDPComSetActivityPolicyOptionFlags)

- ea: `0x1800482f0`
- end: `0x1800484fa`
- name: `?SetActivityPermissionScopePolicy@CDPComActivityStoreManagementControl@@UEAAJPEBUCDPComActivityPolicySourceAndType@@EPEBDHW4CDPComSetActivityPolicyOptionFlags@@@Z`
- size: `522`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000e934`
- `0x180018820`
- `0x18001d0f4`
- `0x180023b70`
- `0x18002d204`
- `0x180042ce0`
- `0x180043988`
- `0x180043d60`
- `0x1800458f0`
- `0x1800482f0`
- `0x18005c800`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048436`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048436`

## string_xrefs

- `0x180048461`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18004841e`: `..\cdpcomactivitystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDPComActivityStoreManagementControl::SetActivityPermissionScopePolicy(
        __int64 a1,
        __int64 a2,
        bool *a3,
        __int64 a4,
        int a5,
        __int16 a6)
{
  __int64 v7; // r14
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v15; // rsi
  __int64 v16; // r8
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // r8d
  _BYTE v27[32]; // [rsp+0h] [rbp-108h] BYREF
  __int64 v28; // [rsp+20h] [rbp-E8h]
  __int64 v29; // [rsp+28h] [rbp-E0h]
  unsigned int v30; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int16 v31; // [rsp+44h] [rbp-C4h] BYREF
  __int64 v32; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B8h] BYREF
  void *v34; // [rsp+58h] [rbp-B0h] BYREF
  char *v35; // [rsp+60h] [rbp-A8h]
  char *v36; // [rsp+68h] [rbp-A0h]
  const char *v37; // [rsp+70h] [rbp-98h] BYREF
  int v38; // [rsp+78h] [rbp-90h] BYREF
  char v39[24]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+98h] [rbp-70h] BYREF

  v7 = (unsigned __int8)a3;
  v10 = cdp::CheckCallerCapability((cdp *)L"activitySystem", &v31, a3);
  if ( v10 < 0 )
  {
    v30 = v10;
    LODWORD(v32) = 1844;
LABEL_3:
    Log<long &,char const (&)[27],int>(v12, v11, &v30, v13, &v32);
    return v30;
  }
  if ( !(_BYTE)v31 )
  {
    v30 = -2147024891;
    LODWORD(v32) = 1845;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v30 = -2147024809;
    LODWORD(v32) = 1847;
    goto LABEL_3;
  }
  v30 = 0;
  try
  {
    std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(&v34);
    v15 = a2 + 8 * v7;
    while ( a2 != v15 )
    {
      LODWORD(v32) = *(_DWORD *)a2;
      WORD2(v32) = *(_WORD *)(a2 + 4);
      if ( v35 == v36 )
      {
        std::vector<CDPActivityPolicySourceAndType>::_Emplace_reallocate<CDPActivityPolicySourceAndType>(
          &v34,
          v35,
          &v32);
      }
      else
      {
        *(_QWORD *)v35 = v32;
        v35 += 8;
      }
      a2 += 8;
    }
    v17 = *(__int64 **)(a1 + 136);
    v18 = *v17;
    LOWORD(v29) = a6;
    LOBYTE(v28) = a5 != 0;
    LOBYTE(v16) = v7;
    v19 = (*(__int64 (__fastcall **)(__int64 *, void *, __int64, __int64, _DWORD, _DWORD))(v18 + 48))(
            v17,
            v34,
            v16,
            a4,
            v28,
            v29);
    if ( v19 < 0 )
    {
      v37 = "..\\cdpcomactivitystore.cpp";
      v38 = 1862;
      LODWORD(v32) = v19;
      CurrentThreadId = GetCurrentThreadId();
      v33 = CurrentThreadId;
      Log<long &,char const * &,int &,unsigned __int64>(
        CurrentThreadId,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v32,
        (unsigned int)&v37,
        (__int64)&v38,
        (__int64)&v33);
      v21 = cdp::ExceptionStackFromSourceLocationInfo(v39, &v37);
      v24 = cdp::ErrorCodeToString((unsigned int)v19, v22, v23, v21);
      ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v19, v24);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    if ( v34 )
      std::_Deallocate<16>(v34, (v36 - (_BYTE *)v34) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  catch ( ... )
  {
    LODWORD(v25) = GetCurrentThreadId();
    v33 = v25;
    LODWORD(v32) = 1864;
    cdp::CatchAllToHR<char const (&)[27],int,unsigned __int64>(
      (unsigned int)v27 + 64,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\""
                    ":\"SetActivityPermissionScopePolicy failed\"}",
      v26,
      (unsigned int)v27 + 72,
      (__int64)&v33);
  }
  return 0;
}

```

## disassembly

```asm
0x1800482f0  push    rbx
0x1800482f2  push    rsi
0x1800482f3  push    rdi
0x1800482f4  push    r13
0x1800482f6  push    r14
0x1800482f8  push    r15
0x1800482fa  sub     rsp, 0D8h
0x180048301  mov     r15, r9
0x180048304  movzx   r14d, r8b
0x180048308  mov     rbx, rdx
0x18004830b  mov     r13, rcx
0x18004830e  lea     rdx, [rsp+108h+var_C4]; unsigned __int16 *
0x180048313  lea     rcx, aActivitysystem; "activitySystem"
0x18004831a  call    ?CheckCallerCapability@cdp@@YAJPEBGAEA_N@Z; cdp::CheckCallerCapability(ushort const *,bool &)
0x18004831f  test    eax, eax
0x180048321  jns     short loc_18004834C
0x180048323  mov     [rsp+108h+var_C8], eax
0x180048327  mov     dword ptr [rsp+108h+var_C0], 734h
0x18004832f  lea     rax, [rsp+108h+var_C0]
0x180048334  mov     [rsp+108h+var_E8], rax
0x180048339  lea     r8, [rsp+108h+var_C8]
0x18004833e  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180048343  mov     eax, [rsp+108h+var_C8]
0x180048347  jmp     loc_1800484E9
0x18004834c  cmp     byte ptr [rsp+108h+var_C4], 0
0x180048351  jnz     short loc_180048365
0x180048353  mov     [rsp+108h+var_C8], 80070005h
0x18004835b  mov     dword ptr [rsp+108h+var_C0], 735h
0x180048363  jmp     short loc_18004832F
0x180048365  test    rbx, rbx
0x180048368  jnz     short loc_18004837C
0x18004836a  mov     [rsp+108h+var_C8], 80070057h
0x180048372  mov     dword ptr [rsp+108h+var_C0], 737h
0x18004837a  jmp     short loc_18004832F
0x18004837c  xor     edi, edi
0x18004837e  mov     [rsp+108h+var_C8], edi
0x180048382  lea     rcx, [rsp+108h+var_B0]
0x180048387  call    ??0?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@QEAA@XZ; std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(void)
0x18004838c  nop
0x18004838d  lea     rsi, [rbx+r14*8]
0x180048391  cmp     rbx, rsi
0x180048394  jz      short loc_1800483D6
0x180048396  mov     eax, [rbx]
0x180048398  mov     dword ptr [rsp+108h+var_C0], eax
0x18004839c  movzx   eax, word ptr [rbx+4]
0x1800483a0  mov     word ptr [rsp+108h+var_C0+4], ax
0x1800483a5  mov     rdx, [rsp+108h+var_A8]
0x1800483aa  cmp     rdx, [rsp+108h+var_A0]
0x1800483af  jz      short loc_1800483C1
0x1800483b1  mov     rax, [rsp+108h+var_C0]
0x1800483b6  mov     [rdx], rax
0x1800483b9  add     [rsp+108h+var_A8], 8
0x1800483bf  jmp     short loc_1800483D0
0x1800483c1  lea     r8, [rsp+108h+var_C0]
0x1800483c6  lea     rcx, [rsp+108h+var_B0]
0x1800483cb  call    ??$_Emplace_reallocate@UCDPActivityPolicySourceAndType@@@?$vector@UCDPActivityPolicySourceAndType@@V?$allocator@UCDPActivityPolicySourceAndType@@@std@@@std@@AEAAPEAUCDPActivityPolicySourceAndType@@QEAU2@$$QEAU2@@Z; std::vector<CDPActivityPolicySourceAndType>::_Emplace_reallocate<CDPActivityPolicySourceAndType>(CDPActivityPolicySourceAndType * const,CDPActivityPolicySourceAndType &&)
0x1800483d0  add     rbx, 8
0x1800483d4  jmp     short loc_180048391
0x1800483d6  mov     rcx, [r13+88h]
0x1800483dd  mov     rax, [rcx]
0x1800483e0  movzx   r9d, [rsp+108h+arg_28]
0x1800483e9  cmp     [rsp+108h+arg_20], 0
0x1800483f1  setnz   r8b
0x1800483f5  mov     word ptr [rsp+108h+var_E0], r9w
0x1800483fb  mov     byte ptr [rsp+108h+var_E8], r8b
0x180048400  mov     r9, r15
0x180048403  mov     r8b, r14b
0x180048406  mov     rdx, [rsp+108h+var_B0]
0x18004840b  mov     rax, [rax+30h]
0x18004840f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048414  mov     ebx, eax
0x180048416  test    eax, eax
0x180048418  jns     loc_1800484B0
0x18004841e  lea     rax, aCdpcomactivity; "..\\cdpcomactivitystore.cpp"
0x180048425  mov     [rsp+108h+var_98], rax
0x18004842a  mov     [rsp+108h+var_90], 746h
0x180048432  mov     dword ptr [rsp+108h+var_C0], ebx
0x180048436  call    cs:__imp_GetCurrentThreadId
0x18004843c  mov     ecx, eax
0x18004843e  mov     [rsp+108h+var_B8], rcx
0x180048443  lea     rax, [rsp+108h+var_B8]
0x180048448  mov     [rsp+108h+var_E0], rax
0x18004844d  lea     rax, [rsp+108h+var_90]
0x180048452  mov     [rsp+108h+var_E8], rax
0x180048457  lea     r9, [rsp+108h+var_98]
0x18004845c  lea     r8, [rsp+108h+var_C0]
0x180048461  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180048468  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18004846d  lea     rdx, [rsp+108h+var_98]
0x180048472  lea     rcx, [rsp+108h+var_88]
0x18004847a  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18004847f  mov     r9, rax
0x180048482  mov     ecx, ebx
0x180048484  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180048489  mov     r8, rax
0x18004848c  mov     edx, ebx
0x18004848e  lea     rcx, [rsp+108h+pExceptionObject]
0x180048496  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18004849b  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800484a2  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800484aa  call    _CxxThrowException_0
0x1800484b0  mov     rcx, [rsp+108h+var_B0]
0x1800484b5  test    rcx, rcx
0x1800484b8  jz      short loc_1800484CC
0x1800484ba  mov     rdx, [rsp+108h+var_A0]
0x1800484bf  sub     rdx, rcx
0x1800484c2  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800484c6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800484cb  nop
0x1800484cc  jmp     short loc_1800484D2
0x1800484ce  mov     edi, [rsp+108h+var_C8]
0x1800484d2  test    edi, edi
0x1800484d4  jns     short loc_1800484E7
0x1800484d6  mov     [rsp+108h+var_C8], edi
0x1800484da  mov     dword ptr [rsp+108h+var_C0], 749h
0x1800484e2  jmp     loc_18004832F
0x1800484e7  xor     eax, eax
0x1800484e9  add     rsp, 0D8h
0x1800484f0  pop     r15
0x1800484f2  pop     r14
0x1800484f4  pop     r13
0x1800484f6  pop     rdi
0x1800484f7  pop     rsi
0x1800484f8  pop     rbx
0x1800484f9  retn
```
