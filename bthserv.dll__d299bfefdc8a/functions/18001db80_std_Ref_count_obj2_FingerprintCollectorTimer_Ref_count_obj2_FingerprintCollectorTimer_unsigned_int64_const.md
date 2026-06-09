# std::_Ref_count_obj2<FingerprintCollectorTimer>::_Ref_count_obj2<FingerprintCollectorTimer>(unsigned __int64 const &)

- ea: `0x18001db80`
- end: `0x18001dd35`
- name: `??$?0AEB_K@?$_Ref_count_obj2@VFingerprintCollectorTimer@@@std@@QEAA@AEB_K@Z`
- size: `437`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f64c`

## callees

- `0x1800024ac`
- `0x1800166f0`
- `0x18001db80`
- `0x18001de38`
- `0x18001f51c`
- `0x18003111c`
- `0x180031c74`
- `0x18003238c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dc64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dc64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dc51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dcd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dc51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dcd0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dcde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dcde`

## string_xrefs

- `0x18001dd23`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\FingerprintCollectorTimers.h`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<FingerprintCollectorTimer>::_Ref_count_obj2<FingerprintCollectorTimer>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v3; // rdi
  __int64 v4; // rbx
  _QWORD *v5; // rsi
  HANDLE ProcessHeap; // rax
  char *v7; // rax
  char *v8; // rbx
  int v9; // edi
  void (__fastcall *v10)(__int64); // rbp
  __int64 v11; // r15
  HANDLE v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  int v18[2]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v19; // [rsp+28h] [rbp-70h]
  __int128 v20; // [rsp+30h] [rbp-68h]
  __int64 v21; // [rsp+40h] [rbp-58h]
  __int64 (__fastcall *v22)(); // [rsp+48h] [rbp-50h]
  __int16 v23; // [rsp+50h] [rbp-48h]
  int v24; // [rsp+52h] [rbp-46h]
  __int16 v25; // [rsp+56h] [rbp-42h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<FingerprintCollectorTimer>::`vftable';
  v3 = a1 + 16;
  v4 = *a2;
  Microsoft::Bluetooth::Foundation::AsyncObjectBase::AsyncObjectBase((Microsoft::Bluetooth::Foundation::AsyncObjectBase *)(a1 + 16));
  *(_DWORD *)(v3 + 24) = 1718641519;
  *(_QWORD *)(v3 + 32) = 0;
  *(_QWORD *)(v3 + 40) = 0;
  *(_QWORD *)(v3 + 48) = 0;
  *(_QWORD *)(v3 + 56) = 0;
  v5 = (_QWORD *)(v3 + 64);
  *(_QWORD *)(v3 + 64) = 0;
  *(_QWORD *)v3 = &FingerprintCollectorTimer::`vftable';
  *(_QWORD *)(v3 + 72) = v4;
  Microsoft::Bluetooth::Foundation::StateMachineTimer::Make();
  *(_QWORD *)(v3 + 96) = 30;
  v24 = 0;
  v25 = 0;
  *(_QWORD *)v18 = &FingerprintCollectorStateMachine<FingerprintCollectorTimer>::c_specification;
  v19 = v3 + 64;
  v23 = 257;
  v20 = 0;
  v21 = 0;
  v22 = FingerprintCollectorStateMachine<FingerprintCollectorTimer>::EvtMachineDestroyedThunk;
  ProcessHeap = GetProcessHeap();
  v7 = (char *)HeapAlloc(ProcessHeap, 0, 0x420u);
  v8 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, 0x420u);
    *(_WORD *)(v8 + 965) = 257;
    v8[967] = 2;
    *v5 = v8;
    *((_QWORD *)v8 + 131) = v5;
    v9 = SmFx::StateMachineEngine::StateMachineEngineImpl::Initialize(
           (SmFx::StateMachineEngine::StateMachineEngineImpl *)v8,
           (const struct SmFx::STATE_MACHINE_ENGINE_CONFIG *)v18);
    if ( v9 < 0 )
    {
      v10 = (void (__fastcall *)(__int64))*((_QWORD *)v8 + 116);
      v11 = *((_QWORD *)v8 + 112);
      SmFx::StateMachineEngine::StateMachineEngineImpl::~StateMachineEngineImpl((SmFx::StateMachineEngine::StateMachineEngineImpl *)v8);
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v8);
      if ( !(unsigned int)Feature_UDFDOD__private_IsEnabledDeviceUsageNoInline(
                            v14,
                            v13,
                            v15,
                            v16,
                            *(_QWORD *)v18,
                            v19,
                            v20)
        && v10 )
      {
        v10(v11);
      }
      *v5 = 0;
    }
    else
    {
      v9 = 0;
    }
  }
  else
  {
    v9 = -1073741670;
  }
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\FingerprintCollectorTimers.h",
      (const char *)(unsigned int)v9,
      v18[0]);
  return a1;
}

```

