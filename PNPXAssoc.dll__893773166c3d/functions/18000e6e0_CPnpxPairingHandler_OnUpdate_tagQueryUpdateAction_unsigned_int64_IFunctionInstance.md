# CPnpxPairingHandler::OnUpdate(tagQueryUpdateAction,unsigned __int64,IFunctionInstance *)

- ea: `0x18000e6e0`
- end: `0x18000e86a`
- name: `?OnUpdate@CPnpxPairingHandler@@UEAAJW4tagQueryUpdateAction@@_KPEAUIFunctionInstance@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(CPnpxPairingHandler *this, enum tagQueryUpdateAction, __int64, struct IFunctionInstance *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callees

- `0x18000bc98`
- `0x18000bce4`
- `0x18000bd30`
- `0x18000d2a8`
- `0x18000d7d8`
- `0x18000db10`
- `0x18000de14`
- `0x18000e6e0`
- `0x18000ebc8`
- `0x18000f134`
- `0x180014010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000e7a8`
- `KERNEL32!LeaveCriticalSection` at `0x18000e7a8`
- `KERNEL32!EnterCriticalSection` at `0x18000e72e`
- `KERNEL32!EnterCriticalSection` at `0x18000e72e`

## pseudocode

```c
__int64 __fastcall CPnpxPairingHandler::OnUpdate(
        CPnpxPairingHandler *this,
        enum tagQueryUpdateAction a2,
        __int64 a3,
        struct IFunctionInstance *a4)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbp
  CPnpxPairingHandler *v7; // rbx
  int v8; // edi
  struct IPairingCallback *PairingCallback; // rdi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v7 = (CPnpxPairingHandler *)((char *)this - 16);
  v8 = 1;
  if ( a2 == QUA_REMOVE && (unsigned int)(*((_DWORD *)v7 + 30) - 6) <= 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  }
  else
  {
    v8 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 58);
  }
  LeaveCriticalSection(v6);
  if ( v8 )
  {
    CPnpxPairingHandler::SetState((__int64)v7, 0, 0);
    CPnpxPairingHandler::BeginCallback(v7);
    PairingCallback = CPnpxPairingHandler::GetPairingCallback(v7);
    if ( PairingCallback )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
      (*(void (__fastcall **)(struct IPairingCallback *, _QWORD, _QWORD))(*(_QWORD *)PairingCallback + 88LL))(
        PairingCallback,
        0,
        0);
      (*(void (__fastcall **)(struct IPairingCallback *))(*(_QWORD *)PairingCallback + 16LL))(PairingCallback);
    }
    CPnpxPairingHandler::EndCallback(v7);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000e6e0  push    rbx
0x18000e6e2  push    rbp
0x18000e6e3  push    rsi
0x18000e6e4  push    rdi
0x18000e6e5  push    r15
0x18000e6e7  sub     rsp, 30h
0x18000e6eb  mov     esi, edx
0x18000e6ed  mov     rbx, rcx
0x18000e6f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6f7  lea     r15, WPP_GLOBAL_Control
0x18000e6fe  cmp     rcx, r15
0x18000e701  jz      short loc_18000E727
0x18000e703  cmp     byte ptr [rcx+19h], 4
0x18000e707  jb      short loc_18000E727
0x18000e709  mov     rcx, [rcx+10h]
0x18000e70d  lea     rax, [rbx-10h]
0x18000e711  mov     edx, 38h ; '8'
0x18000e716  mov     [rsp+58h+var_38], rax
0x18000e71b  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000e722  call    WPP_SF_sq
0x18000e727  lea     rbp, [rbx+10h]
0x18000e72b  mov     rcx, rbp; lpCriticalSection
0x18000e72e  call    cs:__imp_EnterCriticalSection
0x18000e734  add     rbx, 0FFFFFFFFFFFFFFF0h
0x18000e738  mov     edi, 1
0x18000e73d  cmp     esi, edi
0x18000e73f  jnz     short loc_18000E779
0x18000e741  mov     r8d, [rbx+78h]
0x18000e745  lea     eax, [r8-6]
0x18000e749  cmp     eax, edi
0x18000e74b  ja      short loc_18000E779
0x18000e74d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e754  cmp     rcx, r15
0x18000e757  jz      short loc_18000E7A5
0x18000e759  cmp     byte ptr [rcx+19h], 4
0x18000e75d  jb      short loc_18000E7A5
0x18000e75f  mov     rcx, [rcx+10h]
0x18000e763  lea     edx, [rdi+38h]
0x18000e766  mov     dword ptr [rsp+58h+var_38], r8d
0x18000e76b  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000e772  call    WPP_SF_sd
0x18000e777  jmp     short loc_18000E7A5
0x18000e779  mov     r8, cs:WPP_GLOBAL_Control
0x18000e780  xor     edi, edi
0x18000e782  cmp     r8, r15
0x18000e785  jz      short loc_18000E7A5
0x18000e787  cmp     byte ptr [r8+19h], 4
0x18000e78c  jb      short loc_18000E7A5
0x18000e78e  mov     eax, [rbx+78h]
0x18000e791  lea     edx, [rdi+3Ah]
0x18000e794  mov     rcx, [r8+10h]
0x18000e798  mov     [rsp+58h+var_30], eax
0x18000e79c  mov     dword ptr [rsp+58h+var_38], esi
0x18000e7a0  call    WPP_SF_sdd
0x18000e7a5  mov     rcx, rbp; lpCriticalSection
0x18000e7a8  call    cs:__imp_LeaveCriticalSection
0x18000e7ae  test    edi, edi
0x18000e7b0  jz      short loc_18000E829
0x18000e7b2  xor     r8d, r8d
0x18000e7b5  xor     edx, edx
0x18000e7b7  mov     rcx, rbx
0x18000e7ba  call    ?SetState@CPnpxPairingHandler@@IEAAJW4_PAIRING_STATE@@PEAW42@@Z; CPnpxPairingHandler::SetState(_PAIRING_STATE,_PAIRING_STATE *)
0x18000e7bf  mov     rcx, rbx; this
0x18000e7c2  call    ?BeginCallback@CPnpxPairingHandler@@IEAAXXZ; CPnpxPairingHandler::BeginCallback(void)
0x18000e7c7  mov     rcx, rbx; this
0x18000e7ca  call    ?GetPairingCallback@CPnpxPairingHandler@@IEAAPEAUIPairingCallback@@XZ; CPnpxPairingHandler::GetPairingCallback(void)
0x18000e7cf  mov     rdi, rax
0x18000e7d2  test    rax, rax
0x18000e7d5  jz      short loc_18000E821
0x18000e7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7de  cmp     rcx, r15
0x18000e7e1  jz      short loc_18000E7FE
0x18000e7e3  cmp     byte ptr [rcx+19h], 4
0x18000e7e7  jb      short loc_18000E7FE
0x18000e7e9  mov     rcx, [rcx+10h]
0x18000e7ed  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000e7f4  mov     edx, 3Bh ; ';'
0x18000e7f9  call    WPP_SF_s
0x18000e7fe  mov     rax, [rdi]
0x18000e801  xor     r8d, r8d
0x18000e804  xor     edx, edx
0x18000e806  mov     rcx, rdi
0x18000e809  mov     rax, [rax+58h]
0x18000e80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e812  mov     rax, [rdi]
0x18000e815  mov     rcx, rdi
0x18000e818  mov     rax, [rax+10h]
0x18000e81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e821  mov     rcx, rbx; this
0x18000e824  call    ?EndCallback@CPnpxPairingHandler@@IEAAXXZ; CPnpxPairingHandler::EndCallback(void)
0x18000e829  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e830  cmp     rcx, r15
0x18000e833  jz      short loc_18000E85D
0x18000e835  cmp     byte ptr [rcx+19h], 4
0x18000e839  jb      short loc_18000E85D
0x18000e83b  mov     rcx, [rcx+10h]
0x18000e83f  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000e846  mov     edx, 3Ch ; '<'
0x18000e84b  mov     [rsp+58h+var_30], 0
0x18000e853  mov     [rsp+58h+var_38], rbx
0x18000e858  call    WPP_SF_sqd
0x18000e85d  xor     eax, eax
0x18000e85f  add     rsp, 30h
0x18000e863  pop     r15
0x18000e865  pop     rdi
0x18000e866  pop     rsi
0x18000e867  pop     rbp
0x18000e868  pop     rbx
0x18000e869  retn
```