## disassembly

```asm
0x18001db80  mov     r11, rsp
0x18001db83  push    rbx
0x18001db84  push    rbp
0x18001db85  push    rsi
0x18001db86  push    rdi
0x18001db87  push    r14
0x18001db89  push    r15
0x18001db8b  sub     rsp, 68h
0x18001db8f  mov     r14, rcx
0x18001db92  mov     ebp, 1
0x18001db97  mov     [rcx+8], ebp
0x18001db9a  mov     [rcx+0Ch], ebp
0x18001db9d  lea     rax, ??_7?$_Ref_count_obj2@VFingerprintCollectorTimer@@@std@@6B@; const std::_Ref_count_obj2<FingerprintCollectorTimer>::`vftable'
0x18001dba4  mov     [rcx], rax
0x18001dba7  lea     rdi, [rcx+10h]
0x18001dbab  mov     [r11+8], rdi
0x18001dbaf  mov     rbx, [rdx]
0x18001dbb2  mov     rcx, rdi; this
0x18001dbb5  call    ??0AsyncObjectBase@Foundation@Bluetooth@Microsoft@@QEAA@XZ; Microsoft::Bluetooth::Foundation::AsyncObjectBase::AsyncObjectBase(void)
0x18001dbba  mov     dword ptr [rdi+18h], 6670636Fh
0x18001dbc1  mov     qword ptr [rdi+20h], 0
0x18001dbc9  mov     qword ptr [rdi+28h], 0
0x18001dbd1  mov     qword ptr [rdi+30h], 0
0x18001dbd9  mov     qword ptr [rdi+38h], 0
0x18001dbe1  lea     rsi, [rdi+40h]
0x18001dbe5  mov     qword ptr [rsi], 0
0x18001dbec  lea     rax, ??_7FingerprintCollectorTimer@@6B@; const FingerprintCollectorTimer::`vftable'
0x18001dbf3  mov     [rdi], rax
0x18001dbf6  mov     [rdi+48h], rbx
0x18001dbfa  lea     rcx, [rdi+50h]
0x18001dbfe  call    ?Make@StateMachineTimer@Foundation@Bluetooth@Microsoft@@SA@XZ; Microsoft::Bluetooth::Foundation::StateMachineTimer::Make(void)
0x18001dc03  nop
0x18001dc04  mov     qword ptr [rdi+60h], 1Eh
0x18001dc0c  mov     [rsp+98h+var_46], 0
0x18001dc14  xor     eax, eax
0x18001dc16  mov     [rsp+98h+var_42], ax
0x18001dc1b  lea     rax, ?c_specification@?$FingerprintCollectorStateMachine@VFingerprintCollectorTimer@@@@0USTATE_MACHINE_SPECIFICATION@SmFx@@B; SmFx::STATE_MACHINE_SPECIFICATION const FingerprintCollectorStateMachine<FingerprintCollectorTimer>::c_specification
0x18001dc22  mov     qword ptr [rsp+98h+var_78], rax; int
0x18001dc27  mov     [rsp+98h+var_70], rsi
0x18001dc2c  mov     [rsp+98h+var_48], 101h
0x18001dc33  xorps   xmm0, xmm0
0x18001dc36  movdqu  [rsp+98h+var_68], xmm0
0x18001dc3c  mov     [rsp+98h+var_58], 0
0x18001dc45  lea     rax, ?EvtMachineDestroyedThunk@?$FingerprintCollectorStateMachine@VFingerprintCollectorTimer@@@@CAXPEAX@Z; FingerprintCollectorStateMachine<FingerprintCollectorTimer>::EvtMachineDestroyedThunk(void *)
0x18001dc4c  mov     [rsp+98h+var_50], rax
0x18001dc51  call    cs:__imp_GetProcessHeap
0x18001dc57  mov     rcx, rax; hHeap
0x18001dc5a  mov     edi, 420h
0x18001dc5f  mov     r8d, edi; dwBytes
0x18001dc62  xor     edx, edx; dwFlags
0x18001dc64  call    cs:__imp_HeapAlloc
0x18001dc6a  mov     rbx, rax
0x18001dc6d  test    rax, rax
0x18001dc70  jnz     short loc_18001DC7C
0x18001dc72  mov     edi, 0C000009Ah
0x18001dc77  jmp     loc_18001DD04
0x18001dc7c  mov     r8, rdi; Size
0x18001dc7f  xor     edx, edx; Val
0x18001dc81  mov     rcx, rbx; void *
0x18001dc84  call    memset_0
0x18001dc89  mov     word ptr [rbx+3C5h], 101h
0x18001dc92  mov     byte ptr [rbx+3C7h], 2
0x18001dc99  mov     [rsi], rbx
0x18001dc9c  mov     [rbx+418h], rsi
0x18001dca3  lea     rdx, [rsp+98h+var_78]; struct SmFx::STATE_MACHINE_ENGINE_CONFIG *
0x18001dca8  mov     rcx, rbx; this
0x18001dcab  call    ?Initialize@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAJAEBUSTATE_MACHINE_ENGINE_CONFIG@3@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::Initialize(SmFx::STATE_MACHINE_ENGINE_CONFIG const &)
0x18001dcb0  mov     edi, eax
0x18001dcb2  test    eax, eax
0x18001dcb4  js      short loc_18001DCBA
0x18001dcb6  xor     edi, edi
0x18001dcb8  jmp     short loc_18001DD04
0x18001dcba  mov     rbp, [rbx+3A0h]
0x18001dcc1  mov     r15, [rbx+380h]
0x18001dcc8  mov     rcx, rbx; this
0x18001dccb  call    ??1StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA@XZ; SmFx::StateMachineEngine::StateMachineEngineImpl::~StateMachineEngineImpl(void)
0x18001dcd0  call    cs:__imp_GetProcessHeap
0x18001dcd6  mov     rcx, rax; hHeap
0x18001dcd9  mov     r8, rbx; lpMem
0x18001dcdc  xor     edx, edx; dwFlags
0x18001dcde  call    cs:__imp_HeapFree
0x18001dce4  call    Feature_UDFDOD__private_IsEnabledDeviceUsageNoInline
0x18001dce9  test    eax, eax
0x18001dceb  jnz     short loc_18001DCFD
0x18001dced  test    rbp, rbp
0x18001dcf0  jz      short loc_18001DCFD
0x18001dcf2  mov     rcx, r15
0x18001dcf5  mov     rax, rbp
0x18001dcf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcfd  mov     qword ptr [rsi], 0
0x18001dd04  mov     rcx, [rsp+98h]; this
0x18001dd0c  test    edi, edi
0x18001dd0e  js      short loc_18001DD20
0x18001dd10  mov     rax, r14
0x18001dd13  add     rsp, 68h
0x18001dd17  pop     r15
0x18001dd19  pop     r14
0x18001dd1b  pop     rdi
0x18001dd1c  pop     rsi
0x18001dd1d  pop     rbp
0x18001dd1e  pop     rbx
0x18001dd1f  retn
0x18001dd20  mov     r9d, edi; char *
0x18001dd23  lea     r8, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x18001dd2a  mov     edx, 19h; void *
0x18001dd2f  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
